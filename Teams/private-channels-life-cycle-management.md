---
title: Verwalten des Lebenszyklus von privaten Kanälen in Microsoft Teams
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
description: Erfahren Sie mehr über die Verwaltung des Lebenszyklus von privaten Kanälen in Ihrer Organisation.
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601660"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Verwalten des Lebenszyklus von privaten Kanälen in Microsoft Teams

Hier finden Sie die Anleitungen, die Sie benötigen, um den Lebenszyklus von [privaten Kanälen](private-channels.md) in Ihrer Organisation zu verwalten.

> [!IMPORTANT]
> Wenn Sie die PowerShell-Schritte in diesem Artikel zur Verwaltung von privaten Kanälen verwenden, müssen Sie das Teams PowerShell Public Preview-Module aus dem [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams/) installieren und verwenden. Die Schritte zur Installation des Moduls finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md). Das aktuelle, generell verfügbare Teams PowerShell-Modul unterstützt die Verwaltung von privaten Kanälen nicht.

## <a name="set-whether-team-members-can-create-private-channels"></a>Festlegen, ob Teammitglieder private Kanäle erstellen können

Teambesitzer können die Berechtigung von Mitgliedern zur Erstellung von privaten Kanälen in den Teameinstellungen aktivieren oder deaktivieren. Dafür müssen sie in der Registerkarte **Einstellungen** für das Team die Option **Die Erstellung von privaten Kanälen durch Mitglieder zulassen** deaktivieren oder aktivieren.

Als Administrator können Sie das Graph-API verwenden, um zu kontrollieren, ob Mitglieder private Kanäle in bestimmten Teams erstellen dürfen. Hier ist ein Beispiel.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Festlegen ob Benutzer in Ihrer Organisation private Kanäle erstellen können

Als Administrator können Sie Richtlinien über das Microsoft Teams Admin Center oder PowerShell festlegen, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Verwenden Sie Teamrichtlinien, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen. Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie **CsTeamsChannelsPolicy**, um festzulegen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen. Setzen Sie den Parameter **AllowPrivateChannelCreation** auf **wahr**, um Benutzern, denen die Richtlinie zugewiesen ist, das Erstellen von privaten Kanälen zu erlauben. Wenn Sie den Parameter auf **falsch** setzen, dann können Benutzer, denen die Richtlinie zugewiesen ist, keine privaten Kanäle mehr erstellen.

Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Erstellen eines privaten Kanals im Auftrag eines Teambesitzers

Als Administrator können Sie PowerShell oder das Graph-API verwenden, um im Auftrag eines Teambesitzers einen privaten Kanal zu erstellen. Sie können dies beispielsweise so umsetzen, wenn Ihre Organisation die Erstellung von privaten Kanälen zentralisieren will.

### <a name="using-powershell"></a>Verwendung von PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Verwendung des Graph-API

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

Als Administrator können Sie PowerShell- oder Graph-API-Befehle verwenden, um diese URLs abzufragen.

### <a name="using-powershell"></a>Verwendung von PowerShell

1. Installieren und verbinden Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) mit Ihrem Administratorkonto.
2. Führen Sie den folgenden Befehl aus, wobei &lt;group_id&gt; die Gruppen-Identifikation des Teams ist. (Sie finden die Gruppen-Identifikation ganz einfach im Link zum Team.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Verwendung des Graph-API

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

Als Administrator können Sie das Microsoft Teams Admin Center, PowerShell oder das Graph-API für die Durchführung dieser Aktionen verwenden.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Weitere Informationen über die Verwaltung von Teammitglieder mit dem Microsoft Teams Admin Center finden Sie unter [Teams im Microsoft Teams Admin Center verwalten](manage-teams-in-modern-portal.md).

### <a name="using-powershell"></a>Verwendung von PowerShell

1. Führen Sie den folgenden Befehl aus, wobei &lt;group_id&gt; die Gruppen-Identifikation des Teams und &lt;channel_name&gt; der Kanalname ist.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Höherstufen eines Mitglieds zum Besitzer.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Verwendung des Graph-API

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

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Verwenden der Microsoft Graph-API zum Arbeiten mit Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Kanäle auflisten](https://docs.microsoft.com/graph/api/channel-list)
    - [Kanal erstellen](https://docs.microsoft.com/graph/api/channel-post)
    - [Mitglied zum Kanal hinzufügen](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Mitglied im Kanal aktualisieren](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Mitglied aus dem Kanal entfernen](https://docs.microsoft.com/graph/api/conversationmember-delete)
