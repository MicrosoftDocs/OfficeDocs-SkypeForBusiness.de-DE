---
title: Verschieben Ihrer StaffHub-Teams in Shifts in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Ihre Microsoft StaffHub-Teams verschieben und in Microsoft Teams Daten in Shifts planen.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780809"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="a801d-103">Verschieben Ihrer Microsoft StaffHub-Teams in Shifts in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-103">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a801d-104">Am 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="a801d-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="a801d-105">Wir bauen StaffHub-Funktionen in Microsoft Teams ein.</span><span class="sxs-lookup"><span data-stu-id="a801d-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="a801d-106">Heute umfasst Microsoft Teams die App "Shifts" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="a801d-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="a801d-107">StaffHub wird am 1. Oktober 2019 für alle Benutzer eingestellt.</span><span class="sxs-lookup"><span data-stu-id="a801d-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="a801d-108">Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet.</span><span class="sxs-lookup"><span data-stu-id="a801d-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="a801d-109">Weitere Informationen finden Sie unter [Microsoft StaffHub soll eingestellt werden](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="a801d-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="a801d-110">Die Shifts-App in Microsoft Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und sämtlichen von Schichttauschaktivitäten und -ausfällen auf täglicher Basis.</span><span class="sxs-lookup"><span data-stu-id="a801d-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="a801d-111">Teammitglieder können direkt in der App und von allen ihren Geräten aus auf Ihren Zeitplan und die Schichtinformationen zugreifen, um Einstellungen festzulegen, ihre Zeitpläne zu verwalten und arbeitsfreie Zeit zu beantragen.</span><span class="sxs-lookup"><span data-stu-id="a801d-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="a801d-112">Dieser Artikel beschreibt, wie Sie die StaffHub-Teams Ihrer Organisation verschieben und Daten für Shifts in Microsoft Teams planen können.</span><span class="sxs-lookup"><span data-stu-id="a801d-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="a801d-113">Inhalt:</span><span class="sxs-lookup"><span data-stu-id="a801d-113">It covers:</span></span>

- [<span data-ttu-id="a801d-114">Was Sie über den Wechsel zu Microsoft Teams wissen müssen</span><span class="sxs-lookup"><span data-stu-id="a801d-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="a801d-115">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="a801d-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="a801d-116">Durchführen eines Pilotversuches</span><span class="sxs-lookup"><span data-stu-id="a801d-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- <span data-ttu-id="a801d-117">[Gehen Sie über Ihren Pilotversuch hinaus und verschieben Sie alle StaffHub-Teams.](#go-beyond-your-pilot-and-move-all-staffhub-teams) </span><span class="sxs-lookup"><span data-stu-id="a801d-117">[Go beyond your pilot and move all StaffHub teams](#go-beyond-your-pilot-and-move-all-staffhub-teams)</span></span>
- [<span data-ttu-id="a801d-118">Überwachung der Team-Nutzung</span><span class="sxs-lookup"><span data-stu-id="a801d-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="a801d-119">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a801d-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="a801d-120">Ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub-Teams oder ein großes Unternehmen mit Hunderten von StaffHub-Teams sind, hier finden Sie den Administratoren-Leitfaden, den Sie benötigen, um Ihren Wechsel zu Microsoft Teams erfolgreich zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="a801d-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="a801d-121">Sie müssen ein globaler Administrator sein, um die Schritte in diesem Artikel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a801d-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="a801d-122">Wenn Sie dies noch nicht getan haben, schauen Sie sich die [StaffHub Deaktivierung häufig gestellte Fragen](microsoft-staffhub-to-be-retired.md) an, um Antworten auf Ihre Fragen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a801d-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="a801d-123">Was Sie über den Wechsel zu Microsoft Teams wissen müssen</span><span class="sxs-lookup"><span data-stu-id="a801d-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="a801d-124">Zeitpunkt für den Wechsel zu Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-124">When to move to Teams</span></span>

<span data-ttu-id="a801d-125">Am 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="a801d-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="a801d-126">Wir empfehlen Ihnen, mit der Verwendung von Microsoft Teams noch heute zu beginnen und mit der Migration der Microsoft Teams und Benutzer Ihrer Organisation von StaffHub zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a801d-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="a801d-127">Da die Zeitplanverwaltung die am häufigsten verwendete Funktion in StaffHub ist, empfehlen wir Ihnen, die Shifts-App in Microsoft Teams zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a801d-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="a801d-128">Was zu Microsoft Teams transferiert wird</span><span class="sxs-lookup"><span data-stu-id="a801d-128">What is moved to Teams</span></span>

<span data-ttu-id="a801d-129">Benutzerdetails, Zeitplaninformationen sowie Chat- und Dateidaten werden zu Microsoft Teams übertragen.</span><span class="sxs-lookup"><span data-stu-id="a801d-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="a801d-130">Dazu gehören Teammitgliedschaft, Teampläne sowie Chats und Dateien der letzten 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="a801d-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="a801d-131">Jedes StaffHub-Team benötigt eine entsprechende Office 365 Gruppe.</span><span class="sxs-lookup"><span data-stu-id="a801d-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="a801d-132">Wenn einem StaffHub-Team keine Office 365-Gruppe zugeordnet ist, wird automatisch eine erstellt, damit die Umstellung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a801d-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="a801d-133">Aufgrund des Unterschieds in der Team- und Gruppennamensvergabe zwischen Microsoft Teams und StaffHub wird in Microsoft Teams möglicherweise ein anderer Teamname angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a801d-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="a801d-134">Während Sie Microsoft Teams von StaffHub zu Microsoft Teams migrieren, haben die Benutzer keinen Zugriff mehr auf ihre Zeitpläne in StaffHub und werden zu Shifts in Microsoft Teams weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a801d-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="a801d-135">Wir empfehlen Ihnen, diese Änderung in Ihrer Organisation zu kommunizieren, um Störungen zu minimieren und die Benutzer zu ermutigen, Microsoft Teams zu implementieren und zu testen.</span><span class="sxs-lookup"><span data-stu-id="a801d-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="a801d-136">Wenn Sie Azure AD Premium haben, können Sie [einen Bericht ausführen](run-report-to-show-staffhub-usage.md), um eine Liste der StaffHub-Benutzer in Ihrer Organisation zu erhalten, die über diese Änderung informiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a801d-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="a801d-137">Es gibt keine Rollback-Option, nachdem Sie ein StaffHub-Team in Microsoft Teams verschoben haben.</span><span class="sxs-lookup"><span data-stu-id="a801d-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="a801d-138">Benutzererfahrung beim Wechsel eines Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-138">User experience when you move a team</span></span>

<span data-ttu-id="a801d-139">Es gibt minimale Ausfallzeiten (weniger als eine Sekunde, wenn überhaupt) für Benutzer, wenn ihr Team von StaffHub auf Shifts in Microsoft Teams umgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a801d-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="a801d-140">Benutzer können StaffHub weiterhin verwenden, bis der Wechsel zu Microsoft Teams abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a801d-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="a801d-141">Wenn der Wechsel abgeschlossen ist, sehen die Teammitglieder eine Meldung, die sie darüber informiert, dass sie damit beginnen müssen, Shifts in Microsoft Teams zu verwenden, um auf ihren Teamplan zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a801d-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="a801d-142">Hier ist ein Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Microsoft Teams verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="a801d-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="a801d-143">![Beispiel für die Nachricht, die Benutzer sehen.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Microsoft Teams verschoben wurde")</span><span class="sxs-lookup"><span data-stu-id="a801d-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="a801d-144">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="a801d-144">Prepare Schema</span></span>

<span data-ttu-id="a801d-145">Hier erfahren Sie, wie Sie sich auf den Wechsel zu Microsoft Teams vorbereiten können.</span><span class="sxs-lookup"><span data-stu-id="a801d-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="a801d-146">Überprüfen Sie, ob die erforderlichen Komponenten erfüllt sind</span><span class="sxs-lookup"><span data-stu-id="a801d-146">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="a801d-147">Bevor Sie ein StaffHub-Team in Microsoft Teams verschieben, müssen Sie auf Folgendes achten:</span><span class="sxs-lookup"><span data-stu-id="a801d-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="a801d-148">Der angemeldete Benutzer ist ein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="a801d-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="a801d-149">Microsoft Teams ist für alle Benutzer im Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a801d-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="a801d-150">Die Erstellung von Office 365-Gruppen ist im Mandanten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a801d-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="a801d-151">Die StaffHub TeamID ist gültig.</span><span class="sxs-lookup"><span data-stu-id="a801d-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="a801d-152">Das StaffHub-Team setzt sich aus Mitgliedern zusammen.</span><span class="sxs-lookup"><span data-stu-id="a801d-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="a801d-153">Alle StaffHub-Teammitglieder sind mit einem Azure AD-Konto verknüpft.</span><span class="sxs-lookup"><span data-stu-id="a801d-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="a801d-154">Wenn diese Voraussetzungen nicht erfüllt sind, schlägt der Umstellungsauftrag fehl.</span><span class="sxs-lookup"><span data-stu-id="a801d-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="a801d-155">Zuweisen von Microsoft Teams-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="a801d-155">Assign Teams licenses</span></span>

<span data-ttu-id="a801d-156">Jeder Benutzer muss über eine aktive Microsoft 365- oder Office 365-Lizenz aus [einem berechtigten Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) verfügen und eine Teamlizenz zugewiesen bekommen.</span><span class="sxs-lookup"><span data-stu-id="a801d-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="a801d-157">Die Zuweisung einer Teams-Lizenz an Benutzer ermöglicht ihnen den Zugriff auf Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a801d-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="a801d-158">Sie verwalten Microsoft Teams-Lizenzen im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="a801d-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a801d-159">Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a801d-159">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a801d-160">Wenn Ihre Organisation Skype for Business verwendet und Sie nicht bereit sind, alle Ihre Benutzer in Microsoft Teams zu verschieben, können Sie Microsoft Teams für Ihre Mitarbeiter in Service und Produktion aktivieren, die dann Microsoft Teams neben Skype for Business ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a801d-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="a801d-161">In diesem Koexistenzmodus, der als *Inseln* genannt wird, arbeitet jede Client-App als separate Lösung.</span><span class="sxs-lookup"><span data-stu-id="a801d-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="a801d-162">Weitere Informationen finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="a801d-162">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="a801d-163">Installieren des StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="a801d-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="a801d-164">Falls noch nicht installiert, [installieren Sie das StaffHub PowerShell-Modul](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="a801d-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="a801d-165">Bereitstellung von Konten für StaffHub-Benutzer, die keine Identität in Azure AD haben.</span><span class="sxs-lookup"><span data-stu-id="a801d-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="a801d-166">Jeder Manager und jedes Teammitglied muss über eine Identität im Azure Active Directory Domain Services (Azure AD) verfügen.</span><span class="sxs-lookup"><span data-stu-id="a801d-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a801d-167">Wenn ein Benutzer noch nicht über eine Identität in Azure AD verfügt, richten Sie ein Konto für ihn ein.</span><span class="sxs-lookup"><span data-stu-id="a801d-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="a801d-168">Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="a801d-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="a801d-169">Erhalten Sie eine Liste aller Benutzer in StaffHub-Teams, die Teammitglieder haben, die nicht über ein Azure AD-Konto verfügen.</span><span class="sxs-lookup"><span data-stu-id="a801d-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="a801d-170">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="a801d-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="a801d-171">Bereitstellen des Kontos</span><span class="sxs-lookup"><span data-stu-id="a801d-171">Provision the account</span></span>

<span data-ttu-id="a801d-172">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a801d-172">Do one of the following:</span></span>

- <span data-ttu-id="a801d-173">Konvertieren und verknüpfen Sie das Konto mit einem bereitgestellten Konto.</span><span class="sxs-lookup"><span data-stu-id="a801d-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="a801d-174">StaffHub Teambesitzer und Manager können einen Dummy oder inaktives Konto konvertieren und mit einem bereitgestellten Konto in StaffHub verknüpfen, indem sie die E-Mail-Adresse des Benutzers auf der StaffHub Team-Einstellungen-Seite in einen gültigen UPN ändern.</span><span class="sxs-lookup"><span data-stu-id="a801d-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="a801d-175">Entfernen Sie das nicht bereitgestellte Konto und fügen Sie es dann mit Hilfe des UPN erneut hinzu.</span><span class="sxs-lookup"><span data-stu-id="a801d-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="a801d-176">Führen Sie den Cmdlet[Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) aus, um das nicht bereitgestellte Konto aus dem StaffHub-Team zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a801d-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="a801d-177">Führen Sie den Cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) aus, um das Konto zurück zum StaffHub-Team hinzuzufügen, indem Sie den UPN verwenden.</span><span class="sxs-lookup"><span data-stu-id="a801d-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="a801d-178">Weisen Sie den Benutzern die FirstlineWorker App-Setup-Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="a801d-178">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="a801d-179">Teams enthält eine eingebaute FirstlineWorker-App-Setup-Richtlinie, mit der Sie Microsoft Teams anpassen können, um die Anwendungen hervorzuheben, die für die Mitarbeiter in Service und Produktion in Ihrer Organisation am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="a801d-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="a801d-180">Wenn Sie diese Richtlinie Benutzern zuweisen, werden die Anwendungen in der Richtlinie an die App-Leiste in Microsoft Teams angeheftet, um einen schnellen und einfachen Zugriff zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a801d-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="a801d-181">Weitere Apps, die in Microsoft Teams hinzugefügt wurden, finden Sie in der App-Leiste, indem Sie auf **...Weitere Apps** in den Teams Desktop- und Webclients klicken und durch das Wischen nach oben im Microsoft Teams Mobile Client.</span><span class="sxs-lookup"><span data-stu-id="a801d-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="a801d-182">Standardmäßig beinhaltet die FirstlineWorker App-Setup-Richtlinie die Apps für Aktivität, Shifts, Chat und Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a801d-182">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="a801d-183">Weitere Informationen zum Zuweisen der FirstlineWorker-App-Setup-Richtlinie an Benutzer finden Sie unter [Verwenden der FirstlineWorker-App-Setup-Richtlinie zum Anhäften von Shifts an Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="a801d-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="a801d-184">Nachdem Sie eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis sie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="a801d-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="a801d-185">Wir empfehlen Ihnen, diesen Schritt mindestens eine Woche vor dem Wechsel Ihrer StaffHub-Teams und Benutzer in Teams durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a801d-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="a801d-186">Wenn Benutzer in Teams sind, bestätigen Sie, dass sie die Shifts-App sehen und darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a801d-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="a801d-187">Sie können auch benutzerdefinierte App-Setup-Richtlinien erstellen und die Einstellungen in der globalen App-Setup-Richtlinie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a801d-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="a801d-188">Weitere Informationen finden Sie unter [Verwalten von App-Setup-Richtlinien in Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a801d-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="a801d-189">Benutzer in Teams einbinden</span><span class="sxs-lookup"><span data-stu-id="a801d-189">Onboard users to Teams</span></span>

<span data-ttu-id="a801d-190">Als Teil Ihrer Onboarding-Strategie bieten Sie Schulungen und Anleitungen für Benutzer an, die diesen helfen, sich mit Teams vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="a801d-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="a801d-191">Geben Sie die folgenden Ressourcen an Benutzer weiter, damit sie wissen, wo sie Team-Clients, Schulungen und Support erhalten:</span><span class="sxs-lookup"><span data-stu-id="a801d-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="a801d-192">Teams-Webclient</span><span class="sxs-lookup"><span data-stu-id="a801d-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="a801d-193">Downloadlinks für Desktop- und mobile Clients</span><span class="sxs-lookup"><span data-stu-id="a801d-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="a801d-194">Teams-Schulungsvideos</span><span class="sxs-lookup"><span data-stu-id="a801d-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="a801d-195">Teams-Hilfedokumentation</span><span class="sxs-lookup"><span data-stu-id="a801d-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="a801d-196">Anleitungen zur Bereitstellung von Teams und zur Förderung der Teams-Akzeptanz finden Sie unter [Wie Sie Teams einführen](../../How-to-roll-out-teams.md) und [Teams übernehmen können](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="a801d-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="a801d-197">Durchführen eines Pilotversuches</span><span class="sxs-lookup"><span data-stu-id="a801d-197">Conduct a user pilot</span></span>

<span data-ttu-id="a801d-198">Wir empfehlen Ihnen, zunächst zwei oder drei StaffHub-Teams für eine ausgewählte Gruppe von Erstanwendern zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="a801d-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="a801d-199">Die Durchführung eines Pilotversuchs hilft Ihnen, Ihren Migrationsplan zu verfeinern und sicherzustellen, dass Sie bereit sind, alle StaffHub-Teams Ihrer Organisation in Teams zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="a801d-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="a801d-200">Es werden auch Experten identifiziert, die dazu beitragen können, die Akzeptanz in Ihrer Organisation zu steigern.</span><span class="sxs-lookup"><span data-stu-id="a801d-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="a801d-201">Wenn Sie ein kleines Unternehmen sind, das keinen mehrstufigen Ansatz benötigt, reichen die Schritte in diesem Abschnitt aus, um den Wechsel von StaffHub zu Teams zu realisieren.</span><span class="sxs-lookup"><span data-stu-id="a801d-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="a801d-202">Auswählen der Pilotteams</span><span class="sxs-lookup"><span data-stu-id="a801d-202">Identify pilot teams</span></span>

<span data-ttu-id="a801d-203">Identifizieren Sie zwei oder drei Pilotteams.</span><span class="sxs-lookup"><span data-stu-id="a801d-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="a801d-204">Alle Teammitglieder sollten sich verpflichten, Shifts in Teams zu verwenden, um ihre Zeitpläne zu verwalten und miteinander zu kommunizieren und zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a801d-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="a801d-205">Auswählen der Teamexperten</span><span class="sxs-lookup"><span data-stu-id="a801d-205">Identify team champions</span></span>

<span data-ttu-id="a801d-206">Suchen Sie über Pilotteams hinweg Experten aus, und fordern Sie diese auf, sich für die Akzeptanz von Shifts einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="a801d-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="a801d-207">Teamexperten sind von ihrer Arbeit begeistert und teilen ihre eigenen Erfahrungen, um den Teammitgliedern Unterstützung und Beratung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="a801d-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="a801d-208">Teamexperten können Teambesitzer oder Manager sein.</span><span class="sxs-lookup"><span data-stu-id="a801d-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="a801d-209">Teamexperten sollten sicherstellen, dass die Teammitglieder so eingerichtet werden, dass jeder Zeit hat, um [Team-Clients zu erhalten](../../get-clients.md), sich bei Teams anzumelden und ihre Zeitpläne in Shifts zu überprüfen und mit einander zu chatten.</span><span class="sxs-lookup"><span data-stu-id="a801d-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="a801d-210">Benutzer, die bereits mit StaffHub vertraut sind, werden in Shifts schnell produktiv sein.</span><span class="sxs-lookup"><span data-stu-id="a801d-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="a801d-211">Sie können sie auch auf die [Shifts Hilfe](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) verweisen, um zusätzliche Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a801d-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="a801d-212">Verschieben eines StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-212">Move a StaffHub team</span></span>

<span data-ttu-id="a801d-213">Führen Sie diese Schritte aus, um ein StaffHub-Team nach dem anderen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="a801d-214">Wir empfehlen diesen Ansatz für Ihre Pilotteams.</span><span class="sxs-lookup"><span data-stu-id="a801d-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="a801d-215">Wenn Sie später bereit sind, alle StaffHub-Teams Ihrer Organisation zu verschieben, finden Sie unter [Verschieben Sie Ihre StaffHub-Teams](#move-your-staffhub-teams) Informationen, wie Sie mehrere Teams auf einmal verschieben können.</span><span class="sxs-lookup"><span data-stu-id="a801d-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="a801d-216">Führen Sie die folgenden Schritte aus, um ein StaffHub-Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="a801d-217">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a801d-217">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="a801d-218">Hier ist ein Beispiel für die Antwort, die Sie erhalten, wenn Sie eine Anfrage senden, ein StaffHub-Team an Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="a801d-219">Um den Status einer Migration zu überprüfen, führen Sie Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="a801d-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="a801d-220">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a801d-220">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="a801d-221">Hier ist ein Beispiel für die Antwort, die Sie erhalten, wenn eine Migration ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a801d-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="a801d-222">Dateien von einem StaffHub-Team in Teams verschieben</span><span class="sxs-lookup"><span data-stu-id="a801d-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="a801d-223">Dieser Schritt gilt nur, wenn das StaffHub-Team, das Sie in Teams verschoben haben, Dateien enthält, die Sie auch in Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="a801d-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="a801d-224">Sie können Dateien direkt in SharePoint Online oder mit PowerShell verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="a801d-225">In SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a801d-225">In SharePoint Online</span></span>

<span data-ttu-id="a801d-226">Hier finden Sie Informationen zum[Verschieben von Dateien in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="a801d-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="a801d-227">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a801d-227">Using Windows PowerShell</span></span>

<span data-ttu-id="a801d-228">Laden Sie [SharePoint Online Verwaltungsshell](https://www.microsoft.com/download/details.aspx?id=35588) herunter und installieren Sie es, falls noch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="a801d-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="a801d-229">Es enthält die Cmdlets, die Sie zum Verschieben von Dateien benötigen.</span><span class="sxs-lookup"><span data-stu-id="a801d-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="a801d-230">Verwenden Sie das Cmdlet [Connect-PnPOnline,](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) um eine Verbindung mit der SharePoint Online-Teamwebsite herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a801d-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="a801d-231">Verwenden Sie für jede Datei, die Sie von StaffHub in Teams verschieben möchten, das Cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile), um die Datei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="a801d-232">Um mehrere Dateien zu verschieben, führen Sie eine Schleife über die Dateien und führen Sie den zweiten Befehl auf der Schleife aus.</span><span class="sxs-lookup"><span data-stu-id="a801d-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="a801d-233">Sie müssen den ersten Befehl nicht wiederholen, wenn die Sitzung aktiv bleibt.</span><span class="sxs-lookup"><span data-stu-id="a801d-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="a801d-234">Gehen Sie über Ihren Piloteversuch hinaus und verschieben Sie alle StaffHub-Teams.</span><span class="sxs-lookup"><span data-stu-id="a801d-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="a801d-235">Bewusstsein schaffen</span><span class="sxs-lookup"><span data-stu-id="a801d-235">Raise awareness</span></span>

<span data-ttu-id="a801d-236">Wenn Sie bereit sind, über Ihre Pilotteams hinauszugehen und die StaffHub-Teams Ihrer Organisation in Teams zu verschieben, ist es wichtig, die Veränderung zunächst in Ihrer Organisation zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="a801d-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="a801d-237">Verbreiten Sie Informationen über Shifts und den Wechsel zu Teams, um das Bewusstsein zu erhöhen, Begeisterung zu erzeugen und die Akzeptanz zu steigern.</span><span class="sxs-lookup"><span data-stu-id="a801d-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="a801d-238">Verschieben Sie Ihre StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-238">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

<span data-ttu-id="a801d-239">Verwenden Sie diese Schritte, um StaffHub-Teams massenhaft zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="a801d-240">Sie können wählen, ob Sie alle StaffHub-Teams Ihrer Organisation oder einzelne StaffHub-Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="a801d-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="a801d-241">Wenn Sie StaffHub-Teams einzeln verschieben möchten, lesen Sie bitte den Abschnitt [Ein StaffHub-Teams verschieben](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="a801d-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="a801d-242">Alle StaffHub-Teams verschieben</span><span class="sxs-lookup"><span data-stu-id="a801d-242">Move all StaffHub teams</span></span>

<span data-ttu-id="a801d-243">Führen Sie den folgenden Befehl aus, um eine Liste aller StaffHub-Teams in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a801d-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="a801d-244">Führen Sie die folgenden Schritte aus, um alle Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="a801d-245">Hier ist ein Beispiel für die Antwort.</span><span class="sxs-lookup"><span data-stu-id="a801d-245">Here's an example of the response.</span></span>

<span data-ttu-id="a801d-246">Für jedes Team, das bereits in Teams verlegt wurde oder bereits in Teams existiert, ist die jobId "null", da kein Auftrag eingereicht werden muss, um dieses Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a801d-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="a801d-247">Verschieben von bestimmten StaffHub-Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="a801d-248">Führen Sie den folgenden Befehl aus, um eine Liste aller StaffHub-Team-IDs in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a801d-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="a801d-249">Wählen Sie in den Ergebnissen, die von dem zuvor ausgeführten `Get-StaffHubteamsForTenant`Cmdlet-Befehl angezeigt werden, die Team-IDs aus, die Sie verschieben möchten, und fügen Sie sie dann einer CSV-Datei (comma-separated values) hinzu.</span><span class="sxs-lookup"><span data-stu-id="a801d-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="a801d-250">Hier ist ein Beispiel, wie die CSV-Datei formatiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="a801d-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="a801d-251">Id</span><span class="sxs-lookup"><span data-stu-id="a801d-251">ID</span></span>  |
|---------|
|<span data-ttu-id="a801d-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="a801d-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="a801d-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="a801d-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="a801d-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="a801d-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="a801d-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="a801d-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="a801d-256">Nachdem Sie die CSV-Datei erstellt haben, führen Sie Folgendes aus, um die Teams zu verschieben, die Sie in der CSV-Datei angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a801d-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="a801d-257">Bestätigen Sie, dass Ihre StaffHub-Teams in die Teams migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="a801d-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="a801d-258">Führen Sie die folgenden Befehl aus, um eine Liste aller Teams in Shifts in Ihrer Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a801d-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="a801d-259">Dateien von Ihren StaffHub-Teams in Microsoft Teams verschieben</span><span class="sxs-lookup"><span data-stu-id="a801d-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="a801d-260">Wenn die StaffHub-Teams, die Sie verschoben haben, Dateien enthalten, die Sie auch in Microsoft Teams verschieben möchten, lesen Sie den Abschnitt [Dateien von einem StaffHub-Team in Microsoft Teams verschieben](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="a801d-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="a801d-261">Überwachung der Teams-Nutzung</span><span class="sxs-lookup"><span data-stu-id="a801d-261">Monitor Teams usage</span></span>

<span data-ttu-id="a801d-262">Mithilfe von Nutzungsberichten können Sie Nutzungsmuster besser verstehen und Sie gelangen so zu Einsichten, die Sie zur Priorisierung von Schulungs- und Kommunikationsinitiativen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a801d-262">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="a801d-263">Da Shifts eine App in Microsoft Teams ist, können Sie die Nutzung über Teams-Berichte einsehen.</span><span class="sxs-lookup"><span data-stu-id="a801d-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="a801d-264">Weitere Informationen finden Sie unter [Teams-Berichte im Microsoft Teams Admincenter](../../teams-analytics-and-reports/teams-reporting-reference.md)und[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="a801d-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a801d-265">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a801d-265">Troubleshooting</span></span> 

<span data-ttu-id="a801d-266">**Wenn Sie versuchen, Dateien von StaffHub in Microsoft Teams zu verschieben, erhalten Sie die Fehlermeldung "Berechtigung verweigert".**</span><span class="sxs-lookup"><span data-stu-id="a801d-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="a801d-267">Dies kann vorkommen, wenn Sie versuchen, Dateien in einer privaten Office 365-Gruppe zu verschieben, der Sie nicht angehören.</span><span class="sxs-lookup"><span data-stu-id="a801d-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="a801d-268">Wenn dies der Fall ist, verwenden Sie das Cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember), um sich zum StaffHub-Team hinzuzufügen, und verschieben Sie dann die Dateien.</span><span class="sxs-lookup"><span data-stu-id="a801d-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="a801d-269">Nachdem Sie die Dateien verschoben haben, verwenden Sie das Cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember), um sich aus dem Team zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a801d-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="a801d-270">**Wenn Sie versuchen, Dateien von StaffHub in Microsoft Teams zu verschieben, erhalten Sie eine Fehlermeldung, dass der Ordner „Allgemein“ nicht existiert.**</span><span class="sxs-lookup"><span data-stu-id="a801d-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="a801d-271">Führen Sie den folgenden Befehl aus, um den Ordner „Allgemein“ zu Microsoft Office SharePoint Online hinzuzufügen, und versuchen Sie es dann erneut:</span><span class="sxs-lookup"><span data-stu-id="a801d-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="a801d-272">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a801d-272">Related topics</span></span>
- [<span data-ttu-id="a801d-273">Bereitstellen von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="a801d-274">Microsoft StaffHub soll eingestellt werden</span><span class="sxs-lookup"><span data-stu-id="a801d-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="a801d-275">Verwalten der Shifts-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a801d-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="a801d-276">StaffHub-PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="a801d-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
