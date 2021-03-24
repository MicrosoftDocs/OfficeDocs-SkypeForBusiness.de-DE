---
title: Übersicht über die Patienten-App
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Erfahren Sie mehr über die Integration von elektronischen Krankenakten in die Microsoft Teams-Patienten-App mithilfe von FHIR-APIs.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096209"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams

> [!NOTE]
> Mit Wirkung vom 30. Oktober 2020 wurde die App "Patienten" zurückgezogen und durch die App [Listen ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Microsoft Teams ersetzt. Die Daten der Patienten-App werden in dem Gruppenpostfach der Office 365-Gruppe gespeichert, das zum Team gehört. Alle der Patienten-App zugeordneten Daten bleiben in dieser Gruppe erhalten, auf sie kann aber nicht mehr über die Benutzeroberfläche zugegriffen werden. Benutzer können ihre Listen mithilfe der App [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) neu erstellen.
>
>Mit der Listen-App können Pflegeteams in Ihrer Organisation im Gesundheitswesen Patientenlisten für Szenarien erstellen, die von Visiten und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen. Sehen Sie sich die Vorlage "Patienten" in der Listen-App an, um die ersten Schritte zu unternehmen. Weitere Informationen zum Verwalten der Listen-App in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Dieser Artikel richtet sich an einen allgemeinen IT-Entwickler im Gesundheitswesen, der über ein medizinisches Informationssystem FHIR-APIs verwenden möchte, um eine Verbindung mit Microsoft Teams herzustellen. Dies würde Szenarien für die Pflegekoordinierung ermöglichen, die den Anforderungen einer Gesundheitsorganisation entsprechen.

In verknüpften Artikeln werden die FHIR-Schnittstellenspezifikationen für die Microsoft Teams-Patienten-App dokumentiert, und in den folgenden Abschnitten wird erläutert, was zum Einrichten eines FHIR-Servers und zum Herstellen einer Verbindung mit der Patienten-App in Ihrer Entwicklungsumgebung oder Ihrem Mandanten erforderlich ist. Außerdem müssen Sie mit der Dokumentation des von Ihnen ausgewählten FHIR-Servers vertraut sein, der eine der unterstützten Optionen sein muss:

- Datica (über ihr [CMI-Angebot)](https://datica.com/compliant-managed-integration/)
- Infor Cloverleaf (über die [Infor FHIR-Brücke)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redox (über den [R^FHIR-Server)](https://www.redoxengine.com/fhir/)
- Dapasoft (über [Corolar auf FHIR)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> Dieser Vorgang umfasst keine Schritte, die das Microsoft Teams Admin Center oder die PowerShell-Cmdlets zum Aktivieren von Features verwenden. Die Konfiguration erfolgt vollständig auf der Server-/Dienstseite von FHIR und im Client der Patienten-App.

Nachstehend wird die Architektur der Patienten-App veranschaulicht:

![Diagramm der Patienten-App-Architektur](../../media/patients-app-architecture.png)

In den folgenden Abschnitten werden die Anforderungen der Datenzugriffsebene nur für die FHIR für die Patienten-App erläutert, die ein FHIR-Server (oder EHR-aktivierte FHIR-APIs) erfüllen muss, um in die Patienten-App integriert zu werden, einschließlich der folgenden:

- Erwartungen an die Benutzerauthentifizierung
- Funktionale und technische Anforderungen der Integrationsschnittstelle
- Erwartungen an Leistung und Zuverlässigkeit
- Erwartungen an FHIR-Ressourcen, die für die Patienten-App unterstützt werden sollen
- Prozess für die Integration und das erwartete Engagementmodell
- Erste Schritte mit FHIR und einigen häufigen Herausforderungen mit der Patienten-App
- Zukünftige Anforderungen für die nächste Iteration der Patienten-App

> [!NOTE]
> In den folgenden Abschnitten wird das Wort "Partner" oder "In-App-Partner" verwendet, um sich auf eine Drittanbieterorganisation zu beziehen, die die Integration in EHR-Systeme für die Patienten-App über FHIR ermöglicht und einen FHIR-Server zur Übereinstimmung mit den aufgeführten Spezifikationen verwendet.

## <a name="functional-and-technical-requirements"></a>Funktionale und technische Anforderungen  

### <a name="authentication"></a>Authentifizierung  

Die Autorisierung  auf App-Ebene ohne Unterstützung für die Autorisierung auf Benutzerebene ist die am häufigsten unterstützte Möglichkeit, Datentransformationen durchzuführen und Verbindungen mit EHR-Daten über FHIR verfügbar zu machen, obwohl das EHR-System möglicherweise die Autorisierung auf Benutzerebene implementiert. Der Interop Service (Partner) erhält erhöhten Zugriff auf die EHR-Daten, und wenn dieselben Daten wie die entsprechenden FHIR-Ressourcen verfügbar gemacht werden, wird kein Autorisierungskontext an den Inop Service Consumer (die Patienten-App) übergeben, der in den InopDienst oder die Plattform integriert ist. Die Patienten-App kann keine Autorisierung auf Benutzerebene erzwingen, unterstützt aber die Anwendung zur Anwendungsauthentifizierung zwischen der Patienten-App und dem Dienst des Inop-Partners.

Das Authentifizierungsmodell "Anwendung auf Anwendung" wird unten beschrieben:

Die Dienst-zu-Dienst-Authentifizierung sollte über den OAuth [2.0-Clientanmeldeinformationenfluss ausgeführt werden.](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/) Der Partnerdienst muss Folgendes bereitstellen:

1. Der Partnerdienst ermöglicht es der Patienten-App, ein Konto beim Partner zu erstellen, mit dem die Patienten-App client_id und client_secret generieren und besitzen kann, die über ein Auth-Registrierungsportal auf dem Authentifizierungsserver des Partners verwaltet werden.

2. Der Partnerdienst besitzt das Authentifizierungs-/Autorisierungssystem, das die bereitgestellten Clientanmeldeinformationen akzeptiert und überprüft (authentifiziert) und wie unten beschrieben ein Zugriffstoken mit Mandantenhinweis zurückgibt.

3. Aus Sicherheitsgründen oder im Fall einer geheimen Verletzung kann die Patienten-App das Geheimnis erneut generieren und das alte Geheimnis ungültig oder löschen (ein Beispiel dafür finden Sie im Azure Portal – AAD-App-Registrierung).

4. Der Metadatenendpunkt, der die Konformitätsausweisung hostt, sollte nicht authentifiziert sein, er sollte ohne Authentifizierungstoken zugänglich sein.

5. Der Partnerdienst stellt den Tokenendpunkt für die Patienten-App zum Anfordern eines Zugriffstokens mithilfe eines Clientanmeldeinformationenflusses zur Verfügung. Die Token-URL nach Autorisierungsserver sollte Teil der FHIR-Konformitäts-Anweisung (Funktion) sein, die wie in diesem Beispiel aus Metadaten auf dem FHIR-Server abgerufen wird:

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

Eine Anforderung für ein Zugriffstoken besteht aus den folgenden Parametern:

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

Der Partnerdienst stellt die app client_id und client_secret für Patienten zur Verfügung, die über ein Registrierungsportal für Auth auf der Seite des Partners verwaltet wird. Der Partnerdienst stellt den Endpunkt zum Anfordern eines Zugriffstokens mithilfe eines Clientanmeldeinformationenflusses zur Verfügung. Eine erfolgreiche Antwort muss die Parameter token_type, access_token und expires_in enthalten.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routing: Zuordnen des AAD-Mandanten zum Anbieterendpunkt

Die Patienten-App stellt eine Verbindung mit einem Partnerdienst über einen einzelnen Endpunkt zur Verfügung. Der Partnerdienst besitzt und verwaltet einen Mechanismus, mit dem jeder Microsoft-Kunde (AAD-Mandanten-ID) einem entsprechenden Anbieter für Gesundheitswesen (FHIR-Server) zugeordnet wird, mit dem der Partnerdienst arbeitet.

Beim Zuordnen des AAD-Mandanten zu einem Anbieterendpunkt wird die AAD-Mandanten-ID (GUID) verwendet. Die Patienten-App übergibt die Mandanten-ID im Bereich, während sie ein Zugriffstoken für jede Anforderung anfordert. Der Partnerdienst behält die Zuordnung der Mandanten-ID zum Anbieterendpunkt bei und leitet Anforderungen basierend auf der Mandanten-ID an einen Anbieterendpunkt um. Zu diesem Zweck unterstützt der Partner die Konfiguration am Ende (manuell oder über ein Portal als Teil des Onboardings von Anbieterorganisationen zu seiner In-App-Plattform).

Der Authentifizierungs- und Routingworkflow wird unten angezeigt:

![Diagramm des Authentifizierungs- und Routingworkflows](../../media/Patient-app-6.png)

1. Anfordern eines App-Zugriffstokens durch Senden:
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. Antworten Sie mit einem App-Token:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Anfordern geschützter Daten mit Access-Token.

4. Autorisierungsmeldung: Wählen Sie den geeigneten FHIR-Server aus, an den die Route von mandanten-ID im Bereich gesendet werden soll.

5. Sendet die app-geschützten Daten vom autorisierten FHIR-Server nach der Authentifizierung mit dem App-Token.

## <a name="interfaces"></a>Schnittstellen

Bestimmte Anrufe und Felder, die von der Patienten-App verwendet werden, sind in den folgenden Artikeln dokumentiert. Wählen Sie die Schnittstelle aus, die für Ihre FHIR-Server-/FHIR-APIs gilt.

- [Benutzeroberflächenspezifikation DSTU2](dstu2-interface.md)
- [Benutzeroberflächenspezifikation STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Leistung und Zuverlässigkeit

Während sich die Patienten-App in der privaten Vorschau befindet, gibt es keine Garantien für die End-to-End-Leistung. Zu den Leistungsfaktoren zählen die relative Latenz aller hops, die am Workflow beteiligt sind, angefangen von der EHR in der Umgebung des Integritätssystems bis zum Infrapartner und deren Infra, einschließlich des FHIR-Servers und der Office 365-Ökosystem- und Patienten-App.

![Abbildung der Leistung von Interop-Partnern](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Erste Schritte mit FHIR  

Wenn Sie noch nicht mit FHIR arbeiten und einfachen Zugriff auf einen FHIR-Server benötigen, den Sie für die Microsoft Teams EHR-Integrationsschnittstelle verfügbar machen können, verfügt Microsoft über einen Open-Source-FHIR-Server, der für alle Entwickler verfügbar ist. Weitere Informationen zum von Microsoft verfügbaren Open Source FHIR Server finden Sie im Artikel Was ist [FHIR Server für Azure,](/azure/healthcare-apis/overview-open-source-server) und stellen Sie ihn für Ihre Organisationen bereit.

Sie können auch die HSPC Open Sandbox EHR-Umgebung verwenden, um eine EHR zu erstellen, die auch einen geöffneten FHIR-Server unterstützt und dies zum Spielen mit der Patienten-App verwendet. Wir empfehlen, die [HSPC-Sandkastendokumentation zu lesen.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) Der Sandkasten bietet nicht nur eine einfache, UI-orientierte und benutzerfreundliche Möglichkeit zum Erstellen, Hinzufügen und Bearbeiten von Patienten, sondern bietet ihnen auch mehrere Beispiele für die ersten Schritte.