---
title: Direktes Routing für Telefonsysteme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Startseite für direktes Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: d643c137145649c0843296300a909c520ba653a6
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157903"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="be094-103">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="be094-103">Phone System Direct Routing</span></span>

<span data-ttu-id="be094-104">Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="be094-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="be094-105">Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="be094-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="be094-106">Vielleichthaben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="be094-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="be094-107">Nun können Sie Cloud-VoIP-Arbeitsauslastungen hinzufügen, und Sie haben sich entschieden, mithilfe des direkten Routings des Telefonsystems ihren eigenen Telefoniedienstanbieter für PSTN-Verbindungen (Public Switched Telephone Network) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="be094-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="be094-108">Mit der direkten Weiterleitung können Sie das Telefon System mit praktisch jedem Telefonnetzbetreiber verwenden.</span><span class="sxs-lookup"><span data-stu-id="be094-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="be094-109">In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für das direkte Routing sowie weitere Überlegungen beschrieben, die Sie je nach den Anforderungen Ihrer Organisation berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="be094-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="be094-110">Sie sollten auch [Cloud-VoIP in Microsoft Teams](cloud-voice-landing-page.md) lesen, um weitere Informationen zu den Cloud-sprach angeboten von Microsoft zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="be094-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="be094-111">Weitere Informationen zum direkten Routing</span><span class="sxs-lookup"><span data-stu-id="be094-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="be094-112">In den folgenden Artikeln finden Sie weitere Informationen zum Konfigurieren und Verwenden des direkten Routings für das Telefon System.</span><span class="sxs-lookup"><span data-stu-id="be094-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="be094-113">Für die Konfiguration des direkten Routings ist das Verständnis des PSTN-Routingentwurfs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="be094-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="be094-114">Sie sollten alle diese Artikel lesen, um zu erfahren, wie Sie das direkte Routing planen und konfigurieren können:</span><span class="sxs-lookup"><span data-stu-id="be094-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="be094-115">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="be094-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="be094-116">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="be094-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="be094-117">Liste der für direktes Routing zertifizierten Session Border Controller</span><span class="sxs-lookup"><span data-stu-id="be094-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="be094-118">Überwachung und Problembehandlung von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="be094-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="be094-119">Darüber hinaus empfiehlt es sich, je nach Ihren Anforderungen die folgenden Artikel zu lesen:</span><span class="sxs-lookup"><span data-stu-id="be094-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="be094-120">Konfigurieren eines Session Border Controllers für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="be094-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="be094-121">Migration zu direktem Routing</span><span class="sxs-lookup"><span data-stu-id="be094-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="be094-122">Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="be094-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="be094-123">Schauen Sie sich die folgende Sitzung an, um mehr über Direct Routing zu erfahren: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="be094-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="be094-124">Zentrale Entscheidungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="be094-124">Core deployment decisions</span></span>

<span data-ttu-id="be094-125">Dies sind die wichtigsten Entscheidungen, die bei der direkten Weiterleitung zu Bedenken sind.</span><span class="sxs-lookup"><span data-stu-id="be094-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="be094-126">Frage</span><span class="sxs-lookup"><span data-stu-id="be094-126">Ask yourself</span></span>|<span data-ttu-id="be094-127">Aktion</span><span class="sxs-lookup"><span data-stu-id="be094-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="be094-128">Für welche Benutzer wird die direkte Weiterleitung aktiviert?</span><span class="sxs-lookup"><span data-stu-id="be094-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="be094-129">Weitere Informationen finden Sie unter [Aktivieren von Benutzern für den direkten Routing Dienst](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="be094-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="be094-130">Habe ich die erforderlichen Lizenzen für die direkte Weiterleitung?</span><span class="sxs-lookup"><span data-stu-id="be094-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="be094-131">Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="be094-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="be094-132">Überlegungen zu Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="be094-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="be094-133">Mit Direct Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt mit dem Telefon System verbinden.</span><span class="sxs-lookup"><span data-stu-id="be094-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="be094-134">Eine Liste der zertifizierten SBCS finden Sie unter [unterstützte Session Border Controllers](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="be094-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="be094-135">Frage</span><span class="sxs-lookup"><span data-stu-id="be094-135">Ask yourself</span></span>|<span data-ttu-id="be094-136">Aktion</span><span class="sxs-lookup"><span data-stu-id="be094-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="be094-137">Wo und wie kann ich SBCS bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="be094-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="be094-138">Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md) .</span><span class="sxs-lookup"><span data-stu-id="be094-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="be094-139">Habe ich mehrere Mandanten?</span><span class="sxs-lookup"><span data-stu-id="be094-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="be094-140">Weitere Informationen finden Sie unter [Konfigurieren eines Sitzungs Grenz Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="be094-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="be094-141">Überlegungen zum VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="be094-141">Voice routing considerations</span></span>

<span data-ttu-id="be094-142">Sie müssen das Telefon System so konfigurieren, dass die Anrufe an den jeweiligen SBCS weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="be094-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="be094-143">Frage</span><span class="sxs-lookup"><span data-stu-id="be094-143">Ask yourself</span></span>|<span data-ttu-id="be094-144">Aktion</span><span class="sxs-lookup"><span data-stu-id="be094-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="be094-145">Welche VoIP-Routing Richtlinien, PSTN-Nutzung und VoIP-Routen muss ich erstellen?</span><span class="sxs-lookup"><span data-stu-id="be094-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="be094-146">Informationen zum VoIP-Routing finden Sie unter [Konfigurieren des VoIP-Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="be094-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="be094-147">Welche Benutzer werden der von mir definierten VoIP-Routing Richtlinie zugewiesen?</span><span class="sxs-lookup"><span data-stu-id="be094-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="be094-148">Sehen Sie sich die Beispiele unter [Konfigurieren des VoIP-Routings](direct-routing-configure.md)an.</span><span class="sxs-lookup"><span data-stu-id="be094-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="be094-149">Sicherstellen, dass eingehende Anrufe im Team-Client mit TeamsUpgradePolicy landen</span><span class="sxs-lookup"><span data-stu-id="be094-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="be094-150">Das direkte Routing wird nur von Microsoft Teams unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be094-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="be094-151">Wenn Sie PSTN-Anrufe über direkte Weiterleitung empfangen möchten, müssen Sie TeamsUpgradePolicy so konfigurieren, dass eingehende Anrufe in Teams empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="be094-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="be094-152">Benutzer müssen sich im Modus "nur für Teams" befinden, was Sie tun können, indem Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zuweisen.</span><span class="sxs-lookup"><span data-stu-id="be094-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="be094-153">Frage</span><span class="sxs-lookup"><span data-stu-id="be094-153">Ask yourself</span></span>|<span data-ttu-id="be094-154">Aktion</span><span class="sxs-lookup"><span data-stu-id="be094-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="be094-155">Was bedeutet "nur für Teams"?</span><span class="sxs-lookup"><span data-stu-id="be094-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="be094-156">Weitere Informationen finden Sie unter [Leitfaden zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="be094-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="be094-157">Weitere Überlegungen zur Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="be094-157">Additional deployment considerations</span></span>

<span data-ttu-id="be094-158">Je nach den Anforderungen und der Konfiguration Ihrer Organisation empfiehlt es sich, die folgenden Punkte zu bedenken:</span><span class="sxs-lookup"><span data-stu-id="be094-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="be094-159">Frage</span><span class="sxs-lookup"><span data-stu-id="be094-159">Ask yourself</span></span>| <span data-ttu-id="be094-160">Aktion</span><span class="sxs-lookup"><span data-stu-id="be094-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="be094-161">Verfügen Sie über eine vorhandene Skype for Business Server-Bereitstellung mit konfigurierter Hybrid Konnektivität?</span><span class="sxs-lookup"><span data-stu-id="be094-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="be094-162">Informationen dazu, wie Benutzerkonten in einer Hybridumgebung bereitgestellt und verwaltet werden, finden Sie unter [Benutzerkonten in einer Hybridumgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="be094-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="be094-163">Migrieren Sie vom Anrufplan zur direkten Weiterleitung oder von einer lokalen Skype for Business-Umgebung?</span><span class="sxs-lookup"><span data-stu-id="be094-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="be094-164">Weitere Informationen zum Migrieren zu direktem Routing aus einer vorhandenen Umgebung finden Sie unter [Migrieren zu direktem Routing](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="be094-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
