---
title: Upgrade von Skype for Business-hybridbereitstellung in Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Erfahren Sie, wie Sie Ihre Organisation von einer Skype for Business-hybridbereitstellung auf Microsoft Teams aktualisieren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a83840029eb1fb433c7a073b49ddaa2232b6485e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905227"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="3f135-103">Upgrade von einer Skype for Business-hybridbereitstellung in Teams</span><span class="sxs-lookup"><span data-stu-id="3f135-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="3f135-104">![Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt](media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")</span><span class="sxs-lookup"><span data-stu-id="3f135-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3f135-105">Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise.</span><span class="sxs-lookup"><span data-stu-id="3f135-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3f135-106">Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="3f135-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="3f135-107">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="3f135-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3f135-108">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="3f135-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3f135-109">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f135-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3f135-110">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="3f135-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3f135-111">Ihre Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="3f135-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3f135-112">Vorbereiten Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="3f135-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="3f135-113">Durchgeführt eines Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="3f135-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="3f135-114">Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft lync lokal bereitgestellt und in einer hybridbereitstellung mit Ihrer Office 365-Organisation konfiguriert haben und Ihre Organisation ein Upgrade auf Teams entweder selektiv durchführen möchte, indem Sie mehrere Koexistenzmodus verwenden – oder All-in.</span><span class="sxs-lookup"><span data-stu-id="3f135-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="3f135-115">Wenn Sie eine Upgrade-Reise durchführen möchten, müssen Sie Ihre Benutzer in Skype for Business Online verschieben (sofern Sie nicht bereits online sind) und Ihnen dann den entsprechenden Koexistenz-und Aktualisierungsmodus zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3f135-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="3f135-116">Schritt 1: Verschieben von Benutzern in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3f135-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="3f135-117">Dieser Schritt bezieht sich auf Benutzer, die derzeit lokal verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3f135-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="3f135-118">Weitere Informationen zum Verschieben dieser Benutzer in Skype for Business Online finden Sie unter [Verschieben von Benutzern von lokal in Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3f135-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="3f135-119">Schritt 2: Zuweisen einer Koexistenz und eines Aktualisierungsmodus</span><span class="sxs-lookup"><span data-stu-id="3f135-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="3f135-120">Nachdem Sie Ihre Benutzer in Skype for Business Online verschoben haben, können Sie Ihnen den passenden Koexistenzmodus zuweisen, der auf der von Ihrer Organisation ausgewählten Upgrade-Reise basiert.</span><span class="sxs-lookup"><span data-stu-id="3f135-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="3f135-121">Weitere Informationen finden Sie unter [Festlegen von Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="3f135-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="3f135-122">Mit Skype for Business Server 2019 und einem zukünftigen kumulativen Update von Skype for Business Server 2015 können Sie Schritt 1 (Verschieben von Benutzern in Skype for Business Online) und Schritt 2 (Benutzer auf Teams aktualisieren) in einem einzigen Schritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="3f135-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="3f135-123">Weitere Informationen werden nach der Veröffentlichung von Skype for Business Server 2019 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3f135-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="3f135-124">Upgrade für Telefonsysteme und Teams</span><span class="sxs-lookup"><span data-stu-id="3f135-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="3f135-125">Wenn Sie Ihre Skype for Business-hybridbereitstellung in das Telefon System mit Anrufplänen umstellen und Microsoft Ihr öffentlich geschaltetes Telefonnetz (PSTN)-Anbieter ist – und vorausgesetzt, dass Sie die Portierung von Telefonnummern abgeschlossen haben – werden durch das Upgrade Ihrer Benutzer auf Teams automatisch eingehende PSTN-Anrufe an Teams übertragen.</span><span class="sxs-lookup"><span data-stu-id="3f135-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="3f135-126">Wenn keine Anrufpläne verfügbar sind oder Sie beabsichtigen, Ihren vorhandenen PSTN-Verbindungsanbieter zu verwenden, müssen Sie Ihre Enterprise-VoIP-Bereitstellung – oder die Hybrid-sprach Bereitstellung, die Ihre vorhandene lokale Bereitstellung oder Cloud Connector Edition verwendet – auf das direkte Routing von Microsoft Phone System umstellen.</span><span class="sxs-lookup"><span data-stu-id="3f135-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="3f135-127">Wenn Sie Ihre Benutzer auf Teams aktualisieren möchten, lesen Sie die [zusätzlichen Überlegungen für das direkte Routing von Telefonsystemen](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3f135-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
