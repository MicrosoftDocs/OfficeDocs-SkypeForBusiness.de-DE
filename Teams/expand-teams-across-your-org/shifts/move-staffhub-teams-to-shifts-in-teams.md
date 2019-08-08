---
title: Verschieben Ihrer StaffHub-Teams in Schichten in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Microsoft StaffHub-Teams verschieben und Daten in Microsoft Teams in Schichten planen können.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cef8c6fbfd5ed0b19d6762b7508b311413d11066
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233283"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="1ef86-103">Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ef86-104">Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="1ef86-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="1ef86-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="1ef86-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1ef86-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="1ef86-107">StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="1ef86-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="1ef86-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="1ef86-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="1ef86-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="1ef86-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="1ef86-110">Die Schicht-app in Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und den konstanten Fluss von Schicht-Swaps und-Abbrüchen, die täglich auftreten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="1ef86-111">Team Mitglieder können auf Ihre Plan-und Schicht Informationen direkt in der APP und auf Ihren Geräten zugreifen, um Ihre Einstellungen festzulegen, ihre Zeitpläne zu verwalten und die Freizeit zu beantragen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="1ef86-112">In diesem Artikel erfahren Sie, wie Sie die StaffHub-Teams Ihrer Organisation verschieben und Daten in Teams verschieben können.</span><span class="sxs-lookup"><span data-stu-id="1ef86-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="1ef86-113">Sie umfasst:</span><span class="sxs-lookup"><span data-stu-id="1ef86-113">It covers:</span></span>

- [<span data-ttu-id="1ef86-114">Was Sie über den Umzug in Teams wissen müssen</span><span class="sxs-lookup"><span data-stu-id="1ef86-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="1ef86-115">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="1ef86-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="1ef86-116">Durchführen eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="1ef86-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="1ef86-117">Gehen Sie über ihr Pilotprojekt hinaus und verschieben Sie alle StaffHub-Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="1ef86-118">Überwachen der Verwendung von Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="1ef86-119">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1ef86-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="1ef86-120">Ganz gleich, ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub-Teams oder einem Großunternehmen mit Hunderten von StaffHub-Teams sind, hier finden Sie die Administratoranleitung, die Sie benötigen, um den Übergang zu Teams erfolgreich zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="1ef86-121">Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="1ef86-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="1ef86-122">Wenn Sie dies noch nicht getan haben, schauen Sie sich die [FAQ zu StaffHub Retirement](microsoft-staffhub-to-be-retired.md) an, um Antworten auf Ihre Fragen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="1ef86-123">Was Sie über den Umzug in Teams wissen müssen</span><span class="sxs-lookup"><span data-stu-id="1ef86-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="1ef86-124">Zeitpunkt für den Wechsel zu Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-124">When to move to Teams</span></span>

<span data-ttu-id="1ef86-125">Ab dem 1. Oktober 2019 wird StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="1ef86-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="1ef86-126">Wir empfehlen Ihnen, die Verwendung von Teams noch heute zu verwenden und zu beginnen, die Teams und Benutzer Ihrer Organisation aus StaffHub zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="1ef86-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="1ef86-127">Da die Zeitplanverwaltung das am häufigsten verwendete Feature in StaffHub ist, empfehlen wir, dass Sie die app "Schichten" in Teams verwenden, die sich weiter bewegen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="1ef86-128">Was wird in Teams verschoben?</span><span class="sxs-lookup"><span data-stu-id="1ef86-128">What is moved to Teams</span></span>

<span data-ttu-id="1ef86-129">Wenn Sie ein StaffHub-Team verschieben, werden Teammitgliedschaft, Benutzer Details, Team Zeitpläne und Chatdaten in Teams verschoben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="1ef86-130">Dateien werden nicht verschoben, wenn Sie ein StaffHub-Team verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="1ef86-131">Wenn ein StaffHub-Team Dateien enthält, die Sie auch in Teams verschieben möchten, verschieben Sie die Dateien in einem separaten Schritt.</span><span class="sxs-lookup"><span data-stu-id="1ef86-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="1ef86-132">Jedes StaffHub-Team benötigt eine entsprechende Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="1ef86-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="1ef86-133">Wenn einem StaffHub-Team keine Office 365-Gruppe zugeordnet ist, wird automatisch ein für Sie erstellt, um den Übergang zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="1ef86-134">Angesichts der Unterschiede bei der Team-und Gruppenbenennung zwischen Teams und StaffHub wird möglicherweise in Teams ein anderer Teamname angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ef86-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="1ef86-135">Wenn Sie Teams von StaffHub in Teams umstellen, haben die Benutzer keinen Zugriff mehr auf ihre Zeitpläne in StaffHub und werden an Schichten in Teams umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="1ef86-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="1ef86-136">Wir empfehlen, dass Sie diese Änderung in Ihrer Organisation übermitteln, um Unterbrechungen zu minimieren und Benutzer zu ermutigen, Teams zu übernehmen und zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="1ef86-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="1ef86-137">Wenn Sie über Azure AD Premium verfügen, können Sie [einen Bericht ausführen](run-report-to-show-staffhub-usage.md) , um eine Liste der StaffHub-Benutzer in Ihrer Organisation abzurufen, die über diese Änderung Bescheid wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="1ef86-138">Nachdem Sie ein StaffHub-Team in Teams verschoben haben, gibt es keine Rollback-Option.</span><span class="sxs-lookup"><span data-stu-id="1ef86-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="1ef86-139">Benutzererfahrung beim Verschieben eines Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-139">User experience when you move a team</span></span>

<span data-ttu-id="1ef86-140">Es gibt minimale Ausfallzeiten (wenn überhaupt keine Sekunde) für Benutzer, wenn Ihr Team von StaffHub zu Schichten in Teams gewechselt hat.</span><span class="sxs-lookup"><span data-stu-id="1ef86-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="1ef86-141">Benutzer können StaffHub weiterhin verwenden, bis der Wechsel zu Teams abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1ef86-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="1ef86-142">Nach Abschluss des Umzugs wird den Teammitgliedern eine Meldung angezeigt, in der Sie darüber informiert werden, dass Sie die Verwendung von Schichten in Teams für den Zugriff auf Ihren Team Zeitplan benötigen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="1ef86-143">Nachfolgend finden Sie ein Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="1ef86-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="1ef86-144">![Beispiel für die Meldung, die Benutzern angezeigt wird.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde")</span><span class="sxs-lookup"><span data-stu-id="1ef86-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="1ef86-145">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="1ef86-145">Prepare</span></span>

<span data-ttu-id="1ef86-146">Hier erfahren Sie, wie Sie sich auf den Umzug in Teams vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="1ef86-147">Überprüfen, ob Voraussetzungen erfüllt sind</span><span class="sxs-lookup"><span data-stu-id="1ef86-147">Check that prerequisites are met</span></span>

<span data-ttu-id="1ef86-148">Bevor Sie ein StaffHub-Team in Teams verschieben, stellen Sie Folgendes sicher:</span><span class="sxs-lookup"><span data-stu-id="1ef86-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="1ef86-149">Der angemeldete Benutzer ist ein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="1ef86-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="1ef86-150">Teams ist für alle Benutzer im Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1ef86-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="1ef86-151">Die Erstellung von Office 365-Gruppen ist im Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1ef86-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="1ef86-152">Die teamStaffHub ist gültig.</span><span class="sxs-lookup"><span data-stu-id="1ef86-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="1ef86-153">Das StaffHub-Team enthält Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="1ef86-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="1ef86-154">Alle StaffHub-Teammitglieder sind mit einem Azure AD-Konto verknüpft.</span><span class="sxs-lookup"><span data-stu-id="1ef86-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="1ef86-155">Wenn diese Voraussetzungen nicht erfüllt werden, schlägt die Verschiebungsanforderung fehl.</span><span class="sxs-lookup"><span data-stu-id="1ef86-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="1ef86-156">Zuweisen von Teams-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="1ef86-156">Assign Teams licenses</span></span>

<span data-ttu-id="1ef86-157">Jeder Benutzer muss über eine aktive Microsoft 365-oder Office 365-Lizenz für [einen berechtigten Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) verfügen und muss eine Teams-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1ef86-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="1ef86-158">Wenn Sie Benutzern eine Teams-Lizenz zuweisen, erhalten Sie Zugriff auf Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="1ef86-159">Sie verwalten die Lizenzen für Teams im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="1ef86-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1ef86-160">Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1ef86-160">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1ef86-161">Wenn Ihre Organisation Skype for Business verwendet und Sie nicht bereit sind, alle Ihre Benutzer in Teams zu verschieben, können Sie Teams für Ihre Mitarbeiter in der First-work-Abteilung aktivieren, die dann Teams neben Skype for Business ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1ef86-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="1ef86-162">In diesem Koexistenzmodus, dem sogenannten " *Inseln*", fungiert jede Client-App als separate Lösung.</span><span class="sxs-lookup"><span data-stu-id="1ef86-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="1ef86-163">Weitere Informationen finden Sie Untergrund Legendes zu [Teams und zur Koexistenz und Interoperabilität von Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="1ef86-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="1ef86-164">Installieren des StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="1ef86-164">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="1ef86-165">Wenn Sie dies noch nicht getan haben, [Installieren Sie das StaffHub PowerShell-Modul](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="1ef86-165">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="1ef86-166">Verknüpfen eines Azure AD-Kontos für StaffHub-Teammitglieder, die nicht über ein Konto verfügen</span><span class="sxs-lookup"><span data-stu-id="1ef86-166">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="1ef86-167">Jedes StaffHub-Teammitglied muss mit einem Azure Active Directory-Konto (Azure AD) verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="1ef86-167">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="1ef86-168">Benutzer in Ihrer Organisation werden nicht mit einem Azure AD-Konto verknüpft, wenn eines der folgenden Szenarien zutrifft:</span><span class="sxs-lookup"><span data-stu-id="1ef86-168">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="1ef86-169">Ein Teambesitzer hat einen Benutzer hinzugefügt, der kein Azure AD-Konto hat.</span><span class="sxs-lookup"><span data-stu-id="1ef86-169">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="1ef86-170">Ein Teambesitzer hat einen Benutzer zu einem StaffHub-Team eingeladen, und dieser Benutzer hat die Einladung nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="1ef86-170">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="1ef86-171">Sie können ein Azure AD-Konto für diese Benutzer verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-171">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="1ef86-172">Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="1ef86-172">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="1ef86-173">Abrufen einer Liste aller Benutzer in StaffHub-Teams mit Teammitgliedern, die nicht mit einem Azure AD-Konto verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="1ef86-173">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="1ef86-174">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="1ef86-174">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="1ef86-175">Verknüpfen des Kontos</span><span class="sxs-lookup"><span data-stu-id="1ef86-175">Link the account</span></span>

<span data-ttu-id="1ef86-176">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1ef86-176">Do one of the following:</span></span>

- <span data-ttu-id="1ef86-177">Konvertieren und Verknüpfen des Kontos</span><span class="sxs-lookup"><span data-stu-id="1ef86-177">Convert and link the account.</span></span>

  <span data-ttu-id="1ef86-178">StaffHub-Teambesitzer und-Manager können ein inaktives Konto konvertieren und es mit einem Azure AD-Konto in StaffHub verknüpfen, indem Sie die e-Mail-Adresse des Benutzers in einen gültigen UPN auf der Seite "StaffHub-Team Einstellungen" ändern.</span><span class="sxs-lookup"><span data-stu-id="1ef86-178">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="1ef86-179">Entfernen Sie das Konto, das nicht verknüpft ist, und fügen Sie es dann mithilfe des UPN erneut hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ef86-179">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="1ef86-180">Führen Sie das Cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) aus, um das nicht bereitgestellte Konto aus dem StaffHub-Team zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-180">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="1ef86-181">Führen Sie das [Add-StaffHubMember-](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) Cmdlet aus, um das Konto mithilfe des UPN dem StaffHub-Team wieder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-181">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="1ef86-182">Entfernen Sie das Unverknüpfte Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="1ef86-182">Remove the unlinked user account.</span></span> <span data-ttu-id="1ef86-183">Verwenden Sie diese Option, damit das Benutzerkonto nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="1ef86-183">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="1ef86-184">Zuweisen der FirstlineWorker-App-Setup Richtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="1ef86-184">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="1ef86-185">Teams umfasst eine integrierte Richtlinie für die FirstlineWorker-APP, die Sie zum Anpassen von Teams verwenden können, um die apps hervorzuheben, die für die ersten Mitarbeiter in Ihrer Organisation am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="1ef86-185">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="1ef86-186">Wenn Sie diese Richtlinie Benutzern zuweisen, werden die apps in der Richtlinie in Teams an die APP-Leiste angeheftet, damit Sie schnell und einfach darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1ef86-186">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="1ef86-187">Andere apps, die zu Teams hinzugefügt wurden, finden Sie in der APP-Leiste, indem Sie auf **... Weitere apps** in den Teams-Desktop-und Webclients und durch wischen im mobilen Team-Client.</span><span class="sxs-lookup"><span data-stu-id="1ef86-187">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="1ef86-188">Standardmäßig umfasst die FirstlineWorker-App-Setup Richtlinie die Aktivitäten, Schichten, Chats und Anruf-apps.</span><span class="sxs-lookup"><span data-stu-id="1ef86-188">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="1ef86-189">Eine schrittweise Anleitung zum Zuweisen der FirstlineWorker-App-Setup Richtlinie für Benutzer finden Sie unter [Verwenden der FirstlineWorker-App-Setup Richtlinie zum Anheften von Schichten an Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="1ef86-189">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="1ef86-190">Nachdem Sie eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis Sie wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="1ef86-190">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="1ef86-191">Wir empfehlen, diesen Schritt mindestens eine Woche abzuschließen, bevor Sie Ihre StaffHub-Teams und-Benutzer in Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-191">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="1ef86-192">Wenn Benutzer in Teams angemeldet sind, vergewissern Sie sich, dass Sie die Schicht-App anzeigen und darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1ef86-192">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="1ef86-193">Sie können auch benutzerdefinierte App-Setup Richtlinien erstellen und die Einstellungen in der globalen App-Setup Richtlinie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-193">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="1ef86-194">Weitere Informationen finden Sie unter [Verwalten von App-Setup Richtlinien in Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1ef86-194">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="1ef86-195">Onboard-Benutzer für Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-195">Onboard users to Teams</span></span>

<span data-ttu-id="1ef86-196">Stellen Sie im Rahmen ihrer Onboarding-Strategie Schulungen und Anleitungen für Benutzer bereit, die Ihnen helfen, sich mit Teams vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-196">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="1ef86-197">Geben Sie die folgenden Ressourcen für die Benutzer frei, damit Sie wissen, wo Sie Teams-Clients, Schulungen und Support erhalten:</span><span class="sxs-lookup"><span data-stu-id="1ef86-197">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="1ef86-198">Teams-Webclient</span><span class="sxs-lookup"><span data-stu-id="1ef86-198">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="1ef86-199">Downloadlinks für Desktop- und mobile Clients</span><span class="sxs-lookup"><span data-stu-id="1ef86-199">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="1ef86-200">Teams-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="1ef86-200">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="1ef86-201">Teams-Hilfedokumentation</span><span class="sxs-lookup"><span data-stu-id="1ef86-201">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="1ef86-202">Anleitungen zum Bereitstellen von Teams und zur Einführung von Teams finden Sie unter so wird es [gemacht: Rollout von Teams](../../How-to-roll-out-teams.md) und über [nehmen von Teams](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="1ef86-202">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="1ef86-203">Durchführen eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="1ef86-203">Conduct a pilot</span></span>

<span data-ttu-id="1ef86-204">Wir empfehlen, dass Sie zunächst zwei oder drei StaffHub-Teams für eine ausgewählte Gruppe von Early Adopters verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-204">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="1ef86-205">Durch das Ausführen eines Pilotprojekts können Sie Ihren Übergangsplan verfeinern und sicherstellen, dass Sie bereit sind, alle StaffHub-Teams Ihrer Organisation in Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-205">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="1ef86-206">Es werden auch Champions identifiziert, die Ihnen bei der Einführung in Ihrer Organisation behilflich sein können.</span><span class="sxs-lookup"><span data-stu-id="1ef86-206">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="1ef86-207">Wenn Sie ein kleines Unternehmen sind, das keinen Phasen orientierten Ansatz benötigt, sind die Schritte in diesem Abschnitt möglicherweise alles, was Sie benötigen, um von StaffHub zu Teams zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="1ef86-207">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="1ef86-208">Ermitteln von Pilot Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-208">Identify pilot teams</span></span>

<span data-ttu-id="1ef86-209">Erreichen Sie zwei oder drei Pilot Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-209">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="1ef86-210">Alle Teammitglieder sollten sich verpflichten, mithilfe von Schichten in Teams ihre Zeitpläne zu verwalten und miteinander zu kommunizieren und zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-210">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="1ef86-211">Identifizieren von Team Champions</span><span class="sxs-lookup"><span data-stu-id="1ef86-211">Identify team champions</span></span>

<span data-ttu-id="1ef86-212">Ermitteln Sie Champions in Pilot Teams, und geben Sie Sie zur Evangelisierung von Schichten ein.</span><span class="sxs-lookup"><span data-stu-id="1ef86-212">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="1ef86-213">Team-Champions sind leidenschaftlich über das, was Sie tun, indem Sie Ihre eigenen Erfahrungen austauschen, um den Teammitgliedern Support und Hilfestellung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-213">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="1ef86-214">Team Champions können Teambesitzer oder Manager sein.</span><span class="sxs-lookup"><span data-stu-id="1ef86-214">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="1ef86-215">Team-Champions sollten sicherstellen, dass die Teammitglieder eingerichtet werden, indem Sie Zeit für jeden einrichten, um [Teams-Clients zu erhalten](../../get-clients.md), sich bei Teams anzumelden und deren Zeitpläne in Schichten zu überprüfen und mit anderen zu chatten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-215">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="1ef86-216">Benutzer, die bereits mit StaffHub vertraut sind, werden in Schichten schnell in Betrieb sein.</span><span class="sxs-lookup"><span data-stu-id="1ef86-216">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="1ef86-217">Sie können auch auf die [Schalt Schicht Hilfe](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) verweisen, um weitere Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-217">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="1ef86-218">Verschieben eines StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-218">Move a StaffHub team</span></span>

<span data-ttu-id="1ef86-219">Führen Sie die folgenden Schritte aus, um ein StaffHub-Team gleichzeitig zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-219">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="1ef86-220">Wir empfehlen diesen Ansatz für Ihre Pilot Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-220">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="1ef86-221">Wenn Sie zu einem späteren Zeitpunkt alle StaffHub-Teams Ihrer Organisation verschieben möchten, lesen Sie [Verschieben von StaffHub Teams](#move-your-staffhub-teams) nach Schritten zum Verschieben mehrerer Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-221">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="1ef86-222">Führen Sie die folgenden Schritte aus, um ein StaffHub-Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-222">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="1ef86-223">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ef86-223">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="1ef86-224">Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn Sie eine Anfrage einreichen, um ein StaffHub-Team in Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-224">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="1ef86-225">Führen Sie die folgenden Schritte aus, um den Status einer Verschiebungsanforderung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-225">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="1ef86-226">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ef86-226">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="1ef86-227">Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn ein Schritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ef86-227">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="1ef86-228">Verschieben von Dateien aus einem StaffHub-Team in Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-228">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="1ef86-229">Dieser Schritt gilt nur, wenn das StaffHub-Team, das Sie in Teams verschoben haben, Dateien enthält, die Sie auch in Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-229">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="1ef86-230">Sie können Dateien direkt in SharePoint Online oder mithilfe von PowerShell verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-230">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="1ef86-231">In SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1ef86-231">In SharePoint Online</span></span>

<span data-ttu-id="1ef86-232">Informationen finden Sie unter [Verschieben von Dateien in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="1ef86-232">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="1ef86-233">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ef86-233">Using PowerShell</span></span>

<span data-ttu-id="1ef86-234">Laden Sie die [SharePoint Online-Verwaltungsshell](https://www.microsoft.com/download/details.aspx?id=35588)herunter, und installieren Sie Sie, falls noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-234">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="1ef86-235">Sie enthält die Cmdlets, die Sie zum Verschieben von Dateien benötigen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-235">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="1ef86-236">Verwenden Sie das Cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) zum Herstellen einer Verbindung mit der SharePoint Online-Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="1ef86-236">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="1ef86-237">Verwenden Sie für jede Datei, die Sie von StaffHub in Teams verschieben möchten, das Cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) , um die Datei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-237">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="1ef86-238">Wenn Sie mehrere Dateien verschieben möchten, durchlaufen Sie die Dateien, und führen Sie den zweiten Befehl auf der Schleife aus.</span><span class="sxs-lookup"><span data-stu-id="1ef86-238">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="1ef86-239">Sie müssen den ersten Befehl nicht wiederholen, wenn die Sitzung aktiv bleibt.</span><span class="sxs-lookup"><span data-stu-id="1ef86-239">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="1ef86-240">Gehen Sie über ihr Pilotprojekt hinaus und verschieben Sie alle StaffHub-Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-240">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="1ef86-241">Sensibilisieren</span><span class="sxs-lookup"><span data-stu-id="1ef86-241">Raise awareness</span></span>

<span data-ttu-id="1ef86-242">Wenn Sie bereit sind, über Ihre Pilot Teams hinauszugehen und die StaffHub-Teams Ihrer Organisation in Teams zu verschieben, ist es wichtig, zunächst die Änderung in Ihrer Organisation zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="1ef86-242">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="1ef86-243">Informieren Sie sich über Schichten und den Übergang zu Teams, um das Bewusstsein zu schärfen, Spannung zu wecken und die Akzeptanz zu steigern.</span><span class="sxs-lookup"><span data-stu-id="1ef86-243">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="1ef86-244">Verschieben Ihrer StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-244">Move your StaffHub teams</span></span>

<span data-ttu-id="1ef86-245">Führen Sie die folgenden Schritte aus, um StaffHub Teams massenhaft zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-245">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="1ef86-246">Sie können auswählen, ob Sie alle StaffHub-Teams Ihrer Organisation verschieben oder bestimmte StaffHub-Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1ef86-246">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="1ef86-247">Wenn Sie StaffHub Teams einzeln verschieben möchten, lesen Sie [Verschieben eines StaffHub](#move-a-staffhub-team)-Teams.</span><span class="sxs-lookup"><span data-stu-id="1ef86-247">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="1ef86-248">Verschieben aller StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-248">Move all StaffHub teams</span></span>

<span data-ttu-id="1ef86-249">Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Teams in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-249">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="1ef86-250">Führen Sie dann die folgenden Schritte aus, um alle Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-250">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="1ef86-251">Hier ist ein Beispiel für die Antwort.</span><span class="sxs-lookup"><span data-stu-id="1ef86-251">Here's an example of the response.</span></span>

<span data-ttu-id="1ef86-252">Für alle Teams, die bereits in Teams verschoben oder bereits in Teams vorhanden sind, ist die JobID "Null", da ein Auftrag nicht gesendet werden muss, um das Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-252">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="1ef86-253">Verschieben spezifischer StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-253">Move specific StaffHub teams</span></span>

<span data-ttu-id="1ef86-254">Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Team-IDs in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-254">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="1ef86-255">Wählen Sie in den Ergebnissen, `Get-StaffHubteamsForTenant` die von dem zuvor ausgeführten Cmdlet zurückgegeben wurden, die Team-IDs aus, die Sie verschieben möchten, und fügen Sie Sie dann einer CSV-Datei (Comma-Separated Values, CSV) hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ef86-255">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="1ef86-256">Im folgenden finden Sie ein Beispiel dafür, wie die CSV-Datei formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ef86-256">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="1ef86-257">ID</span><span class="sxs-lookup"><span data-stu-id="1ef86-257">Id</span></span>  |
|---------|
|<span data-ttu-id="1ef86-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="1ef86-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="1ef86-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="1ef86-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="1ef86-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="1ef86-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="1ef86-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="1ef86-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="1ef86-262">Nachdem Sie die CSV-Datei erstellt haben, führen Sie die folgenden Schritte aus, um die in der CSV-Datei angegebenen Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1ef86-262">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="1ef86-263">Überprüfen, ob Ihre StaffHub-Teams in Teams umgezogen sind</span><span class="sxs-lookup"><span data-stu-id="1ef86-263">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="1ef86-264">Führen Sie die folgenden Schritte aus, um eine Liste aller Teams in Schichten in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-264">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="1ef86-265">Verschieben von Dateien aus ihren StaffHub-Teams in Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-265">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="1ef86-266">Wenn die von Ihnen verschobenen StaffHub-Teams Dateien enthalten, die Sie auch in Teams verschieben möchten, lesen Sie [Verschieben von Dateien aus einem StaffHub-Team in Teams](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="1ef86-266">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="1ef86-267">Überwachen der Verwendung von Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-267">Monitor Teams usage</span></span>

<span data-ttu-id="1ef86-268">Verwendungsberichte können Ihnen dabei helfen, Nutzungsmuster besser zu verstehen und Ihnen Einblicke zu geben, wo Sie die Schulungs-und Kommunikationsaktivitäten in Ihrer Organisation priorisieren können.</span><span class="sxs-lookup"><span data-stu-id="1ef86-268">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="1ef86-269">Sie können Berichte ausführen, die Ihnen die Verwendung der allgemeinen Teams, die Art der Aktivitäten, die Benutzer in Teams ausführen, die Art und Weise, wie Benutzer eine Verbindung mit Teams herstellen, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="1ef86-269">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="1ef86-270">Weitere Informationen finden Sie unter [Teams-Berichterstattung im Microsoft Teams Admin Center](../../teams-analytics-and-reports/teams-reporting-reference.md) und [Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="1ef86-270">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1ef86-271">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1ef86-271">Troubleshooting</span></span>

<span data-ttu-id="1ef86-272">**Wenn Sie versuchen, Dateien von StaffHub in Teams zu verschieben, erhalten Sie die Fehlermeldung "Berechtigung verweigert".**</span><span class="sxs-lookup"><span data-stu-id="1ef86-272">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="1ef86-273">Dies kann auftreten, wenn Sie versuchen, Dateien in einer privaten Office 365-Gruppe zu verschieben, in der Sie nicht Mitglied sind.</span><span class="sxs-lookup"><span data-stu-id="1ef86-273">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="1ef86-274">Wenn dies der Fall ist, verwenden Sie das [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) -Cmdlet, um sich selbst dem StaffHub-Team hinzuzufügen, und verschieben Sie dann die Dateien.</span><span class="sxs-lookup"><span data-stu-id="1ef86-274">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="1ef86-275">Nachdem Sie die Dateien verschoben haben, verwenden Sie das Cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) , um sich selbst aus dem Team zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="1ef86-275">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="1ef86-276">**Wenn Sie versuchen, Dateien aus StaffHub in Teams zu verschieben, erhalten Sie eine Fehlermeldung, die besagt, dass der Ordner "Allgemein" nicht vorhanden ist.**</span><span class="sxs-lookup"><span data-stu-id="1ef86-276">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="1ef86-277">Führen Sie den folgenden Befehl aus, um den Ordner "Allgemein" zu SharePoint hinzuzufügen, und versuchen Sie es dann erneut:</span><span class="sxs-lookup"><span data-stu-id="1ef86-277">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="1ef86-278">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1ef86-278">Related topics</span></span>
- [<span data-ttu-id="1ef86-279">Bereitstellen von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-279">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="1ef86-280">Microsoft StaffHub soll eingestellt werden</span><span class="sxs-lookup"><span data-stu-id="1ef86-280">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="1ef86-281">Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ef86-281">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="1ef86-282">StaffHub PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="1ef86-282">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
