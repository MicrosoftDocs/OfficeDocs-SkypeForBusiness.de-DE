---
title: Aktualisieren von Skype für Business hybridbereitstellung zu Microsoft-Teams | PSTN
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade von Teams aus einer Skype für Business hybridbereitstellung.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e27e36a26115acf23536edb896066d6bc78daa4e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464812"
---
<span data-ttu-id="bf33b-103">![Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase] (media/upgrade-banner-deployment.png "Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase")</span><span class="sxs-lookup"><span data-stu-id="bf33b-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="bf33b-104">Dieser Artikel ist Teil der Bereitstellung und Implementierung Stufe der Ihrem Upgrade Weg.</span><span class="sxs-lookup"><span data-stu-id="bf33b-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="bf33b-105">Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="bf33b-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="bf33b-106">Ihre Projektbeteiligten eingetragen</span><span class="sxs-lookup"><span data-stu-id="bf33b-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="bf33b-107">Definiert die Projektumfang</span><span class="sxs-lookup"><span data-stu-id="bf33b-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="bf33b-108">Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden</span><span class="sxs-lookup"><span data-stu-id="bf33b-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="bf33b-109">Ihre Reise Upgrade ausgewählt</span><span class="sxs-lookup"><span data-stu-id="bf33b-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="bf33b-110">Die Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="bf33b-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="bf33b-111">Ihre Organisation vorbereitet</span><span class="sxs-lookup"><span data-stu-id="bf33b-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="bf33b-112">Ein Pilotprojekt durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf33b-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="bf33b-113">Upgrade von einer Skype für Business hybridbereitstellung auf Teams</span><span class="sxs-lookup"><span data-stu-id="bf33b-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="bf33b-114">Befolgen Sie die Anweisungen in diesem Artikel, wenn Sie Skype für Unternehmen bereitgestellt haben oder Microsoft Lync lokal und in einer hybridbereitstellung mit Ihrem Office 365-Mandanten konfiguriert und möchte, dass Ihre Organisation auf Teams entweder selektiv aktualisieren – durch die Verwendung mehrerer Koexistenz Modi – oder-Ansatz repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="bf33b-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="bf33b-115">Für ein Upgrade Weg müssen Sie Ihre Benutzer (Wenn sie bereits online verwaltet werden nicht) zu Skype für Business Online verschieben, und weisen Sie diese der entsprechenden Koexistenz und Upgrade-Modus.</span><span class="sxs-lookup"><span data-stu-id="bf33b-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="bf33b-116">Schritt 1: Migrieren von Benutzern zu Skype für Business Online</span><span class="sxs-lookup"><span data-stu-id="bf33b-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="bf33b-117">Dieser Schritt gilt für Benutzer, die derzeit lokal sind.</span><span class="sxs-lookup"><span data-stu-id="bf33b-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="bf33b-118">Weitere Informationen zum Verschieben von Benutzern zu Skype für Business Online finden Sie unter [Verschieben von Benutzern aus lokal - auf Skype für Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="bf33b-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="bf33b-119">Schritt 2: Zuweisen einer Koexistenz und Aktualisierungsmodus</span><span class="sxs-lookup"><span data-stu-id="bf33b-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="bf33b-120">Nachdem Sie Ihre Benutzer in Skype für Business Online verschoben haben, können Sie diese Zuordnen des entsprechenden Koexistenzmodus basierend auf der Upgrade Weg, die Ihre Organisation ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="bf33b-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="bf33b-121">Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="bf33b-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="bf33b-122">Mit Skype für Business Server 2019 und einem zukünftigen kumulativen Update von Skype für Business Server 2015 können Sie Schritt 1 (Migrieren von Benutzern zu Skype für Business Online) und Schritt2 (Upgrade Benutzer Teams) in einem einzigen Schritt ausführen können.</span><span class="sxs-lookup"><span data-stu-id="bf33b-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="bf33b-123">Weitere Informationen werden nach der Veröffentlichung von Skype für Business Server 2019 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bf33b-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="bf33b-124">Upgrade Telefonsystem und Teams</span><span class="sxs-lookup"><span data-stu-id="bf33b-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="bf33b-125">Wenn Sie Ihre Skype für Business hybridbereitstellung zu Telefonsystem mit Aufrufen plant übergebenden und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) – und unter der Annahme, dass Sie das Telefon Nummer Portieren abgeschlossen haben – aktualisieren die Benutzer Teams werden automatisch eingehende PSTN-Aufruf von Teams umzustellen.</span><span class="sxs-lookup"><span data-stu-id="bf33b-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="bf33b-126">Wenn plant aufrufen, ist nicht verfügbar, oder Sie Ihre vorhandenen PSTN-Konnektivität-Dienstanbieter verwenden möchten, müssen Sie für den Übergang Ihrer Enterprise-VoIP-bereitstellungs – oder Hybrid-VoIP-Bereitstellung, die Ihre vorhandenen verwendet lokale Bereitstellung oder Cloud Connector Edition – an Microsoft Telefonsystem direktes Routing.</span><span class="sxs-lookup"><span data-stu-id="bf33b-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="bf33b-127">Wenn Ihre Benutzer auf Teams aktualisieren, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="bf33b-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
