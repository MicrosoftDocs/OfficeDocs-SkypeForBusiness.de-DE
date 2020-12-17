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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="a2cf8-103">Verwalten des Lebenszyklus von privaten Kanälen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a2cf8-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="a2cf8-104">Hier finden Sie die Anleitungen, die Sie benötigen, um den Lebenszyklus von [privaten Kanälen](private-channels.md) in Ihrer Organisation zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2cf8-105">Wenn Sie die PowerShell-Schritte in diesem Artikel zur Verwaltung von privaten Kanälen verwenden, müssen Sie das Teams PowerShell Public Preview-Module aus dem [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams/) installieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="a2cf8-106">Die Schritte zur Installation des Moduls finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="a2cf8-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="a2cf8-107">Das aktuelle, generell verfügbare Teams PowerShell-Modul unterstützt die Verwaltung von privaten Kanälen nicht.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="a2cf8-108">Festlegen, ob Teammitglieder private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="a2cf8-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="a2cf8-109">Teambesitzer können die Berechtigung von Mitgliedern zur Erstellung von privaten Kanälen in den Teameinstellungen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="a2cf8-110">Dafür müssen sie in der Registerkarte **Einstellungen** für das Team die Option **Die Erstellung von privaten Kanälen durch Mitglieder zulassen** deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="a2cf8-111">Als Administrator können Sie das Graph-API verwenden, um zu kontrollieren, ob Mitglieder private Kanäle in bestimmten Teams erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="a2cf8-112">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="a2cf8-113">Festlegen ob Benutzer in Ihrer Organisation private Kanäle erstellen können</span><span class="sxs-lookup"><span data-stu-id="a2cf8-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="a2cf8-114">Als Administrator können Sie Richtlinien über das Microsoft Teams Admin Center oder PowerShell festlegen, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a2cf8-115">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="a2cf8-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a2cf8-116">Verwenden Sie Teamrichtlinien, um zu steuern, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="a2cf8-117">Weitere Informationen finden Sie unter [Verwalten von Teamrichtlinien in Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a2cf8-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a2cf8-118">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2cf8-118">Using PowerShell</span></span>

<span data-ttu-id="a2cf8-119">Verwenden Sie **CsTeamsChannelsPolicy**, um festzulegen, welche Benutzer in Ihrer Organisation private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="a2cf8-120">Setzen Sie den Parameter **AllowPrivateChannelCreation** auf **wahr**, um Benutzern, denen die Richtlinie zugewiesen ist, das Erstellen von privaten Kanälen zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="a2cf8-121">Wenn Sie den Parameter auf **falsch** setzen, dann können Benutzer, denen die Richtlinie zugewiesen ist, keine privaten Kanäle mehr erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="a2cf8-122">Weitere Informationen finden Sie unter [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a2cf8-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="a2cf8-123">Erstellen eines privaten Kanals im Auftrag eines Teambesitzers</span><span class="sxs-lookup"><span data-stu-id="a2cf8-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="a2cf8-124">Als Administrator können Sie PowerShell oder das Graph-API verwenden, um im Auftrag eines Teambesitzers einen privaten Kanal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="a2cf8-125">Sie können dies beispielsweise so umsetzen, wenn Ihre Organisation die Erstellung von privaten Kanälen zentralisieren will.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a2cf8-126">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2cf8-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="a2cf8-127">Verwendung des Graph-API</span><span class="sxs-lookup"><span data-stu-id="a2cf8-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="a2cf8-128">Abrufen einer Liste aller privaten Kanalnachrichten</span><span class="sxs-lookup"><span data-stu-id="a2cf8-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="a2cf8-129">Aus Archivierungs- und Überwachungsgründen möchten Sie allenfalls eine Liste aller in einem privaten Kanal veröffentlichten Nachrichten und Antworten abrufen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="a2cf8-130">So verwenden Sie das Graph-API, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="a2cf8-131">Finden der SharePoint-URLs für alle privaten Kanäle in einem Team</span><span class="sxs-lookup"><span data-stu-id="a2cf8-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="a2cf8-132">Unabhängig davon, ob Sie eDiscovery oder die Aufbewahrung für juristische Zwecke in einem privaten Kanal durchführen, oder eine benutzerdefinierte App erstellen möchten, die Dateien in bestimmten privaten Kanälen platziert: Sie wollen eine Möglichkeit zur Abfrage der eindeutigen SharePoint-Websitesammlungen haben, die für jeden privaten Kanal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="a2cf8-133">Als Administrator können Sie PowerShell- oder Graph-API-Befehle verwenden, um diese URLs abzufragen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a2cf8-134">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2cf8-134">Using PowerShell</span></span>

1. <span data-ttu-id="a2cf8-135">Installieren und verbinden Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) mit Ihrem Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="a2cf8-136">Führen Sie den folgenden Befehl aus, wobei &lt;group_id&gt; die Gruppen-Identifikation des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="a2cf8-137">(Sie finden die Gruppen-Identifikation ganz einfach im Link zum Team.)</span><span class="sxs-lookup"><span data-stu-id="a2cf8-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="a2cf8-138">Verwendung des Graph-API</span><span class="sxs-lookup"><span data-stu-id="a2cf8-138">Using Graph API</span></span>

<span data-ttu-id="a2cf8-139">Sie können diese Befehle über den [Graph-Tester](https://developer.microsoft.com/graph/graph-explorer) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="a2cf8-140">Verwenden Sie den folgenden Befehl, um eine Liste aller privaten Kanal-IDs für ein bestimmtes Team zu erhalten, wobei <group_id> die Gruppen-Identifikation des Teams ist.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="a2cf8-141">Sie benötigen dies in nachfolgenden Aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="a2cf8-142">(Sie finden die Gruppen-Identifikation ganz einfach im Link zum Team).</span><span class="sxs-lookup"><span data-stu-id="a2cf8-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="a2cf8-143">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="a2cf8-144">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-144">**Response**</span></span>

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

2. <span data-ttu-id="a2cf8-145">Für jeden privaten Kanal, für den Sie die SharePoint-URL abrufen wollen, führen Sie die folgende Anforderung aus, wobei &lt;channel_id&gt; die Kanal-Identifikation ist.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="a2cf8-146">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="a2cf8-147">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="a2cf8-148">Auflisten und Aktualisieren der Rollen von Besitzern und Mitgliedern in einen privaten Kanal</span><span class="sxs-lookup"><span data-stu-id="a2cf8-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="a2cf8-149">Möglicherweise möchten Sie die Besitzer und Mitglieder eines privaten Kanals auflisten, um zu entscheiden, ob Sie bestimmte Mitglieder des privaten Kanals zu Besitzer hochstufen müssen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="a2cf8-150">Dies kann der Fall sein, wenn Besitzer von privaten Kanälen die Organisation verlassen haben und der private Kanal die Hilfe eines Administrator benötigt, um den Besitz des Kanals wieder zu beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="a2cf8-151">Als Administrator können Sie das Microsoft Teams Admin Center, PowerShell oder das Graph-API für die Durchführung dieser Aktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a2cf8-152">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="a2cf8-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a2cf8-153">Weitere Informationen über die Verwaltung von Teammitglieder mit dem Microsoft Teams Admin Center finden Sie unter [Teams im Microsoft Teams Admin Center verwalten](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="a2cf8-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="a2cf8-154">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2cf8-154">Using PowerShell</span></span>

1. <span data-ttu-id="a2cf8-155">Führen Sie den folgenden Befehl aus, wobei &lt;group_id&gt; die Gruppen-Identifikation des Teams und &lt;channel_name&gt; der Kanalname ist.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="a2cf8-156">Höherstufen eines Mitglieds zum Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="a2cf8-157">Verwendung des Graph-API</span><span class="sxs-lookup"><span data-stu-id="a2cf8-157">Using Graph API</span></span>

<span data-ttu-id="a2cf8-158">Sie können diese Befehle über den [Graph-Tester](https://developer.microsoft.com/graph/graph-explorer) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="a2cf8-159">Verwenden Sie den folgenden Befehl, wobei &lt;group_id&gt; die Gruppen-Identifikation des Teams und &lt;channel_name&gt; der Kanalname ist.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="a2cf8-160">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="a2cf8-161">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-161">**Response**</span></span>

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
2. <span data-ttu-id="a2cf8-162">Verwenden Sie den folgenden Befehl, um das Mitglied zum Besitzer hochzustufen, wobei &lt;group_id&gt;, &lt;channel_id&gt;, und &lt;id&gt; in einem früheren Aufruf zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="a2cf8-163">Beachten Sie, dass &lt;id&gt; und &lt;userId&gt;, welche aus einem früheren Aufruf zurückgegeben wurden, nicht dasselbe und nicht austauschbar sind.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="a2cf8-164">Stellen Sie sicher, dass Sie &lt;id&gt; verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="a2cf8-165">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="a2cf8-166">**Antwort**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="a2cf8-167">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a2cf8-167">Related topics</span></span>

- [<span data-ttu-id="a2cf8-168">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a2cf8-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a2cf8-169">Verwenden der Microsoft Graph-API zum Arbeiten mit Teams</span><span class="sxs-lookup"><span data-stu-id="a2cf8-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="a2cf8-170">Kanäle auflisten</span><span class="sxs-lookup"><span data-stu-id="a2cf8-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="a2cf8-171">Kanal erstellen</span><span class="sxs-lookup"><span data-stu-id="a2cf8-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="a2cf8-172">Mitglied zum Kanal hinzufügen</span><span class="sxs-lookup"><span data-stu-id="a2cf8-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="a2cf8-173">Mitglied im Kanal aktualisieren</span><span class="sxs-lookup"><span data-stu-id="a2cf8-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="a2cf8-174">Mitglied aus dem Kanal entfernen</span><span class="sxs-lookup"><span data-stu-id="a2cf8-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
