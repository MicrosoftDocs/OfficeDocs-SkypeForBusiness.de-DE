---
title: Verwalten von Teams im Admin Center für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Hier erfahren Sie, wie Sie Ihre Teams im Microsoft Teams Admin Center anzeigen oder aktualisieren.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b8937827cb5e3fa80e9ebae93d9958be2cf0f38
ms.sourcegitcommit: 8a8c71aea5bd2420b110619607ef0715136578ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2019
ms.locfileid: "36286233"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="4e597-103">Verwalten von Teams im Admin Center für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e597-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="4e597-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e597-104">Overview</span></span>

<span data-ttu-id="4e597-105">Als Administrator müssen Sie möglicherweise die Teams anzeigen oder aktualisieren, die Ihre Organisation für die Zusammenarbeit eingerichtet hat, oder Sie müssen möglicherweise Behebungsaktionen wie das Zuweisen von Besitzern für besitzerlos ausgeführte Teams ausführen.</span><span class="sxs-lookup"><span data-stu-id="4e597-105">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="4e597-106">Sie können die in Ihrer Organisation verwendeten Teams sowohl über das PowerShell-Modul von Microsoft Teams als auch über das Microsoft Teams Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="4e597-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="4e597-107">Wenn Sie die vollständigen Verwaltungsfunktionen mithilfe dieser beiden Toolsets verwenden möchten, müssen Sie sicherstellen, dass Ihnen eine der folgenden Rollen zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="4e597-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="4e597-108">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="4e597-108">Global Administrator</span></span>
- <span data-ttu-id="4e597-109">Teams-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="4e597-109">Teams Service Administrator</span></span>

<span data-ttu-id="4e597-110">Weitere Informationen zu Administratorrollen in Teams finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md), und Sie können weitere Informationen zur Verwendung der PowerShell-Cmdlets für die Verwaltung von Teams in der [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)finden.</span><span class="sxs-lookup"><span data-stu-id="4e597-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>

<span data-ttu-id="4e597-111">Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="4e597-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="4e597-112">Übersicht über Teams</span><span class="sxs-lookup"><span data-stu-id="4e597-112">Teams overview grid</span></span>

<span data-ttu-id="4e597-113">Verwaltungstools für Teams befinden sich im Microsoft Teams Admin Center unter dem Knoten **Teams** .</span><span class="sxs-lookup"><span data-stu-id="4e597-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4e597-114">(Wählen Sie im Admin Center **Teams** > **Manage Teams**aus.) Jedes Team wird von einer Office 365-Gruppe unterstützt, und dieser Knoten bietet eine Ansicht von Gruppen, die in Ihrer Organisation in Microsoft Teams aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="4e597-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Screenshot des Rasters ' Teams-Übersicht '](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="4e597-116">Im Raster werden die folgenden Eigenschaften angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4e597-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="4e597-117">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="4e597-117">**Team name**</span></span>
- <span data-ttu-id="4e597-118">**Kanäle** – die Anzahl aller Kanäle im Team, einschließlich des Standard Kanals für allgemein.</span><span class="sxs-lookup"><span data-stu-id="4e597-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="4e597-119">**Team Mitglieder** – eine Anzahl von Gesamt Benutzern, einschließlich Besitzern, Gästen und Mitgliedern Ihres Mandanten.</span><span class="sxs-lookup"><span data-stu-id="4e597-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="4e597-120">**Besitzer** – eine Anzahl von Besitzern für dieses Team.</span><span class="sxs-lookup"><span data-stu-id="4e597-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="4e597-121">**Gäste** – eine Anzahl von Azure Active Directory-Gastbenutzern, die Mitglieder dieses Teams sind.</span><span class="sxs-lookup"><span data-stu-id="4e597-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="4e597-122">**Datenschutz** – die Sichtbarkeit/der Zugriff auf die Gruppe "Backing Office 365".</span><span class="sxs-lookup"><span data-stu-id="4e597-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="4e597-123">**Status** – der archivierte oder aktive Status für dieses Team.</span><span class="sxs-lookup"><span data-stu-id="4e597-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="4e597-124">Weitere Informationen zum Archivieren von Teams finden Sie unter [archivieren oder Wiederherstellen eines](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)Teams.</span><span class="sxs-lookup"><span data-stu-id="4e597-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="4e597-125">**Beschreibung** – die Beschreibung der Gruppe "Backing Office 365".</span><span class="sxs-lookup"><span data-stu-id="4e597-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="4e597-126">**Klassifizierung** : die Klassifizierung (falls in Ihrer Organisation verwendet), die der Gruppe "Backing Office 365" zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4e597-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="4e597-127">Weitere Informationen zu Klassifizierungen finden Sie unter [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="4e597-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="4e597-128">**Gruppen** -Nr – die eindeutige Gruppen-Nr der Sicherungs-Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="4e597-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="4e597-129">Wenn nicht alle diese Eigenschaften im Raster angezeigt werden, klicken Sie auf das Symbol **Spalten bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="4e597-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="4e597-130">Im Bereich **Spalten bearbeiten** können Sie die Umschalter verwenden, um Spalten im Raster zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4e597-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="4e597-131">Wenn Sie fertig sind, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="4e597-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="4e597-132">Hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4e597-132">Add</span></span>

<span data-ttu-id="4e597-133">Wenn Sie ein neues Team hinzufügen möchten, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4e597-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="4e597-134">Geben Sie im Bereich **Neues Team hinzufügen** dem Team einen Namen und eine Beschreibung, legen Sie fest, ob es sich um ein privates oder öffentliches Team machen soll, und legen Sie die Klassifizierung fest.</span><span class="sxs-lookup"><span data-stu-id="4e597-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="4e597-135">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="4e597-135">Edit</span></span>

<span data-ttu-id="4e597-136">Wenn Sie Gruppen-und Team spezifische Einstellungen bearbeiten möchten, wählen Sie das Team aus, indem Sie links neben dem Teamnamen klicken, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="4e597-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="4e597-137">Archiv</span><span class="sxs-lookup"><span data-stu-id="4e597-137">Archive</span></span>

<span data-ttu-id="4e597-138">Sie können ein Team archivieren.</span><span class="sxs-lookup"><span data-stu-id="4e597-138">You can archive a team.</span></span> <span data-ttu-id="4e597-139">Durch die Archivierung eines Teams wird das Team in Teams in den schreibgeschützten Modus versetzt.</span><span class="sxs-lookup"><span data-stu-id="4e597-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="4e597-140">Als Administrator können Sie Teams im Namen Ihrer Organisation im Admin Center archivieren und aufteilen.</span><span class="sxs-lookup"><span data-stu-id="4e597-140">As an admin, you can archive and unarchive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="4e597-141">Löschen</span><span class="sxs-lookup"><span data-stu-id="4e597-141">Delete</span></span>

<span data-ttu-id="4e597-142">Das Löschen eines Teams ist ein Soft-Delete des Teams und der entsprechenden Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="4e597-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="4e597-143">Wenn Sie ein versehentlich gelöschtes Team wiederherstellen möchten, folgen Sie den Anweisungen unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4e597-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="4e597-144">Suche</span><span class="sxs-lookup"><span data-stu-id="4e597-144">Search</span></span>

<span data-ttu-id="4e597-145">Die Suche unterstützt derzeit die Zeichenfolge "beginnt mit" \*\*\*\* und durchsucht das Feld Teamname.</span><span class="sxs-lookup"><span data-stu-id="4e597-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="4e597-146">Team Profil</span><span class="sxs-lookup"><span data-stu-id="4e597-146">Team profile</span></span>

<span data-ttu-id="4e597-147">Durch Klicken auf den Teamnamen können Sie zur Seite "Teamprofil" eines beliebigen Teams aus dem Hauptübersicht-Raster "Teams" navigieren.</span><span class="sxs-lookup"><span data-stu-id="4e597-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="4e597-148">Auf der Seite "Teamprofil" werden die Mitglieder, Besitzer und Gäste angezeigt, die zum Team gehören (und die Gruppe "Backing Office 365") sowie die Kanäle und Einstellungen des Teams.</span><span class="sxs-lookup"><span data-stu-id="4e597-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="4e597-149">Auf der Seite Teamprofil können Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4e597-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="4e597-150">Mitglieder und Besitzer hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="4e597-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="4e597-151">Hinzufügen oder Entfernen von Kanälen (Beachten Sie, dass Sie den Kanal "Allgemein" nicht entfernen können).</span><span class="sxs-lookup"><span data-stu-id="4e597-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="4e597-152">Ändern Sie die Team-und Gruppeneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4e597-152">Change team and group settings.</span></span>
 
![Screenshot eines Beispiel Team Profils](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="4e597-154">Vornehmen von Änderungen an Teams</span><span class="sxs-lookup"><span data-stu-id="4e597-154">Making changes to teams</span></span>

<span data-ttu-id="4e597-155">Auf der Profilseite des Teams können Sie die folgenden Elemente eines Teams ändern:</span><span class="sxs-lookup"><span data-stu-id="4e597-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="4e597-156">**Mitglieder** – Mitglieder hinzufügen oder entfernen sowie Besitzer höher-oder tiefer stufen.</span><span class="sxs-lookup"><span data-stu-id="4e597-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="4e597-157">**Kanäle** – fügen Sie neue Kanäle hinzu, und bearbeiten oder entfernen Sie vorhandene Kanäle.</span><span class="sxs-lookup"><span data-stu-id="4e597-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="4e597-158">Beachten Sie, dass Sie den standardmäßigen allgemeinen Kanal nicht löschen können.</span><span class="sxs-lookup"><span data-stu-id="4e597-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="4e597-159">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="4e597-159">**Team name**</span></span>
- <span data-ttu-id="4e597-160">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4e597-160">**Description**</span></span>
- <span data-ttu-id="4e597-161">**Privatsphäre** – legen Sie fest, ob das Team öffentlich oder privat ist.</span><span class="sxs-lookup"><span data-stu-id="4e597-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="4e597-162">**Klassifizierung** – Dies wird durch Ihre Office 365-Gruppen Klassifizierungen unter sichert.</span><span class="sxs-lookup"><span data-stu-id="4e597-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="4e597-163">Wählen Sie **vertraulich**, **hoch vertraulich**oder **Allgemein**aus.</span><span class="sxs-lookup"><span data-stu-id="4e597-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="4e597-164">**Konversations Einstellungen** – legen Sie fest, ob Mitglieder gesendete Nachrichten bearbeiten und löschen können.</span><span class="sxs-lookup"><span data-stu-id="4e597-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="4e597-165">**Kanaleinstellungen** – legen Sie fest, ob Mitglieder neue Kanäle erstellen und vorhandene bearbeiten sowie Tabstopps, Connectors und apps hinzufügen, bearbeiten und entfernen können.</span><span class="sxs-lookup"><span data-stu-id="4e597-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="4e597-166">Die Änderungen, die Sie an einem Team vornehmen, werden protokolliert.</span><span class="sxs-lookup"><span data-stu-id="4e597-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="4e597-167">Wenn Sie Gruppeneinstellungen ändern (Name, Beschreibung, Foto, Datenschutz, Klassifikation oder Teammitglieder ändern), werden Ihnen die Änderungen über die Überwachungs Pipeline zugeschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e597-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="4e597-168">Wenn Sie Aktionen für Teams-spezifische Einstellungen durchführen, werden Ihre Änderungen nachverfolgt und Ihnen im allgemeinen Kanal des Teams zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4e597-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4e597-169">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="4e597-169">Troubleshooting</span></span>

<span data-ttu-id="4e597-170">**Problem: fehlende Teams im Team Übersicht-Raster**</span><span class="sxs-lookup"><span data-stu-id="4e597-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="4e597-171">Einige ihrer Teams fehlen in der Liste der Teams im Team Übersicht-Raster.</span><span class="sxs-lookup"><span data-stu-id="4e597-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="4e597-172">**Ursache**: dieses Problem tritt auf, wenn das Team fälschlicherweise (oder noch nicht) vom System profiliert wurde, was zu einer fehlenden Eigenschaft führen kann, damit es erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="4e597-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="4e597-173">**Lösung: Manuelles Festlegen der Eigenschaft auf den richtigen Wert über MS Graph**</span><span class="sxs-lookup"><span data-stu-id="4e597-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="4e597-174">Ersetzen Sie **{Gruppen** -Nr} in der Abfrage für die eigentliche fragliche Gruppen-Nr, die Sie über die Exchange Online-PowerShell mit dem Cmdlet **"[Get-Unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** als "**ExternalDirectoryObjectId**"-Attribut abrufen können.</span><span class="sxs-lookup"><span data-stu-id="4e597-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="4e597-175">Access- [Diagramm-Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="4e597-175">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).</span></span>

2. <span data-ttu-id="4e597-176">Anmelden beim Diagramm-Explorer im linken Menü</span><span class="sxs-lookup"><span data-stu-id="4e597-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="4e597-177">Ändern Sie die Abfragezeile in: Patch #a0 v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}#a1.</span><span class="sxs-lookup"><span data-stu-id="4e597-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="4e597-178">Fügen Sie im Anforderungstext den folgenden Wert hinzu: {"resourceProvisioningOptions": ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="4e597-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="4e597-179">Führen Sie die Abfrage oben rechts aus.</span><span class="sxs-lookup"><span data-stu-id="4e597-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="4e597-180">Bestätigen Sie, dass das Team im Microsoft Teams Admin Center-Team Übersicht richtig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4e597-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="4e597-181">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e597-181">Learn more</span></span>

- [<span data-ttu-id="4e597-182">Teams-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="4e597-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="4e597-183">Verwenden von Teams-Administratorrollen zum Verwalten von Teams</span><span class="sxs-lookup"><span data-stu-id="4e597-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="4e597-184">Planen der Lebenszyklusverwaltung in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e597-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
