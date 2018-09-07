---
title: Zuweisen von Rollen und Berechtigungen in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98ec3b95395a3d972af245f6653ea0294cfa670d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856315"
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="3b8aa-103">Zuweisen von Rollen und Berechtigungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b8aa-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="3b8aa-p101">Es gibt in Microsoft Teams zwei Rollen: **Besitzer** und **Mitglied**. Standardmäßig wird einem Benutzer, der ein neues Team erstellt. der Status „Besitzer“ gewährt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden die Berechtigungen vererbt.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="3b8aa-107">Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds:</span><span class="sxs-lookup"><span data-stu-id="3b8aa-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="3b8aa-108">Teambesitzer</span><span class="sxs-lookup"><span data-stu-id="3b8aa-108">Team Owner</span></span>  |<span data-ttu-id="3b8aa-109">Teammitglied</span><span class="sxs-lookup"><span data-stu-id="3b8aa-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="3b8aa-110">**Team erstellen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-110">**Create team**</span></span>     |<span data-ttu-id="3b8aa-111">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-111">Yes</span></span>        |<span data-ttu-id="3b8aa-112">Nein</span><span class="sxs-lookup"><span data-stu-id="3b8aa-112">No</span></span>         |
|<span data-ttu-id="3b8aa-113">**Team verlassen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-113">**Leave team**</span></span>     |<span data-ttu-id="3b8aa-114">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-114">Yes</span></span>         |<span data-ttu-id="3b8aa-115">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-115">Yes</span></span>         |
|<span data-ttu-id="3b8aa-116">**Teamnamen/Teambeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-116">**Edit team name/description**</span></span>      |<span data-ttu-id="3b8aa-117">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-117">Yes</span></span>         |<span data-ttu-id="3b8aa-118">Nein</span><span class="sxs-lookup"><span data-stu-id="3b8aa-118">No</span></span>         |
|<span data-ttu-id="3b8aa-119">**Team löschen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-119">**Delete team**</span></span>      |<span data-ttu-id="3b8aa-120">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-120">Yes</span></span>         |<span data-ttu-id="3b8aa-121">Nein</span><span class="sxs-lookup"><span data-stu-id="3b8aa-121">No</span></span>         |
|<span data-ttu-id="3b8aa-122">**Kanal hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-122">**Add channel**</span></span>      |<span data-ttu-id="3b8aa-123">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-123">Yes</span></span>         |<span data-ttu-id="3b8aa-124">Ja\*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-124">Yes\*</span></span>         |
|<span data-ttu-id="3b8aa-125">**Kanalnamen/Kanalbeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="3b8aa-126">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-126">Yes</span></span>         |<span data-ttu-id="3b8aa-127">Ja\*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-127">Yes\*</span></span>         |
|<span data-ttu-id="3b8aa-128">**Kanal löschen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-128">**Delete channel**</span></span>      |<span data-ttu-id="3b8aa-129">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-129">Yes</span></span>         |<span data-ttu-id="3b8aa-130">Ja\*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-130">Yes\*</span></span>         |
|<span data-ttu-id="3b8aa-131">**Mitglieder hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-131">**Add members**</span></span>      |<span data-ttu-id="3b8aa-132">Ja\*\*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-132">Yes\*\*</span></span>         |<span data-ttu-id="3b8aa-133">Nein</span><span class="sxs-lookup"><span data-stu-id="3b8aa-133">No</span></span>         |
|<span data-ttu-id="3b8aa-134">**Registerkarten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-134">**Add tabs**</span></span>      |<span data-ttu-id="3b8aa-135">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-135">Yes</span></span>         |<span data-ttu-id="3b8aa-136">Ja\*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-136">Yes\*</span></span>         |
|<span data-ttu-id="3b8aa-137">**Connectors hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-137">**Add connectors**</span></span>      |<span data-ttu-id="3b8aa-138">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-138">Yes</span></span>         |<span data-ttu-id="3b8aa-139">Ja\*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-139">Yes\*</span></span>         |
|<span data-ttu-id="3b8aa-140">**Bots hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="3b8aa-140">**Add bots**</span></span>      |<span data-ttu-id="3b8aa-141">Ja</span><span class="sxs-lookup"><span data-stu-id="3b8aa-141">Yes</span></span>         |<span data-ttu-id="3b8aa-142">Ja\*</span><span class="sxs-lookup"><span data-stu-id="3b8aa-142">Yes\*</span></span>         |
<span data-ttu-id="3b8aa-143">\* Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall verfügen Mitglieder nicht über den entsprechenden Zugriff.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="3b8aa-p102">\*\*Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied zum Status eines Besitzers hochstufen. Ein Besitzer kann auch seinen eigenen Status zu dem eines Mitglieds herabstufen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="3b8aa-146">Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="3b8aa-147">Ein Team kann maximal 100 Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="3b8aa-148">Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="3b8aa-149">Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="3b8aa-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="3b8aa-150">Berechtigungen zum Erstellen von Teams</span><span class="sxs-lookup"><span data-stu-id="3b8aa-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="3b8aa-151">Standardmäßig haben alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Office 365-Gruppen und daher ein Team in Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="3b8aa-152">Sie können haben eine genauere Kontrolle und die Erstellung des neuen Teams und somit die Erstellung des neuen Office 365-Gruppen nach Gruppe erstellen und Verwaltungsrechte an eine Gruppe von Benutzern delegieren einschränken.</span><span class="sxs-lookup"><span data-stu-id="3b8aa-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="3b8aa-153">Anweisungen finden Sie unter [verwalten, die Office 365 Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="3b8aa-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="3b8aa-155">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="3b8aa-155">Decision Point</span></span>         |<span data-ttu-id="3b8aa-156">Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="3b8aa-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="3b8aa-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3b8aa-158">Next Steps</span></span>         |<span data-ttu-id="3b8aa-159">Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann</span><span class="sxs-lookup"><span data-stu-id="3b8aa-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
