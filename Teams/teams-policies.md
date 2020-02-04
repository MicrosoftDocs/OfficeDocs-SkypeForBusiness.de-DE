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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen zur Verwendung und Verwaltung von Teamrichtlinien in Ihrer Organisation, damit Sie steuern können, wozu Benutzer in Teams und Kanälen berechtigt sind.
f1.keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 81192f405563c3f7eb023050745d68fcd4c067f9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708321"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="b7f80-103">Verwalten von Teamrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7f80-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="b7f80-104">Als Administrator können Sie mithilfe von Teamrichtlinien in Microsoft Teams steuern, wozu Benutzer in Ihrer Organisation in Teams und Kanälen berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="b7f80-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="b7f80-105">Sie können z. B. festlegen, ob private Teams für Benutzer in den Suchergebnissen und im Teamkatalog sichtbar sind und ob Benutzer private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="b7f80-106">Zum Verwalten von Teamrichtlinien wechseln Sie im Microsoft Teams Admin Center zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b7f80-107">Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="b7f80-108">Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="b7f80-109">Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="b7f80-110">Sofern einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen wurde, gilt diese Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b7f80-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="b7f80-111">Wurde einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen, gilt für diesen Benutzer die globale Standardrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="b7f80-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="b7f80-112">Nachdem Sie die globale Standardrichtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="b7f80-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="b7f80-113">Erstellen einer benutzerdefinierten Teamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="b7f80-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="b7f80-114">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b7f80-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-115">Click **Add**.</span></span>
3. <span data-ttu-id="b7f80-116">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="b7f80-116">Enter a name and description for the policy.</span></span>

    ![Screenshot der Richtlinieneinstellungen für Teams](media/teams-policies.png)
4. <span data-ttu-id="b7f80-118">Wählen Sie die gewünschten Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="b7f80-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="b7f80-119">**Entdecken Sie private Teams**:<a name="discoverteams"> </a> aktivieren Sie diese Einstellung, damit Benutzer private Teams in Suchergebnissen und im Team Katalog entdecken können.</span><span class="sxs-lookup"><span data-stu-id="b7f80-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="b7f80-120">**Private Kanäle erstellen**: <a name="createchannels"> </a>aktivieren Sie diese Einstellung, damit Benutzer private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="b7f80-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="b7f80-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="b7f80-122">Bearbeiten einer Teamrichtlinie</span><span class="sxs-lookup"><span data-stu-id="b7f80-122">Edit a teams policy</span></span>

<span data-ttu-id="b7f80-123">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="b7f80-124">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b7f80-125">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="b7f80-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b7f80-126">Aktivieren oder deaktivieren Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="b7f80-127">Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer</span><span class="sxs-lookup"><span data-stu-id="b7f80-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="b7f80-128">Um einem oder mehreren Benutzern eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Microsoft Teams Admin Center verwenden. Um Benutzergruppen, z. B. einer Sicherheitsgruppe oder einer Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Skype for Business PowerShell-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7f80-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="b7f80-129">Zuweisen einer benutzerdefinierten Teamrichtlinie an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="b7f80-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="b7f80-130">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Benutzer**, und klicken Sie dann den gewünschten Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="b7f80-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="b7f80-131">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b7f80-132">Wählen Sie unter **Teamrichtlinien** diejenige Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="b7f80-133">Informationen dazu, wie Sie eine benutzerdefinierte Teamrichtlinie mehreren Benutzern gleichzeitig zuweisen können, finden Sie unter [Batchbearbeitung von Benutzereinstellungen eines Teams](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="b7f80-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="b7f80-134">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b7f80-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b7f80-135">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b7f80-136">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="b7f80-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b7f80-137">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="b7f80-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="b7f80-138">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b7f80-139">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7f80-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b7f80-140">Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b7f80-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="b7f80-141">Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer in einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="b7f80-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="b7f80-142">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Teamrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="b7f80-143">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="b7f80-144">Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="b7f80-145">Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b7f80-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="b7f80-146">In diesem Beispiel wird eine als „Marketing-Teamrichtlinie“ bezeichnete Teamrichtlinie allen Benutzern in der Contoso-Marketinggruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="b7f80-147">Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="b7f80-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="b7f80-148">Abrufen der GroupObject-ID der jeweiligen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="b7f80-148">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="b7f80-149">Abrufen der Mitglieder der gewählten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="b7f80-149">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="b7f80-150">Zuweisen aller Benutzer in der Gruppe zu einer bestimmten Teamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="b7f80-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="b7f80-151">Bei diesem Beispiel handelt es sich um die „Marketing-Teamrichtlinie“.</span><span class="sxs-lookup"><span data-stu-id="b7f80-151">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="b7f80-152">Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="b7f80-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7f80-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b7f80-153">Related topics</span></span>

- [<span data-ttu-id="b7f80-154">Verwalten der Sichtbarkeit privater Teams unter Teams</span><span class="sxs-lookup"><span data-stu-id="b7f80-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="b7f80-155">Private Kanäle in Teams</span><span class="sxs-lookup"><span data-stu-id="b7f80-155">Private channels in Teams</span></span>](private-channels.md)
