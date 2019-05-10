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
description: Informationen Sie zum Verschieben von Ihren Teams bei Microsoft StaffHub und Daten im Microsoft-Teams Schichten planen.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74a9b23479f5357c0014ef5ef88b3f5da03ace7f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865051"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="586bc-103">Verschieben Sie Ihren Teams bei Microsoft StaffHub in Schichten in der Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="586bc-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="586bc-104">Die Übermittlung wirksamer wird 1 Oktober 2019, Microsoft StaffHub zurückgezogen werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="586bc-105">Wir erstellen StaffHub-Funktionen in Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="586bc-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="586bc-106">Heute, Teams enthält die Schichten app für zeitplanverwaltung und zusätzliche Funktionen, die über einen Zeitraum einführen werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="586bc-107">StaffHub werden nicht für alle Benutzer auf 1 Oktober 2019 mehr.</span><span class="sxs-lookup"><span data-stu-id="586bc-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="586bc-108">Jeder Benutzer, der versucht, StaffHub öffnen wird eine Meldung mit der Weiterleitung zum Herunterladen von Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="586bc-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="586bc-109">Weitere Informationen finden Sie unter [Microsoft StaffHub zurückgezogen werden](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="586bc-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="586bc-110">Die Möglichkeit, die in diesem Artikel erläuterten noch nicht noch zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="586bc-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="586bc-111">Es ist bekannt gegeben und wird in Kürze verfügbar, in die Mitte der Mai 2019.</span><span class="sxs-lookup"><span data-stu-id="586bc-111">It's been announced, and is coming soon, towards the middle of May 2019.</span></span> <span data-ttu-id="586bc-112">Wenn Sie ein Administrator sind, können Sie feststellen, wenn dies in der Mitte der Nachricht (in der [Microsoft-365-Verwaltungskonsole](https://portal.office.com/adminportal/home)) zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="586bc-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="586bc-113">Die Schichten-app in Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und der Konstante Ablauf UMSCHALT vertauscht und absagen, die täglich auftreten.</span><span class="sxs-lookup"><span data-stu-id="586bc-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="586bc-114">Teammitglieder können seinen Zeitplan zugreifen und UMSCHALT Informationen direkt in der app über ihren Geräten ihren Vorlieben festgelegt, deren Zeitpläne verwalten und Anforderungszeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="586bc-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="586bc-115">Dieser Artikel führt Sie durch das Verschieben Ihrer Organisation StaffHub Teams und Daten im Teams Schichten planen.</span><span class="sxs-lookup"><span data-stu-id="586bc-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="586bc-116">Ganz gleich, ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub Teams oder große Unternehmen mit Hunderten von StaffHub Teams, finden hier die Admin-Anleitung Sie, die Sie benötigen, um des Übergangs Teams Erfolg zu machen.</span><span class="sxs-lookup"><span data-stu-id="586bc-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="586bc-117">Sie müssen ein globaler Administrator zum Ausführen der Schritte in diesem Artikel werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="586bc-118">Wenn Sie dies noch nicht getan haben, haben Sie einen Überblick über die [StaffHub Stilllegung – häufig gestellte Fragen](microsoft-staffhub-to-be-retired.md) , Antworten auf Fragen zu erhalten, die Sie möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="586bc-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="586bc-119">Sie müssen über die Verschiebung Teams wissen sollten</span><span class="sxs-lookup"><span data-stu-id="586bc-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="586bc-120">Beim Verschieben von Teams</span><span class="sxs-lookup"><span data-stu-id="586bc-120">When to move to Teams</span></span>

<span data-ttu-id="586bc-121">Die Übermittlung wirksamer wird 1 Oktober 2019, StaffHub zurückgezogen werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="586bc-122">Wir empfehlen Ihnen, starten Sie heute mithilfe von Teams und für den Übergang von Teams und Benutzer aus StaffHub Ihres Unternehmens beginnen.</span><span class="sxs-lookup"><span data-stu-id="586bc-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="586bc-123">Mit zeitplanverwaltung wird das Feature am häufigsten verwendeten in StaffHub wird empfohlen, dass Sie die app Schichten in Teams verwenden vorwärts verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="586bc-124">Was ist in Teams verschoben.</span><span class="sxs-lookup"><span data-stu-id="586bc-124">What is moved to Teams</span></span>

<span data-ttu-id="586bc-125">Teams sind Benutzerdetails Zeitplaninformationen und Chat und Dateidaten gewechselt.</span><span class="sxs-lookup"><span data-stu-id="586bc-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="586bc-126">Dazu gehören Teammitgliedschaft, Team Zeitpläne, und Chats und Dateien von der letzten 90 Tage.</span><span class="sxs-lookup"><span data-stu-id="586bc-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="586bc-127">Jedes Team StaffHub benötigt eine entsprechende Office 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="586bc-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="586bc-128">Wenn ein Team StaffHub ein mit ihm verbundenes Office 365-Gruppe vorhanden ist, wird eine automatisch für Sie zur Unterstützung des Übergangs erstellt.</span><span class="sxs-lookup"><span data-stu-id="586bc-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="586bc-129">In Anbetracht der unterschiedlichen in Teams und der Gruppe Namenskonflikt zwischen Teams und StaffHub, sehen Sie möglicherweise einen anderen Teamnamen in Teams.</span><span class="sxs-lookup"><span data-stu-id="586bc-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="586bc-130">Wie Sie Teams aus StaffHub Teams Übergang, Benutzer haben Zugriff auf ihre Zeitpläne nicht mehr in StaffHub und zu Schichten in Teams weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="586bc-131">Es wird empfohlen, dass Sie diese Änderung in Ihrer Organisation, um Unterbrechung zu minimieren und fordern Sie die Benutzer zu übernehmen und Erforschen von Teams kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="586bc-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="586bc-132">Wenn Sie Azure AD Premium verfügen, können Sie zum Abrufen einer Liste von Benutzern in Ihrer Organisation, die über diese Änderung wissen sollten StaffHub [Führen Sie einen Bericht](run-report-to-show-staffhub-usage.md) .</span><span class="sxs-lookup"><span data-stu-id="586bc-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="586bc-133">Es gibt keine Rollbackoption, nachdem Sie ein Team StaffHub Teams verschoben.</span><span class="sxs-lookup"><span data-stu-id="586bc-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="586bc-134">Wenn Sie ein Team verschieben Benutzererlebnis</span><span class="sxs-lookup"><span data-stu-id="586bc-134">User experience when you move a team</span></span>

<span data-ttu-id="586bc-135">Es ist die minimale Ausfallzeit (weniger als eine Sekunde, wenn überhaupt) für Benutzer, wenn ihr Team von StaffHub zu Schichten in Teams gewechselt wird.</span><span class="sxs-lookup"><span data-stu-id="586bc-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="586bc-136">Benutzer können weiterhin mit StaffHub erst nach Abschluss der Wechsel zu Teams.</span><span class="sxs-lookup"><span data-stu-id="586bc-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="586bc-137">Wenn die Verschiebung abgeschlossen ist, sehen Teammitglieder eine Nachricht an diese darüber informieren, dass sie über die Verwendung Schichten in Teams auf seinen Zeitplan Team zugreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="586bc-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="586bc-138">Es folgt ein Beispiel der Nachricht, die Benutzer sehen.</span><span class="sxs-lookup"><span data-stu-id="586bc-138">Here's an example of the message that users see.</span></span>

<span data-ttu-id="586bc-139">![Beispiel für die Meldung, die Benutzern in StaffHub angezeigt, nachdem das Team StaffHub Teams verschoben wird.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer sehen in StaffHub nach das Team StaffHub Teams verschoben wird")</span><span class="sxs-lookup"><span data-stu-id="586bc-139">![Example of the message that users see in StaffHub after the StaffHub team is moved to Teams. ](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="586bc-140">Zubereiten</span><span class="sxs-lookup"><span data-stu-id="586bc-140">Prepare</span></span>

<span data-ttu-id="586bc-141">Hier ist wie für das Verschieben der Teams vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="586bc-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="586bc-142">Zuweisen von Teams-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="586bc-142">Assign Teams licenses</span></span>

<span data-ttu-id="586bc-143">Jeder Benutzer benötigen eine aktive Microsoft 365 oder Office 365-Lizenz aus [einem Anspruch Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) und Teams Lizenz zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="586bc-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="586bc-144">Zuweisen einer Lizenz Teams für Benutzer erhalten sie Zugriff auf Teams.</span><span class="sxs-lookup"><span data-stu-id="586bc-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="586bc-145">Sie können Teams-Lizenzen in der Microsoft-365-Verwaltungskonsole verwalten.</span><span class="sxs-lookup"><span data-stu-id="586bc-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="586bc-146">Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs für Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="586bc-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="586bc-147">Wenn Ihre Organisation Skype für Unternehmen verwendet, und Sie sind nicht alle Benutzer in Teams zu verschieben, können Sie Teams für Ihre Mitarbeiter Firstline aktivieren, die dann Teams zusammen mit Skype für Unternehmen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="586bc-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="586bc-148">In diesem Koexistenzmodus *Inseln*aufgerufen, wird jede Clientanwendung als eine separate Lösung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="586bc-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="586bc-149">Weitere Informationen finden Sie finden Sie unter [Grundlegendes zu Teams und Skype für Interoperabilität und Koexistenz von Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="586bc-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="586bc-150">Bereitstellung von Konten für StaffHub-Benutzer, die nicht über eine Identität in Azure AD verfügen</span><span class="sxs-lookup"><span data-stu-id="586bc-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="586bc-151">Jeden Manager und Teammitglied benötigen eine Identität in Azure Active Directory (AD Azure).</span><span class="sxs-lookup"><span data-stu-id="586bc-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="586bc-152">Wenn ein Benutzer eine Identität in Azure AD bereits vorhanden ist, stellen Sie ein Konto für diese bereit.</span><span class="sxs-lookup"><span data-stu-id="586bc-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="586bc-153">Vorgehensweise:</span><span class="sxs-lookup"><span data-stu-id="586bc-153">Here's how.</span></span>

- <span data-ttu-id="586bc-154">StaffHub Team Eigentümer und Manager können eine simulierte Kontostatus konvertieren und Verknüpfen des Arbeitsbereichs mit einem bereitgestellten Konto in StaffHub durch Ändern der e-Mail-Adresse des Benutzers für einen gültigen UPN auf der Seite StaffHub Team Settings.</span><span class="sxs-lookup"><span data-stu-id="586bc-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="586bc-155">Administratoren können die [Hinzufügen-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) ausführen und [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) -Cmdlets zum Entfernen eines Kontos nicht bereitgestellte aus einem Team StaffHub, und fügen Sie das Konto mithilfe des UPN sichern.</span><span class="sxs-lookup"><span data-stu-id="586bc-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="586bc-156">Installieren des StaffHub PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="586bc-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="586bc-157">Wenn Sie nicht bereits geschehen, [Installieren Sie das Modul StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="586bc-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="586bc-158">Wenn Sie ein Team StaffHub verschieben, wird die verschiebungsanforderung für erforderliche Komponenten überprüft.</span><span class="sxs-lookup"><span data-stu-id="586bc-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="586bc-159">Nachfolgend finden Sie Gründe, warum eine verschiebungsanforderung fehlschlagen kann:</span><span class="sxs-lookup"><span data-stu-id="586bc-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="586bc-160">Der Benutzer angemeldet ist kein globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="586bc-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="586bc-161">Teams ist für alle Benutzer in den Mandanten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="586bc-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="586bc-162">Office 365 Gruppen erstellen ist in den Mandanten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="586bc-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="586bc-163">Das Team StaffHub ist ungültig oder enthält keine Mitglieder</span><span class="sxs-lookup"><span data-stu-id="586bc-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="586bc-164">Das StaffHub Team enthält Elemente, die mit einem Azure AD-Konto verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="586bc-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="586bc-165">Ausführen eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="586bc-165">Run a pilot</span></span>

<span data-ttu-id="586bc-166">Es wird empfohlen, dass Sie starten, indem Sie zwei oder drei StaffHub Teams für eine ausgewählte Gruppe von frühe Übernahmen verschieben.</span><span class="sxs-lookup"><span data-stu-id="586bc-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="586bc-167">Ausführen eines Pilotprojekts Dank Optimieren des Plans für den Umstieg von, und stellen Sie sicher, dass Sie Ihrer Organisation StaffHub Teams Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="586bc-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="586bc-168">Er gibt außerdem Champions, die Akzeptanz in Ihrem Unternehmen helfen können.</span><span class="sxs-lookup"><span data-stu-id="586bc-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="586bc-169">Wenn Sie ein kleines Unternehmen, das phasenweise nicht erforderlich ist sind, können die Schritte in diesem Abschnitt alle können, Sie die Option von StaffHub Teams müssen.</span><span class="sxs-lookup"><span data-stu-id="586bc-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="586bc-170">Identifizieren von pilot-teams</span><span class="sxs-lookup"><span data-stu-id="586bc-170">Identify pilot teams</span></span>

<span data-ttu-id="586bc-171">Erreichen von zwei oder drei pilot Teams zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="586bc-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="586bc-172">Alle Teammitglieder sollten mithilfe von Schichten Teams ihre Zeitpläne verwalten und Kommunikation und Zusammenarbeit miteinander in commit.</span><span class="sxs-lookup"><span data-stu-id="586bc-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="586bc-173">Identifizieren von Champions team</span><span class="sxs-lookup"><span data-stu-id="586bc-173">Identify team champions</span></span>

<span data-ttu-id="586bc-174">Identifizieren von Champions über pilot Teams und registrieren, mit denen Schichten Wechsels bekannt.</span><span class="sxs-lookup"><span data-stu-id="586bc-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="586bc-175">Team Champions am Herzen was sie tun, werden ihre eigenen Befunde um bieten Unterstützung und an die Teammitglieder freigeben.</span><span class="sxs-lookup"><span data-stu-id="586bc-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="586bc-176">Team Champions kann Team Besitzer oder -Manager.</span><span class="sxs-lookup"><span data-stu-id="586bc-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="586bc-177">Team Champions sollten sicherstellen, Teammitglieder eingesetzten Hörers Zeit für alle Benutzer, [Teams Clients erhalten möchten](../../get-clients.md), melden Sie sich bei Teams sind und ihre Zeitpläne in Schichten Auschecken und miteinander chatten.</span><span class="sxs-lookup"><span data-stu-id="586bc-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="586bc-178">Benutzer, die bereits mit StaffHub vertraut sind werden betriebsbereit schnell Schichten in.</span><span class="sxs-lookup"><span data-stu-id="586bc-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="586bc-179">Sie können Sie auch zur [Schichten](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) zusätzliche Hilfe verweisen.</span><span class="sxs-lookup"><span data-stu-id="586bc-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="586bc-180">Verschieben eines StaffHub-Teams (bald verfügbar)</span><span class="sxs-lookup"><span data-stu-id="586bc-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="586bc-181">Verwenden Sie folgende Schritte aus, um ein StaffHub Team gleichzeitig zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="586bc-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="586bc-182">Es wird empfohlen, diese Herangehensweise an die die pilot-Teams.</span><span class="sxs-lookup"><span data-stu-id="586bc-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="586bc-183">Später, wenn Sie zum Verschieben von Ihrer Organisation StaffHub Teams bereit sind, finden Sie unter Schritte zum Verschieben Sie mehrere Teams zu einem Zeitpunkt [Verschieben Ihrer StaffHub Teams](#move-your-staffhub-teams-coming-soon) .</span><span class="sxs-lookup"><span data-stu-id="586bc-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="586bc-184">Führen Sie Folgendes ein, um ein Team StaffHub verschieben.</span><span class="sxs-lookup"><span data-stu-id="586bc-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="586bc-185">Es folgt ein Beispiel der Antwort, die Sie erhalten, wenn Sie die Anforderung einer Verschiebung einer Team StaffHub Teams übermitteln.</span><span class="sxs-lookup"><span data-stu-id="586bc-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="586bc-186">Führen Sie folgenden Befehl zum Überprüfen des Status einer Anforderung verschieben.</span><span class="sxs-lookup"><span data-stu-id="586bc-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="586bc-187">Es folgt ein Beispiel der Antwort, die Sie erhalten, wenn eine Verschiebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="586bc-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="586bc-188">Nehmen Sie den Übergang von StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="586bc-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="586bc-189">Bewusstsein</span><span class="sxs-lookup"><span data-stu-id="586bc-189">Raise awareness</span></span>

<span data-ttu-id="586bc-190">Wenn können Sie jetzt Ihre pilot Teams hinausgehen, und Verschieben von Ihrer Organisation StaffHub Teams Teams, es ist wichtig, zuerst die Änderung in Ihrer Organisation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="586bc-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="586bc-191">Das Wort zu Schichten und den Übergang zu Teams Bewusstsein, Interesse generieren und bessere Akzeptanz verteilt.</span><span class="sxs-lookup"><span data-stu-id="586bc-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="586bc-192">Verschieben Sie die StaffHub-Teams (bald verfügbar)</span><span class="sxs-lookup"><span data-stu-id="586bc-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="586bc-193">Verwenden Sie folgende Schritte aus, um StaffHub Teams in einer Sammeloperation verschieben.</span><span class="sxs-lookup"><span data-stu-id="586bc-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="586bc-194">Sie können auswählen, verschieben Sie alle Ihrer Organisation StaffHub Teams oder bestimmte StaffHub Teams.</span><span class="sxs-lookup"><span data-stu-id="586bc-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="586bc-195">Wenn Sie, dass StaffHub teams, die jeweils einzeln verschieben möchten, finden Sie unter [Verschieben Sie ein Team StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="586bc-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="586bc-196">Verschieben Sie alle StaffHub-Teams (bald verfügbar)</span><span class="sxs-lookup"><span data-stu-id="586bc-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="586bc-197">Führen Sie Folgendes ein, um eine Liste aller StaffHub Teams in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="586bc-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="586bc-198">Führen Sie dann Folgendes ein, um alle Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="586bc-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="586bc-199">Es folgt ein Beispiel der Antwort.</span><span class="sxs-lookup"><span data-stu-id="586bc-199">Here's an example of the response.</span></span>

<span data-ttu-id="586bc-200">Für alle Teams, die bereits für Teams verschoben wurde oder bereits im Teams, wird die JobId "null" während ein Auftrags muss nicht zum Verschieben von diesem Teams übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="586bc-201">Verschieben Sie bestimmte StaffHub-Teams (bald verfügbar)</span><span class="sxs-lookup"><span data-stu-id="586bc-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="586bc-202">Führen Sie Folgendes ein, um eine Liste aller StaffHub Team Ids in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="586bc-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="586bc-203">In den zurückgegebenen Ergebnissen der `Get-StaffHubteamsForTenant` Cmdlet ausgeführt Sie zuvor, wählen Sie die Team-Ids, die Sie verschieben möchten, und klicken Sie dann eine durch Trennzeichen getrennten Werten (CSV)-Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="586bc-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="586bc-204">Hier ist ein Beispiel, wie die CSV-Datei formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="586bc-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="586bc-205">ID</span><span class="sxs-lookup"><span data-stu-id="586bc-205">Id</span></span>  |
|---------|
|<span data-ttu-id="586bc-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="586bc-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="586bc-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="586bc-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="586bc-208">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="586bc-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="586bc-209">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="586bc-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="586bc-210">Nachdem Sie die CSV-Datei erstellt haben, führen Sie Folgendes ein, um die Teams verschieben, den, die Sie in der CSV-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="586bc-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="586bc-211">Vergewissern Sie sich, dass Ihre StaffHub Teams Teams (bald verfügbar) verschoben wurden</span><span class="sxs-lookup"><span data-stu-id="586bc-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="586bc-212">Führen Sie Folgendes ein, um eine Liste aller Teams in Schichten in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="586bc-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="586bc-213">Überwachen der Verwendung von Teams</span><span class="sxs-lookup"><span data-stu-id="586bc-213">Monitor Teams usage</span></span>

<span data-ttu-id="586bc-214">Verwendungsberichte können Ihnen besser verstehen Verwendungsmuster und bieten Ihnen Insights an, wo Sie in Ihrer Organisation Schulung und Kommunikation Maßnahmen priorisieren.</span><span class="sxs-lookup"><span data-stu-id="586bc-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="586bc-215">Da Schichten ist eine app in Teams, können Sie die Verwendung durch Teams Berichte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="586bc-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="586bc-216">Weitere Informationen finden Sie unter [Teams Berichte in der Verwaltungskonsole von Microsoft-Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) und [Teams Berichte in der Microsoft-365-Verwaltungskonsole](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="586bc-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="586bc-217">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="586bc-217">Related topics</span></span>
- [<span data-ttu-id="586bc-218">Microsoft StaffHub soll eingestellt werden</span><span class="sxs-lookup"><span data-stu-id="586bc-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="586bc-219">Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="586bc-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="586bc-220">Referenz zu den StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="586bc-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
