---
title: Verschieben Ihrer StaffHub-Teams in Schichten in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Microsoft StaffHub-Teams verschieben und Daten in Microsoft Teams in Schichten planen können.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548294"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="331e9-103">Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="331e9-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="331e9-104">Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="331e9-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="331e9-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="331e9-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="331e9-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="331e9-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="331e9-107">StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="331e9-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="331e9-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="331e9-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="331e9-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="331e9-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="331e9-110">Die in diesem Artikel beschriebene Funktion wurde noch nicht veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="331e9-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="331e9-111">Es wurde angekündigt, und wird in Kürze, Anfang Juni 2019.</span><span class="sxs-lookup"><span data-stu-id="331e9-111">It's been announced, and is coming soon, in early June 2019.</span></span> <span data-ttu-id="331e9-112">Wenn Sie ein Administrator sind, können Sie herausfinden, wann dies im Nachrichtencenter (im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)) verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="331e9-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="331e9-113">Die Schicht-app in Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und den konstanten Fluss von Schicht-Swaps und-Abbrüchen, die täglich auftreten.</span><span class="sxs-lookup"><span data-stu-id="331e9-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="331e9-114">Team Mitglieder können auf Ihre Plan-und Schicht Informationen direkt in der APP und auf Ihren Geräten zugreifen, um Ihre Einstellungen festzulegen, ihre Zeitpläne zu verwalten und die Freizeit zu beantragen.</span><span class="sxs-lookup"><span data-stu-id="331e9-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="331e9-115">In diesem Artikel erfahren Sie, wie Sie die StaffHub-Teams Ihrer Organisation verschieben und Daten in Teams verschieben können.</span><span class="sxs-lookup"><span data-stu-id="331e9-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="331e9-116">Ganz gleich, ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub-Teams oder einem Großunternehmen mit Hunderten von StaffHub-Teams sind, hier finden Sie die Administratoranleitung, die Sie benötigen, um den Übergang zu Teams erfolgreich zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="331e9-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="331e9-117">Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="331e9-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="331e9-118">Wenn Sie dies noch nicht getan haben, schauen Sie sich die [FAQ zu StaffHub Retirement](microsoft-staffhub-to-be-retired.md) an, um Antworten auf Ihre Fragen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="331e9-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="331e9-119">Was Sie über den Umzug in Teams wissen müssen</span><span class="sxs-lookup"><span data-stu-id="331e9-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="331e9-120">Zeitpunkt für den Wechsel zu Teams</span><span class="sxs-lookup"><span data-stu-id="331e9-120">When to move to Teams</span></span>

<span data-ttu-id="331e9-121">Ab dem 1. Oktober 2019 wird StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="331e9-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="331e9-122">Wir empfehlen Ihnen, die Verwendung von Teams noch heute zu verwenden und zu beginnen, die Teams und Benutzer Ihrer Organisation aus StaffHub zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="331e9-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="331e9-123">Da die Zeitplanverwaltung das am häufigsten verwendete Feature in StaffHub ist, empfehlen wir, dass Sie die app "Schichten" in Teams verwenden, die sich weiter bewegen.</span><span class="sxs-lookup"><span data-stu-id="331e9-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="331e9-124">Was wird in Teams verschoben?</span><span class="sxs-lookup"><span data-stu-id="331e9-124">What is moved to Teams</span></span>

<span data-ttu-id="331e9-125">Benutzer Details, Zeitplaninformationen sowie Chat-und Dateidaten werden in Teams umgestellt.</span><span class="sxs-lookup"><span data-stu-id="331e9-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="331e9-126">Dazu gehören Teammitgliedschaft, Team Zeitpläne sowie Chats und Dateien aus den letzten 90 Tagen.</span><span class="sxs-lookup"><span data-stu-id="331e9-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="331e9-127">Jedes StaffHub-Team benötigt eine entsprechende Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="331e9-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="331e9-128">Wenn einem StaffHub-Team keine Office 365-Gruppe zugeordnet ist, wird automatisch ein für Sie erstellt, um den Übergang zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="331e9-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="331e9-129">Angesichts der Unterschiede bei der Team-und Gruppenbenennung zwischen Teams und StaffHub wird möglicherweise in Teams ein anderer Teamname angezeigt.</span><span class="sxs-lookup"><span data-stu-id="331e9-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="331e9-130">Wenn Sie Teams von StaffHub in Teams umstellen, haben die Benutzer keinen Zugriff mehr auf ihre Zeitpläne in StaffHub und werden an Schichten in Teams umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="331e9-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="331e9-131">Wir empfehlen, dass Sie diese Änderung in Ihrer Organisation übermitteln, um Unterbrechungen zu minimieren und Benutzer zu ermutigen, Teams zu übernehmen und zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="331e9-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="331e9-132">Wenn Sie über Azure AD Premium verfügen, können Sie [einen Bericht ausführen](run-report-to-show-staffhub-usage.md) , um eine Liste der StaffHub-Benutzer in Ihrer Organisation abzurufen, die über diese Änderung Bescheid wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="331e9-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="331e9-133">Nachdem Sie ein StaffHub-Team in Teams verschoben haben, gibt es keine Rollback-Option.</span><span class="sxs-lookup"><span data-stu-id="331e9-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="331e9-134">Benutzererfahrung beim Verschieben eines Teams</span><span class="sxs-lookup"><span data-stu-id="331e9-134">User experience when you move a team</span></span>

<span data-ttu-id="331e9-135">Es gibt minimale Ausfallzeiten (wenn überhaupt keine Sekunde) für Benutzer, wenn Ihr Team von StaffHub zu Schichten in Teams gewechselt hat.</span><span class="sxs-lookup"><span data-stu-id="331e9-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="331e9-136">Benutzer können StaffHub weiterhin verwenden, bis der Wechsel zu Teams abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="331e9-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="331e9-137">Nach Abschluss des Umzugs wird den Teammitgliedern eine Meldung angezeigt, in der Sie darüber informiert werden, dass Sie die Verwendung von Schichten in Teams für den Zugriff auf Ihren Team Zeitplan benötigen.</span><span class="sxs-lookup"><span data-stu-id="331e9-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="331e9-138">Nachfolgend finden Sie ein Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="331e9-138">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="331e9-139">![Beispiel für die Meldung, die Benutzern angezeigt wird.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde")</span><span class="sxs-lookup"><span data-stu-id="331e9-139">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="331e9-140">Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="331e9-140">Prepare</span></span>

<span data-ttu-id="331e9-141">Hier erfahren Sie, wie Sie sich auf den Umzug in Teams vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="331e9-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="331e9-142">Zuweisen von Teams-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="331e9-142">Assign Teams licenses</span></span>

<span data-ttu-id="331e9-143">Jeder Benutzer muss über eine aktive Microsoft 365-oder Office 365-Lizenz für [einen berechtigten Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) verfügen und muss eine Teams-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="331e9-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="331e9-144">Wenn Sie Benutzern eine Teams-Lizenz zuweisen, erhalten Sie Zugriff auf Teams.</span><span class="sxs-lookup"><span data-stu-id="331e9-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="331e9-145">Sie verwalten die Lizenzen für Teams im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="331e9-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="331e9-146">Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="331e9-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="331e9-147">Wenn Ihre Organisation Skype for Business verwendet und Sie nicht bereit sind, alle Ihre Benutzer in Teams zu verschieben, können Sie Teams für Ihre Mitarbeiter in der First-work-Abteilung aktivieren, die dann Teams neben Skype for Business ausführen können.</span><span class="sxs-lookup"><span data-stu-id="331e9-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="331e9-148">In diesem Koexistenzmodus, dem sogenannten " *Inseln*", fungiert jede Client-App als separate Lösung.</span><span class="sxs-lookup"><span data-stu-id="331e9-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="331e9-149">Weitere Informationen finden Sie Untergrund Legendes zu [Teams und zur Koexistenz und Interoperabilität von Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="331e9-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="331e9-150">Bereitstellen von Konten für StaffHub-Benutzer, die keine Identität in Azure AD besitzen</span><span class="sxs-lookup"><span data-stu-id="331e9-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="331e9-151">Jeder Manager und jedes Teammitglied muss über eine Identität in Azure Active Directory (Azure AD) verfügen.</span><span class="sxs-lookup"><span data-stu-id="331e9-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="331e9-152">Wenn ein Benutzer noch keine Identität in Azure AD hat, stellen Sie ihm ein Konto bereit.</span><span class="sxs-lookup"><span data-stu-id="331e9-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="331e9-153">Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="331e9-153">Here's how.</span></span>

- <span data-ttu-id="331e9-154">StaffHub-Teambesitzer und-Manager können ein Dummy-oder Inaktives Konto konvertieren und mit einem bereitgestellten Konto in StaffHub verknüpfen, indem Sie die e-Mail-Adresse des Benutzers in einen gültigen UPN auf der Seite "StaffHub-Team Einstellungen" ändern.</span><span class="sxs-lookup"><span data-stu-id="331e9-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="331e9-155">Administratoren können die Cmdlets [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) und [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) ausführen, um ein nicht bereitgestelltes Konto aus einem StaffHub-Team zu entfernen und das Konto mithilfe des UPN wieder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="331e9-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="331e9-156">Installieren des StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="331e9-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="331e9-157">Wenn Sie dies noch nicht getan haben, [Installieren Sie das StaffHub PowerShell-Modul](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="331e9-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="331e9-158">Wenn Sie ein StaffHub-Team verschieben, überprüft die Verschiebungsanforderung die Voraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="331e9-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="331e9-159">Hier sind die Gründe, warum eine Verschiebungsanforderung fehlschlagen kann:</span><span class="sxs-lookup"><span data-stu-id="331e9-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="331e9-160">Der angemeldete Benutzer ist kein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="331e9-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="331e9-161">Teams ist für alle Benutzer im Mandanten deaktiviert</span><span class="sxs-lookup"><span data-stu-id="331e9-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="331e9-162">Die Erstellung von Office 365-Gruppen ist im Mandanten deaktiviert</span><span class="sxs-lookup"><span data-stu-id="331e9-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="331e9-163">Die teamStaffHub ist ungültig oder hat keine Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="331e9-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="331e9-164">Das StaffHub-Team enthält Mitglieder, die nicht mit einem Azure AD-Konto verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="331e9-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="331e9-165">Führen eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="331e9-165">Run a pilot</span></span>

<span data-ttu-id="331e9-166">Wir empfehlen, dass Sie zunächst zwei oder drei StaffHub-Teams für eine ausgewählte Gruppe von Early Adopters verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="331e9-167">Durch das Ausführen eines Pilotprojekts können Sie Ihren Übergangsplan verfeinern und sicherstellen, dass Sie bereit sind, alle StaffHub-Teams Ihrer Organisation in Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="331e9-168">Es werden auch Champions identifiziert, die Ihnen bei der Einführung in Ihrer Organisation behilflich sein können.</span><span class="sxs-lookup"><span data-stu-id="331e9-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="331e9-169">Wenn Sie ein kleines Unternehmen sind, das keinen Phasen orientierten Ansatz benötigt, sind die Schritte in diesem Abschnitt möglicherweise alles, was Sie benötigen, um von StaffHub zu Teams zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="331e9-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="331e9-170">Ermitteln von Pilot Teams</span><span class="sxs-lookup"><span data-stu-id="331e9-170">Identify pilot teams</span></span>

<span data-ttu-id="331e9-171">Erreichen Sie zwei oder drei Pilot Teams.</span><span class="sxs-lookup"><span data-stu-id="331e9-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="331e9-172">Alle Teammitglieder sollten sich verpflichten, mithilfe von Schichten in Teams ihre Zeitpläne zu verwalten und miteinander zu kommunizieren und zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="331e9-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="331e9-173">Identifizieren von Team Champions</span><span class="sxs-lookup"><span data-stu-id="331e9-173">Identify team champions</span></span>

<span data-ttu-id="331e9-174">Ermitteln Sie Champions in Pilot Teams, und geben Sie Sie zur Evangelisierung von Schichten ein.</span><span class="sxs-lookup"><span data-stu-id="331e9-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="331e9-175">Team-Champions sind leidenschaftlich über das, was Sie tun, indem Sie Ihre eigenen Erfahrungen austauschen, um den Teammitgliedern Support und Hilfestellung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="331e9-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="331e9-176">Team Champions können Teambesitzer oder Manager sein.</span><span class="sxs-lookup"><span data-stu-id="331e9-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="331e9-177">Team-Champions sollten sicherstellen, dass die Teammitglieder eingerichtet werden, indem Sie Zeit für jeden einrichten, um [Teams-Clients zu erhalten](../../get-clients.md), sich bei Teams anzumelden und deren Zeitpläne in Schichten zu überprüfen und mit anderen zu chatten.</span><span class="sxs-lookup"><span data-stu-id="331e9-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="331e9-178">Benutzer, die bereits mit StaffHub vertraut sind, werden in Schichten schnell in Betrieb sein.</span><span class="sxs-lookup"><span data-stu-id="331e9-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="331e9-179">Sie können auch auf die [Schalt Schicht Hilfe](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) verweisen, um weitere Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="331e9-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="331e9-180">Verschieben eines StaffHub-Teams (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="331e9-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="331e9-181">Führen Sie die folgenden Schritte aus, um ein StaffHub-Team gleichzeitig zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="331e9-182">Wir empfehlen diesen Ansatz für Ihre Pilot Teams.</span><span class="sxs-lookup"><span data-stu-id="331e9-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="331e9-183">Wenn Sie zu einem späteren Zeitpunkt alle StaffHub-Teams Ihrer Organisation verschieben möchten, lesen Sie [Verschieben von StaffHub Teams](#move-your-staffhub-teams-coming-soon) nach Schritten zum Verschieben mehrerer Teams.</span><span class="sxs-lookup"><span data-stu-id="331e9-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="331e9-184">Führen Sie die folgenden Schritte aus, um ein StaffHub-Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="331e9-185">Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn Sie eine Anfrage einreichen, um ein StaffHub-Team in Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="331e9-186">Führen Sie die folgenden Schritte aus, um den Status einer Verschiebungsanforderung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="331e9-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="331e9-187">Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn ein Schritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="331e9-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="331e9-188">Durchführen des Übergangs von StaffHub zu Teams</span><span class="sxs-lookup"><span data-stu-id="331e9-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="331e9-189">Sensibilisieren</span><span class="sxs-lookup"><span data-stu-id="331e9-189">Raise awareness</span></span>

<span data-ttu-id="331e9-190">Wenn Sie bereit sind, über Ihre Pilot Teams hinauszugehen und die StaffHub-Teams Ihrer Organisation in Teams zu verschieben, ist es wichtig, zunächst die Änderung in Ihrer Organisation zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="331e9-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="331e9-191">Informieren Sie sich über Schichten und den Übergang zu Teams, um das Bewusstsein zu schärfen, Spannung zu wecken und die Akzeptanz zu steigern.</span><span class="sxs-lookup"><span data-stu-id="331e9-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="331e9-192">Verschieben Ihrer StaffHub-Teams (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="331e9-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="331e9-193">Führen Sie die folgenden Schritte aus, um StaffHub Teams massenhaft zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="331e9-194">Sie können auswählen, ob Sie alle StaffHub-Teams Ihrer Organisation verschieben oder bestimmte StaffHub-Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="331e9-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="331e9-195">Wenn Sie StaffHub Teams einzeln verschieben möchten, lesen Sie [Verschieben eines StaffHub](#move-a-staffhub-team-coming-soon)-Teams.</span><span class="sxs-lookup"><span data-stu-id="331e9-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="331e9-196">Verschieben aller StaffHub-Teams (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="331e9-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="331e9-197">Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Teams in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="331e9-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="331e9-198">Führen Sie dann die folgenden Schritte aus, um alle Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="331e9-199">Hier ist ein Beispiel für die Antwort.</span><span class="sxs-lookup"><span data-stu-id="331e9-199">Here's an example of the response.</span></span>

<span data-ttu-id="331e9-200">Für alle Teams, die bereits in Teams verschoben oder bereits in Teams vorhanden sind, ist die JobID "Null", da ein Auftrag nicht gesendet werden muss, um das Team zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="331e9-201">Verschieben spezifischer StaffHub-Teams (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="331e9-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="331e9-202">Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Team-IDs in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="331e9-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="331e9-203">Wählen Sie in den Ergebnissen, `Get-StaffHubteamsForTenant` die von dem zuvor ausgeführten Cmdlet zurückgegeben wurden, die Team-IDs aus, die Sie verschieben möchten, und fügen Sie Sie dann einer CSV-Datei (Comma-Separated Values, CSV) hinzu.</span><span class="sxs-lookup"><span data-stu-id="331e9-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="331e9-204">Im folgenden finden Sie ein Beispiel dafür, wie die CSV-Datei formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="331e9-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="331e9-205">ID</span><span class="sxs-lookup"><span data-stu-id="331e9-205">Id</span></span>  |
|---------|
|<span data-ttu-id="331e9-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="331e9-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="331e9-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="331e9-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="331e9-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="331e9-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="331e9-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="331e9-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="331e9-210">Nachdem Sie die CSV-Datei erstellt haben, führen Sie die folgenden Schritte aus, um die in der CSV-Datei angegebenen Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="331e9-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="331e9-211">Vergewissern Sie sich, dass Ihre StaffHub-Teams in die Teams umgezogen sind (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="331e9-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="331e9-212">Führen Sie die folgenden Schritte aus, um eine Liste aller Teams in Schichten in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="331e9-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="331e9-213">Überwachen der Verwendung von Teams</span><span class="sxs-lookup"><span data-stu-id="331e9-213">Monitor Teams usage</span></span>

<span data-ttu-id="331e9-214">Verwendungsberichte können Ihnen dabei helfen, Nutzungsmuster besser zu verstehen und Ihnen Einblicke zu geben, wo Sie die Schulungs-und Kommunikationsaktivitäten in Ihrer Organisation priorisieren können.</span><span class="sxs-lookup"><span data-stu-id="331e9-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="331e9-215">Da es sich bei Schichten um eine app in Teams handelt, können Sie die Verwendung über Teams-Berichte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="331e9-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="331e9-216">Weitere Informationen finden Sie unter [Teams-Berichterstattung im Microsoft Teams Admin Center](../../teams-analytics-and-reports/teams-reporting-reference.md) und [Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="331e9-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="331e9-217">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="331e9-217">Related topics</span></span>
- [<span data-ttu-id="331e9-218">Microsoft StaffHub soll eingestellt werden</span><span class="sxs-lookup"><span data-stu-id="331e9-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="331e9-219">Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="331e9-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="331e9-220">StaffHub PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="331e9-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
