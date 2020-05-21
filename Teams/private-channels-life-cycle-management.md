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
ms.openlocfilehash: 45d9591eed2bd3a880d3ca3e2ceb2252bf6f8898
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326692"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="250d3-103">Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="250d3-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="250d3-104">Hier finden Sie die Anleitungen, die Sie zum Verwalten des Lebenszyklus [privater Kanäle](private-channels.md) in Ihrer Organisation benötigen.</span><span class="sxs-lookup"><span data-stu-id="250d3-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="250d3-105">Wenn Sie die PowerShell-Schritte in diesem Artikel zum Verwalten privater Kanäle verwenden, müssen Sie die neueste Vorabversion des Teams PowerShell-Moduls aus dem [PowerShell-Test Katalog](https://www.poshtestgallery.com/packages/MicrosoftTeams/)installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="250d3-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="250d3-106">Eine schrittweise Anleitung zum Installieren des Moduls finden Sie unter [Installieren der Vorabversion des Teams PowerShell-Moduls](install-prerelease-teams-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="250d3-106">For steps on how to install the module, see [Install the pre-release version of the Teams PowerShell module](install-prerelease-teams-powershell-module.md).</span></span> <span data-ttu-id="250d3-107">Die neueste öffentlich verfügbare Version des Teams PowerShell-Moduls unterstützt nicht das Verwalten privater Kanäle.</span><span class="sxs-lookup"><span data-stu-id="250d3-107">The latest publicly available version of the Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="250d3-108">Festlegen, ob Teammitglieder private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="250d3-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="250d3-109">Teambesitzer können die Möglichkeit für Mitglieder, private Kanäle in Team Einstellungen zu erstellen, deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="250d3-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="250d3-110">Deaktivieren oder aktivieren Sie dazu auf der Registerkarte **Einstellungen** für das Team **zulassen, dass Mitglieder private Kanäle erstellen**.</span><span class="sxs-lookup"><span data-stu-id="250d3-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="250d3-111">Als Administrator können Sie die Diagramm-API verwenden, um zu steuern, ob Mitglieder private Kanäle in bestimmten Teams erstellen können.</span><span class="sxs-lookup"><span data-stu-id="250d3-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="250d3-112">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="250d3-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="250d3-113">Festlegen, ob Benutzer in Ihrer Organisation private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="250d3-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="250d3-114">Als Administrator können Sie Richtlinien festlegen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="250d3-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="250d3-115">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="250d3-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="250d3-116">Verwenden Sie die Richtlinien für Teams, um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="250d3-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="250d3-117">Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="250d3-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="250d3-118">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="250d3-118">Using PowerShell</span></span>

<span data-ttu-id="250d3-119">Verwenden Sie **CsTeamsChannelsPolicy** , um zu bestimmen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="250d3-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="250d3-120">Legen Sie den **AllowPrivateChannelCreation** -Parameter auf " **true** " fest, damit Benutzer, denen die Richtlinie zugewiesen ist, private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="250d3-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="250d3-121">Wenn der Parameter auf " **false** " festgelegt wird, wird die Möglichkeit zum Erstellen privater Kanäle für Benutzer deaktiviert, denen die Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="250d3-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="250d3-122">Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="250d3-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="250d3-123">Erstellen eines privaten Kanals im Auftrag eines Team Besitzers</span><span class="sxs-lookup"><span data-stu-id="250d3-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="250d3-124">Als Administrator können Sie die PowerShell-oder Diagramm-API verwenden, um einen privaten Kanal im Auftrag eines Team Besitzers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="250d3-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="250d3-125">Beispielsweise sollten Sie dies tun, wenn Ihre Organisation die Erstellung privater Kanäle zentralisieren möchte.</span><span class="sxs-lookup"><span data-stu-id="250d3-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="250d3-126">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="250d3-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="250d3-127">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="250d3-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="250d3-128">Abrufen einer Liste aller privaten Kanal Nachrichten</span><span class="sxs-lookup"><span data-stu-id="250d3-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="250d3-129">Möglicherweise möchten Sie eine Liste aller Nachrichten und Antworten abrufen, die in einem privaten Kanal zu Archivierungs-und Überwachungszwecken gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="250d3-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="250d3-130">Hier erfahren Sie, wie Sie die Diagramm-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="250d3-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="250d3-131">Suchen von SharePoint-URLs für alle privaten Kanäle in einem Team</span><span class="sxs-lookup"><span data-stu-id="250d3-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="250d3-132">Unabhängig davon, ob Sie eDiscovery-oder rechtliche Aufbewahrungsmöglichkeiten für Dateien in einem privaten Kanal durchführen oder eine benutzerdefinierte app erstellen möchten, mit der Dateien in bestimmten privaten Kanälen platziert werden, sollten Sie eine Möglichkeit zum Abfragen der eindeutigen SharePoint-Websitesammlungen benötigen, die für jeden privaten Kanal erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="250d3-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="250d3-133">Als Administrator können Sie PowerShell-oder Graph-APIs-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="250d3-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="250d3-134">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="250d3-134">Using PowerShell</span></span>

1. <span data-ttu-id="250d3-135">Installieren Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) , und stellen Sie eine Verbindung mit Ihrem Administratorkonto her.</span><span class="sxs-lookup"><span data-stu-id="250d3-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="250d3-136">Führen Sie die folgenden Schritte &lt; aus, wobei group_id &gt; die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="250d3-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="250d3-137">(Sie können die Gruppen-ID einfach im Link zum Team finden.)</span><span class="sxs-lookup"><span data-stu-id="250d3-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="250d3-138">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="250d3-138">Using Graph API</span></span>

<span data-ttu-id="250d3-139">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="250d3-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="250d3-140">Führen Sie die folgenden Schritte aus, um die Liste der privaten Kanal-IDs für ein bestimmtes Team abzurufen, wobei <group_id> die Gruppen-ID des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="250d3-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="250d3-141">Sie benötigen dies bei nachfolgenden anrufen.</span><span class="sxs-lookup"><span data-stu-id="250d3-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="250d3-142">(Sie können die Gruppen-ID einfach im Link zum Team finden).</span><span class="sxs-lookup"><span data-stu-id="250d3-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="250d3-143">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="250d3-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="250d3-144">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="250d3-144">**Response**</span></span>

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

2. <span data-ttu-id="250d3-145">Führen Sie für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen möchten, die folgende Anforderung aus, wobei &lt; channel_id &gt; die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="250d3-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="250d3-146">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="250d3-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="250d3-147">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="250d3-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="250d3-148">Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einem privaten Kanal</span><span class="sxs-lookup"><span data-stu-id="250d3-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="250d3-149">Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu einem Besitzer heraufstufen müssen.</span><span class="sxs-lookup"><span data-stu-id="250d3-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="250d3-150">Dies kann geschehen, wenn Sie Besitzer von privaten Kanälen sind, die die Organisation verlassen haben und der private Kanal Administratorhilfe benötigt, um den Besitz des Kanals zu beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="250d3-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="250d3-151">Als Administrator können Sie die Microsoft Teams Admin Center-, PowerShell-oder Graph-API verwenden, um diese Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="250d3-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="250d3-152">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="250d3-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="250d3-153">Informationen zum Verwalten von Teammitgliedern mithilfe des Microsoft Teams admin Centers finden Sie unter [Verwalten von Teams im Microsoft Teams Admin Center](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="250d3-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="250d3-154">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="250d3-154">Using PowerShell</span></span>

1. <span data-ttu-id="250d3-155">Führen Sie die folgenden Schritte &lt; aus, wobei group_id &gt; die Gruppen-ID des Teams und &lt; channel_name &gt; der Kanal Name ist.</span><span class="sxs-lookup"><span data-stu-id="250d3-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="250d3-156">Höher Stufen eines Mitglieds zu einem Besitzer</span><span class="sxs-lookup"><span data-stu-id="250d3-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="250d3-157">Verwenden der Diagramm-API</span><span class="sxs-lookup"><span data-stu-id="250d3-157">Using Graph API</span></span>

<span data-ttu-id="250d3-158">Sie können diese Befehle über den [Diagramm-Explorer](https://developer.microsoft.com/graph/graph-explorer)testen.</span><span class="sxs-lookup"><span data-stu-id="250d3-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="250d3-159">Verwenden Sie Folgendes, wobei &lt; group_id &gt; die Gruppen-ID des Teams und &lt; channel_id &gt; die Kanal-ID ist.</span><span class="sxs-lookup"><span data-stu-id="250d3-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="250d3-160">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="250d3-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="250d3-161">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="250d3-161">**Response**</span></span>

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
2. <span data-ttu-id="250d3-162">Führen Sie die folgenden Schritte aus, um das Mitglied für einen Besitzer zu bewerben, wobei &lt; group_id &gt; , &lt; channel_id &gt; und &lt; ID &gt; vom vorherigen Anruf zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="250d3-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="250d3-163">Beachten Sie, dass die &lt; &gt; &lt; &gt; vom vorherigen Anruf zurückgegebene ID und UserID nicht identisch sind und nicht austauschbar sind.</span><span class="sxs-lookup"><span data-stu-id="250d3-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="250d3-164">Stellen Sie sicher, dass Sie &lt; ID verwenden &gt; .</span><span class="sxs-lookup"><span data-stu-id="250d3-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="250d3-165">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="250d3-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="250d3-166">**Reaktion**</span><span class="sxs-lookup"><span data-stu-id="250d3-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="250d3-167">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="250d3-167">Related topics</span></span>

- [<span data-ttu-id="250d3-168">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="250d3-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="250d3-169">Verwenden der Microsoft Graph-API zum Arbeiten mit Teams</span><span class="sxs-lookup"><span data-stu-id="250d3-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="250d3-170">Listen Kanäle</span><span class="sxs-lookup"><span data-stu-id="250d3-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="250d3-171">Kanal erstellen</span><span class="sxs-lookup"><span data-stu-id="250d3-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="250d3-172">Mitglied zu Kanal hinzufügen</span><span class="sxs-lookup"><span data-stu-id="250d3-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="250d3-173">Mitglied im Kanal aktualisieren</span><span class="sxs-lookup"><span data-stu-id="250d3-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="250d3-174">Mitglied aus Kanal entfernen</span><span class="sxs-lookup"><span data-stu-id="250d3-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
