---
title: Verwalten von Teams im Microsoft Teams Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Hier erfahren Sie, wie Sie Ihre Teams im Microsoft Teams Admin Center anzeigen oder aktualisieren können.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e0e96b05aff2d1c0e54bf6f1edb33f9b91aad6d
ms.sourcegitcommit: 4060f20e8e3ce5a0464c12cfebdf8fe3473733fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627031"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="75102-103">Verwalten von Teams im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="75102-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="75102-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="75102-104">Overview</span></span>

<span data-ttu-id="75102-105">Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="75102-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="75102-106">Als Administrator müssen Sie möglicherweise die Teams anzeigen oder aktualisieren, die Ihre Organisation für die Zusammenarbeit eingerichtet hat, oder Wartungsaktionen ausführen, z. b. Teams, die keinen Besitzer haben, einen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="75102-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="75102-107">Sie können die in Ihrer Organisation bestehenden Teams sowohl über das PowerShell-Modul von Microsoft Teams als auch über das Microsoft Teams Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="75102-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="75102-108">Um die vollständigen Verwaltungsfunktionen, die diese beiden Toolsets bieten, nutzen zu können, sollten Sie sicherstellen, dass Sie eine der folgenden Rollen besitzen:</span><span class="sxs-lookup"><span data-stu-id="75102-108">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="75102-109">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="75102-109">Global Administrator</span></span>
- <span data-ttu-id="75102-110">Teams-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="75102-110">Teams Service Administrator</span></span>

<span data-ttu-id="75102-111">Weitere Informationen zu Administratorrollen in Teams finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md). Um mehr über die Nutzung von PowerShell-Cmdlets für die Verwaltung von Teams zu erfahren, lesen Sie die [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="75102-111">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="75102-112">Teams-Übersichtraster</span><span class="sxs-lookup"><span data-stu-id="75102-112">Teams overview grid</span></span>

<span data-ttu-id="75102-113">Verwaltungstools für Teams befinden sich im Microsoft Teams Admin Center unter dem Knoten **Teams**.</span><span class="sxs-lookup"><span data-stu-id="75102-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="75102-114">(Wählen Sie im Admin Center **Teams** > **Teams verwalten** aus.) Jedes Team wird von einer Office 365-Gruppe unterstützt. Dieser Knoten bietet eine Übersicht über Gruppen, die in Ihrer Organisation für Microsoft Teams aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="75102-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Screenshot des Rasters ' Teams-Übersicht '](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="75102-116">Das Raster zeigt die folgenden Eigenschaften an:</span><span class="sxs-lookup"><span data-stu-id="75102-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="75102-117">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="75102-117">**Team name**</span></span>
- <span data-ttu-id="75102-118">**Kanäle**: die Anzahl aller Kanäle im Team, einschließlich des Standardkanals „Allgemein“.</span><span class="sxs-lookup"><span data-stu-id="75102-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="75102-119">**Teammitglieder**: die Anzahl aller Benutzer, einschließlich Besitzern, Gästen und Mitgliedern Ihres Mandanten.</span><span class="sxs-lookup"><span data-stu-id="75102-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="75102-120">**Besitzer**: die Anzahl der Besitzer dieses Teams.</span><span class="sxs-lookup"><span data-stu-id="75102-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="75102-121">**Gäste**: die Anzahl von Azure Active Directory B2B-Gastbenutzern, die Mitglieder dieses Teams sind.</span><span class="sxs-lookup"><span data-stu-id="75102-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="75102-122">**Datenschutz**: der Visibility/AccessType der zugrundeliegenden Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="75102-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="75102-123">**Status**: der archivierte oder aktive Status dieses Teams.</span><span class="sxs-lookup"><span data-stu-id="75102-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="75102-124">Weitere Informationen zum Archivieren von Teams finden Sie unter [Archivieren oder Wiederherstellen eines Teams](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="75102-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="75102-125">**Beschreibung**: die Beschreibung der zugrundeliegenden Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="75102-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="75102-126">**Klassifizierung**: die Klassifizierung (sofern in Ihrer Organisation verwendet), die der zugrundeliegenden Office 365-Gruppe zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="75102-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="75102-127">Erfahren Sie mehr über Klassifizierungen unter [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="75102-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="75102-128">**GroupId**: die eindeutige GroupId der zugrundeliegenden Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="75102-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="75102-129">Wenn nicht alle diese Eigenschaften im Raster angezeigt werden, klicken Sie auf das Symbol **Spalten bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="75102-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="75102-130">Im Bereich \*\*Spalten bearbeiten \*\* können Sie die Umschaltflächen zum Aktivieren oder Deaktivieren von Spalten im Raster verwenden.</span><span class="sxs-lookup"><span data-stu-id="75102-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="75102-131">Klicken Sie nach Abschluss des Vorgangs auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="75102-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="75102-132">Hinzufügen</span><span class="sxs-lookup"><span data-stu-id="75102-132">Add</span></span>

<span data-ttu-id="75102-133">Klicken Sie auf **Hinzufügen**, um ein neues Team hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="75102-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="75102-134">Geben Sie im Bereich **Neues Team hinzufügen** einen Namen und eine Beschreibung ein, legen Sie fest, ob es sich um ein privates oder öffentliches Team handelt und legen Sie die Klassifizierung fest.</span><span class="sxs-lookup"><span data-stu-id="75102-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="75102-135">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="75102-135">Edit</span></span>

<span data-ttu-id="75102-136">Wenn Sie gruppen- und teamspezifische Einstellungen bearbeiten möchten, wählen Sie das Team aus, indem Sie auf die linke Seite des Teamnamens klicken und dann **Bearbeiten** wählen.</span><span class="sxs-lookup"><span data-stu-id="75102-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="75102-137">Archivieren</span><span class="sxs-lookup"><span data-stu-id="75102-137">Archive</span></span>

<span data-ttu-id="75102-138">Sie können ein Team archivieren.</span><span class="sxs-lookup"><span data-stu-id="75102-138">You can archive a team.</span></span> <span data-ttu-id="75102-139">Durch die Archivierung wird das Team in Microsoft Teams in den schreibgeschützten Modus versetzt.</span><span class="sxs-lookup"><span data-stu-id="75102-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="75102-140">Als Administrator können Sie Teams im Namen Ihrer Organisation im Admin Center archivieren und UN-archivieren.</span><span class="sxs-lookup"><span data-stu-id="75102-140">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="75102-141">Löschen</span><span class="sxs-lookup"><span data-stu-id="75102-141">Delete</span></span>

<span data-ttu-id="75102-142">Beim Löschen eines Teams handelt es sich um ein vorläufiges Löschen des Teams und der entsprechenden Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="75102-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="75102-143">Zum Wiederherstellen eines versehentlich gelöschten Teams folgen Sie den Anweisungen unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="75102-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="75102-144">Suche</span><span class="sxs-lookup"><span data-stu-id="75102-144">Search</span></span>

<span data-ttu-id="75102-145">Die Suche unterstützt derzeit die Zeichenfolge „beginnt mit“ und durchsucht das Feld **Teamname**.</span><span class="sxs-lookup"><span data-stu-id="75102-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="75102-146">Teamprofil</span><span class="sxs-lookup"><span data-stu-id="75102-146">Team profile</span></span>

<span data-ttu-id="75102-147">Sie können von der Hauptübersicht aus auf die Profilseite jedes Teams navigieren, indem Sie auf den Teamnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="75102-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="75102-148">Auf der Teamprofilseite werden die Mitglieder, Besitzer und Gäste angezeigt, die zu dem Team (und der Gruppe der zugrundeliegenden Office 365-Gruppe) gehören sowie die Kanäle und Einstellungen des Teams.</span><span class="sxs-lookup"><span data-stu-id="75102-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="75102-149">Auf der Teamprofilseite können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="75102-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="75102-150">Hinzufügen oder Entfernen von Mitgliedern und Besitzern.</span><span class="sxs-lookup"><span data-stu-id="75102-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="75102-151">Hinzufügen oder Entfernen von Kanälen. (beachten Sie, dass Sie den Kanal „Allgemein“ nicht entfernen können.)</span><span class="sxs-lookup"><span data-stu-id="75102-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="75102-152">Ändern von Team- und Gruppeneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="75102-152">Change team and group settings.</span></span>
 
![Screenshot eines Beispiel Team Profils](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="75102-154">Vornehmen von Änderungen an Teams</span><span class="sxs-lookup"><span data-stu-id="75102-154">Making changes to teams</span></span>

<span data-ttu-id="75102-155">Auf der Profilseite des Teams können Sie die folgenden Elemente eines Teams ändern:</span><span class="sxs-lookup"><span data-stu-id="75102-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="75102-156">**Mitglieder**: Mitglieder hinzufügen oder entfernen sowie Besitzer herauf- oder herunterstufen.</span><span class="sxs-lookup"><span data-stu-id="75102-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="75102-157">**Kanäle**: neue Kanäle hinzufügen und vorhandene Kanäle bearbeiten oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="75102-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="75102-158">Denken Sie daran, dass der Standardkanal „Allgemein“ nicht gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="75102-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="75102-159">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="75102-159">**Team name**</span></span>
- <span data-ttu-id="75102-160">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="75102-160">**Description**</span></span>
- <span data-ttu-id="75102-161">**Datenschutz**: Legen Sie fest, ob das Team öffentlich oder privat sein soll.</span><span class="sxs-lookup"><span data-stu-id="75102-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="75102-162">**Klassifizierung**: Dies wird durch Ihre Office 365-Gruppenklassifizierungen gesichert.</span><span class="sxs-lookup"><span data-stu-id="75102-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="75102-163">Wählen Sie zwischen **Vertraulich**, **Streng vertraulich** oder **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="75102-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="75102-164">**Unterhaltungseinstellungen**: Hier legen Sie fest, ob Mitglieder gesendete Nachrichten bearbeiten und löschen können.</span><span class="sxs-lookup"><span data-stu-id="75102-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="75102-165">**Kanaleinstellungen**: Hier legen Sie fest, ob Mitglieder neue Kanäle erstellen und bestehende bearbeiten können. Außerdem, ob sie Registerkarten, Connectors und Apps hinzufügen, bearbeiten und entfernen können.</span><span class="sxs-lookup"><span data-stu-id="75102-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="75102-166">Die Änderungen, die Sie an einem Team vornehmen, werden protokolliert.</span><span class="sxs-lookup"><span data-stu-id="75102-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="75102-167">Wenn Sie Gruppeneinstellungen ändern (ändern des Namens, der Beschreibung, des Fotos, des Datenschutzes, der Klassifizierung oder der Teammitglieder), werden die Änderungen durch die Audit-Pipeline Ihnen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="75102-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="75102-168">Wenn Sie Aktionen gegen teamspezifische Einstellungen ausführen, werden Ihre Änderungen nachverfolgt und Ihnen im Kanal „Allgemein“ des Teams zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="75102-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="75102-169">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="75102-169">Troubleshooting</span></span>

<span data-ttu-id="75102-170">**Problem: Teams fehlen im Team-Übersichtsraster**</span><span class="sxs-lookup"><span data-stu-id="75102-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="75102-171">Einige ihrer Teams fehlen in der Liste der Teams im Team-Übersichtraster.</span><span class="sxs-lookup"><span data-stu-id="75102-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="75102-172">**Ursache**: Dieses Problem tritt auf, wenn das Teamprofil vom System falsch (oder noch nicht) erstellt worden ist, was zu einer fehlenden Eigenschaft und infolgedessen dazu führen kann, dass es nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="75102-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="75102-173">**Lösung: Legen Sie den richtigen Wert der Eigenschaft MS Graph fest**</span><span class="sxs-lookup"><span data-stu-id="75102-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="75102-174">Ersetzen Sie **{groupid}** in der Abfrage durch die tatsächliche zutreffende GroupId, die Sie über Exchange Online PowerShell mit dem Cmdlet **„[Get-Unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)“** als „**ExternalDirectoryObjectId**“-Attribut abrufen können.</span><span class="sxs-lookup"><span data-stu-id="75102-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="75102-175">Auf [Graph-Tester](https://developer.microsoft.com/graph/graph-explorer) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75102-175">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="75102-176">Melden Sie sich bei Graph Explorer im linken Menü an.</span><span class="sxs-lookup"><span data-stu-id="75102-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="75102-177">Ändern Sie die Abfragezeile in: PATCH > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}.</span><span class="sxs-lookup"><span data-stu-id="75102-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="75102-178">Fügen Sie dem Anforderungstext den folgenden Wert hinzu: {"resourceProvisioningOptions": ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="75102-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="75102-179">Führen Sie die Abfrage oben rechts aus.</span><span class="sxs-lookup"><span data-stu-id="75102-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="75102-180">Vergewissern Sie sich, dass das Team ordnungsgemäß in der Teamübersicht des Microsoft Teams Admin Centers angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="75102-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="75102-181">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75102-181">Learn more</span></span>

- [<span data-ttu-id="75102-182">Teams-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="75102-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="75102-183">Verwenden von Teams-Administratorrollen zum Verwalten von Teams</span><span class="sxs-lookup"><span data-stu-id="75102-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="75102-184">Planen der Lebenszyklusverwaltung in Teams</span><span class="sxs-lookup"><span data-stu-id="75102-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
