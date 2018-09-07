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
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a65f12399c18708b54404cb5df60bc5e24190f6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855361"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="48932-104">Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48932-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="48932-105">Microsoft Teams kombiniert drei Arten von Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="48932-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="48932-106">Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)</span><span class="sxs-lookup"><span data-stu-id="48932-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="48932-107">Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="48932-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="48932-108">Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="48932-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="48932-p102">Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.</span><span class="sxs-lookup"><span data-stu-id="48932-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48932-112">Zurzeit werden Besprechungen auf mobilen Geräten unter iOS und Android unterstützt, aber nicht unter Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="48932-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone.</span></span>

<span data-ttu-id="48932-113">Für die optimale Verwendung von Echtzeitmedien in Microsoft Teams müssen die Netzwerkanforderungen für Office 365 erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="48932-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="48932-114">Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="48932-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="48932-115">Sollten Sie für die zwei definierenden Netzwerksegmente (Client Microsoft Edge) und Customer Kante Microsoft Edge die folgenden Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="48932-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="48932-116">Wert</span><span class="sxs-lookup"><span data-stu-id="48932-116">Value</span></span>  |<span data-ttu-id="48932-117">Client zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="48932-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="48932-118">Kundenedge zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="48932-118">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="48932-119">**Latenz (ein Weg)**</span><span class="sxs-lookup"><span data-stu-id="48932-119">**Latency (one way)**</span></span>     |<span data-ttu-id="48932-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="48932-120">< 50ms</span></span>          |<span data-ttu-id="48932-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="48932-121">< 30ms</span></span>          |
|<span data-ttu-id="48932-122">**Latenz (RTT oder Roundtripzeit)**</span><span class="sxs-lookup"><span data-stu-id="48932-122">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="48932-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="48932-123">< 100ms</span></span>         |<span data-ttu-id="48932-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="48932-124">< 60ms</span></span>         |
|<span data-ttu-id="48932-125">**Burstverlust von Paketen**</span><span class="sxs-lookup"><span data-stu-id="48932-125">**Burst packet loss**</span></span>    |<span data-ttu-id="48932-126">< 10 % in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="48932-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="48932-127">< 1% in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="48932-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="48932-128">**Paketverlust**</span><span class="sxs-lookup"><span data-stu-id="48932-128">**Packet loss**</span></span>     |<span data-ttu-id="48932-129">< 1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="48932-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="48932-130">< 0,1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="48932-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="48932-131">**Jitter zwischen der Ankunftszeit von Paketen**</span><span class="sxs-lookup"><span data-stu-id="48932-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="48932-132">< 30 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="48932-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="48932-133">< 15 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="48932-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="48932-134">**Neuanordnung von Paketen**</span><span class="sxs-lookup"><span data-stu-id="48932-134">**Packet reorder**</span></span>    |<span data-ttu-id="48932-135">< 0,05 % Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="48932-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="48932-136">< 0,01% Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="48932-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="48932-137">Um beide Netzwerksegmente zu testen, können Sie das [Network Assessment-Tool](https://go.microsoft.com/fwlink/?linkid=855799) verwenden.</span><span class="sxs-lookup"><span data-stu-id="48932-137">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="48932-138">Dieses Tool kann direkt auf dem Client-PC sowie auf einem PC, der mit dem Netzwerkedge des Kunden verbunden ist, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="48932-138">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="48932-139">Das Tool selbst enthält eine begrenzte Dokumentation, eine umfassendere Dokumentation zur Verwendung des Tools finden Sie hier: [Bewertung der Netzwerkbereitschaft](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="48932-139">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="48932-140">Indem Sie diese Bewertung der Netzwerkbereitschaft ausführen, können Sie die Bereitschaft Ihres Netzwerks für die Ausführung von Echtzeitmedienanwendungen wie beispielsweise Microsoft Teams validieren.</span><span class="sxs-lookup"><span data-stu-id="48932-140">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="48932-141">Dabei handelt es sich um die gleiche Bewertung der Netzwerkbereitschaft, deren Ausführung Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="48932-141">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="48932-142">Bandbreitenanforderungen</span><span class="sxs-lookup"><span data-stu-id="48932-142">Bandwidth requirements</span></span>
----------

<span data-ttu-id="48932-143">Bandbreitenberechnungen für Microsoft Teams sind komplex. Zu Ihrer Unterstützung wurde ein Rechner erstellt.</span><span class="sxs-lookup"><span data-stu-id="48932-143">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="48932-144">Den Rechner finden Sie unter [„Netzwerkplaner“ in MyAdvisor](https://aka.ms/bwcalc/).</span><span class="sxs-lookup"><span data-stu-id="48932-144">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="48932-145">Zusätzliche Netzwerküberlegungen</span><span class="sxs-lookup"><span data-stu-id="48932-145">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="48932-146">**Externe Namensauflösung**</span><span class="sxs-lookup"><span data-stu-id="48932-146">**External Name Resolution**</span></span>

<span data-ttu-id="48932-147">Stellen Sie sicher, dass alle Clientcomputer, auf denen Microsoft Teams ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Office 365 bereitgestellten Dienste zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="48932-147">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="48932-148">**NAT-Poolgröße**</span><span class="sxs-lookup"><span data-stu-id="48932-148">**NAT Pool Size**</span></span>

<span data-ttu-id="48932-149">Wenn mehrere Benutzer/Geräte mit NAT (Network Address Translation, Netzwerkadressenübersetzung) oder PAT (Port Address Translation, Portadressenübersetzung) auf Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter den einzelnen öffentlich routingfähigen IP-Adressen verborgenen Geräte nicht die unterstützte Anzahl überschreiten.</span><span class="sxs-lookup"><span data-stu-id="48932-149">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="48932-150">Verringern Sie dieses Risiko, indem Sie sicherstellen, dass den NAT-Pools entsprechend viele öffentliche IP-Adressen zugewiesen sind, um Portauslastung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="48932-150">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="48932-151">Portauslastung führt dazu, dass für interne Endbenutzer und Geräte Probleme beim Herstellen der Verbindung mit den Office 365-Diensten auftreten.</span><span class="sxs-lookup"><span data-stu-id="48932-151">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="48932-152">Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="48932-152">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="48932-153">**Leitfaden zur Angriffserkennung und zum Eindringschutz**</span><span class="sxs-lookup"><span data-stu-id="48932-153">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="48932-154">Wenn in Ihrer Umgebung ein Angriffserkennungs- und/oder Eindringschutzsystem (Intrusion Detection System/Prevention System, IDS/IPS) als zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt ist, stellen Sie sicher, dass Datenverkehr, dessen Ziel Office 365-URLs sind, in der Whitelist enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="48932-154">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="48932-155">Ermittlung der Netzwerkintegrität</span><span class="sxs-lookup"><span data-stu-id="48932-155">Network health determination</span></span>
-----------------

<span data-ttu-id="48932-156">Beim Planen der Implementierung von Microsoft Teams in Ihrem Netzwerk müssen Sie sicherstellen, dass die erforderliche Bandbreite sowie Zugriff auf alle erforderlichen IP-Adressen verfügbar ist, dass die richtigen Ports geöffnet sind und dass die Leistungsanforderungen für Echtzeitmedien erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="48932-156">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="48932-157">Wenn Sie wissen, dass Sie diese Kriterien nicht erfüllen, können Ihre Endbenutzer Microsoft Teams aufgrund der schlechten Qualität bei Anrufen und Besprechungen nicht optimal nutzen.</span><span class="sxs-lookup"><span data-stu-id="48932-157">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="48932-158">Falls diese Kriterien nicht erfüllt sind, sollten Sie in Betracht ziehen, das Projekt zu pausieren, um die Erfüllung der Kriterien sicherzustellen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="48932-158">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="48932-160">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="48932-160">Decision Point</span></span>         |<span data-ttu-id="48932-161">Haben Sie die Möglichkeiten für die Unterstützung von Echtzeitmedien in Ihrem Netzwerk bewertet?</span><span class="sxs-lookup"><span data-stu-id="48932-161">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="48932-162">Werden Sie, wenn das Netzwerk nicht ordnungsgemäß bewertet wurde oder Sie wissen, dass Echtzeitmedien nicht unterstützt werden, Video- und Bildschirmübertragungsfunktionen deaktivieren, um die Auswirkungen auf das Netzwerk und Beeinträchtigungen der Verwendung von Teams zu verringern?</span><span class="sxs-lookup"><span data-stu-id="48932-162">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="48932-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="48932-164">Next Steps</span></span>         |<span data-ttu-id="48932-165">Netzwerkqualität unbekannt: Ermitteln Sie anhand des Leitfadens zur [Bewertung der Netzwerkbereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness), ob Ihr Netzwerk für Echtzeitmedien bereit ist.</span><span class="sxs-lookup"><span data-stu-id="48932-165">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="48932-166">Netzwerkqualität schlecht: Führen Sie die Netzwerkwiederherstellungsschritte aus, um eine geeignete Umgebung für Echtzeitmedien von hoher Qualität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="48932-166">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="48932-167">Netzwerk zufriedenstellend: Stellen Sie sicher, dass der Zugriff auf alle IP-Adressen und Ports ordnungsgemäß möglich ist.</span><span class="sxs-lookup"><span data-stu-id="48932-167">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

