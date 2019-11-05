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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="8a0b6-103">Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a0b6-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="8a0b6-104">Hier finden Sie die Anleitungen, die Sie zum Verwalten des Lebenszyklus [privater Kanäle](private-channels.md) in Ihrer Organisation benötigen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="8a0b6-105">Festlegen, ob Teammitglieder private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="8a0b6-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="8a0b6-106">Teambesitzer können die Möglichkeit für Mitglieder, private Kanäle in Team Einstellungen zu erstellen, deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="8a0b6-107">Deaktivieren oder aktivieren Sie dazu auf der Registerkarte **Einstellungen** für das Team **zulassen, dass Mitglieder private Kanäle erstellen**.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="8a0b6-108">Als Administrator können Sie die Diagramm-API verwenden, um zu steuern, ob Mitglieder private Kanäle in bestimmten Teams erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="8a0b6-109">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="8a0b6-110">Festlegen, ob Benutzer in Ihrer Organisation private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="8a0b6-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="8a0b6-111">Als Administrator können Sie Richtlinien festlegen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8a0b6-112">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="8a0b6-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="8a0b6-113">Verwenden Sie die Richtlinien für Teams, um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="8a0b6-114">Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8a0b6-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8a0b6-115">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a0b6-115">Using PowerShell</span></span>

<span data-ttu-id="8a0b6-116">Verwenden Sie **CsTeamsChannelsPolicy** , um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="8a0b6-117">Legen Sie den **AllowPrivateChannelCreation** -Parameter auf " **true** " fest, damit Benutzer, denen die Richtlinie zugewiesen ist, private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="8a0b6-118">Wenn der Parameter auf " **false** " festgelegt wird, wird die Möglichkeit zum Erstellen privater Kanäle für Benutzer deaktiviert, denen die Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="8a0b6-119">Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8a0b6-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="8a0b6-120">Erstellen eines privaten Kanals im Auftrag eines Team Besitzers</span><span class="sxs-lookup"><span data-stu-id="8a0b6-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="8a0b6-121">Als Administrator können Sie die PowerShell-oder Diagramm-API verwenden, um einen privaten Kanal im Auftrag eines Team Besitzers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="8a0b6-122">Beispielsweise sollten Sie dies tun, wenn Ihre Organisation die Erstellung privater Kanäle zentralisieren möchte.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8a0b6-123">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a0b6-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="8a0b6-124">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="8a0b6-124">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="8a0b6-125">Abrufen einer Liste aller privaten Kanal Nachrichten</span><span class="sxs-lookup"><span data-stu-id="8a0b6-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="8a0b6-126">Möglicherweise möchten Sie eine Liste aller Nachrichten und Antworten abrufen, die in einem privaten Kanal zu Archivierungs-und Überwachungszwecken gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="8a0b6-127">Hier erfahren Sie, wie Sie die Diagramm-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="8a0b6-128">Suchen von SharePoint-URLs für alle privaten Kanäle in einem Team</span><span class="sxs-lookup"><span data-stu-id="8a0b6-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="8a0b6-129">Unabhängig davon, ob Sie eDiscovery-oder rechtliche Aufbewahrungsmöglichkeiten für Dateien in einem privaten Kanal durchführen oder eine Branchen-app erstellen möchten, die Dateien in bestimmten privaten Kanälen platziert, sollten Sie eine Möglichkeit zum Abfragen der eindeutigen SharePoint-Websitesammlungen benötigen, die für jeden privaten Kanal.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="8a0b6-130">Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8a0b6-131">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a0b6-131">Using PowerShell</span></span>

1. <span data-ttu-id="8a0b6-132">Installieren Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) , und stellen Sie eine Verbindung mit Ihrem Administratorkonto her.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="8a0b6-133">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="8a0b6-134">(Sie können die Gruppen-ID einfach im Link zum Team finden.)</span><span class="sxs-lookup"><span data-stu-id="8a0b6-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="8a0b6-135">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="8a0b6-135">Using Graph API</span></span>

<span data-ttu-id="8a0b6-136">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8a0b6-137">Gehen Sie wie folgt vor, um die Liste der privaten Kanal-IDs für ein bestimmtes Team abzurufen, wobei <group_id> die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="8a0b6-138">Sie benötigen dies bei nachfolgenden anrufen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="8a0b6-139">(Sie können die Gruppen-ID einfach im Link zum Team finden).</span><span class="sxs-lookup"><span data-stu-id="8a0b6-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="8a0b6-140">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="8a0b6-141">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-141">**Response**</span></span>

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

2. <span data-ttu-id="8a0b6-142">Führen Sie für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen möchten, die &lt;folgende&gt; Anforderung aus, wobei channel_id die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="8a0b6-143">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="8a0b6-144">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-144">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="8a0b6-145">Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einem privaten Kanal</span><span class="sxs-lookup"><span data-stu-id="8a0b6-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="8a0b6-146">Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu einem Besitzer heraufstufen müssen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="8a0b6-147">Dies kann geschehen, wenn Sie Besitzer von privaten Kanälen sind, die die Organisation verlassen haben und der private Kanal Administratorhilfe benötigt, um den Besitz des Kanals zu beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="8a0b6-148">Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8a0b6-149">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a0b6-149">Using PowerShell</span></span>

1. <span data-ttu-id="8a0b6-150">Installieren Sie das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) mit Ihrem Administratorkonto, und stellen Sie eine Verbindung mit diesem her.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="8a0b6-151">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des &lt;Teams&gt; und channel_id die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="8a0b6-152">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="8a0b6-153">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-153">**Response**</span></span>

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

3. <span data-ttu-id="8a0b6-154">Höher Stufen eines Mitglieds zu einem Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a0b6-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="8a0b6-155">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="8a0b6-155">Using Graph API</span></span>

<span data-ttu-id="8a0b6-156">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="8a0b6-157">Verwenden Sie Folgendes, wobei &lt;group_id&gt; die Gruppen-ID des Teams und &lt;channel_id&gt; die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="8a0b6-158">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="8a0b6-159">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-159">**Response**</span></span>

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
2.  <span data-ttu-id="8a0b6-160">Führen Sie die folgenden Schritte aus, um das Mitglied für einen &lt;Besitzer&gt;zu &lt;bewerben&gt;, wobei &lt;group_id&gt; , channel_id und ID vom vorherigen Anruf zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="8a0b6-161">Beachten Sie &lt;,&gt; dass &lt;die&gt; vom vorherigen Anruf zurückgegebene ID und UserID nicht identisch sind und nicht austauschbar sind.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="8a0b6-162">Stellen Sie sicher, &lt;dass&gt;Sie ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a0b6-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="8a0b6-163">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="8a0b6-164">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="8a0b6-164">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="8a0b6-165">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8a0b6-165">Related topics</span></span>

- [<span data-ttu-id="8a0b6-166">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a0b6-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="8a0b6-167">Verwenden der Microsoft Graph-API zum Arbeiten mit Teams</span><span class="sxs-lookup"><span data-stu-id="8a0b6-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="8a0b6-168">Listen Kanäle</span><span class="sxs-lookup"><span data-stu-id="8a0b6-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="8a0b6-169">Kanal erstellen</span><span class="sxs-lookup"><span data-stu-id="8a0b6-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="8a0b6-170">Mitglied zu Kanal hinzufügen</span><span class="sxs-lookup"><span data-stu-id="8a0b6-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="8a0b6-171">Mitglied im Kanal aktualisieren</span><span class="sxs-lookup"><span data-stu-id="8a0b6-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="8a0b6-172">Mitglied aus Kanal entfernen</span><span class="sxs-lookup"><span data-stu-id="8a0b6-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)