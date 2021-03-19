---
title: Exportieren von Inhalten mit den Microsoft Teams-Export-APIs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In diesem Artikel erfahren Sie, wie Sie Teams-Inhalte mithilfe der Microsoft Teams-Export-APIs exportieren.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1bca4eb70bff07e809630e1b997f377064b5e0e
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861409"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportieren von Inhalten mit den Microsoft Teams-Export-APIs

Mit Den Export-APIs von Teams können Sie 1:1-, Gruppenchat- und Kanalnachrichten aus Microsoft Teams exportieren. Wenn Ihre Organisation Microsoft Teams-Nachrichten exportieren muss, können Sie sie mithilfe von Teams Export-APIs extrahieren. *Chatnachricht* stellt eine einzelne Chatnachricht innerhalb eines [Kanals oder Chats](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) [dar.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) Die Chatnachricht kann eine Stammchatnachricht oder ein Teil eines Antwortthreads sein, der durch die **eigenschaft replyToId** in der Chatnachricht definiert wird.

Hier sind einige Beispiele für die Verwendung dieser Export-APIs:

- **Beispiel 1:** Wenn Sie Microsoft Teams in Ihrer Organisation aktiviert haben und alle Microsoft Teams-Nachrichten programmgesteuert exportieren möchten, indem Sie den Datumsbereich für einen bestimmten Benutzer oder ein bestimmtes Team übergeben.
- **Beispiel 2:** Wenn Sie alle Benutzer- oder Teamnachrichten täglich programmgesteuert exportieren möchten, indem Sie einen Datumsbereich bereitstellen. Export-APIs können alle Nachrichten abrufen, die während des angegebenen Datumsbereichs erstellt oder aktualisiert wurden.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Was wird von den Teams Export-APIs unterstützt?

- **Massenexport von Teams Nachricht:** Teams Export-APIs unterstützen bis zu 200 RPS pro App pro Mandant und 600 RPS für eine Anwendung, mit diesen Beschränkungen sollten Sie in der Lage sein, Teams-Nachrichten massenexportieren zu können.
- **Anwendungskontext:** Zum Aufrufen von Microsoft Graph muss Ihre App ein Zugriffstoken von der Microsoft-Identitätsplattform erwerben. Das Zugriffstoken enthält Informationen zu Ihrer App und die Berechtigungen, die sie für die über Microsoft Graph verfügbaren Ressourcen und APIs besitzt. Um ein Zugriffstoken zu erhalten, muss Ihre App bei der Microsoft-Identitätsplattform registriert sein und entweder von einem Benutzer oder einem Administrator für den Zugriff auf die benötigten Microsoft Graph-Ressourcen autorisiert werden.

    Wenn Sie bereits mit der Integration einer App mit der Microsoft-Identitätsplattform vertraut sind, um Token abzurufen, finden Sie informationen und Beispiele speziell für Microsoft Graph im Abschnitt Nächste Schritte. [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)
- **Hybridumgebung:** Export-APIs unterstützen Nachrichten, die von Benutzern gesendet werden, die in der Hybridumgebung (lokale Exchange und Teams) bereitgestellt werden. Auf alle Nachrichten, die von Benutzern gesendet werden, die für die Hybridumgebung konfiguriert sind, kann mithilfe von Export-APIs zugegriffen werden.
- **Vom Benutzer gelöschte Nachrichten:** Auf Nachrichten, die vom Benutzer aus dem Teams-Client gelöscht werden, kann über Export-APIs bis zu 30 Tage nach dem Zeitpunkt des Löschens zugegriffen werden.
- **Nachrichtenanlagen:** Export-APIs enthalten die Links zu den Anlagen, die als Teil von Nachrichten gesendet werden. Mithilfe von Export-APIs können Sie die in den Nachrichten angefügten Dateien abrufen.
- **Eigenschaften von Chatnachrichten:** Hier finden Sie die vollständige Liste der Eigenschaften, die von Teams Export-APIs [unterstützt werden.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Zugreifen auf Teams Export-APIs

- **Beispiel 1** ist eine einfache Abfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams ohne Filter:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **Beispiel 2** ist eine Beispielabfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams durch Angeben von Datumszeitfiltern und den 50 besten Nachrichten:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>Die API gibt eine Antwort mit dem Link für die nächste Seite zurück, wenn mehrere Ergebnisse angezeigt werden. Um die nächsten Ergebnisse zu erhalten, rufen Sie einfach get on the url von @odata.nextlink auf. Wenn @odata.nextlink nicht vorhanden oder null ist, werden alle Nachrichten abgerufen.

## <a name="prerequisites-to-access-teams-export-apis"></a>Voraussetzungen für den Zugriff auf Teams-Export-APIs 

- Die Export-APIs von Teams befinden sich derzeit in der Vorschau. Sie steht nur Benutzern und Mandanten zur Verfügung, die über die erforderlichen [Lizenzen für](https://aka.ms/teams-changenotification-licenses) APIs verfügen. In Zukunft kann Microsoft Von Ihnen oder Ihren Kunden verlangen, zusätzliche Gebühren basierend auf der Datenmenge zu bezahlen, auf die über die API zugegriffen wird.
- Microsoft Teams-APIs in Microsoft Graph, die auf vertrauliche Daten zugreifen, gelten als geschützte APIs. Export-APIs erfordern eine zusätzliche Überprüfung über Berechtigungen und Zustimmung hinaus, bevor Sie sie verwenden können. Zum Anfordern des Zugriffs auf diese geschützten APIs füllen Sie das [Anforderungsformular aus.](https://aka.ms/teamsgraph/requestaccess)
- Anwendungsberechtigungen werden von Apps verwendet, die ausgeführt werden, ohne dass ein angemeldeter Benutzer anwesend ist. Anwendungsberechtigungen können nur von einem Administrator erteilt werden. Die folgenden Berechtigungen sind erforderlich:

    - *Chat.Read.All*: Ermöglicht den Zugriff auf alle 1:1- und Gruppenchatnachrichten 
    - *User.Read.All*: Ermöglicht den Zugriff auf die Liste der Benutzer für einen Mandanten 

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
>Weitere Details zur chatMessage-Ressource finden Sie im [Artikel zum Ressourcentyp "chatMessage".](https://docs.microsoft.com/graph/api/resources/chatmessage)
