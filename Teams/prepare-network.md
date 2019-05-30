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
ms.openlocfilehash: 330b62bc98d4a45d8d6902707dd2ebb9fd031913
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548278"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="30331-104">Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30331-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="30331-105">Microsoft Teams kombiniert drei Arten von Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="30331-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="30331-106">Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)</span><span class="sxs-lookup"><span data-stu-id="30331-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="30331-107">Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="30331-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="30331-108">Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="30331-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="30331-p102">Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.</span><span class="sxs-lookup"><span data-stu-id="30331-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="30331-112">Besprechungen werden auf mobilen IOS-und Android-Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="30331-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="30331-113">Damit Sie die optimale Nutzung von Echt Zeit Medien in Microsoft Teams erzielen können, muss Ihr Netzwerk die Netzwerkanforderungen für Office 365 erfüllen.</span><span class="sxs-lookup"><span data-stu-id="30331-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="30331-114">Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="30331-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="30331-115">Für die beiden definierenden Netzwerksegmente (Client zum Edge von Microsoft und Kundenedge zum Edge von Microsoft) gelten die folgenden Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="30331-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="30331-116">Wert</span><span class="sxs-lookup"><span data-stu-id="30331-116">Value</span></span>  |<span data-ttu-id="30331-117">Client zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="30331-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="30331-118">Kundenedge zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="30331-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="30331-119">**Latenz (eine Möglichkeit)**\*</span><span class="sxs-lookup"><span data-stu-id="30331-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="30331-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="30331-120">< 50ms</span></span>          |<span data-ttu-id="30331-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="30331-121">< 30ms</span></span>         |
|<span data-ttu-id="30331-122">**Latenz (RTT oder Round-Trip-Zeit)**\*</span><span class="sxs-lookup"><span data-stu-id="30331-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="30331-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="30331-123">< 100ms</span></span>   |<span data-ttu-id="30331-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="30331-124">< 60ms</span></span> |
|<span data-ttu-id="30331-125">**Burstverlust von Paketen**</span><span class="sxs-lookup"><span data-stu-id="30331-125">**Burst packet loss**</span></span>    |<span data-ttu-id="30331-126">< 10 % in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="30331-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="30331-127">< 1% in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="30331-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="30331-128">**Paketverlust**</span><span class="sxs-lookup"><span data-stu-id="30331-128">**Packet loss**</span></span>     |<span data-ttu-id="30331-129">< 1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="30331-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="30331-130">< 0,1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="30331-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="30331-131">**Jitter zwischen der Ankunftszeit von Paketen**</span><span class="sxs-lookup"><span data-stu-id="30331-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="30331-132">< 30 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="30331-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="30331-133">< 15 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="30331-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="30331-134">**Neuanordnung von Paketen**</span><span class="sxs-lookup"><span data-stu-id="30331-134">**Packet reorder**</span></span>    |<span data-ttu-id="30331-135">< 0,05 % Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="30331-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="30331-136">< 0,01% Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="30331-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="30331-137">\*Bei den Metrikdaten für Latenzen wird davon ausgegangen, dass Ihre Unternehmenswebsite oder Ihre Websites und die Microsoft-Ränder auf demselben Kontinent sind.</span><span class="sxs-lookup"><span data-stu-id="30331-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="30331-138">Die Verbindung Ihres Firmenstandorts mit dem Microsoft-Netzwerk-Edge umfasst den Zugriff auf den First Hop-Netzwerkzugriff, der WLAN-oder eine andere drahtlose Technologie sein kann.</span><span class="sxs-lookup"><span data-stu-id="30331-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="30331-139">Die Netzwerk Leistungsziele gehen von der richtigen Bandbreiten-und/oder [QoS-Planung](QoS-in-Teams.md)aus.</span><span class="sxs-lookup"><span data-stu-id="30331-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="30331-140">Anders ausgedrückt: die Anforderungen gelten direkt für Teams in Echtzeit-Mediendatenverkehr, wenn die Netzwerkverbindung unter einer Spitzenauslastung liegt.</span><span class="sxs-lookup"><span data-stu-id="30331-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="30331-141">Zum Testen beider Netzwerksegmente können Sie das [Tool Netzwerkbewertung](https://go.microsoft.com/fwlink/?linkid=855799)verwenden.</span><span class="sxs-lookup"><span data-stu-id="30331-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="30331-142">Dieses Tool kann sowohl auf dem Client-PC direkt als auch auf einem PC bereitgestellt werden, der mit dem Kundennetzwerk-Edge verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="30331-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="30331-143">Das Tool enthält eine begrenzte Dokumentation, aber eine umfassendere Dokumentation rund um die Verwendung des Tools finden Sie hier: [Netzwerk Bereitschaftsbewertung](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="30331-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="30331-144">Wenn Sie diese Netzwerk Bereitschaftsbewertung ausführen, können Sie die Bereitschaft Ihres Netzwerks zur Ausführung von Echt Zeit Medienanwendungen wie Microsoft Teams überprüfen.</span><span class="sxs-lookup"><span data-stu-id="30331-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="30331-145">Hierbei handelt es sich um die gleiche Netzwerk Bereitschaftsbewertung, die für Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="30331-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="30331-146">Bandbreitenanforderungen</span><span class="sxs-lookup"><span data-stu-id="30331-146">Bandwidth requirements</span></span>
<span data-ttu-id="30331-147">Microsoft Teams bietet Ihnen optimale Audio-, Video-und Inhaltsfreigabe Funktionen unabhängig von ihren Netzwerkbedingungen.</span><span class="sxs-lookup"><span data-stu-id="30331-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="30331-148">Mit Variablen Codecs können Medien in Umgebungen mit begrenzter Bandbreite mit minimalen Auswirkungen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="30331-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="30331-149">Wenn die Bandbreite jedoch kein Problem darstellt, können die Erfahrungen für die Qualität optimiert werden, einschließlich einer Videoauflösung von bis zu 1080p, bis zu 30 bps für Video-und 15bps für Inhalte und HiFi-Audio.</span><span class="sxs-lookup"><span data-stu-id="30331-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="30331-150">Zusätzliche Netzwerküberlegungen</span><span class="sxs-lookup"><span data-stu-id="30331-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="30331-151">Auflösung externer Namen</span><span class="sxs-lookup"><span data-stu-id="30331-151">External Name Resolution</span></span>

<span data-ttu-id="30331-152">Stellen Sie sicher, dass alle Clientcomputer, auf denen der Team Client ausgeführt wird, externe DNS-Abfragen beheben können, um die von Office 365 bereitgestellten Dienste zu ermitteln, und dass ihre Firewalls keinen Zugriff verhindern.</span><span class="sxs-lookup"><span data-stu-id="30331-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="30331-153">Informationen zum Konfigurieren von Firewall-Ports finden Sie unter [Office 365-URLs und IP-Bereiche](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="30331-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="30331-154">Größe des NAT-Pools</span><span class="sxs-lookup"><span data-stu-id="30331-154">NAT Pool Size</span></span>

<span data-ttu-id="30331-155">Wenn mehrere Benutzer/Geräte über die Netzwerkadressübersetzung (NAT) oder die Port Address Translation (Pat) auf Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter jeder öffentlich routingfähigen IP-Adresse verborgenen Geräte die unterstützte Nummer nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="30331-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="30331-156">Um dieses Risiko zu verringern, stellen Sie sicher, dass den NAT-Pools angemessene öffentliche IP-Adressen zugewiesen sind, um die Port Erschöpfung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="30331-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="30331-157">Die Port Erschöpfung führt zu internen Endbenutzern und Geräten, die Probleme beim Herstellen einer Verbindung mit den Office 365-Diensten verursachen.</span><span class="sxs-lookup"><span data-stu-id="30331-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="30331-158">Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="30331-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="30331-159">**Leitfaden zur Intrusionserkennung und-Prävention**</span><span class="sxs-lookup"><span data-stu-id="30331-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="30331-160">Wenn in Ihrer Umgebung ein Intrusion Detection-und/oder Prevention-System (IDS/IPS) für eine zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt wird, stellen Sie sicher, dass alle Datenverkehr mit Ziel-zu-Office-365-URLs in der Whitelist aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="30331-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="30331-161">Netzwerk Integritäts Bestimmung</span><span class="sxs-lookup"><span data-stu-id="30331-161">Network health determination</span></span>
-----------------

<span data-ttu-id="30331-162">Bei der Planung der Implementierung von Microsoft Teams in Ihrem Netzwerk müssen Sie sicherstellen, dass Sie über die erforderliche Bandbreite verfügen, Zugriff auf alle erforderlichen IP-Adressen haben, die richtigen Ports öffnen und die Leistungsanforderungen für echt Zeit Medien erfüllen. .</span><span class="sxs-lookup"><span data-stu-id="30331-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="30331-163">Wenn Sie wissen, dass Sie diese Kriterien nicht erfüllen, erhalten Ihre Endbenutzer keine optimale Erfahrung aus Teams aufgrund schlechter Qualität bei Anrufen und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="30331-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="30331-164">Wenn Sie diese Kriterien nicht erfüllen, ist es an der Zeit, das Projekt zu pausieren, um sicherzustellen, dass Sie die Kriterien erfüllen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="30331-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="30331-166">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="30331-166">Decision Point</span></span>         |<span data-ttu-id="30331-167">Haben Sie Ihre Netzwerkfunktionen zur Unterstützung von Echt Zeit Medien bewertet?</span><span class="sxs-lookup"><span data-stu-id="30331-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="30331-168">Wenn Ihr Netzwerk nicht richtig bewertet wurde oder Sie wissen, dass es keine Echt Zeit Medien unterstützt, können Sie die Video-und Bildschirmfreigabe Funktionen deaktivieren, um die Auswirkungen auf das Netzwerk und schlechte Teams zu verringern?</span><span class="sxs-lookup"><span data-stu-id="30331-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="30331-170">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="30331-170">Next Steps</span></span>         |<span data-ttu-id="30331-171">Netzwerkqualität unbekannt: Folgen Sie den Richtlinien zur [Beurteilung der Netzwerk Bereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) , um festzustellen, ob Ihr Netzwerk für echt Zeit Medien bereit ist.</span><span class="sxs-lookup"><span data-stu-id="30331-171">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="30331-172">Schlechte Netzwerkqualität: führen Sie die Schritte zur Netzwerk Sanierung durch, um eine geeignete Umgebung für hochwertige Echt Zeit Medien bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="30331-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="30331-173">Netzwerk zufrieden stellend: Stellen Sie sicher, dass alle IP-Adressen und Ports ordnungsgemäß verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="30331-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="30331-174">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="30331-174">Related Topics</span></span>

[<span data-ttu-id="30331-175">Video: Netzwerkplanung</span><span class="sxs-lookup"><span data-stu-id="30331-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
