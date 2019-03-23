---
title: Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Hier erfahren Sie, wie Sie Ihr Microsoft Teams-Netzwerk vorbereiten und verwalten. Unter anderem erhalten Sie Informationen zu den Netzwerkanforderungen, den Bandbreitenanforderungen und zusätzlichen Überlegungen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c39924df868d7d9a3dae45a68b9785a4f493b35a
ms.sourcegitcommit: 889295b507c77a93b10b3a5e826f2b0c79c31f75
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2019
ms.locfileid: "30771710"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="dd2df-104">Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd2df-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="dd2df-105">Microsoft Teams kombiniert drei Arten von Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="dd2df-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="dd2df-106">Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)</span><span class="sxs-lookup"><span data-stu-id="dd2df-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="dd2df-107">Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="dd2df-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="dd2df-108">Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="dd2df-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="dd2df-p102">Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.</span><span class="sxs-lookup"><span data-stu-id="dd2df-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="dd2df-112">Besprechungen werden auf iOS und Android mobilen Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dd2df-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="dd2df-113">Wenn Sie eine optimale wünschen mit Echtzeit-Medien in Microsoft-Teams erhalten möchten, muss Ihr Netzwerk Netzwerken Anforderungen für Office 365 erfüllen.</span><span class="sxs-lookup"><span data-stu-id="dd2df-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="dd2df-114">Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="dd2df-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="dd2df-115">Für die beiden definierenden Netzwerksegmente (Client zum Edge von Microsoft und Kundenedge zum Edge von Microsoft) gelten die folgenden Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="dd2df-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="dd2df-116">Wert</span><span class="sxs-lookup"><span data-stu-id="dd2df-116">Value</span></span>  |<span data-ttu-id="dd2df-117">Client zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dd2df-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="dd2df-118">Kundenedge zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dd2df-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="dd2df-119">**Wartezeit (unidirektional)**\*</span><span class="sxs-lookup"><span data-stu-id="dd2df-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="dd2df-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="dd2df-120">< 50ms</span></span>          |<span data-ttu-id="dd2df-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="dd2df-121">< 30ms</span></span>         |
|<span data-ttu-id="dd2df-122">**Wartezeit (Zeit oder Roundtripzeit)**\*</span><span class="sxs-lookup"><span data-stu-id="dd2df-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="dd2df-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="dd2df-123">< 100ms</span></span>   |<span data-ttu-id="dd2df-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="dd2df-124">< 60ms</span></span> |
|<span data-ttu-id="dd2df-125">**Burstverlust von Paketen**</span><span class="sxs-lookup"><span data-stu-id="dd2df-125">**Burst packet loss**</span></span>    |<span data-ttu-id="dd2df-126">< 10 % in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="dd2df-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="dd2df-127">< 1% in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="dd2df-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="dd2df-128">**Paketverlust**</span><span class="sxs-lookup"><span data-stu-id="dd2df-128">**Packet loss**</span></span>     |<span data-ttu-id="dd2df-129">< 1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="dd2df-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="dd2df-130">< 0,1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="dd2df-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="dd2df-131">**Jitter zwischen der Ankunftszeit von Paketen**</span><span class="sxs-lookup"><span data-stu-id="dd2df-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="dd2df-132">< 30 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="dd2df-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="dd2df-133">< 15 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="dd2df-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="dd2df-134">**Neuanordnung von Paketen**</span><span class="sxs-lookup"><span data-stu-id="dd2df-134">**Packet reorder**</span></span>    |<span data-ttu-id="dd2df-135">< 0,05 % Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="dd2df-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="dd2df-136">< 0,01% Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="dd2df-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="dd2df-137">\*Die Wartezeit metrischen Ziele gehen davon aus Ihrer Firma Website oder Websites und die Microsoft Kanten auf dem gleichen Kontinent.</span><span class="sxs-lookup"><span data-stu-id="dd2df-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="dd2df-138">Die Unternehmen Website-Verbindung mit der Microsoft-Netzwerkgrenze enthält ersten Hop Netzwerkzugriff, WiFi oder einer anderen drahtlosen Technologie werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd2df-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="dd2df-139">Die Netzwerk-Leistungsziele wird vorausgesetzt, ordnungsgemäße Bandbreite und/oder [QoS planen](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="dd2df-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="dd2df-140">Mit anderen Worten, gelten die Anforderungen direkt in Echtzeit Mediendatenverkehr Teams, wenn eine spitzenauslastung die Netzwerkschnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="dd2df-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="dd2df-141">Um beide Netzwerksegmente zu testen, können Sie das [Tool zur Bewertung der Netzwerk](https://go.microsoft.com/fwlink/?linkid=855799)verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd2df-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="dd2df-142">Dieses Tool kann auf dem Client PC direkt und auf einem PC verbunden mit dem Kunden Netzwerkgrenze bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dd2df-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="dd2df-143">Das Tool umfasst begrenzte Dokumentation, aber eine tiefere Dokumentation entsprechend der Verwendung des Tools finden Sie hier: [Bereitschaft des Netzwerks](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="dd2df-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="dd2df-144">Diese Bereitschaft Netzwerk ausführen, können Sie Netzwerks auszuführenden Real-Time Media-Anwendungen wie Microsoft-Teams überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dd2df-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="dd2df-145">Dies ist die gleiche Netzwerk Bereitschaft, die für Kunden ausgeführt werden soll, die erfolgreiche Bereitstellung von Skype für Unternehmen suchen empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="dd2df-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="dd2df-146">Erforderliche Bandbreite</span><span class="sxs-lookup"><span data-stu-id="dd2df-146">Bandwidth requirements</span></span>


<span data-ttu-id="dd2df-147">Dieser Artikel beschreibt eine präzise Version wie Bandbreite von Microsoft-Teams Echtzeit Audio-, Video- und Desktopfreigabe Modalitäten in verschiedene Anwendungsfälle genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="dd2df-147">This article describes a concise version of how bandwidth is utilized by Microsoft Teams real time audio, video, and desktop sharing modalities in various use cases.</span></span> <span data-ttu-id="dd2df-148">Teams ist immer auf bandbreitenauslastung konservativ und HD-Videoqualität in unter 1.2Mbps realisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="dd2df-148">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.2Mbps.</span></span>  <span data-ttu-id="dd2df-149">Die tatsächlichen Bandbreitenverbrauch in einzelnen a/v-Anruf oder Besprechung, hängt Grundlage verschiedener Faktoren, wie video Layout, Auflösung und Videoframes pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="dd2df-149">The actual bandwidth consumption in each audio/video call or meeting will vary, based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="dd2df-150">Wenn mehr Bandbreite verfügbar ist werden die Qualität und Nutzung am besten zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="dd2df-150">When more bandwidth is available quality and usage will increase to deliver the best experience.</span></span>


|<span data-ttu-id="dd2df-151">Bandwidth(Up/Down)</span><span class="sxs-lookup"><span data-stu-id="dd2df-151">Bandwidth(up/down)</span></span> |<span data-ttu-id="dd2df-152">Szenarien</span><span class="sxs-lookup"><span data-stu-id="dd2df-152">Scenarios</span></span> |
|---|---|
|<span data-ttu-id="dd2df-153">30 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="dd2df-153">30 kbps</span></span> |<span data-ttu-id="dd2df-154">Aufrufen von Peer-zu-Peer-audio</span><span class="sxs-lookup"><span data-stu-id="dd2df-154">Peer-to-peer audio calling</span></span> |
|<span data-ttu-id="dd2df-155">130 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="dd2df-155">130 kbps</span></span> |<span data-ttu-id="dd2df-156">Peer-zu-Peer-audio Anruf- und Bildschirmfreigabe</span><span class="sxs-lookup"><span data-stu-id="dd2df-156">Peer-to-peer audio calling and screen sharing</span></span> |
|<span data-ttu-id="dd2df-157">500 KBit/s</span><span class="sxs-lookup"><span data-stu-id="dd2df-157">500 kbps</span></span> |<span data-ttu-id="dd2df-158">Peer-zu-Peer-Bildqualität 360p mit 30fps aufrufen</span><span class="sxs-lookup"><span data-stu-id="dd2df-158">Peer-to-peer quality video calling 360p at 30fps</span></span> |
|<span data-ttu-id="dd2df-159">1.2 Mbit/s</span><span class="sxs-lookup"><span data-stu-id="dd2df-159">1.2 Mbps</span></span> |<span data-ttu-id="dd2df-160">Durch den Aufruf von Auflösung von HD 720p mit 30fps Videoqualität HD Peer-zu-peer</span><span class="sxs-lookup"><span data-stu-id="dd2df-160">Peer-to-peer HD quality video calling with resolution of HD 720p at 30fps</span></span> |
|<span data-ttu-id="dd2df-161">1,5 Mbit/s</span><span class="sxs-lookup"><span data-stu-id="dd2df-161">1.5 Mbps</span></span> |<span data-ttu-id="dd2df-162">Durch den Aufruf von Auflösung von HD 1080p mit 30fps Videoqualität HD Peer-zu-peer</span><span class="sxs-lookup"><span data-stu-id="dd2df-162">Peer-to-peer HD quality video calling with resolution of HD 1080p at 30fps</span></span> |
|<span data-ttu-id="dd2df-163">500 KBit/s/1 Mbit/s</span><span class="sxs-lookup"><span data-stu-id="dd2df-163">500kbps/1Mbps</span></span> |<span data-ttu-id="dd2df-164">Gruppe Video aufrufen</span><span class="sxs-lookup"><span data-stu-id="dd2df-164">Group Video calling</span></span> |
|<span data-ttu-id="dd2df-165">1 Mbit/s/2 Mbit/s</span><span class="sxs-lookup"><span data-stu-id="dd2df-165">1Mbps/2Mbps</span></span> |<span data-ttu-id="dd2df-166">HD-Gruppe video aufrufen (540p Videos auf 1080p Bildschirm)</span><span class="sxs-lookup"><span data-stu-id="dd2df-166">HD Group video calling (540p videos on 1080p screen)</span></span> |

<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="dd2df-167">Zusätzliche Netzwerkaspekte</span><span class="sxs-lookup"><span data-stu-id="dd2df-167">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="dd2df-168">Externe namensauflösung</span><span class="sxs-lookup"><span data-stu-id="dd2df-168">External Name Resolution</span></span>

<span data-ttu-id="dd2df-169">Stellen Sie sicher, dass alle Clientcomputer unter Teams Client externe DNS-Abfragen zum Ermitteln der Dienste von Office 365 beheben können und Ihrer Firewalls Access nicht verhindern.</span><span class="sxs-lookup"><span data-stu-id="dd2df-169">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="dd2df-170">Informationen zum Konfigurieren von Firewallports wechseln Sie zu [Office 365-URLs und IP-Adressbereichen](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="dd2df-170">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="dd2df-171">NAT-Pool-Größe</span><span class="sxs-lookup"><span data-stu-id="dd2df-171">NAT Pool Size</span></span>

<span data-ttu-id="dd2df-172">Bei Office 365 (Network Address Translation, NAT) oder Port Address Translation (PAT) mit Zugriff auf mehrere Benutzer/Geräte müssen Sie sicherstellen, dass die Geräte hinter jeder öffentlich routingfähige IP-Adresse ausgeblendet unterstützte Anzahl nicht überschritten werden.</span><span class="sxs-lookup"><span data-stu-id="dd2df-172">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="dd2df-173">Um dieses Risiko zu verringern, stellen Sie sicher, über ausreichend öffentliche IP-Adressen in der NAT-Pools zu verhindern, dass Port Erschöpfung zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="dd2df-173">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="dd2df-174">Port Erschöpfung bewirkt, dass interne Endbenutzer und Geräten, um Probleme mit der Vorderseite nach beim Verbinden mit Office 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="dd2df-174">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="dd2df-175">Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="dd2df-175">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="dd2df-176">**Erkennung und Prevention Anleitungen**</span><span class="sxs-lookup"><span data-stu-id="dd2df-176">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="dd2df-177">Wenn Ihre Umgebung eine Erkennung und/oder Prevention-System (IDS/IPS) für eine zusätzliche Sicherheitsebene für ausgehende Verbindungen bereitgestellt hat, sicher, dass jeder Datenverkehr mit Ziel zu Office 365-URLs White.</span><span class="sxs-lookup"><span data-stu-id="dd2df-177">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="dd2df-178">Bestimmung der Netzwerk-Integrität</span><span class="sxs-lookup"><span data-stu-id="dd2df-178">Network health determination</span></span>
-----------------

<span data-ttu-id="dd2df-179">Bei der Planung der Implementierung des Microsoft-Teams innerhalb des Netzwerks, müssen Sie darauf achten Sie über die erforderliche Bandbreite verfügen, haben Sie Zugriff auf alle erforderlichen IP-Adressen, die richtigen Ports geöffnet, und Sie sind die leistungsanforderungen für Real-Time Media meeting .</span><span class="sxs-lookup"><span data-stu-id="dd2df-179">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="dd2df-180">Wenn Sie, dass Sie diese Kriterien nicht erfüllt werden wissen, erhalten die Endbenutzer nicht optimal arbeiten von Teams aufgrund ungültiger Qualität während der Anrufe und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="dd2df-180">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="dd2df-181">Sie diesen Kriterien nicht entsprechen soll, ist dies die Zeit, zu berücksichtigen sind Anhalten des Projekts, um sicherzustellen, dass Sie die Kriterien erfüllen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="dd2df-181">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="dd2df-183">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="dd2df-183">Decision Point</span></span>         |<span data-ttu-id="dd2df-184">Haben Sie Ihr Netzwerkfunktionen zur Unterstützung von Real Time Media ausgewertet?</span><span class="sxs-lookup"><span data-stu-id="dd2df-184">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="dd2df-185">Wenn Ihr Netzwerk nicht ordnungsgemäß bewertet oder wissen Sie, dass Real Time Media nicht unterstützt wird, werden Sie Video- und Freigabefunktionen Reduzierung der Netzwerklast und schlechte Erfahrungen von Teams Bildschirm deaktivieren?</span><span class="sxs-lookup"><span data-stu-id="dd2df-185">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="dd2df-187">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dd2df-187">Next Steps</span></span>         |<span data-ttu-id="dd2df-188">Netzwerk-Qualität unbekannt: befolgen Sie die [Bereitschaft des Netzwerks](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) -Anweisungen, um festzustellen, ob Ihr Netzwerk für Real Time Media bereit ist.</span><span class="sxs-lookup"><span data-stu-id="dd2df-188">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="dd2df-189">Anrufe schlechter Qualität der Netzwerk: Führen Sie Netzwerk Remediation Schritte aus, um eine ordnungsgemäße Umgebung für hohe Qualität Real Time Media bieten.</span><span class="sxs-lookup"><span data-stu-id="dd2df-189">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="dd2df-190">Netzwerk befriedigend: Sicher, dass alle IP-Adressen und Ports sind ordnungsgemäß zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="dd2df-190">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="dd2df-191">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="dd2df-191">Related Topics</span></span>

[<span data-ttu-id="dd2df-192">Video: Netzwerkplanung</span><span class="sxs-lookup"><span data-stu-id="dd2df-192">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
