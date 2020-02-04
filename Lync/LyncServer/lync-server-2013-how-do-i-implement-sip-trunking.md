---
title: 'Lync Server 2013: Implementierung von SIP-Trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de621d7508b69dd3adc3babf487406825f3a93f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="d3183-102">Implementierung von SIP-Trunking in Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="d3183-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3183-103">_**Letztes Änderungsdatum des Themas:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="d3183-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="d3183-104">Wenn Sie SIP-Trunking implementieren möchten, müssen Sie die Verbindung über einen Vermittlungs Server weiterleiten, der als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert und die Medien bei Bedarf transcodieren kann.</span><span class="sxs-lookup"><span data-stu-id="d3183-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="d3183-105">Jeder Vermittlungs Server verfügt über eine interne Netzwerkschnittstelle und eine externe Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d3183-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="d3183-106">Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern her.</span><span class="sxs-lookup"><span data-stu-id="d3183-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="d3183-107">Die externe Schnittstelle wird gemeinhin als Gateway-Schnittstelle bezeichnet, da Sie traditionell verwendet wurde, um den Vermittlungs Server mit einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Telefonanlage zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="d3183-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="d3183-108">Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle des Vermittlungsservers mit der Komponente External Edge des ITSP.</span><span class="sxs-lookup"><span data-stu-id="d3183-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3183-109">Die externe Edgekomponente des ITSP könnte ein Session Border Controller (SBC), ein Router oder ein Gateway sein.</span><span class="sxs-lookup"><span data-stu-id="d3183-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="d3183-110">Details zu Vermittlungsservern finden Sie unter [Mediation Server Component in lync Server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="d3183-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="d3183-111">Zentralisiertes und verteiltes SIP-Trunking im Vergleich</span><span class="sxs-lookup"><span data-stu-id="d3183-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="d3183-112">*Zentralisiert* SIP-Trunking leitet den gesamten VoIP-Datenverkehr (einschließlich Zweigstellen-Websitedatenverkehr) über Ihren zentralen Standort weiter.</span><span class="sxs-lookup"><span data-stu-id="d3183-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="d3183-113">Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und im Allgemeinen der empfohlene Ansatz für die Implementierung von SIP-Stämmen mit lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3183-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="d3183-114">*Verteilte* SIP Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einer oder mehreren Zweigstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="d3183-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="d3183-115">VoIP-Datenverkehr wird dann direkt von der Verzweigungs Website an einen Dienstanbieter weitergeleitet, ohne die zentrale Website zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d3183-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="d3183-116">Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="d3183-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="d3183-117">Die Verzweigungs Website erfordert eine überlebensfähige Telefonverbindung (beispielsweise, wenn das WAN ausfällt).</span><span class="sxs-lookup"><span data-stu-id="d3183-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="d3183-118">Diese Anforderung sollte für jede Verzweigungs Website analysiert werden. einige ihrer Zweigstellen erfordern möglicherweise Redundanz und Failover, während andere möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="d3183-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="d3183-119">Zwischen zwei zentralen Standorten ist eine Ausfallsicherheit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3183-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="d3183-120">Sie müssen sicherstellen, dass ein SIP-Trunk an jedem zentralen Standort beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3183-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="d3183-121">Wenn Sie beispielsweise über Dublin-und Tukwila-zentrale Websites verfügen und beide nur den SIP-Stamm einer Website verwenden, können die Benutzer der anderen Website keine PSTN-Anrufe tätigen, wenn der trunk herunterfällt.</span><span class="sxs-lookup"><span data-stu-id="d3183-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="d3183-122">Die Verzweigungs Website und der zentrale Standort befinden sich in verschiedenen Ländern/Regionen.</span><span class="sxs-lookup"><span data-stu-id="d3183-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="d3183-123">Aus Kompatibilitäts-und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region.</span><span class="sxs-lookup"><span data-stu-id="d3183-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="d3183-124">In der Europäischen Union kann die Kommunikation beispielsweise ein Land/eine Region nicht bestanden, ohne lokal an einem zentralen Punkt zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d3183-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="d3183-125">Je nach geographischem Standort der Websites und dem voraussichtlichen Datenverkehr in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralen SIP-Stamm weiterleiten, oder Sie können einige Benutzer über einen SIP-Stamm an ihrer Zweigstelle weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="d3183-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="d3183-126">Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="d3183-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="d3183-127">Wie groß ist jede Website (also, wie viele Benutzer sind für Enterprise-VoIP aktiviert)?</span><span class="sxs-lookup"><span data-stu-id="d3183-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="d3183-128">Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?</span><span class="sxs-lookup"><span data-stu-id="d3183-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="d3183-129">Die Entscheidung zur Bereitstellung des zentralisierten oder verteilten SIP-Trunkings erfordert eine Kosten-Nutzen-Analyse.</span><span class="sxs-lookup"><span data-stu-id="d3183-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="d3183-130">In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="d3183-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="d3183-131">Bei einer vollständig zentralisierten Bereitstellung wird der gesamte Datenverkehr der Zweigstelle über WAN-Verbindungen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d3183-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="d3183-132">Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, können Sie das verteilte SIP-Trunking verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3183-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="d3183-133">So können Sie beispielsweise einen Standard Edition-Server an einer Zweigstelle mit Föderations Standort an der zentralen Website bereitstellen, oder Sie möchten eine Survivable Branch-Appliance oder einen Überlebenden Branch-Server mit einem kleinen Gateway bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d3183-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3183-134">Details zum verteilten SIP-Trunking finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">SIP-Trunking in der Zweigstelle in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d3183-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="d3183-135">Unterstützte Verbindungstypen für das SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="d3183-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="d3183-136">Lync Server unterstützt die folgenden Verbindungstypen für SIP-Trunking:</span><span class="sxs-lookup"><span data-stu-id="d3183-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="d3183-p109">Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.</span><span class="sxs-lookup"><span data-stu-id="d3183-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="d3183-p110">Eine private Verbindung ohne anderen Datenverkehr – beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung – stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d3183-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="d3183-145">Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="d3183-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="d3183-146">Internet Verbindung ist die einzige SIP-Trunking-Verbindungsart für lync Server, für die VPN erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d3183-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="d3183-147">Auswählen eines Verbindungstyps</span><span class="sxs-lookup"><span data-stu-id="d3183-147">Selecting a Connection Type</span></span>

<span data-ttu-id="d3183-148">Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.</span><span class="sxs-lookup"><span data-stu-id="d3183-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="d3183-p112">Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="d3183-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="d3183-151">Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).</span><span class="sxs-lookup"><span data-stu-id="d3183-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="d3183-152">Für ein kleines Unternehmen oder eine Zweigstelle mit geringem Anrufaufkommen kann die SIP-Trunkierung über das Internet die beste Wahl sein.</span><span class="sxs-lookup"><span data-stu-id="d3183-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="d3183-153">Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d3183-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="d3183-154">Erforderliche Bandbreite</span><span class="sxs-lookup"><span data-stu-id="d3183-154">Bandwidth Requirements</span></span>

<span data-ttu-id="d3183-p114">Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (der Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="d3183-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="d3183-158">Spitzenbandbreite für den SIP-Trunk = Max. gleichzeitige Anrufe x (64 KBit/s + Headergröße)</span><span class="sxs-lookup"><span data-stu-id="d3183-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3183-159">Die Headergröße beträgt maximal 20 Byte.</span><span class="sxs-lookup"><span data-stu-id="d3183-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="d3183-160">Codec-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d3183-160">Codec Support</span></span>

<span data-ttu-id="d3183-161">Lync Server 2013 unterstützt nur die folgenden Codecs:</span><span class="sxs-lookup"><span data-stu-id="d3183-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="d3183-162">G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)</span><span class="sxs-lookup"><span data-stu-id="d3183-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="d3183-163">G.711 µ-Law (wird in Nordamerika eingesetzt)</span><span class="sxs-lookup"><span data-stu-id="d3183-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="d3183-164">Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="d3183-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="d3183-165">Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten.</span><span class="sxs-lookup"><span data-stu-id="d3183-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="d3183-166">Informationen zur Bereitstellung erhalten Sie von Ihrem Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="d3183-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="d3183-167">Eine Liste der zertifizierten SIP-Trunking-Dienstanbieter finden Sie auf der [Microsoft Unified Communications Open Interoperability Program-Website](http://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="d3183-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="d3183-168">Ausführliche Informationen zu für Microsoft zertifizierten Anbietern von SIP-Trunking erhalten Sie bei Ihrem Microsoft-Ansprechpartner.</span><span class="sxs-lookup"><span data-stu-id="d3183-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3183-p116">Sie müssen einen für Microsoft zertifizierten Dienstanbieter nutzen, um sicherzustellen, dass Ihr Anbieter von Internettelefoniediensten sämtliche Funktionen unterstützt, die über den SIP-Trunk verarbeitet werden (z. B. das Einrichten und Verwalten von Sitzungen sowie die Unterstützung aller erweiterten VoIP-Dienste). Der technische Support von Microsoft kann nicht für Konfigurationen in Anspruch genommen werden, die nicht zertifizierte Anbieter verwenden. Wenn Sie gegenwärtig einen Internetdienstanbieter nutzen, der nicht für SIP-Trunking zertifiziert ist, können Sie diesen Anbieter weiterhin als ISP nutzen und sich für das SIP-Trunking für einen für Microsoft zertifizierten Anbieter entscheiden.</span><span class="sxs-lookup"><span data-stu-id="d3183-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

