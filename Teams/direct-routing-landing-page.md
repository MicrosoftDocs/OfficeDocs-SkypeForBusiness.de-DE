---
title: Telefon System direkten Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Zielseite zum direkten Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c2e225090c6d58db2184113dd43995847f9409
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595403"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="f4fde-103">Telefon System direkten Routing</span><span class="sxs-lookup"><span data-stu-id="f4fde-103">Phone System Direct Routing</span></span>

<span data-ttu-id="f4fde-104">Sie haben den [Einstieg in die](get-started-with-teams-quick-start.md)abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f4fde-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="f4fde-105">Sie haben, Teams mit [Chat, Teams, Kanäle, &-apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f4fde-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="f4fde-106">Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f4fde-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="f4fde-107">Sie können nun Cloud VoIP Arbeitslasten hinzufügen, und Sie haben entschieden, Telefonie-Anbieter für die Verbindungen (Public Switched Telephone Network, PSTN) zu verwenden, mithilfe von Telefon System direkten Routing.</span><span class="sxs-lookup"><span data-stu-id="f4fde-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="f4fde-108">Mit direktem Routing können Sie mit nahezu jedes beliebigen Telefonie Netzbetreiber Telefonsystem.</span><span class="sxs-lookup"><span data-stu-id="f4fde-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="f4fde-109">Dieser Artikel beschreibt Core Bereitstellung Entscheidungen für das direkte Routing sowie weitere Aspekte zu beachten, dass Sie möglicherweise konfigurieren möchten, basierend auf der Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f4fde-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to configure, based on your organization's needs.</span></span>  <span data-ttu-id="f4fde-110">[Cloud-VoIP in Microsoft-Teams,](cloud-voice-landing-page.md) lesen Sie auch weitere Informationen zu VoIP Cloudlösungen von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4fde-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="f4fde-111">Erfahren Sie mehr über die direkte Routing</span><span class="sxs-lookup"><span data-stu-id="f4fde-111">Learn more about Direct Routing</span></span>


<span data-ttu-id="f4fde-112">Die folgenden Artikel enthalten weitere Informationen zum Konfigurieren und Telefon System direktes Routing.</span><span class="sxs-lookup"><span data-stu-id="f4fde-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="f4fde-113">Konfigurieren von direkten Routing erfordert Verständnis der PSTN-routing-Entwurf.</span><span class="sxs-lookup"><span data-stu-id="f4fde-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="f4fde-114">Lesen Sie alle in diesen Artikeln zu verstehen, wie beim Planen und Konfigurieren von direkten Routing:</span><span class="sxs-lookup"><span data-stu-id="f4fde-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="f4fde-115">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="f4fde-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="f4fde-116">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="f4fde-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="f4fde-117">Liste der für direktes Routing zertifizierten Session Border Controller</span><span class="sxs-lookup"><span data-stu-id="f4fde-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="f4fde-118">Überwachung und Problembehandlung von direkten Routing</span><span class="sxs-lookup"><span data-stu-id="f4fde-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="f4fde-119">Darüber hinaus sollten Sie je nach Bedarf die folgenden Artikel lesen:</span><span class="sxs-lookup"><span data-stu-id="f4fde-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="f4fde-120">Konfigurieren eines Session Border Controllers für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="f4fde-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="f4fde-121">Migrieren zu direkten Routing</span><span class="sxs-lookup"><span data-stu-id="f4fde-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="f4fde-122">Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="f4fde-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="f4fde-123">Sehen Sie sich die folgenden Sitzung Weitere Informationen zum direkten Routing: [Direktes Routing in Microsoft-Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="f4fde-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="f4fde-124">Zentrale Bereitstellung Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="f4fde-124">Core deployment decisions</span></span>

<span data-ttu-id="f4fde-125">Dies sind die Core Entscheidungen zu berücksichtigende zum direkten weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="f4fde-125">These are the core decisions to consider for Direct Routing.</span></span> 


|<span data-ttu-id="f4fde-126">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="f4fde-126">Ask yourself</span></span>|<span data-ttu-id="f4fde-127">Aktion</span><span class="sxs-lookup"><span data-stu-id="f4fde-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="f4fde-128">Für welche Benutzer aktivieren ich direkten Routing?</span><span class="sxs-lookup"><span data-stu-id="f4fde-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="f4fde-129">Weitere Informationen finden Sie unter [Aktivieren von Benutzern für direkte Routingdienst](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="f4fde-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="f4fde-130">Habe ich die erforderlichen Lizenzen für das direkte Routing?</span><span class="sxs-lookup"><span data-stu-id="f4fde-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="f4fde-131">Weitere Informationen finden Sie unter [Lizenzierung und anderen Anforderungen an](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="f4fde-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="f4fde-132">Session Border Controller (SBC) Aspekte</span><span class="sxs-lookup"><span data-stu-id="f4fde-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="f4fde-133">Mit direktem Routing verbinden Sie Ihre eigene Session Border Controller (SBC) direkt mit Telefonsystem.</span><span class="sxs-lookup"><span data-stu-id="f4fde-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="f4fde-134">Eine Liste mit zertifizierten SBCs finden Sie unter [Unterstützte Session Border Controller](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="f4fde-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="f4fde-135">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="f4fde-135">Ask yourself</span></span>|<span data-ttu-id="f4fde-136">Aktion</span><span class="sxs-lookup"><span data-stu-id="f4fde-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="f4fde-137">Wo und wie werden ich SBCs bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="f4fde-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="f4fde-138">Weitere Informationen finden Sie unter [Konfigurieren von direkten Routing](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="f4fde-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="f4fde-139">Ist mehrere Mandanten vorhanden?</span><span class="sxs-lookup"><span data-stu-id="f4fde-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="f4fde-140">Weitere Informationen finden Sie unter [Configure a Session Border Controller für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="f4fde-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="f4fde-141">VoIP-routing Aspekte</span><span class="sxs-lookup"><span data-stu-id="f4fde-141">Voice routing considerations</span></span>

<span data-ttu-id="f4fde-142">Sie müssen so konfigurieren Sie Telefonsystem so, dass die Aufrufe an die bestimmte SBCs weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="f4fde-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="f4fde-143">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="f4fde-143">Ask yourself</span></span>|<span data-ttu-id="f4fde-144">Aktion</span><span class="sxs-lookup"><span data-stu-id="f4fde-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="f4fde-145">Welche VoIP-Routingrichtlinien zurückgegeben, PSTN-Verwendung und VoIP-Routen benötige ich erstellen?</span><span class="sxs-lookup"><span data-stu-id="f4fde-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="f4fde-146">VoIP-routing-Informationen finden Sie unter [Konfigurieren der VoIP-Routing](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="f4fde-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="f4fde-147">Welche Benutzer werden die VoIP-routing-Richtlinie zugewiesen werden, die ich definieren?</span><span class="sxs-lookup"><span data-stu-id="f4fde-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="f4fde-148">Siehe die Beispiele in [VoIP-Routing konfigurieren](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="f4fde-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="f4fde-149">Aufrufen und Interop-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="f4fde-149">Calling and interop policies</span></span>

<span data-ttu-id="f4fde-150">Direktes Routing wird nur mit Microsoft-Teams, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f4fde-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="f4fde-151">Zum tätigen oder Entgegennehmen von Anrufen über direkte Weiterleitung PSTN, müssen Sie zum Konfigurieren der erforderlichen Richtlinien, um sicherzustellen, dass eingehende Anrufe in Teams empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="f4fde-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="f4fde-152">Sie können die Benutzer zum Festlegen von Teams als bevorzugter Client für Anrufe durch Konfigurieren des Benutzers für Teams nur Kopfzeilen herunterladen, oder Konfigurieren von Teams als bevorzugter Client aufrufende durch Zuweisen von der TeamsCallingPolicy und die TeamsInteropPolicy konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4fde-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="f4fde-153">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="f4fde-153">Ask yourself</span></span>|<span data-ttu-id="f4fde-154">Aktion</span><span class="sxs-lookup"><span data-stu-id="f4fde-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="f4fde-155">Wie soll ich Teams als bevorzugter Client für Anrufe festlegen?</span><span class="sxs-lookup"><span data-stu-id="f4fde-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="f4fde-156">Weitere Informationen finden Sie unter [Microsoft-Teams festgelegt, als der bevorzugte Client für Benutzer aufrufen](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="f4fde-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="f4fde-157">Weitere Bereitstellungsaspekte</span><span class="sxs-lookup"><span data-stu-id="f4fde-157">Additional deployment considerations</span></span>

<span data-ttu-id="f4fde-158">Möglicherweise möchten Sie die folgenden Punkte beachten basierend auf Ihrer Organisation Anforderungen und Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="f4fde-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="f4fde-159">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="f4fde-159">Ask yourself</span></span>| <span data-ttu-id="f4fde-160">Aktion</span><span class="sxs-lookup"><span data-stu-id="f4fde-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="f4fde-161">Haben Sie eine vorhandene Skype für Business Server-Bereitstellung mit hybridkonnektivität konfiguriert?</span><span class="sxs-lookup"><span data-stu-id="f4fde-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="f4fde-162">Zu verstehen, wie Benutzerkonten in einer hybridumgebung bereitgestellt werden, und verwaltet werden, finden Sie unter [Benutzerkonten in einer hybridumgebung mit PSTN-Anbindung](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f4fde-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="f4fde-163">Zum direkten Routing aus aufrufen planen oder aus einem Skype für Business lokalen Umgebung migrieren Sie?</span><span class="sxs-lookup"><span data-stu-id="f4fde-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="f4fde-164">Um weitere Informationen zum Migrieren zu direkten Routing von einer vorhandenen Umgebung zu verstehen, finden Sie unter [Migrating zum direkten Routing](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="f4fde-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
