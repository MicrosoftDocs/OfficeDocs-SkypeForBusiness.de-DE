---
title: Verwalten von Teams im Admin Center für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin
description: Hier erfahren Sie, wie Sie Ihre Teams im Microsoft Teams Admin Center anzeigen oder aktualisieren.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f495a9cc5b3bfb1fd270e85b2a1fb17bd5f11e68
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233352"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6f53e-103">Verwalten von Teams im Admin Center für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f53e-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="6f53e-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6f53e-104">Overview</span></span>

<span data-ttu-id="6f53e-105">Als IT-Administrator müssen Sie möglicherweise die Teams anzeigen oder aktualisieren, die Ihre Organisation für die Zusammenarbeit eingerichtet hat, oder Sie müssen möglicherweise Behebungsaktionen wie das Zuweisen von Besitzern für besitzerlos ausgeführte Teams ausführen.</span><span class="sxs-lookup"><span data-stu-id="6f53e-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="6f53e-106">Sie können die in Ihrer Organisation verwendeten Teams sowohl über das PowerShell-Modul von Microsoft Teams als auch über das Microsoft Teams Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="6f53e-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="6f53e-107">Wenn Sie die vollständigen Verwaltungsfunktionen mithilfe dieser beiden Toolsets verwenden möchten, müssen Sie sicherstellen, dass Ihnen eine der folgenden Rollen zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="6f53e-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="6f53e-108">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="6f53e-108">Global Administrator</span></span>
- <span data-ttu-id="6f53e-109">Teams-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="6f53e-109">Teams Service Administrator</span></span>

<span data-ttu-id="6f53e-110">Weitere Informationen zu Administratorrollen in Teams finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md), und Sie können weitere Informationen zur Verwendung der PowerShell-Cmdlets für die Verwaltung von Teams in der [Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)finden.</span><span class="sxs-lookup"><span data-stu-id="6f53e-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="6f53e-111">Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="6f53e-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="6f53e-112">Übersicht über Teams</span><span class="sxs-lookup"><span data-stu-id="6f53e-112">Teams overview grid</span></span>

<span data-ttu-id="6f53e-113">Verwaltungstools für Teams befinden sich im Microsoft Teams Admin Center unter dem Knoten **Teams** .</span><span class="sxs-lookup"><span data-stu-id="6f53e-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6f53e-114">(Wählen Sie im Admin Center **Teams** > **Manage Teams**aus.) Jedes Team wird von einer Office 365-Gruppe unterstützt, und dieser Knoten bietet eine Ansicht von Gruppen, die in Ihrer Organisation in Microsoft Teams aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="6f53e-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Screenshot des Rasters ' Teams-Übersicht '](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="6f53e-116">Im Raster werden die folgenden Eigenschaften angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6f53e-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="6f53e-117">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="6f53e-117">**Team name**</span></span>
- <span data-ttu-id="6f53e-118">**Kanäle** – die Anzahl aller Kanäle im Team, einschließlich des Standard Kanals für allgemein.</span><span class="sxs-lookup"><span data-stu-id="6f53e-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="6f53e-119">**Benutzer** – die Anzahl der Gesamtbenutzer, einschließlich Besitzern, Gästen und Mitgliedern Ihres Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6f53e-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="6f53e-120">**Besitzer** – eine Anzahl von Besitzern für dieses Team.</span><span class="sxs-lookup"><span data-stu-id="6f53e-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="6f53e-121">**Gäste** – eine Anzahl von Azure Active Directory-Gastbenutzern, die Mitglieder dieses Teams sind.</span><span class="sxs-lookup"><span data-stu-id="6f53e-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="6f53e-122">**Datenschutz** – die Sichtbarkeit/der Zugriff auf die Gruppe "Backing Office 365".</span><span class="sxs-lookup"><span data-stu-id="6f53e-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="6f53e-123">**Status** – der archivierte oder aktive Status für dieses Team.</span><span class="sxs-lookup"><span data-stu-id="6f53e-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="6f53e-124">Weitere Informationen finden Sie unter Archivieren von Teams [oder Wiederherstellen eines](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)Teams.</span><span class="sxs-lookup"><span data-stu-id="6f53e-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="6f53e-125">**Gruppen** -Nr – die eindeutige Gruppen-Nr der Backing Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="6f53e-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="6f53e-126">**Klassifizierung** : die Klassifizierung (falls in Ihrer Organisation verwendet), die der Gruppe "Backing Office 365" zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6f53e-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="6f53e-127">Weitere Informationen zu Klassifizierungen finden Sie unter [Erstellen von Klassifizierungen für Office-Gruppen in Ihrer Organisation](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="6f53e-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="6f53e-128">**Beschreibung** – die Beschreibung für die Backing Office 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="6f53e-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="6f53e-129">Suche</span><span class="sxs-lookup"><span data-stu-id="6f53e-129">Search</span></span>

<span data-ttu-id="6f53e-130">Die Suche unterstützt derzeit die Zeichenfolge "beginnt mit" \*\*\*\* und durchsucht das Feld Teamname.</span><span class="sxs-lookup"><span data-stu-id="6f53e-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="6f53e-131">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="6f53e-131">Edit</span></span>

<span data-ttu-id="6f53e-132">Sie können Gruppen-und Team spezifische Einstellungen bearbeiten, indem Sie ein Team aus dem Raster auswählen und dann die Schaltfläche " **Bearbeiten** " auswählen.</span><span class="sxs-lookup"><span data-stu-id="6f53e-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Screenshot der Optionen für "Team bearbeiten"](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="6f53e-134">Team Profil</span><span class="sxs-lookup"><span data-stu-id="6f53e-134">Team profile</span></span>

<span data-ttu-id="6f53e-135">Durch Klicken auf den Teamnamen können Sie zur Seite "Teamprofil" eines beliebigen Teams aus dem Hauptübersicht-Raster "Teams" navigieren.</span><span class="sxs-lookup"><span data-stu-id="6f53e-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="6f53e-136">Auf der Seite Teamprofil werden die Mitglieder, Besitzer und Gäste angezeigt, die dem Team (und der zugehörigen Office 365-Gruppe) sowie den Kanälen und Einstellungen des Teams angehören.</span><span class="sxs-lookup"><span data-stu-id="6f53e-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="6f53e-137">Auf der Seite Teamprofil können Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="6f53e-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="6f53e-138">Mitglieder und Besitzer hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f53e-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="6f53e-139">Hinzufügen oder Entfernen von Kanälen (Beachten Sie, dass Sie den Kanal "Allgemein" nicht entfernen können).</span><span class="sxs-lookup"><span data-stu-id="6f53e-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="6f53e-140">Aktualisieren Sie die Team-und Gruppeneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6f53e-140">Update team and group settings.</span></span>
 
![Screenshot eines Beispiel Team Profils](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="6f53e-142">Vornehmen von Änderungen an Teams</span><span class="sxs-lookup"><span data-stu-id="6f53e-142">Making changes to teams</span></span>

<span data-ttu-id="6f53e-143">Sie können die folgenden Elemente eines Teams ändern:</span><span class="sxs-lookup"><span data-stu-id="6f53e-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="6f53e-144">**Benutzer im Team** – Sie können Mitglieder hinzufügen oder entfernen sowie Besitzer herauf-oder herunterstufen.</span><span class="sxs-lookup"><span data-stu-id="6f53e-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="6f53e-145">**Kanäle** – Sie können neue Kanäle hinzufügen oder vorhandene Kanäle entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f53e-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="6f53e-146">Sie können den Standardkanal "Allgemein" nicht löschen, und nach der Erstellung können Sie nur den Kanalnamen, nicht die Beschreibung, bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6f53e-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="6f53e-147">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="6f53e-147">**Team name**</span></span>
- <span data-ttu-id="6f53e-148">**Team Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6f53e-148">**Team description**</span></span>
- <span data-ttu-id="6f53e-149">**Team Datenschutz** – öffentlich oder privat</span><span class="sxs-lookup"><span data-stu-id="6f53e-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="6f53e-150">**Team Klassifizierung** – unter dem Namen Ihrer Office 365-Gruppen Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="6f53e-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="6f53e-151">**Einstellungen für Teammitglieder** – wählen Sie die Einstellungen für Teammitglieder aus.</span><span class="sxs-lookup"><span data-stu-id="6f53e-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="6f53e-152">Weitere unterstützte Änderungen an Teams</span><span class="sxs-lookup"><span data-stu-id="6f53e-152">Other supported changes to teams</span></span>

- <span data-ttu-id="6f53e-153">**Löschen** – das Löschen eines Teams ist ein Soft-Delete des Teams und der entsprechenden Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="6f53e-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="6f53e-154">Wenn Sie ein versehentlich gelöschtes Team wiederherstellen möchten, folgen Sie den Anweisungen unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="6f53e-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="6f53e-155">**Archiv** -Archivierung ein Team versetzt das Team in Microsoft Teams in den schreibgeschützten Modus.</span><span class="sxs-lookup"><span data-stu-id="6f53e-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="6f53e-156">Als Administrator können Sie Teams im Namen Ihrer Organisation über das Administratorportal archivieren und aufteilen.</span><span class="sxs-lookup"><span data-stu-id="6f53e-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="6f53e-157">Die Änderungen, die Sie an einem Team vornehmen, werden protokolliert.</span><span class="sxs-lookup"><span data-stu-id="6f53e-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="6f53e-158">Wenn Sie Gruppeneinstellungen ändern (Name, Beschreibung, Foto, Datenschutz, Klassifikation oder Teammitglieder ändern), werden Ihnen diese Änderungen über die Audit-Pipeline zugeschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f53e-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="6f53e-159">Wenn Sie Aktionen für Teams-spezifische Einstellungen durchführen, werden Ihre Änderungen nachverfolgt und Ihnen im allgemeinen Kanal des Teams zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6f53e-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6f53e-160">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="6f53e-160">Troubleshooting</span></span>

<span data-ttu-id="6f53e-161">**Problem: fehlende Teams im Team Übersicht-Raster**</span><span class="sxs-lookup"><span data-stu-id="6f53e-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="6f53e-162">Wenn Sie das Microsoft Teams Admin Center aufrufen, fehlen einige ihrer Teams unter der Option **Teams** in der Liste im Team Übersicht-Raster.</span><span class="sxs-lookup"><span data-stu-id="6f53e-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="6f53e-163">**Ursache**: dieses Problem tritt auf, wenn das Team fälschlicherweise (oder noch nicht) vom System profiliert wurde, was zu einer fehlenden Eigenschaft führen kann, damit es erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="6f53e-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="6f53e-164">**Lösung: Manuelles Festlegen der Eigenschaft auf den richtigen Wert über MS Graph**</span><span class="sxs-lookup"><span data-stu-id="6f53e-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="6f53e-165">Ersetzen Sie **{Gruppen** -Nr} in der Abfrage für die eigentliche fragliche Gruppen-Nr, die Sie über die Exchange Online-PowerShell mit dem Cmdlet **"[Get-Unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** als "**ExternalDirectoryObjectId**"-Attribut abrufen können.</span><span class="sxs-lookup"><span data-stu-id="6f53e-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="6f53e-166">Access- [Diagramm-Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="6f53e-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="6f53e-167">Anmelden beim Diagramm-Explorer im linken Menü</span><span class="sxs-lookup"><span data-stu-id="6f53e-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="6f53e-168">Ändern Sie die Abfragezeile in: Patch #a0 v 1.0 #a1https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="6f53e-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="6f53e-169">Fügen Sie den folgenden Wert für den Anforderungstext hinzu: {"resourceProvisioningOptions": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="6f53e-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="6f53e-170">Führen Sie die Abfrage oben rechts aus.</span><span class="sxs-lookup"><span data-stu-id="6f53e-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="6f53e-171">Bestätigen, dass das Team im Microsoft Teams Admin Center richtig angezeigt wird – Team Übersicht</span><span class="sxs-lookup"><span data-stu-id="6f53e-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="6f53e-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f53e-172">Learn more</span></span>

[<span data-ttu-id="6f53e-173">Microsoft Teams-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="6f53e-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="6f53e-174">Administratorrollen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f53e-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

