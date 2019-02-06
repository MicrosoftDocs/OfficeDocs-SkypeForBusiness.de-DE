---
title: Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: Hier erfahren Sie, wie Sie Ihr Microsoft Teams-Netzwerk vorbereiten und verwalten. Unter anderem erhalten Sie Informationen zu den Netzwerkanforderungen, den Bandbreitenanforderungen und zusätzlichen Überlegungen.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6b95da8ee416d4f64d22a8c0622acd417b7bb1d
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742848"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="980c1-104">Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="980c1-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

> [!Tip]
> <span data-ttu-id="980c1-105">Sehen Sie sich die folgenden Sitzung erfahren, wie Sie Teams nutzt Ihr Netzwerk und am besten für die optimale Netzwerkkonnektivität planen: [Teams Netzwerkplanung](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="980c1-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="980c1-106">Microsoft Teams kombiniert drei Arten von Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="980c1-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="980c1-107">Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)</span><span class="sxs-lookup"><span data-stu-id="980c1-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="980c1-108">Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="980c1-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="980c1-109">Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="980c1-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="980c1-p102">Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.</span><span class="sxs-lookup"><span data-stu-id="980c1-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="980c1-113">Besprechungen werden auf iOS und Android mobilen Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="980c1-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="980c1-114">Für die optimale Verwendung von Echtzeitmedien in Microsoft Teams müssen die Netzwerkanforderungen für Office 365 erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="980c1-114">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="980c1-115">Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="980c1-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="980c1-116">Sollten Sie für die zwei definierenden Netzwerksegmente (Client Microsoft Edge) und Customer Kante Microsoft Edge die folgenden Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="980c1-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="980c1-117">Wert</span><span class="sxs-lookup"><span data-stu-id="980c1-117">Value</span></span>  |<span data-ttu-id="980c1-118">Client zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="980c1-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="980c1-119">Kundenedge zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="980c1-119">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="980c1-120">**Latenz (ein Weg)**</span><span class="sxs-lookup"><span data-stu-id="980c1-120">**Latency (one way)**</span></span>     |<span data-ttu-id="980c1-121">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="980c1-121">< 50ms</span></span>          |<span data-ttu-id="980c1-122">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="980c1-122">< 30ms</span></span>          |
|<span data-ttu-id="980c1-123">**Latenz (RTT oder Roundtripzeit)**</span><span class="sxs-lookup"><span data-stu-id="980c1-123">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="980c1-124">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="980c1-124">< 100ms</span></span>         |<span data-ttu-id="980c1-125">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="980c1-125">< 60ms</span></span>         |
|<span data-ttu-id="980c1-126">**Burstverlust von Paketen**</span><span class="sxs-lookup"><span data-stu-id="980c1-126">**Burst packet loss**</span></span>    |<span data-ttu-id="980c1-127">< 10 % in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="980c1-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="980c1-128">< 1% in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="980c1-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="980c1-129">**Paketverlust**</span><span class="sxs-lookup"><span data-stu-id="980c1-129">**Packet loss**</span></span>     |<span data-ttu-id="980c1-130">< 1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="980c1-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="980c1-131">< 0,1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="980c1-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="980c1-132">**Jitter zwischen der Ankunftszeit von Paketen**</span><span class="sxs-lookup"><span data-stu-id="980c1-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="980c1-133">< 30 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="980c1-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="980c1-134">< 15 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="980c1-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="980c1-135">**Neuanordnung von Paketen**</span><span class="sxs-lookup"><span data-stu-id="980c1-135">**Packet reorder**</span></span>    |<span data-ttu-id="980c1-136">< 0,05 % Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="980c1-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="980c1-137">< 0,01% Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="980c1-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="980c1-138">Um beide Netzwerksegmente zu testen, können Sie das [Network Assessment-Tool](https://go.microsoft.com/fwlink/?linkid=855799) verwenden.</span><span class="sxs-lookup"><span data-stu-id="980c1-138">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="980c1-139">Dieses Tool kann direkt auf dem Client-PC sowie auf einem PC, der mit dem Netzwerkedge des Kunden verbunden ist, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="980c1-139">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="980c1-140">Das Tool selbst enthält eine begrenzte Dokumentation, eine umfassendere Dokumentation zur Verwendung des Tools finden Sie hier: [Bewertung der Netzwerkbereitschaft](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="980c1-140">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="980c1-141">Indem Sie diese Bewertung der Netzwerkbereitschaft ausführen, können Sie die Bereitschaft Ihres Netzwerks für die Ausführung von Echtzeitmedienanwendungen wie beispielsweise Microsoft Teams validieren.</span><span class="sxs-lookup"><span data-stu-id="980c1-141">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="980c1-142">Dabei handelt es sich um die gleiche Bewertung der Netzwerkbereitschaft, deren Ausführung Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="980c1-142">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="980c1-143">Bandbreitenanforderungen</span><span class="sxs-lookup"><span data-stu-id="980c1-143">Bandwidth requirements</span></span>
----------

<span data-ttu-id="980c1-144">Bandbreitenberechnungen für Microsoft Teams sind komplex. Zu Ihrer Unterstützung wurde ein Rechner erstellt.</span><span class="sxs-lookup"><span data-stu-id="980c1-144">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="980c1-145">Den Rechner finden Sie unter [„Netzwerkplaner“ in MyAdvisor](https://aka.ms/bwcalc/).</span><span class="sxs-lookup"><span data-stu-id="980c1-145">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

> [!NOTE]
> <span data-ttu-id="980c1-146">Behandlung von Teams Bandbreite wurden verbessert Skype für Business Online: für eine hohe Qualität aufrufen oder meeting-Erfahrung (mit Audio, Video und Freigabe), Teams nur 1,2 Mbit/s benötigt.</span><span class="sxs-lookup"><span data-stu-id="980c1-146">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="980c1-147">Sie können auch Skalieren bis super hochwertige weiter, wenn genügend Bandbreite vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="980c1-147">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="980c1-148">Wenn eine Anforderung Teams eine Bedingung geringer Bandbreite stößt, können Teams schnell Auslastung der Bandbreite Anpassung an die verfügbare Bandbreite textlichen.</span><span class="sxs-lookup"><span data-stu-id="980c1-148">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="980c1-149">Zusätzliche Netzwerküberlegungen</span><span class="sxs-lookup"><span data-stu-id="980c1-149">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="980c1-150">**Externe Namensauflösung**</span><span class="sxs-lookup"><span data-stu-id="980c1-150">**External Name Resolution**</span></span>

<span data-ttu-id="980c1-151">Stellen Sie sicher, dass alle Clientcomputer, auf denen Microsoft Teams ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Office 365 bereitgestellten Dienste zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="980c1-151">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="980c1-152">**NAT-Poolgröße**</span><span class="sxs-lookup"><span data-stu-id="980c1-152">**NAT Pool Size**</span></span>

<span data-ttu-id="980c1-153">Wenn mehrere Benutzer/Geräte mit NAT (Network Address Translation, Netzwerkadressenübersetzung) oder PAT (Port Address Translation, Portadressenübersetzung) auf Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter den einzelnen öffentlich routingfähigen IP-Adressen verborgenen Geräte nicht die unterstützte Anzahl überschreiten.</span><span class="sxs-lookup"><span data-stu-id="980c1-153">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="980c1-154">Verringern Sie dieses Risiko, indem Sie sicherstellen, dass den NAT-Pools entsprechend viele öffentliche IP-Adressen zugewiesen sind, um Portauslastung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="980c1-154">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="980c1-155">Portauslastung führt dazu, dass für interne Endbenutzer und Geräte Probleme beim Herstellen der Verbindung mit den Office 365-Diensten auftreten.</span><span class="sxs-lookup"><span data-stu-id="980c1-155">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="980c1-156">Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="980c1-156">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="980c1-157">**Leitfaden zur Angriffserkennung und zum Eindringschutz**</span><span class="sxs-lookup"><span data-stu-id="980c1-157">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="980c1-158">Wenn in Ihrer Umgebung ein Angriffserkennungs- und/oder Eindringschutzsystem (Intrusion Detection System/Prevention System, IDS/IPS) als zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt ist, stellen Sie sicher, dass Datenverkehr, dessen Ziel Office 365-URLs sind, in der Whitelist enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="980c1-158">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="980c1-159">Ermittlung der Netzwerkintegrität</span><span class="sxs-lookup"><span data-stu-id="980c1-159">Network health determination</span></span>
-----------------

<span data-ttu-id="980c1-160">Beim Planen der Implementierung von Microsoft Teams in Ihrem Netzwerk müssen Sie sicherstellen, dass die erforderliche Bandbreite sowie Zugriff auf alle erforderlichen IP-Adressen verfügbar ist, dass die richtigen Ports geöffnet sind und dass die Leistungsanforderungen für Echtzeitmedien erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="980c1-160">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="980c1-161">Wenn Sie wissen, dass Sie diese Kriterien nicht erfüllen, können Ihre Endbenutzer Microsoft Teams aufgrund der schlechten Qualität bei Anrufen und Besprechungen nicht optimal nutzen.</span><span class="sxs-lookup"><span data-stu-id="980c1-161">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="980c1-162">Falls diese Kriterien nicht erfüllt sind, sollten Sie in Betracht ziehen, das Projekt zu pausieren, um die Erfüllung der Kriterien sicherzustellen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="980c1-162">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="980c1-164">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="980c1-164">Decision Point</span></span>         |<span data-ttu-id="980c1-165">Haben Sie die Möglichkeiten für die Unterstützung von Echtzeitmedien in Ihrem Netzwerk bewertet?</span><span class="sxs-lookup"><span data-stu-id="980c1-165">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="980c1-166">Werden Sie, wenn das Netzwerk nicht ordnungsgemäß bewertet wurde oder Sie wissen, dass Echtzeitmedien nicht unterstützt werden, Video- und Bildschirmübertragungsfunktionen deaktivieren, um die Auswirkungen auf das Netzwerk und Beeinträchtigungen der Verwendung von Teams zu verringern?</span><span class="sxs-lookup"><span data-stu-id="980c1-166">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="980c1-168">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="980c1-168">Next Steps</span></span>         |<span data-ttu-id="980c1-169">Netzwerkqualität unbekannt: Ermitteln Sie anhand des Leitfadens zur [Bewertung der Netzwerkbereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness), ob Ihr Netzwerk für Echtzeitmedien bereit ist.</span><span class="sxs-lookup"><span data-stu-id="980c1-169">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="980c1-170">Netzwerkqualität schlecht: Führen Sie die Netzwerkwiederherstellungsschritte aus, um eine geeignete Umgebung für Echtzeitmedien von hoher Qualität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="980c1-170">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="980c1-171">Netzwerk zufriedenstellend: Stellen Sie sicher, dass der Zugriff auf alle IP-Adressen und Ports ordnungsgemäß möglich ist.</span><span class="sxs-lookup"><span data-stu-id="980c1-171">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="980c1-172">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="980c1-172">Related Topics</span></span>

[<span data-ttu-id="980c1-173">Video: Netzwerkplanung</span><span class="sxs-lookup"><span data-stu-id="980c1-173">Video: Network Planning</span></span>](https://aka.ms/teams-networking)