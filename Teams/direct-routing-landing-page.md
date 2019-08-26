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
ms.openlocfilehash: 965fb26aee3d83550740e2ae7f855559fd9cdb79
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484059"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="b3ea1-103">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="b3ea1-103">Phone System Direct Routing</span></span>

<span data-ttu-id="b3ea1-104">Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="b3ea1-105">Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="b3ea1-106">Sie haben möglicherweise [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="b3ea1-107">Jetzt sind Sie bereit, Cloud-Sprach-Workloads hinzuzufügen, und Sie haben sich entschieden, Ihren eigenen Telefonie-Betreiber für die PSTN-Konnektivität (Public Switched Telephone Network) zu verwenden, indem Sie direktes Routing für Telefonsysteme verwenden.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="b3ea1-108">Mit dem direkten Routing können Sie die Telefonsysteme mit praktisch jedem Telefonieanbieter nutzen.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="b3ea1-109">Dieser Artikel beschreibt die wichtigsten Bereitstellungsentscheidungen für das direkte Routing sowie zusätzliche Faktoren, die Sie berücksichtigen sollten, basierend auf den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="b3ea1-110">Weitere Informationen über die Cloud-Sprachangebote von Microsoft finden Sie auch unter [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="b3ea1-111">Hier finden Sie weitere Informationen zu direktem Routing</span><span class="sxs-lookup"><span data-stu-id="b3ea1-111">Learn more about Direct Routing.</span></span>

<span data-ttu-id="b3ea1-112">In den folgenden Artikeln finden Sie weitere Informationen zur Konfiguration und Verwendung von direktem Routing für das Telefonsysteme.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="b3ea1-113">Für die Konfiguration des direkten Routings sind Kenntnisse des PSTN-Routing Designs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="b3ea1-114">Lesen Sie alle diese Artikel, um zu verstehen, wie Sie direktes Routing planen und konfigurieren können:</span><span class="sxs-lookup"><span data-stu-id="b3ea1-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="b3ea1-115">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="b3ea1-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="b3ea1-116">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="b3ea1-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="b3ea1-117">Liste der für direktes Routing zertifizierten Session Border Controller</span><span class="sxs-lookup"><span data-stu-id="b3ea1-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="b3ea1-118">Überwachung und Problembehandlung von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="b3ea1-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="b3ea1-119">Zusätzlich können Sie je nach Ihren Anforderungen die folgenden Artikel lesen:</span><span class="sxs-lookup"><span data-stu-id="b3ea1-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="b3ea1-120">Konfigurieren eines Session Border Controllers für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="b3ea1-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="b3ea1-121">Migration zu direktem Routing</span><span class="sxs-lookup"><span data-stu-id="b3ea1-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="b3ea1-122">Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="b3ea1-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="b3ea1-123">In der folgenden Sitzung erfahren Sie mehr über direktes Routing: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="b3ea1-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="b3ea1-124">Zentrale Entscheidungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="b3ea1-124">Core deployment decisions</span></span>

<span data-ttu-id="b3ea1-125">Diese Kernetscheidungen sind für das direkte Routing zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="b3ea1-126">Frage</span><span class="sxs-lookup"><span data-stu-id="b3ea1-126">Ask yourself</span></span>|<span data-ttu-id="b3ea1-127">Aktion</span><span class="sxs-lookup"><span data-stu-id="b3ea1-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="b3ea1-128">Für welche Benutzer werde ich das direkte Routing aktivieren?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="b3ea1-129">Weitere Informationen finden Sie unter[Aktivieren von Benutzern für den direkten Routing-Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="b3ea1-130">Habe ich die erforderlichen Lizenzen für das direkte Routing?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="b3ea1-131">Weitere Informationen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="b3ea1-132">Überlegungen zum Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="b3ea1-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="b3ea1-133">Mit dem direkten Routing können Sie Ihren eigenen Session Border Controller (SBC) direkt an das Telefonsystem anschließen.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="b3ea1-134">Eine Liste der zertifizierten SBCS finden Sie unter [Unterstützte Session Border Controller](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="b3ea1-135">Frage</span><span class="sxs-lookup"><span data-stu-id="b3ea1-135">Ask yourself</span></span>|<span data-ttu-id="b3ea1-136">Aktion</span><span class="sxs-lookup"><span data-stu-id="b3ea1-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="b3ea1-137">Wo und wie werde ich SBC bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="b3ea1-138">Weitere Informationen finden Sie unter [Konfigurieren von direktem Routing](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b3ea1-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="b3ea1-139">Habe ich mehrere Mandanten?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="b3ea1-140">Weitere Informationen finden Sie unter [Konfigurieren eines Session Border Controllers für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="b3ea1-141">Überlegungen zum VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="b3ea1-141">Voice routing considerations</span></span>

<span data-ttu-id="b3ea1-142">Sie müssen das Telefonsystem so konfigurieren, um die Anrufe an die jeweiligen SBCs weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="b3ea1-143">Frage</span><span class="sxs-lookup"><span data-stu-id="b3ea1-143">Ask yourself</span></span>|<span data-ttu-id="b3ea1-144">Aktion</span><span class="sxs-lookup"><span data-stu-id="b3ea1-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="b3ea1-145">Welche VoIP-Routing Richtlinien, die PSTN-Nutzung und die VoIP-Routen muss ich erstellen?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="b3ea1-146">Weitere Informationen zum VoIP-Routing finden Sie unter [Konfigurieren von VoIP-Routing](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="b3ea1-147">Welche Benutzer werden der von mir definierten VoIP-Routing-Richtlinie zugeordnet?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="b3ea1-148">Weitere Beispiele finden Sie unter [Konfigurieren von VoIP](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="b3ea1-149">Anruf-und Interop-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="b3ea1-149">Calling and interop policies</span></span>

<span data-ttu-id="b3ea1-150">Direktes Routing wird nur von Microsoft Teams unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="b3ea1-151">Um PSTN-Anrufe über das direkte Routing zu tätigen oder zu empfangen, müssen Sie die erforderlichen Richtlinien konfigurieren, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="b3ea1-152">Sie können Benutzer konfigurieren, um Teams als bevorzugten Client für Anrufe festzulegen, indem Sie entweder den Benutzer für den „Nur Teams“-Modus konfigurieren oder Teams als bevorzugten Anruf-Client konfigurieren, indem Sie die TeamsCallingPolicy und die TeamsInteropPolicy zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b3ea1-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="b3ea1-153">Frage</span><span class="sxs-lookup"><span data-stu-id="b3ea1-153">Ask yourself</span></span>|<span data-ttu-id="b3ea1-154">Aktion</span><span class="sxs-lookup"><span data-stu-id="b3ea1-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="b3ea1-155">Wie kann ich Teams als bevorzugten Client für Anrufe festlegen?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="b3ea1-156">Weitere Informationen finden Sie unter [Microsoft Teams als bevorzugten Anruf-Client für Benutzer festlegen](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="b3ea1-157">Zusätzliche Bereitstellungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="b3ea1-157">Additional deployment considerations</span></span>

<span data-ttu-id="b3ea1-158">Je nach den Anforderungen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, Folgendes zu berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="b3ea1-158">You may want to change these settings, based on your organization's needs and configuration.</span></span>

| <span data-ttu-id="b3ea1-159">Frage</span><span class="sxs-lookup"><span data-stu-id="b3ea1-159">Ask yourself</span></span>| <span data-ttu-id="b3ea1-160">Aktion</span><span class="sxs-lookup"><span data-stu-id="b3ea1-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="b3ea1-161">Haben Sie eine bestehende Skype für Business Server-Bereitstellung mit hybrider Konnektivität konfiguriert?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="b3ea1-162">Weitere Informationen darüber, wie Benutzerkonten in einer hybriden Umgebung bereitgestellt und verwaltet werden, finden Sie unter [Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="b3ea1-163">Migrieren Sie von einem Anrufplan oder von einer lokalen Skype for Business Umgebung auf direktes Routing?</span><span class="sxs-lookup"><span data-stu-id="b3ea1-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="b3ea1-164">Weitere Informationen zur Migration auf direktes Routing von einer bestehenden Umgebung finden Sie unter [Migration auf direktes Routing](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="b3ea1-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
