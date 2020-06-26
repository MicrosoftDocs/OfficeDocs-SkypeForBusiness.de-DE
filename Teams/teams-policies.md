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
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: b28b61a6b2d4c441fc69d0e50124df50f95b4a49
ms.sourcegitcommit: 2e8a61abdd586bf8f0f88cac3b7d4ca4b9d9be34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44889974"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="198e0-103">Verwalten von Teamrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="198e0-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="198e0-104">Als Administrator können Sie mithilfe von Teamrichtlinien in Microsoft Teams steuern, wozu Benutzer in Ihrer Organisation in Teams und Kanälen berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="198e0-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="198e0-105">Sie können z. B. festlegen, ob private Teams für Benutzer in den Suchergebnissen und im Teamkatalog sichtbar sind und ob Benutzer private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="198e0-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="198e0-106">Zum Verwalten von Teamrichtlinien wechseln Sie im Microsoft Teams Admin Center zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="198e0-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="198e0-107">Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="198e0-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="198e0-108">Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="198e0-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="198e0-109">Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="198e0-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="198e0-110">Sofern einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen wurde, gilt diese Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="198e0-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="198e0-111">Wurde einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen, gilt für diesen Benutzer die globale Standardrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="198e0-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="198e0-112">Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="198e0-112">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="198e0-113">Erstellen einer benutzerdefinierten Teamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="198e0-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="198e0-114">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="198e0-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="198e0-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="198e0-115">Click **Add**.</span></span>
3. <span data-ttu-id="198e0-116">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="198e0-116">Enter a name and description for the policy.</span></span>

    ![Screenshot der Richtlinieneinstellungen für Teams](media/teams-policies.png)
4. <span data-ttu-id="198e0-118">Wählen Sie die gewünschten Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="198e0-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="198e0-119">**Entdecken privater Teams** (in der privaten Vorschau)<a name="discoverteams"> </a> : Aktivieren Sie diese Einstellung, damit Benutzer private Teams in Suchergebnissen und im Team Katalog entdecken können.</span><span class="sxs-lookup"><span data-stu-id="198e0-119">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="198e0-120">**Private Kanäle erstellen**: <a name="createchannels"> </a>aktivieren Sie diese Einstellung, damit Benutzer private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="198e0-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="198e0-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="198e0-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="198e0-122">Bearbeiten einer Teamrichtlinie</span><span class="sxs-lookup"><span data-stu-id="198e0-122">Edit a teams policy</span></span>

<span data-ttu-id="198e0-123">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="198e0-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="198e0-124">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="198e0-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="198e0-125">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="198e0-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="198e0-126">Aktivieren oder deaktivieren Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="198e0-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="198e0-127">Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer</span><span class="sxs-lookup"><span data-stu-id="198e0-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="198e0-128">Um einem oder mehreren Benutzern eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Microsoft Teams Admin Center verwenden. Um Benutzergruppen, z. B. einer Sicherheitsgruppe oder einer Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Skype for Business PowerShell-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="198e0-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="198e0-129">Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer</span><span class="sxs-lookup"><span data-stu-id="198e0-129">Assign a custom teams policy to users</span></span>

<span data-ttu-id="198e0-130">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="198e0-130">To assign a policy to one user:</span></span>

1. <span data-ttu-id="198e0-131">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="198e0-131">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="198e0-132">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="198e0-132">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="198e0-133">Wählen Sie unter **Teamrichtlinien** diejenige Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="198e0-133">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="198e0-134">So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="198e0-134">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="198e0-135">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="198e0-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="198e0-136">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="198e0-136">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="198e0-137">Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="198e0-137">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="198e0-138">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="198e0-138">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="198e0-139">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="198e0-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="198e0-140">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="198e0-140">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="198e0-141">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="198e0-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="198e0-142">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="198e0-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="198e0-143">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="198e0-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="198e0-144">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="198e0-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="198e0-145">Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="198e0-145">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="198e0-146">Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer in einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="198e0-146">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="198e0-147">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Teams-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="198e0-147">You may want to assign a custom teams policy to multiple users that you've already identified.</span></span> <span data-ttu-id="198e0-148">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="198e0-148">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="198e0-149">Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="198e0-149">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="198e0-150">Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="198e0-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="198e0-151">In diesem Beispiel wird eine als „Marketing-Teamrichtlinie“ bezeichnete Teamrichtlinie allen Benutzern in der Contoso-Marketinggruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="198e0-151">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="198e0-152">Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="198e0-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="198e0-153">Abrufen der GroupObject-ID der jeweiligen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="198e0-153">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="198e0-154">Abrufen der Mitglieder der gewählten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="198e0-154">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="198e0-155">Zuweisen aller Benutzer in der Gruppe zu einer bestimmten Teamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="198e0-155">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="198e0-156">Bei diesem Beispiel handelt es sich um die „Marketing-Teamrichtlinie“.</span><span class="sxs-lookup"><span data-stu-id="198e0-156">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="198e0-157">Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="198e0-157">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="198e0-158">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="198e0-158">Related topics</span></span>

- [<span data-ttu-id="198e0-159">Verwalten der Sichtbarkeit privater Teams unter Teams</span><span class="sxs-lookup"><span data-stu-id="198e0-159">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="198e0-160">Private Kanäle in Teams</span><span class="sxs-lookup"><span data-stu-id="198e0-160">Private channels in Teams</span></span>](private-channels.md)
- [<span data-ttu-id="198e0-161">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="198e0-161">Assign policies to your users in Teams</span></span>](assign-policies.md)
