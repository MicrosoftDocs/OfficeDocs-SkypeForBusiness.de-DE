---
title: Upgrade von Skype for Business Online auf Microsoft Teams | Bereitstellen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade auf Teams von Skype for Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b1cfb8302476983eeb5be180307bc143eb281dc
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548509"
---
<span data-ttu-id="07f63-103">![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Bereitstellung und Implementierung] (media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")</span><span class="sxs-lookup"><span data-stu-id="07f63-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="07f63-104">Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise.</span><span class="sxs-lookup"><span data-stu-id="07f63-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="07f63-105">Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="07f63-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="07f63-106">Ihre Projekt Beteiligten wurden eingetragen</span><span class="sxs-lookup"><span data-stu-id="07f63-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="07f63-107">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="07f63-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="07f63-108">Verständliche Koexistenz und Interoperabilität von Skype for Business und Teams</span><span class="sxs-lookup"><span data-stu-id="07f63-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="07f63-109">Ihre Upgrade-Reise gewählt</span><span class="sxs-lookup"><span data-stu-id="07f63-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="07f63-110">Ihre Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="07f63-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="07f63-111">Vorbereiten Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="07f63-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="07f63-112">Durchgeführt eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="07f63-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="07f63-113">Upgrade von Skype for Business Online auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="07f63-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="07f63-114">Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business Online vollständig bereitgestellt haben und Ihre Benutzer von Skype for Business auf Teams aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="07f63-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="07f63-115">Sie können Benutzer auf der Grundlage der von Ihrer Organisation ausgewählten Upgrade-Reise selektiv oder vollständig aktualisieren, indem Sie Ihren Benutzern den entsprechenden Koexistenz-und Aktualisierungsmodus zuweisen.</span><span class="sxs-lookup"><span data-stu-id="07f63-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="07f63-116">Zuweisen des Koexistenz-und Aktualisierungsmodus</span><span class="sxs-lookup"><span data-stu-id="07f63-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="07f63-117">Sie können Ihre Benutzer auf den TeamsOnly-Modus aktualisieren, indem Sie die UpgradeToTeams-Instanz von TeamsUpgradePolicy zuweisen, die mithilfe des Microsoft Teams admin Centers oder einer Skype for Business-Remote-Windows PowerShell-Sitzung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="07f63-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="07f63-118">Sie können dies entweder auf Benutzerbasis oder auf Mandantenebene tun, wenn Sie den gesamten Mandanten in einem Schritt ugprade möchten.</span><span class="sxs-lookup"><span data-stu-id="07f63-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="07f63-119">Weitere Informationen finden Sie unter [Festlegen von Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="07f63-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="07f63-120">Gleichzeitiges Aktualisieren aller Benutzer auf Teams</span><span class="sxs-lookup"><span data-stu-id="07f63-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="07f63-121">Führen Sie die folgenden Schritte aus, um alle Benutzer gleichzeitig auf Teams zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="07f63-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="07f63-122">Schritt 1: Benachrichtigen der Benutzer über die Änderung (optional)</span><span class="sxs-lookup"><span data-stu-id="07f63-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="07f63-123">Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen** > **Teams Upgrade**aus.</span><span class="sxs-lookup"><span data-stu-id="07f63-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="07f63-124">Ändern Sie unter **Koexistenzmodus**die Option **Skype for Business-Benutzer benachrichtigen, dass ein Upgrade auf Teams verfügbar ist** , auf ein. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="07f63-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="07f63-125">Schritt 2: Festlegen des Koexistenzmodus auf "TeamsOnly" für die Organisation</span><span class="sxs-lookup"><span data-stu-id="07f63-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="07f63-126">Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="07f63-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="07f63-127">Wählen Sie in der Dropdownliste **Koexistenzmodus** den Modus **nur Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="07f63-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="07f63-128">Stufenweises Aktualisieren von Benutzern</span><span class="sxs-lookup"><span data-stu-id="07f63-128">Upgrade users in stages</span></span>

<span data-ttu-id="07f63-129">Führen Sie die folgenden Schritte aus, wenn Sie Ihre Benutzer schrittweise auf TeamsOnly upgraden möchten.</span><span class="sxs-lookup"><span data-stu-id="07f63-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="07f63-130">Schritt 1: Identifizieren von Benutzergruppen für ein Upgrade</span><span class="sxs-lookup"><span data-stu-id="07f63-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="07f63-131">Oft können Organisationen beschließen, ihre Organisationen in Erfolgs Wellen von Benutzern zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="07f63-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="07f63-132">Sie sollten diese Benutzer zuerst identifizieren, damit Sie im Microsoft Teams Admin Center einfach nach diesen Benutzern suchen können.</span><span class="sxs-lookup"><span data-stu-id="07f63-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="07f63-133">Alternativ können Sie PowerShell verwenden, um dies effizienter zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="07f63-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="07f63-134">Nachdem Sie die Gruppe der Benutzer für eine bestimmte Upgrade-Welle identifiziert haben, fahren Sie mit den restlichen Schritten fort.</span><span class="sxs-lookup"><span data-stu-id="07f63-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="07f63-135">Schritt 2: Einrichten der Benachrichtigung für die Benutzer in der aktuellen ugprade-Welle (optional)</span><span class="sxs-lookup"><span data-stu-id="07f63-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="07f63-136">Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="07f63-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="07f63-137">Wählen Sie im Microsoft Teams Admin Center die Option **Benutzer**aus, und wählen Sie das Kontrollkästchen für bis zu 20 Benutzer aus, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="07f63-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="07f63-138">Wählen Sie in der oberen linken Ecke der ListView die Option **Einstellungen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="07f63-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="07f63-139">Ändern Sie im Bereich **Bearbeitungseinstellungen** auf der rechten Seite unter **Teams**-Upgrade **die Option Skype for Business-Benutzer** auf **ein**umschalten.</span><span class="sxs-lookup"><span data-stu-id="07f63-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="07f63-140">Hinweis: Wenn der Wert des Koexistenzmodus "org-Wide-Einstellungen verwenden" lautet, wird dieser Schalter nicht angezeigt, daher müssen Sie zuerst explizit den Koexistenzmodus für diese Benutzer auf den Standardwert für die Organisation festlegen.</span><span class="sxs-lookup"><span data-stu-id="07f63-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="07f63-141">Alternativ können Sie es einfacher finden, Benachrichtigungen für Gruppen von Benutzern gleichzeitig mithilfe von PowerShell zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="07f63-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="07f63-142">Schritt 3: Einrichten des Koexistenzmodus für Benutzer nur für Teams</span><span class="sxs-lookup"><span data-stu-id="07f63-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="07f63-143">Wenn Sie bereit sind, die Benutzer in der aktuellen Welle zu aktualisieren, um Teams als ihre einzige Anwendung zu verwenden, legen Sie den Koexistenzmodus für die Benutzer nur auf Teams fest.</span><span class="sxs-lookup"><span data-stu-id="07f63-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="07f63-144">Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="07f63-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="07f63-145">Wählen Sie im Microsoft Teams Admin Center die Option **Benutzer**aus, und aktivieren Sie dann das Kontrollkästchen für bis zu 20 Benutzer.</span><span class="sxs-lookup"><span data-stu-id="07f63-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="07f63-146">Wählen Sie in der oberen linken Ecke der ListView die Option **Einstellungen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="07f63-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="07f63-147">Legen Sie im Bereich " **Einstellungen bearbeiten** " auf der rechten Seite unter " **Teams-Upgrade** " den Koexistenzmodus nur in der Dropdownliste auf " **Teams** " fest.</span><span class="sxs-lookup"><span data-stu-id="07f63-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="07f63-148">Alternativ können Sie es einfacher finden, Gruppen von Benutzern gleichzeitig mithilfe von PowerShell zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="07f63-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="07f63-149">Schritt 4: Wiederholen Sie die Schritte 1-3 für aufeinander folgende Wellen von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="07f63-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="07f63-150">Wiederholen Sie die vorherigen Schritte, um TeamsOnly auf weitere Benutzer anzuwenden, während Sie Ihr Upgrade auf den Modus nur für Teams überprüfen und bereit zum Erweitern sind.</span><span class="sxs-lookup"><span data-stu-id="07f63-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="07f63-151">Upgrade für Telefonsysteme und Teams</span><span class="sxs-lookup"><span data-stu-id="07f63-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="07f63-152">Wenn Ihre Skype for Business Online-Bereitstellung Telefon System mit Anrufplänen umfasst und Microsoft Ihr PSTN-Anbieter (Public Switched Telephone Network) ist, wird durch das Upgrade Ihrer Benutzer auf Teams automatisch ein eingehender PSTN-Anruf an Teams weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="07f63-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="07f63-153">Wenn Ihre Skype for Business Online-Bereitstellung das Telefonsystem mit Cloud Connector Edition umfasst, lesen Sie die [zusätzlichen Überlegungen zur direkten Weiterleitung von Telefonsystemen](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="07f63-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
