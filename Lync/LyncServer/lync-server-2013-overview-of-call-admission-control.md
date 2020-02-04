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
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="04313-102">Übersicht über die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04313-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04313-103">_**Letztes Änderungsdatum des Themas:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="04313-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="04313-104">Echtzeitkommunikation ist sensibel für Latenz-und Paketverluste, die in überlasteten Netzwerken auftreten können.</span><span class="sxs-lookup"><span data-stu-id="04313-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="04313-105">Der Anrufsteuerungsdienst ermittelt anhand der verfügbaren Netzwerkbandbreite, ob Kommunikationssitzungen (beispielsweise Sprach- oder Videoanrufe) in Echtzeit eingerichtet werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="04313-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="04313-106">Das CAC-Design in lync Server 2013 bietet vier Hauptattribute:</span><span class="sxs-lookup"><span data-stu-id="04313-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="04313-107">Sie lässt sich problemlos bereitstellen und verwalten, ohne dass zusätzliche Geräte (z. B. speziell konfigurierte Router) erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="04313-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="04313-p102">Sie eignet sich für wichtige Unified Communications-Anwendungsfälle, z. B. für Roamingbenutzer und für die Anmeldung auf mehreren Geräten. Anrufsteuerungsrichtlinien werden nicht abhängig davon erzwungen, wo der Benutzer verwaltet wird, sondern basierend auf dem Standort des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="04313-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="04313-110">Zusätzlich zu VoIP-Anrufen kann die Anrufsteuerung auf andere Typen von Datenverkehr angewendet werden, z. B. auf Videoanrufe und Audio/Video-Konferenzsitzungen.</span><span class="sxs-lookup"><span data-stu-id="04313-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="04313-111">Dies bietet die Flexibilität, verschiedene Arten von Netzwerktopologien darstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="04313-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="04313-112">Beispiele finden Sie unter [Komponenten und Topologien für CAC in lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="04313-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="04313-113">Wenn eine neue VoIP- oder Videositzung die festgelegten Bandbreiteneinschränkungen einer WAN-Leitung überschreitet, wird die Sitzung entweder blockiert oder (dies gilt nur für Telefonanrufe) an das Festnetz umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="04313-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="04313-p104">Mit der Anrufsteuerung wird lediglich Echtzeitdatenverkehr für VoIP- und Videoanrufe gesteuert. Anderer Datenverkehr wird nicht gesteuert.</span><span class="sxs-lookup"><span data-stu-id="04313-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="04313-116">Administratoren definieren CAC-Richtlinien, die vom bandbreitenrichtliniendienst erzwungen werden, der mit jedem Front-End-Pool installiert wird.</span><span class="sxs-lookup"><span data-stu-id="04313-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="04313-117">Die CAC-Einstellungen werden automatisch an alle lync Server-Front-End-Server in Ihrem Netzwerk weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="04313-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="04313-118">Bei Anrufen, die aufgrund von Anrufsteuerungsrichtlinien nicht erfolgreich durchgeführt werden können, gilt folgende Reihenfolge für die Anrufumleitung:</span><span class="sxs-lookup"><span data-stu-id="04313-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="04313-119">Internet</span><span class="sxs-lookup"><span data-stu-id="04313-119">Internet</span></span>

2.  <span data-ttu-id="04313-120">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="04313-120">PSTN</span></span>

3.  <span data-ttu-id="04313-121">Voicemail</span><span class="sxs-lookup"><span data-stu-id="04313-121">Voice mail</span></span>

<span data-ttu-id="04313-p106">Bei der Aufzeichnung von Kommunikationsdatensätzen werden Informationen zu Anrufen erfasst, die an das Festnetz oder an einen Voicemaildienst umgeleitet werden. Da das Internet nicht als sekundäre Option, sondern als alternativer Pfad behandelt wird, werden bei der Aufzeichnung von Kommunikationsdatensätzen keine Informationen zu Anrufen erfasst, die an das Internet umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="04313-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04313-124">Das Hinterlassen von Voicemails wird aufgrund von Bandbreitenbeschränkungen nicht abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="04313-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="04313-p107">Der Bandbreitenrichtliniendienst generiert zwei Typen von Protokolldateien im CSV-Format (durch Trennzeichen getrennte Datei). In der Protokolldatei für **Fehler bei der Überprüfung** werden Informationen erfasst, wenn Bandbreitenanforderungen abgelehnt werden. In der Protokolldatei zur **Verbindungsauslastung** werden ein Snapshot der Netzwerktopologie sowie die Bandbreitenauslastung der WAN-Verbindung erfasst. Unter Verwendung dieser beiden Protokolldateien können Sie Ihre Anrufsteuerungsrichtlinien basierend auf der Auslastung optimieren.</span><span class="sxs-lookup"><span data-stu-id="04313-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="04313-129">Überlegungen zur Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="04313-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="04313-130">Der Administrator wählt aus, dass der Bandbreitenrichtliniendienst auf dem ersten Pool am zentralen Standort konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="04313-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="04313-131">Da es pro Netzwerkregion einen einzelnen zentralen Standort gibt, gibt es pro Netzwerkregion auch nur einen einzigen Bandbreitenrichtliniendienst, der die Bandbreitenrichtlinien für die entsprechende Region, die zugeordneten Standorte und die Links zu diesen Standorten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="04313-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="04313-132">Der bandbreitenrichtliniendienst wird als Teil der Front-End-Server ausgeführt, und daher ist eine höhere Verfügbarkeit innerhalb dieses Pools integriert.</span><span class="sxs-lookup"><span data-stu-id="04313-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="04313-133">Der bandbreitenrichtliniendienst, der auf jedem Front-End-Server ausgeführt wird, synchronisiert alle 15 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="04313-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="04313-134">Wenn der Front-End-Pool ausfällt, werden die CAC-Richtlinien für diese Website erst dann erzwungen, wenn der Front-End-Pool und damit der bandbreitenrichtliniendienst wieder in Betrieb genommen wird.</span><span class="sxs-lookup"><span data-stu-id="04313-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="04313-135">Das bedeutet, dass während der Zeit, in der der Bandbreitenrichtliniendienst ausfällt, alle Anrufe durchgehen.</span><span class="sxs-lookup"><span data-stu-id="04313-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="04313-136">Aus diesem Grund besteht in diesem Zeitraum die Möglichkeit einer zu hohen Bandbreitenbelegung Ihrer Links.</span><span class="sxs-lookup"><span data-stu-id="04313-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="04313-137">Der bandbreitenrichtliniendienst bietet eine große Verfügbarkeit innerhalb eines Front-End-Pools. Es bietet jedoch keine Redundanz über Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="04313-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="04313-138">Der bandbreitenrichtliniendienst kann nicht von einem Front-End-Pool zu einem anderen Failover.</span><span class="sxs-lookup"><span data-stu-id="04313-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="04313-139">Nachdem der Service für den Front-End-Pool wiederhergestellt wurde, wird der bandbreitenrichtliniendienst fortgesetzt und kann die Überprüfung der Bandbreitenrichtlinien erneut erzwingen.</span><span class="sxs-lookup"><span data-stu-id="04313-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="04313-140">Überlegungen zum Netzwerk</span><span class="sxs-lookup"><span data-stu-id="04313-140">Network Considerations</span></span>

<span data-ttu-id="04313-141">Obwohl die Bandbreitenbeschränkung für Audio und Video vom bandbreitenrichtliniendienst in lync Server 2013 erzwungen wird, wird diese Einschränkung beim Netzwerkrouter nicht erzwungen (Layer 2 und 3).</span><span class="sxs-lookup"><span data-stu-id="04313-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="04313-142">Lync Server 2010 CAC kann eine Daten Anwendung beispielsweise nicht daran hindern, die gesamte Netzwerkbandbreite einer WAN-Verbindung zu nutzen, einschließlich der Bandbreite, die von ihrer CAC-Richtlinie für Audio und Video reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="04313-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="04313-143">Um sicherzustellen, dass die erforderliche Bandbreite in Ihrem Netzwerk reserviert wird, können Sie ein QoS-Protokoll (Quality of Service) wie Differenzierte Dienste (DiffServ) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="04313-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="04313-144">Daher empfiehlt es sich, die definierten Bandbreitenrichtlinien der Anrufsteuerung auf QoS-Einstellungen abzustimmen, die Sie gegebenenfalls bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="04313-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="04313-145">Medien- und Signalpfade über ein VPN</span><span class="sxs-lookup"><span data-stu-id="04313-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="04313-p111">Wenn Ihr Unternehmen die Medienübermittlung über ein VPN unterstützt, müssen Sie sicherstellen, dass sowohl der Medien- als auch der Signaldatenstrom über das VPN verarbeitet werden bzw. beide Datenströme über das Internet geroutet werden. In der Standardeinstellung werden die Medien- und Signaldatenströme durch den VPN-Tunnel verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="04313-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="04313-148">Anrufsteuerung für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="04313-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="04313-149">Die Anrufsteuerung wird nicht für Remotebenutzer erzwungen, bei denen der Netzwerkdatenverkehr über das Internet fließt.</span><span class="sxs-lookup"><span data-stu-id="04313-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="04313-150">Da der Mediendatenverkehr das Internet durchläuft, das nicht von lync Server verwaltet wird, kann CAC nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="04313-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="04313-151">Für den Teil des Anrufs, der über das Unternehmensnetzwerk fließt, werden jedoch CAC-Prüfungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="04313-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="04313-152">Anrufsteuerung für PSTN-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="04313-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="04313-153">Die Anrufsteuerung ist auf dem Vermittlungs Server unabhängig davon durchsetzbar, ob Sie mit einer IP/PBX-Anlage, einem PSTN-Gateway oder einem SIP-Trunk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="04313-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="04313-154">Da es sich bei dem Vermittlungs Server um einen Back-to-Back-Benutzer-Agent (B2BUA) handelt, wird der Mediendienst beendet.</span><span class="sxs-lookup"><span data-stu-id="04313-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="04313-155">Es hat zwei Verbindungsseiten: eine Seite, die mit dem lync-Server verbunden ist, und eine Gatewayseite, die mit PSTN-Gateways, IP/PBX-Anlagen oder SIP-Stämmen verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="04313-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="04313-156">Details zu PSTN-Verbindungen finden Sie unter [Planen der PSTN-Konnektivität in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="04313-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="04313-157">CAC kann auf beiden Seiten des Vermittlungsservers erzwungen werden, es sei denn, die medienumgehung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="04313-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="04313-158">Wenn die medienumgehung aktiviert ist, wird der Mediendatenverkehr nicht durch den Vermittlungs Server durchlaufen, sondern direkt zwischen dem lync-Client und dem Gateway.</span><span class="sxs-lookup"><span data-stu-id="04313-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="04313-159">In diesem Fall wird die Anrufsteuerung nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="04313-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="04313-160">Ausführliche Informationen finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="04313-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="04313-161">Die folgende Abbildung zeigt, wie die Anrufsteuerung für PSTN-Verbindungen mit und ohne Medienumgehung erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="04313-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="04313-162">**Erzwingen der Anrufsteuerung für Verbindungen mit dem PSTN**</span><span class="sxs-lookup"><span data-stu-id="04313-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="04313-163">![Voice CAC Media Bypass-Verbindungserzwingung](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass-Verbindungserzwingung")</span><span class="sxs-lookup"><span data-stu-id="04313-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="04313-164">Kompatibilität der Anrufsteuerung mit früheren Versionen von Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="04313-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="04313-165">Die Anrufsteuerung kann nur auf Endpunkten aktiviert werden, die für lync Server 2010 und höher aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="04313-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="04313-166">Die Anrufsteuerung kann auf Endpunkten mit Office Communicator 2007 R2 oder früheren Versionen nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="04313-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="04313-167">**Anwendung von CAC in verschiedenen lync Server-Versionen**</span><span class="sxs-lookup"><span data-stu-id="04313-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="04313-168">![Sprach-CAC-Versionsvergleichs Diagramm](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Sprach-CAC-Versionsvergleichs Diagramm")</span><span class="sxs-lookup"><span data-stu-id="04313-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

