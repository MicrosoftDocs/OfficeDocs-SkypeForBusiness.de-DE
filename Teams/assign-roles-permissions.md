---
title: Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teambesitzer- und Mitgliederrollen sowie Berechtigungen (einschließlich Berechtigungen zum Erstellen von Teams) in Microsoft Teams zuweisen.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "30569958"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="d6e98-103">Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6e98-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="d6e98-p101">Es gibt in Microsoft Teams zwei Benutzerrollen: **Besitzer** und **Mitglied**. Standardmäßig wird einem Benutzer, der ein neues Team erstellt. der Status „Besitzer“ gewährt. Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden die Berechtigungen vererbt.</span><span class="sxs-lookup"><span data-stu-id="d6e98-p101">Within Microsoft Teams there are two roles: **Owner** and **Member**. By default, a user that creates a new team is granted the Owner status. If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="d6e98-107">Die folgende Tabelle zeigt den Unterschied zwischen Berechtigungen eines Besitzers und eines Mitglieds.</span><span class="sxs-lookup"><span data-stu-id="d6e98-107">The table below shows the difference in permissions between an owner and a member:</span></span>


|                                   | <span data-ttu-id="d6e98-108">Teambesitzer</span><span class="sxs-lookup"><span data-stu-id="d6e98-108">Team Owner</span></span> | <span data-ttu-id="d6e98-109">Teammitglied</span><span class="sxs-lookup"><span data-stu-id="d6e98-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="d6e98-110">**Team erstellen**</span><span class="sxs-lookup"><span data-stu-id="d6e98-110">**Create team**</span></span>          |    <span data-ttu-id="d6e98-111">Ja<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="d6e98-112">Nein</span><span class="sxs-lookup"><span data-stu-id="d6e98-112">No</span></span>      |
|          <span data-ttu-id="d6e98-113">**Team verlassen**</span><span class="sxs-lookup"><span data-stu-id="d6e98-113">**Leave team**</span></span>           |    <span data-ttu-id="d6e98-114">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-114">Yes</span></span>     |     <span data-ttu-id="d6e98-115">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-115">Yes</span></span>     |
|  <span data-ttu-id="d6e98-116">**Teamnamen/Teambeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="d6e98-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="d6e98-117">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-117">Yes</span></span>     |     <span data-ttu-id="d6e98-118">Nein</span><span class="sxs-lookup"><span data-stu-id="d6e98-118">No</span></span>      |
|          <span data-ttu-id="d6e98-119">**Team löschen**</span><span class="sxs-lookup"><span data-stu-id="d6e98-119">**Delete team**</span></span>          |    <span data-ttu-id="d6e98-120">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-120">Yes</span></span>     |     <span data-ttu-id="d6e98-121">Nein</span><span class="sxs-lookup"><span data-stu-id="d6e98-121">No</span></span>      |
|          <span data-ttu-id="d6e98-122">**Kanal hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="d6e98-122">**Add channel**</span></span>          |    <span data-ttu-id="d6e98-123">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-123">Yes</span></span>     |    <span data-ttu-id="d6e98-124">Ja<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="d6e98-125">**Kanalnamen/Kanalbeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="d6e98-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="d6e98-126">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-126">Yes</span></span>     |    <span data-ttu-id="d6e98-127">Ja<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="d6e98-128">**Delete channel**</span><span class="sxs-lookup"><span data-stu-id="d6e98-128">**Delete channel**</span></span>         |    <span data-ttu-id="d6e98-129">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-129">Yes</span></span>     |    <span data-ttu-id="d6e98-130">Ja<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="d6e98-131">**Hinzufügen von Mitgliedern**</span><span class="sxs-lookup"><span data-stu-id="d6e98-131">**Add members**</span></span>          |  <span data-ttu-id="d6e98-132">Ja<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="d6e98-133">Nein<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="d6e98-134">**Hinzufügen von Mitgliedern anfordern**</span><span class="sxs-lookup"><span data-stu-id="d6e98-134">**Request to add members**</span></span>          |  <span data-ttu-id="d6e98-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d6e98-135">N/A</span></span>   |     <span data-ttu-id="d6e98-136">Ja<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="d6e98-137">**Registerkarten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="d6e98-137">**Add tabs**</span></span>            |    <span data-ttu-id="d6e98-138">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-138">Yes</span></span>     |    <span data-ttu-id="d6e98-139">Ja<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="d6e98-140">**Connectors hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="d6e98-140">**Add connectors**</span></span>         |    <span data-ttu-id="d6e98-141">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-141">Yes</span></span>     |    <span data-ttu-id="d6e98-142">Ja<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="d6e98-143">**Bots hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="d6e98-143">**Add bots**</span></span>            |    <span data-ttu-id="d6e98-144">Ja</span><span class="sxs-lookup"><span data-stu-id="d6e98-144">Yes</span></span>     |    <span data-ttu-id="d6e98-145">Ja<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d6e98-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="d6e98-146"><sup>1</sup> Teambesitzer können Teams erstellen, es sei denn, sie wurden davon ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d6e98-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="d6e98-147">Siehe „Berechtigungen zum Erstellen von Teams“ weiter unten.</span><span class="sxs-lookup"><span data-stu-id="d6e98-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="d6e98-148"><sup>2</sup> Diese Elemente können von einem Besitzer auf Teamebene deaktiviert werden. In diesem Fall können Mitglieder nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d6e98-148"><sup></sup> These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="d6e98-149"><sup>3</sup> Nach dem Hinzufügen eines Mitglieds zu einem Team kann ein Besitzer auch ein Mitglied in den Besitzerstatus höherstufen.</span><span class="sxs-lookup"><span data-stu-id="d6e98-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="d6e98-150">Es ist auch möglich, dass ein Besitzer seinen eigenen Status zu einem Mitglied tiefer stuft.</span><span class="sxs-lookup"><span data-stu-id="d6e98-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="d6e98-151"><sup>4</sup> Teammitglieder können andere Mitglieder zu einem öffentlichen Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6e98-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="d6e98-152"><sup>5</sup> Während ein Teammitglied Mitglieder nicht direkt zu einem privaten Team hinzufügen kann, kann es das Hinzufügen einer anderen Person zu einem Team anfordern, in dem es bereits Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="d6e98-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="d6e98-153">Wenn ein Mitglied das Hinzufügen einer anderen Person zu einem Team anfordert, erhalten Teambesitzer eine Benachrichtigung über eine ausstehende Anforderung, die sie annehmen oder ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="d6e98-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="d6e98-154">Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen.</span><span class="sxs-lookup"><span data-stu-id="d6e98-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="d6e98-155">Ein Team kann maximal 100 Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="d6e98-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="d6e98-156">Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="d6e98-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="d6e98-157">Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="d6e98-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="d6e98-158">Berechtigungen zum Erstellen von Teams</span><span class="sxs-lookup"><span data-stu-id="d6e98-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="d6e98-159">Standardmäßig verfügen alle Benutzer mit einem Postfach in Exchange Online über die Berechtigung zum Erstellen von Office 365-Gruppen und damit zum Erstellen eines Teams in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6e98-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="d6e98-160">Sie können dies genauer steuern und die Erstellung neuer Teams und damit die Erstellung neuer Office 365-Gruppen einschränken, indem Sie die Gruppenerstellungs- und Verwaltungsrechte an eine Gruppe von Benutzern delegieren.</span><span class="sxs-lookup"><span data-stu-id="d6e98-160">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams. You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="d6e98-161">Anweisungen finden Sie unter [Verwalten von Personen, die Office 365-Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="d6e98-161">For more information, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="d6e98-163">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="d6e98-163">Decision Point</span></span>         |<span data-ttu-id="d6e98-164">Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="d6e98-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="d6e98-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d6e98-166">Next Steps</span></span>         |<span data-ttu-id="d6e98-167">Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann</span><span class="sxs-lookup"><span data-stu-id="d6e98-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
