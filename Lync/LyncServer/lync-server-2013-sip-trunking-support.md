---
title: 'Lync Server 2013: SIP-Trunking-Unterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="ce097-102">SIP-Trunking-Unterstützung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce097-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce097-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ce097-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ce097-104">Wenn Sie Enterprise-VoIP mit SIP-Trunking verwenden möchten, müssen Sie einen Vermittlungs Server bereitstellen und sicherstellen, dass andere Infrastrukturen und Komponenten die für Ihr Bereitstellungsmodell geeigneten Supportanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ce097-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="ce097-105">Details zum ermitteln, ob SIP-Trunking implementiert werden soll, finden Sie unter [Übersicht über SIP-Trunking in lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ce097-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="ce097-106">Sie können das offene Interoperabilitäts Programm Microsoft Unified Communications für die Enterprise-Telefonie-Infrastruktur verwenden, um qualifizierte PSTN-Gateways (Public Switched Telephone Network), IP-PBX-Anlagen und SIP-Trunking-Dienste, einschließlich qualifizierter IP-Telefonie, zu finden. Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="ce097-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="ce097-107">Ausführliche Informationen finden Sie auf [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)der Microsoft Unified Communications Open Interoperability Program-Website unter.</span><span class="sxs-lookup"><span data-stu-id="ce097-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="ce097-108">Vermittlungs Server Unterstützung</span><span class="sxs-lookup"><span data-stu-id="ce097-108">Mediation Server Support</span></span>

<span data-ttu-id="ce097-109">Um SIP-Trunking zu implementieren, müssen Sie die Verbindung über einen Vermittlungs Server weiterleiten, der als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert.</span><span class="sxs-lookup"><span data-stu-id="ce097-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="ce097-110">Der Vermittlungs Server dekodiert den Mediendatenverkehr von Clients und Servern und codiert ihn erneut, bevor er an den Dienstanbieter gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="ce097-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="ce097-111">Die erneute Codierung ist erforderlich, da SIP-Trunks einige verwendete Codecs nicht unterstützen, wie etwa Echtzeit-Audio (RTA) oder Interaktions Einrichtung (ICE) Protocol Negotiation für die Firewall-Durchquerung.</span><span class="sxs-lookup"><span data-stu-id="ce097-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="ce097-112">Jeder Vermittlungs Server kann über zwei Netzwerkadapter verfügen, die eine interne und eine externe Netzwerkschnittstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ce097-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="ce097-113">Die externe Schnittstelle wird gemeinhin als Gateway-Schnittstelle bezeichnet, da Sie üblicherweise für die Verbindung mit einem PSTN-Gateway oder einer IP-PBX-Anlage verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ce097-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="ce097-114">Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle mit einem Session Border Controller (SBC) bei einem Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="ce097-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="ce097-115">Zentralisiertes und verteiltes SIP-Trunking im Vergleich</span><span class="sxs-lookup"><span data-stu-id="ce097-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="ce097-116">*Zentralisiert* SIP-Trunking leitet den gesamten VoIP-Datenverkehr (einschließlich Zweigstellen-Websitedatenverkehr) über Ihr Rechenzentrum weiter.</span><span class="sxs-lookup"><span data-stu-id="ce097-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="ce097-117">Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und im Allgemeinen der bevorzugte Ansatz für die Implementierung von SIP-Stämmen mit lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce097-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="ce097-118">Je nach Verwendungsmustern in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralisierten SIP-Stamm weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="ce097-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="ce097-119">Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="ce097-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="ce097-120">Wie groß ist jede Website?</span><span class="sxs-lookup"><span data-stu-id="ce097-120">How big is each site?</span></span> <span data-ttu-id="ce097-121">Wie viele Benutzer?</span><span class="sxs-lookup"><span data-stu-id="ce097-121">How many users?</span></span>

  - <span data-ttu-id="ce097-122">Welche direkten Durchwahlnummern (DID) an jedem Standort erhalten die meisten Telefonanrufe?</span><span class="sxs-lookup"><span data-stu-id="ce097-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="ce097-123">*Verteilte* SIP Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einer oder mehreren Zweigstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="ce097-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="ce097-124">VoIP-Datenverkehr wird dann direkt von der Verzweigungs Website an Ihren Dienstanbieter weitergeleitet, ohne Ihr Rechenzentrum zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="ce097-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="ce097-125">Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="ce097-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="ce097-126">Die Verzweigungs Website erfordert eine überlebensfähige Telefonverbindung (beispielsweise, wenn das WAN ausfällt).</span><span class="sxs-lookup"><span data-stu-id="ce097-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="ce097-127">Wenn für die Verzweigung Redundanz und Failover erforderlich sind, berechnet der Dienstanbieter mehr, und die Konfiguration wird länger dauern.</span><span class="sxs-lookup"><span data-stu-id="ce097-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="ce097-128">Dies sollte für jede Verzweigungs Website analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="ce097-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="ce097-129">Einige ihrer Zweigstellen erfordern möglicherweise Redundanz und Failover, während andere möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="ce097-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="ce097-130">Die Verzweigungs Website und das Rechenzentrum befinden sich in verschiedenen Ländern/Regionen.</span><span class="sxs-lookup"><span data-stu-id="ce097-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="ce097-131">Aus Kompatibilitäts-und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region.</span><span class="sxs-lookup"><span data-stu-id="ce097-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="ce097-132">Die Entscheidung, ob eine zentralisierte oder verteilte SIP-Trunkierung bereitgestellt werden soll, erfordert eine Kosten-Nutzen-Analyse.</span><span class="sxs-lookup"><span data-stu-id="ce097-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="ce097-133">In einigen Fällen kann es vorteilhaft sein, den verteilten Bereitstellungsmodus zu wählen, auch wenn dies nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ce097-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="ce097-134">Bei einer vollständig zentralisierten Bereitstellung wird der gesamte Datenverkehr der Zweigstelle über WAN-Verbindungen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ce097-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="ce097-135">Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, können Sie das verteilte SIP-Trunking verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce097-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce097-136">Ausführliche Informationen dazu, warum und wie Sie das verteilte SIP-Trunking verwenden können, finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">SIP-Trunking in der Zweigstelle in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ce097-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="ce097-137">Unterstützte Verbindungstypen für das SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="ce097-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="ce097-138">Lync Server 2013 unterstützt die folgenden Verbindungstypen für SIP-Trunking:</span><span class="sxs-lookup"><span data-stu-id="ce097-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="ce097-139">Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt.</span><span class="sxs-lookup"><span data-stu-id="ce097-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="ce097-140">Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ce097-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="ce097-141">Für diesen Verbindungstyp ist kein VPN erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce097-141">This connection type does not require VPN.</span></span> <span data-ttu-id="ce097-142">Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.</span><span class="sxs-lookup"><span data-stu-id="ce097-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="ce097-143">Eine private Verbindung ohne anderen Datenverkehr ist in der Regel der zuverlässigste und sicherste Verbindungstyp (beispielsweise eine geleaste Glasfaser-oder T1-Verbindung).</span><span class="sxs-lookup"><span data-stu-id="ce097-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="ce097-144">Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist aber in der Regel am teuersten.</span><span class="sxs-lookup"><span data-stu-id="ce097-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="ce097-145">Ein VPN ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce097-145">VPN is not required.</span></span> <span data-ttu-id="ce097-146">Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="ce097-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="ce097-147">Das öffentliche Internet ist der kostengünstigste Verbindungstyp, aber auch der am wenigsten zuverlässige, und der mit der niedrigsten Anruf Tragfähigkeit.</span><span class="sxs-lookup"><span data-stu-id="ce097-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="ce097-148">Ihr Internet-Telefoniedienstanbieter (ITSP) kann diesen SIP Trunk-Verbindungstyp schützen, wenn er TLS (Transport Layer Security) und SRTP (Secure Real-Time Transport Protocol) unterstützt, um Signalisierungs-und Mediendatenverkehr zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ce097-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="ce097-149">Wenn Sie keine SIP Trunk-Verbindung über das Internet für die Verwendung von TLS und SRTP konfigurieren können, wird dringend empfohlen, einen VPN-Tunnel zu verwenden, um eine sicherere Verbindung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ce097-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="ce097-150">Wenden Sie sich an Ihren ITSP, um zu ermitteln, ob er TLS mit SRTP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ce097-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="ce097-151">Auswählen eines Verbindungstyps</span><span class="sxs-lookup"><span data-stu-id="ce097-151">Selecting a Connection Type</span></span>

<span data-ttu-id="ce097-152">Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.</span><span class="sxs-lookup"><span data-stu-id="ce097-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="ce097-153">Für ein mittelständisches oder größeres Unternehmen bietet ein MPLS-Netzwerk im Allgemeinen den größten Wert.</span><span class="sxs-lookup"><span data-stu-id="ce097-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="ce097-154">Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="ce097-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="ce097-155">Große Unternehmen benötigen möglicherweise eine private Fiber-Optic-oder T1-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="ce097-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="ce097-156">Für ein kleines Unternehmen oder eine Zweigstelle mit geringem Anrufaufkommen kann die SIP-Trunkierung über das Internet die beste Wahl sein.</span><span class="sxs-lookup"><span data-stu-id="ce097-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="ce097-157">Dieser Verbindungstyp wird jedoch für mittelgroße oder größere Websites nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ce097-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="ce097-158">Codec-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="ce097-158">Codec Support</span></span>

<span data-ttu-id="ce097-159">Der Dienstanbieter Proxy muss die folgenden Codecs unterstützen:</span><span class="sxs-lookup"><span data-stu-id="ce097-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="ce097-160">G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)</span><span class="sxs-lookup"><span data-stu-id="ce097-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="ce097-161">G.711 µ-Law (wird in Nordamerika eingesetzt)</span><span class="sxs-lookup"><span data-stu-id="ce097-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

