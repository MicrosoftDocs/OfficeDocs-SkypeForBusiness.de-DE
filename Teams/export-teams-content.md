---
title: Exportieren von Inhalten mit den Microsoft Teams-Export-APIs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In diesem Artikel erfahren Sie, wie Sie Microsoft Teams-Inhalte mithilfe der Microsoft Teams-Export-APIs exportieren.
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
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944600"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportieren von Inhalten mit den Microsoft Teams-Export-APIs

Mit den Teams -Export-APIs können Sie 1:1-, Gruppenchat- und Kanalnachrichten aus Microsoft Teams exportieren. Wenn Ihre Organisation Microsoft Teams-Nachrichten exportieren muss, können Sie diese mithilfe von Teams-Export-APIs extrahieren. *Chatnachricht* stellt eine einzelne Chatnachricht in einem [Kanal oder Chat](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) [dar.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) Bei der Chatnachricht kann es sich um eine Chatstammnachricht oder um einen Teil eines Antwortthreads handelt, der durch die **"replyToId"-Eigenschaft** in der Chatnachricht definiert ist.

Im Folgenden finden Sie einige Beispiele für die Verwendung dieser Export-APIs:

- **Beispiel 1:** Wenn Sie Microsoft Teams in Ihrer Organisation aktiviert haben und alle Microsoft Teams-Nachrichten programmgesteuert exportieren möchten, indem Sie den Datumsbereich für einen bestimmten Benutzer oder ein bestimmtes Team übergeben.
- **Beispiel 2:** Wenn Sie alle Benutzer- oder Teamnachrichten täglich programmgesteuert exportieren möchten, indem Sie einen Datumsbereich bereitstellen. Export-APIs können alle Nachrichten abrufen, die während des angegebenen Datumsbereichs erstellt oder aktualisiert wurden.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Was wird von den Teams-Export-APIs unterstützt?

- **Massenexport von Teams-Nachricht:** Teams -Export-APIs unterstützen bis zu 200 RPS pro App pro Mandant und 600 RPS für eine Anwendung. Mit diesen Grenzwerten sollten Sie in der Lage sein, Massenexporte von Teamnachrichten zu starten.
- **Anwendungskontext:** Zum Aufrufen von Microsoft Graph muss Ihre App ein Zugriffstoken von der Microsoft-Identitätsplattform erhalten. Das Zugriffstoken enthält Informationen zu Ihrer App sowie die Berechtigungen, über die es für die über Microsoft Graph verfügbaren Ressourcen und APIs verfügt. Um ein Zugriffstoken zu erhalten, muss Ihre App bei der Microsoft-Identitätsplattform registriert sein und entweder von einem Benutzer oder einem Administrator für den Zugriff auf die benötigten Microsoft Graph-Ressourcen autorisiert sein.

    Wenn Sie bereits mit der Integration einer App mit der Microsoft-Identitätsplattform zum Erhalten von Token vertraut sind, finden Sie im Abschnitt "Nächste Schritte" Informationen und Beispiele speziell für Microsoft Graph. [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)
- **Hybridumgebung:** Export-APIs unterstützen Nachrichten, die von Benutzern gesendet werden, die in einer Hybridumgebung (lokales Exchange und Teams) bereitgestellt werden. Auf alle Nachrichten, die von Benutzern gesendet werden, die für eine Hybridumgebung konfiguriert sind, kann über die Export-APIs zugegriffen werden.
- **Vom Benutzer gelöschte Nachrichten:** Auf Nachrichten, die vom Benutzer aus dem Teamclient gelöscht wurden, kann bis zu 30 Tage nach dem Löschvorgang mithilfe von Export-APIs zugegriffen werden.
- **Nachrichtenanlagen:** Zu den Export-APIs gehören die Links zu den Anlagen, die als Teil von Nachrichten gesendet werden. Mit den EXPORT-APIs können Sie die in den Nachrichten angefügten Dateien abrufen.
- **Eigenschaften von Chatnachrichten:** Die vollständige Liste der Eigenschaften, die von Teams Export-APIs unterstützt werden, finden Sie [hier.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Zugreifen auf Teams-Export-APIs

- **Beispiel 1** ist eine einfache Abfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams ohne Filter:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- **Beispiel 2** ist eine Beispielabfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams durch Angabe von Datumszeitfiltern und den 50 am besten 50 Nachrichten:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

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
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Weitere Details zur Ressource "chatMessage" finden Sie im Artikel zum Ressourcentyp ["chatMessage".](https://docs.microsoft.com/graph/api/resources/chatmessage)
