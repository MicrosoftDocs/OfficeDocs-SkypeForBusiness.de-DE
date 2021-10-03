---
title: Exportieren von Inhalten mit Microsoft Teams Export-APIs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In diesem Artikel erfahren Sie, wie Sie Inhalte mithilfe der Teams Exportieren-APIs Microsoft Teams exportieren.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082865"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportieren von Inhalten mit Microsoft Teams Export-APIs

Teams Mit Export-APIs können Sie 1:1-, Gruppenchats, Besprechungschats und Kanalnachrichten aus Microsoft Teams. Wenn Ihre Organisation Nachrichten exportieren Microsoft Teams muss, können Sie diese mithilfe der Export-APIs Teams extrahieren. *Chatnachricht* stellt eine einzelne Chatnachricht in einem [Kanal oder Chat](/graph/api/resources/channel?view=graph-rest-beta) [dar.](/graph/api/resources/chat?view=graph-rest-beta) Bei der Chatnachricht kann es sich um eine Chat-Stammnachricht oder um einen Teil eines Antwortthreads handelt, der durch die **replyToId-Eigenschaft** in der Chatnachricht definiert ist.

Im Folgenden finden Sie einige Beispiele für die Verwendung dieser Export-APIs:

- **Beispiel 1:** Wenn Sie Microsoft Teams in Ihrer Organisation aktiviert haben und alle Microsoft Teams-Nachrichten programmgesteuert nach Datum exportieren möchten, indem Sie den Datumsbereich für einen bestimmten Benutzer oder ein bestimmtes Team übergeben.
- **Beispiel 2:** Wenn Sie alle Benutzer- oder Teamnachrichten pro Tag programmgesteuert exportieren möchten, indem Sie einen Datumsbereich bereitstellen. Export-APIs können alle Nachrichten abrufen, die während des angegebenen Datumsbereichs erstellt oder aktualisiert wurden.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Was wird von den Export-Teams-APIs unterstützt?

- Massenexport von **Teams-Nachrichten:** Teams Mit diesen Grenzwerten sollten Sie in der Lage sein, Massenexporte von E-Mails Teams-Nachrichten zu exportieren.
- **Anwendungskontext:** Zum Aufrufen von Microsoft Graph muss Ihre App ein Zugriffstoken von der App Microsoft Identity Platform. Das Zugriffstoken enthält Informationen zu Ihrer App sowie die Berechtigungen, über die sie für die Ressourcen und APIs verfügt, die über Microsoft Graph. Um ein Zugriffstoken zu erhalten, muss Ihre App beim Microsoft Identity Platform registriert sein und entweder von einem Benutzer oder einem Administrator für den Zugriff auf die benötigten Microsoft Graph-Ressourcen autorisiert werden.

    Wenn Sie bereits mit der Integration einer App in den Microsoft Identity Platform [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) zum Erhalten von Token vertraut sind, finden Sie Im Abschnitt Nächste Schritte Informationen und Beispiele für Microsoft-spezifische Graph.
- **Hybridumgebung:** Export-APIs unterstützen Nachrichten, die von Benutzern gesendet werden, die in einer Hybridumgebung (lokale Bereitstellung Exchange und Teams) bereitgestellt werden. Auf Alle Nachrichten, die von Benutzern gesendet werden, die für die Hybridumgebung konfiguriert sind, kann mithilfe von Export-APIs zugegriffen werden.
- **Gelöschte Nachrichten des Benutzers:** Auf Nachrichten, die von Benutzern aus dem Teams-Client gelöscht wurden, kann bis zu 21 Tage nach dem Löschvorgang mithilfe von Export-APIs zugegriffen werden.
- **Nachrichtenanlagen:** Export-APIs enthalten die Links zu den Anlagen, die als Teil von Nachrichten gesendet werden. Mithilfe von Export-APIs können Sie die in den Nachrichten angefügten Dateien abrufen.
- **Eigenschaften von Chatnachrichten:** Hier finden Sie die vollständige Liste der Eigenschaften, Teams Export-APIs [unterstützt werden.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

>[!NOTE]
>Export-APIs unterstützen keine *Reaktionen.*

## <a name="how-to-access-teams-export-apis"></a>Zugreifen auf die Teams-APIs

- **Beispiel 1** ist eine einfache Abfrage, mit der Sie alle Nachrichten eines Benutzers oder Teams ohne Filter abrufen können:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **Beispiel 2** ist eine Beispielabfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams durch Angabe von Datums-/Uhrzeitfiltern und den 50 obersten Nachrichten:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>Die API gibt bei mehreren Ergebnissen eine Antwort mit dem Link zur nächsten Seite zurück. Rufen Sie zum Abrufen der nächsten Gruppe von Ergebnissen einfach get für die URL von @odata.nextlink auf. Wenn @odata.nextlink nicht oder NULL ist, werden alle Nachrichten abgerufen.

## <a name="prerequisites-to-access-teams-export-apis"></a>Voraussetzungen für den Zugriff auf Teams Export-APIs 

- Microsoft Teams APIs in Microsoft Graph, die auf vertrauliche Daten zugreifen, werden als geschützte APIs betrachtet. Export-APIs erfordern eine zusätzliche Überprüfung, die über Berechtigungen und Zustimmung hinaus geht, bevor Sie sie verwenden können. Um Zugriff auf diese geschützten APIs an fordern, füllen Sie das [Anforderungsformular aus.](https://aka.ms/teamsgraph/requestaccess)
- Anwendungsberechtigungen werden von Apps verwendet, die ausgeführt werden, ohne dass ein angemeldeter Benutzer anwesend ist. Anwendungsberechtigungen können nur von einem Administrator erteilt werden. Die folgenden Berechtigungen sind erforderlich:

    - *Chat.Read.All:* Ermöglicht den Zugriff auf alle 1:1-, Gruppen- und Besprechungschatnachrichten. 
    - *ChannelMessage.Read.All:* Ermöglicht den Zugriff auf alle Kanalnachrichten.  
    - *User.Read.All:* Ermöglicht den Zugriff auf die Liste der Benutzer für einen Mandanten.

## <a name="license-requirements-for-teams-export-apis"></a>Lizenzanforderungen für Teams Export-APIs

Die Export-API unterstützt Security and Compliance (S+C) und allgemeine Verwendungsszenarien über einen Modellabfrageparameter. S+C-Szenarien (Modell A) umfassen Startkapazität und erfordern ein E5-Abonnement sowie allgemeine Nutzungsszenarien (Modell B), die für alle Abonnements verfügbar sind und nur für den Verbrauch verfügbar sind. Weitere Informationen zu Startkapazitäts- und -nutzungsgebühren finden Sie unter Lizenzierungs- und Zahlungsanforderungen für [Microsoft Graph Teams-APIs.](/graph/teams-licenses)

### <a name="scmodel-a-scenarios"></a>S+C/Modell A-Szenarien

Eingeschränkt auf Anwendungen, die Sicherheits- und/oder Compliancefunktionen ausführen, müssen Benutzer über bestimmte E5-Lizenzen verfügen, um diese Funktionalität nutzen und Startkapazität erhalten zu können. Die Startkapazität wird pro Benutzer berechnet und pro Monat berechnet und auf Mandantenebene aggregiert. Für die Nutzung, die über die Startkapazität hinaus geht, wird den App-Besitzern die API-Nutzung in Rechnung gerechnet. Modell A kann nur auf Nachrichten von Benutzern mit einer zugewiesenen E5-Lizenz zugreifen.

### <a name="general-usagemodel-b-scenarios"></a>Allgemeine Verwendung/Modell B-Szenarien

Verfügbar für alle Nicht-S+C-bezogenen Szenarien, es gibt keine Lizenzanforderungen oder Startkapazität. Wenn Verbrauchszähler verfügbar werden, werden die App-Besitzer für alle monatlichen API-Aufrufe in Rechnung gestellt. 

### <a name="evaluation-mode-default"></a>Auswertungsmodus (Standard)

Keine Modelldeklaration ermöglicht den Zugriff auf APIs mit eingeschränkter Verwendung pro Anforderung zur Auswertung. 

## <a name="json-representation"></a>JSON-Darstellung

Das folgende Beispiel ist eine JSON-Darstellung der Ressource:

Namespace: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Weitere Informationen zur ChatMessage-Ressource finden Sie im Artikel zum [Ressourcentyp chatMessage.](/graph/api/resources/chatmessage)