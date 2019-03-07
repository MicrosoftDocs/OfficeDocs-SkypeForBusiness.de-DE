---
title: Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
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
ms.openlocfilehash: 4887cb129242473da46a611c4f873e79384e5e32
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460340"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="28042-103">Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28042-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="28042-104">In Microsoft-Teams, es gibt zwei Benutzerrollen: **Besitzer** und **Member**.</span><span class="sxs-lookup"><span data-stu-id="28042-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="28042-105">Standardmäßig wird ein neues Team erstellt ein Benutzer den Status eines Besitzers erteilt.</span><span class="sxs-lookup"><span data-stu-id="28042-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="28042-106">Wenn ein Team aus einer vorhandenen Office 365-Gruppe erstellt wird, werden Berechtigungen vererbt.</span><span class="sxs-lookup"><span data-stu-id="28042-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="28042-107">Die folgende Tabelle zeigt den Unterschied Berechtigungen zwischen einer Besitzer und Mitglied.</span><span class="sxs-lookup"><span data-stu-id="28042-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="28042-108">Teambesitzer</span><span class="sxs-lookup"><span data-stu-id="28042-108">Team Owner</span></span> | <span data-ttu-id="28042-109">Teammitglied</span><span class="sxs-lookup"><span data-stu-id="28042-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="28042-110">**Team erstellen**</span><span class="sxs-lookup"><span data-stu-id="28042-110">**Create team**</span></span>          |    <span data-ttu-id="28042-111">Ja,<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="28042-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="28042-112">Nein</span><span class="sxs-lookup"><span data-stu-id="28042-112">No</span></span>      |
|          <span data-ttu-id="28042-113">**Team verlassen**</span><span class="sxs-lookup"><span data-stu-id="28042-113">**Leave team**</span></span>           |    <span data-ttu-id="28042-114">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-114">Yes</span></span>     |     <span data-ttu-id="28042-115">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-115">Yes</span></span>     |
|  <span data-ttu-id="28042-116">**Teamnamen/Teambeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="28042-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="28042-117">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-117">Yes</span></span>     |     <span data-ttu-id="28042-118">Nein</span><span class="sxs-lookup"><span data-stu-id="28042-118">No</span></span>      |
|          <span data-ttu-id="28042-119">**Team löschen**</span><span class="sxs-lookup"><span data-stu-id="28042-119">**Delete team**</span></span>          |    <span data-ttu-id="28042-120">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-120">Yes</span></span>     |     <span data-ttu-id="28042-121">Nein</span><span class="sxs-lookup"><span data-stu-id="28042-121">No</span></span>      |
|          <span data-ttu-id="28042-122">**Kanal hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="28042-122">**Add channel**</span></span>          |    <span data-ttu-id="28042-123">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-123">Yes</span></span>     |    <span data-ttu-id="28042-124">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="28042-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="28042-125">**Kanalnamen/Kanalbeschreibung bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="28042-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="28042-126">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-126">Yes</span></span>     |    <span data-ttu-id="28042-127">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="28042-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="28042-128">**Kanal löschen**</span><span class="sxs-lookup"><span data-stu-id="28042-128">**Delete channel**</span></span>         |    <span data-ttu-id="28042-129">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-129">Yes</span></span>     |    <span data-ttu-id="28042-130">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="28042-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="28042-131">**Mitglieder hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="28042-131">**Add members**</span></span>          |  <span data-ttu-id="28042-132">Ja,<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="28042-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="28042-133">Nein</span><span class="sxs-lookup"><span data-stu-id="28042-133">No</span></span>      |
|           <span data-ttu-id="28042-134">**Registerkarten hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="28042-134">**Add tabs**</span></span>            |    <span data-ttu-id="28042-135">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-135">Yes</span></span>     |    <span data-ttu-id="28042-136">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="28042-136">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="28042-137">**Connectors hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="28042-137">**Add connectors**</span></span>         |    <span data-ttu-id="28042-138">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-138">Yes</span></span>     |    <span data-ttu-id="28042-139">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="28042-139">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="28042-140">**Bots hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="28042-140">**Add bots**</span></span>            |    <span data-ttu-id="28042-141">Ja</span><span class="sxs-lookup"><span data-stu-id="28042-141">Yes</span></span>     |    <span data-ttu-id="28042-142">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="28042-142">Yes<sup>2</sup></span></span>|

<span data-ttu-id="28042-143"><sup>1</sup> Team Besitzer können Teams erstellen, es sei denn, sie haben aus auf diese Weise eingeschränkt wurde.</span><span class="sxs-lookup"><span data-stu-id="28042-143"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="28042-144">Siehe "Berechtigungen zum Erstellen von Teams" weiter unten.</span><span class="sxs-lookup"><span data-stu-id="28042-144">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="28042-145"><sup>2</sup> dieser Elemente können mithilfe eines Besitzers auf einer Teamebene deaktiviert werden in diesem Fall würde die Mitglieder nicht darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="28042-145"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="28042-146"><sup>3</sup> nach dem Hinzufügen eines Elements zu einem Team, kann ein Besitzers auch Mitglied, um den Status eines Besitzers heraufgestuft werden.</span><span class="sxs-lookup"><span data-stu-id="28042-146"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="28042-147">Es ist außerdem möglich, dass Besitzer zu stufende Websites ihren eigenen Status auf einen Member.</span><span class="sxs-lookup"><span data-stu-id="28042-147">It is also possible for an owner to demote their own status to a member.</span></span>



> [!NOTE]
> <span data-ttu-id="28042-148">Besitzer können in der Option „View Teams“ (Teams anzeigen) andere Mitglieder zu Besitzern ernennen.</span><span class="sxs-lookup"><span data-stu-id="28042-148">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="28042-149">Ein Team kann maximal 100 Besitzer haben.</span><span class="sxs-lookup"><span data-stu-id="28042-149">A team can have up to 100 owners.</span></span> <span data-ttu-id="28042-150">Es wird empfohlen, mindestens ein paar Besitzer festzulegen, die beim Verwalten des Teams helfen. Dadurch verhindern Sie auch verwaiste Gruppen, wenn der einzige Besitzer Ihre Organisation verlässt.</span><span class="sxs-lookup"><span data-stu-id="28042-150">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="28042-151">Weitere Informationen zu verwaisten Gruppen finden Sie unter [Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="28042-151">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="28042-152">Berechtigungen zum Erstellen von Teams</span><span class="sxs-lookup"><span data-stu-id="28042-152">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="28042-153">Standardmäßig haben alle Benutzer mit einem Postfach in Exchange Online Berechtigungen zum Erstellen von Office 365-Gruppen und daher ein Team in Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="28042-153">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="28042-154">Sie können haben eine genauere Kontrolle und die Erstellung des neuen Teams und somit die Erstellung des neuen Office 365-Gruppen nach Gruppe erstellen und Verwaltungsrechte an eine Gruppe von Benutzern delegieren einschränken.</span><span class="sxs-lookup"><span data-stu-id="28042-154">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="28042-155">Anweisungen finden Sie unter [verwalten, die Office 365 Gruppen erstellen können](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="28042-155">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Entscheidungspunktsymbol](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="28042-157">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="28042-157">Decision Point</span></span>         |<span data-ttu-id="28042-158">Sollen alle Microsoft Teams-Benutzer in der Lage sein, Teams zu erstellen (empfohlen)?</span><span class="sxs-lookup"><span data-stu-id="28042-158">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Symbol für „Nächste Schritte“](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="28042-160">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28042-160">Next Steps</span></span>         |<span data-ttu-id="28042-161">Ändern der Standardberechtigungen für Benutzer, die Office 365-Gruppen erstellen können, wenn Sie begrenzen müssen, wer Team erstellen kann</span><span class="sxs-lookup"><span data-stu-id="28042-161">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
