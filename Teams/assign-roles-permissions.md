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
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569958"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="0761e-103">Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0761e-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0761e-104">In Microsoft-Teams, es gibt zwei Benutzerrollen: **Besitzer** und **Member**.</span><span class="sxs-lookup"><span data-stu-id="0761e-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="0761e-105">Standardmäßig wird ein neues Team erstellt ein Benutzer den Status eines Besitzers erteilt.</span><span class="sxs-lookup"><span data-stu-id="0761e-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="0761e-106">Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden Berechtigungen vererbt.</span><span class="sxs-lookup"><span data-stu-id="0761e-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="0761e-107">Die folgende Tabelle zeigt den Unterschied Berechtigungen zwischen einer Besitzer und Mitglied.</span><span class="sxs-lookup"><span data-stu-id="0761e-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="0761e-108">Teambesitzer</span><span class="sxs-lookup"><span data-stu-id="0761e-108">Team Owner</span></span> | <span data-ttu-id="0761e-109">Teammitglied</span><span class="sxs-lookup"><span data-stu-id="0761e-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="0761e-110">**Team erstellen**</span><span class="sxs-lookup"><span data-stu-id="0761e-110">**Create team**</span></span>          |    <span data-ttu-id="0761e-111">Ja,<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="0761e-112">Nein</span><span class="sxs-lookup"><span data-stu-id="0761e-112">No</span></span>      |
|          <span data-ttu-id="0761e-113">**Team verlassen**</span><span class="sxs-lookup"><span data-stu-id="0761e-113">**Leave team**</span></span>           |    <span data-ttu-id="0761e-114">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-114">Yes</span></span>     |     <span data-ttu-id="0761e-115">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-115">Yes</span></span>     |
|  <span data-ttu-id="0761e-116">**Teamnamen/Teambeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="0761e-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="0761e-117">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-117">Yes</span></span>     |     <span data-ttu-id="0761e-118">Nein</span><span class="sxs-lookup"><span data-stu-id="0761e-118">No</span></span>      |
|          <span data-ttu-id="0761e-119">**Team löschen**</span><span class="sxs-lookup"><span data-stu-id="0761e-119">**Delete team**</span></span>          |    <span data-ttu-id="0761e-120">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-120">Yes</span></span>     |     <span data-ttu-id="0761e-121">Nein</span><span class="sxs-lookup"><span data-stu-id="0761e-121">No</span></span>      |
|          <span data-ttu-id="0761e-122">**Kanal hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="0761e-122">**Add channel**</span></span>          |    <span data-ttu-id="0761e-123">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-123">Yes</span></span>     |    <span data-ttu-id="0761e-124">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="0761e-125">**Kanalnamen/Kanalbeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="0761e-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="0761e-126">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-126">Yes</span></span>     |    <span data-ttu-id="0761e-127">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="0761e-128">**Kanal löschen**</span><span class="sxs-lookup"><span data-stu-id="0761e-128">**Delete channel**</span></span>         |    <span data-ttu-id="0761e-129">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-129">Yes</span></span>     |    <span data-ttu-id="0761e-130">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="0761e-131">**Mitglieder hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="0761e-131">**Add members**</span></span>          |  <span data-ttu-id="0761e-132">Ja,<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="0761e-133">Keine<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="0761e-134">**Anforderung zum Hinzufügen von Mitgliedern**</span><span class="sxs-lookup"><span data-stu-id="0761e-134">**Request to add members**</span></span>          |  <span data-ttu-id="0761e-135">n/v</span><span class="sxs-lookup"><span data-stu-id="0761e-135">N/A</span></span>   |     <span data-ttu-id="0761e-136">Ja,<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="0761e-137">**Registerkarten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="0761e-137">**Add tabs**</span></span>            |    <span data-ttu-id="0761e-138">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-138">Yes</span></span>     |    <span data-ttu-id="0761e-139">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="0761e-140">**Connectors hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="0761e-140">**Add connectors**</span></span>         |    <span data-ttu-id="0761e-141">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-141">Yes</span></span>     |    <span data-ttu-id="0761e-142">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="0761e-143">**Bots hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="0761e-143">**Add bots**</span></span>            |    <span data-ttu-id="0761e-144">Ja</span><span class="sxs-lookup"><span data-stu-id="0761e-144">Yes</span></span>     |    <span data-ttu-id="0761e-145">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0761e-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="0761e-146"><sup>1</sup> Team Besitzer können Teams erstellen, es sei denn, sie haben aus auf diese Weise eingeschränkt wurde.</span><span class="sxs-lookup"><span data-stu-id="0761e-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="0761e-147">Siehe "Berechtigungen zum Erstellen von Teams" weiter unten.</span><span class="sxs-lookup"><span data-stu-id="0761e-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="0761e-148"><sup>2</sup> dieser Elemente können mithilfe eines Besitzers auf einer Teamebene deaktiviert werden in diesem Fall würde die Mitglieder nicht darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0761e-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="0761e-149"><sup>3</sup> nach dem Hinzufügen eines Elements zu einem Team, kann ein Besitzers auch Mitglied, um den Status eines Besitzers heraufgestuft werden.</span><span class="sxs-lookup"><span data-stu-id="0761e-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="0761e-150">Es ist außerdem möglich, dass Besitzer zu stufende Websites ihren eigenen Status auf einen Member.</span><span class="sxs-lookup"><span data-stu-id="0761e-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="0761e-151"><sup>4</sup> Teammitglieder können andere Mitglieder zu einem öffentlichen Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0761e-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="0761e-152"><sup>5</sup> während ein Teammitglied Mitglieder direkt zu einem privaten Team hinzufügen kann, können sie Anfordern einer Person zu einem Team hinzugefügt werden, den sie bereits Mitglied sind.</span><span class="sxs-lookup"><span data-stu-id="0761e-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="0761e-153">Wenn ein Element einer Person zu einem Team hinzugefügt werden anfordert, empfangen Team Besitzer eine Benachrichtigung, dass sie eine ausstehende Anforderung sind, die sie annehmen oder ablehnen können.</span><span class="sxs-lookup"><span data-stu-id="0761e-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="0761e-154">Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen.</span><span class="sxs-lookup"><span data-stu-id="0761e-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="0761e-155">Ein Team kann maximal 100 Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="0761e-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="0761e-156">Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="0761e-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="0761e-157">Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="0761e-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="0761e-158">Berechtigungen zum Erstellen von Teams</span><span class="sxs-lookup"><span data-stu-id="0761e-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="0761e-159">Standardmäßig haben alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Office 365-Gruppen und daher ein Team in Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="0761e-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="0761e-160">Sie können haben eine genauere Kontrolle und die Erstellung des neuen Teams und somit die Erstellung des neuen Office 365-Gruppen nach Gruppe erstellen und Verwaltungsrechte an eine Gruppe von Benutzern delegieren einschränken.</span><span class="sxs-lookup"><span data-stu-id="0761e-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="0761e-161">Anweisungen finden Sie unter [verwalten, die Office 365 Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="0761e-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="0761e-163">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="0761e-163">Decision Point</span></span>         |<span data-ttu-id="0761e-164">Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="0761e-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="0761e-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0761e-166">Next Steps</span></span>         |<span data-ttu-id="0761e-167">Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann</span><span class="sxs-lookup"><span data-stu-id="0761e-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
