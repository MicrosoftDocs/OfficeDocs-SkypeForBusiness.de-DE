---
title: Verwalten der privaten Kanäle in Microsoft Teams mit Graph-API
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie private Kanäle in Ihrer Organisation mithilfe einer Graph-API verwalten.
ms.openlocfilehash: e97d808bd9f544ef611b0b5e4b0456d302b4013d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117743"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Verwalten des Lebenszyklus von privaten Kanälen in Microsoft Teams

Hier finden Sie die Anleitungen, die Sie verwalten müssen, um die Graph-API zum Verwalten Teams [privaten](./private-channels.md) Kanälen in Ihrer Organisation zu verwenden.

## <a name="set-whether-team-members-can-create-private-channels"></a>Festlegen, ob Teammitglieder private Kanäle erstellen können

Als Administrator können Sie das Graph-API verwenden, um zu kontrollieren, ob Mitglieder private Kanäle in bestimmten Teams erstellen dürfen. Hier ist ein Beispiel.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Erstellen eines privaten Kanals im Auftrag eines Teambesitzers

Als Administrator können Sie die Graph-API verwenden, um im Namen eines Teambesitzers einen privaten Kanal zu erstellen. Sie können dies beispielsweise so umsetzen, wenn Ihre Organisation die Erstellung von privaten Kanälen zentralisieren will.

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>Abrufen einer Liste aller privaten Kanalnachrichten

Aus Archivierungs- und Überwachungsgründen möchten Sie allenfalls eine Liste aller in einem privaten Kanal veröffentlichten Nachrichten und Antworten abrufen.  So verwenden Sie das Graph-API, um dies zu tun.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Finden der SharePoint-URLs für alle privaten Kanäle in einem Team

Unabhängig davon, ob Sie eDiscovery oder die Aufbewahrung für juristische Zwecke in einem privaten Kanal durchführen, oder eine benutzerdefinierte App erstellen möchten, die Dateien in bestimmten privaten Kanälen platziert: Sie wollen eine Möglichkeit zur Abfrage der eindeutigen SharePoint-Websitesammlungen haben, die für jeden privaten Kanal erstellt wurden.

Als Administrator können Sie die Graph-APIs verwenden, um diese URLs ababfragen.

Sie können diese Befehle über den [Graph-Tester](https://developer.microsoft.com/graph/graph-explorer) ausprobieren.

1. Verwenden Sie den folgenden Befehl, um eine Liste aller privaten Kanal-IDs für ein bestimmtes Team zu erhalten, wobei <group_id> die Gruppen-Identifikation des Teams ist. Sie benötigen dies in nachfolgenden Aufrufen. (Sie finden die Gruppen-Identifikation ganz einfach im Link zum Team).

    **Anforderung**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Antwort**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. Für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen wollen, führen Sie die folgende Anforderung aus, wobei &lt;channel_id&gt; die Kanal-Identifikation ist.

    **Anforderung**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Antwort**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einen privaten Kanal

Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu Besitzer hochstufen müssen. Dies kann der Fall sein, wenn Besitzer von privaten Kanälen die Organisation verlassen haben und der private Kanal die Hilfe eines Administrator benötigt, um den Besitz des Kanals wieder zu beanspruchen.

Als Administrator können Sie diese Aktionen mithilfe Graph-API ausführen.

Sie können diese Befehle über den [Graph-Tester](https://developer.microsoft.com/graph/graph-explorer) ausprobieren.

1. Verwenden Sie den folgenden Befehl, wobei &lt;group_id&gt; die Gruppen-Identifikation des Teams und &lt;channel_name&gt; der Kanalname ist.

    **Anforderung**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Antwort**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. Verwenden Sie den folgenden Befehl, um das Mitglied zum Besitzer hochzustufen, wobei &lt;group_id&gt;, &lt;channel_id&gt;, und &lt;id&gt; in einem früheren Aufruf zurückgegeben wurden. Beachten Sie, dass &lt;id&gt; und &lt;userId&gt;, welche aus einem früheren Aufruf zurückgegeben wurden, nicht dasselbe und nicht austauschbar sind. Stellen Sie sicher, dass Sie &lt;id&gt; verwenden.

    **Anforderung**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Antwort**

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>Verwandte Themen

[Verwenden der Microsoft Graph-API zum Arbeiten mit Teams](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[Kanäle auflisten](/graph/api/channel-list)

[Kanal erstellen](/graph/api/channel-post)

[Mitglied zum Kanal hinzufügen](/graph/api/conversationmember-add)

[Mitglied im Kanal aktualisieren](/graph/api/conversationmember-update)

[Mitglied aus dem Kanal entfernen](/graph/api/conversationmember-delete)