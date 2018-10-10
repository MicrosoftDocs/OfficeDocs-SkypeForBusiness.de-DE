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
ms.openlocfilehash: 919c598b02724de2f21fce52cb5f362c8faea34b
ms.sourcegitcommit: dba62f1cb6058e73a1a4c75f3473119a04a1b9e3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2018
ms.locfileid: "25456867"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="1e373-104">Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e373-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="1e373-105">Microsoft Teams kombiniert drei Arten von Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="1e373-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="1e373-106">Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)</span><span class="sxs-lookup"><span data-stu-id="1e373-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="1e373-107">Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="1e373-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="1e373-108">Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)</span><span class="sxs-lookup"><span data-stu-id="1e373-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="1e373-p102">Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.</span><span class="sxs-lookup"><span data-stu-id="1e373-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e373-112">Zurzeit werden Besprechungen auf mobilen Geräten unter iOS und Android unterstützt, aber nicht unter Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="1e373-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone.</span></span>

<span data-ttu-id="1e373-113">Für die optimale Verwendung von Echtzeitmedien in Microsoft Teams müssen die Netzwerkanforderungen für Office 365 erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="1e373-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="1e373-114">Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="1e373-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="1e373-115">Für die beiden definierenden Netzwerksegmente (Client zum Edge von Microsoft und Kundenedge zum Edge von Microsoft) gelten die folgenden Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="1e373-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="1e373-116">Wert</span><span class="sxs-lookup"><span data-stu-id="1e373-116">Value</span></span>  |<span data-ttu-id="1e373-117">Client zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1e373-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="1e373-118">Kundenedge zu Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1e373-118">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="1e373-119">**Latenz (ein Weg)**</span><span class="sxs-lookup"><span data-stu-id="1e373-119">**Latency (one way)**</span></span>     |<span data-ttu-id="1e373-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="1e373-120">< 50ms</span></span>          |<span data-ttu-id="1e373-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="1e373-121">< 30ms</span></span>          |
|<span data-ttu-id="1e373-122">**Latenz (RTT oder Roundtripzeit)**</span><span class="sxs-lookup"><span data-stu-id="1e373-122">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="1e373-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="1e373-123">< 100ms</span></span>         |<span data-ttu-id="1e373-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="1e373-124">< 60ms</span></span>         |
|<span data-ttu-id="1e373-125">**Burstverlust von Paketen**</span><span class="sxs-lookup"><span data-stu-id="1e373-125">**Burst packet loss**</span></span>    |<span data-ttu-id="1e373-126">< 10 % in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="1e373-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="1e373-127">< 1% in einem Intervall von 200 ms</span><span class="sxs-lookup"><span data-stu-id="1e373-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="1e373-128">**Paketverlust**</span><span class="sxs-lookup"><span data-stu-id="1e373-128">**Packet loss**</span></span>     |<span data-ttu-id="1e373-129">< 1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="1e373-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="1e373-130">< 0,1% in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="1e373-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="1e373-131">**Jitter zwischen der Ankunftszeit von Paketen**</span><span class="sxs-lookup"><span data-stu-id="1e373-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="1e373-132">< 30 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="1e373-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="1e373-133">< 15 ms in einem Intervall von 15 s</span><span class="sxs-lookup"><span data-stu-id="1e373-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="1e373-134">**Neuanordnung von Paketen**</span><span class="sxs-lookup"><span data-stu-id="1e373-134">**Packet reorder**</span></span>    |<span data-ttu-id="1e373-135">< 0,05 % Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="1e373-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="1e373-136">< 0,01% Pakete in falscher Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="1e373-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="1e373-137">Um beide Netzwerksegmente zu testen, können Sie das [Network Assessment-Tool](https://go.microsoft.com/fwlink/?linkid=855799) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e373-137">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="1e373-138">Dieses Tool kann direkt auf dem Client-PC sowie auf einem PC, der mit dem Netzwerkedge des Kunden verbunden ist, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1e373-138">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="1e373-139">Das Tool selbst enthält eine begrenzte Dokumentation, eine umfassendere Dokumentation zur Verwendung des Tools finden Sie hier: [Bewertung der Netzwerkbereitschaft](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="1e373-139">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="1e373-140">Indem Sie diese Bewertung der Netzwerkbereitschaft ausführen, können Sie die Bereitschaft Ihres Netzwerks für die Ausführung von Echtzeitmedienanwendungen wie beispielsweise Microsoft Teams validieren.</span><span class="sxs-lookup"><span data-stu-id="1e373-140">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="1e373-141">Dabei handelt es sich um die gleiche Bewertung der Netzwerkbereitschaft, deren Ausführung Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1e373-141">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="1e373-142">Bandbreitenanforderungen</span><span class="sxs-lookup"><span data-stu-id="1e373-142">Bandwidth requirements</span></span>
----------

<span data-ttu-id="1e373-143">Bandbreitenberechnungen für Microsoft Teams sind komplex. Zu Ihrer Unterstützung wurde ein Rechner erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e373-143">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="1e373-144">Den Rechner finden Sie unter [„Network Planner“ in MyAdvisor](https://aka.ms/bwcalc/).</span><span class="sxs-lookup"><span data-stu-id="1e373-144">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

> [!NOTE]
> <span data-ttu-id="1e373-145">Behandlung von Teams Bandbreite wurden verbessert Skype für Business Online: für eine hohe Qualität aufrufen oder meeting-Erfahrung (mit Audio, Video und Freigabe), Teams nur 1,2 Mbit/s benötigt.</span><span class="sxs-lookup"><span data-stu-id="1e373-145">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="1e373-146">Sie können auch Skalieren bis super hochwertige weiter, wenn genügend Bandbreite vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1e373-146">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="1e373-147">Wenn eine Anforderung Teams eine Bedingung geringer Bandbreite stößt, können Teams schnell Auslastung der Bandbreite Anpassung an die verfügbare Bandbreite textlichen.</span><span class="sxs-lookup"><span data-stu-id="1e373-147">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="1e373-148">Zusätzliche Netzwerküberlegungen</span><span class="sxs-lookup"><span data-stu-id="1e373-148">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="1e373-149">**Externe Namensauflösung**</span><span class="sxs-lookup"><span data-stu-id="1e373-149">**External Name Resolution**</span></span>

<span data-ttu-id="1e373-150">Stellen Sie sicher, dass alle Clientcomputer, auf denen Microsoft Teams ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Office 365 bereitgestellten Dienste zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1e373-150">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="1e373-151">**NAT-Poolgröße**</span><span class="sxs-lookup"><span data-stu-id="1e373-151">**NAT Pool Size**</span></span>

<span data-ttu-id="1e373-152">Wenn mehrere Benutzer/Geräte mit NAT (Network Address Translation, Netzwerkadressenübersetzung) oder PAT (Port Address Translation, Portadressenübersetzung) auf Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter den einzelnen öffentlich routingfähigen IP-Adressen verborgenen Geräte nicht die unterstützte Anzahl überschreiten.</span><span class="sxs-lookup"><span data-stu-id="1e373-152">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="1e373-153">Verringern Sie dieses Risiko, indem Sie sicherstellen, dass den NAT-Pools entsprechend viele öffentliche IP-Adressen zugewiesen sind, um Portauslastung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1e373-153">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="1e373-154">Portauslastung führt dazu, dass für interne Endbenutzer und Geräte Probleme beim Herstellen der Verbindung mit den Office 365-Diensten auftreten.</span><span class="sxs-lookup"><span data-stu-id="1e373-154">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="1e373-155">Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="1e373-155">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="1e373-156">**Leitfaden zur Angriffserkennung und zum Eindringschutz**</span><span class="sxs-lookup"><span data-stu-id="1e373-156">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="1e373-157">Wenn in Ihrer Umgebung ein Angriffserkennungs- und/oder Eindringschutzsystem (Intrusion Detection System/Prevention System, IDS/IPS) als zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt ist, stellen Sie sicher, dass Datenverkehr, dessen Ziel Office 365-URLs sind, in der Whitelist enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1e373-157">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="1e373-158">Ermittlung der Netzwerkintegrität</span><span class="sxs-lookup"><span data-stu-id="1e373-158">Network health determination</span></span>
-----------------

<span data-ttu-id="1e373-159">Beim Planen der Implementierung von Microsoft Teams in Ihrem Netzwerk müssen Sie sicherstellen, dass die erforderliche Bandbreite sowie Zugriff auf alle erforderlichen IP-Adressen verfügbar ist, dass die richtigen Ports geöffnet sind und dass die Leistungsanforderungen für Echtzeitmedien erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="1e373-159">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="1e373-160">Wenn Sie wissen, dass Sie diese Kriterien nicht erfüllen, können Ihre Endbenutzer Microsoft Teams aufgrund der schlechten Qualität bei Anrufen und Besprechungen nicht optimal nutzen.</span><span class="sxs-lookup"><span data-stu-id="1e373-160">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="1e373-161">Falls diese Kriterien nicht erfüllt sind, sollten Sie in Betracht ziehen, das Projekt zu pausieren, um die Erfüllung der Kriterien sicherzustellen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1e373-161">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="1e373-163">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="1e373-163">Decision Point</span></span>         |<span data-ttu-id="1e373-164">Haben Sie die Möglichkeiten für die Unterstützung von Echtzeitmedien in Ihrem Netzwerk bewertet?</span><span class="sxs-lookup"><span data-stu-id="1e373-164">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="1e373-165">Werden Sie, wenn das Netzwerk nicht ordnungsgemäß bewertet wurde oder Sie wissen, dass Echtzeitmedien nicht unterstützt werden, Video- und Bildschirmübertragungsfunktionen deaktivieren, um die Auswirkungen auf das Netzwerk und Beeinträchtigungen der Verwendung von Teams zu verringern?</span><span class="sxs-lookup"><span data-stu-id="1e373-165">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="1e373-167">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1e373-167">Next Steps</span></span>         |<span data-ttu-id="1e373-168">Netzwerkqualität unbekannt: Ermitteln Sie anhand des Leitfadens zur [Bewertung der Netzwerkbereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness), ob Ihr Netzwerk für Echtzeitmedien bereit ist.</span><span class="sxs-lookup"><span data-stu-id="1e373-168">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="1e373-169">Netzwerkqualität schlecht: Führen Sie die Netzwerkwiederherstellungsschritte aus, um eine geeignete Umgebung für Echtzeitmedien von hoher Qualität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1e373-169">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="1e373-170">Netzwerk zufriedenstellend: Stellen Sie sicher, dass der Zugriff auf alle IP-Adressen und Ports ordnungsgemäß möglich ist.</span><span class="sxs-lookup"><span data-stu-id="1e373-170">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

