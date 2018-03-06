---
title: Zuweisen von Rollen und Berechtigungen in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: "Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0919d588cedf654a515f47f16fafb70cdc923f16
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="f0ded-103">Zuweisen von Rollen und Berechtigungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0ded-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="f0ded-p101">Es gibt in Microsoft Teams zwei Rollen: **Besitzer** und **Mitglied**. Standardmäßig wird einem Benutzer, der ein neues Team erstellt. der Status „Besitzer“ gewährt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden die Berechtigungen vererbt.</span><span class="sxs-lookup"><span data-stu-id="f0ded-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="f0ded-107">Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds:</span><span class="sxs-lookup"><span data-stu-id="f0ded-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="f0ded-108">Teambesitzer</span><span class="sxs-lookup"><span data-stu-id="f0ded-108">Team Owner</span></span>  |<span data-ttu-id="f0ded-109">Teammitglied</span><span class="sxs-lookup"><span data-stu-id="f0ded-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f0ded-110">**Team erstellen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-110">**Create team**</span></span>     |<span data-ttu-id="f0ded-111">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-111">Yes</span></span>        |<span data-ttu-id="f0ded-112">Nein</span><span class="sxs-lookup"><span data-stu-id="f0ded-112">No</span></span>         |
|<span data-ttu-id="f0ded-113">**Team verlassen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-113">**Leave team**</span></span>     |<span data-ttu-id="f0ded-114">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-114">Yes</span></span>         |<span data-ttu-id="f0ded-115">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-115">Yes</span></span>         |
|<span data-ttu-id="f0ded-116">**Teamnamen/Teambeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="f0ded-116">**Edit team name/description**</span></span>      |<span data-ttu-id="f0ded-117">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-117">Yes</span></span>         |<span data-ttu-id="f0ded-118">Nein</span><span class="sxs-lookup"><span data-stu-id="f0ded-118">No</span></span>         |
|<span data-ttu-id="f0ded-119">**Team löschen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-119">**Delete team**</span></span>      |<span data-ttu-id="f0ded-120">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-120">Yes</span></span>         |<span data-ttu-id="f0ded-121">Nein</span><span class="sxs-lookup"><span data-stu-id="f0ded-121">No</span></span>         |
|<span data-ttu-id="f0ded-122">**Kanal hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-122">**Add channel**</span></span>      |<span data-ttu-id="f0ded-123">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-123">Yes</span></span>         |<span data-ttu-id="f0ded-124">Ja\*</span><span class="sxs-lookup"><span data-stu-id="f0ded-124">Yes\*</span></span>         |
|<span data-ttu-id="f0ded-125">**Kanalnamen/Kanalbeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="f0ded-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="f0ded-126">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-126">Yes</span></span>         |<span data-ttu-id="f0ded-127">Ja\*</span><span class="sxs-lookup"><span data-stu-id="f0ded-127">Yes\*</span></span>         |
|<span data-ttu-id="f0ded-128">**Kanal löschen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-128">**Delete channel**</span></span>      |<span data-ttu-id="f0ded-129">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-129">Yes</span></span>         |<span data-ttu-id="f0ded-130">Ja\*</span><span class="sxs-lookup"><span data-stu-id="f0ded-130">Yes\*</span></span>         |
|<span data-ttu-id="f0ded-131">**Mitglieder hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-131">**Add members**</span></span>      |<span data-ttu-id="f0ded-132">Ja**</span><span class="sxs-lookup"><span data-stu-id="f0ded-132">Yes**</span></span>         |<span data-ttu-id="f0ded-133">Nein</span><span class="sxs-lookup"><span data-stu-id="f0ded-133">No</span></span>         |
|<span data-ttu-id="f0ded-134">**Registerkarten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-134">**Add tabs**</span></span>      |<span data-ttu-id="f0ded-135">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-135">Yes</span></span>         |<span data-ttu-id="f0ded-136">Ja\*</span><span class="sxs-lookup"><span data-stu-id="f0ded-136">Yes\*</span></span>         |
|<span data-ttu-id="f0ded-137">**Connectors hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-137">**Add connectors**</span></span>      |<span data-ttu-id="f0ded-138">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-138">Yes</span></span>         |<span data-ttu-id="f0ded-139">Ja\*</span><span class="sxs-lookup"><span data-stu-id="f0ded-139">Yes\*</span></span>         |
|<span data-ttu-id="f0ded-140">**Bots hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="f0ded-140">**Add bots**</span></span>      |<span data-ttu-id="f0ded-141">Ja</span><span class="sxs-lookup"><span data-stu-id="f0ded-141">Yes</span></span>         |<span data-ttu-id="f0ded-142">Ja\*</span><span class="sxs-lookup"><span data-stu-id="f0ded-142">Yes\*</span></span>         |
<span data-ttu-id="f0ded-143">\* Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall verfügen Mitglieder nicht über den entsprechenden Zugriff.</span><span class="sxs-lookup"><span data-stu-id="f0ded-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="f0ded-p102">\*\*Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied zum Status eines Besitzers hochstufen. Ein Besitzer kann auch seinen eigenen Status zu dem eines Mitglieds herabstufen.</span><span class="sxs-lookup"><span data-stu-id="f0ded-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="f0ded-146">Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen.</span><span class="sxs-lookup"><span data-stu-id="f0ded-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="f0ded-147">Ein Team kann maximal 100 Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="f0ded-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="f0ded-148">Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="f0ded-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="f0ded-149">Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="f0ded-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="f0ded-150">Berechtigungen zum Erstellen von Teams</span><span class="sxs-lookup"><span data-stu-id="f0ded-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="f0ded-p104">Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigung zum Erstellen von Office 365-Gruppen und damit zum Erstellen eines Teams in Microsoft Teams. Sie können dies genauer steuern und die Erstellung neuer Teams und damit die Erstellung neuer Office 365-Gruppen einschränken, indem Sie die Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Benutzern delegieren.</span><span class="sxs-lookup"><span data-stu-id="f0ded-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="f0ded-153">Wenn Ihre Organisation daran interessiert ist, werden in der folgenden Anleitung die dazu erforderlichen Aufgaben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0ded-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="f0ded-154">Identifizieren oder erstellen Sie eine Sicherheitsgruppe (SG) von Benutzern, die über delegierte Berechtigungen zum Erstellen von Office 365-Gruppen verfügen sollen.</span><span class="sxs-lookup"><span data-stu-id="f0ded-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="f0ded-p105">a. **Aktion:** Richten Sie in Office 365 eine Sicherheitsgruppe ein, damit Sie Ihre Benutzer hinzufügen können, die Office 365-Gruppen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f0ded-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="f0ded-p106">b. Weitere Informationen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Office 365 Admin Center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="f0ded-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="f0ded-159">Überprüfen Sie, ob die firmenweite Steuerung für Benutzer zum Erstellen von Gruppen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f0ded-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="f0ded-p107">a. **Aktion:** Führen Sie das folgende PowerShell-Skript aus, und überprüfen Sie, ob der Parameter „UsersPermissiontoCreateGroupsEnabled“ auf **True** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f0ded-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    ```
    Connect-MsolService

    Get-MsolCompanyInformation
    ```

    <span data-ttu-id="f0ded-162">b.</span><span class="sxs-lookup"><span data-stu-id="f0ded-162">b.</span></span>  <span data-ttu-id="f0ded-163">Wenn hier nicht „True“ festgelegt ist, führen Sie das Cmdlet „Set-MsolCompanySettings“ aus, um **„True“ festzulegen**.</span><span class="sxs-lookup"><span data-stu-id="f0ded-163">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="f0ded-164">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="f0ded-164">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="f0ded-p109">c. Weitere Informationen finden Sie unter [Verwalten der Erstellung von Office 365-Gruppen](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span><span class="sxs-lookup"><span data-stu-id="f0ded-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="f0ded-167">Konfigurieren von Einstellungen für Office 365-Gruppen, um nur identifizierten Sicherheitsgruppen die Berechtigung zum Erstellen von Gruppen zu erteilen</span><span class="sxs-lookup"><span data-stu-id="f0ded-167">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="f0ded-p110">a. **Aktion:** Erstellen Sie ein Gruppeneinstellungsobjekt, das die Konfigurationseinstellungen der Gruppe enthält, der delegierte Berechtigungen zum Erstellen von Gruppen zugewiesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0ded-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    ```
    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "false"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings
    ```

    <span data-ttu-id="f0ded-170">b.</span><span class="sxs-lookup"><span data-stu-id="f0ded-170">b.</span></span> <span data-ttu-id="f0ded-171">Weitere Informationen finden Sie unter [Verwalten der Erstellung von Office 365-Gruppen](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3).</span><span class="sxs-lookup"><span data-stu-id="f0ded-171">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="f0ded-173">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="f0ded-173">Decision Point</span></span>         |<span data-ttu-id="f0ded-174">Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="f0ded-174">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="f0ded-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f0ded-176">Next Steps</span></span>         |<span data-ttu-id="f0ded-177">Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann</span><span class="sxs-lookup"><span data-stu-id="f0ded-177">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
