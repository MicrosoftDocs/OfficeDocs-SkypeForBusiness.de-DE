---
title: Patienten app-Übersicht
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integration von Microsoft-Teams Patienten app EHR
ms.openlocfilehash: 25eb1b4ee09eec8395db2ac821d19624a508c937
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643113"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integrieren von elektronische Datensätze aus dem Gesundheitswesen in Microsoft-Teams

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Dieser Artikel richtet eine allgemeine Gesundheitswesen interessiert FHIR APIs auf der Basis eines Systems medizinische Informationen zu Microsoft-Teams, Herstellen einer Verbindung mithilfe von IT-Entwickler. Auf diese Weise Vorsicht Koordinierung Szenarien können, die die Anforderungen einer Organisation aus dem Gesundheitswesen entsprechen.

In diesem Artikel Dokumente FHIR Schnittstellenspezifikationen für die Microsoft-Teams Patienten-app und Grundlegendes zu, die für das Einrichten eines Servers FHIR und Herstellen einer Verbindung mit der Patienten-app in der Entwicklung Environment\tenant erforderlich ist. Sie müssen auch machen Sie sich vertraut mit der Dokumentation für den FHIR-Server, den Sie ausgewählt haben, den muss eine der unterstützten Optionen:
- Datica (über das Angebot [CMI](https://datica.com/compliant-managed-integration/) )
- An Cloverleaf (über die [An FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (über die [R ^ FHIR Server](https://www.redoxengine.com/fhir/))
- Dapasoft (durch [Klicken auf FHIR Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Dieser Prozess wird nicht enthält die Schritte, die das Microsoft-Teams, Administrationscenter oder die PowerShell-Cmdlets verwenden, um Features zu aktivieren. Die Konfiguration erfolgt vollständig auf der Seite FHIR Server-Dienst und in der Patienten app-Client.

Unten dargestellt ist die Architektur der Patienten-app:

![Architektur der Patienten-app](../../media/patients-app-architecture.png)

Den folgenden Abschnitten werden die Anforderungen von der FHIR-only Datenzugriffsschicht für die app Patienten, die einen FHIR-Server (oder EHR FHIR APIs aktiviert), um mit der Patienten-app, einschließlich der folgenden integrieren erfüllen müssen:

- Die Erwartungen um Benutzerauthentifizierung
- Funktionale und technische Anforderungen der Integrationsschnittstelle
- Die Erwartungen um Leistung und Zuverlässigkeit
- Voraussichtliche um FHIR Ressourcen für die Patienten app unterstützt werden
- Prozess für die Integration und der erwarteten Engagement-Modell
- Gewusst wie: Registrieren Sie sich selbst und Ihren Kunden in der privaten Vorschau der Patienten-app
- Erste Schritte mit FHIR und einige allgemeinen Herausforderungen mit der Patienten-app
- Zukünftige Anforderungen für die nächste Iteration der Patienten-app

> [!NOTE]
> In den folgenden Abschnitten wird das Wort "Partner" oder "Interop-Partner" auf einer 3. Partei Organisation verweisen, ermöglicht die Integration in EHR Systeme für die app Patienten über FHIR und einem FHIR Server entsprechend die aufgelisteten Spezifikationen implementiert.

## <a name="functional-and-technical-requirements"></a>Funktionale und technische Anforderungen  

### <a name="authentication"></a>Authentifizierung  

App-Autorisierung *mit keine Unterstützung für die Autorisierung des Benutzers auf* ist die am häufigsten unterstützte Möglichkeit zum Datentransformationen ausführen und Verfügbarmachen von Verbindungen mit EHR Daten über FHIR, obwohl das System EHR Ebene benutzerautorisierung implementieren kann . Ruft der Interop-Dienst (Partner) mit erhöhten Rechten Zugriff auf die EHR Daten, und wenn sie die gleichen Daten wie die entsprechenden FHIR Ressourcen verfügbar machen es gibt keinen Autorisierungskontext an der Interop Dienstconsumer (der Patienten app) übergeben integrieren in der Interopassembly Dienst oder einer anderen Plattform. Die app Patienten werden nicht Ebene benutzerautorisierung erzwingen, aber Anwendung Authentifizierung zwischen der app Patienten und des Partners Interop-Dienst unterstützt.

Das Anwendung Authentifizierungsmodell wird im folgenden beschrieben:

Dienst-Authentifizierungen sollte über OAuth 2.0 [Clientanmeldeinformationen Fluss](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)ausgeführt werden. Der Partner-Dienst muss Folgendes sicherstellen:

1. Der Partnerservice ermöglicht die Patienten-app erstellen Sie ein Konto mit dem Partner, wodurch die Patienten-app zu generieren und eigene Client_id und Client_secret, über ein Auth Registrierung Portal auf den Partner Authentifizierungsserver verwaltet.
2. Der Partnerservice besitzt das System Authentifizierung, die akzeptiert und überprüft (authentifiziert) der Client bereitgestellten Anmeldeinformationen und benennt wieder ein Zugriffstoken mit Mandanten Hinweis im Gültigkeitsbereich, wie unten beschrieben.
3. Aus Sicherheitsgründen oder in dem Fall eine geheime Verletzung kann die Patienten-app den geheimen Schlüssel erneut generieren und ungültig oder löschen den alten Schlüssel (Beispiel der gleichen ist in Azure-Verwaltungsportal - AAD App-Registrierung verfügbar)
4. Der Hosten der Konformitätserklärung Metadatenendpunkt sollten nicht authentifizierte, ohne Authentifizierungstoken zugegriffen wird.
5. Der Partnerservice bietet den token Endpunkt für die app Patienten ein Zugriffstoken mit einem Client Anmeldeinformationen Flow anfordern. Die token Url gemäß den Anweisungen in autorisierungsserver sollte Teil der FHIR (Funktion) die Konformität Anweisung aus Metadaten abgerufen werden, auf dem Server FHIR wie in diesem Beispiel werden:

![Patienten app 5](../../media/Patient-app-5.png)

Eine Anforderung für ein Zugriffstoken umfasst die folgenden Parameter:

    POST /token HTTP/1.1
    Host: authorization-server.com

    grant-type=client_credentials
    &client_id=xxxxxxxxxx
    &client_secret=xxxxxxxxxx

Die Partnerservice bietet Client_id und Client_secret für Patienten-app, die über ein Auth Registrierung Portal aufseiten des Partners verwaltet. Die Partner-Webdienst stellt den Endpunkt Anforderung Zugriffstoken mit einem Client Anmeldeinformationen Flow bereit. Eine erfolgreiche Antwort muss der Parameter Token_type, Access_token und Expires_in enthalten.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routing: Zuordnung AAD Mandanten an den Anbieter-Endpunkt

Die Patienten app stellt eine Verbindung mit einem Partner-Dienst über einen einzelnen Endpunkt. Der Partner-Dienst besitzt und verwaltet einen Mechanismus zum Zuordnen von jedem Microsoft-Kunden (AAD Mandanten-ID) zu einem entsprechenden aus dem Gesundheitswesen-Anbieter (FHIR Server), mit denen der Partnerservice arbeitet.

Zuordnen von den Mandanten AAD an einen Anbieterendpunkt verwendet AAD Mandanten-ID (GUID). Die Patienten app übergibt die Mandanten-ID im Bereich, während ein Zugriffstoken bei jeder Anforderung anfordern. Der Partnerservice behält die Zuordnung der Mandanten-ID an Anbieterendpunkt und leitet Anforderungen an einen Anbieterendpunkt basierend auf die Mandanten-ID Zu diesem Zweck unterstützt der Partner die Konfiguration ihrem Ende an (manuell oder über ein Portal als Bestandteil der Anbieter Organisationen ihre Interop-Plattform Onboarding).

Der Authentifizierung und Routing Workflow sieht folgendermaßen aus:

![Patienten app 6](../../media/Patient-app-6.png)

1. Anforderung für app-Zugriffstoken durch senden:
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. Antworten Sie mit einer app-Token:

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. Geschützte Daten mit Zugriffstoken anfordern.
4. Autorisierung Nachricht: Wählen Sie den entsprechenden FHIR Server zum Weiterleiten an aus Mandanten-ID im Bereich
5. Sendet die app geschützte Daten vom autorisierten FHIR Server nach der Authentifizierung mit dem app-Token.

## <a name="interfaces"></a>Schnittstellen

Bestimmte Aufrufe und wird von der app Patienten Felder sind in den folgenden Artikeln dokumentiert. Wählen Sie die Schnittstelle für Ihre FHIR Server/FHIR APIs gelten.

- [DSTU2 Interface-Spezifikation](dstu2-interface.md)
- [STU3 Interface-Spezifikation](stu3-interface.md)

## <a name="performance-and-reliability"></a>Leistung und Zuverlässigkeit

Während der app Patienten private Preview liegt, gibt es keine Garantie auf die End-to-End-Leistung. Die relativen Wartezeiten der alle Hops beteiligt des Workflows, beginnend mit dem Interop-Partner die EKA in die Integrität des Systems-Umgebung die folgenden Faktoren in Leistung und ihre Infrarot, einschließlich der FHIR Server und über zu Office 365-Ökosystem und Patienten-app.

![Interop-Partner](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Erste Schritte mit FHIR  

Wenn Sie neu sind FHIR und Sie benötigen Zugriff auf einen FHIR-Server, die Sie auf die Microsoft-Teams EHR Integrationsschnittstelle verfügbar machen können, hat Microsoft eine Open-Source-FHIR-Server für alle Entwickler verwenden. Finden Sie Artikel [Was ist FHIR Server für Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) erfahren mehr über die open-Source-FHIR Server Supportoptionen von Microsoft und für Ihre Organisationen bereitgestellt.

Sie können auch die HSPC öffnen EHR sandkastenumgebung zum Erstellen einer ein EHR die ebenfalls unterstützt open FHIR Server und Hiermit können Sie mit der app Patienten experimentieren. Es wird empfohlen, dass Sie durch die [HSPC Sandkasten-Dokumentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)gelesen. Nicht nur Sandkasten bietet eine einfache Benutzeroberfläche und den benutzerfreundlichen Weise erstellen, hinzufügen und Bearbeiten von Patienten außerdem haben Sie Reihe von Beispielen für den Einstieg.  

## <a name="enroll-in-the-private-preview"></a>In der privaten Preview registrieren

Nachdem Sie die open-Source Server FHIR erstellt haben, ist es wirklich einfach die Patienten app innerhalb Ihres Mandanten herstellen einer Verbindung mithilfe der unten aufgeführten Schritte:

1. [So erreichen Sie uns](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) , mit den folgenden anfänglichen Angaben:  
    - Ihr Name 
    - Ihre Position 
    - Der Firma oder Organisation, die Sie darstellen
    - Warum Sie die Patienten-app für die Integration von EHR interessiert sind. 

    Wir erhalten Sie so bald wie möglich mit weiteren Fragen und führen Sie durch einen Prozess zum Abrufen von Setup für die private Vorschau.

2. Stellen Sie sicher, Sideloading benutzerdefinierten apps in den Mandanten werden soll, auf dem die Patienten app testen aktiviert ist. Näheres [App Berechtigungsrichtlinien](../../admin-settings.md) erfahren, wie dies im Teams Admin Center für Ihre oder der Mandant des Kunden einschalten.

3. Sideload der Patienten-app-Manifestdatei, dass Sie von Microsoft erhalten werden (nachdem wir uns Ihre e-Mails verarbeiten) in einem Team in den Mandanten, der für die Pflege-Koordinierung und Patienten Rundung Szenarien verwendet werden. Ausführliche Informationen dazu, wie auf der Seite eine app laden befinden sich in [einer app-Paket für Microsoft-Teams hochladen](/microsoftteams/platform/concepts/apps/apps-upload)

4. Navigieren Sie zu den allgemeinen DDE-Kanal als Besitzer Team, und klicken Sie dann auf die Registerkarte Patienten. Sollte angezeigt werden, dass eine erste Textlauf Erfahrung, die zwei dargestellt werden, d. h. EHR und manuellen Modus Optionen. Wählen Sie den **Modus EHR** , und kopieren Sie den Endpunkt des FHIR Servers (, die nur Setup zuvor mit allen erforderlichen Daten und Ressourcen entsprechend den oben-Spezifikationen haben) in das Feld Link, und benennen Sie der Verbindung, die auch die FHIR Server darstellt. Klicken Sie auf Verbinden, und alles sein bereit.

    ![App-servereinstellungen Patienten](../../media/patients-server.png)

5. Starten Sie mithilfe der app Patienten aus FHIR Server/EHR suchen und diese zu einer Liste hinzufügen und geben [uns Feedback geben](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) , wenn etwas nicht funktioniert. Darüber hinaus herstellen eine vollständig authentifizierte Version der app Patienten-> FHIR-Server-Fluss Bitte Teilnahme offline Dialog mit Microsoft-Teams, für das Produkt aus dem Gesundheitswesen engineering, über die e-Mail-Anforderung erwähnten um Anforderungen zu verdeutlichen, und wir Hilfe hierzu für Sie pro im Dokument FHIR Schnittstelle oben beschriebenen Anforderungen für die Authentifizierung.  


