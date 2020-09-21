---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955902"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="f88e1-103">Implementieren Ihres Upgrades von Skype for Business in Teams &mdash; für IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="f88e1-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="f88e1-104">In diesem Artikel wird beschrieben, wie Sie Ihr Upgrade implementieren.</span><span class="sxs-lookup"><span data-stu-id="f88e1-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="f88e1-105">Dieser Artikel ist der fünfte von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f88e1-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="f88e1-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f88e1-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="f88e1-107">Upgrade-Methoden</span><span class="sxs-lookup"><span data-stu-id="f88e1-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="f88e1-108">Tools zum Verwalten des Upgrades</span><span class="sxs-lookup"><span data-stu-id="f88e1-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="f88e1-109">Weitere Überlegungen für Organisationen mit Skype for Business lokal</span><span class="sxs-lookup"><span data-stu-id="f88e1-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="f88e1-110">**Implementieren des Upgrades** (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="f88e1-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="f88e1-111">Überlegungen zum Public Switched Telephone Network (PSTN)</span><span class="sxs-lookup"><span data-stu-id="f88e1-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="f88e1-112">Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f88e1-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="f88e1-113">Koexistenz von Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f88e1-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="f88e1-114">Koexistenzmodus – Referenz</span><span class="sxs-lookup"><span data-stu-id="f88e1-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="f88e1-115">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="f88e1-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="f88e1-116">Aktualisierungsoptionen</span><span class="sxs-lookup"><span data-stu-id="f88e1-116">Upgrade options</span></span>

<span data-ttu-id="f88e1-117">In diesem Abschnitt wird beschrieben, wie Sie das Upgrade mithilfe einer der folgenden Aktualisierungsoptionen implementieren:</span><span class="sxs-lookup"><span data-stu-id="f88e1-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="f88e1-118">Überlappende Funktionen Upgrade (im Modus "Inseln")</span><span class="sxs-lookup"><span data-stu-id="f88e1-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="f88e1-119">Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat</span><span class="sxs-lookup"><span data-stu-id="f88e1-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="f88e1-120">Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inseln-Modus verwendet</span><span class="sxs-lookup"><span data-stu-id="f88e1-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="f88e1-121">Wenn Sie weitere Informationen zu den Optionen benötigen, stellen Sie sicher, dass Sie die [Upgrade-Methoden](upgrade-to-teams-on-prem-upgrade-methods.md)bereits gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="f88e1-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="f88e1-122">Überlappende Funktionen Upgrade (im Modus "Inseln")</span><span class="sxs-lookup"><span data-stu-id="f88e1-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="f88e1-123">Für die Option zum überlappenden Funktions Upgrade:</span><span class="sxs-lookup"><span data-stu-id="f88e1-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="f88e1-124">Bedenken Sie diese Option, wenn Sie ein schnelles Upgrade für Ihre gesamte Organisation durchführen können.</span><span class="sxs-lookup"><span data-stu-id="f88e1-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="f88e1-125">Da es potenzielle Verwirrungs Risiken für Endbenutzer mit der Ausführung beider Clients gibt, ist es am besten, wenn Sie den Zeitraum minimieren können, in dem Benutzer beide Clients ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="f88e1-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="f88e1-126">Sie sollten sicherstellen, dass Ihre Benutzer wissen, dass beide Clients ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f88e1-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="f88e1-127">Bei dieser Option handelt es sich um das Out-of-the-Box-Modell, das keine Administratoraktion erfordert, um mit Teams zu beginnen, es sei denn, Sie weisen die Microsoft 365-oder Office 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="f88e1-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="f88e1-128">Wenn Ihre Benutzer bereits über Skype for Business Online verfügen, sind Sie möglicherweise bereits in diesem Modell.</span><span class="sxs-lookup"><span data-stu-id="f88e1-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="f88e1-129">Es kann schwierig sein, den überlappenden Funktionsmodus zu verlassen und zu TeamsOnly zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="f88e1-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="f88e1-130">Da aktualisierte Benutzer nur über Teams kommunizieren, müssen alle anderen Benutzer in der Organisation, die mit diesem Benutzer kommunizieren, Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="f88e1-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="f88e1-131">Wenn Sie über Benutzer verfügen, die nicht mit der Verwendung von Teams begonnen haben, werden Sie fehlenden Nachrichten ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f88e1-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="f88e1-132">Darüber hinaus werden die TeamsOnly-Benutzer in Skype for Business nicht online angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f88e1-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="f88e1-133">Einige Organisationen entscheiden sich für ein mandantenweites Upgrade mit der globalen Mandanten-Richtlinie, um dies zu vermeiden, was jedoch eine Vorausplanung erfordert und wartet, bis alle Benutzer zum Upgrade bereit sind.</span><span class="sxs-lookup"><span data-stu-id="f88e1-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="f88e1-134">Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat</span><span class="sxs-lookup"><span data-stu-id="f88e1-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="f88e1-135">Wenn in Ihrer Organisation noch keine aktiven Benutzer in Teams vorhanden sind, besteht der erste Schritt darin, die standardmäßige Mandantenweite Richtlinie für TeamsUpgradePolicy auf einen der Skype for Business-Modi zu setzen, beispielsweise SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="f88e1-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="f88e1-136">Benutzer, die noch nicht mit der Verwendung von Teams begonnen haben, bemerken keinen Unterschied im Verhalten.</span><span class="sxs-lookup"><span data-stu-id="f88e1-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="f88e1-137">Durch das Festlegen dieser Richtlinie auf Mandantenebene ist es jedoch möglich, Benutzer auf den TeamsOnly-Modus zu aktualisieren und sicherzustellen, dass die aktualisierten Benutzer weiterhin mit nicht aktualisierten Benutzern kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="f88e1-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="f88e1-138">Nachdem Sie Ihre Pilotbenutzer identifiziert haben, können Sie Sie auf TeamsOnly aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f88e1-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="f88e1-139">Wenn Sie lokal sind, verwenden Sie Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="f88e1-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="f88e1-140">Wenn Sie online sind, weisen Sie Ihnen einfach den TeamsOnly-Modus mithilfe von Grant-CsTeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="f88e1-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="f88e1-141">Standardmäßig werden alle von diesen Benutzern geplanten Skype for Business-Besprechungen in Teams migriert.</span><span class="sxs-lookup"><span data-stu-id="f88e1-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="f88e1-142">Im folgenden finden Sie die wichtigsten Befehle:</span><span class="sxs-lookup"><span data-stu-id="f88e1-142">Following are the key commands:</span></span>

1. <span data-ttu-id="f88e1-143">Setzen Sie die Mandantenweite Standardeinstellung auf Mode SfbWithTeamsCollab wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f88e1-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="f88e1-144">Aktualisieren Sie die Pilotbenutzer auf TeamsOnly wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f88e1-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="f88e1-145">Für einen Benutzer, der Online ist:</span><span class="sxs-lookup"><span data-stu-id="f88e1-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="f88e1-146">Für einen lokalen Benutzer:</span><span class="sxs-lookup"><span data-stu-id="f88e1-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="f88e1-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f88e1-147">Notes</span></span>
 
- <span data-ttu-id="f88e1-148">Anstatt die Mandantenweite Richtlinie auf "SfbWithTeamsCollab" festzulegen, können Sie Sie auf "SfbWithTeamsCollabAndMeetings" festlegen.</span><span class="sxs-lookup"><span data-stu-id="f88e1-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="f88e1-149">Dies bewirkt, dass alle Benutzer alle neuen Besprechungen in Teams planen.</span><span class="sxs-lookup"><span data-stu-id="f88e1-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="f88e1-150">`Move-CsUser` ist ein Cmdlet in den lokalen Tools.</span><span class="sxs-lookup"><span data-stu-id="f88e1-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="f88e1-151">Für den `MoveToTeams` Switch ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f88e1-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="f88e1-152">Wenn Sie eine frühere Version verwenden, können Sie den Benutzer zunächst in Skype for Business Online verschieben und dann dem Benutzer den TeamsOnly-Modus erteilen.</span><span class="sxs-lookup"><span data-stu-id="f88e1-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="f88e1-153">Standardmäßig werden Skype for Business-Besprechungen in Teams migriert, wenn Sie auf den TeamsOnly-Modus aktualisieren oder den SfbWithTeamsCollabAndMeetings-Modus zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f88e1-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="f88e1-154">Das folgende Diagramm zeigt die konzeptionellen Phasen des Upgrades von SELECT-Funktionen für eine Organisation ohne vorherige Verwendung von Teams.</span><span class="sxs-lookup"><span data-stu-id="f88e1-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="f88e1-155">Die Höhe der Balken steht für die Anzahl der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f88e1-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="f88e1-156">In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="f88e1-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="f88e1-157">Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzern über Interop und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f88e1-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="f88e1-158">Benutzer im Inseln-Modus müssen sicherstellen, dass beide Clients ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f88e1-158">Users in Islands mode must be sure to run both clients.</span></span>

![Diagramm mit Auswahlmöglichkeiten für Upgrades ohne vorherige Verwendung von Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="f88e1-160">Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inseln-Modus verwendet</span><span class="sxs-lookup"><span data-stu-id="f88e1-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="f88e1-161">Wenn einige Benutzer in Ihrer Organisation Teams im Modus "Inseln" aktiv verwenden, möchten Sie möglicherweise die Funktionalität von vorhandenen Benutzern nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="f88e1-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="f88e1-162">Daher ist ein zusätzlicher Schritt erforderlich, bevor die Mandantenweite Richtlinie geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f88e1-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="f88e1-163">Die Lösung besteht darin, diese vorhandenen aktiven Teams-Benutzer in den Modus "Inseln" zu übersetzen, bevor Sie die Mandantenweite Richtlinie auf "SfbWithTeamsCollab" festlegen.</span><span class="sxs-lookup"><span data-stu-id="f88e1-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="f88e1-164">Nachdem Sie dies abgeschlossen haben, können Sie die Bereitstellung wie oben beschrieben fortsetzen, jedoch haben Sie zwei Gruppen von Benutzern, die zu TeamsOnly wechseln: die Benutzer, die in Teams aktiv waren, befinden sich im Modus "Inseln", und die restlichen Benutzer befinden sich im SfbWithTeamsCollab-Modus.</span><span class="sxs-lookup"><span data-stu-id="f88e1-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="f88e1-165">Sie können diese Benutzer schrittweise in den TeamsOnly-Modus verschieben.</span><span class="sxs-lookup"><span data-stu-id="f88e1-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="f88e1-166">Suchen Sie nach Benutzern, die in Teams wie folgt aktiv sind:</span><span class="sxs-lookup"><span data-stu-id="f88e1-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="f88e1-167">Wechseln Sie im Microsoft 365 Admin Center in der Navigationsleiste auf der linken Seite zu Berichte, und verwenden Sie dann die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f88e1-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="f88e1-168">Wählen Sie im Dropdownmenü "Bericht auswählen" den Eintrag Microsoft Teams und dann Benutzeraktivität aus.</span><span class="sxs-lookup"><span data-stu-id="f88e1-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="f88e1-169">Dadurch wird eine exportierbare Tabelle mit Benutzern bereitgestellt, die in Teams aktiv waren.</span><span class="sxs-lookup"><span data-stu-id="f88e1-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="f88e1-170">Klicken Sie auf exportieren, öffnen Sie Excel, und Filtern Sie, um nur die Benutzer anzuzeigen, die in Teams aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="f88e1-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="f88e1-171">Weisen Sie für jeden in Schritt 1 gefundenen aktiven Teams-Benutzer den Modus "Inseln" in der Remote-PowerShell zu.</span><span class="sxs-lookup"><span data-stu-id="f88e1-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="f88e1-172">So können Sie mit dem nächsten Schritt fortfahren und sicherstellen, dass Sie die Benutzeroberfläche nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="f88e1-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="f88e1-173">Setzen Sie die Mandantenweite Richtlinie auf SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="f88e1-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="f88e1-174">Ausgewählte Benutzer auf den TeamsOnly-Modus aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f88e1-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="f88e1-175">Sie können entweder Benutzer im Inseln-Modus oder im SfbWithTeamsCollab-Modus aktualisieren, obwohl Sie möglicherweise zuerst die Aktualisierung der Benutzer im Modus "Inseln" priorisieren möchten, um die Verwirrung zu minimieren, die entstehen kann, wenn sich Benutzer im Inseln-Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="f88e1-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="f88e1-176">Für Benutzer, die in Skype for Business Online verwaltet werden:</span><span class="sxs-lookup"><span data-stu-id="f88e1-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="f88e1-177">Für Benutzer, die in Skype for Business Server lokal verwaltet werden:</span><span class="sxs-lookup"><span data-stu-id="f88e1-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="f88e1-178">Das folgende Diagramm zeigt die konzeptionellen Phasen eines Auswahl Funktions Übergangs, in dem am Anfang aktive Inseln-Benutzer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f88e1-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="f88e1-179">Die Höhe der Balken steht für die Anzahl der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f88e1-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="f88e1-180">In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="f88e1-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="f88e1-181">Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzern über Interop und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f88e1-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagramm mit Auswahlmöglichkeiten für das Upgrade für aktive Benutzer im Modus "Inseln"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="f88e1-183">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="f88e1-183">Related links</span></span>

[<span data-ttu-id="f88e1-184">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="f88e1-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="f88e1-185">Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="f88e1-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="f88e1-186">Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud</span><span class="sxs-lookup"><span data-stu-id="f88e1-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="f88e1-187">Festlegen Ihrer Einstellungen für Koexistenz und Upgrades</span><span class="sxs-lookup"><span data-stu-id="f88e1-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="f88e1-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f88e1-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="f88e1-189">Verwenden des Besprechungs Migrations Diensts (MMS)</span><span class="sxs-lookup"><span data-stu-id="f88e1-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

