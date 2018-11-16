---
title: Verwalten von Teams in der Microsoft-Teams & Skype für Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Informationen Sie zum Anzeigen oder aktualisieren Ihren Teams im Microsoft-Teams & Skype für Business Admin Center.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14ab474289e5a677e1125df7146ba7c5a6fc2ca1
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539057"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="8c71c-103">Verwalten von Teams in der Microsoft-Teams & Skype für Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="8c71c-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="8c71c-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8c71c-104">Overview</span></span>

<span data-ttu-id="8c71c-105">Als IT-Administrator müssen Sie anzeigen oder Aktualisieren der Teams, die Ihre Organisation für die Zusammenarbeit, oder Sie eingerichtet wurde möglicherweise Remediation-Aktionen wie dem Zuweisen der Besitzer für eigentümerloser Teams ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="8c71c-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="8c71c-106">Sie können die in Ihrer Organisation über die Microsoft-Teams PowerShell-Modul und an den Microsoft-Teams & die Skype für Business Admin Center verwendeten Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="8c71c-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="8c71c-107">Für vollständige Administration diese zwei Toolsets verwenden sollten Sie sicherstellen, dass Sie eine der folgenden Rollen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="8c71c-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="8c71c-108">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="8c71c-108">Global Administrator</span></span>
- <span data-ttu-id="8c71c-109">Teams-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="8c71c-109">Teams Service Administrator</span></span>

<span data-ttu-id="8c71c-110">Sie sollten auch sicherstellen, dass Ihr Konto ein nicht-Teams eine Testversion für die Verwaltung zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="8c71c-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="8c71c-111">Als Teil des ein bekanntes Problem sollten Sie sicherstellen, dass Ihr Konto nur **eine** Administratorrolle zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="8c71c-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="8c71c-112">Weitere Informationen finden Sie Informationen zu Administratorrollen in Microsoft-Teams, in der [Microsoft-Teams verwenden, Administratorrollen zum Verwalten von Teams](using-admin-roles.md), und Lesen Sie dazu, wie Sie die PowerShell-Cmdlets zum Verwalten von Teams in der [Microsoft-Teams, Cmdlet-Referenz zu](https://docs.microsoft.com/powershell/teams/?view=teams-ps)verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c71c-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="8c71c-113">Dieser Artikel enthält eine Übersicht über die Verwaltungstools für Teams in der Microsoft-Teams & Skype für Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="8c71c-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="8c71c-114">Teams Übersichtsraster</span><span class="sxs-lookup"><span data-stu-id="8c71c-114">Teams overview grid</span></span>

<span data-ttu-id="8c71c-115">Verwaltungstools für Teams sind unter dem Knoten **Teams** im Microsoft-Teams & Skype für Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="8c71c-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="8c71c-116">(Wählen Sie in der Verwaltungskonsole **Teams** > **Verwalten Teams**.) Jedes Team wird von einer Office 365-Gruppe, und dieser Knoten bietet einen Überblick über die Gruppen, die Microsoft-Teams in Ihrer Organisation aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="8c71c-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="8c71c-117">Es werden gerade abgleichen, die zuvor erstellte Teams, um sicherzustellen, dass sie in dieser Ansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8c71c-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Teams Übersichtsraster](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="8c71c-119">Das Raster zeigt die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8c71c-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="8c71c-120">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="8c71c-120">**Team name**</span></span>
- <span data-ttu-id="8c71c-121">**Kanäle** - Anzahl alle Kanäle in Teams, einschließlich des allgemeinen Standard-Kanals.</span><span class="sxs-lookup"><span data-stu-id="8c71c-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="8c71c-122">**Benutzer** : Anzahl der Benutzer insgesamt, einschließlich Besitzer, Gäste und Mitglieder von Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="8c71c-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="8c71c-123">**Besitzer** - Anzahl der Besitzer für dieses Team.</span><span class="sxs-lookup"><span data-stu-id="8c71c-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="8c71c-124">**Gäste** - Anzahl von Azure Active Directory B2B Gastbenutzern, die Mitglieder dieser Gruppe sind.</span><span class="sxs-lookup"><span data-stu-id="8c71c-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="8c71c-125">**Private** - die AccessType der Gruppe der unterstützenden Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c71c-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="8c71c-126">Suche</span><span class="sxs-lookup"><span data-stu-id="8c71c-126">Search</span></span>

<span data-ttu-id="8c71c-127">Suche derzeit unterstützt die Zeichenfolge "Beginnt mit" und das Feld **Teamname** durchsucht.</span><span class="sxs-lookup"><span data-stu-id="8c71c-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="8c71c-128">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="8c71c-128">Edit</span></span>

<span data-ttu-id="8c71c-129">Sie können Gruppe und Team-spezifischen Einstellungen bearbeiten, indem Sie ein Team aus dem Raster auswählen auswählen und dann auf die Schaltfläche **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="8c71c-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Team bearbeiten](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="8c71c-131">Team-Profil</span><span class="sxs-lookup"><span data-stu-id="8c71c-131">Team profile</span></span>

<span data-ttu-id="8c71c-132">Sie können der Profilseite Team von jedem Team aus dem Hauptfenster Teams Übersichtsraster, indem Sie auf den Teamnamen navigieren.</span><span class="sxs-lookup"><span data-stu-id="8c71c-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="8c71c-133">Die Team Profilseite zeigt die Mitglieder, Besitzer und Gäste, die an das Team gehören (und dessen sichern O365 Gruppe), sowie des Teams Kanäle und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8c71c-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="8c71c-134">Auf der Profilseite Team können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="8c71c-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="8c71c-135">Hinzufügen oder Entfernen von Mitgliedern und Besitzern.</span><span class="sxs-lookup"><span data-stu-id="8c71c-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="8c71c-136">Hinzufügen oder Entfernen von Kanäle (Beachten Sie, dass den allgemeinen Channel nicht entfernt werden können).</span><span class="sxs-lookup"><span data-stu-id="8c71c-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="8c71c-137">Aktualisieren von Teams und -Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8c71c-137">Update team and group settings.</span></span>
 
![Team-Profil](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="8c71c-139">Das Ändern von teams</span><span class="sxs-lookup"><span data-stu-id="8c71c-139">Making changes to teams</span></span>

<span data-ttu-id="8c71c-140">Sie können die folgenden Elemente eines Teams ändern:</span><span class="sxs-lookup"><span data-stu-id="8c71c-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="8c71c-141">**Benutzer im Team** : Sie können hinzufügen oder Entfernen von Mitgliedern, und herauf- oder herabstufen Besitzer</span><span class="sxs-lookup"><span data-stu-id="8c71c-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="8c71c-142">**Kanäle** : Sie können neue Kanäle hinzufügen oder Entfernen von vorhandenen Kanäle.</span><span class="sxs-lookup"><span data-stu-id="8c71c-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="8c71c-143">Sie den Standardwert "Allgemein" DDE-Kanal kann nicht gelöscht werden, und Sie nach der Erstellung Channel Name, nicht Beschreibung kann nur bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c71c-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="8c71c-144">**Teamname**</span><span class="sxs-lookup"><span data-stu-id="8c71c-144">**Team name**</span></span>
- <span data-ttu-id="8c71c-145">**Team Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8c71c-145">**Team description**</span></span>
- <span data-ttu-id="8c71c-146">**Team Privacy** - öffentliche oder private</span><span class="sxs-lookup"><span data-stu-id="8c71c-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="8c71c-147">**Team Klassifizierung** -, die auf Ihrer Office 365 Gruppe Klassifikationen</span><span class="sxs-lookup"><span data-stu-id="8c71c-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="8c71c-148">**Einstellungen für Team Members** - select Team Member Einstellungen</span><span class="sxs-lookup"><span data-stu-id="8c71c-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="8c71c-149">Die Änderungen, die Sie ein Team stellen angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="8c71c-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="8c71c-150">Wenn Sie Clientgruppen (Ändern der Name, Beschreibung, Foto, private, Klassifizierung oder Teammitglieder) ändern, werden diese Änderungen an Sie über die Pipeline Audit Ergebnisarray als Attribut zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8c71c-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="8c71c-151">Falls Sie Aktionen für Teams-spezifischen Einstellungen ausführen, werden die Änderungen nachverfolgt und Ergebnisarray als Attribut zugewiesen, die Sie im Allgemeinen Kanal des Teams.</span><span class="sxs-lookup"><span data-stu-id="8c71c-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="8c71c-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c71c-152">Learn more</span></span>

[<span data-ttu-id="8c71c-153">Cmdlet-Referenz zu Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="8c71c-153">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="8c71c-154">Administratorrollen in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="8c71c-154">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

