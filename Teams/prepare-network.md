---
title: Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
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
ms.openlocfilehash: de9092e9253ef93268d19fb8ff8e74261e4d44a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898580"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="fc497-104">Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc497-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="fc497-105">Microsoft Teams kombiniert drei Arten von Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="fc497-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="fc497-106">Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)</span><span class="sxs-lookup"><span data-stu-id="fc497-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="fc497-107">Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="fc497-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="fc497-108">Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="fc497-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="fc497-p102">Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.</span><span class="sxs-lookup"><span data-stu-id="fc497-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="fc497-112">Besprechungen werden auf iOS und Android mobilen Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc497-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="fc497-113">Wenn Sie eine optimale wünschen mit Echtzeit-Medien in Microsoft-Teams erhalten möchten, muss Ihr Netzwerk Netzwerken Anforderungen für Office 365 erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fc497-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="fc497-114">Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="fc497-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="fc497-115">Für die beiden definierenden Netzwerksegmente (Client zum Edge von Microsoft und Kundenedge zum Edge von Microsoft) gelten die folgenden Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="fc497-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="fc497-116">Wert</span><span class="sxs-lookup"><span data-stu-id="fc497-116">Value</span></span>  |<span data-ttu-id="fc497-117">Client zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fc497-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="fc497-118">Kundenedge zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fc497-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="fc497-119">**Wartezeit (unidirektional)**\*</span><span class="sxs-lookup"><span data-stu-id="fc497-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="fc497-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="fc497-120">< 50ms</span></span>          |<span data-ttu-id="fc497-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="fc497-121">< 30ms</span></span>         |
|<span data-ttu-id="fc497-122">**Wartezeit (Zeit oder Roundtripzeit)**\*</span><span class="sxs-lookup"><span data-stu-id="fc497-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="fc497-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="fc497-123">< 100ms</span></span>   |<span data-ttu-id="fc497-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="fc497-124">< 60ms</span></span> |
|<span data-ttu-id="fc497-125">**Burstverlust von Paketen**</span><span class="sxs-lookup"><span data-stu-id="fc497-125">**Burst packet loss**</span></span>    |<span data-ttu-id="fc497-126">< 10 % in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="fc497-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="fc497-127">< 1% in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="fc497-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="fc497-128">**Paketverlust**</span><span class="sxs-lookup"><span data-stu-id="fc497-128">**Packet loss**</span></span>     |<span data-ttu-id="fc497-129">< 1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="fc497-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="fc497-130">< 0,1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="fc497-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="fc497-131">**Jitter zwischen der Ankunftszeit von Paketen**</span><span class="sxs-lookup"><span data-stu-id="fc497-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="fc497-132">< 30 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="fc497-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="fc497-133">< 15 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="fc497-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="fc497-134">**Neuanordnung von Paketen**</span><span class="sxs-lookup"><span data-stu-id="fc497-134">**Packet reorder**</span></span>    |<span data-ttu-id="fc497-135">< 0,05 % Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="fc497-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="fc497-136">< 0,01% Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="fc497-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="fc497-137">\*Die Wartezeit metrischen Ziele gehen davon aus Ihrer Firma Website oder Websites und die Microsoft Kanten auf dem gleichen Kontinent.</span><span class="sxs-lookup"><span data-stu-id="fc497-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="fc497-138">Die Unternehmen Website-Verbindung mit der Microsoft-Netzwerkgrenze enthält ersten Hop Netzwerkzugriff, WiFi oder einer anderen drahtlosen Technologie werden kann.</span><span class="sxs-lookup"><span data-stu-id="fc497-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="fc497-139">Die Netzwerk-Leistungsziele wird vorausgesetzt, ordnungsgemäße Bandbreite und/oder [QoS planen](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="fc497-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="fc497-140">Mit anderen Worten, gelten die Anforderungen direkt in Echtzeit Mediendatenverkehr Teams, wenn eine spitzenauslastung die Netzwerkschnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="fc497-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="fc497-141">Um beide Netzwerksegmente zu testen, können Sie das [Tool zur Bewertung der Netzwerk](https://go.microsoft.com/fwlink/?linkid=855799)verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc497-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="fc497-142">Dieses Tool kann auf dem Client PC direkt und auf einem PC verbunden mit dem Kunden Netzwerkgrenze bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fc497-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="fc497-143">Das Tool umfasst begrenzte Dokumentation, aber eine tiefere Dokumentation entsprechend der Verwendung des Tools finden Sie hier: [Bereitschaft des Netzwerks](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="fc497-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="fc497-144">Diese Bereitschaft Netzwerk ausführen, können Sie Netzwerks auszuführenden Real-Time Media-Anwendungen wie Microsoft-Teams überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fc497-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="fc497-145">Dies ist die gleiche Netzwerk Bereitschaft, die für Kunden ausgeführt werden soll, die erfolgreiche Bereitstellung von Skype für Unternehmen suchen empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="fc497-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="fc497-146">Erforderliche Bandbreite</span><span class="sxs-lookup"><span data-stu-id="fc497-146">Bandwidth requirements</span></span>
<span data-ttu-id="fc497-147">Microsoft-Teams, können Sie die beste Audio-, Video- und unabhängig von den netzwerkbedingungen Erfahrung von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="fc497-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="fc497-148">Mit den Variablen Codecs können Medien in Umgebungen mit minimaler Beeinträchtigung eingeschränkter Bandbreite ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="fc497-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="fc497-149">Aber wo Bandbreite kein Belang ist, können Erfahrungen optimiert für die Qualität, videoauflösung 1080p, einschließlich von bis zu 30 f/s für Video und 15fps für Inhalte und Audio mit hoher Qualität.</span><span class="sxs-lookup"><span data-stu-id="fc497-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


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

<a name="additional-network-considerations"></a><span data-ttu-id="fc497-150">Zusätzliche Netzwerkaspekte</span><span class="sxs-lookup"><span data-stu-id="fc497-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="fc497-151">Externe namensauflösung</span><span class="sxs-lookup"><span data-stu-id="fc497-151">External Name Resolution</span></span>

<span data-ttu-id="fc497-152">Stellen Sie sicher, dass alle Clientcomputer unter Teams Client externe DNS-Abfragen zum Ermitteln der Dienste von Office 365 beheben können und Ihrer Firewalls Access nicht verhindern.</span><span class="sxs-lookup"><span data-stu-id="fc497-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="fc497-153">Informationen zum Konfigurieren von Firewallports wechseln Sie zu [Office 365-URLs und IP-Adressbereichen](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="fc497-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="fc497-154">NAT-Pool-Größe</span><span class="sxs-lookup"><span data-stu-id="fc497-154">NAT Pool Size</span></span>

<span data-ttu-id="fc497-155">Bei Office 365 (Network Address Translation, NAT) oder Port Address Translation (PAT) mit Zugriff auf mehrere Benutzer/Geräte müssen Sie sicherstellen, dass die Geräte hinter jeder öffentlich routingfähige IP-Adresse ausgeblendet unterstützte Anzahl nicht überschritten werden.</span><span class="sxs-lookup"><span data-stu-id="fc497-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="fc497-156">Um dieses Risiko zu verringern, stellen Sie sicher, über ausreichend öffentliche IP-Adressen in der NAT-Pools zu verhindern, dass Port Erschöpfung zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="fc497-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="fc497-157">Port Erschöpfung bewirkt, dass interne Endbenutzer und Geräten, um Probleme mit der Vorderseite nach beim Verbinden mit Office 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="fc497-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="fc497-158">Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="fc497-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="fc497-159">**Erkennung und Prevention Anleitungen**</span><span class="sxs-lookup"><span data-stu-id="fc497-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="fc497-160">Wenn Ihre Umgebung eine Erkennung und/oder Prevention-System (IDS/IPS) für eine zusätzliche Sicherheitsebene für ausgehende Verbindungen bereitgestellt hat, sicher, dass jeder Datenverkehr mit Ziel zu Office 365-URLs White.</span><span class="sxs-lookup"><span data-stu-id="fc497-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="fc497-161">Bestimmung der Netzwerk-Integrität</span><span class="sxs-lookup"><span data-stu-id="fc497-161">Network health determination</span></span>
-----------------

<span data-ttu-id="fc497-162">Bei der Planung der Implementierung des Microsoft-Teams innerhalb des Netzwerks, müssen Sie darauf achten Sie über die erforderliche Bandbreite verfügen, haben Sie Zugriff auf alle erforderlichen IP-Adressen, die richtigen Ports geöffnet, und Sie sind die leistungsanforderungen für Real-Time Media meeting .</span><span class="sxs-lookup"><span data-stu-id="fc497-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="fc497-163">Wenn Sie, dass Sie diese Kriterien nicht erfüllt werden wissen, erhalten die Endbenutzer nicht optimal arbeiten von Teams aufgrund ungültiger Qualität während der Anrufe und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="fc497-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="fc497-164">Sie diesen Kriterien nicht entsprechen soll, ist dies die Zeit, zu berücksichtigen sind Anhalten des Projekts, um sicherzustellen, dass Sie die Kriterien erfüllen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fc497-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="fc497-166">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="fc497-166">Decision Point</span></span>         |<span data-ttu-id="fc497-167">Haben Sie Ihr Netzwerkfunktionen zur Unterstützung von Real Time Media ausgewertet?</span><span class="sxs-lookup"><span data-stu-id="fc497-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="fc497-168">Wenn Ihr Netzwerk nicht ordnungsgemäß bewertet oder wissen Sie, dass Real Time Media nicht unterstützt wird, werden Sie Video- und Freigabefunktionen Reduzierung der Netzwerklast und schlechte Erfahrungen von Teams Bildschirm deaktivieren?</span><span class="sxs-lookup"><span data-stu-id="fc497-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="fc497-170">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fc497-170">Next Steps</span></span>         |<span data-ttu-id="fc497-171">Netzwerk-Qualität unbekannt: befolgen Sie die [Bereitschaft des Netzwerks](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) -Anweisungen, um festzustellen, ob Ihr Netzwerk für Real Time Media bereit ist.</span><span class="sxs-lookup"><span data-stu-id="fc497-171">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="fc497-172">Anrufe schlechter Qualität der Netzwerk: Führen Sie Netzwerk Remediation Schritte aus, um eine ordnungsgemäße Umgebung für hohe Qualität Real Time Media bieten.</span><span class="sxs-lookup"><span data-stu-id="fc497-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="fc497-173">Netzwerk befriedigend: Sicher, dass alle IP-Adressen und Ports sind ordnungsgemäß zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="fc497-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="fc497-174">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fc497-174">Related Topics</span></span>

[<span data-ttu-id="fc497-175">Video: Netzwerkplanung</span><span class="sxs-lookup"><span data-stu-id="fc497-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
