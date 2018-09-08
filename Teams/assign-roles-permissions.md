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
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: da4bae93a35775141c246145e1375e73963ec120
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892698"
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="22ada-103">Zuweisen von Rollen und Berechtigungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22ada-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="22ada-p101">Es gibt in Microsoft Teams zwei Rollen: **Besitzer** und **Mitglied**. Standardmäßig wird einem Benutzer, der ein neues Team erstellt. der Status „Besitzer“ gewährt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden die Berechtigungen vererbt.</span><span class="sxs-lookup"><span data-stu-id="22ada-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="22ada-107">Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds:</span><span class="sxs-lookup"><span data-stu-id="22ada-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="22ada-108">Teambesitzer</span><span class="sxs-lookup"><span data-stu-id="22ada-108">Team Owner</span></span>  |<span data-ttu-id="22ada-109">Teammitglied</span><span class="sxs-lookup"><span data-stu-id="22ada-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="22ada-110">**Team erstellen**</span><span class="sxs-lookup"><span data-stu-id="22ada-110">**Create team**</span></span>     |<span data-ttu-id="22ada-111">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-111">Yes</span></span>        |<span data-ttu-id="22ada-112">Nein</span><span class="sxs-lookup"><span data-stu-id="22ada-112">No</span></span>         |
|<span data-ttu-id="22ada-113">**Team verlassen**</span><span class="sxs-lookup"><span data-stu-id="22ada-113">**Leave team**</span></span>     |<span data-ttu-id="22ada-114">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-114">Yes</span></span>         |<span data-ttu-id="22ada-115">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-115">Yes</span></span>         |
|<span data-ttu-id="22ada-116">**Teamnamen/Teambeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="22ada-116">**Edit team name/description**</span></span>      |<span data-ttu-id="22ada-117">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-117">Yes</span></span>         |<span data-ttu-id="22ada-118">Nein</span><span class="sxs-lookup"><span data-stu-id="22ada-118">No</span></span>         |
|<span data-ttu-id="22ada-119">**Team löschen**</span><span class="sxs-lookup"><span data-stu-id="22ada-119">**Delete team**</span></span>      |<span data-ttu-id="22ada-120">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-120">Yes</span></span>         |<span data-ttu-id="22ada-121">Nein</span><span class="sxs-lookup"><span data-stu-id="22ada-121">No</span></span>         |
|<span data-ttu-id="22ada-122">**Kanal hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="22ada-122">**Add channel**</span></span>      |<span data-ttu-id="22ada-123">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-123">Yes</span></span>         |<span data-ttu-id="22ada-124">Ja\*</span><span class="sxs-lookup"><span data-stu-id="22ada-124">Yes\*</span></span>         |
|<span data-ttu-id="22ada-125">**Kanalnamen/Kanalbeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="22ada-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="22ada-126">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-126">Yes</span></span>         |<span data-ttu-id="22ada-127">Ja\*</span><span class="sxs-lookup"><span data-stu-id="22ada-127">Yes\*</span></span>         |
|<span data-ttu-id="22ada-128">**Kanal löschen**</span><span class="sxs-lookup"><span data-stu-id="22ada-128">**Delete channel**</span></span>      |<span data-ttu-id="22ada-129">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-129">Yes</span></span>         |<span data-ttu-id="22ada-130">Ja\*</span><span class="sxs-lookup"><span data-stu-id="22ada-130">Yes\*</span></span>         |
|<span data-ttu-id="22ada-131">**Mitglieder hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="22ada-131">**Add members**</span></span>      |<span data-ttu-id="22ada-132">Ja\*\*</span><span class="sxs-lookup"><span data-stu-id="22ada-132">Yes\*\*</span></span>         |<span data-ttu-id="22ada-133">Nein</span><span class="sxs-lookup"><span data-stu-id="22ada-133">No</span></span>         |
|<span data-ttu-id="22ada-134">**Registerkarten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="22ada-134">**Add tabs**</span></span>      |<span data-ttu-id="22ada-135">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-135">Yes</span></span>         |<span data-ttu-id="22ada-136">Ja\*</span><span class="sxs-lookup"><span data-stu-id="22ada-136">Yes\*</span></span>         |
|<span data-ttu-id="22ada-137">**Connectors hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="22ada-137">**Add connectors**</span></span>      |<span data-ttu-id="22ada-138">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-138">Yes</span></span>         |<span data-ttu-id="22ada-139">Ja\*</span><span class="sxs-lookup"><span data-stu-id="22ada-139">Yes\*</span></span>         |
|<span data-ttu-id="22ada-140">**Bots hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="22ada-140">**Add bots**</span></span>      |<span data-ttu-id="22ada-141">Ja</span><span class="sxs-lookup"><span data-stu-id="22ada-141">Yes</span></span>         |<span data-ttu-id="22ada-142">Ja\*</span><span class="sxs-lookup"><span data-stu-id="22ada-142">Yes\*</span></span>         |
<span data-ttu-id="22ada-143">\* Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall verfügen Mitglieder nicht über den entsprechenden Zugriff.</span><span class="sxs-lookup"><span data-stu-id="22ada-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="22ada-p102">\*\*Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied zum Status eines Besitzers hochstufen. Ein Besitzer kann auch seinen eigenen Status zu dem eines Mitglieds herabstufen.</span><span class="sxs-lookup"><span data-stu-id="22ada-p102">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status. It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="22ada-146">Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen.</span><span class="sxs-lookup"><span data-stu-id="22ada-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="22ada-147">Ein Team kann maximal 100 Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="22ada-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="22ada-148">Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="22ada-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="22ada-149">Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="22ada-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="22ada-150">Berechtigungen zum Erstellen von Teams</span><span class="sxs-lookup"><span data-stu-id="22ada-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="22ada-151">Standardmäßig haben alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Office 365-Gruppen und daher ein Team in Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="22ada-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="22ada-152">Sie können haben eine genauere Kontrolle und die Erstellung des neuen Teams und somit die Erstellung des neuen Office 365-Gruppen nach Gruppe erstellen und Verwaltungsrechte an eine Gruppe von Benutzern delegieren einschränken.</span><span class="sxs-lookup"><span data-stu-id="22ada-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="22ada-153">Anweisungen finden Sie unter [verwalten, die Office 365 Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="22ada-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="22ada-155">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="22ada-155">Decision Point</span></span>         |<span data-ttu-id="22ada-156">Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="22ada-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="22ada-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="22ada-158">Next Steps</span></span>         |<span data-ttu-id="22ada-159">Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann</span><span class="sxs-lookup"><span data-stu-id="22ada-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
