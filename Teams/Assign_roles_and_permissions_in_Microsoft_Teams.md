---
title: Zuweisen von Rollen und Berechtigungen in Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: solution
ms.prod: teams
description: "Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen."
ms.openlocfilehash: 9367148bb98e5b36f43c512e4955827a63fc8863
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="5feb5-103">Zuweisen von Rollen und Berechtigungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5feb5-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="5feb5-p101">Es gibt in Microsoft Teams zwei Rollen: **Besitzer** und **Mitglied**. Standardmäßig wird einem Benutzer, der ein neues Team erstellt. der Status „Besitzer“ gewährt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden die Berechtigungen vererbt.</span><span class="sxs-lookup"><span data-stu-id="5feb5-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="5feb5-107">Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds:</span><span class="sxs-lookup"><span data-stu-id="5feb5-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="5feb5-108">Teambesitzer</span><span class="sxs-lookup"><span data-stu-id="5feb5-108">Team Owner</span></span>  |<span data-ttu-id="5feb5-109">Teammitglied</span><span class="sxs-lookup"><span data-stu-id="5feb5-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5feb5-110">**Team erstellen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-110">**Create team**</span></span>     |<span data-ttu-id="5feb5-111">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-111">Yes</span></span>        |<span data-ttu-id="5feb5-112">Nein</span><span class="sxs-lookup"><span data-stu-id="5feb5-112">No</span></span>         |
|<span data-ttu-id="5feb5-113">**Team verlassen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-113">**Leave team**</span></span>     |<span data-ttu-id="5feb5-114">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-114">Yes</span></span>         |<span data-ttu-id="5feb5-115">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-115">Yes</span></span>         |
|<span data-ttu-id="5feb5-116">**Teamnamen/Teambeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="5feb5-116">**Edit team name/description**</span></span>      |<span data-ttu-id="5feb5-117">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-117">Yes</span></span>         |<span data-ttu-id="5feb5-118">Nein</span><span class="sxs-lookup"><span data-stu-id="5feb5-118">No</span></span>         |
|<span data-ttu-id="5feb5-119">**Team löschen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-119">**Delete team**</span></span>      |<span data-ttu-id="5feb5-120">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-120">Yes</span></span>         |<span data-ttu-id="5feb5-121">Nein</span><span class="sxs-lookup"><span data-stu-id="5feb5-121">No</span></span>         |
|<span data-ttu-id="5feb5-122">**Kanal hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-122">**Add channel**</span></span>      |<span data-ttu-id="5feb5-123">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-123">Yes</span></span>         |<span data-ttu-id="5feb5-124">Ja*</span><span class="sxs-lookup"><span data-stu-id="5feb5-124">Yes*</span></span>         |
|<span data-ttu-id="5feb5-125">**Kanalnamen/Kanalbeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="5feb5-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="5feb5-126">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-126">Yes</span></span>         |<span data-ttu-id="5feb5-127">Ja*</span><span class="sxs-lookup"><span data-stu-id="5feb5-127">Yes*</span></span>         |
|<span data-ttu-id="5feb5-128">**Kanal löschen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-128">**Delete channel**</span></span>      |<span data-ttu-id="5feb5-129">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-129">Yes</span></span>         |<span data-ttu-id="5feb5-130">Ja*</span><span class="sxs-lookup"><span data-stu-id="5feb5-130">Yes*</span></span>         |
|<span data-ttu-id="5feb5-131">**Mitglieder hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-131">**Add members**</span></span>      |<span data-ttu-id="5feb5-132">Ja**</span><span class="sxs-lookup"><span data-stu-id="5feb5-132">Yes</span></span>         |<span data-ttu-id="5feb5-133">Nein</span><span class="sxs-lookup"><span data-stu-id="5feb5-133">No</span></span>         |
|<span data-ttu-id="5feb5-134">**Registerkarten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-134">**Add tabs**</span></span>      |<span data-ttu-id="5feb5-135">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-135">Yes</span></span>         |<span data-ttu-id="5feb5-136">Ja*</span><span class="sxs-lookup"><span data-stu-id="5feb5-136">Yes*</span></span>         |
|<span data-ttu-id="5feb5-137">**Connectors hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-137">**Add connectors**</span></span>      |<span data-ttu-id="5feb5-138">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-138">Yes</span></span>         |<span data-ttu-id="5feb5-139">Ja*</span><span class="sxs-lookup"><span data-stu-id="5feb5-139">Yes*</span></span>         |
|<span data-ttu-id="5feb5-140">**Bots hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="5feb5-140">**Add bots**</span></span>      |<span data-ttu-id="5feb5-141">Ja</span><span class="sxs-lookup"><span data-stu-id="5feb5-141">Yes</span></span>         |<span data-ttu-id="5feb5-142">Ja*</span><span class="sxs-lookup"><span data-stu-id="5feb5-142">Yes*</span></span>         |
<span data-ttu-id="5feb5-143">\* Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall verfügen Mitglieder nicht über den entsprechenden Zugriff.</span><span class="sxs-lookup"><span data-stu-id="5feb5-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="5feb5-p102">\*\*Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied zum Status eines Besitzers hochstufen. Ein Besitzer kann auch seinen eigenen Status zu dem eines Mitglieds herabstufen.</span><span class="sxs-lookup"><span data-stu-id="5feb5-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>


| | |
|---------|---------|
|![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br><span data-ttu-id="5feb5-146">Hinweis</span><span class="sxs-lookup"><span data-stu-id="5feb5-146">Note:</span></span>     |<span data-ttu-id="5feb5-p103">Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen. Ein Team kann maximal zehn Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="5feb5-p103">Owners can make other members owners in the View teams option. A team can have up to 10 owners.</span></span>         |

<a name="permissions-to-create-teams"></a><span data-ttu-id="5feb5-149">Berechtigungen zum Erstellen von Teams</span><span class="sxs-lookup"><span data-stu-id="5feb5-149">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="5feb5-p104">Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigung zum Erstellen von Office 365-Gruppen und damit zum Erstellen eines Teams in Microsoft Teams. Sie können dies genauer steuern und die Erstellung neuer Teams und damit die Erstellung neuer Office 365-Gruppen einschränken, indem Sie die Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Benutzern delegieren.</span><span class="sxs-lookup"><span data-stu-id="5feb5-p104">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="5feb5-152">Wenn Ihre Organisation daran interessiert ist, werden in der folgenden Anleitung die dazu erforderlichen Aufgaben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5feb5-152">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="5feb5-153">Identifizieren oder erstellen Sie eine Sicherheitsgruppe (SG) von Benutzern, die über delegierte Berechtigungen zum Erstellen von Office 365-Gruppen verfügen sollen.</span><span class="sxs-lookup"><span data-stu-id="5feb5-153">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="5feb5-p105">a. **Aktion:** Richten Sie in Office 365 eine Sicherheitsgruppe ein, damit Sie Ihre Benutzer hinzufügen können, die Office 365-Gruppen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="5feb5-p105">a.  **Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="5feb5-p106">b. Weitere Informationen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Office 365 Admin Center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="5feb5-p106">b.  For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="5feb5-158">Überprüfen Sie, ob die firmenweite Steuerung für Benutzer zum Erstellen von Gruppen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5feb5-158">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="5feb5-p107">a. **Aktion:** Führen Sie das folgende PowerShell-Skript aus, und überprüfen Sie, ob der Parameter „UsersPermissiontoCreateGroupsEnabled“ auf **True** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5feb5-p107">a.  **Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="5feb5-161">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="5feb5-161">Connect-MsolService</span></span>

    <span data-ttu-id="5feb5-162">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="5feb5-162">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="5feb5-p108">b. Wenn hier nicht „True“ festgelegt ist, führen Sie das Cmdlet „Set-MsolCompanySettings“ aus, um **„True“ festzulegen**. Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="5feb5-p108">b.  If this is not true, run the Set-MsolCompanySettings  cmdet **to set it to True**. Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>


    <span data-ttu-id="5feb5-p109">c. Weitere Informationen finden Sie unter: [Verwalten der Erstellung von Office 365-Gruppen](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span><span class="sxs-lookup"><span data-stu-id="5feb5-p109">c. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

<!-- -->

3.  <span data-ttu-id="5feb5-168">Konfigurieren von Einstellungen für Office 365-Gruppen, um nur identifizierten Sicherheitsgruppen die Berechtigung zum Erstellen von Gruppen zu erteilen</span><span class="sxs-lookup"><span data-stu-id="5feb5-168">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="5feb5-p110">a. **Aktion:** Erstellen Sie ein Gruppeneinstellungsobjekt, das die Konfigurationseinstellungen der Gruppe enthält, der delegierte Berechtigungen zum Erstellen von Gruppen zugewiesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5feb5-p110">a.  **Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="5feb5-171">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="5feb5-171">Connect-AzureAD</span></span>

    <span data-ttu-id="5feb5-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="5feb5-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="5feb5-173">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="5feb5-173">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="5feb5-174">$setting["EnableGroupCreation"] = "false"</span><span class="sxs-lookup"><span data-stu-id="5feb5-174">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="5feb5-175">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId der Gruppe, die Gruppen erstellen darf>"</span><span class="sxs-lookup"><span data-stu-id="5feb5-175">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="5feb5-176">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="5feb5-176">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="5feb5-p111">b. Weitere Informationen finden Sie unter: [Verwalten der Erstellung von Office 365-Gruppen](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="5feb5-p111">b. For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="5feb5-179">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="5feb5-179">Policy Decision Point</span></span>         |<span data-ttu-id="5feb5-180">Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="5feb5-180">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="5feb5-181">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5feb5-181">Next Steps</span></span>         |<span data-ttu-id="5feb5-182">Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann</span><span class="sxs-lookup"><span data-stu-id="5feb5-182">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |

