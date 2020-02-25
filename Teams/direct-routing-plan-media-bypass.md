---
title: Planen der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: In diesem Thema erfahren Sie, wie Sie die medienumgehung mit dem direkten Routing des Telefonsystems planen.
ms.openlocfilehash: c40840e2169a67172f006a0f0910c715feb40253
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265640"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="82c03-103">Planen der Medienumgehung mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="82c03-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="82c03-104">Informationen zur medienumgehung mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="82c03-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="82c03-105">Mit der medienumgehung können Sie den Pfad des Mediendatenverkehrs verkürzen und die Anzahl der Hops auf der Übertragung reduzieren, um eine bessere Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="82c03-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="82c03-106">Bei der medienumgehung werden Medien zwischen dem Session Border Controller (SBC) und dem Client aufbewahrt, anstatt Sie über das Microsoft Phone-System zu senden.</span><span class="sxs-lookup"><span data-stu-id="82c03-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="82c03-107">Um die medienumgehung zu konfigurieren, muss sich der SBC und der Client am gleichen Standort oder im gleichen Netzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="82c03-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="82c03-108">Sie können die medienumgehung für jeden SBC mithilfe des Befehls " **CSOnlinePSTNGateway** " Steuern, wobei der **-MediaBypass-** Parameter auf "true" oder "false" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="82c03-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="82c03-109">Wenn Sie die medienumgehung aktivieren, bedeutet dies nicht, dass der gesamte Mediendatenverkehr im Unternehmensnetzwerk verbleibt.</span><span class="sxs-lookup"><span data-stu-id="82c03-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="82c03-110">In diesem Artikel wird der Anruffluss in verschiedenen Szenarien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82c03-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="82c03-111">Die folgenden Diagramme veranschaulichen den Unterschied beim Anruffluss mit und ohne medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="82c03-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="82c03-112">Ohne medienumgehung wird, wenn ein Client einen Anruf tätigt oder empfängt, sowohl der Signalisierungs-als auch der Medienfluss zwischen dem SBC, dem Microsoft Phone-System und dem Teams-Client erfolgen, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="82c03-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![Zeigt Signalisierungs-und Medienfluss ohne medienumgehung](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="82c03-114">Angenommen, ein Benutzer befindet sich im selben Gebäude oder Netzwerk wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="82c03-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="82c03-115">Angenommen, ein Benutzer, der sich in einem Gebäude in Frankfurt befindet, führt einen Anruf an einen PSTN-Benutzer durch:</span><span class="sxs-lookup"><span data-stu-id="82c03-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="82c03-116">**Ohne medienumgehung**fließen Medien entweder über Amsterdam oder Dublin (wo Microsoft-Rechenzentren bereitgestellt werden) und zurück zum SBC in Frankfurt.</span><span class="sxs-lookup"><span data-stu-id="82c03-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="82c03-117">Das Rechenzentrum in Europa ist ausgewählt, da sich der SBC in Europa befindet, und Microsoft verwendet das Rechenzentrum, das dem SBC am nächsten ist.</span><span class="sxs-lookup"><span data-stu-id="82c03-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="82c03-118">Dieser Ansatz hat zwar keine Auswirkungen auf die Anrufqualität aufgrund einer Optimierung des Datenverkehrs in Microsoft-Netzwerken in den meisten Regionen, aber der Datenverkehr hat eine unnötige Schleife.</span><span class="sxs-lookup"><span data-stu-id="82c03-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="82c03-119">**Bei der medienumgehung**wird das Medium direkt zwischen dem Team Benutzer und dem SBC aufbewahrt, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="82c03-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![Zeigt Signalisierungs-und Medienfluss mit medienumgehung](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="82c03-121">Die medienumgehung nutzt die Protokolle namens Interactive Connectivity Establishment (ICE) auf dem Microsoft Teams-Client und Ice lite auf dem SBC.</span><span class="sxs-lookup"><span data-stu-id="82c03-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="82c03-122">Mithilfe dieser Protokolle können Sie Direktes Routing verwenden, um den direktesten Medienpfad für optimale Qualität zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c03-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="82c03-123">Ice und Ice lite sind WebRTC-Standards.</span><span class="sxs-lookup"><span data-stu-id="82c03-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="82c03-124">Ausführliche Informationen zu diesen Protokollen finden Sie unter RFC 5245.</span><span class="sxs-lookup"><span data-stu-id="82c03-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="82c03-125">Anruffluss-und Firewall-Planung</span><span class="sxs-lookup"><span data-stu-id="82c03-125">Call flow and firewall planning</span></span>

<span data-ttu-id="82c03-126">Die Planung des Anrufflusses und der Firewall hängt davon ab, ob der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat und ob sich der Benutzer innerhalb oder außerhalb des Netzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="82c03-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="82c03-127">Anruffluss, wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat</span><span class="sxs-lookup"><span data-stu-id="82c03-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="82c03-128">Wenn der Benutzer direkten Zugriff auf die öffentliche IP-Adresse des SBC hat, sieht der Anruffluss wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="82c03-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="82c03-129">Bei der medienumgehung muss der Team-Clientzugriff auf die öffentliche IP-Adresse des SBC haben, auch über ein internes Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="82c03-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="82c03-130">Wenn kein direktes Medium erwünscht ist, kann das Medium über Transport-Relays fließen.</span><span class="sxs-lookup"><span data-stu-id="82c03-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="82c03-131">Dies ist die empfohlene Lösung, wenn sich ein Benutzer im gleichen Gebäude und/oder im gleichen Netzwerk wie der SBC befindet – entfernen Sie Microsoft Cloud-Komponenten aus dem Medienpfad.</span><span class="sxs-lookup"><span data-stu-id="82c03-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="82c03-132">Die Signalübertragung fließt immer über die Microsoft-Cloud.</span><span class="sxs-lookup"><span data-stu-id="82c03-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="82c03-133">Das folgende Diagramm zeigt den Anruffluss, wenn die medienumgehung aktiviert ist, der Client intern ist und der Client die öffentliche IP-Adresse des SBC (Direct Media) erreichen kann:</span><span class="sxs-lookup"><span data-stu-id="82c03-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="82c03-134">Die Pfeile und numerischen Werte der Pfade entsprechen dem [Microsoft Teams Call Flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) -Artikel.</span><span class="sxs-lookup"><span data-stu-id="82c03-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="82c03-135">Das SIP-Signal nimmt immer die Pfade 4 und 4 auf (je nach Verkehrsrichtung).</span><span class="sxs-lookup"><span data-stu-id="82c03-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="82c03-136">Das Medium bleibt lokal und nimmt den Pfad 5B.</span><span class="sxs-lookup"><span data-stu-id="82c03-136">Media stays local and takes path 5b.</span></span>

![Anzeige des Anrufflusses mit aktivierter medienumgehung, Client ist intern](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="82c03-138">Anruffluss, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat</span><span class="sxs-lookup"><span data-stu-id="82c03-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="82c03-139">Im folgenden wird der Anruffluss beschrieben, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat.</span><span class="sxs-lookup"><span data-stu-id="82c03-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="82c03-140">Angenommen, der Benutzer ist extern, und der mandantenadministrator hat entschieden, die öffentliche IP-Adresse des SBC nicht für jeden im Internet, sondern nur für die Microsoft-Cloud zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="82c03-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="82c03-141">Die internen Komponenten des Datenverkehrs können über die Teams-Transport-Relays fließen.</span><span class="sxs-lookup"><span data-stu-id="82c03-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="82c03-142">Dies ist die empfohlene Konfiguration für Benutzer außerhalb des Unternehmensnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="82c03-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="82c03-143">Beachten Sie dabei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="82c03-143">Consider the following:</span></span>

- <span data-ttu-id="82c03-144">Es werden Transport-Relays für Teams verwendet.</span><span class="sxs-lookup"><span data-stu-id="82c03-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="82c03-145">Bei der medienumgehung verwendet Microsoft eine Version von Transport-Relays, die das Öffnen von Ports 50 000 bis 59 999 zwischen den Teams-Transport-Relays und dem SBC erfordert (in Zukunft planen wir, zu der Version zu wechseln, die nur 3478-und 3479-Ports erfordert).</span><span class="sxs-lookup"><span data-stu-id="82c03-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="82c03-146">Zu Zwecken der Medienoptimierung empfiehlt Microsoft, die öffentliche IP-Adresse des SBC nur für Teams-Transport-Relays zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="82c03-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="82c03-147">Für Clients außerhalb des Unternehmensnetzwerks empfiehlt Microsoft die Verwendung von Transport-Relays, anstatt die öffentliche IP-Adresse des SBC direkt zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="82c03-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="82c03-148">Das folgende Diagramm zeigt den Anruffluss, wenn die medienumgehung aktiviert ist, der Client ist extern, und der Client kann die öffentliche IP-Adresse des Session Border Controllers nicht erreichen (Medien werden von Teams Transport Relay weitergeleitet).</span><span class="sxs-lookup"><span data-stu-id="82c03-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="82c03-149">Die Pfeile und numerischen Werte der Pfade entsprechen dem [Microsoft Teams Call Flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) -Artikel.</span><span class="sxs-lookup"><span data-stu-id="82c03-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="82c03-150">Medien werden über die Pfade 3, 3 ', 4 und 4 ' weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="82c03-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="82c03-152">Anruffluss, wenn sich ein Benutzer außerhalb des Netzwerks befindet und Zugriff auf die öffentliche IP des SBC hat</span><span class="sxs-lookup"><span data-stu-id="82c03-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="82c03-153">Diese Konfiguration wird nicht empfohlen, da Sie nicht die Vorteile von Teams-Transport-Relays nutzt.</span><span class="sxs-lookup"><span data-stu-id="82c03-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="82c03-154">Stattdessen sollten Sie das vorherige Szenario berücksichtigen, in dem der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat.</span><span class="sxs-lookup"><span data-stu-id="82c03-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="82c03-155">Das folgende Diagramm zeigt den Anruffluss, wenn die medienumgehung aktiviert ist, der Client ist extern, und der Client kann die öffentliche IP-Adresse des SBC (Direct Media) erreichen.</span><span class="sxs-lookup"><span data-stu-id="82c03-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="82c03-156">Die Pfeile und numerischen Werte der Pfade entsprechen dem [Microsoft Teams Call Flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) -Artikel.</span><span class="sxs-lookup"><span data-stu-id="82c03-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="82c03-157">Das SIP-Signal nimmt immer die Pfade 3 und 3 auf (abhängig von der Richtung des Datenverkehrs).</span><span class="sxs-lookup"><span data-stu-id="82c03-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="82c03-158">Mediendatenströme mit Pfad 2.</span><span class="sxs-lookup"><span data-stu-id="82c03-158">Media flows using path 2.</span></span>

![Zeigt den Anruffluss an, wenn der Benutzer keinen Zugriff auf die öffentliche IP-Adresse des SBC hat](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="82c03-160">Verwendung von Medien Prozessoren und Transport-Relays</span><span class="sxs-lookup"><span data-stu-id="82c03-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="82c03-161">Es gibt zwei Komponenten in der Microsoft-Cloud, die sich im Pfad des Medien Verkehrs befinden können: Medien Prozessoren und Transport-Relays.</span><span class="sxs-lookup"><span data-stu-id="82c03-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="82c03-162">Der medienprozessor ist eine öffentlich zugängliche Komponente, die Medien in nicht-Bypass-Fällen verarbeitet und Medien für Sprachanwendungen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="82c03-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="82c03-163">Medien Prozessoren sind für Endbenutzer, die keine Umgehungs Anrufe führen, immer im Pfad, aber niemals im Pfad für umgegangene Anrufe.</span><span class="sxs-lookup"><span data-stu-id="82c03-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="82c03-164">Medien Prozessoren sind immer im Pfad für alle Sprachanwendungen wie "Parken von Anrufen", "organisatorische automatische Telefonzentrale" und "Anrufwarteschlangen".</span><span class="sxs-lookup"><span data-stu-id="82c03-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="82c03-165">Das Transport-Relay wird verwendet, um eine Verbindung mit dem nächstgelegenen Transportdienst herzustellen, um Echtzeitverkehr zu senden.</span><span class="sxs-lookup"><span data-stu-id="82c03-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="82c03-166">Transport-Relays befinden sich möglicherweise nicht im Pfad für umgeleitete Anrufe – die von Endbenutzern stammen oder dazu bestimmt sind – je nachdem, wo sich der Benutzer befindet und wie das Netzwerk konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="82c03-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="82c03-167">Das folgende Diagramm zeigt zwei Anruf Flüsse: eine mit aktivierter medienumgehung und die zweite mit deaktivierter medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="82c03-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="82c03-168">Hinweis Das Diagramm zeigt nur Datenverkehr, der von--oder bestimmten-Endbenutzern stammt.</span><span class="sxs-lookup"><span data-stu-id="82c03-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="82c03-169">Der Medien Controller ist ein microservice in Azure, der Medien Prozessoren zuordnet und SDP-Angebote (Session Description Protocol) erstellt.</span><span class="sxs-lookup"><span data-stu-id="82c03-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="82c03-170">Der SIP-Proxy ist eine Komponente, die http-Ruhe Signalisierungen übersetzt, die in Teams für SIP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82c03-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![Zeigt Anruf Flüsse mit aktivierter und deaktivierter medienumgehung](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="82c03-172">In der nachstehenden Tabelle werden die Unterschiede zwischen Medien Prozessoren und Transport-Relays zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="82c03-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="82c03-173">Medien Prozessoren</span><span class="sxs-lookup"><span data-stu-id="82c03-173">Media Processors</span></span> | <span data-ttu-id="82c03-174">Transport-Relays</span><span class="sxs-lookup"><span data-stu-id="82c03-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="82c03-175">Im Medienpfad für nicht Umgehungs Anrufe für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="82c03-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="82c03-176">Immer</span><span class="sxs-lookup"><span data-stu-id="82c03-176">Always</span></span> | <span data-ttu-id="82c03-177">Nie</span><span class="sxs-lookup"><span data-stu-id="82c03-177">Never</span></span> | 
<span data-ttu-id="82c03-178">Im Medienpfad für umgehende Anrufe für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="82c03-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="82c03-179">Nie</span><span class="sxs-lookup"><span data-stu-id="82c03-179">Never</span></span> | <span data-ttu-id="82c03-180">Wenn der Client den SBC für die öffentliche IP-Adresse nicht erreichen kann</span><span class="sxs-lookup"><span data-stu-id="82c03-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="82c03-181">In Medienpfad für Sprachanwendungen</span><span class="sxs-lookup"><span data-stu-id="82c03-181">In media path for voice applications</span></span> | <span data-ttu-id="82c03-182">Immer</span><span class="sxs-lookup"><span data-stu-id="82c03-182">Always</span></span> | <span data-ttu-id="82c03-183">Nie</span><span class="sxs-lookup"><span data-stu-id="82c03-183">Never</span></span> | 
<span data-ttu-id="82c03-184">Can do Transcodierung (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="82c03-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="82c03-185">Ja</span><span class="sxs-lookup"><span data-stu-id="82c03-185">Yes</span></span> | <span data-ttu-id="82c03-186">Nein, nur Audio zwischen Endpunkten weiterleiten</span><span class="sxs-lookup"><span data-stu-id="82c03-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="82c03-187">Anzahl der Instanzen weltweit und Standort</span><span class="sxs-lookup"><span data-stu-id="82c03-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="82c03-188">8 gesamt: 2 in den USA Ost und West; 2 in Amsterdam und Dublin; 2 in Hongkong und Singapur; 2 in Japan</span><span class="sxs-lookup"><span data-stu-id="82c03-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan</span></span>  | <span data-ttu-id="82c03-189">Mehrere</span><span class="sxs-lookup"><span data-stu-id="82c03-189">Multiple</span></span>

<span data-ttu-id="82c03-190">Der IP-Bereich ist 52.112.0.0/14 (IP-Adressen von 52.112.0.1 zu 52.115.255.254).</span><span class="sxs-lookup"><span data-stu-id="82c03-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="82c03-191">\*Erläuterung der Transcodierung:</span><span class="sxs-lookup"><span data-stu-id="82c03-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="82c03-192">Der medienprozessor ist B2BUA, was bedeutet, dass er einen Codec ändern kann (beispielsweise Seide vom Microsoft Teams-Client zu MP und G. 711 zwischen MP und SBC).</span><span class="sxs-lookup"><span data-stu-id="82c03-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="82c03-193">Transport-Relays sind nicht B2BUA, was bedeutet, dass der Codec nie zwischen dem Client und dem SBC geändert wird – auch wenn der Datenverkehr über Relays abläuft.</span><span class="sxs-lookup"><span data-stu-id="82c03-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="82c03-194">Verwendung von Teams-Medien Prozessoren, wenn trunk für die medienumgehung konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="82c03-194">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="82c03-195">Teams-Medien Prozessoren werden in den folgenden Szenarien immer in den Medienpfad eingefügt:</span><span class="sxs-lookup"><span data-stu-id="82c03-195">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="82c03-196">Anruf wird von 1:1 zu einem Gruppenanruf eskaliert</span><span class="sxs-lookup"><span data-stu-id="82c03-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="82c03-197">Der Anruf wird an einen Benutzer von Federated Teams weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="82c03-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="82c03-198">Der Anruf wird an einen Skype for Business-Nutzer weitergeleitet oder übertragen</span><span class="sxs-lookup"><span data-stu-id="82c03-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="82c03-199">Stellen Sie sicher, dass Ihr SBC Zugriff auf die Medien Prozessoren und Transport-Relays-Bereiche hat, wie nachstehend beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82c03-199">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="82c03-200">SIP-Signalisierung: FQDNs</span><span class="sxs-lookup"><span data-stu-id="82c03-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="82c03-201">Für SIP-Signalisierungen sind die Anforderungen für FQDN und Firewall dieselben wie für nicht Umgehungs Fälle.</span><span class="sxs-lookup"><span data-stu-id="82c03-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="82c03-202">Das direkte Routing wird in den folgenden Office 365-Umgebungen angeboten:</span><span class="sxs-lookup"><span data-stu-id="82c03-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="82c03-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="82c03-203">Office 365</span></span>
- <span data-ttu-id="82c03-204">Office 365 gcc</span><span class="sxs-lookup"><span data-stu-id="82c03-204">Office 365 GCC</span></span>
- <span data-ttu-id="82c03-205">Office 365 gcc-höchst</span><span class="sxs-lookup"><span data-stu-id="82c03-205">Office 365 GCC High</span></span>
- <span data-ttu-id="82c03-206">Office 365 DoD Weitere Informationen zu [Office 365-und US Government-Umgebungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) wie gcc, gcc-groß und DoD.</span><span class="sxs-lookup"><span data-stu-id="82c03-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="82c03-207">Office 365 und Office 365 gcc-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="82c03-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="82c03-208">Die Verbindungspunkte für die direkte Weiterleitung sind die folgenden drei FQDNs:</span><span class="sxs-lookup"><span data-stu-id="82c03-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="82c03-209">**SIP.pstnhub.Microsoft.com** – globaler FQDN – muss zuerst ausprobiert werden.</span><span class="sxs-lookup"><span data-stu-id="82c03-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="82c03-210">Wenn der SBC eine Anforderung zum Beheben dieses Namens sendet, geben die Microsoft Azure-DNS-Server eine IP-Adresse zurück, die auf das primäre Azure Datacenter verweist, das dem SBC zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="82c03-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="82c03-211">Die Aufgabe basiert auf den Leistungs Metriken der Rechenzentren und der geographischen Nähe zum SBC.</span><span class="sxs-lookup"><span data-stu-id="82c03-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="82c03-212">Die zurückgegebene IP-Adresse entspricht dem primären FQDN.</span><span class="sxs-lookup"><span data-stu-id="82c03-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="82c03-213">**sip2.pstnhub.Microsoft.com** – sekundärer FQDN – wird geografisch dem zweiten Prioritätsbereich zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="82c03-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="82c03-214">**sip3.pstnhub.Microsoft.com** – tertiärer FQDN – ordnet geographisch dem dritten Prioritätsbereich zu.</span><span class="sxs-lookup"><span data-stu-id="82c03-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="82c03-215">Sie müssen diese drei FQDNs platzieren, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="82c03-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="82c03-216">Optimale Benutzerfreundlichkeit (geringere Belastung und Nähe zum SBC-Rechenzentrum, das durch Abfragen des ersten FQDN zugeordnet ist).</span><span class="sxs-lookup"><span data-stu-id="82c03-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="82c03-217">Stellen Sie ein Failover bereit, wenn eine Verbindung von einem SBC zu einem Datacenter hergestellt wird, bei dem ein temporäres Problem auftritt.</span><span class="sxs-lookup"><span data-stu-id="82c03-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="82c03-218">Weitere Informationen finden Sie unten unter Failover-Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="82c03-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="82c03-219">Die FQDNs **SIP.pstnhub.Microsoft.com**, **sip2.pstnhub.Microsoft.com**und **sip3.pstnhub.Microsoft.com** werden in eine der folgenden IP-Adressen aufgelöst:</span><span class="sxs-lookup"><span data-stu-id="82c03-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="82c03-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="82c03-220">52.114.148.0</span></span>
- <span data-ttu-id="82c03-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="82c03-221">52.114.132.46</span></span>
- <span data-ttu-id="82c03-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="82c03-222">52.114.75.24</span></span>
- <span data-ttu-id="82c03-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="82c03-223">52.114.76.76</span></span>
- <span data-ttu-id="82c03-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="82c03-224">52.114.7.24</span></span>
- <span data-ttu-id="82c03-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="82c03-225">52.114.14.70</span></span>

<span data-ttu-id="82c03-226">Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="82c03-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="82c03-227">Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN- **SIP-all.pstnhub.Microsoft.com** in alle diese IP-Adressen aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="82c03-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="82c03-228">Office 365 gcc DoD-Umgebung</span><span class="sxs-lookup"><span data-stu-id="82c03-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="82c03-229">Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:</span><span class="sxs-lookup"><span data-stu-id="82c03-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="82c03-230">**SIP.pstnhub.DoD.Teams.Microsoft.US** – globaler FQDN.</span><span class="sxs-lookup"><span data-stu-id="82c03-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="82c03-231">Da die Office 365 DoD-Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.</span><span class="sxs-lookup"><span data-stu-id="82c03-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="82c03-232">Die FQDNs – SIP.pstnhub.DoD.Teams.Microsoft.US werden in eine der folgenden IP-Adressen aufgelöst:</span><span class="sxs-lookup"><span data-stu-id="82c03-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="82c03-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="82c03-233">52.127.64.33</span></span>
- <span data-ttu-id="82c03-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="82c03-234">52.127.68.34</span></span>

<span data-ttu-id="82c03-235">Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="82c03-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="82c03-236">Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN-SIP.pstnhub.DoD.Teams.Microsoft.US in alle diese IP-Adressen aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="82c03-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="82c03-237">Office 365 gcc-höchst Umgebung</span><span class="sxs-lookup"><span data-stu-id="82c03-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="82c03-238">Der Verbindungspunkt für das direkte Routing ist der folgende FQDN:</span><span class="sxs-lookup"><span data-stu-id="82c03-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="82c03-239">**SIP.pstnhub.gov.Teams.Microsoft.US** – globaler FQDN.</span><span class="sxs-lookup"><span data-stu-id="82c03-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="82c03-240">Da die gcc-höchst Umgebung nur in den US-Rechenzentren vorhanden ist, gibt es keine sekundären und tertiären FQDNs.</span><span class="sxs-lookup"><span data-stu-id="82c03-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="82c03-241">Die FQDNs – SIP.pstnhub.gov.Teams.Microsoft.US werden in eine der folgenden IP-Adressen aufgelöst:</span><span class="sxs-lookup"><span data-stu-id="82c03-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="82c03-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="82c03-242">52.127.88.59</span></span>
- <span data-ttu-id="82c03-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="82c03-243">52.127.92.64</span></span>

<span data-ttu-id="82c03-244">Sie müssen Ports für alle diese IP-Adressen in Ihrer Firewall öffnen, um eingehenden und ausgehenden Datenverkehr zu und von den Adressen für das signalisieren zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="82c03-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="82c03-245">Wenn Ihre Firewall DNS-Namen unterstützt, wird der FQDN-SIP.pstnhub.gov.Teams.Microsoft.US in alle diese IP-Adressen aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="82c03-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="82c03-246">SIP-Signalisierung: Anschlüsse</span><span class="sxs-lookup"><span data-stu-id="82c03-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="82c03-247">Die Port Anforderungen sind für alle Office 365-Umgebungen identisch, in denen Direktes Routing angeboten wird:</span><span class="sxs-lookup"><span data-stu-id="82c03-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="82c03-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="82c03-248">Office 365</span></span>
- <span data-ttu-id="82c03-249">Office 365 gcc</span><span class="sxs-lookup"><span data-stu-id="82c03-249">Office 365 GCC</span></span>
- <span data-ttu-id="82c03-250">Office 365 gcc-höchst</span><span class="sxs-lookup"><span data-stu-id="82c03-250">Office 365 GCC High</span></span>
- <span data-ttu-id="82c03-251">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="82c03-251">Office 365 DoD</span></span>

<span data-ttu-id="82c03-252">Sie müssen die folgenden Ports verwenden:</span><span class="sxs-lookup"><span data-stu-id="82c03-252">You must use the following ports:</span></span>

| <span data-ttu-id="82c03-253">Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="82c03-253">Traffic</span></span> | <span data-ttu-id="82c03-254">Von</span><span class="sxs-lookup"><span data-stu-id="82c03-254">From</span></span> | <span data-ttu-id="82c03-255">Bis</span><span class="sxs-lookup"><span data-stu-id="82c03-255">To</span></span> | <span data-ttu-id="82c03-256">Quellport</span><span class="sxs-lookup"><span data-stu-id="82c03-256">Source port</span></span> | <span data-ttu-id="82c03-257">Zielport</span><span class="sxs-lookup"><span data-stu-id="82c03-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="82c03-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="82c03-258">SIP/TLS</span></span>| <span data-ttu-id="82c03-259">SIP-Proxy</span><span class="sxs-lookup"><span data-stu-id="82c03-259">SIP Proxy</span></span> | <span data-ttu-id="82c03-260">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-260">SBC</span></span> | <span data-ttu-id="82c03-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="82c03-261">1024 - 65535</span></span> | <span data-ttu-id="82c03-262">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-262">Defined on the SBC</span></span> |
| <span data-ttu-id="82c03-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="82c03-263">SIP/TLS</span></span> | <span data-ttu-id="82c03-264">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-264">SBC</span></span> | <span data-ttu-id="82c03-265">SIP-Proxy</span><span class="sxs-lookup"><span data-stu-id="82c03-265">SIP Proxy</span></span> | <span data-ttu-id="82c03-266">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-266">Defined on the SBC</span></span> | <span data-ttu-id="82c03-267">5061</span><span class="sxs-lookup"><span data-stu-id="82c03-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="82c03-268">Mediendatenverkehr: IP-und Port Bereiche</span><span class="sxs-lookup"><span data-stu-id="82c03-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="82c03-269">Der Mediendatenverkehr fließt zwischen dem SBC-und dem Teams-Client, wenn direkte Konnektivität verfügbar ist, oder über Teams Transport Relays, wenn der Client den SBC nicht über die öffentliche IP-Adresse erreichen kann.</span><span class="sxs-lookup"><span data-stu-id="82c03-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="82c03-270">Voraussetzungen für direkten Medien Verkehr (zwischen dem Teams-Client und dem SBC)</span><span class="sxs-lookup"><span data-stu-id="82c03-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="82c03-271">Der Client muss Zugriff auf die angegebenen Ports (siehe Tabelle) für die öffentliche IP-Adresse des SBC haben.</span><span class="sxs-lookup"><span data-stu-id="82c03-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="82c03-272">Hinweis: Wenn sich der Client in einem internen Netzwerk befindet, fließt das Medium an die öffentliche IP-Adresse des SBC.</span><span class="sxs-lookup"><span data-stu-id="82c03-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="82c03-273">Sie können das Anheften von Haaren auf Ihrem NAT-Gerät so konfigurieren, dass der Datenverkehr nie das Netzwerkequipment des Unternehmens verlässt.</span><span class="sxs-lookup"><span data-stu-id="82c03-273">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="82c03-274">Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="82c03-274">Traffic</span></span> | <span data-ttu-id="82c03-275">Von</span><span class="sxs-lookup"><span data-stu-id="82c03-275">From</span></span> | <span data-ttu-id="82c03-276">Bis</span><span class="sxs-lookup"><span data-stu-id="82c03-276">To</span></span> | <span data-ttu-id="82c03-277">Quellport</span><span class="sxs-lookup"><span data-stu-id="82c03-277">Source port</span></span> | <span data-ttu-id="82c03-278">Zielport</span><span class="sxs-lookup"><span data-stu-id="82c03-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="82c03-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="82c03-279">UDP/SRTP</span></span> | <span data-ttu-id="82c03-280">Client</span><span class="sxs-lookup"><span data-stu-id="82c03-280">Client</span></span> | <span data-ttu-id="82c03-281">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-281">SBC</span></span> | <span data-ttu-id="82c03-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="82c03-282">50 000 – 50 019</span></span>  | <span data-ttu-id="82c03-283">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-283">Defined on the SBC</span></span> |
| <span data-ttu-id="82c03-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="82c03-284">UDP/SRTP</span></span> | <span data-ttu-id="82c03-285">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-285">SBC</span></span> | <span data-ttu-id="82c03-286">Client</span><span class="sxs-lookup"><span data-stu-id="82c03-286">Client</span></span> | <span data-ttu-id="82c03-287">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-287">Defined on the SBC</span></span> | <span data-ttu-id="82c03-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="82c03-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="82c03-289">Hinweis: Wenn Sie über ein Netzwerkgerät verfügen, das die Quell Anschlüsse des Clients übersetzt, stellen Sie sicher, dass übersetzte Ports zwischen dem Netzwerkgerät und dem SBC geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="82c03-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="82c03-290">Voraussetzungen für die Verwendung von Transport-Relays</span><span class="sxs-lookup"><span data-stu-id="82c03-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="82c03-291">Transport-Relays befinden sich im gleichen Bereich wie Medien Prozessoren (für nicht-Bypass-Fälle):</span><span class="sxs-lookup"><span data-stu-id="82c03-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="82c03-292">Office 365 und Office 365 gcc-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="82c03-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="82c03-293">-52.112.0.0/14 (IP-Adressen von 52.112.0.1 nach 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="82c03-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="82c03-294">Office 365 gcc DoD-Umgebung</span><span class="sxs-lookup"><span data-stu-id="82c03-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="82c03-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="82c03-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="82c03-296">Office 365 gcc-höchst Umgebung</span><span class="sxs-lookup"><span data-stu-id="82c03-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="82c03-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="82c03-297">52.127.88.0/21</span></span>


<span data-ttu-id="82c03-298">Der Portbereich der Teams-Transport-Relays (für alle Umgebungen) ist in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="82c03-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="82c03-299">Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="82c03-299">Traffic</span></span> | <span data-ttu-id="82c03-300">Von</span><span class="sxs-lookup"><span data-stu-id="82c03-300">From</span></span> | <span data-ttu-id="82c03-301">Bis</span><span class="sxs-lookup"><span data-stu-id="82c03-301">To</span></span> | <span data-ttu-id="82c03-302">Quellport</span><span class="sxs-lookup"><span data-stu-id="82c03-302">Source port</span></span> | <span data-ttu-id="82c03-303">Zielport</span><span class="sxs-lookup"><span data-stu-id="82c03-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="82c03-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="82c03-304">UDP/SRTP</span></span> | <span data-ttu-id="82c03-305">Transport-Relay</span><span class="sxs-lookup"><span data-stu-id="82c03-305">Transport Relay</span></span> | <span data-ttu-id="82c03-306">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-306">SBC</span></span> | <span data-ttu-id="82c03-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="82c03-307">50 000 -59 999</span></span>    | <span data-ttu-id="82c03-308">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-308">Defined on the SBC</span></span> |
| <span data-ttu-id="82c03-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="82c03-309">UDP/SRTP</span></span> | <span data-ttu-id="82c03-310">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-310">SBC</span></span> | <span data-ttu-id="82c03-311">Transport-Relay</span><span class="sxs-lookup"><span data-stu-id="82c03-311">Transport Relay</span></span> | <span data-ttu-id="82c03-312">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-312">Defined on the SBC</span></span> | <span data-ttu-id="82c03-313">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="82c03-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="82c03-314">Hinweis: Microsoft empfiehlt mindestens zwei Ports pro gleichzeitigen Anruf im SBC.</span><span class="sxs-lookup"><span data-stu-id="82c03-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="82c03-315">Da Microsoft über zwei Versionen von Transport-Relays verfügt, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="82c03-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="82c03-316">V4, das nur mit Portbereich 50 000 bis 59 999 funktionieren kann</span><span class="sxs-lookup"><span data-stu-id="82c03-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="82c03-317">V6, das mit Ports 3478, 3479, kompatibel ist</span><span class="sxs-lookup"><span data-stu-id="82c03-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="82c03-318">Zu diesem Zeitpunkt unterstützt Media Bypass nur die V4-Version von Transport-Relays.</span><span class="sxs-lookup"><span data-stu-id="82c03-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="82c03-319">Wir werden die Unterstützung von V6 in Zukunft vorstellen.</span><span class="sxs-lookup"><span data-stu-id="82c03-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="82c03-320">Sie müssen Ports 3478 und 3479 für den Übergang öffnen.</span><span class="sxs-lookup"><span data-stu-id="82c03-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="82c03-321">Wenn Microsoft Unterstützung für V6-Transport-Relays mit Media Bypass einführt, müssen Sie Ihre Netzwerkausrüstung oder SBCS nicht neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="82c03-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="82c03-322">Voraussetzungen für die Verwendung von Medien Prozessoren</span><span class="sxs-lookup"><span data-stu-id="82c03-322">Requirements for using media processors</span></span>

<span data-ttu-id="82c03-323">Medien Prozessoren sind immer im Medienpfad für Sprachanwendungen und für Webclients (beispielsweise Teams-Clients in Edge oder Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="82c03-323">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="82c03-324">Die Anforderungen sind identisch mit der Konfiguration ohne Bypass.</span><span class="sxs-lookup"><span data-stu-id="82c03-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="82c03-325">Der IP-Bereich für den Medien Verkehr ist</span><span class="sxs-lookup"><span data-stu-id="82c03-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="82c03-326">Office 365 und Office 365 gcc-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="82c03-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="82c03-327">-52.112.0.0/14 (IP-Adressen von 52.112.0.1 nach 52.115.255.254)</span><span class="sxs-lookup"><span data-stu-id="82c03-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="82c03-328">Office 365 gcc DoD-Umgebung</span><span class="sxs-lookup"><span data-stu-id="82c03-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="82c03-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="82c03-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="82c03-330">Office 365 gcc-höchst Umgebung</span><span class="sxs-lookup"><span data-stu-id="82c03-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="82c03-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="82c03-331">52.127.88.0/21</span></span>

<span data-ttu-id="82c03-332">In der folgenden Tabelle wird der Portbereich der Medien Prozessoren (für alle Umgebungen) angezeigt:</span><span class="sxs-lookup"><span data-stu-id="82c03-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="82c03-333">Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="82c03-333">Traffic</span></span> | <span data-ttu-id="82c03-334">Von</span><span class="sxs-lookup"><span data-stu-id="82c03-334">From</span></span> | <span data-ttu-id="82c03-335">Bis</span><span class="sxs-lookup"><span data-stu-id="82c03-335">To</span></span> | <span data-ttu-id="82c03-336">Quellport</span><span class="sxs-lookup"><span data-stu-id="82c03-336">Source port</span></span> | <span data-ttu-id="82c03-337">Zielport</span><span class="sxs-lookup"><span data-stu-id="82c03-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="82c03-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="82c03-338">UDP/SRTP</span></span> | <span data-ttu-id="82c03-339">Medienprozessor</span><span class="sxs-lookup"><span data-stu-id="82c03-339">Media Processor</span></span> | <span data-ttu-id="82c03-340">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-340">SBC</span></span> | <span data-ttu-id="82c03-341">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="82c03-341">49 152 – 53 247</span></span>    | <span data-ttu-id="82c03-342">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-342">Defined on the SBC</span></span> |
| <span data-ttu-id="82c03-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="82c03-343">UDP/SRTP</span></span> | <span data-ttu-id="82c03-344">Sbchttps</span><span class="sxs-lookup"><span data-stu-id="82c03-344">SBC</span></span> | <span data-ttu-id="82c03-345">Medienprozessor</span><span class="sxs-lookup"><span data-stu-id="82c03-345">Media Processor</span></span> | <span data-ttu-id="82c03-346">Im SBC definiert</span><span class="sxs-lookup"><span data-stu-id="82c03-346">Defined on the SBC</span></span> | <span data-ttu-id="82c03-347">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="82c03-347">49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="82c03-348">Konfigurieren separater Trunks für medienumgehung und nicht medienumgehung</span><span class="sxs-lookup"><span data-stu-id="82c03-348">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="82c03-349">Wenn Sie von einer nicht-medienumgehung zur medienumgehung migrieren und die Funktionalität vor dem Migrieren aller Nutzungen zur medienumgehung bestätigen möchten, können Sie einen separaten trunk und eine separate Online-VoIP-Routing Richtlinie erstellen, um Sie an den Medien Umgehungs trunk weiterzuleiten und bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="82c03-349">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="82c03-350">Konfigurationsschritte auf höherer Ebene:</span><span class="sxs-lookup"><span data-stu-id="82c03-350">High-level configuration steps:</span></span>

- <span data-ttu-id="82c03-351">Identifizieren Sie Benutzer, um die medienumgehung zu testen.</span><span class="sxs-lookup"><span data-stu-id="82c03-351">Identify users to test media bypass.</span></span>

- <span data-ttu-id="82c03-352">Erstellen Sie zwei getrennte Stämme mit unterschiedlichen FQDNs: eine für die medienumgehung aktivierte Option; der andere nicht.</span><span class="sxs-lookup"><span data-stu-id="82c03-352">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="82c03-353">Beide Trunks zeigen auf denselben SBC.</span><span class="sxs-lookup"><span data-stu-id="82c03-353">Both trunks point to the same SBC.</span></span> <span data-ttu-id="82c03-354">Die Ports für TLS-SIP-Signalisierungen müssen unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="82c03-354">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="82c03-355">Die Ports für Medien müssen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="82c03-355">The ports for media must be the same.</span></span>

- <span data-ttu-id="82c03-356">Erstellen Sie eine neue Online-VoIP-Routing Richtlinie, und weisen Sie den Medien Umgehungs trunk den entsprechenden Routen zu, die der PSTN-Verwendung für diese Richtlinie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="82c03-356">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="82c03-357">Weisen Sie den Benutzern, die Sie identifiziert haben, die medienumgehung zu testen, die neue Online-VoIP-Routing Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="82c03-357">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="82c03-358">Im folgenden Beispiel wird diese Logik veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="82c03-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="82c03-359">Gruppe von Benutzern</span><span class="sxs-lookup"><span data-stu-id="82c03-359">Set of users</span></span> | <span data-ttu-id="82c03-360">Anzahl der Benutzer</span><span class="sxs-lookup"><span data-stu-id="82c03-360">Number of users</span></span> | <span data-ttu-id="82c03-361">In OVRP zugewiesener trunk-FQDN</span><span class="sxs-lookup"><span data-stu-id="82c03-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="82c03-362">Medienumgehung aktiviert</span><span class="sxs-lookup"><span data-stu-id="82c03-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="82c03-363">Benutzer mit nicht Medien Umgehungs trunk</span><span class="sxs-lookup"><span data-stu-id="82c03-363">Users with non-media bypass trunk</span></span> | <span data-ttu-id="82c03-364">980</span><span class="sxs-lookup"><span data-stu-id="82c03-364">980</span></span> | <span data-ttu-id="82c03-365">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="82c03-365">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="82c03-366">True</span><span class="sxs-lookup"><span data-stu-id="82c03-366">true</span></span>
<span data-ttu-id="82c03-367">Benutzer mit Medien Umgehungs trunk</span><span class="sxs-lookup"><span data-stu-id="82c03-367">Users with media bypass trunk</span></span> | <span data-ttu-id="82c03-368">20</span><span class="sxs-lookup"><span data-stu-id="82c03-368">20</span></span> | <span data-ttu-id="82c03-369">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="82c03-369">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="82c03-370">false</span><span class="sxs-lookup"><span data-stu-id="82c03-370">false</span></span> | 

<span data-ttu-id="82c03-371">Beide Trunks können auf denselben SBC mit der gleichen öffentlichen IP-Adresse verweisen.</span><span class="sxs-lookup"><span data-stu-id="82c03-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="82c03-372">Die TLS-Signalisierungs Anschlüsse auf dem SBC müssen unterschiedlich sein, wie in der nachstehenden Abbildung zu sehen ist.</span><span class="sxs-lookup"><span data-stu-id="82c03-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="82c03-373">Hinweis Sie müssen sicherstellen, dass Ihr Zertifikat beide Trunks unterstützt.</span><span class="sxs-lookup"><span data-stu-id="82c03-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="82c03-374">In San benötigen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.</span><span class="sxs-lookup"><span data-stu-id="82c03-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![Zeigt, dass beide Trunks auf denselben SBC mit der gleichen öffentlichen IP-Adresse verweisen können.](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="82c03-376">Informationen zum Konfigurieren von zwei Stämmen im gleichen SBC finden Sie in der Dokumentation Ihres SBC-Anbieters:</span><span class="sxs-lookup"><span data-stu-id="82c03-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="82c03-377">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="82c03-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="82c03-378">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="82c03-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="82c03-379">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="82c03-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="82c03-380">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="82c03-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="82c03-381">Mit der medienumgehung unterstützte Client Endpunkte</span><span class="sxs-lookup"><span data-stu-id="82c03-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="82c03-382">Die medienumgehung wird für alle Teams-Desktop Clients und Teams-Telefongeräte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="82c03-382">Media bypass is supported with all Teams Desktop clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="82c03-383">Für alle anderen Endpunkte, die keine medienumgehung unterstützen, wird der Anruf an non-Bypass abgestellt, auch wenn er als Bypass-Anruf gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="82c03-383">For all other endpoints that do not support media bypass, we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="82c03-384">Dies geschieht automatisch und erfordert keine Aktionen des Administrators.</span><span class="sxs-lookup"><span data-stu-id="82c03-384">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="82c03-385">Dazu gehören Skype for Business 3PIP-Telefone und Teams-Webclients, die direkte Routing Anrufe unterstützen (neuer Microsoft Edge basierend auf Chrom, Google Chrome, Mozilla Firefox).</span><span class="sxs-lookup"><span data-stu-id="82c03-385">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (New Microsoft Edge based on Chromium, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="82c03-386">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82c03-386">See also</span></span>

[<span data-ttu-id="82c03-387">Konfigurieren der Medienumgehung mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="82c03-387">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



