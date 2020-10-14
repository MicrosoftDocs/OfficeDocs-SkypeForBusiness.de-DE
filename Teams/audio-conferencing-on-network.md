---
title: Netzwerkkonferenz für Audiokonferenzen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Im folgenden wird die Funktion zum Öffnen der Vorschau für das Netzwerk für Audiokonferenzen beschrieben.
ms.openlocfilehash: 18bd33281379efe7dd2e64019e20a66a2dbec920
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444211"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="ae102-103">Öffnen der Vorschau von Netzwerk Konferenzen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="ae102-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="ae102-104">Die offene Vorschau auf Netzwerk Konferenzen steht allen Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae102-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="ae102-105">Bei Netzwerk Konferenzen können Organisationen eingehende und ausgehende Audiokonferenz-Anrufe an Microsoft-Einwahlnummern über direkte Weiterleitung senden.</span><span class="sxs-lookup"><span data-stu-id="ae102-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="ae102-106">Diese Funktion ist nicht dazu vorgesehen, die Unterstützung von Audiokonferenzen auf Einwahlnummern von Drittanbietern zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ae102-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="ae102-107">Netzwerk Konferenzen werden nicht unterstützt, wenn Sie zum Weiterleiten eingehender Anrufe an den Audio-Konferenzdienst über Einwahlnummern von Drittanbietern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ae102-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="ae102-108">In diesem Artikel werden die Voraussetzungen und Konfigurationsschritte beschrieben, die zum Aktivieren von Netzwerk Konferenzen für Ihre Organisation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ae102-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae102-109">Netzwerk Konferenzen dürfen nicht mit beliebigen Telefongeräten in Indien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ae102-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="ae102-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ae102-110">Prerequisites</span></span>

<span data-ttu-id="ae102-111">Bevor Sie Netzwerk Konferenzen konfigurieren, müssen Sie sicherstellen, dass Ihre Organisation die folgenden Voraussetzungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="ae102-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="ae102-112">Stellen Sie sicher, dass alle Benutzer in Ihrer Organisation, die für Audiokonferenzen aktiviert sind oder aktiviert werden, Teams für alle Besprechungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae102-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="ae102-113">Die Weiterleitung von eingehenden und ausgehenden Audiokonferenz-anrufen über Netzwerk Konferenzen wird nur für Teams-Besprechungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ae102-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="ae102-114">Weisen Sie allen Benutzern, die eine Netzwerkkonferenz verwenden werden, Audiokonferenz-Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="ae102-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="ae102-115">Einrichten des Audio-Konferenz Diensts</span><span class="sxs-lookup"><span data-stu-id="ae102-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="ae102-116">Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ae102-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="ae102-117">Richten Sie Ihren Session Border Controller (SBC) für die direkte Weiterleitung ein.</span><span class="sxs-lookup"><span data-stu-id="ae102-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="ae102-118">Weitere Informationen finden Sie unter [Planen des direkten Routings](direct-routing-plan.md) und [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="ae102-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="ae102-119">Wenn Sie die direkte Weiterleitung nur für Audiokonferenzen einrichten, müssen Sie nur "Schritt 1: Verbinden Ihres SBC" für Netzwerk Konferenzen ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae102-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="ae102-120">Aktivieren des Routings von Einwahl Anrufen an Microsoft-Audiokonferenzen über direktes Routing</span><span class="sxs-lookup"><span data-stu-id="ae102-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="ae102-121">Wenn Sie Einwahl Anrufe, die von Ihren lokalen Benutzern durch direkte Weiterleitung an den Audiokonferenzdienst durchgeführt werden, weiterleiten möchten, müssen Sie geeignete Routingregeln für Ihre SBCS und Private Branch Exchange (s) (PBX) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ae102-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="ae102-122">Sie müssen die Telefonanlage ihrer Websites so konfigurieren, dass Anrufe an eine beliebige Dienstnummer der Konferenzbrücke Ihrer Organisation über einen direkten Routing-Stamm weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ae102-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="ae102-123">Sie finden die Dienstnummern im Team Admin Center unter **Besprechungen – > Konferenz Brücken** oder mithilfe des PowerShell-Cmdlets "CsOnlineDialInConferencingBridge" von Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ae102-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="ae102-124">Weitere Informationen finden Sie in der Liste der [Audiokonferenz-Nummern in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ae102-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ae102-125">Dieses Feature steht Benutzern mit der Lizenz für Pay-per-Minute-Audio-Konferenzen nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae102-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="ae102-126">Aktivieren des Routings von Teams für die Auswahl von Anruf Gesprächen über direktes Routing</span><span class="sxs-lookup"><span data-stu-id="ae102-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="ae102-127">In einer Besprechung in Ihrer Organisation werden Anrufe von Teams für die Anruf Besprechung an PSTN-Nummern initiiert, einschließlich Anrufe und Anrufe, um neue Teilnehmer zu einer Besprechung zu führen.</span><span class="sxs-lookup"><span data-stu-id="ae102-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="ae102-128">Sie müssen eine Richtlinie für die Audiokonferenz-Routing Richtlinie mit dem Namen "OnlineAudioConferencingRoutingPolicy" erstellen und zuweisen, um Teams das Einwahl Routing über das direkte Routing zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ae102-128">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="ae102-129">Die OnlineAudioConferencingRoutingPolicy-Richtlinie entspricht den CsOnlineVoiceRoutingPolicy für 1:1-PSTN-Anrufe über direkte Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="ae102-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="ae102-130">Die OnlineAudioConferencingRoutingPolicy-Richtlinie kann mithilfe der folgenden Cmdlets verwaltet werden:</span><span class="sxs-lookup"><span data-stu-id="ae102-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="ae102-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="ae102-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="ae102-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="ae102-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="ae102-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="ae102-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="ae102-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="ae102-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="ae102-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="ae102-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="ae102-136">Weitere Informationen zum Routing für das direkte Routing finden Sie unter [Konfigurieren des VoIP-Routings für das direkte Routing](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="ae102-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="ae102-137">Um das Routing von Anruf Gesprächen über direktes Routing zu aktivieren, müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ae102-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="ae102-138">Konfigurieren von Richtlinien für die Audiokonferenz-Routing</span><span class="sxs-lookup"><span data-stu-id="ae102-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="ae102-139">Konfigurieren des Routings für die Telefonieanlagen Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="ae102-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="ae102-140">Optional Konfigurieren eines Wählplans</span><span class="sxs-lookup"><span data-stu-id="ae102-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="ae102-141">Anrufe aus Teams-Besprechungen werden von der standardmäßigen Dienstnummer auf der Konferenzbrücke abgewählt.</span><span class="sxs-lookup"><span data-stu-id="ae102-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="ae102-142">Weitere Informationen zur Standarddienst Nummer Ihrer Audiokonferenz-Brücke finden Sie unter [Ändern der Telefonnummern auf der Audiokonferenz-Brücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="ae102-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="ae102-143">Konfigurieren von Richtlinien für die Audiokonferenz-Routing</span><span class="sxs-lookup"><span data-stu-id="ae102-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="ae102-144">Die Richtlinie für die OnlineAudioConferencingRoutingPolicy von Audiokonferenzen bestimmt, welche Besprechungs-Dial-Out-Anrufe an Direct Routing-Stämme weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ae102-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="ae102-145">Wenn Sie mit der CsOnlineVoiceRoutingPolicy-Richtlinie vertraut sind, funktioniert diese Richtlinie auf eine sehr ähnliche Weise.</span><span class="sxs-lookup"><span data-stu-id="ae102-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="ae102-146">Die folgenden Schritte sind erforderlich, um Richtlinien für die Audiokonferenz-Routing Einrichtung einzurichten:</span><span class="sxs-lookup"><span data-stu-id="ae102-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="ae102-147">Erstellen von PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="ae102-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="ae102-148">Konfigurieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="ae102-148">Configure voice routes</span></span>
3.  <span data-ttu-id="ae102-149">Erstellen von VoIP-Routing Richtlinien für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="ae102-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="ae102-150">Zuweisen einer Richtlinie zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="ae102-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="ae102-151">Erstellen von PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="ae102-151">Create PSTN usages</span></span>

<span data-ttu-id="ae102-152">PSTN-Nutzungen sind Sammlungen von VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="ae102-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="ae102-153">Wenn ein Auswähl-Anruf aus der Besprechung eines bestimmten Organisators initiiert wird, werden VoIP-Routen verwendet, um den Routingpfad des Anrufs anhand der PSTN-Nutzungen zu ermitteln, die dem Benutzer über die VoIP-Routing Richtlinie des Benutzers zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ae102-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="ae102-154">Sie können eine PSTN-Nutzung mithilfe des Cmdlets "festgelegte CsOnlinePstnUsage" erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae102-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="ae102-155">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ae102-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="ae102-156">Konfigurieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="ae102-156">Configure voice routes</span></span>

<span data-ttu-id="ae102-157">VoIP-Routen bestimmen das PSTN-Gateway, das zum Weiterleiten eines Anrufs basierend auf der Telefonnummer verwendet werden soll, die von einer Teambesprechung gewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ae102-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="ae102-158">VoIP-Routen ermitteln das PSTN-Gateway, das zum Weiterleiten eines bestimmten Anrufs verwendet werden soll, indem Sie die von einer Teambesprechung gewählte Telefonnummer mit einem Regex-Muster vergleichen.</span><span class="sxs-lookup"><span data-stu-id="ae102-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="ae102-159">Beim Erstellen einer VoIP-Route muss die Route mindestens einer PSTN-Nutzung zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="ae102-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="ae102-160">Mithilfe des Cmdlets "New-CsOnlineVoiceRoute" können Sie eine VoIP-Route erstellen und die Regex und Gateways definieren, die mit der VoIP-Route verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ae102-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="ae102-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ae102-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="ae102-162">Erstellen von VoIP-Routing Richtlinien für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="ae102-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="ae102-163">Audiokonferenz-VoIP-Routing Richtlinien ermitteln die möglichen Routen, die verwendet werden können, um einen Anruf aus den Besprechungen eines Organisators basierend auf der Zieltelefonnummer des Anrufs für die Besprechung zu leiten.</span><span class="sxs-lookup"><span data-stu-id="ae102-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="ae102-164">Audiokonferenz-VoIP-Routing Richtlinien sind einer oder mehreren PSTN-Nutzungen zugeordnet, die wiederum die möglichen Routen ermitteln, die für die Besprechung von Wähl anrufen der Organisatoren verwendet werden, die der Richtlinie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ae102-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="ae102-165">Mit dem Cmdlet "New-CsOnlineAudioConferencingRoutingPolicy" können Sie eine VoIP-Routing Richtlinie für Audiokonferenzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae102-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="ae102-166">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ae102-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="ae102-167">Nachdem die Richtlinie einem Benutzer zugewiesen wurde und ein Anruf aus einer der Besprechungen des Benutzers initiiert wird, werden die VoIP-Routen in den PSTN-Nutzungen, die dem Organisator über die VoIP-Routing Richtlinie des Benutzers zugeordnet sind, ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ae102-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="ae102-168">Wenn das Ziel des Anrufs für die Besprechungs Auswahl mit einem Regex in einer der VoIP-Routen übereinstimmt, die dem Organisator zugeordnet sind, wird der Anruf zur Anruf Abwahl an das PSTN-Gateway weitergeleitet, das in der VoIP-Route definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae102-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="ae102-169">Wenn das Anruf Ziel des Besprechungs Anrufs nicht mit den VoIP-Routen übereinstimmt, die dem Organisator zugeordnet sind, wird der Anruf zur Anruf Abwahl von Microsoft weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ae102-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="ae102-170">Zuweisen einer Richtlinie zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="ae102-170">Assign a policy to your users</span></span>

<span data-ttu-id="ae102-171">Nachdem Sie die Richtlinien für die Audiokonferenz-Routing definiert haben, können Sie Sie nun Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ae102-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="ae102-172">Nachdem ihnen Richtlinien zugewiesen wurden, werden die Anruf Abwahlen für Besprechungen ausgewertet, um deren Routingpfad zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ae102-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="ae102-173">Richtlinien für die Audiokonferenz-Routing werden immer basierend auf dem Organisator der Besprechung ausgewertet, unabhängig vom Benutzer in der Besprechung, der einen Anruf zur Anruf Besprechung initiiert.</span><span class="sxs-lookup"><span data-stu-id="ae102-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="ae102-174">Sie können einem Benutzer mithilfe des Cmdlets "Grant-CsOnlineAudioConferencingRoutingPolicy" eine VoIP-Routing Richtlinie für Audiokonferenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ae102-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="ae102-175">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ae102-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="ae102-176">Konfigurieren des Routings für die Telefonieanlagen Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="ae102-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="ae102-177">Auf der Telefonieanlage Ihrer Organisation müssen Sie sicherstellen, dass die durch direkte Weiterleitung geleiteten Wähl Anruf Anrufe an das beabsichtigte Netzwerkziel weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ae102-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="ae102-178">Optional Konfigurieren eines Wählplans</span><span class="sxs-lookup"><span data-stu-id="ae102-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="ae102-179">Bei einem Wählplan handelt es sich um eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern von einem einzelnen Benutzer in ein alternatives Format (in der Regel E. 164) übersetzen, um eine Anruf Autorisierung und ein Anrufrouting zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae102-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="ae102-180">Standardmäßig können Benutzer von Teams im E. 164-Format, also +, zu PSTN-Nummern wählen \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="ae102-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="ae102-181">Wählpläne können jedoch verwendet werden, um Benutzern die Wahl von Telefonnummern in anderen Formaten zu ermöglichen, beispielsweise vierstellige Durchwahlnummern.</span><span class="sxs-lookup"><span data-stu-id="ae102-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="ae102-182">Wenn Sie das Erweiterungs basierte wählen über Netzwerk Konferenzen aktivieren möchten, können Sie die Wählpläne so einrichten, dass Sie mit dem Wählmuster für Durchwahlnummern der Rufnummernbereiche der Telefonnummer Ihrer Organisation übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ae102-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="ae102-183">Informationen zum Einrichten von Wählplänen finden Sie unter [Erstellen und Verwalten von Wähl](create-and-manage-dial-plans.md)Plänen.</span><span class="sxs-lookup"><span data-stu-id="ae102-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="ae102-184">Bekannte Probleme in der geöffneten Vorschau</span><span class="sxs-lookup"><span data-stu-id="ae102-184">Known issues in Open Preview</span></span>

<span data-ttu-id="ae102-185">Im folgenden finden Sie eine Liste bekannter Probleme, die derzeit in der Open Preview-Version von Netzwerk Konferenzen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ae102-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="ae102-186">Microsoft arbeitet an der Behebung dieser Probleme.</span><span class="sxs-lookup"><span data-stu-id="ae102-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="ae102-187">Problem</span><span class="sxs-lookup"><span data-stu-id="ae102-187">Issue</span></span> | <span data-ttu-id="ae102-188">Workaround</span><span class="sxs-lookup"><span data-stu-id="ae102-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="ae102-189">Einwahl Anrufe mit anonymen/versteckten Rufnummern Anzeigern, die über Netzwerk Konferenzen weitergeleitet werden, können nicht mit der Besprechung verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="ae102-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="ae102-190">Wenn möglich, legen Sie eine Konfiguration in Ihrer Telefonanlage oder SBC fest, um immer eine Rufnummernanzeige für Anrufe zu senden, die über Netzwerk Konferenzen weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ae102-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="ae102-191">In einigen Fällen wird die Willkommensnachricht, die den Benutzern beim Einwählen in den Dienst ("Willkommen beim Audiokonferenzdienst...") abgespielt wird, abgeschnitten, und die Benutzer hören nicht das "Willkommen"-Wort.</span><span class="sxs-lookup"><span data-stu-id="ae102-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="ae102-192">Zurzeit gibt es keine Problemumgehungen für dieses Problem.</span><span class="sxs-lookup"><span data-stu-id="ae102-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="ae102-193">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ae102-193">Related topics</span></span>


