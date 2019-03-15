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
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640730"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="f9ad5-104">Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9ad5-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="f9ad5-105">Sehen Sie sich die folgenden Sitzung erfahren, wie Sie Teams nutzt Ihr Netzwerk und am besten für die optimale Netzwerkkonnektivität planen: [Teams Netzwerkplanung](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="f9ad5-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="f9ad5-106">Teams sind drei Arten von Datenverkehr kombiniert:</span><span class="sxs-lookup"><span data-stu-id="f9ad5-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="f9ad5-107">Datenverkehr zwischen online Office 365-Umgebung und dem Client Teams (Signale, Anwesenheit, Chat, Dateien hochladen und herunterladen, OneNote-Synchronisierung).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="f9ad5-108">Real-Time Communications Peer-zu-Peer-Datenverkehr (audio, video, desktop freigeben).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="f9ad5-109">Echtzeitkommunikation konferenzdatenverkehr (audio, video, desktop freigeben).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="f9ad5-110">Dies wirkt sich auf das Netzwerk auf zwei Ebenen: Datenverkehr fließt zwischen den Clients Microsoft-Teams, direkt für Peer-zu-Peer-Szenarien und Datenverkehr fließt zwischen Office 365-Umgebung und den Clients Microsoft-Teams zur Erfüllung Szenarien.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="f9ad5-111">Um eine optimale mediendatenfluss zu gewährleisten, Datenverkehr muss dürfen beide zwischen dem internen Netzwerksegmente (beispielsweise zwischen Standorten über das WAN) wie sowie zwischen flow der Netzwerkstandorte und Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="f9ad5-112">Nicht die richtigen Ports öffnen oder aktiv bestimmte Ports Sperren führt zu einer beeinträchtigter wünschen.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="f9ad5-113">Besprechungen werden auf iOS und Android mobilen Geräten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="f9ad5-114">Wenn Sie eine optimale wünschen mit Echtzeit-Medien in Microsoft-Teams erhalten möchten, muss Ihr Netzwerk Netzwerken Anforderungen für Office 365 erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-114">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="f9ad5-115">Weitere Informationen finden Sie unter [Medienqualität und Leistung des Netzwerks Konnektivität für Skype für Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="f9ad5-116">Sollten Sie für die zwei definierenden Netzwerksegmente (Client Microsoft Edge) und Customer Kante Microsoft Edge die folgenden Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="f9ad5-117">Wert</span><span class="sxs-lookup"><span data-stu-id="f9ad5-117">Value</span></span>  |<span data-ttu-id="f9ad5-118">Client für Microsoft-Edge</span><span class="sxs-lookup"><span data-stu-id="f9ad5-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="f9ad5-119">Customer Edge zum Microsoft Rand</span><span class="sxs-lookup"><span data-stu-id="f9ad5-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="f9ad5-120">**Wartezeit (unidirektional)**\*</span><span class="sxs-lookup"><span data-stu-id="f9ad5-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="f9ad5-121">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="f9ad5-121">< 50ms</span></span>          |<span data-ttu-id="f9ad5-122">< 30ms</span><span class="sxs-lookup"><span data-stu-id="f9ad5-122">< 30ms</span></span>         |
|<span data-ttu-id="f9ad5-123">**Wartezeit (Zeit oder Roundtripzeit)**\*</span><span class="sxs-lookup"><span data-stu-id="f9ad5-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="f9ad5-124">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="f9ad5-124">< 100ms</span></span>   |<span data-ttu-id="f9ad5-125">< 60ms</span><span class="sxs-lookup"><span data-stu-id="f9ad5-125">< 60ms</span></span> |
|<span data-ttu-id="f9ad5-126">**Bursts von Paketverlusten**</span><span class="sxs-lookup"><span data-stu-id="f9ad5-126">**Burst packet loss**</span></span>    |<span data-ttu-id="f9ad5-127"><10 % Intervall 200 ms</span><span class="sxs-lookup"><span data-stu-id="f9ad5-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="f9ad5-128"><1 % Intervall 200 ms</span><span class="sxs-lookup"><span data-stu-id="f9ad5-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="f9ad5-129">**Paketverlust**</span><span class="sxs-lookup"><span data-stu-id="f9ad5-129">**Packet loss**</span></span>     |<span data-ttu-id="f9ad5-130"><1 % während alle 15 s Intervall</span><span class="sxs-lookup"><span data-stu-id="f9ad5-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="f9ad5-131"><0.1% während alle 15 s Intervall</span><span class="sxs-lookup"><span data-stu-id="f9ad5-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="f9ad5-132">**Die Kommunikation zwischen hinzukommen Jitter Paket**</span><span class="sxs-lookup"><span data-stu-id="f9ad5-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="f9ad5-133"><30ms während alle 15 s Intervall</span><span class="sxs-lookup"><span data-stu-id="f9ad5-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="f9ad5-134"><15ms während alle 15 s Intervall</span><span class="sxs-lookup"><span data-stu-id="f9ad5-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="f9ad5-135">**Paket neu anordnen**</span><span class="sxs-lookup"><span data-stu-id="f9ad5-135">**Packet reorder**</span></span>    |<span data-ttu-id="f9ad5-136"><0.05% außerhalb der Reihenfolge Pakete</span><span class="sxs-lookup"><span data-stu-id="f9ad5-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="f9ad5-137"><0.01% außerhalb der Reihenfolge Pakete</span><span class="sxs-lookup"><span data-stu-id="f9ad5-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="f9ad5-138">\*Die Wartezeit metrischen Ziele gehen davon aus Ihrer Firma Website oder Websites und die Microsoft Kanten auf dem gleichen Kontinent.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="f9ad5-139">Die Unternehmen Website-Verbindung mit der Microsoft-Netzwerkgrenze enthält ersten Hop Netzwerkzugriff, WiFi oder einer anderen drahtlosen Technologie werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="f9ad5-140">Die Netzwerk-Leistungsziele wird vorausgesetzt, ordnungsgemäße Bandbreite und/oder [QoS planen](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="f9ad5-141">Mit anderen Worten, gelten die Anforderungen direkt in Echtzeit Mediendatenverkehr Teams, wenn eine spitzenauslastung die Netzwerkschnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="f9ad5-142">Um beide Netzwerksegmente zu testen, können Sie das [Tool zur Bewertung der Netzwerk](https://go.microsoft.com/fwlink/?linkid=855799)verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="f9ad5-143">Dieses Tool kann auf dem Client PC direkt und auf einem PC verbunden mit dem Kunden Netzwerkgrenze bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="f9ad5-144">Das Tool umfasst begrenzte Dokumentation, aber eine tiefere Dokumentation entsprechend der Verwendung des Tools finden Sie hier: [Bereitschaft des Netzwerks](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="f9ad5-145">Diese Bereitschaft Netzwerk ausführen, können Sie Netzwerks auszuführenden Real-Time Media-Anwendungen wie Microsoft-Teams überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f9ad5-146">Dies ist die gleiche Netzwerk Bereitschaft, die für Kunden ausgeführt werden soll, die erfolgreiche Bereitstellung von Skype für Unternehmen suchen empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="f9ad5-147">Erforderliche Bandbreite</span><span class="sxs-lookup"><span data-stu-id="f9ad5-147">Bandwidth requirements</span></span>

<span data-ttu-id="f9ad5-148">Bandbreite Berechnungen für Microsoft-Teams sind komplex und dabei zu unterstützen, um ein Rechner erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="f9ad5-149">Um den Rechner zuzugreifen, wechseln Sie zur [Netzwerk Planner](https://aka.ms/bwcalc/) in MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="f9ad5-150">Behandlung von Teams Bandbreite wurden verbessert Skype für Business Online: für eine hohe Qualität aufrufen oder meeting-Erfahrung (mit Audio, Video und Freigabe), Teams nur 1,2 Mbit/s benötigt.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="f9ad5-151">Sie können auch Skalieren bis super hochwertige weiter, wenn genügend Bandbreite vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="f9ad5-152">Wenn eine Anforderung Teams eine Bedingung geringer Bandbreite stößt, können Teams schnell Auslastung der Bandbreite Anpassung an die verfügbare Bandbreite textlichen.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="f9ad5-153">Zusätzliche Netzwerkaspekte</span><span class="sxs-lookup"><span data-stu-id="f9ad5-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="f9ad5-154">Externe namensauflösung</span><span class="sxs-lookup"><span data-stu-id="f9ad5-154">External Name Resolution</span></span>

<span data-ttu-id="f9ad5-155">Stellen Sie sicher, dass alle Clientcomputer unter Teams Client externe DNS-Abfragen zum Ermitteln der Dienste von Office 365 beheben können und Ihrer Firewalls Access nicht verhindern.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="f9ad5-156">Informationen zum Konfigurieren von Firewallports wechseln Sie zu [Office 365-URLs und IP-Adressbereichen](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="f9ad5-157">NAT-Pool-Größe</span><span class="sxs-lookup"><span data-stu-id="f9ad5-157">NAT Pool Size</span></span>

<span data-ttu-id="f9ad5-158">Bei Office 365 (Network Address Translation, NAT) oder Port Address Translation (PAT) mit Zugriff auf mehrere Benutzer/Geräte müssen Sie sicherstellen, dass die Geräte hinter jeder öffentlich routingfähige IP-Adresse ausgeblendet unterstützte Anzahl nicht überschritten werden.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="f9ad5-159">Um dieses Risiko zu verringern, stellen Sie sicher, über ausreichend öffentliche IP-Adressen in der NAT-Pools zu verhindern, dass Port Erschöpfung zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="f9ad5-160">Port Erschöpfung bewirkt, dass interne Endbenutzer und Geräten, um Probleme mit der Vorderseite nach beim Verbinden mit Office 365-Dienste.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="f9ad5-161">Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="f9ad5-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="f9ad5-162">**Erkennung und Prevention Anleitungen**</span><span class="sxs-lookup"><span data-stu-id="f9ad5-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="f9ad5-163">Wenn Ihre Umgebung eine Erkennung und/oder Prevention-System (IDS/IPS) für eine zusätzliche Sicherheitsebene für ausgehende Verbindungen bereitgestellt hat, sicher, dass jeder Datenverkehr mit Ziel zu Office 365-URLs White.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="f9ad5-164">Bestimmung der Netzwerk-Integrität</span><span class="sxs-lookup"><span data-stu-id="f9ad5-164">Network health determination</span></span>
-----------------

<span data-ttu-id="f9ad5-165">Bei der Planung der Implementierung des Microsoft-Teams innerhalb des Netzwerks, müssen Sie darauf achten Sie über die erforderliche Bandbreite verfügen, haben Sie Zugriff auf alle erforderlichen IP-Adressen, die richtigen Ports geöffnet, und Sie sind die leistungsanforderungen für Real-Time Media meeting .</span><span class="sxs-lookup"><span data-stu-id="f9ad5-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="f9ad5-166">Wenn Sie, dass Sie diese Kriterien nicht erfüllt werden wissen, erhalten die Endbenutzer nicht optimal arbeiten von Teams aufgrund ungültiger Qualität während der Anrufe und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="f9ad5-167">Sie diesen Kriterien nicht entsprechen soll, ist dies die Zeit, zu berücksichtigen sind Anhalten des Projekts, um sicherzustellen, dass Sie die Kriterien erfüllen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="f9ad5-169">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="f9ad5-169">Decision Point</span></span>         |<span data-ttu-id="f9ad5-170">Haben Sie Ihr Netzwerkfunktionen zur Unterstützung von Real Time Media ausgewertet?</span><span class="sxs-lookup"><span data-stu-id="f9ad5-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="f9ad5-171">Wenn Ihr Netzwerk nicht ordnungsgemäß bewertet oder wissen Sie, dass Real Time Media nicht unterstützt wird, werden Sie Video- und Freigabefunktionen Reduzierung der Netzwerklast und schlechte Erfahrungen von Teams Bildschirm deaktivieren?</span><span class="sxs-lookup"><span data-stu-id="f9ad5-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="f9ad5-173">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f9ad5-173">Next Steps</span></span>         |<span data-ttu-id="f9ad5-174">Netzwerk-Qualität unbekannt: befolgen Sie die [Bereitschaft des Netzwerks](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) -Anweisungen, um festzustellen, ob Ihr Netzwerk für Real Time Media bereit ist.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="f9ad5-175">Anrufe schlechter Qualität der Netzwerk: Führen Sie Netzwerk Remediation Schritte aus, um eine ordnungsgemäße Umgebung für hohe Qualität Real Time Media bieten.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="f9ad5-176">Netzwerk befriedigend: Sicher, dass alle IP-Adressen und Ports sind ordnungsgemäß zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f9ad5-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="f9ad5-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f9ad5-177">Related Topics</span></span>

[<span data-ttu-id="f9ad5-178">Video: Netzwerkplanung</span><span class="sxs-lookup"><span data-stu-id="f9ad5-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)