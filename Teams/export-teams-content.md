---
title: Exportieren von Inhalten mit den Microsoft Teams Export-APIs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: In diesem Artikel erfahren Sie, wie Sie Team Inhalte mithilfe der Microsoft Teams-Export-APIs exportieren können.
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
ms.openlocfilehash: bbb03fc030361419e5f42b2e792e752f2007e6d2
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333491"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportieren von Inhalten mit den Microsoft Teams Export-APIs

Teams-Export-APIs ermöglichen es Ihnen, 1:1-und Gruppen-Chatnachrichten aus Microsoft Teams zu exportieren. Wenn Ihre Organisation Microsoft Teams-Nachrichten exportieren muss, können Sie diese mithilfe von Team Export-APIs extrahieren. *Chat-Nachricht* stellt eine einzelne Chatnachricht in einem [Kanal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) oder [Chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)dar. Bei der Chatnachricht kann es sich um eine root-Chatnachricht oder einen Teil eines Antwort Threads handeln, der durch die **replyToId** -Eigenschaft in der Chatnachricht definiert ist.

Nachfolgend finden Sie einige Beispiele, wie Sie diese Export-APIs verwenden können:

- **Beispiel 1**: Wenn Sie Microsoft Teams in Ihrer Organisation aktiviert haben und alle Microsoft Teams-Nachrichten bis dato programmgesteuert exportieren möchten, indem Sie den Datumsbereich für einen bestimmten Benutzer übergeben.
- **Beispiel 2**: Wenn Sie alle Benutzer Nachrichten programmgesteuert exportieren möchten, indem Sie einen Datumsbereich angeben. Export-APIs können alle Nachrichten abrufen, die während des angegebenen Datumsbereichs erstellt oder aktualisiert wurden.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Was wird von den Export-APIs für Teams unterstützt?

- **Massen Export der Teams-Nachricht:** Teams-Export-APIs unterstützen bis zu 200 RPS pro App pro Mandant und 600 RPS für eine Anwendung, mit diesen Einschränkungen sollten Sie in der Lage sein, den Massen Export von Teams-Nachrichten auszuführen.
- **Anwendungskontext**: zum Aufrufen von Microsoft Graph muss Ihre APP ein Zugriffstoken von der Microsoft Identity-Plattform erwerben. Das Zugriffstoken enthält Informationen über Ihre APP und die Berechtigungen für die Ressourcen und APIs, die über Microsoft Graph zur Verfügung stehen. Zum Abrufen eines Zugriffstokens muss Ihre APP bei der Microsoft Identity-Plattform registriert und von einem Benutzer oder Administrator für den Zugriff auf die benötigten Microsoft Graph-Ressourcen autorisiert werden.

    Wenn Sie bereits mit der Integration einer APP mit der Microsoft Identity-Plattform zum Abrufen von Token vertraut sind, lesen Sie den Abschnitt [Nächste Schritte](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) für Informationen und Beispiele für Microsoft Graph.
- **Hybrid Umgebung:** Export-APIs unterstützen Nachrichten, die von Benutzern gesendet werden, die in einer Hybrid Umgebung bereitgestellt werden (Lokales Exchange und Teams). Alle Nachrichten, die von Benutzern gesendet werden, die für eine Hybridumgebung konfiguriert sind, können mithilfe von Export-APIs aufgerufen werden.
- **Gelöschte Nachrichten des Benutzers:** Nachrichten, die vom Benutzer des Teams-Clients gelöscht werden, können mithilfe von Export-APIs bis zu 30 Tage nach dem Löschvorgang aufgerufen werden.
- **Nachrichtenanlagen:** Export-APIs enthalten die Links zu den Anlagen, die als Teil von Nachrichten gesendet werden. Mit Export-APIs können Sie die in den Nachrichten angefügten Dateien abrufen.
- **Eigenschaften von Chat Nachrichten:** Weitere Informationen finden Sie in der vollständigen Liste der Eigenschaften, die Team- [APIs unterstützen](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

## <a name="how-to-access-teams-export-apis"></a>Zugreifen auf Team Export-APIs

- **Beispiel 1** ist eine einfache Abfrage, mit der alle Nachrichten eines Benutzers ohne Filter abgerufen werden:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- **Beispiel 2** ist eine Beispielabfrage, um alle Nachrichten eines Benutzers abzurufen, indem Datums Zeitfilter und Top 50-Nachrichten angegeben werden:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>Die API gibt die Antwort mit dem Link "Nächste Seite" zurück, falls mehrere Ergebnisse vorliegen. Wenn Sie den nächsten Satz von Ergebnissen erhalten möchten, rufen Sie einfach die URL von @odata. Nextlink. Wenn @odata. Nextlink nicht vorhanden oder NULL ist, werden alle Nachrichten abgerufen.

## <a name="prerequisites-to-access-teams-export-apis"></a>Voraussetzungen für den Zugriff auf Team Export-APIs 

- Die Export-APIs für Teams befinden sich derzeit in der Vorschau. Es steht Benutzern und Mandanten nur zur Verfügung, die über die [erforderlichen Lizenzen](https://aka.ms/teams-changenotification-licenses) für APIs verfügen. In Zukunft kann Microsoft verlangen, dass Sie oder Ihre Kunden zusätzliche Gebühren auf der Grundlage der Datenmenge Zahlen, auf die über die API zugegriffen wird.
- Microsoft Teams-APIs in Microsoft Graph, die auf vertrauliche Daten zugreifen, gelten als geschützte APIs. Für Export-APIs ist es erforderlich, dass Sie über Berechtigungen und Zustimmung hinaus zusätzliche Überprüfung haben, bevor Sie Sie verwenden können. Wenn Sie den Zugriff auf diese geschützten APIs anfordern möchten, füllen Sie das [Anforderungsformular](https://aka.ms/teamsgraph/requestaccess)aus.
- Anwendungsberechtigungen werden von apps verwendet, die ohne angemeldeten Benutzer ausgeführt werden. Anwendungsberechtigungen können nur von einem Administrator zugestimmt werden. Die folgenden Berechtigungen sind erforderlich:

    - *Chat. Read. all*: ermöglicht den Zugriff auf alle 1:1-und Gruppen-Chatnachrichten 
    - *User. Read. all*: ermöglicht den Zugriff auf die Liste der Benutzer für einen Mandanten 

## <a name="json-representation"></a>JSON-Darstellung

Im folgenden Beispiel handelt es sich um eine JSON-Darstellung der Ressource:

Namespace: Microsoft. Graph

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
                    "id": "0de69e5e-2da8-4cf2-821f-5e6585b2c65b",
                    "displayName": "User Name",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "19:0de69e5e-2da8-4cf2-821f-5e6585b2c65b_5c64e248-3269-4268-a36e-0f80314e9c39@unq.gbl.spaces"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Weitere Informationen zur chatMessage-Ressource finden Sie im Artikel zum [chatMessage-Ressourcentyp](https://docs.microsoft.com/graph/api/resources/chatmessage) .
