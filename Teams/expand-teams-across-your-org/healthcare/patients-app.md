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
description: Erfahren Sie, wie Sie elektronische Gesundheitswesen-Einträge mithilfe von F SIGNATURE-APIs in die App Microsoft Teams Patienten integrieren.
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

Dieser Artikel richtet sich an IT-Entwickler im Gesundheitswesen, die über ein medizinisches Informationssystem hinaus FSCHI-APIs zum Herstellen einer Verbindung mit ihrem Microsoft Teams. Dies ermöglicht Szenarien für die Behandlungskoordinierung, die den Anforderungen einer Organisation im Gesundheitswesen entsprechen.

In den verlinkten Artikeln werden die FHI-Schnittstellenspezifikationen für die App "Microsoft Teams-Patienten" dokumentiert, und in den folgenden Abschnitten wird erläutert, was erforderlich ist, um einen FKÄUFE-Server zu einrichten und eine Verbindung mit der Patienten-App in Ihrer Entwicklungsumgebung oder Ihrem Mandanten herzustellen. Außerdem müssen Sie mit der Dokumentation des von Ihnen ausgewählten FSCHI-Servers vertraut sein, der eine der unterstützten Optionen sein muss:

- Datica (über ihr [CMI-Angebot)](https://datica.com/compliant-managed-integration/)
- Infor Cloverleaf (über die [Infor FSCHI-Brücke)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redox (über [den R^FSCHI-Server)](https://www.redoxengine.com/fhir/)
- Dapasoft (über [Corolar auf FSCHI)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> Dieser Vorgang umfasst keine Schritte, die das Microsoft Teams Admin Center oder PowerShell-Cmdlets zum Aktivieren von Features verwenden. Die Konfiguration erfolgt ausschließlich auf der FSCHI-Server-/-Dienstseite und im Patienten-App-Client.

Im Folgenden wird die Architektur der Patienten-App veranschaulicht:

![Diagramm der Patienten-App-Architektur](../../media/patients-app-architecture.png)

In den folgenden Abschnitten werden die Anforderungen der Datenzugriffsschicht F AUSVERTEILT für die Patienten-App erläutert, die ein FSCHI-Server (oder EHR-fähige FSCHI-APIs) erfüllen muss, um die Patienten-App zu integrieren, einschließlich der folgenden:

- Erwartungen an die Benutzerauthentifizierung
- Funktionale und technische Anforderungen der Integrationsschnittstelle
- Erwartungen an Leistung und Zuverlässigkeit
- Erwartungen an F IMMER-Ressourcen, die bei der Patienten-App unterstützt werden sollen
- Prozess für Integration und erwartetes Einsatzmodell
- Erste Schritte mit F IMMER und einige häufige Herausforderungen bei der Patienten-App
- Zukünftige Anforderungen für die nächste Iteration der Patienten-App

> [!NOTE]
> In den folgenden Abschnitten bezieht sich das Wort "Partner" oder "Interop-Partner" auf eine beliebige Drittanbieterorganisation, die die Integration in EHR-Systeme für die Patienten-App über F IMMER ermöglicht und einen FKEHR-Server zur Übereinstimmung mit den aufgelisteten Spezifikationen implementieren.

## <a name="functional-and-technical-requirements"></a>Funktionale und technische Anforderungen  

### <a name="authentication"></a>Authentifizierung  

Die Autorisierung  auf App-Ebene ohne Unterstützung für die Autorisierung auf Benutzerebene ist die am häufigsten unterstützte Methode zum Durchführen von Datentransformationen und zum Verfügbar machen von Verbindungen mit EHR-Daten über FEHR, obwohl das EHR-System möglicherweise eine Benutzerautorisierung implementiert. Der Interop Service (Partner) erhält erhöhten Zugriff auf die EHR-Daten, und wenn er dieselben Daten verfügbar macht wie die entsprechenden FPERSONENBEZOGENE-Ressourcen, wird kein Autorisierungskontext an die Inop Service Consumer (die Patienten-App) weitergegeben, die in den Interop Service oder Platform integriert ist. Die Patienten-App kann die Autorisierung auf Benutzerebene nicht erzwingen, unterstützt aber die Anwendung auf Anwendungsauthentifizierung zwischen der Patienten-App und dem Dienst des Interop-Partners.

Das Authentifizierungsmodell "Anwendung auf Anwendung" wird unten beschrieben:

Die Dienst-zu-Dienst-Authentifizierung sollte über den OAuth [2.0-Clientanmeldeinformationsfluss ausgeführt werden.](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/) Der Partnerdienst muss Folgendes bereitstellen:

1. Der Partnerdienst ermöglicht es der Patienten-App, ein Konto bei dem Partner zu erstellen. Auf diese Weise kann die Patienten-App client_id und client_secret generieren und besitzen, die über ein Auth-Registrierungsportal auf dem Authentifizierungsserver des Partners verwaltet werden.

2. Der Partnerdienst besitzt das Authentifizierungs-/Autorisierungssystem, das die bereitgestellten Clientanmeldeinformationen akzeptiert und überprüft (authentifiziert) und wie unten beschrieben ein Zugriffstoken mit Mandantenhinweis zurückgibt.

3. Aus Sicherheitsgründen oder im Fall einer geheimen Verletzung kann die Patienten-App das Geheime erneut generieren und das alte Geheime erneut generieren oder löschen (ein Beispiel dafür finden Sie im Azure-Portal – AAD-App-Registrierung).

4. Der Metadatenendpunkt, der die Konformitätsausweisung hosten soll, sollte nicht authentifiziert werden, und der Zugriff auf ihn sollte ohne Authentifizierungstoken möglich sein.

5. Der Partnerdienst stellt den Tokenendpunkt für die Patienten-App zum Anfordern eines Zugriffstokens mithilfe eines Ablaufs der Clientanmeldeinformationen zur Verfügung. Die Token-URL gemäß Autorisierungsserver sollte Teil der FSCHI-Konformitäts-Anweisung (Capability) sein, die wie im folgenden Beispiel aus Metadaten auf dem F IMMER-Server abgerufen wird:

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

Der Partnerdienst stellt die App client_id und client_secret für Patienten zur Verfügung, die über ein Auth-Registrierungsportal auf Partnerseite verwaltet wird. Der Partnerdienst stellt den Endpunkt zum Anfordern eines Zugriffstokens mithilfe eines Ablaufs der Clientanmeldeinformationen zur Verfügung. Eine erfolgreiche Antwort muss die Parameter token_type, access_token und expires_in enthalten.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routing: Zuordnen des AAD-Mandanten zum Anbieterendpunkt

Die Patienten-App stellt eine Verbindung mit einem Partnerdienst über einen einzigen Endpunkt zusammen. Der Partnerdienst besitzt und verwaltet einen Mechanismus, mit dem jeder Microsoft-Kunde (AAD-Mandanten-ID) einem entsprechenden F IMMER-Server zugeordnet wird, mit dem der Partnerdienst arbeitet.

Für die Zuordnung des AAD-Mandanten zu einem Anbieterendpunkt wird die AAD-Mandanten-ID (GUID) verwendet. Die Patienten-App übergibt die Mandanten-ID im Leistungsumfang und fordert für jede Anforderung ein Zugriffstoken an. Der Partnerdienst behält die Zuordnung von Mandanten-ID zum Anbieterendpunkt bei und leitet Anforderungen basierend auf der Mandanten-ID an einen Anbieterendpunkt um. Zu diesem Zweck unterstützt der Partner die Konfiguration auf deren Seite (manuell oder über ein Portal als Teil des Onboardings von Anbieterorganisationen bei ihrer Interop-Plattform).

Der Authentifizierungs- und Routingworkflow wird unten dargestellt:

![Diagramm des Authentifizierungs- und Routingworkflows](../../media/Patient-app-6.png)

1. Anfordern des App-Zugriffstokens durch Senden:
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. Antworten mit einem App-Token:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Anfordern geschützter Daten mit Access-Token

4. Meldung zur Autorisierung: Wählen Sie den entsprechenden FTRAM-Server aus, zu dem die Route von der Mandanten-ID im Bereich ausgeführt werden soll.

5. Sendet nach der Authentifizierung mit dem App-Token geschützte Daten von dem autorisierten F DISTRIBUTOR-Server.

## <a name="interfaces"></a>Schnittstellen

Bestimmte Anrufe und Felder, die von der Patienten-App verwendet werden, sind in den folgenden Artikeln dokumentiert. Wählen Sie die Schnittstelle aus, die für Ihre F JEWEILIGEN Server-/FLEKTOR-APIs gilt.

- [Benutzeroberflächenspezifikation DSTU2](dstu2-interface.md)
- [Benutzeroberflächenspezifikation STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Leistung und Zuverlässigkeit

Während sich die Patienten-App in einer privaten Vorschau befindet, gibt es keine Garantien für die End-to-End-Leistung. Zu den Leistungsfaktoren zählen die relative Latenz aller am Workflow beteiligten Hops, angefangen von der EHR in der Umgebung des Gesundheitssystems bis zum Interop-Partner und deren Infra, einschließlich des FKEHR-Servers und des Wegs zum Office 365-Ökosystem und zur Patienten-App.

![Abbildung der Leistung von Interop-Partnern](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Erste Schritte mit F IMMER  

Wenn Sie noch nicht mit F UNTR in Verbindung stehen und einfachen Zugriff auf einen F IMMER-Server benötigen, den Sie über die EHR-Integrationsschnittstelle von Microsoft Teams verfügbar machen können, steht Microsoft ein Open-Source-F TYP Server zur Verfügung, der von allen Entwicklern verwendet werden kann. Lesen Sie den [Artikel Was ist FSCHI-Server](/azure/healthcare-apis/overview-open-source-server) für Azure, wenn Sie mehr über den von Microsoft verfügbaren Open Source-F IMMER-Server erfahren und ihn für Ihre Organisationen bereitstellen möchten.

Sie können auch die HSPC Open Sandbox EHR-Umgebung verwenden, um eine EHR zu erstellen, die auch einen offenen FSCHI-Server unterstützt, und diese Umgebung verwenden, um mit der Patienten-App zu spielen. Wir empfehlen, die [HSPC-Sandbox-Dokumentation durchlesen zu können.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) Der Sandkasten bietet nicht nur eine einfache, UI-orientierte und benutzerfreundliche Möglichkeit zum Erstellen, Hinzufügen und Bearbeiten von Patienten, sondern bietet ihnen auch mehrere Beispiele für die ersten Schritte.