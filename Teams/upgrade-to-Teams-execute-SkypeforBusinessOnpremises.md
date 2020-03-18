---
title: Upgrade von Skype for Business lokal auf Microsoft Teams | Bereitstellen | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb6815c805c9f5bcf47d6ee88a6c43c559b932d3
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706645"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="85306-103">Upgrade von einer lokalen Bereitstellung von Skype for Business in Teams</span><span class="sxs-lookup"><span data-stu-id="85306-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="85306-104">![Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt](media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")</span><span class="sxs-lookup"><span data-stu-id="85306-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="85306-105">Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise.</span><span class="sxs-lookup"><span data-stu-id="85306-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="85306-106">Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="85306-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="85306-107">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="85306-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="85306-108">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="85306-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="85306-109">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85306-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="85306-110">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="85306-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="85306-111">Ihre Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="85306-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="85306-112">Vorbereiten Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="85306-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="85306-113">Durchgeführt eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="85306-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="85306-114">Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft lync lokal bereitgestellt haben und Ihre Organisation ein Upgrade auf Microsoft Teams entweder selektiv – mithilfe mehrerer Koexistenzmodus – oder All-in durchführen möchte.</span><span class="sxs-lookup"><span data-stu-id="85306-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="85306-115">Schritt 1: Bereitstellen von Hybrid Konnektivität</span><span class="sxs-lookup"><span data-stu-id="85306-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="85306-116">Die wichtigste Voraussetzung für das Upgrade Ihrer Benutzer auf Teams ist die Bereitstellung von Hybrid Konnektivität.</span><span class="sxs-lookup"><span data-stu-id="85306-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="85306-117">Weitere Informationen finden Sie unter [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) .</span><span class="sxs-lookup"><span data-stu-id="85306-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="85306-118">Schritt 2: Implementieren der ausgewählten Upgrade-Reise für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="85306-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="85306-119">Nachdem Sie Ihre Hybrid Einrichtung abgeschlossen haben, können Sie planen, Ihre Benutzer nach Office 365 zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="85306-119">After you've completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="85306-120">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="85306-120">For more information, see:</span></span>

- <span data-ttu-id="85306-121">[TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)</span><span class="sxs-lookup"><span data-stu-id="85306-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="85306-122">[Verschieben von Benutzern von lokal in Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="85306-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="85306-123">Upgrade für Telefonsysteme und Teams</span><span class="sxs-lookup"><span data-stu-id="85306-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="85306-124">Wenn Sie von lokalen Telefonsystemen zu Teams wechseln, können Sie die Vorteile des direkten Routings für das Telefon System ("Direktes Routing") oder der von Microsoft bereitgestellten Anrufpläne für Office 365 nutzen.</span><span class="sxs-lookup"><span data-stu-id="85306-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="85306-125">Wenn Sie in Office 365 keine Anrufpläne verwenden, müssen Sie Ihre Enterprise-VoIP-Bereitstellung als Teil des Upgrades für Teams in das Telefon System Direct Routing umstellen.</span><span class="sxs-lookup"><span data-stu-id="85306-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="85306-126">Weitere Informationen finden Sie unter [Weitere Überlegungen zum direkten Routing von Telefonsystemen](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="85306-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="85306-127">Wenn Sie beabsichtigen, Anrufpläne in Office 365 zu verwenden, beziehen Sie sich bitte auf unsere Anleitungen für die über [Tragung ihrer Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="85306-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>