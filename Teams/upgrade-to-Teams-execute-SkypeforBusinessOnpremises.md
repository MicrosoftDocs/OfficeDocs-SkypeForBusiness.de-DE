---
title: Aktualisieren von Skype für lokale Teams für Microsoft Business | Bereitstellen von | Lync
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 'Überlegungen für das Upgrade auf Teams aus einer Skype, for Business: Bereitstellung lokal.'
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5628b0bb382ef12580bb7bab12dca13e288fead7
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349335"
---
<span data-ttu-id="bd6d6-103">![Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase] (media/upgrade-banner-deployment.png "Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase")</span><span class="sxs-lookup"><span data-stu-id="bd6d6-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="bd6d6-104">Dieser Artikel ist Teil der Bereitstellung und Implementierung Stufe der Ihrem Upgrade Weg.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="bd6d6-105">Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="bd6d6-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="bd6d6-106">Ihre Projektbeteiligten eingetragen</span><span class="sxs-lookup"><span data-stu-id="bd6d6-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="bd6d6-107">Definiert die Projektumfang</span><span class="sxs-lookup"><span data-stu-id="bd6d6-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="bd6d6-108">Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden</span><span class="sxs-lookup"><span data-stu-id="bd6d6-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="bd6d6-109">Ihre Reise Upgrade ausgewählt</span><span class="sxs-lookup"><span data-stu-id="bd6d6-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="bd6d6-110">Die Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="bd6d6-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="bd6d6-111">Ihre Organisation vorbereitet</span><span class="sxs-lookup"><span data-stu-id="bd6d6-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="bd6d6-112">Ein Pilotprojekt durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="bd6d6-113">Upgrade von einer Skype für die lokale Bereitstellung Business auf Teams</span><span class="sxs-lookup"><span data-stu-id="bd6d6-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="bd6d6-114">Führen Sie die Anweisungen in diesem Artikel, wenn Sie Skype für Unternehmen bereitgestellt haben oder lokalen Microsoft Lync und Ihre Organisation möchte Teams entweder selektiv upgrade – mithilfe von mehreren Koexistenz Modi – oder-Ansatz repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="bd6d6-115">Im erste Schritt wird zum Einrichten von hybridkonnektivität mit Ihrem Office 365-Mandanten, und verschieben Sie Ihre Benutzer zu Skype für Business Online und weisen Sie ihnen die entsprechende Koexistenz und Aktualisierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="bd6d6-116">Schritt 1: Bereitstellen von hybridkonnektivität</span><span class="sxs-lookup"><span data-stu-id="bd6d6-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="bd6d6-117">Die wichtige Voraussetzung für die Aktualisierung auf Teams ist zum Bereitstellen von hybridkonnektivität.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="bd6d6-118">Dies kann neue externe Konnektivität für Ihre vorhandenen Skype für Business oder Lync-Bereitstellung bereitstellen oder einfach mit Ihrem Office 365-Mandanten Konfigurieren einer hybriden Beziehungs umfassen.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="bd6d6-119">Weitere Informationen finden Sie unter [Deploy hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="bd6d6-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="bd6d6-120">Schritt 2: Migrieren von Benutzern zu Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="bd6d6-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="bd6d6-121">Nachdem Sie Ihre Hybriden Setup abgeschlossen haben, verschieben Sie Benutzer in Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span>

<span data-ttu-id="bd6d6-122">Weitere Informationen finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="bd6d6-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="bd6d6-123">Schritt 3: Zuweisen einer Koexistenz und Aktualisierungsmodus</span><span class="sxs-lookup"><span data-stu-id="bd6d6-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="bd6d6-124">Nachdem Sie Ihre Benutzer in Skype für Business Online verschoben haben, können Sie diese Zuordnen des entsprechenden Koexistenzmodus basierend auf der Upgrade Weg, die Ihre Organisation ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="bd6d6-125">Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="bd6d6-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="bd6d6-126">Mit Skype für Business Server 2019 und einem zukünftigen kumulativen Update von Skype für Business Server 2015 benötigen Sie (Migrieren von Benutzern zu Skype für Business Online) Schritt2 und Schritt 3 (Upgrade Benutzer Teams) in einem einzigen Schritt ausführen können.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="bd6d6-127">Weitere Informationen werden nach der Veröffentlichung von Skype für Business Server 2019 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="bd6d6-128">Upgrade Telefonsystem und Teams</span><span class="sxs-lookup"><span data-stu-id="bd6d6-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="bd6d6-129">Wenn Sie Ihre Skype für Business lokale Bereitstellung von Enterprise-VoIP zu Telefonsystem mit Aufrufen plant übergebenden und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) – und unter der Annahme, dass Sie die Telefonnummer abgeschlossen haben Portieren – Aktualisieren Ihrer Benutzer auf Teams wird automatisch eingehenden PSTN-Anrufe zu Teams umzustellen.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="bd6d6-130">Wenn aufrufen Pläne nicht verfügbar ist, müssen Sie Ihre Enterprise-VoIP-Bereitstellung Microsoft Phone System direkten Routing Übergang.</span><span class="sxs-lookup"><span data-stu-id="bd6d6-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="bd6d6-131">Wenn Ihre Benutzer auf Teams aktualisieren, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="bd6d6-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>