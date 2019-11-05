---
title: Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie den Lebenszyklus privater Kanäle in Ihrer Organisation verwalten können.
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969413"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams

Hier finden Sie die Anleitungen, die Sie zum Verwalten des Lebenszyklus [privater Kanäle](private-channels.md) in Ihrer Organisation benötigen.

## <a name="set-whether-team-members-can-create-private-channels"></a>Festlegen, ob Teammitglieder private Kanäle erstellen können

Teambesitzer können die Möglichkeit für Mitglieder, private Kanäle in Team Einstellungen zu erstellen, deaktivieren oder aktivieren. Deaktivieren oder aktivieren Sie dazu auf der Registerkarte **Einstellungen** für das Team **zulassen, dass Mitglieder private Kanäle erstellen**.

Als Administrator können Sie die Diagramm-API verwenden, um zu steuern, ob Mitglieder private Kanäle in bestimmten Teams erstellen können. Hier ist ein Beispiel.

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Festlegen, ob Benutzer in Ihrer Organisation private Kanäle erstellen können

Als Administrator können Sie Richtlinien festlegen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

Verwenden Sie die Richtlinien für Teams, um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen. Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).

### <a name="using-powershell"></a>Verwenden von PowerShell

Verwenden Sie **CsTeamsChannelsPolicy** , um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen. Legen Sie den **AllowPrivateChannelCreation** -Parameter auf " **true** " fest, damit Benutzer, denen die Richtlinie zugewiesen ist, private Kanäle erstellen können. Wenn der Parameter auf " **false** " festgelegt wird, wird die Möglichkeit zum Erstellen privater Kanäle für Benutzer deaktiviert, denen die Richtlinie zugewiesen ist.

Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Erstellen eines privaten Kanals im Auftrag eines Team Besitzers

Als Administrator können Sie die PowerShell-oder Diagramm-API verwenden, um einen privaten Kanal im Auftrag eines Team Besitzers zu erstellen. Beispielsweise sollten Sie dies tun, wenn Ihre Organisation die Erstellung privater Kanäle zentralisieren möchte.

### <a name="using-powershell"></a>Verwenden von PowerShell

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Verwenden der Diagramm-API

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a>Abrufen einer Liste aller privaten Kanal Nachrichten

Möglicherweise möchten Sie eine Liste aller Nachrichten und Antworten abrufen, die in einem privaten Kanal zu Archivierungs-und Überwachungszwecken gepostet wurden.  Hier erfahren Sie, wie Sie die Diagramm-API verwenden.

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Suchen von SharePoint-URLs für alle privaten Kanäle in einem Team

Unabhängig davon, ob Sie eDiscovery-oder rechtliche Aufbewahrungsmöglichkeiten für Dateien in einem privaten Kanal durchführen oder eine Branchen-app erstellen möchten, die Dateien in bestimmten privaten Kanälen platziert, sollten Sie eine Möglichkeit zum Abfragen der eindeutigen SharePoint-Websitesammlungen benötigen, die für jeden privaten Kanal.

Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.

### <a name="using-powershell"></a>Verwenden von PowerShell

1. Installieren Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) , und stellen Sie eine Verbindung mit Ihrem Administratorkonto her.
2. Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des Teams ist. (Sie können die Gruppen-ID einfach im Link zum Team finden.)

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Verwenden der Diagramm-API

Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.

1. Gehen Sie wie folgt vor, um die Liste der privaten Kanal-IDs für ein bestimmtes Team abzurufen, wobei <group_id> die Gruppen-ID des Teams ist. Sie benötigen dies bei nachfolgenden anrufen. (Sie können die Gruppen-ID einfach im Link zum Team finden).

    **Anforderung**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Reaktion**

    ```
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

2. Führen Sie für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen möchten, die &lt;folgende&gt; Anforderung aus, wobei channel_id die Kanal-ID ist.

    **Anforderung**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Reaktion**

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einem privaten Kanal

Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu einem Besitzer heraufstufen müssen. Dies kann geschehen, wenn Sie Besitzer von privaten Kanälen sind, die die Organisation verlassen haben und der private Kanal Administratorhilfe benötigt, um den Besitz des Kanals zu beanspruchen.

Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.

### <a name="using-powershell"></a>Verwenden von PowerShell

1. Installieren Sie das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) mit Ihrem Administratorkonto, und stellen Sie eine Verbindung mit diesem her.
2. Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des &lt;Teams&gt; und channel_id die Kanal-ID ist.

    **Anforderung**

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    **Reaktion**

    ```
    HTTP/1.1 200 OK Content-type: application/json
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

3. Höher Stufen eines Mitglieds zu einem Besitzer

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Verwenden der Diagramm-API

Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.

1. Verwenden Sie Folgendes, wobei &lt;group_id&gt; die Gruppen-ID des Teams und &lt;channel_id&gt; die Kanal-ID ist.

    **Anforderung**

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Reaktion**

    ```
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
2.  Führen Sie die folgenden Schritte aus, um das Mitglied für einen &lt;Besitzer&gt;zu &lt;bewerben&gt;, wobei &lt;group_id&gt; , channel_id und ID vom vorherigen Anruf zurückgegeben werden. Beachten Sie &lt;,&gt; dass &lt;die&gt; vom vorherigen Anruf zurückgegebene ID und UserID nicht identisch sind und nicht austauschbar sind. Stellen Sie sicher, &lt;dass&gt;Sie ID verwenden.

    **Anforderung**

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Reaktion**

    ```
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

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Verwenden der Microsoft Graph-API zum Arbeiten mit Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Listen Kanäle](https://docs.microsoft.com/graph/api/channel-list)
    - [Kanal erstellen](https://docs.microsoft.com/graph/api/channel-post)
    - [Mitglied zu Kanal hinzufügen](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Mitglied im Kanal aktualisieren](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Mitglied aus Kanal entfernen](https://docs.microsoft.com/graph/api/conversationmember-delete)