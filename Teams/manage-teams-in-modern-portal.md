---
title: Verwalten von Teams im Admin Center für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Informationen Sie zum Anzeigen oder aktualisieren Ihren Teams bei der in der Verwaltungskonsole von Microsoft-Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202740"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="dc0fa-103">Verwalten von Teams im Admin Center für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc0fa-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="dc0fa-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="dc0fa-104">Overview</span></span>

<span data-ttu-id="dc0fa-105">Als IT-Administrator müssen Sie anzeigen oder Aktualisieren der Teams, die Ihre Organisation für die Zusammenarbeit, oder Sie eingerichtet wurde möglicherweise Remediation-Aktionen wie dem Zuweisen der Besitzer für eigentümerloser Teams ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="dc0fa-106">Sie können die in Ihrer Organisation über die Microsoft-Teams PowerShell-Modul und das Microsoft-Teams, Administrationscenter verwendeten Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="dc0fa-107">Für vollständige Administration diese zwei Toolsets verwenden sollten Sie sicherstellen, dass Sie eine der folgenden Rollen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="dc0fa-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="dc0fa-108">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="dc0fa-108">Global Administrator</span></span>
- <span data-ttu-id="dc0fa-109">Teams-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="dc0fa-109">Teams Service Administrator</span></span>

<span data-ttu-id="dc0fa-110">Weitere Informationen finden Sie Informationen zu Administratorrollen Teams in [Administratorrollen für Microsoft-Teams, verwenden Sie zum Verwalten von Teams](using-admin-roles.md), und Lesen Sie dazu, wie Sie die PowerShell-Cmdlets zum Verwalten von Teams in der [Microsoft-Teams, Cmdlet-Referenz zu](https://docs.microsoft.com/powershell/teams/?view=teams-ps)verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="dc0fa-111">Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams in der Verwaltungskonsole von Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="dc0fa-112">Teams Übersichtsraster</span><span class="sxs-lookup"><span data-stu-id="dc0fa-112">Teams overview grid</span></span>

<span data-ttu-id="dc0fa-113">Verwaltungstools für Teams sind unter dem Knoten **Teams** in der Verwaltungskonsole von Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="dc0fa-114">(Wählen Sie in der Verwaltungskonsole **Teams** > **Verwalten Teams**.) Jedes Team wird von einer Office 365-Gruppe, und dieser Knoten bietet einen Überblick über die Gruppen, die Microsoft-Teams in Ihrer Organisation aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Teams Übersichtsraster](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="dc0fa-116">Das Raster zeigt die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="dc0fa-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="dc0fa-117">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="dc0fa-117">**Team name**</span></span>
- <span data-ttu-id="dc0fa-118">**Kanäle** - Anzahl alle Kanäle in Teams, einschließlich des allgemeinen Standard-Kanals.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="dc0fa-119">**Benutzer** : Anzahl der Benutzer insgesamt, einschließlich Besitzer, Gäste und Mitglieder von Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="dc0fa-120">**Besitzer** - Anzahl der Besitzer für dieses Team.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="dc0fa-121">**Gäste** - Anzahl von Azure Active Directory B2B Gastbenutzern, die Mitglieder dieser Gruppe sind.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="dc0fa-122">**Private** - die Sichtbarkeit/AccessType der Gruppe der unterstützenden Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="dc0fa-123">**Status** – die archiviert oder den Status "aktiv" für dieses Team.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="dc0fa-124">Weitere Informationen zur Archivierung von Teams in der [Archivierung oder Wiederherstellung ein Team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="dc0fa-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="dc0fa-125">**GroupID** - die eindeutige GroupID der Gruppe der unterstützenden Office 365</span><span class="sxs-lookup"><span data-stu-id="dc0fa-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="dc0fa-126">**Klassifizierung** - Klassifizierung (Wenn in Ihrer Organisation verwendet wird) Sicherung Office 365-Gruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="dc0fa-127">Erfahren Sie mehr über Klassifikationen unter [Klassifikationen für Office-Gruppen in Ihrer Organisation zu erstellen](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="dc0fa-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="dc0fa-128">**Beschreibung** : die Beschreibung für die Sicherung Office 365-Gruppe festlegen</span><span class="sxs-lookup"><span data-stu-id="dc0fa-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="dc0fa-129">Suche</span><span class="sxs-lookup"><span data-stu-id="dc0fa-129">Search</span></span>

<span data-ttu-id="dc0fa-130">Suche derzeit unterstützt die Zeichenfolge "Beginnt mit" und das Feld **Teamname** durchsucht.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="dc0fa-131">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="dc0fa-131">Edit</span></span>

<span data-ttu-id="dc0fa-132">Sie können Gruppe und Team-spezifischen Einstellungen bearbeiten, indem Sie ein Team aus dem Raster auswählen auswählen und dann auf die Schaltfläche **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="dc0fa-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Team bearbeiten](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="dc0fa-134">Team-Profil</span><span class="sxs-lookup"><span data-stu-id="dc0fa-134">Team profile</span></span>

<span data-ttu-id="dc0fa-135">Sie können der Profilseite Team von jedem Team aus dem Hauptfenster Teams Übersichtsraster, indem Sie auf den Teamnamen navigieren.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="dc0fa-136">Die Team Profilseite zeigt die Mitglieder, Besitzer und Gäste, die an das Team gehören (und dessen sichern O365 Gruppe), sowie des Teams Kanäle und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="dc0fa-137">Auf der Profilseite Team können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="dc0fa-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="dc0fa-138">Hinzufügen oder Entfernen von Mitgliedern und Besitzern.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="dc0fa-139">Hinzufügen oder Entfernen von Kanäle (Beachten Sie, dass den allgemeinen Channel nicht entfernt werden können).</span><span class="sxs-lookup"><span data-stu-id="dc0fa-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="dc0fa-140">Aktualisieren von Teams und -Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-140">Update team and group settings.</span></span>
 
![Team-Profil](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="dc0fa-142">Das Ändern von teams</span><span class="sxs-lookup"><span data-stu-id="dc0fa-142">Making changes to teams</span></span>

<span data-ttu-id="dc0fa-143">Sie können die folgenden Elemente eines Teams ändern:</span><span class="sxs-lookup"><span data-stu-id="dc0fa-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="dc0fa-144">**Benutzer im Team** : Sie können hinzufügen oder Entfernen von Mitgliedern, und herauf- oder herabstufen Besitzer</span><span class="sxs-lookup"><span data-stu-id="dc0fa-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="dc0fa-145">**Kanäle** : Sie können neue Kanäle hinzufügen oder Entfernen von vorhandenen Kanäle.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="dc0fa-146">Sie den Standardwert "Allgemein" DDE-Kanal kann nicht gelöscht werden, und Sie nach der Erstellung Channel Name, nicht Beschreibung kann nur bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="dc0fa-147">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="dc0fa-147">**Team name**</span></span>
- <span data-ttu-id="dc0fa-148">**Team Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dc0fa-148">**Team description**</span></span>
- <span data-ttu-id="dc0fa-149">**Team Privacy** - öffentliche oder private</span><span class="sxs-lookup"><span data-stu-id="dc0fa-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="dc0fa-150">**Team Klassifizierung** -, die auf Ihrer Office 365 Gruppe Klassifikationen</span><span class="sxs-lookup"><span data-stu-id="dc0fa-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="dc0fa-151">**Einstellungen für Team Members** - select Team Member Einstellungen</span><span class="sxs-lookup"><span data-stu-id="dc0fa-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="dc0fa-152">Andere unterstützten Änderungen an teams</span><span class="sxs-lookup"><span data-stu-id="dc0fa-152">Other supported changes to teams</span></span>

- <span data-ttu-id="dc0fa-153">**Löschen** : Löschen ein Team ist eine Soft-Löschung des Teams und der entsprechenden Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="dc0fa-154">Um eine versehentlich gelöschte Team wiederherzustellen, befolgen Sie die Anweisungen unter [Wiederherstellen einer gelöschten Office 365-Gruppe](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="dc0fa-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="dc0fa-155">**Archiv** - Archivierung ein Team versetzt das Team in den schreibgeschützten Modus innerhalb von Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="dc0fa-156">Sie können als Administrator archivieren und entpackt Teams im Namen Ihrer Organisation über die Administratorportal.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="dc0fa-157">Die Änderungen, die Sie ein Team stellen angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="dc0fa-158">Wenn Sie Clientgruppen (Ändern der Name, Beschreibung, Foto, private, Klassifizierung oder Teammitglieder) ändern, werden diese Änderungen an Sie über die Pipeline Audit Ergebnisarray als Attribut zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="dc0fa-159">Falls Sie Aktionen für Teams-spezifischen Einstellungen ausführen, werden die Änderungen nachverfolgt und Ergebnisarray als Attribut zugewiesen, die Sie im Allgemeinen Kanal des Teams.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="dc0fa-160">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="dc0fa-160">Troubleshooting</span></span>

<span data-ttu-id="dc0fa-161">**Problem: Teams fehlende aus dem Team Übersichtsraster**</span><span class="sxs-lookup"><span data-stu-id="dc0fa-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="dc0fa-162">Wenn Sie das Microsoft-Teams, Administrationscenter eingeben, fehlen unter der Option **Teams** einige Ihrer Teams aus der Liste im Raster Übersicht Teams.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="dc0fa-163">**Ursache**: Dieses Problem tritt auf, wenn das Team falsch (oder noch nicht) vom System ein Profil erstellt wurde die eine fehlende-Eigenschaft erkannt werden führen können.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="dc0fa-164">**Lösung: Legen Sie die-Eigenschaft manuell auf den richtigen Wert über MS Graph**</span><span class="sxs-lookup"><span data-stu-id="dc0fa-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="dc0fa-165">Ersetzen Sie mit dem Cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** **{Groupid}** in der Abfrage für die tatsächliche GroupId bezieht, die Sie über die Exchange Online Powershell abrufen können, wie das Attribut "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="dc0fa-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="dc0fa-166">Access- [Diagramm-Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="dc0fa-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="dc0fa-167">Melden Sie sich bei Diagramm Explorer im linken Menü auf</span><span class="sxs-lookup"><span data-stu-id="dc0fa-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="dc0fa-168">Ändern der Abfragezeile an: PATCH > v1. 0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="dc0fa-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="dc0fa-169">Fügen Sie den folgenden Wert auf den Text der Anforderung: {"ResourceProvisioningOptions": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="dc0fa-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="dc0fa-170">Führen Sie die Abfrage, auf der oberen rechten.</span><span class="sxs-lookup"><span data-stu-id="dc0fa-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="dc0fa-171">Bestätigen Sie, dass das Team in der Verwaltungskonsole von Microsoft-Teams - ordnungsgemäß angezeigt Team (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="dc0fa-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="dc0fa-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc0fa-172">Learn more</span></span>

[<span data-ttu-id="dc0fa-173">Cmdlet-Referenz zu Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="dc0fa-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="dc0fa-174">Administratorrollen in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="dc0fa-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

