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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie den Lebenszyklus privater Kanäle in Ihrer Organisation verwalten können.
ms.openlocfilehash: 154cde6ad8371b2d9f902bf3803f48e72ade0a77
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321699"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams

Hier finden Sie die Anleitungen, die Sie zum Verwalten des Lebenszyklus [privater Kanäle](private-channels.md) in Ihrer Organisation benötigen.

> [!IMPORTANT]
> Wenn Sie die PowerShell-Schritte in diesem Artikel zum Verwalten privater Kanäle verwenden, müssen Sie die neueste Vorabversion des Teams PowerShell-Moduls aus dem [PowerShell-Test Katalog](https://www.poshtestgallery.com/packages/MicrosoftTeams/)installieren und verwenden. Eine schrittweise Anleitung zum Installieren des Moduls finden Sie unter [Installieren der Vorabversion des Teams PowerShell-Moduls](install-prerelease-teams-powershell-module.md). Die neueste öffentlich verfügbare Version des Teams PowerShell-Moduls unterstützt nicht das Verwalten privater Kanäle.

## <a name="set-whether-team-members-can-create-private-channels"></a>Festlegen, ob Teammitglieder private Kanäle erstellen können

Teambesitzer können die Möglichkeit für Mitglieder, private Kanäle in Team Einstellungen zu erstellen, deaktivieren oder aktivieren. Deaktivieren oder aktivieren Sie dazu auf der Registerkarte **Einstellungen** für das Team **zulassen, dass Mitglieder private Kanäle erstellen**.

Als Administrator können Sie die Diagramm-API verwenden, um zu steuern, ob Mitglieder private Kanäle in bestimmten Teams erstellen können. Hier ist ein Beispiel.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Festlegen, ob Benutzer in Ihrer Organisation private Kanäle erstellen können

Als Administrator können Sie Richtlinien festlegen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Verwenden Sie die Richtlinien für Teams, um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen. Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie **CsTeamsChannelsPolicy** , um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen. Legen Sie den **AllowPrivateChannelCreation** -Parameter auf " **true** " fest, damit Benutzer, denen die Richtlinie zugewiesen ist, private Kanäle erstellen können. Wenn der Parameter auf " **false** " festgelegt wird, wird die Möglichkeit zum Erstellen privater Kanäle für Benutzer deaktiviert, denen die Richtlinie zugewiesen ist.

Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Erstellen eines privaten Kanals im Auftrag eines Team Besitzers

Als Administrator können Sie die PowerShell-oder Diagramm-API verwenden, um einen privaten Kanal im Auftrag eines Team Besitzers zu erstellen. Beispielsweise sollten Sie dies tun, wenn Ihre Organisation die Erstellung privater Kanäle zentralisieren möchte.

### <a name="using-powershell"></a>Verwendung von PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Verwenden der Diagramm-API

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Abrufen einer Liste aller privaten Kanal Nachrichten

Möglicherweise möchten Sie eine Liste aller Nachrichten und Antworten abrufen, die in einem privaten Kanal zu Archivierungs-und Überwachungszwecken gepostet wurden.  Hier erfahren Sie, wie Sie die Diagramm-API verwenden.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Suchen von SharePoint-URLs für alle privaten Kanäle in einem Team

Unabhängig davon, ob Sie eDiscovery-oder rechtliche Aufbewahrungsmöglichkeiten für Dateien in einem privaten Kanal durchführen oder eine benutzerdefinierte app erstellen möchten, mit der Dateien in bestimmten privaten Kanälen platziert werden, sollten Sie eine Möglichkeit zum Abfragen der eindeutigen SharePoint-Websitesammlungen benötigen, die für jeden privaten Kanal erstellt werden.

Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.

### <a name="using-powershell"></a>Verwendung von PowerShell

1. Installieren Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) , und stellen Sie eine Verbindung mit Ihrem Administratorkonto her.
2. Führen Sie die folgenden Schritte &lt; aus, wobei group_id &gt; die Gruppen-ID des Teams ist. (Sie können die Gruppen-ID einfach im Link zum Team finden.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Verwenden der Diagramm-API

Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.

1. Führen Sie die folgenden Schritte aus, um die Liste der privaten Kanal-IDs für ein bestimmtes Team abzurufen, wobei <group_id> die Gruppen-ID des Teams ist. Sie benötigen dies bei nachfolgenden anrufen. (Sie können die Gruppen-ID einfach im Link zum Team finden).

    **Anforderung**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Reaktion**

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

2. Führen Sie für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen möchten, die folgende Anforderung aus, wobei &lt; channel_id &gt; die Kanal-ID ist.

    **Anforderung**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Reaktion**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einem privaten Kanal

Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu einem Besitzer heraufstufen müssen. Dies kann geschehen, wenn Sie Besitzer von privaten Kanälen sind, die die Organisation verlassen haben und der private Kanal Administratorhilfe benötigt, um den Besitz des Kanals zu beanspruchen.

Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.

### <a name="using-powershell"></a>Verwendung von PowerShell

1. Führen Sie die folgenden Schritte &lt; aus, wobei group_id &gt; die Gruppen-ID des Teams und &lt; channel_name &gt; der Kanal Name ist.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Höher Stufen eines Mitglieds zu einem Besitzer

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Verwenden der Diagramm-API

Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.

1. Verwenden Sie Folgendes, wobei &lt; group_id &gt; die Gruppen-ID des Teams und &lt; channel_id &gt; die Kanal-ID ist.

    **Anforderung**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Reaktion**

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
2. Führen Sie die folgenden Schritte aus, um das Mitglied für einen Besitzer zu bewerben, wobei &lt; group_id &gt; , &lt; channel_id &gt; und &lt; ID &gt; vom vorherigen Anruf zurückgegeben werden. Beachten Sie, dass die &lt; &gt; &lt; &gt; vom vorherigen Anruf zurückgegebene ID und UserID nicht identisch sind und nicht austauschbar sind. Stellen Sie sicher, dass Sie &lt; ID verwenden &gt; .

    **Anforderung**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Reaktion**

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

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Verwenden der Microsoft Graph-API zum Arbeiten mit Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Listen Kanäle](https://docs.microsoft.com/graph/api/channel-list)
    - [Kanal erstellen](https://docs.microsoft.com/graph/api/channel-post)
    - [Mitglied zu Kanal hinzufügen](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Mitglied im Kanal aktualisieren](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Mitglied aus Kanal entfernen](https://docs.microsoft.com/graph/api/conversationmember-delete)
