---
title: 'Lync Server 2013: Übersicht über die Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ad2be78d3e2af4c5b016b02e152ba0430d2a1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="9795f-102">Übersicht über die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9795f-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9795f-103">_**Letztes Änderungsstand des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="9795f-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="9795f-104">Die Echtzeitkommunikation ist anfällig für Latenzprobleme und Paketverluste, wie sie bei überlasteten Netzwerken auftreten können.</span><span class="sxs-lookup"><span data-stu-id="9795f-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="9795f-105">Der Anrufsteuerungsdienst ermittelt anhand der verfügbaren Netzwerkbandbreite, ob Kommunikationssitzungen (beispielsweise Sprach- oder Videoanrufe) in Echtzeit eingerichtet werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="9795f-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="9795f-106">Das CAC-Design in lync Server 2013 bietet vier Hauptattribute:</span><span class="sxs-lookup"><span data-stu-id="9795f-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="9795f-107">Die Bereitstellung und Verwaltung ist einfach, ohne dass zusätzliche Geräte erforderlich sind, wie speziell konfigurierte Router.</span><span class="sxs-lookup"><span data-stu-id="9795f-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="9795f-108">Es behandelt wichtige Unified Communications-Anwendungsfälle wie Roaming-Benutzer und mehrere Points of Presence.</span><span class="sxs-lookup"><span data-stu-id="9795f-108">It addresses critical unified communications use cases, such as roaming users and multiple points of presence.</span></span> <span data-ttu-id="9795f-109">Richtlinien für die Anrufsteuerung werden entsprechend der Position des Endpunkts und nicht des Standorts des Benutzers erzwungen.</span><span class="sxs-lookup"><span data-stu-id="9795f-109">CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="9795f-110">Zusätzlich zu Sprachanrufen kann es auf anderen Datenverkehr angewendet werden, wie Videoanrufe und Audio/Video-Konferenzsitzungen.</span><span class="sxs-lookup"><span data-stu-id="9795f-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="9795f-111">Bietet die Flexibilität, die Darstellung verschiedener Arten von Netzwerktopologien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9795f-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="9795f-112">Beispiele finden Sie unter [Components and Topologies for CAC in lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="9795f-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="9795f-113">Wenn eine neue sprach-oder Videositzung die Bandbreitengrenzwerte überschreitet, die Sie für eine WAN-Verbindung festgelegt haben, wird die Sitzung entweder blockiert oder (nur bei Anrufen) an das PSTN umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9795f-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="9795f-114">Die Anrufsteuerung steuert den echtzeitdatenverkehr nur für Sprache und Video.</span><span class="sxs-lookup"><span data-stu-id="9795f-114">CAC controls real-time traffic for voice and video only.</span></span> <span data-ttu-id="9795f-115">Der Datenverkehr wird nicht gesteuert.</span><span class="sxs-lookup"><span data-stu-id="9795f-115">It does not control data traffic.</span></span>

<span data-ttu-id="9795f-116">Administratoren definieren CAC-Richtlinien, die durch den bandbreitenrichtliniendienst erzwungen werden, der mit jeder Front-End-Pool installiert wird.</span><span class="sxs-lookup"><span data-stu-id="9795f-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="9795f-117">Die Einstellungen für die Anrufsteuerung werden automatisch an alle lync Server-Front-End-Server in Ihrem Netzwerk weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="9795f-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="9795f-118">Bei Anrufen, die aufgrund von CAC-Richtlinien fehlschlagen, lautet die Prioritätsreihenfolge für das erneute Routing des Anrufs wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9795f-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="9795f-119">Internet</span><span class="sxs-lookup"><span data-stu-id="9795f-119">Internet</span></span>

2.  <span data-ttu-id="9795f-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="9795f-120">PSTN</span></span>

3.  <span data-ttu-id="9795f-121">Voicemail</span><span class="sxs-lookup"><span data-stu-id="9795f-121">Voice mail</span></span>

<span data-ttu-id="9795f-122">Mit der Aufzeichnung von Kommunikationsdatensätzen (KDS) werden Informationen zu anrufen erfasst, die an das PSTN oder an Voicemail umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9795f-122">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail.</span></span> <span data-ttu-id="9795f-123">In KDS werden keine Informationen zu anrufen erfasst, die an das Internet umgeleitet werden, da das Internet als alternativer Pfad statt als sekundäre Option behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="9795f-123">CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9795f-124">Voicemail-Ablagerungen werden aufgrund von Bandbreiteneinschränkungen nicht verweigert.</span><span class="sxs-lookup"><span data-stu-id="9795f-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="9795f-125">Der bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (Comma Separated Values).</span><span class="sxs-lookup"><span data-stu-id="9795f-125">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format.</span></span> <span data-ttu-id="9795f-126">In der Protokolldatei **Überprüfen von Fehlern** werden Informationen erfasst, wenn Bandbreitenanforderungen verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="9795f-126">The **check failures** log file captures information when bandwidth requests are denied.</span></span> <span data-ttu-id="9795f-127">In der Protokolldatei für die **Link Nutzung** wird eine Momentaufnahme der Netzwerktopologie und der Bandbreitenauslastung der WAN-Verbindung erfasst.</span><span class="sxs-lookup"><span data-stu-id="9795f-127">The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization.</span></span> <span data-ttu-id="9795f-128">Beide Protokolldateien können Sie bei der Feinabstimmung Ihrer CAC-Richtlinien basierend auf der Auslastung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9795f-128">Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="9795f-129">Überlegungen zur Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="9795f-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="9795f-130">Der Administrator wählt den bandbreitenrichtliniendienst im ersten am zentralen Standort konfigurierten Pool aus.</span><span class="sxs-lookup"><span data-stu-id="9795f-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="9795f-131">Da es einen einzelnen zentralen Standort pro netzwerkregion gibt, gibt es nur einen bandbreitenrichtliniendienst pro netzwerkregion, der die bandbreitenrichtlinie für diese Region, die zugehörigen Standorte und die Links zu diesen Websites verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9795f-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="9795f-132">Der bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, und daher ist die hohe Verfügbarkeit in diesem Pool integriert.</span><span class="sxs-lookup"><span data-stu-id="9795f-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="9795f-133">Der bandbreitenrichtliniendienst, der auf jedem Front-End-Server ausgeführt wird, wird alle 15 Sekunden synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="9795f-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="9795f-134">Wenn die Front-End-Pool fehlschlägt, werden CAC-Richtlinien für diesen Standort erst dann erzwungen, wenn der Front-End-Pool und damit der bandbreitenrichtliniendienst wieder betriebsbereit ist.</span><span class="sxs-lookup"><span data-stu-id="9795f-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="9795f-135">Dies bedeutet, dass alle Anrufe für den Zeitraum, in dem der bandbreitenrichtliniendienst außer Betrieb ist, durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="9795f-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="9795f-136">Daher gibt es die Möglichkeit der Bandbreiten Überzeichnung Ihrer Links während dieses Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="9795f-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="9795f-137">Der bandbreitenrichtliniendienst bietet eine hohe Verfügbarkeit innerhalb eines Front-End-Pools; Es bietet jedoch keine Redundanz für Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="9795f-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="9795f-138">Der bandbreitenrichtliniendienst kann kein Failover von einem Front-End-Pool auf einen anderen durch haben.</span><span class="sxs-lookup"><span data-stu-id="9795f-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="9795f-139">Sobald der Dienst für das Front-End-Pool wiederhergestellt wurde, wird der bandbreitenrichtliniendienst fortgesetzt und kann erneut die Bandbreitenrichtlinien Überprüfung erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9795f-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="9795f-140">Überlegungen zum Netzwerk</span><span class="sxs-lookup"><span data-stu-id="9795f-140">Network Considerations</span></span>

<span data-ttu-id="9795f-141">Obwohl Bandbreiteneinschränkungen für Audio und Video durch den bandbreitenrichtliniendienst in lync Server 2013 erzwungen werden, wird diese Einschränkung nicht auf dem Netzwerkrouter erzwungen (Ebene 2 und 3).</span><span class="sxs-lookup"><span data-stu-id="9795f-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="9795f-142">Lync Server 2010-Anrufsteuerung kann nicht verhindern, dass eine Daten Anwendung beispielsweise die gesamte Netzwerkbandbreite für eine WAN-Verbindung beansprucht, einschließlich der Bandbreite, die für Audio und Video von der Anruf Steuerungsrichtlinie reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="9795f-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="9795f-143">Um die erforderliche Bandbreite in Ihrem Netzwerk zu schützen, können Sie ein QoS-Protokoll (Quality of Service) wie unterschiedliche Dienste (Diffserv) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9795f-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="9795f-144">Es empfiehlt sich daher, die von Ihnen definierten Richtlinien für die CAC-Bandbreiten mit allen QoS-Einstellungen zu koordinieren, die Sie bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="9795f-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="9795f-145">Medien-und Signalisierungs Pfade über VPN</span><span class="sxs-lookup"><span data-stu-id="9795f-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="9795f-146">Wenn Ihr Unternehmen Medien über VPN unterstützt, stellen Sie sicher, dass entweder sowohl der Mediendatenstrom als auch der Signalisierungsdaten Strom durch das VPN geleitet werden oder beide über das Internet geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="9795f-146">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet.</span></span> <span data-ttu-id="9795f-147">Standardmäßig durchlaufen die Medien-und Signalisierungsdaten Ströme den VPN-Tunnel.</span><span class="sxs-lookup"><span data-stu-id="9795f-147">By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="9795f-148">Anrufsteuerung für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="9795f-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="9795f-149">Die Anrufsteuerung wird nicht für Remotebenutzer erzwungen, bei denen der Netzwerkdatenverkehr über das Internet fließt.</span><span class="sxs-lookup"><span data-stu-id="9795f-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="9795f-150">Da der Mediendatenverkehr das Internet durchläuft, das nicht von lync Server verwaltet wird, kann die Anrufsteuerung nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9795f-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="9795f-151">Für den Teil des Anrufs, der über das Unternehmensnetzwerk fließt, werden jedoch CAC-Prüfungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="9795f-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="9795f-152">Anrufsteuerung für PSTN-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="9795f-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="9795f-153">Die Anrufsteuerung ist auf dem Vermittlungsserver vollstreckbar, unabhängig davon, ob Sie mit einer IP/PBX-Anlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9795f-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="9795f-154">Da es sich bei dem Vermittlungsserver um einen Back-to-Back-Benutzer-Agent (B2BUA) handelt, werden die Medien beendet.</span><span class="sxs-lookup"><span data-stu-id="9795f-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="9795f-155">Es hat zwei Verbindungsseiten: eine Seite, die mit lync Server und einer Gatewayseite verbunden ist, die mit PSTN-Gateways, IP/PBX-Anlagen oder SIP-Trunks verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9795f-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="9795f-156">Ausführliche Informationen zu PSTN-Verbindungen finden Sie unter [Planning for PSTN Connectivity in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="9795f-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="9795f-157">Die Anrufsteuerung kann auf beiden Seiten des Vermittlungsserver erzwungen werden, es sei denn, die medienumgehung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9795f-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="9795f-158">Wenn die medienumgehung aktiviert ist, wird der Mediendatenverkehr nicht durchlaufen Vermittlungsserver sondern direkt zwischen dem lync-Client und dem Gateway fließt.</span><span class="sxs-lookup"><span data-stu-id="9795f-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="9795f-159">In diesem Fall ist keine Anrufsteuerung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9795f-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="9795f-160">Ausführliche Informationen finden Sie unter [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="9795f-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="9795f-161">In der folgenden Abbildung wird veranschaulicht, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne medienumgehung erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="9795f-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="9795f-162">**Erzwingen der Anrufsteuerung für Verbindungen mit dem PSTN**</span><span class="sxs-lookup"><span data-stu-id="9795f-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="9795f-163">![VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "VoIP-Anrufsteuerung medienumgehung Verbindungserzwingung")</span><span class="sxs-lookup"><span data-stu-id="9795f-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="9795f-164">Kompatibilität der Anrufsteuerung mit früheren Versionen von Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="9795f-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="9795f-165">Die Anrufsteuerung kann nur für Endpunkte aktiviert werden, die für lync Server 2010 und höher aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9795f-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="9795f-166">Die Anrufsteuerung kann nicht für Endpunkte aktiviert werden, die Office Communicator 2007 R2 oder früher durchführen.</span><span class="sxs-lookup"><span data-stu-id="9795f-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="9795f-167">**Anwendung der Anrufsteuerung in verschiedenen lync Server Versionen**</span><span class="sxs-lookup"><span data-stu-id="9795f-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="9795f-168">![Sprach-CAC-Versionsvergleichs Diagramm](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Sprach-CAC-Versionsvergleichs Diagramm")</span><span class="sxs-lookup"><span data-stu-id="9795f-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

