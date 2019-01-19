---
title: Aktualisieren von Skype für Unternehmen, die Microsoft-Teams Online | Bereitstellen
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen für das Upgrade auf Teams von Skype für Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44f3cdad4ab65935c2721244364861db7a140f15
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349295"
---
<span data-ttu-id="df474-103">![Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase] (media/upgrade-banner-deployment.png "Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase")</span><span class="sxs-lookup"><span data-stu-id="df474-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="df474-104">Dieser Artikel ist Teil der Bereitstellung und Implementierung Stufe der Ihrem Upgrade Weg.</span><span class="sxs-lookup"><span data-stu-id="df474-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="df474-105">Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="df474-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="df474-106">Ihre Projektbeteiligten eingetragen</span><span class="sxs-lookup"><span data-stu-id="df474-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="df474-107">Definiert die Projektumfang</span><span class="sxs-lookup"><span data-stu-id="df474-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="df474-108">Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden</span><span class="sxs-lookup"><span data-stu-id="df474-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="df474-109">Ihre Reise Upgrade ausgewählt</span><span class="sxs-lookup"><span data-stu-id="df474-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="df474-110">Die Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="df474-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="df474-111">Ihre Organisation vorbereitet</span><span class="sxs-lookup"><span data-stu-id="df474-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="df474-112">Ein Pilotprojekt durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="df474-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="df474-113">Aktualisieren von Skype für Unternehmen Online auf Teams</span><span class="sxs-lookup"><span data-stu-id="df474-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="df474-114">Führen Sie die Anweisungen in diesem Artikel, wenn Sie vollständig Skype für Business Online bereitgestellt haben und Ihre Benutzer von Skype für Unternehmen, die Teams aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="df474-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="df474-115">Sie können Benutzer selektiv aktualisieren oder-Ansatz repräsentieren, basierend auf das Upgrade journey, die Ihrer Organisation ausgewählt hat, durch Ihre Benutzer die entsprechenden Koexistenz und Aktualisierungsmodus zuweisen.</span><span class="sxs-lookup"><span data-stu-id="df474-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="df474-116">Weisen Sie den Modus für Upgrade und Koexistenz</span><span class="sxs-lookup"><span data-stu-id="df474-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="df474-117">Sie können die Benutzer von Teams, die durch Zuweisen von den TeamsOnly Modus der TeamsUpgradePolicy, die ausgeführt werden kann, unter Verwendung der Microsoft-Teams & Skype für Business Admin Center oder einen Skype für Business remote Windows Powershell-Sitzung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="df474-117">You can upgrade your users by Teams by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="df474-118">Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="df474-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="df474-119">Aktualisieren Sie alle Benutzer gleichzeitig auf Teams</span><span class="sxs-lookup"><span data-stu-id="df474-119">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="df474-120">Befolgen Sie diese Schritte, um alle Benutzer gleichzeitig auf Teams aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="df474-120">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change"></a><span data-ttu-id="df474-121">Schritt 1: Fordern Sie die Benutzer der Änderung</span><span class="sxs-lookup"><span data-stu-id="df474-121">Step 1: Notify the users of the change</span></span>

1. <span data-ttu-id="df474-122">Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen** > **Teams zu aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="df474-122">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="df474-123">Ändern Sie die Option **Benachrichtigen Skype für Unternehmensbenutzer, dass ein Upgrade auf Teams verfügbar ist** unter **Koexistenzmodus**auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="df474-123">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a><span data-ttu-id="df474-124">Schritt 2: Festlegen des Koexistenzmodus für die Benutzer</span><span class="sxs-lookup"><span data-stu-id="df474-124">Step 2: Set the coexistence mode for the users</span></span>

1. <span data-ttu-id="df474-125">Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="df474-125">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="df474-126">Wählen Sie aus der Dropdownliste **Koexistenzmodus** **Teams** nur Kopfzeilen herunterladen aus.</span><span class="sxs-lookup"><span data-stu-id="df474-126">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="df474-127">Aktualisieren Sie die Benutzer in Phasen</span><span class="sxs-lookup"><span data-stu-id="df474-127">Upgrade users in stages</span></span>

<span data-ttu-id="df474-128">Gehen Sie folgendermaßen vor, wenn Sie Ihren Benutzern, Teams schrittweise aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="df474-128">Follow these steps if you want to gradually upgrade your users to Teams.</span></span>

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a><span data-ttu-id="df474-129">Schritt 1: Erstellen Sie Ihrer Benutzer Kohorten für das upgrade</span><span class="sxs-lookup"><span data-stu-id="df474-129">Step 1: Create your user cohorts for the upgrade</span></span>

<span data-ttu-id="df474-130">Benutzer Kohorten sind Gruppen von Benutzern, die gleichzeitig in Teams nur Kopfzeilen herunterladen verschoben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="df474-130">User cohorts are groups of users who will be moved to Teams Only mode at the same time.</span></span>

<span data-ttu-id="df474-131">Erstellen Sie Ihre Benutzer Kohorten (Add Link zur Seite zur Auswahl)</span><span class="sxs-lookup"><span data-stu-id="df474-131">To create your user cohorts (Add link to user selection page)</span></span>

### <a name="step-2-set-the-user-mode-to-islands"></a><span data-ttu-id="df474-132">Schritt 2: Festlegen des Benutzermodus Inseln</span><span class="sxs-lookup"><span data-stu-id="df474-132">Step 2: Set the user mode to Islands</span></span>

1. <span data-ttu-id="df474-133">Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Benutzer**aus, und wählen Sie dann einen Benutzer Kohorte aus.</span><span class="sxs-lookup"><span data-stu-id="df474-133">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="df474-134">Neben der **Aktualisierung von Teams**wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="df474-134">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="df474-135">Wählen Sie im Bereich **Teams zu aktualisieren** , klicken Sie unter **Koexistenzmodus** **Inseln** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="df474-135">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Islands** from the drop-down list.</span></span>

### <a name="step-3-set-notification-for-the-user-optional"></a><span data-ttu-id="df474-136">Schritt 3: Einrichten der Benachrichtigung für den Benutzer (optional)</span><span class="sxs-lookup"><span data-stu-id="df474-136">Step 3: Set notification for the user (optional)</span></span>

1. <span data-ttu-id="df474-137">Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Benutzer**aus, und wählen Sie einen Benutzer Kohorte aus.</span><span class="sxs-lookup"><span data-stu-id="df474-137">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and select a user cohort.</span></span>
2. <span data-ttu-id="df474-138">Neben der **Aktualisierung von Teams**wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="df474-138">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="df474-139">Ändern Sie im Bereich **Teams Upgrade** unter **Koexistenzmodus** **Benachrichtigen der Skype für Geschäftsbenutzer** Switch auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="df474-139">In the **Teams Upgrade** pane, under **Coexistence mode**, change **Notify the Skype for Business user** switch to **On**.</span></span>

### <a name="step-4-set-the-user-mode-to-teams-only"></a><span data-ttu-id="df474-140">Schritt 4: Festlegen des Benutzermodus nur Teams</span><span class="sxs-lookup"><span data-stu-id="df474-140">Step 4: Set the user mode to Teams Only</span></span>

<span data-ttu-id="df474-141">Wenn Sie die Benutzer zum Verwenden von Teams als einzige Programmversionen aktualisieren möchten, legen Sie den Modus der Koexistenz für den Benutzer nur Teams.</span><span class="sxs-lookup"><span data-stu-id="df474-141">When you are ready to upgrade the users to use Teams as their only application, set the Coexistence mode for the user to Teams Only.</span></span>

1. <span data-ttu-id="df474-142">Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Benutzer**aus, und wählen Sie dann einen Benutzer Kohorte aus.</span><span class="sxs-lookup"><span data-stu-id="df474-142">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="df474-143">Neben der **Aktualisierung von Teams**wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="df474-143">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="df474-144">Wählen Sie das **Aktualisieren von Teams** unter **Koexistenzmodus**im Bereich **Teams nur** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="df474-144">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Teams Only** from the drop-down list.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="df474-145">Upgrade Telefonsystem und Teams</span><span class="sxs-lookup"><span data-stu-id="df474-145">Phone System and Teams upgrade</span></span>

<span data-ttu-id="df474-146">Wenn Ihre Skype für Business Online-Bereitstellung Telefonsystem mit Aufrufen plant umfasst und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) ist, wird Aktualisieren Ihrer Benutzer auf Teams automatisch eingehende PSTN-Aufruf von Teams umzustellen.</span><span class="sxs-lookup"><span data-stu-id="df474-146">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="df474-147">Wenn Ihre Skype für Business Online Bereitstellung Telefonsystem mit Cloud Connector Edition umfasst, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="df474-147">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>