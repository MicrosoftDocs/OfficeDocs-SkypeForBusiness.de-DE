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
ms.openlocfilehash: 0f2a1f9fc4921ae12092655102d4a442fd653df3
ms.sourcegitcommit: f3b698379eb663202ce127eeaf6c07328c166556
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2019
ms.locfileid: "38077408"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="4c661-103">Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c661-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="4c661-104">Hier finden Sie die Anleitungen, die Sie zum Verwalten des Lebenszyklus [privater Kanäle](private-channels.md) in Ihrer Organisation benötigen.</span><span class="sxs-lookup"><span data-stu-id="4c661-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c661-105">Wenn Sie die PowerShell-Schritte in diesem Artikel zum Verwalten privater Kanäle verwenden, müssen Sie die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c661-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="4c661-106">Eine schrittweise Anleitung hierzu finden Sie unter [Installieren des neuesten Teams PowerShell-Moduls aus dem PowerShell-Test Katalog](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span><span class="sxs-lookup"><span data-stu-id="4c661-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="4c661-107">Die neueste öffentlich verfügbare Version des Teams PowerShell-Moduls (derzeit [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) unterstützt keine Verwaltung privater Kanäle.</span><span class="sxs-lookup"><span data-stu-id="4c661-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="4c661-108">Festlegen, ob Teammitglieder private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="4c661-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="4c661-109">Teambesitzer können die Möglichkeit für Mitglieder, private Kanäle in Team Einstellungen zu erstellen, deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4c661-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="4c661-110">Deaktivieren oder aktivieren Sie dazu auf der Registerkarte **Einstellungen** für das Team **zulassen, dass Mitglieder private Kanäle erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4c661-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="4c661-111">Als Administrator können Sie die Diagramm-API verwenden, um zu steuern, ob Mitglieder private Kanäle in bestimmten Teams erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4c661-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="4c661-112">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4c661-112">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="4c661-113">Festlegen, ob Benutzer in Ihrer Organisation private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="4c661-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="4c661-114">Als Administrator können Sie Richtlinien festlegen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="4c661-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4c661-115">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="4c661-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4c661-116">Verwenden Sie die Richtlinien für Teams, um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="4c661-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="4c661-117">Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4c661-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c661-118">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c661-118">Using PowerShell</span></span>

<span data-ttu-id="4c661-119">Verwenden Sie **CsTeamsChannelsPolicy** , um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="4c661-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="4c661-120">Legen Sie den **AllowPrivateChannelCreation** -Parameter auf " **true** " fest, damit Benutzer, denen die Richtlinie zugewiesen ist, private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4c661-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="4c661-121">Wenn der Parameter auf " **false** " festgelegt wird, wird die Möglichkeit zum Erstellen privater Kanäle für Benutzer deaktiviert, denen die Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4c661-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="4c661-122">Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4c661-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="4c661-123">Erstellen eines privaten Kanals im Auftrag eines Team Besitzers</span><span class="sxs-lookup"><span data-stu-id="4c661-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="4c661-124">Als Administrator können Sie die PowerShell-oder Diagramm-API verwenden, um einen privaten Kanal im Auftrag eines Team Besitzers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c661-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="4c661-125">Beispielsweise sollten Sie dies tun, wenn Ihre Organisation die Erstellung privater Kanäle zentralisieren möchte.</span><span class="sxs-lookup"><span data-stu-id="4c661-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c661-126">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c661-126">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="4c661-127">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="4c661-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="4c661-128">Abrufen einer Liste aller privaten Kanal Nachrichten</span><span class="sxs-lookup"><span data-stu-id="4c661-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="4c661-129">Möglicherweise möchten Sie eine Liste aller Nachrichten und Antworten abrufen, die in einem privaten Kanal zu Archivierungs-und Überwachungszwecken gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="4c661-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="4c661-130">Hier erfahren Sie, wie Sie die Diagramm-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c661-130">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="4c661-131">Suchen von SharePoint-URLs für alle privaten Kanäle in einem Team</span><span class="sxs-lookup"><span data-stu-id="4c661-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="4c661-132">Unabhängig davon, ob Sie eDiscovery-oder rechtliche Aufbewahrungsmöglichkeiten für Dateien in einem privaten Kanal durchführen oder eine Branchen-app erstellen möchten, die Dateien in bestimmten privaten Kanälen platziert, sollten Sie eine Möglichkeit zum Abfragen der eindeutigen SharePoint-Websitesammlungen benötigen, die für jeden privaten Kanal.</span><span class="sxs-lookup"><span data-stu-id="4c661-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="4c661-133">Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="4c661-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c661-134">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c661-134">Using PowerShell</span></span>

1. <span data-ttu-id="4c661-135">Installieren Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) , und stellen Sie eine Verbindung mit Ihrem Administratorkonto her.</span><span class="sxs-lookup"><span data-stu-id="4c661-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="4c661-136">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="4c661-136">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="4c661-137">(Sie können die Gruppen-ID einfach im Link zum Team finden.)</span><span class="sxs-lookup"><span data-stu-id="4c661-137">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="4c661-138">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="4c661-138">Using Graph API</span></span>

<span data-ttu-id="4c661-139">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="4c661-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="4c661-140">Führen Sie die folgenden Schritte aus, um die Liste der privaten Kanal-IDs für ein bestimmtes Team abzurufen, wobei <group_id> die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="4c661-140">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="4c661-141">Sie benötigen dies bei nachfolgenden anrufen.</span><span class="sxs-lookup"><span data-stu-id="4c661-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="4c661-142">(Sie können die Gruppen-ID einfach im Link zum Team finden).</span><span class="sxs-lookup"><span data-stu-id="4c661-142">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="4c661-143">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4c661-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="4c661-144">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="4c661-144">**Response**</span></span>

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

2. <span data-ttu-id="4c661-145">Führen Sie für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen möchten, die &lt;folgende&gt; Anforderung aus, wobei channel_id die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="4c661-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="4c661-146">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4c661-146">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="4c661-147">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="4c661-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="4c661-148">Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einem privaten Kanal</span><span class="sxs-lookup"><span data-stu-id="4c661-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="4c661-149">Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu einem Besitzer heraufstufen müssen.</span><span class="sxs-lookup"><span data-stu-id="4c661-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="4c661-150">Dies kann geschehen, wenn Sie Besitzer von privaten Kanälen sind, die die Organisation verlassen haben und der private Kanal Administratorhilfe benötigt, um den Besitz des Kanals zu beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="4c661-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="4c661-151">Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="4c661-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4c661-152">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c661-152">Using PowerShell</span></span>

1. <span data-ttu-id="4c661-153">Installieren Sie das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) mit Ihrem Administratorkonto, und stellen Sie eine Verbindung mit diesem her.</span><span class="sxs-lookup"><span data-stu-id="4c661-153">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="4c661-154">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des &lt;Teams&gt; und channel_id die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="4c661-154">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="4c661-155">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4c661-155">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="4c661-156">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="4c661-156">**Response**</span></span>

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

3. <span data-ttu-id="4c661-157">Höher Stufen eines Mitglieds zu einem Besitzer</span><span class="sxs-lookup"><span data-stu-id="4c661-157">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="4c661-158">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="4c661-158">Using Graph API</span></span>

<span data-ttu-id="4c661-159">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="4c661-159">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="4c661-160">Verwenden Sie Folgendes, wobei &lt;group_id&gt; die Gruppen-ID des Teams und &lt;channel_id&gt; die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="4c661-160">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="4c661-161">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4c661-161">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="4c661-162">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="4c661-162">**Response**</span></span>

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
2.  <span data-ttu-id="4c661-163">Führen Sie die folgenden Schritte aus, um das Mitglied für einen &lt;Besitzer&gt;zu &lt;bewerben&gt;, wobei &lt;group_id&gt; , channel_id und ID vom vorherigen Anruf zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c661-163">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="4c661-164">Beachten Sie &lt;,&gt; dass &lt;die&gt; vom vorherigen Anruf zurückgegebene ID und UserID nicht identisch sind und nicht austauschbar sind.</span><span class="sxs-lookup"><span data-stu-id="4c661-164">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="4c661-165">Stellen Sie sicher, &lt;dass&gt;Sie ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c661-165">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="4c661-166">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="4c661-166">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="4c661-167">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="4c661-167">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="4c661-168">Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="4c661-168">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="4c661-169">Installieren des neuesten Teams PowerShell-Moduls aus dem PowerShell-Test Katalog</span><span class="sxs-lookup"><span data-stu-id="4c661-169">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="4c661-170">Die neueste öffentlich verfügbare Version des Teams PowerShell-Moduls (derzeit [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) unterstützt keine Verwaltung privater Kanäle.</span><span class="sxs-lookup"><span data-stu-id="4c661-170">The latest publicly available version of the Teams PowerShell module (currently [1.0.2](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.2)) doesn't support managing private channels.</span></span> <span data-ttu-id="4c661-171">Führen Sie die folgenden Schritte aus, um die neueste Version des Teams PowerShell-Moduls mit privater Kanal Unterstützung (derzeit 1.0.18) aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4c661-171">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.18) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="4c661-172">Installieren Sie das Teams PowerShell-Modul nicht aus dem PowerShell-Test Katalog parallel mit einer Version des Moduls aus dem öffentlichen PowerShell-Katalog.</span><span class="sxs-lookup"><span data-stu-id="4c661-172">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="4c661-173">Führen Sie die folgenden Schritte aus, um das Team-PowerShell-Modul zunächst aus dem öffentlichen PowerShell-Katalog zu deinstallieren und dann die neueste Version des Moduls aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4c661-173">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="4c661-174">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4c661-174">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="4c661-175">Starten Sie eine neue Instanz des Windows PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="4c661-175">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="4c661-176">Führen Sie die folgenden Schritte aus, um das PowerShell-Modul von Teams aus dem öffentlichen PowerShell-Katalog zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="4c661-176">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="4c661-177">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4c661-177">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="4c661-178">Starten Sie das Windows PowerShell-Modul erneut, und führen Sie dann die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="4c661-178">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="4c661-179">Führen Sie die folgenden Schritte aus, um das neueste Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren:</span><span class="sxs-lookup"><span data-stu-id="4c661-179">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="4c661-180">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="4c661-180">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="4c661-181">Aktualisieren auf die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog</span><span class="sxs-lookup"><span data-stu-id="4c661-181">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="4c661-182">Wenn Sie das Teams PowerShell-Modul bereits aus dem PowerShell-Test Katalog installiert haben, führen Sie die folgenden Schritte aus, um auf die neueste Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4c661-182">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="4c661-183">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4c661-183">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="4c661-184">Starten Sie eine neue Instanz des Windows PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="4c661-184">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="4c661-185">Führen Sie die folgenden Schritte aus, um die aktuell installierte Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="4c661-185">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="4c661-186">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="4c661-186">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="4c661-187">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4c661-187">Related topics</span></span>

- [<span data-ttu-id="4c661-188">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c661-188">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="4c661-189">Verwenden der Microsoft Graph-API zum Arbeiten mit Teams</span><span class="sxs-lookup"><span data-stu-id="4c661-189">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="4c661-190">Listen Kanäle</span><span class="sxs-lookup"><span data-stu-id="4c661-190">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="4c661-191">Kanal erstellen</span><span class="sxs-lookup"><span data-stu-id="4c661-191">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="4c661-192">Mitglied zu Kanal hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4c661-192">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="4c661-193">Mitglied im Kanal aktualisieren</span><span class="sxs-lookup"><span data-stu-id="4c661-193">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="4c661-194">Mitglied aus Kanal entfernen</span><span class="sxs-lookup"><span data-stu-id="4c661-194">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)