---
title: Verwalten von Teamrichtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
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
description: Hier erfahren Sie, wie Sie Teamrichtlinien in Ihrer Organisation verwenden und verwalten, um zu steuern, welche Aktionen Benutzer in Teams und Kanälen durchführen können.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 40647aec4f55d3d922f29c853ec84ee175dc8166
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483202"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="eed71-103">Verwalten von Teamrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eed71-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="eed71-104">Als Administrator können Sie die Teamrichtlinien in Microsoft Teams verwenden, um zu steuern, welche Benutzer in Ihrer Organisation in Teams und Kanälen tun können.</span><span class="sxs-lookup"><span data-stu-id="eed71-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="eed71-105">So können Sie beispielsweise festlegen, ob Benutzer private Teams in Suchergebnissen und in der Team Galerie entdecken dürfen und ob Benutzer private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="eed71-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="eed71-106">Sie verwalten die Teamrichtlinien im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="eed71-106">You manage teams policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="eed71-107">Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und diesen Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eed71-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="eed71-108">Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, wenn Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eed71-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="eed71-109">Sie können die globale Richtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eed71-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="eed71-110">Wenn einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eed71-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="eed71-111">Wenn einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen ist, gilt die globale Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eed71-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="eed71-112">Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="eed71-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="eed71-113">Erstellen einer benutzerdefinierten Teams-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="eed71-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="eed71-114">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams** > Teams-**Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="eed71-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="eed71-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eed71-115">Click **Add**.</span></span>
3. <span data-ttu-id="eed71-116">Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="eed71-116">Enter a name and description for the policy.</span></span>

    ![Screenshot der Richtlinieneinstellungen für Teams](media/teams-policies.png)
4. <span data-ttu-id="eed71-118">Wählen Sie die gewünschten Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="eed71-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="eed71-119">[**Entdecken Sie private Teams**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): Aktivieren Sie diese Einstellung, damit Benutzer private Teams in Suchergebnissen und im Team Katalog entdecken können.</span><span class="sxs-lookup"><span data-stu-id="eed71-119">[**Discover private teams**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="eed71-120">[**Private Kanäle erstellen**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): Aktivieren Sie diese Einstellung, damit Benutzer private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="eed71-120">[**Create private channels**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="eed71-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eed71-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="eed71-122">Bearbeiten einer Teams-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="eed71-122">Edit a teams policy</span></span>

<span data-ttu-id="eed71-123">Sie können die globale Richtlinie oder alle von Ihnen erstellten benutzerdefinierten Richtlinien bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eed71-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="eed71-124">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams** > Teams-**Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="eed71-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="eed71-125">Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken und dann auf **Bearbeiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="eed71-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="eed71-126">Aktivieren oder deaktivieren Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eed71-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="eed71-127">Zuweisen einer benutzerdefinierten Teams-Richtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="eed71-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="eed71-128">Mit dem Microsoft Teams Admin Center können Sie einem oder mehreren Benutzern oder dem Skype for Business PowerShell-Modul eine benutzerdefinierte Richtlinie zuweisen, um Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eed71-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="eed71-129">Zuweisen einer benutzerdefinierten Teams-Richtlinie zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="eed71-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="eed71-130">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eed71-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="eed71-131">Klicken Sie auf **Richtlinien**und dann neben **zugewiesene Richtlinien**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eed71-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="eed71-132">Wählen Sie unter **Teamrichtlinien**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eed71-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="eed71-133">Informationen zum Zuweisen einer benutzerdefinierten Teams-Richtlinie zu mehreren Benutzern gleichzeitig finden Sie unter [Bearbeiten von Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="eed71-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="eed71-134">Oder Sie können auch die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="eed71-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="eed71-135">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams** > Teams-**Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="eed71-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="eed71-136">Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.</span><span class="sxs-lookup"><span data-stu-id="eed71-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="eed71-137">Wählen Sie **Benutzer verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="eed71-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="eed71-138">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="eed71-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="eed71-139">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="eed71-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="eed71-140">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eed71-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="eed71-141">Zuweisen einer benutzerdefinierten Teams-Richtlinie zu Benutzern in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="eed71-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="eed71-142">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Teams-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eed71-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="eed71-143">So können Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eed71-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="eed71-144">Sie können dies tun, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="eed71-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="eed71-145">Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eed71-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="eed71-146">In diesem Beispiel weisen wir allen Benutzern in der Contoso-Marketinggruppe eine Teams-Richtlinie namens "Marketingteams-Richtlinie" zu.</span><span class="sxs-lookup"><span data-stu-id="eed71-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="eed71-147">Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="eed71-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="eed71-148">Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="eed71-148">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="eed71-149">Rufen Sie die Mitglieder der angegebenen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="eed71-149">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="eed71-150">Weisen Sie alle Benutzer in der Gruppe einer bestimmten Teams-Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="eed71-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="eed71-151">In diesem Beispiel handelt es sich um die Richtlinie für Marketing Teams.</span><span class="sxs-lookup"><span data-stu-id="eed71-151">In this example, it's Marketing Teams Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="eed71-152">Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="eed71-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eed71-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="eed71-153">Related topics</span></span>

- [<span data-ttu-id="eed71-154">Verwalten der Erkennung privater Teams in Teams</span><span class="sxs-lookup"><span data-stu-id="eed71-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
