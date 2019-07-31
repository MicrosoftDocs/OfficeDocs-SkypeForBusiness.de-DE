---
title: Upgrade auf Microsoft Teams von einer Hybrid-Bereitstellung oder einer lokalen Bereitstellung von Skype for Business – Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade auf Teams von einer Skype for Business-Hybrid-oder lokalen Bereitstellung.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934518"
---
<span data-ttu-id="61764-103">![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Bereitstellung und Implementierung] (media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")</span><span class="sxs-lookup"><span data-stu-id="61764-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="61764-104">Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise.</span><span class="sxs-lookup"><span data-stu-id="61764-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="61764-105">Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="61764-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="61764-106">Ihre Projekt Beteiligten wurden eingetragen</span><span class="sxs-lookup"><span data-stu-id="61764-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="61764-107">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="61764-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="61764-108">Verständliche Koexistenz und Interoperabilität von Skype for Business und Teams</span><span class="sxs-lookup"><span data-stu-id="61764-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="61764-109">Ihre Upgrade-Reise gewählt</span><span class="sxs-lookup"><span data-stu-id="61764-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="61764-110">Ihre Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="61764-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="61764-111">Vorbereiten Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="61764-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="61764-112">Durchgeführt eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="61764-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="61764-113">Upgrade auf Teams von einer Skype for Business-Hybrid-oder lokalen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="61764-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="61764-114">Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft lync lokal bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams entweder selektiv – mithilfe mehrerer Koexistenzmodus – oder All-in durchführen möchte.</span><span class="sxs-lookup"><span data-stu-id="61764-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="61764-115">Der erste Schritt besteht darin, eine hybridverbindung mit Ihrem Office 365-Mandanten einzurichten und dann Ihre Benutzer in Skype for Business Online zu verschieben und Ihnen den entsprechenden Koexistenz-und Aktualisierungsmodus zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="61764-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="61764-116">Skype for Business Online wird am 31. Juli 2021 eingestellt, danach wird es nicht mehr barrierefrei oder unterstützt.</span><span class="sxs-lookup"><span data-stu-id="61764-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="61764-117">Um die Leistung zu maximieren und sicherzustellen, dass Ihre Organisation die richtige Zeit für die Implementierung Ihres Upgrades hat, empfehlen wir Ihnen, Ihre Reise zu Microsoft Teams heute zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="61764-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="61764-118">Beachten Sie, dass ein erfolgreiches Upgrade die technische und Benutzer Bereitschaft ausrichtet, damit Sie die hierin beschriebenen Anleitungen für die Navigation in Ihrer Reise zu Microsoft Teams nutzen können.</span><span class="sxs-lookup"><span data-stu-id="61764-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="61764-119">Schritt 1: Bereitstellen von Hybrid Konnektivität</span><span class="sxs-lookup"><span data-stu-id="61764-119">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="61764-120">Die wichtigste Voraussetzung für das Upgrade Ihrer Benutzer auf Teams ist die Bereitstellung von Hybrid Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="61764-120">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="61764-121">Hierbei kann es sich um die Bereitstellungneuer externer Verbindungen für Ihre vorhandene Skype for Business-oder lync-Bereitstellung oder einfach um das Konfigurieren einer Hybrid Beziehung mit Ihrem Office 365-Mandanten handelt.</span><span class="sxs-lookup"><span data-stu-id="61764-121">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="61764-122">Weitere Informationen finden Sie unter [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="61764-122">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="61764-123">Schritt 2: Verschieben von Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="61764-123">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="61764-124">Nachdem Sie Ihre Hybrid Einrichtung abgeschlossen haben, verschieben Sie die Benutzer in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="61764-124">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="61764-125">Weitere Informationen finden Sie unter [Verschieben von Benutzern von lokal in Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="61764-125">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="61764-126">Schritt 3: Zuweisen einer Koexistenz und eines Aktualisierungsmodus</span><span class="sxs-lookup"><span data-stu-id="61764-126">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="61764-127">Nachdem Sie Ihre Benutzer in Skype for Business Online verschoben haben, können Sie Ihnen den passenden Koexistenzmodus zuweisen, der auf der von Ihrer Organisation ausgewählten Upgrade-Reise basiert.</span><span class="sxs-lookup"><span data-stu-id="61764-127">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="61764-128">Weitere Informationen finden Sie unter [Festlegen von Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="61764-128">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="61764-129">Mit Skype for Business Server 2019 und einem zukünftigen kumulativen Update von Skype for Business Server 2015 können Sie Schritt 2 (Verschieben von Benutzern in Skype for Business Online) und Schritt 3 (Benutzer auf Teams aktualisieren) in einem einzigen Schritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="61764-129">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="61764-130">Weitere Informationen werden nach der Veröffentlichung von Skype for Business Server 2019 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="61764-130">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="61764-131">Upgrade für Telefonsysteme und Teams</span><span class="sxs-lookup"><span data-stu-id="61764-131">Phone System and Teams upgrade</span></span>

<span data-ttu-id="61764-132">Wenn Sie Ihre Skype for Business-hybridbereitstellung in das Telefon System mit Anrufplänen umstellen und Microsoft Ihr öffentlich geschaltetes Telefonnetz (PSTN)-Anbieter ist – und davon ausgehend, dass Sie die Portierung von Telefonnummern abgeschlossen haben – aktualisieren Sie Ihre Benutzer auf Teams über gehen automatisch eingehende PSTN-Anrufe an Teams.</span><span class="sxs-lookup"><span data-stu-id="61764-132">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="61764-133">Wenn keine Anrufpläne verfügbar sind, müssen Sie Ihre Enterprise-VoIP-Bereitstellung auf das direkte Routing von Microsoft Phone System umstellen.</span><span class="sxs-lookup"><span data-stu-id="61764-133">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="61764-134">Wenn Sie Ihre Benutzer auf Teams aktualisieren möchten, lesen Sie die [zusätzlichen Überlegungen für das direkte Routing von Telefonsystemen](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="61764-134">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
