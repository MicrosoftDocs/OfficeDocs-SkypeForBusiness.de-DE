---
title: Verschieben Ihrer StaffHub-Teams in Shifts in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Ihre Microsoft StaffHub-Teams verschieben und in Microsoft Teams Daten in Shifts planen.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf9776dbf5a5992354f542436b4904d53d58508
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142045"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="6ea4e-103">Verschieben Ihrer Microsoft StaffHub-Teams in Shifts in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-103">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ea4e-104">Am 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="6ea4e-105">Wir bauen StaffHub-Funktionen in Microsoft Teams ein.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="6ea4e-106">Heute umfasst Microsoft Teams die App "Shifts" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="6ea4e-107">StaffHub wird am 1. Oktober 2019 für alle Benutzer eingestellt.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="6ea4e-108">Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="6ea4e-109">Weitere Informationen finden Sie unter [Microsoft StaffHub soll eingestellt werden](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="6ea4e-110">Die Shifts-App in Microsoft Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und sämtlichen von Schichttauschaktivitäten und -ausfällen auf täglicher Basis.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="6ea4e-111">Teammitglieder können direkt in der App und von allen ihren Geräten aus auf Ihren Zeitplan und die Schichtinformationen zugreifen, um Einstellungen festzulegen, ihre Zeitpläne zu verwalten und arbeitsfreie Zeit zu beantragen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="6ea4e-112">Dieser Artikel beschreibt, wie Sie die StaffHub-Teams Ihrer Organisation verschieben und Daten für Shifts in Microsoft Teams planen können.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="6ea4e-113">Inhalt:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-113">It covers:</span></span>

- [<span data-ttu-id="6ea4e-114">Was Sie über den Wechsel zu Microsoft Teams wissen müssen</span><span class="sxs-lookup"><span data-stu-id="6ea4e-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="6ea4e-115">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="6ea4e-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="6ea4e-116">Durchführen eines Pilotversuches</span><span class="sxs-lookup"><span data-stu-id="6ea4e-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- <span data-ttu-id="6ea4e-117">[Gehen Sie über Ihren Pilotversuch hinaus und verschieben Sie alle StaffHub-Teams.](#go-beyond-your-pilot-and-move-all-staffhub-teams) </span><span class="sxs-lookup"><span data-stu-id="6ea4e-117">[Go beyond your pilot and move all StaffHub teams](#go-beyond-your-pilot-and-move-all-staffhub-teams)</span></span>
- [<span data-ttu-id="6ea4e-118">Überwachung der Team-Nutzung</span><span class="sxs-lookup"><span data-stu-id="6ea4e-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="6ea4e-119">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="6ea4e-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="6ea4e-120">Ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub-Teams oder ein großes Unternehmen mit Hunderten von StaffHub-Teams sind, hier finden Sie den Administratoren-Leitfaden, den Sie benötigen, um Ihren Wechsel zu Microsoft Teams erfolgreich zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="6ea4e-121">Sie müssen ein globaler Administrator sein, um die Schritte in diesem Artikel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="6ea4e-122">Wenn Sie dies noch nicht getan haben, schauen Sie sich die [StaffHub Deaktivierung häufig gestellte Fragen](microsoft-staffhub-to-be-retired.md) an, um Antworten auf Ihre Fragen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="6ea4e-123">Was Sie über den Wechsel zu Microsoft Teams wissen müssen</span><span class="sxs-lookup"><span data-stu-id="6ea4e-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="6ea4e-124">Zeitpunkt für den Wechsel zu Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-124">When to move to Teams</span></span>

<span data-ttu-id="6ea4e-125">Am 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="6ea4e-126">Wir empfehlen Ihnen, mit der Verwendung von Microsoft Teams noch heute zu beginnen und mit der Migration der Microsoft Teams und Benutzer Ihrer Organisation von StaffHub zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="6ea4e-127">Da die Zeitplanverwaltung die am häufigsten verwendete Funktion in StaffHub ist, empfehlen wir Ihnen, die Shifts-App in Microsoft Teams zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="6ea4e-128">Was zu Microsoft Teams transferiert wird</span><span class="sxs-lookup"><span data-stu-id="6ea4e-128">What is moved to Teams</span></span>

<span data-ttu-id="6ea4e-129">Wenn Sie ein StaffHub-Team verschieben, werden Teammitgliedschaft, Benutzerdetails, Team-Zeitpläne und Chatdaten zu Teams verschoben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="6ea4e-130">Dateien werden nicht verschoben, wenn Sie ein StaffHub-Team verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="6ea4e-131">Wenn ein StaffHub-Team Dateien enthält, die Sie ebenfalls zu Teams verschieben möchten, können Sie diese in einem separaten Schritt verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="6ea4e-132">Jedes StaffHub-Team benötigt eine entsprechende Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="6ea4e-133">Wenn einem StaffHub-Team keine Office 365-Gruppe zugeordnet ist, wird automatisch eine erstellt, damit die Umstellung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="6ea4e-134">Aufgrund des Unterschieds in der Team- und Gruppennamensvergabe zwischen Microsoft Teams und StaffHub wird in Microsoft Teams möglicherweise ein anderer Teamname angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="6ea4e-135">Während Sie Microsoft Teams von StaffHub zu Microsoft Teams migrieren, haben die Benutzer keinen Zugriff mehr auf ihre Zeitpläne in StaffHub und werden zu Shifts in Microsoft Teams weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="6ea4e-136">Wir empfehlen Ihnen, diese Änderung in Ihrer Organisation zu kommunizieren, um Störungen zu minimieren und die Benutzer zu ermutigen, Microsoft Teams zu implementieren und zu testen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="6ea4e-137">Wenn Sie Azure AD Premium haben, können Sie [einen Bericht ausführen](run-report-to-show-staffhub-usage.md), um eine Liste der StaffHub-Benutzer in Ihrer Organisation zu erhalten, die über diese Änderung informiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="6ea4e-138">Es gibt keine Rollback-Option, nachdem Sie ein StaffHub-Team in Microsoft Teams verschoben haben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="6ea4e-139">Benutzererfahrung beim Wechsel eines Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-139">User experience when you move a team</span></span>

<span data-ttu-id="6ea4e-140">Es gibt minimale Ausfallzeiten (weniger als eine Sekunde, wenn überhaupt) für Benutzer, wenn ihr Team von StaffHub auf Shifts in Microsoft Teams umgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="6ea4e-141">Benutzer können StaffHub weiterhin verwenden, bis der Wechsel zu Microsoft Teams abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="6ea4e-142">Wenn der Wechsel abgeschlossen ist, sehen die Teammitglieder eine Meldung, die sie darüber informiert, dass sie damit beginnen müssen, Shifts in Microsoft Teams zu verwenden, um auf ihren Teamplan zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="6ea4e-143">Hier ist ein Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Microsoft Teams verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="6ea4e-144">![Beispiel für die Nachricht, die Benutzer sehen.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Microsoft Teams verschoben wurde")</span><span class="sxs-lookup"><span data-stu-id="6ea4e-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="6ea4e-145">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="6ea4e-145">Prepare Schema</span></span>

<span data-ttu-id="6ea4e-146">Hier erfahren Sie, wie Sie sich auf den Wechsel zu Microsoft Teams vorbereiten können.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="6ea4e-147">Überprüfen Sie, ob die erforderlichen Komponenten erfüllt sind</span><span class="sxs-lookup"><span data-stu-id="6ea4e-147">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="6ea4e-148">Bevor Sie ein StaffHub-Team in Microsoft Teams verschieben, müssen Sie auf Folgendes achten:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="6ea4e-149">Der angemeldete Benutzer ist ein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="6ea4e-150">Microsoft Teams ist für alle Benutzer im Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="6ea4e-151">Die Erstellung von Office 365-Gruppen ist im Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="6ea4e-152">Die StaffHub TeamID ist gültig.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="6ea4e-153">Das StaffHub-Team setzt sich aus Mitgliedern zusammen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="6ea4e-154">Alle StaffHub-Teammitglieder sind mit einem Azure AD-Konto verknüpft.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="6ea4e-155">Wenn diese Voraussetzungen nicht erfüllt sind, schlägt der Umstellungsauftrag fehl.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="6ea4e-156">Zuweisen von Microsoft Teams-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="6ea4e-156">Assign Teams licenses</span></span>

<span data-ttu-id="6ea4e-157">Jeder Benutzer muss über eine aktive Microsoft 365- oder Office 365-Lizenz aus [einem berechtigten Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) verfügen und eine Teamlizenz zugewiesen bekommen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="6ea4e-158">Die Zuweisung einer Teams-Lizenz an Benutzer ermöglicht ihnen den Zugriff auf Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="6ea4e-159">Sie verwalten Microsoft Teams-Lizenzen im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6ea4e-160">Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-160">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6ea4e-161">Wenn Ihre Organisation Skype for Business verwendet und Sie nicht bereit sind, alle Ihre Benutzer in Microsoft Teams zu verschieben, können Sie Microsoft Teams für Ihre Mitarbeiter in Service und Produktion aktivieren, die dann Microsoft Teams neben Skype for Business ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="6ea4e-162">In diesem Koexistenzmodus, der als *Inseln* genannt wird, arbeitet jede Client-App als separate Lösung.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="6ea4e-163">Weitere Informationen finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="6ea4e-164">Installieren der Vorabversion des StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="6ea4e-164">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="6ea4e-165">[Installieren Sie die Vorabversion des StaffHub PowerShell-Moduls](install-the-staffhub-powershell-module.md), sofern noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-165">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

<span data-ttu-id="6ea4e-166">Sie müssen die Vorabversion des-Moduls installiert haben, um Ihre StaffHub-Teams in Microsoft Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-166">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="6ea4e-167">Verknüpfen eines Azure AD-Kontos für StaffHub-Teammitglieder, die über keines verfügen</span><span class="sxs-lookup"><span data-stu-id="6ea4e-167">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="6ea4e-168">Jedes StaffHub-Teammitglied muss mit einem Azure Active Directory-Konto (Azure AD) verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-168">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="6ea4e-169">Benutzer in Ihrer Organisation werden nicht mit einem Azure AD-Konto verknüpft, wenn eines der folgenden Szenarien zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-169">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="6ea4e-170">Ein Teambesitzer hat einen Benutzer hinzugefügt, der über kein Azure AD-Konto verfügt.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-170">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="6ea4e-171">Ein Teambesitzer hat einen Benutzer zu einem StaffHub-Team eingeladen, und der Benutzer hat die Einladung nicht angenommen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-171">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="6ea4e-172">Sie können eine Verknüpfung mit einem Azure AD-Konto für diese Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-172">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="6ea4e-173">Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-173">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="6ea4e-174">Erhalten Sie eine Liste aller Benutzer in StaffHub-Teams, die Teammitglieder haben, die nicht mit einem Azure AD-Konto verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-174">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="6ea4e-175">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-175">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="6ea4e-176">Verknüpfen des Kontos</span><span class="sxs-lookup"><span data-stu-id="6ea4e-176">Link the account</span></span>

<span data-ttu-id="6ea4e-177">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-177">Do one of the following:</span></span>

- <span data-ttu-id="6ea4e-178">Konvertieren Sie das Konto, und verknüpfen Sie es.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-178">Convert and link the account.</span></span>

  <span data-ttu-id="6ea4e-179">StaffHub-Teambesitzer und Manager können ein inaktives Konto konvertieren und mit einem Azure AD-Konto in StaffHub verknüpfen, indem sie die E-Mail-Adresse des Benutzers auf der StaffHub Team-Einstellungen-Seite in einen gültigen UPN ändern.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-179">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="6ea4e-180">Entfernen Sie das nicht verknüpfte Konto und fügen Sie es dann unter Verwendung des UPN erneut hinzu.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-180">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="6ea4e-181">Führen Sie das Cmdlet[Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember?view=staffhub-ps) aus, um das nicht bereitgestellte Konto aus dem StaffHub-Team zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-181">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="6ea4e-182">Führen Sie das Cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) aus, um das Konto unter Verwendung des UPN erneut zum StaffHub-Team hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-182">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="6ea4e-183">Entfernen Sie das nicht verknüpfte Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-183">Remove the unlinked user account.</span></span> <span data-ttu-id="6ea4e-184">Verwenden Sie diese Option, wenn das Benutzerkonto nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-184">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="6ea4e-185">Weisen Sie Benutzern die FirstlineWorker App-Setup-Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-185">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="6ea4e-186">Teams enthält eine eingebaute FirstlineWorker-App-Setup-Richtlinie, mit der Sie Microsoft Teams anpassen können, um die Anwendungen hervorzuheben, die für die Mitarbeiter in Service und Produktion in Ihrer Organisation am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-186">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="6ea4e-187">Wenn Sie diese Richtlinie Benutzern zuweisen, werden die Anwendungen in der Richtlinie an die App-Leiste in Microsoft Teams angeheftet, um einen schnellen und einfachen Zugriff zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-187">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="6ea4e-188">Weitere Apps, die in Microsoft Teams hinzugefügt wurden, finden Sie in der App-Leiste, indem Sie auf **...Weitere Apps** in den Teams Desktop- und Webclients klicken und durch das Wischen nach oben im Microsoft Teams Mobile Client.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-188">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="6ea4e-189">Standardmäßig beinhaltet die FirstlineWorker App-Setup-Richtlinie die Apps für Aktivität, Shifts, Chat und Anrufe.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-189">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="6ea4e-190">Weitere Informationen zum Zuweisen der FirstlineWorker-App-Setup-Richtlinie an Benutzer finden Sie unter [Verwenden der FirstlineWorker-App-Setup-Richtlinie zum Anhäften von Shifts an Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-190">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="6ea4e-191">Nachdem Sie eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-191">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="6ea4e-192">Wir empfehlen Ihnen, diesen Schritt mindestens eine Woche vor dem Wechsel Ihrer StaffHub-Teams und Benutzer in Teams durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-192">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="6ea4e-193">Wenn Benutzer in Teams sind, bestätigen Sie, dass sie die Shifts-App sehen und darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-193">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="6ea4e-194">Sie können auch benutzerdefinierte App-Setup-Richtlinien erstellen und die Einstellungen in der globalen App-Setup-Richtlinie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-194">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="6ea4e-195">Weitere Informationen finden Sie unter [Verwalten von App-Setup-Richtlinien in Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-195">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="6ea4e-196">Benutzer in Teams einbinden</span><span class="sxs-lookup"><span data-stu-id="6ea4e-196">Onboard users to Teams</span></span>

<span data-ttu-id="6ea4e-197">Als Teil Ihrer Onboarding-Strategie bieten Sie Schulungen und Anleitungen für Benutzer an, die diesen helfen, sich mit Teams vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-197">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="6ea4e-198">Geben Sie die folgenden Ressourcen an Benutzer weiter, damit sie wissen, wo sie Team-Clients, Schulungen und Support erhalten:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-198">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="6ea4e-199">Teams-Webclient</span><span class="sxs-lookup"><span data-stu-id="6ea4e-199">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="6ea4e-200">Downloadlinks für Desktop- und mobile Clients</span><span class="sxs-lookup"><span data-stu-id="6ea4e-200">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="6ea4e-201">Teams-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="6ea4e-201">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="6ea4e-202">Teams-Hilfedokumentation</span><span class="sxs-lookup"><span data-stu-id="6ea4e-202">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="6ea4e-203">Anleitungen zur Bereitstellung von Teams und zur Förderung der Teams-Akzeptanz finden Sie unter [Wie Sie Teams einführen](../../How-to-roll-out-teams.md) und [Teams übernehmen können](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-203">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="6ea4e-204">Durchführen eines Pilotversuches</span><span class="sxs-lookup"><span data-stu-id="6ea4e-204">Conduct a user pilot</span></span>

<span data-ttu-id="6ea4e-205">Wir empfehlen Ihnen, zunächst zwei oder drei StaffHub-Teams für eine ausgewählte Gruppe von Erstanwendern zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-205">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="6ea4e-206">Die Durchführung eines Pilotversuchs hilft Ihnen, Ihren Migrationsplan zu verfeinern und sicherzustellen, dass Sie bereit sind, alle StaffHub-Teams Ihrer Organisation in Teams zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-206">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="6ea4e-207">Es werden auch Experten identifiziert, die dazu beitragen können, die Akzeptanz in Ihrer Organisation zu steigern.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-207">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="6ea4e-208">Wenn Sie ein kleines Unternehmen sind, das keinen mehrstufigen Ansatz benötigt, reichen die Schritte in diesem Abschnitt aus, um den Wechsel von StaffHub zu Teams zu realisieren.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-208">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="6ea4e-209">Auswählen der Pilotteams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-209">Identify pilot teams</span></span>

<span data-ttu-id="6ea4e-210">Identifizieren Sie zwei oder drei Pilotteams.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-210">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="6ea4e-211">Alle Teammitglieder sollten sich verpflichten, Shifts in Teams zu verwenden, um ihre Zeitpläne zu verwalten und miteinander zu kommunizieren und zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-211">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="6ea4e-212">Auswählen der Teamexperten</span><span class="sxs-lookup"><span data-stu-id="6ea4e-212">Identify team champions</span></span>

<span data-ttu-id="6ea4e-213">Suchen Sie über Pilotteams hinweg Experten aus, und fordern Sie diese auf, sich für die Akzeptanz von Shifts einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-213">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="6ea4e-214">Teamexperten sind von ihrer Arbeit begeistert und teilen ihre eigenen Erfahrungen, um den Teammitgliedern Unterstützung und Beratung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-214">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="6ea4e-215">Teamexperten können Teambesitzer oder Manager sein.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-215">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="6ea4e-216">Teamexperten sollten sicherstellen, dass die Teammitglieder so eingerichtet werden, dass jeder Zeit hat, um [Team-Clients zu erhalten](../../get-clients.md), sich bei Teams anzumelden und ihre Zeitpläne in Shifts zu überprüfen und mit einander zu chatten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-216">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="6ea4e-217">Benutzer, die bereits mit StaffHub vertraut sind, werden in Shifts schnell produktiv sein.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-217">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="6ea4e-218">Sie können sie auch auf die [Shifts Hilfe](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) verweisen, um zusätzliche Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-218">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="6ea4e-219">Verschieben eines StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-219">Move a StaffHub team</span></span>

<span data-ttu-id="6ea4e-220">Führen Sie diese Schritte aus, um ein StaffHub-Team nach dem anderen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-220">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="6ea4e-221">Wir empfehlen diesen Ansatz für Ihre Pilotteams.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-221">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="6ea4e-222">Wenn Sie später bereit sind, alle StaffHub-Teams Ihrer Organisation zu verschieben, finden Sie unter [Verschieben Sie Ihre StaffHub-Teams](#move-your-staffhub-teams) Informationen, wie Sie mehrere Teams auf einmal verschieben können.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-222">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="6ea4e-223">Führen Sie die folgenden Schritte aus, um ein StaffHub-Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-223">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="6ea4e-224">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-224">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="6ea4e-225">Hier ist ein Beispiel für die Antwort, die Sie erhalten, wenn Sie eine Anfrage senden, ein StaffHub-Team an Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-225">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="6ea4e-226">Um den Status einer Migration zu überprüfen, führen Sie Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-226">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="6ea4e-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-227">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="6ea4e-228">Hier ist ein Beispiel für die Antwort, die Sie erhalten, wenn eine Migration ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-228">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="6ea4e-229">Dateien von einem StaffHub-Team in Teams verschieben</span><span class="sxs-lookup"><span data-stu-id="6ea4e-229">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="6ea4e-230">Dieser Schritt gilt nur, wenn das StaffHub-Team, das Sie in Teams verschoben haben, Dateien enthält, die Sie auch in Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-230">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="6ea4e-231">Sie können Dateien direkt in SharePoint Online oder mit PowerShell verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-231">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="6ea4e-232">In SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6ea4e-232">In SharePoint Online</span></span>

<span data-ttu-id="6ea4e-233">Hier finden Sie Informationen zum[Verschieben von Dateien in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-233">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="6ea4e-234">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ea4e-234">Using Windows PowerShell</span></span>

<span data-ttu-id="6ea4e-235">Laden Sie [SharePoint Online Verwaltungsshell](https://www.microsoft.com/download/details.aspx?id=35588) herunter und installieren Sie es, falls noch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-235">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="6ea4e-236">Es enthält die Cmdlets, die Sie zum Verschieben von Dateien benötigen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-236">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="6ea4e-237">Verwenden Sie das Cmdlet [Connect-PnPOnline,](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) um eine Verbindung mit der SharePoint Online-Teamwebsite herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-237">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="6ea4e-238">Verwenden Sie für jede Datei, die Sie von StaffHub in Teams verschieben möchten, das Cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile), um die Datei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-238">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="6ea4e-239">Um mehrere Dateien zu verschieben, führen Sie eine Schleife über die Dateien und führen Sie den zweiten Befehl auf der Schleife aus.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-239">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="6ea4e-240">Sie müssen den ersten Befehl nicht wiederholen, wenn die Sitzung aktiv bleibt.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-240">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="6ea4e-241">Gehen Sie über Ihren Piloteversuch hinaus und verschieben Sie alle StaffHub-Teams.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-241">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="6ea4e-242">Bewusstsein schaffen</span><span class="sxs-lookup"><span data-stu-id="6ea4e-242">Raise awareness</span></span>

<span data-ttu-id="6ea4e-243">Wenn Sie bereit sind, über Ihre Pilotteams hinauszugehen und die StaffHub-Teams Ihrer Organisation in Teams zu verschieben, ist es wichtig, die Veränderung zunächst in Ihrer Organisation zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-243">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="6ea4e-244">Verbreiten Sie Informationen über Shifts und den Wechsel zu Teams, um das Bewusstsein zu erhöhen, Begeisterung zu erzeugen und die Akzeptanz zu steigern.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-244">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="6ea4e-245">Verschieben Sie Ihre StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-245">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

<span data-ttu-id="6ea4e-246">Verwenden Sie diese Schritte, um StaffHub-Teams massenhaft zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-246">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="6ea4e-247">Sie können wählen, ob Sie alle StaffHub-Teams Ihrer Organisation oder einzelne StaffHub-Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-247">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="6ea4e-248">Wenn Sie StaffHub-Teams einzeln verschieben möchten, lesen Sie bitte den Abschnitt [Ein StaffHub-Teams verschieben](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-248">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="6ea4e-249">Alle StaffHub-Teams verschieben</span><span class="sxs-lookup"><span data-stu-id="6ea4e-249">Move all StaffHub teams</span></span>

<span data-ttu-id="6ea4e-250">Führen Sie den folgenden Befehl aus, um eine Liste aller StaffHub-Teams in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-250">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="6ea4e-251">Führen Sie die folgenden Schritte aus, um alle Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-251">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="6ea4e-252">Hier ist ein Beispiel für die Antwort.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-252">Here's an example of the response.</span></span>

<span data-ttu-id="6ea4e-253">Für jedes Team, das bereits in Teams verlegt wurde oder bereits in Teams existiert, ist die jobId "null", da kein Auftrag eingereicht werden muss, um dieses Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-253">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="6ea4e-254">Verschieben von bestimmten StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-254">Move specific StaffHub teams</span></span>

<span data-ttu-id="6ea4e-255">Führen Sie den folgenden Befehl aus, um eine Liste aller StaffHub-Team-IDs in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-255">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="6ea4e-256">Wählen Sie in den Ergebnissen, die von dem zuvor ausgeführten `Get-StaffHubteamsForTenant`Cmdlet-Befehl angezeigt werden, die Team-IDs aus, die Sie verschieben möchten, und fügen Sie sie dann einer CSV-Datei (comma-separated values) hinzu.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-256">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="6ea4e-257">Hier ist ein Beispiel, wie die CSV-Datei formatiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-257">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="6ea4e-258">Id</span><span class="sxs-lookup"><span data-stu-id="6ea4e-258">ID</span></span>  |
|---------|
|<span data-ttu-id="6ea4e-259">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="6ea4e-259">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="6ea4e-260">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="6ea4e-260">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="6ea4e-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="6ea4e-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="6ea4e-262">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="6ea4e-262">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="6ea4e-263">Nachdem Sie die CSV-Datei erstellt haben, führen Sie Folgendes aus, um die Teams zu verschieben, die Sie in der CSV-Datei angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-263">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="6ea4e-264">Bestätigen Sie, dass Ihre StaffHub-Teams in die Teams migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-264">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="6ea4e-265">Führen Sie die folgenden Befehl aus, um eine Liste aller Teams in Shifts in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-265">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="6ea4e-266">Dateien von Ihren StaffHub-Teams in Microsoft Teams verschieben</span><span class="sxs-lookup"><span data-stu-id="6ea4e-266">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="6ea4e-267">Wenn die StaffHub-Teams, die Sie verschoben haben, Dateien enthalten, die Sie auch in Microsoft Teams verschieben möchten, lesen Sie den Abschnitt [Dateien von einem StaffHub-Team in Microsoft Teams verschieben](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-267">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="6ea4e-268">Überwachung der Teams-Nutzung</span><span class="sxs-lookup"><span data-stu-id="6ea4e-268">Monitor Teams usage</span></span>

<span data-ttu-id="6ea4e-269">Mithilfe von Verwendungsberichten können Sie Verwendungsmuster besser verstehen und Erkenntnisse gewinnen, die Sie zur Priorisierung von Schulungs- und Kommunikationsinitiativen in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-269">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="6ea4e-270">Sie können Berichte zur Gesamtnutzung von Microsoft Teams, den Arten von Aktivitäten, die Benutzer in Microsoft Teams ausführen, der Art und Weise, wie sich Benutzer mit Teams verbinden, und vielem mehr erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-270">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="6ea4e-271">Weitere Informationen finden Sie unter [Teams-Berichte im Microsoft Teams Admin Center](../../teams-analytics-and-reports/teams-reporting-reference.md)und[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="6ea4e-271">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6ea4e-272">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="6ea4e-272">Troubleshooting</span></span>

<span data-ttu-id="6ea4e-273">**Wenn Sie versuchen, Dateien von StaffHub in Microsoft Teams zu verschieben, erhalten Sie die Fehlermeldung "Berechtigung verweigert".**</span><span class="sxs-lookup"><span data-stu-id="6ea4e-273">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="6ea4e-274">Dies kann vorkommen, wenn Sie versuchen, Dateien in einer privaten Office 365-Gruppe zu verschieben, der Sie nicht angehören.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-274">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="6ea4e-275">Wenn dies der Fall ist, verwenden Sie das Cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember), um sich zum StaffHub-Team hinzuzufügen, und verschieben Sie dann die Dateien.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-275">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="6ea4e-276">Nachdem Sie die Dateien verschoben haben, verwenden Sie das Cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember), um sich aus dem Team zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6ea4e-276">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="6ea4e-277">**Wenn Sie versuchen, Dateien von StaffHub in Microsoft Teams zu verschieben, erhalten Sie eine Fehlermeldung, dass der Ordner „Allgemein“ nicht existiert.**</span><span class="sxs-lookup"><span data-stu-id="6ea4e-277">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="6ea4e-278">Führen Sie den folgenden Befehl aus, um den Ordner „Allgemein“ zu Microsoft Office SharePoint Online hinzuzufügen, und versuchen Sie es dann erneut:</span><span class="sxs-lookup"><span data-stu-id="6ea4e-278">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="6ea4e-279">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6ea4e-279">Related topics</span></span>
- [<span data-ttu-id="6ea4e-280">Bereitstellen von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-280">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="6ea4e-281">Microsoft StaffHub soll eingestellt werden</span><span class="sxs-lookup"><span data-stu-id="6ea4e-281">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="6ea4e-282">Verwalten der Shifts-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ea4e-282">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="6ea4e-283">StaffHub-PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="6ea4e-283">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
