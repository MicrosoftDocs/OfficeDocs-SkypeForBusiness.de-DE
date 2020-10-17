---
title: Lync Server 2013 Unterstützung für SIP-Trunking
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
ms.openlocfilehash: 8d9bbf5ea35b6b24180f7853fd3715ad95973051
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519652"
---
# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="103f1-102">Unterstützung für SIP-Trunking in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="103f1-102">SIP trunking support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="103f1-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="103f1-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="103f1-104">Wenn Sie Enterprise-VoIP mit SIP-Trunking verwenden möchten, müssen Sie eine Vermittlungsserver bereitstellen und sicherstellen, dass andere Infrastrukturen und Komponenten die für Ihr Bereitstellungsmodell geeigneten Supportanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="103f1-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="103f1-105">Ausführliche Informationen zum ermitteln, ob SIP-Trunking implementiert werden soll, finden Sie unter [Overview of SIP Trunking in lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="103f1-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="103f1-106">Sie können das Microsoft Unified Communications Open Interoperability-Programm für die Enterprise-Telefonie-Infrastruktur verwenden, um qualifizierte PSTN-Gateways (Public Switched Telephone Network), IP-Nebenstellenanlagen und SIP-Trunking-Dienste zu finden, einschließlich qualifizierter IP-Telefonie-Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="103f1-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="103f1-107">Ausführliche Informationen finden Sie auf der Website Microsoft Unified Communications Open Interoperability Program unter [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .</span><span class="sxs-lookup"><span data-stu-id="103f1-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="103f1-108">Unterstützung eines Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="103f1-108">Mediation Server Support</span></span>

<span data-ttu-id="103f1-109">Zum Implementieren des SIP-trunkings müssen Sie die Verbindung über eine Vermittlungsserver weiterleiten, die als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert.</span><span class="sxs-lookup"><span data-stu-id="103f1-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="103f1-110">Der Vermittlungsserver entschlüsselt den Mediendatenverkehr von Clients und Servern und führt eine erneute Verschlüsselung durch, bevor die Daten an den Dienstanbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="103f1-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="103f1-111">Die erneute Codierung wird benötigt, da SIP-Trunks einige verwendete Codecs nicht unterstützen, beispielsweise Real Time Audio (RTA) oder Ice-Protokoll Aushandlung (Interactive Connectivity Establishment) für die Firewall-Durchquerung.</span><span class="sxs-lookup"><span data-stu-id="103f1-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="103f1-112">Jeder Vermittlungsserver kann über zwei Netzwerkkarten verfügen, die eine interne und externe Netzwerkschnittstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="103f1-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="103f1-113">Die externe Schnittstelle wird häufig als Gateway-Schnittstelle bezeichnet, da Sie traditionell verwendet wurde, um eine Verbindung mit einem PSTN-Gateway oder einer IP-Nebenstellenanlage herzustellen.</span><span class="sxs-lookup"><span data-stu-id="103f1-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="103f1-114">Zur Implementierung eines SIP-Trunks verbinden Sie die externe Schnittstelle mit einem SBC (Session Border Controller) beim Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="103f1-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="103f1-115">Zentralisiertes und verteiltes SIP-Trunking im Vergleich</span><span class="sxs-lookup"><span data-stu-id="103f1-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="103f1-116">*Zentralisiert* Mit SIP-Trunking werden alle VoIP-Datenverkehr (Voice over Internet Protocol), einschließlich des Datenverkehrs in der Zweigstelle, über das Rechenzentrum weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="103f1-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="103f1-117">Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und stellt im Allgemeinen den bevorzugten Ansatz für die Implementierung von SIP-Trunks mit lync Server 2013 dar.</span><span class="sxs-lookup"><span data-stu-id="103f1-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="103f1-p106">In Abhängigkeit von den Verwendungsmustern in Ihrem Unternehmen ist jedoch ein Routing aller Benutzer über den zentralisierten SIP-Trunk möglicherweise nicht erwünscht. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="103f1-p106">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk. To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="103f1-p107">Wie groß ist jeder Standort? Wie viele Benutzer sind vorhanden?</span><span class="sxs-lookup"><span data-stu-id="103f1-p107">How big is each site? How many users?</span></span>

  - <span data-ttu-id="103f1-122">Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?</span><span class="sxs-lookup"><span data-stu-id="103f1-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="103f1-p108">Das *verteilte* SIP-Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einem oder mehreren Zweigstellenstandorten implementieren. Der VoIP-Datenverkehr wird anschließend vom Zweigstellenstandort direkt an den zugehörigen Dienstanbieter geroutet, ohne über Ihr Rechenzentrum geleitet zu werden.</span><span class="sxs-lookup"><span data-stu-id="103f1-p108">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites. VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="103f1-125">Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="103f1-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="103f1-126">Für den Zweigstellenstandort muss Ausfallsicherheit gewährleistet werden (beispielsweise bei einem WAN-Ausfall).</span><span class="sxs-lookup"><span data-stu-id="103f1-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="103f1-127">Wenn für die Zweigstelle Redundanz und Failover erforderlich sind, berechnet der Dienstanbieter höhere Gebühren, und die Konfiguration erfordert mehr Zeit.</span><span class="sxs-lookup"><span data-stu-id="103f1-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="103f1-128">Diese Anforderung sollte für jeden Zweigstellenstandort geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="103f1-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="103f1-129">Einige ihrer Zweigstellen benötigen möglicherweise Redundanz und Failover, andere möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="103f1-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="103f1-p110">Der Zweigstellenstandort und das Rechenzentrum befinden sich in unterschiedlichen Ländern/Regionen. Aus Kompatibilitäts- und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region.</span><span class="sxs-lookup"><span data-stu-id="103f1-p110">The branch site and data center are in different countries/regions. For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="103f1-132">Für die Entscheidung, ob zentralisiertes oder verteiltes SIP-Trunking bereitgestellt werden soll, ist eine Kosten-Nutzen-Analyse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="103f1-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="103f1-133">In einigen Fällen kann es vorteilhaft sein, sich für den verteilten Bereitstellungsmodus zu entscheiden, auch wenn dies nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="103f1-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="103f1-134">In einer vollständig zentralisierten Bereitstellung wird der gesamte Zweigstellendatenverkehr über WAN-Verbindungen geroutet.</span><span class="sxs-lookup"><span data-stu-id="103f1-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="103f1-135">Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, möchten Sie möglicherweise das verteilte SIP-Trunking verwenden.</span><span class="sxs-lookup"><span data-stu-id="103f1-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="103f1-136">Ausführliche Informationen dazu, warum und wie Sie verteilte SIP-Trunking verwenden können, finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">Branch Site SIP Trunking in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="103f1-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="103f1-137">Unterstützte Verbindungstypen für das SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="103f1-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="103f1-138">Lync Server 2013 unterstützt die folgenden Verbindungstypen für das SIP-Trunking:</span><span class="sxs-lookup"><span data-stu-id="103f1-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="103f1-p112">Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet, und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.</span><span class="sxs-lookup"><span data-stu-id="103f1-p112">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require VPN. A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="103f1-p113">Eine private Verbindung ohne anderen Datenverkehr ist im Allgemeinen die zuverlässigste und sicherste Form der Verbindung (beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung). Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="103f1-p113">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line). This connection type provides the highest call-carrying capacity, but is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="103f1-147">Das öffentliche Internet ist der günstigste Verbindungstyp, bietet jedoch auch die geringste Zuverlässigkeit und Anrufkapazität.</span><span class="sxs-lookup"><span data-stu-id="103f1-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="103f1-148">Ihr Internet Telefonie-Dienstanbieter (ITSP) kann diesen SIP-Trunk-Verbindungstyp schützen, wenn er TLS (Transport Layer Security) und SRTP (Secure Real-Time Transport Protocol) zur Verschlüsselung von Signal-und Mediendatenverkehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="103f1-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="103f1-149">Wenn Sie eine SIP-Trunkverbindung über das Internet nicht für die Verwendung von TLS und SRTP konfigurieren können, wird dringend empfohlen, einen VPN-Tunnel zu verwenden, um eine sicherere Verbindung zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="103f1-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="103f1-150">Erkundigen Sie sich bei Ihrem Dienstanbieter, ob er TLS mit SRTP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="103f1-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="103f1-151">Auswählen eines Verbindungstyps</span><span class="sxs-lookup"><span data-stu-id="103f1-151">Selecting a Connection Type</span></span>

<span data-ttu-id="103f1-152">Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.</span><span class="sxs-lookup"><span data-stu-id="103f1-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="103f1-153">Für ein mittelständisches oder größeres Unternehmen bietet ein MPLS-Netzwerk im Allgemeinen den größten Nutzen.</span><span class="sxs-lookup"><span data-stu-id="103f1-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="103f1-154">Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="103f1-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="103f1-155">Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung oder eine T1-Leitung.</span><span class="sxs-lookup"><span data-stu-id="103f1-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="103f1-156">Bei einem kleinen Unternehmen oder Zweigstellenstandort mit niedrigem Anrufvolumen ist die SIP-Trunkierung über das Internet möglicherweise die beste Wahl.</span><span class="sxs-lookup"><span data-stu-id="103f1-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="103f1-157">Dieser Verbindungstyp wird jedoch nicht für mittelgroße oder größere Websites empfohlen.</span><span class="sxs-lookup"><span data-stu-id="103f1-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="103f1-158">Codec-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="103f1-158">Codec Support</span></span>

<span data-ttu-id="103f1-159">Der Dienstanbieterproxy muss die folgenden Codecs unterstützen:</span><span class="sxs-lookup"><span data-stu-id="103f1-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="103f1-160">G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)</span><span class="sxs-lookup"><span data-stu-id="103f1-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="103f1-161">G.711 µ-Law (wird in Nordamerika verwendet)</span><span class="sxs-lookup"><span data-stu-id="103f1-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

