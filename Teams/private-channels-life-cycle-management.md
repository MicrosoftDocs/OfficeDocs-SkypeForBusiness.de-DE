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
ms.openlocfilehash: 39830035ba91b2fa50c7d5bbd82e6da6e60d0f00
ms.sourcegitcommit: 379bfaf6b0584c1ac93341af605f93ab932a442b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240635"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="9abef-103">Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9abef-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="9abef-104">Hier finden Sie die Anleitungen, die Sie zum Verwalten des Lebenszyklus [privater Kanäle](private-channels.md) in Ihrer Organisation benötigen.</span><span class="sxs-lookup"><span data-stu-id="9abef-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9abef-105">Wenn Sie die PowerShell-Schritte in diesem Artikel zum Verwalten privater Kanäle verwenden, müssen Sie die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="9abef-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="9abef-106">Eine schrittweise Anleitung hierzu finden Sie unter [Installieren des neuesten Teams PowerShell-Moduls aus dem PowerShell-Test Katalog](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span><span class="sxs-lookup"><span data-stu-id="9abef-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="9abef-107">Die neueste öffentlich verfügbare Version des Teams PowerShell-Moduls (derzeit [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) unterstützt keine Verwaltung privater Kanäle.</span><span class="sxs-lookup"><span data-stu-id="9abef-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="9abef-108">Festlegen, ob Teammitglieder private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="9abef-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="9abef-109">Teambesitzer können die Möglichkeit für Mitglieder, private Kanäle in Team Einstellungen zu erstellen, deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9abef-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="9abef-110">Deaktivieren oder aktivieren Sie dazu auf der Registerkarte **Einstellungen** für das Team **zulassen, dass Mitglieder private Kanäle erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9abef-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="9abef-111">Als Administrator können Sie die Diagramm-API verwenden, um zu steuern, ob Mitglieder private Kanäle in bestimmten Teams erstellen können.</span><span class="sxs-lookup"><span data-stu-id="9abef-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="9abef-112">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9abef-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="9abef-113">Festlegen, ob Benutzer in Ihrer Organisation private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="9abef-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="9abef-114">Als Administrator können Sie Richtlinien festlegen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="9abef-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9abef-115">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="9abef-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9abef-116">Verwenden Sie die Richtlinien für Teams, um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="9abef-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="9abef-117">Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9abef-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9abef-118">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9abef-118">Using PowerShell</span></span>

<span data-ttu-id="9abef-119">Verwenden Sie **CsTeamsChannelsPolicy** , um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="9abef-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="9abef-120">Legen Sie den **AllowPrivateChannelCreation** -Parameter auf " **true** " fest, damit Benutzer, denen die Richtlinie zugewiesen ist, private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="9abef-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="9abef-121">Wenn der Parameter auf " **false** " festgelegt wird, wird die Möglichkeit zum Erstellen privater Kanäle für Benutzer deaktiviert, denen die Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="9abef-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="9abef-122">Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9abef-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="9abef-123">Erstellen eines privaten Kanals im Auftrag eines Team Besitzers</span><span class="sxs-lookup"><span data-stu-id="9abef-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="9abef-124">Als Administrator können Sie die PowerShell-oder Diagramm-API verwenden, um einen privaten Kanal im Auftrag eines Team Besitzers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9abef-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="9abef-125">Beispielsweise sollten Sie dies tun, wenn Ihre Organisation die Erstellung privater Kanäle zentralisieren möchte.</span><span class="sxs-lookup"><span data-stu-id="9abef-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9abef-126">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9abef-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="9abef-127">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="9abef-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="9abef-128">Abrufen einer Liste aller privaten Kanal Nachrichten</span><span class="sxs-lookup"><span data-stu-id="9abef-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="9abef-129">Möglicherweise möchten Sie eine Liste aller Nachrichten und Antworten abrufen, die in einem privaten Kanal zu Archivierungs-und Überwachungszwecken gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="9abef-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="9abef-130">Hier erfahren Sie, wie Sie die Diagramm-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="9abef-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="9abef-131">Suchen von SharePoint-URLs für alle privaten Kanäle in einem Team</span><span class="sxs-lookup"><span data-stu-id="9abef-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="9abef-132">Unabhängig davon, ob Sie eDiscovery-oder rechtliche Aufbewahrungsmöglichkeiten für Dateien in einem privaten Kanal durchführen oder eine Branchen-app erstellen möchten, die Dateien in bestimmten privaten Kanälen platziert, sollten Sie eine Möglichkeit zum Abfragen der eindeutigen SharePoint-Websitesammlungen benötigen, die für jeden privaten Kanal erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9abef-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="9abef-133">Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="9abef-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9abef-134">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9abef-134">Using PowerShell</span></span>

1. <span data-ttu-id="9abef-135">Installieren Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) , und stellen Sie eine Verbindung mit Ihrem Administratorkonto her.</span><span class="sxs-lookup"><span data-stu-id="9abef-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="9abef-136">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="9abef-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="9abef-137">(Sie können die Gruppen-ID einfach im Link zum Team finden.)</span><span class="sxs-lookup"><span data-stu-id="9abef-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="9abef-138">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="9abef-138">Using Graph API</span></span>

<span data-ttu-id="9abef-139">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="9abef-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="9abef-140">Führen Sie die folgenden Schritte aus, um die Liste der privaten Kanal-IDs für ein bestimmtes Team abzurufen, wobei <group_id> die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="9abef-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="9abef-141">Sie benötigen dies bei nachfolgenden anrufen.</span><span class="sxs-lookup"><span data-stu-id="9abef-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="9abef-142">(Sie können die Gruppen-ID einfach im Link zum Team finden).</span><span class="sxs-lookup"><span data-stu-id="9abef-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="9abef-143">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9abef-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="9abef-144">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="9abef-144">**Response**</span></span>

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

2. <span data-ttu-id="9abef-145">Führen Sie für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen möchten, die &lt;folgende&gt; Anforderung aus, wobei channel_id die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="9abef-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="9abef-146">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9abef-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="9abef-147">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="9abef-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="9abef-148">Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einem privaten Kanal</span><span class="sxs-lookup"><span data-stu-id="9abef-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="9abef-149">Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu einem Besitzer heraufstufen müssen.</span><span class="sxs-lookup"><span data-stu-id="9abef-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="9abef-150">Dies kann geschehen, wenn Sie Besitzer von privaten Kanälen sind, die die Organisation verlassen haben und der private Kanal Administratorhilfe benötigt, um den Besitz des Kanals zu beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="9abef-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="9abef-151">Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="9abef-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9abef-152">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9abef-152">Using PowerShell</span></span>

1. <span data-ttu-id="9abef-153">Führen Sie die folgenden Schritte &lt;aus&gt; , wobei group_id die Gruppen-ID des &lt;Teams&gt; und channel_name der Kanal Name ist.</span><span class="sxs-lookup"><span data-stu-id="9abef-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="9abef-154">Höher Stufen eines Mitglieds zu einem Besitzer</span><span class="sxs-lookup"><span data-stu-id="9abef-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="9abef-155">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="9abef-155">Using Graph API</span></span>

<span data-ttu-id="9abef-156">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="9abef-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="9abef-157">Verwenden Sie Folgendes, wobei &lt;group_id&gt; die Gruppen-ID des Teams und &lt;channel_id&gt; die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="9abef-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="9abef-158">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9abef-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="9abef-159">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="9abef-159">**Response**</span></span>

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
2.  <span data-ttu-id="9abef-160">Führen Sie die folgenden Schritte aus, um das Mitglied für einen &lt;Besitzer&gt;zu &lt;bewerben&gt;, wobei &lt;group_id&gt; , channel_id und ID vom vorherigen Anruf zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9abef-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="9abef-161">Beachten Sie &lt;,&gt; dass &lt;die&gt; vom vorherigen Anruf zurückgegebene ID und UserID nicht identisch sind und nicht austauschbar sind.</span><span class="sxs-lookup"><span data-stu-id="9abef-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="9abef-162">Stellen Sie sicher, &lt;dass&gt;Sie ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="9abef-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="9abef-163">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="9abef-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="9abef-164">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="9abef-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="9abef-165">Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="9abef-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="9abef-166">Installieren des neuesten Teams PowerShell-Moduls aus dem PowerShell-Test Katalog</span><span class="sxs-lookup"><span data-stu-id="9abef-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="9abef-167">Die neueste öffentlich verfügbare Version des Teams PowerShell-Moduls (derzeit [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) unterstützt keine Verwaltung privater Kanäle.</span><span class="sxs-lookup"><span data-stu-id="9abef-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) doesn't support managing private channels.</span></span> <span data-ttu-id="9abef-168">Führen Sie die folgenden Schritte aus, um die neueste Version des Teams PowerShell-Moduls mit privater Kanal Unterstützung (derzeit 1.0.21) aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9abef-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.21) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="9abef-169">Installieren Sie das Teams PowerShell-Modul nicht aus dem PowerShell-Test Katalog parallel mit einer Version des Moduls aus dem öffentlichen PowerShell-Katalog.</span><span class="sxs-lookup"><span data-stu-id="9abef-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="9abef-170">Führen Sie die folgenden Schritte aus, um das Team-PowerShell-Modul zunächst aus dem öffentlichen PowerShell-Katalog zu deinstallieren und dann die neueste Version des Moduls aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9abef-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="9abef-171">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9abef-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="9abef-172">Starten Sie eine neue Instanz des Windows PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="9abef-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="9abef-173">Führen Sie die folgenden Schritte aus, um das PowerShell-Modul von Teams aus dem öffentlichen PowerShell-Katalog zu deinstallieren:</span><span class="sxs-lookup"><span data-stu-id="9abef-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="9abef-174">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9abef-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="9abef-175">Starten Sie das Windows PowerShell-Modul erneut, und führen Sie dann die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="9abef-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="9abef-176">Führen Sie die folgenden Schritte aus, um das neueste Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren:</span><span class="sxs-lookup"><span data-stu-id="9abef-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="9abef-177">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="9abef-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="9abef-178">Aktualisieren auf die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog</span><span class="sxs-lookup"><span data-stu-id="9abef-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="9abef-179">Wenn Sie das Teams PowerShell-Modul bereits aus dem PowerShell-Test Katalog installiert haben, führen Sie die folgenden Schritte aus, um auf die neueste Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9abef-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="9abef-180">Schließen Sie alle vorhandenen PowerShell-Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9abef-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="9abef-181">Starten Sie eine neue Instanz des Windows PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="9abef-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="9abef-182">Führen Sie die folgenden Schritte aus, um die aktuell installierte Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="9abef-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="9abef-183">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die neueste Version des Teams PowerShell-Moduls aus dem PowerShell-Test Katalog erfolgreich installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="9abef-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="9abef-184">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9abef-184">Related topics</span></span>

- [<span data-ttu-id="9abef-185">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9abef-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="9abef-186">Verwenden der Microsoft Graph-API zum Arbeiten mit Teams</span><span class="sxs-lookup"><span data-stu-id="9abef-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="9abef-187">Listen Kanäle</span><span class="sxs-lookup"><span data-stu-id="9abef-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="9abef-188">Kanal erstellen</span><span class="sxs-lookup"><span data-stu-id="9abef-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="9abef-189">Mitglied zu Kanal hinzufügen</span><span class="sxs-lookup"><span data-stu-id="9abef-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="9abef-190">Mitglied im Kanal aktualisieren</span><span class="sxs-lookup"><span data-stu-id="9abef-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="9abef-191">Mitglied aus Kanal entfernen</span><span class="sxs-lookup"><span data-stu-id="9abef-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
