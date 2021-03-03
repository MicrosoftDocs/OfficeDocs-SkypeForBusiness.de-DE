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
ms.openlocfilehash: 9c99bed1ef9a1862b469dd5214b8d829bde8479b
ms.sourcegitcommit: 15c45befbee35e69f9ec82493151cb82e61da4fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50096928"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportieren von Inhalten mit den Microsoft Teams-Export-APIs

Mit den Teams -Export-APIs können Sie 1:1-, Gruppenchat- und Kanalnachrichten aus Microsoft Teams exportieren. Wenn Ihre Organisation Microsoft Teams-Nachrichten exportieren muss, können Sie diese mithilfe von Teams-Export-APIs extrahieren. *Chatnachricht* stellt eine einzelne Chatnachricht in einem [Kanal oder Chat](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) [dar.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) Bei der Chatnachricht kann es sich um eine Chatstammnachricht oder um einen Teil eines Antwortthreads handelt, der durch die **"replyToId"-Eigenschaft** in der Chatnachricht definiert ist.

Im Folgenden finden Sie einige Beispiele für die Verwendung dieser Export-APIs:

- **Beispiel 1:** Wenn Sie Microsoft Teams in Ihrer Organisation aktiviert haben und alle Microsoft Teams-Nachrichten programmgesteuert exportieren möchten, indem Sie den Datumsbereich für einen bestimmten Benutzer oder ein bestimmtes Team übergeben.
- **Beispiel 2:** Wenn Sie alle Benutzer- oder Teamnachrichten täglich programmgesteuert exportieren möchten, indem Sie einen Datumsbereich bereitstellen. Export-APIs können alle Nachrichten abrufen, die während des angegebenen Datumsbereichs erstellt oder aktualisiert wurden.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Was wird von den Teams-Export-APIs unterstützt?

- **Massenexport von Teams-Nachrichten:** Teams -Export-APIs unterstützen bis zu 200 RPS pro App pro Mandant und 600 RPS für eine Anwendung. Mit diesen Grenzwerten sollten Sie in der Lage sein, Massenexporte von Teamnachrichten zu starten.
- **Anwendungskontext:** Zum Aufrufen von Microsoft Graph muss Ihre App ein Zugriffstoken von der Microsoft-Identitätsplattform erhalten. Das Zugriffstoken enthält Informationen zu Ihrer App sowie die Berechtigungen, über die es für die über Microsoft Graph verfügbaren Ressourcen und APIs verfügt. Um ein Zugriffstoken zu erhalten, muss Ihre App bei der Microsoft-Identitätsplattform registriert sein und entweder von einem Benutzer oder einem Administrator für den Zugriff auf die benötigten Microsoft Graph-Ressourcen autorisiert sein.

    Wenn Sie bereits mit der Integration einer App mit der Microsoft-Identitätsplattform zum Erhalten von Token vertraut sind, finden Sie im Abschnitt "Nächste Schritte" Informationen und Beispiele speziell für Microsoft Graph. [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)
- **Hybridumgebung:** Export-APIs unterstützen Nachrichten, die von Benutzern gesendet werden, die in einer Hybridumgebung (lokales Exchange und Teams) bereitgestellt werden. Auf alle Nachrichten, die von Benutzern gesendet werden, die für eine Hybridumgebung konfiguriert sind, kann über die Export-APIs zugegriffen werden.
- **Vom Benutzer gelöschte Nachrichten:** Auf Nachrichten, die vom Benutzer aus dem Teamclient gelöscht wurden, kann bis zu 30 Tage nach dem Löschvorgang mithilfe von Export-APIs zugegriffen werden.
- **Nachrichtenanlagen:** Zu den Export-APIs gehören die Links zu den Anlagen, die als Teil von Nachrichten gesendet werden. Mit den EXPORT-APIs können Sie die in den Nachrichten angefügten Dateien abrufen.
- **Eigenschaften von Chatnachrichten:** Die vollständige Liste der Eigenschaften, die von Teams Export-APIs unterstützt werden, finden Sie [hier.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Zugreifen auf Teams-Export-APIs

- **Beispiel 1** ist eine einfache Abfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams ohne Filter:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **Beispiel 2** ist eine Beispielabfrage zum Abrufen aller Nachrichten eines Benutzers oder Teams durch Angabe von Datums-/Uhrzeitfiltern und den 50 am besten 50 Nachrichten:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>Die API gibt bei mehreren Ergebnissen eine Antwort mit dem Link "Nächste Seite" zurück. Um die nächste Gruppe von Ergebnissen zu erhalten, rufen Sie einfach "ABRUFEN für die URL" von "@odata.nextlink" auf. Wenn @odata.nextlink nicht vorhanden oder NULL ist, werden alle Nachrichten abgerufen.

## <a name="prerequisites-to-access-teams-export-apis"></a>Voraussetzungen für den Zugriff auf die Teams-Export-APIs 

- Die Teams-Export-APIs werden derzeit in der Vorschau angezeigt. Sie steht nur Benutzern und Mandanten zur Verfügung, die über die [erforderlichen Lizenzen für](https://aka.ms/teams-changenotification-licenses) APIs verfügen. In Zukunft kann Microsoft von Ihnen oder Ihren Kunden zusätzliche Gebühren auf der Grundlage der Datenmenge verlangen, auf die über die API zugegriffen wird.
- Microsoft Teams-APIs in Microsoft Graph, die auf vertrauliche Daten zugreifen, werden als geschützte APIs betrachtet. Export-APIs erfordern eine zusätzliche Überprüfung, die über Berechtigungen und Zustimmung hinaus geht, bevor Sie sie verwenden können. Füllen Sie das Anforderungsformular aus, um Zugriff auf diese geschützten APIs [an fordern.](https://aka.ms/teamsgraph/requestaccess)
- Anwendungsberechtigungen werden von Apps verwendet, die ausgeführt werden, ohne dass ein angemeldeter Benutzer anwesend ist. Anwendungsberechtigungen können nur von einem Administrator erteilt werden. Die folgenden Berechtigungen sind erforderlich:

    - *Chat.Read.All*: Ermöglicht den Zugriff auf alle 1:1- und Gruppenchatnachrichten. 
    - *User.Read.All*: Ermöglicht den Zugriff auf die Liste der Benutzer für einen Mandanten. 

## <a name="json-representation"></a>Darstellung von JSON

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
