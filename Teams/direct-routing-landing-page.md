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
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Angebotsseite für direktes Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ded644f552c233b712f43de212f2269ee6e70b2
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018801"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="9a0a8-103">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="9a0a8-103">Phone System Direct Routing</span></span>

<span data-ttu-id="9a0a8-104">Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="9a0a8-105">Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="9a0a8-106">Sie haben möglicherweise [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="9a0a8-107">Jetzt sind Sie bereit, Cloud-Sprach-Workloads hinzuzufügen, und Sie haben sich entschieden, Ihren eigenen Telefonie-Betreiber für die PSTN-Konnektivität (Public Switched Telephone Network) zu verwenden, indem Sie direktes Routing für Telefonsysteme verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="9a0a8-108">Mit dem direkten Routing können Sie die Telefonsysteme mit praktisch jedem Telefonieanbieter nutzen.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="9a0a8-109">Dieser Artikel beschreibt die wichtigsten Bereitstellungsentscheidungen für das direkte Routing sowie zusätzliche Faktoren, die Sie berücksichtigen sollten, basierend auf den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="9a0a8-110">Weitere Informationen über die Cloud-Sprachangebote von Microsoft finden Sie auch unter [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="9a0a8-111">Hier finden Sie weitere Informationen zu direktem Routing</span><span class="sxs-lookup"><span data-stu-id="9a0a8-111">Learn more about Direct Routing.</span></span>

<span data-ttu-id="9a0a8-112">In den folgenden Artikeln finden Sie weitere Informationen zur Konfiguration und Verwendung von direktem Routing für das Telefonsysteme.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="9a0a8-113">Für die Konfiguration des direkten Routings sind Kenntnisse des PSTN-Routing Designs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="9a0a8-114">Lesen Sie alle diese Artikel, um zu verstehen, wie Sie direktes Routing planen und konfigurieren können:</span><span class="sxs-lookup"><span data-stu-id="9a0a8-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="9a0a8-115">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="9a0a8-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="9a0a8-116">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="9a0a8-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="9a0a8-117">Liste der für direktes Routing zertifizierten Session Border Controller</span><span class="sxs-lookup"><span data-stu-id="9a0a8-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="9a0a8-118">Überwachung und Problembehandlung von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="9a0a8-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="9a0a8-119">Zusätzlich können Sie je nach Ihren Anforderungen die folgenden Artikel lesen:</span><span class="sxs-lookup"><span data-stu-id="9a0a8-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="9a0a8-120">Konfigurieren eines Session Border Controllers für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="9a0a8-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="9a0a8-121">Migration zu direktem Routing</span><span class="sxs-lookup"><span data-stu-id="9a0a8-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="9a0a8-122">Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="9a0a8-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="9a0a8-123">In der folgenden Sitzung erfahren Sie mehr über direktes Routing: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="9a0a8-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="9a0a8-124">Zentrale Entscheidungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9a0a8-124">Core deployment decisions</span></span>

<span data-ttu-id="9a0a8-125">Diese Kernetscheidungen sind für das direkte Routing zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="9a0a8-126">Frage</span><span class="sxs-lookup"><span data-stu-id="9a0a8-126">Ask yourself</span></span>|<span data-ttu-id="9a0a8-127">Aktion</span><span class="sxs-lookup"><span data-stu-id="9a0a8-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="9a0a8-128">Für welche Benutzer werde ich das direkte Routing aktivieren?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="9a0a8-129">Weitere Informationen finden Sie unter[Aktivieren von Benutzern für den direkten Routing-Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="9a0a8-130">Habe ich die erforderlichen Lizenzen für das direkte Routing?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="9a0a8-131">Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="9a0a8-132">Überlegungen zum Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="9a0a8-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="9a0a8-133">Mit dem direkten Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt an das Telefonsystem anschließen.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="9a0a8-134">Eine Liste der zertifizierten SBCS finden Sie unter [Unterstützte Session Border Controller](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="9a0a8-135">Frage</span><span class="sxs-lookup"><span data-stu-id="9a0a8-135">Ask yourself</span></span>|<span data-ttu-id="9a0a8-136">Aktion</span><span class="sxs-lookup"><span data-stu-id="9a0a8-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9a0a8-137">Wo und wie werde ich SBC bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="9a0a8-138">Weitere Informationen finden Sie unter [Konfigurieren von direktem Routing](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="9a0a8-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="9a0a8-139">Habe ich mehrere Mandanten?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="9a0a8-140">Weitere Informationen finden Sie unter [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="9a0a8-141">Überlegungen zum VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="9a0a8-141">Voice routing considerations</span></span>

<span data-ttu-id="9a0a8-142">Sie müssen das Telefonsystem so konfigurieren, um die Anrufe an die jeweiligen SBCs weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="9a0a8-143">Frage</span><span class="sxs-lookup"><span data-stu-id="9a0a8-143">Ask yourself</span></span>|<span data-ttu-id="9a0a8-144">Aktion</span><span class="sxs-lookup"><span data-stu-id="9a0a8-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9a0a8-145">Welche VoIP-Routing Richtlinien, die PSTN-Nutzung und die VoIP-Routen muss ich erstellen?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="9a0a8-146">Weitere Informationen zum VoIP-Routing finden Sie unter [Konfigurieren von VoIP-Routing](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="9a0a8-147">Welche Benutzer werden der von mir definierten VoIP-Routing-Richtlinie zugeordnet?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="9a0a8-148">Weitere Beispiele finden Sie unter [Konfigurieren von VoIP](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="9a0a8-149">Stellen Sie sicher, dass eingehende Anrufe mit TeamsUpgradePolicy im Team-Client eingehen.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="9a0a8-150">Direktes Routing wird nur von Microsoft Teams unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="9a0a8-151">Um PSTN-Anrufe über das direkte Routing zu tätigen oder zu empfangen, müssen Sie die erforderlichen TeamsUpgradePolicy konfigurieren, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="9a0a8-152">Benutzer müssen sich im Modus „Nur Teams“ befinden, indem Sie ihnen die Instanz "UpgradeToTeams" von TeamsUpgradePolicy zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9a0a8-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="9a0a8-153">Frage</span><span class="sxs-lookup"><span data-stu-id="9a0a8-153">Ask yourself</span></span>|<span data-ttu-id="9a0a8-154">Aktion</span><span class="sxs-lookup"><span data-stu-id="9a0a8-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9a0a8-155">Was bedeutet der Modus „Nur Teams“?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="9a0a8-156">Weitere Informationen finden Sie unter[Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-156">[Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="9a0a8-157">Zusätzliche Bereitstellungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="9a0a8-157">Additional deployment considerations</span></span>

<span data-ttu-id="9a0a8-158">Je nach den Anforderungen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, Folgendes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="9a0a8-158">You may want to change these settings, based on your organization's needs and configuration.</span></span>

| <span data-ttu-id="9a0a8-159">Frage</span><span class="sxs-lookup"><span data-stu-id="9a0a8-159">Ask yourself</span></span>| <span data-ttu-id="9a0a8-160">Aktion</span><span class="sxs-lookup"><span data-stu-id="9a0a8-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9a0a8-161">Haben Sie eine bestehende Skype für Business Server-Bereitstellung mit hybrider Konnektivität konfiguriert?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="9a0a8-162">Weitere Informationen darüber, wie Benutzerkonten in einer hybriden Umgebung bereitgestellt und verwaltet werden, finden Sie unter [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="9a0a8-163">Migrieren Sie von einem Anrufplan oder von einer lokalen Skype for Business Umgebung auf direktes Routing?</span><span class="sxs-lookup"><span data-stu-id="9a0a8-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="9a0a8-164">Weitere Informationen zur Migration auf direktes Routing von einer bestehenden Umgebung finden Sie unter [Migration auf direktes Routing](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="9a0a8-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
