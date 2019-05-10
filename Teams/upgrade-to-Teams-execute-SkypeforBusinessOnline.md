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
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc1334e019abadb030199518df15b0dde74dde52
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835335"
---
<span data-ttu-id="e556f-103">![Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase] (media/upgrade-banner-deployment.png "Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase")</span><span class="sxs-lookup"><span data-stu-id="e556f-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e556f-104">Dieser Artikel ist Teil der Bereitstellung und Implementierung Stufe der Ihrem Upgrade Weg.</span><span class="sxs-lookup"><span data-stu-id="e556f-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e556f-105">Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="e556f-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="e556f-106">Ihre Projektbeteiligten eingetragen</span><span class="sxs-lookup"><span data-stu-id="e556f-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e556f-107">Definiert die Projektumfang</span><span class="sxs-lookup"><span data-stu-id="e556f-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e556f-108">Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden</span><span class="sxs-lookup"><span data-stu-id="e556f-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e556f-109">Ihre Reise Upgrade ausgewählt</span><span class="sxs-lookup"><span data-stu-id="e556f-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e556f-110">Die Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="e556f-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="e556f-111">Ihre Organisation vorbereitet</span><span class="sxs-lookup"><span data-stu-id="e556f-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="e556f-112">Ein Pilotprojekt durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="e556f-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="e556f-113">Upgrade von Skype for Business Online auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e556f-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="e556f-114">Führen Sie die Anweisungen in diesem Artikel, wenn Sie vollständig Skype für Business Online bereitgestellt haben und Ihre Benutzer von Skype für Unternehmen, die Teams aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e556f-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="e556f-115">Sie können Benutzer selektiv aktualisieren oder-Ansatz repräsentieren, basierend auf das Upgrade journey, die Ihrer Organisation ausgewählt hat, durch Ihre Benutzer die entsprechenden Koexistenz und Aktualisierungsmodus zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e556f-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="e556f-116">Weisen Sie den Modus für Upgrade und Koexistenz</span><span class="sxs-lookup"><span data-stu-id="e556f-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="e556f-117">Sie können Ihre Benutzer in den Modus TeamsOnly aktualisieren, durch Zuweisen der UpgradeToTeams Instanz des TeamsUpgradePolicy, die über das Microsoft-Teams, Administrationscenter oder einen Skype für Business remote Windows Powershell-Sitzung durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e556f-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="e556f-118">Sie können für jeden Benutzer einzeln oder für einzelne Mandanten geltende vorgehen, wenn Sie den gesamten Mandanten in einem Schritt Ugprade möchten.</span><span class="sxs-lookup"><span data-stu-id="e556f-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="e556f-119">Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="e556f-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="e556f-120">Aktualisieren Sie alle Benutzer gleichzeitig auf Teams</span><span class="sxs-lookup"><span data-stu-id="e556f-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="e556f-121">Befolgen Sie diese Schritte, um alle Benutzer gleichzeitig auf Teams aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e556f-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="e556f-122">Schritt 1: Fordern Sie die Benutzer der Änderung (optional)</span><span class="sxs-lookup"><span data-stu-id="e556f-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="e556f-123">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Org geltende Einstellungen** > **Teams zu aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="e556f-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="e556f-124">Ändern Sie die Option **Benachrichtigen Skype für Unternehmensbenutzer, dass ein Upgrade auf Teams verfügbar ist** unter **Koexistenzmodus**auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="e556f-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="e556f-125">Schritt 2: Legen Sie den Koexistenzmodus auf TeamsOnly für die Organisation</span><span class="sxs-lookup"><span data-stu-id="e556f-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="e556f-126">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Org geltende Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="e556f-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="e556f-127">Wählen Sie aus der Dropdownliste **Koexistenzmodus** **Teams** nur Kopfzeilen herunterladen aus.</span><span class="sxs-lookup"><span data-stu-id="e556f-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="e556f-128">Aktualisieren Sie die Benutzer in Phasen</span><span class="sxs-lookup"><span data-stu-id="e556f-128">Upgrade users in stages</span></span>

<span data-ttu-id="e556f-129">Gehen Sie folgendermaßen vor, wenn Ihre Benutzer auf TeamsOnly schrittweise aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e556f-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="e556f-130">Schritt 1: Identifizieren der Gruppen von Benutzern für das upgrade</span><span class="sxs-lookup"><span data-stu-id="e556f-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="e556f-131">Häufig Organisationen möglicherweise entscheiden sich für Organisationen in Erfolg hochrangige von Benutzern zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e556f-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="e556f-132">Sie sollten diese Benutzer zuerst zu identifizieren, damit Sie auf einfache Weise in der Verwaltungskonsole von Microsoft-Teams suchen können.</span><span class="sxs-lookup"><span data-stu-id="e556f-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e556f-133">Alternativ können Sie PowerShell effizienter dazu verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e556f-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="e556f-134">Nachdem Sie die Gruppe von Benutzern für eine bestimmte Upgrade Welle identifiziert haben, fahren Sie mit der restlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="e556f-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="e556f-135">Schritt 2: Einrichten der Benachrichtigung für die Benutzer in der aktuellen Ugprade Welle (optional)</span><span class="sxs-lookup"><span data-stu-id="e556f-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="e556f-136">Wenn Sie das Microsoft-Teams, Administrationscenter verwenden, können Sie gleichzeitig TeamsUpgradePolicy für bis zu 20 Benutzer konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e556f-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="e556f-137">Kontrollkästchen Sie in der Verwaltungskonsole von Microsoft-Teams **Benutzer**, und suchen und mit mehreren auswählen das für bis zu 20 Benutzer, die aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e556f-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="e556f-138">Wählen Sie in der oberen linken Ecke des Listview **Einstellungen bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="e556f-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="e556f-139">Ändern Sie im Bereich **Einstellungen bearbeiten** auf der rechten Seite unter **Aktualisieren von Teams** **Benachrichtigen der Skype für Geschäftsbenutzer** Switch auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="e556f-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="e556f-140">Hinweis: Wenn der Wert der Koexistenzmodus "Einstellungen für Verwendung Org geltende" ist, wird dieser Option nicht angezeigt, müssen Sie zunächst explizit festlegen den Koexistenz-Modus für diese Benutzer auf den Inhalt der Standardwert für die org ist</span><span class="sxs-lookup"><span data-stu-id="e556f-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="e556f-141">Alternativ können Sie zum Aktivieren von Benachrichtigungen für Gruppen von Benutzern, die gleichzeitig von PowerShell einfacher.</span><span class="sxs-lookup"><span data-stu-id="e556f-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="e556f-142">Schritt 3: Festlegen des Koexistenzmodus für Benutzer nur Teams</span><span class="sxs-lookup"><span data-stu-id="e556f-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="e556f-143">Wenn Sie die Benutzer in der aktuellen Welle zum Verwenden von Teams als einzige Programmversionen aktualisieren möchten, legen Sie den Modus Koexistenz für die Benutzer nur Teams.</span><span class="sxs-lookup"><span data-stu-id="e556f-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="e556f-144">Wenn Sie das Microsoft-Teams, Administrationscenter verwenden, können Sie gleichzeitig TeamsUpgradePolicy für bis zu 20 Benutzer konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e556f-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="e556f-145">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams **Benutzer**aus, und klicken Sie dann das Kontrollkästchen für bis zu 20 Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e556f-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="e556f-146">Wählen Sie in der oberen linken Ecke des Listview **Einstellungen bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="e556f-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="e556f-147">Klicken Sie im Bereich **Einstellungen bearbeiten** auf der rechten Seite unter **Aktualisieren von Teams** Abschnitt legen Sie die Koexistenz auf **Teams nur** in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="e556f-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="e556f-148">Alternativ können Sie Gruppen von Benutzern, die gleichzeitig von PowerShell aktualisieren einfacher.</span><span class="sxs-lookup"><span data-stu-id="e556f-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="e556f-149">Schritt 4: Wiederholen Sie die Schritte 1 bis 3 für aufeinander folgende hochrangige von Benutzern</span><span class="sxs-lookup"><span data-stu-id="e556f-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="e556f-150">Beim Überprüfen des Upgrades auf Teams nur Kopfzeilen herunterladen und zum Erweitern bereit sind, wiederholen Sie die vorherigen Schritte, um TeamsOnly auf mehrere Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="e556f-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e556f-151">Upgrade Telefonsystem und Teams</span><span class="sxs-lookup"><span data-stu-id="e556f-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e556f-152">Wenn Ihre Skype für Business Online-Bereitstellung Telefonsystem mit Aufrufen plant umfasst und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) ist, wird Aktualisieren Ihrer Benutzer auf Teams automatisch eingehende PSTN-Aufruf von Teams umzustellen.</span><span class="sxs-lookup"><span data-stu-id="e556f-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e556f-153">Wenn Ihre Skype für Business Online Bereitstellung Telefonsystem mit Cloud Connector Edition umfasst, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e556f-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
