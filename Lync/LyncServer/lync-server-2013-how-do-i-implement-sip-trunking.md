---
title: 'Lync Server 2013: Wie kann ich SIP-Trunking implementieren?'
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
ms.openlocfilehash: 5e5265f580e3894d0fc8214b974ad03c9559323c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="6d5c7-102">Wie kann ich SIP-Trunking in lync Server 2013 implementieren?</span><span class="sxs-lookup"><span data-stu-id="6d5c7-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d5c7-103">_**Letztes Änderungsstand des Themas:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="6d5c7-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="6d5c7-104">Um SIP-Trunking implementieren zu können, müssen Sie die Verbindung über eine Vermittlungsserver weiterleiten, die als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert und bei Bedarf transcodierte Medien.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="6d5c7-105">Jedes Vermittlungsserver verfügt über eine interne Netzwerkschnittstelle und eine externe Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="6d5c7-106">Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern her.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="6d5c7-107">Die externe Schnittstelle wird häufig als Gateway-Schnittstelle bezeichnet, da Sie traditionell verwendet wurde, um die Vermittlungsserver mit einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Nebenstellenanlage zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="6d5c7-108">Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle des Vermittlungsserver mit der externen Edge-Komponente des ITSP.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d5c7-109">Die externe Edgekomponente des ITSP kann ein SBC (Session Border Controller), ein Router oder ein Gateway sein.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="6d5c7-110">Ausführliche Informationen zu Vermittlungsservern finden Sie unter [Vermittlungsserver-Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="6d5c7-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="6d5c7-111">Zentralisiertes und verteiltes SIP-Trunking im Vergleich</span><span class="sxs-lookup"><span data-stu-id="6d5c7-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="6d5c7-112">*Zentralisiert* Mit SIP-Trunking werden alle VoIP-Datenverkehr (Voice over Internet Protocol), einschließlich des Datenverkehrs an der Zweigstelle, über den zentralen Standort weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="6d5c7-113">Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und wird im Allgemeinen als Ansatz zur Implementierung von SIP-Trunks mit lync Server 2013 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="6d5c7-114">*Verteilt* Bei SIP-Trunking handelt es sich um ein Bereitstellungsmodell, in dem Sie einen lokalen SIP-Trunk an einem oder mehreren Zweigstellenstandorten implementieren.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="6d5c7-115">VoIP-Datenverkehr wird dann direkt vom Zweigstellenstandort an einen Dienstanbieter weitergeleitet, ohne den zentralen Standort zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="6d5c7-116">Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6d5c7-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="6d5c7-117">Für den Zweigstellenstandort muss Ausfallsicherheit gewährleistet werden (beispielsweise bei einem WAN-Ausfall).</span><span class="sxs-lookup"><span data-stu-id="6d5c7-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="6d5c7-118">Diese Anforderung sollte für jeden Zweigstellenstandort analysiert werden. einige ihrer Zweigstellen benötigen möglicherweise Redundanz und Failover, andere dagegen nicht.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="6d5c7-119">Ausfallsicherheit ist zwischen zwei zentralen Standorten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="6d5c7-120">Sie müssen sicherstellen, dass ein SIP-Trunk an jedem zentralen Standort beendet wird.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="6d5c7-121">Wenn beispielsweise die zentralen Standorte Dublin und Tukwila und beide nur den SIP-Trunk eines Standorts verwenden und der trunk ausfällt, können die Benutzer der anderen Website keine PSTN-Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="6d5c7-122">Der Zweigstellenstandort und der zentrale Standort befinden sich in unterschiedlichen Ländern/Regionen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="6d5c7-123">Aus Kompatibilitäts- und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="6d5c7-124">Beispielsweise kann die Kommunikation in der Europäischen Union ein Land/eine Region nicht verlassen, ohne lokal an einem zentralen Ort zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="6d5c7-125">Abhängig vom geografischen Standort der Standorte und von der voraussichtlichen Menge an Datenverkehr in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralen SIP-Trunk weiterleiten, oder Sie können einige Benutzer über einen SIP-Trunk an Ihrem Zweigstellenstandort weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="6d5c7-126">Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="6d5c7-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="6d5c7-127">Wie groß ist jeder Standort (also wie viele Benutzer sind für Enterprise-VoIP aktiviert)?</span><span class="sxs-lookup"><span data-stu-id="6d5c7-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="6d5c7-128">Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?</span><span class="sxs-lookup"><span data-stu-id="6d5c7-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="6d5c7-129">Die Entscheidung, ob ein zentralisiertes oder verteiltes SIP-Trunking bereitgestellt werden soll, erfordert eine Kosten-Nutzen-Analyse.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="6d5c7-130">In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="6d5c7-131">In einer vollständig zentralisierten Bereitstellung wird der gesamte Zweigstellendatenverkehr über WAN-Verbindungen geroutet.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="6d5c7-132">Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, möchten Sie möglicherweise das verteilte SIP-Trunking verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="6d5c7-133">Sie können beispielsweise eine Standard Edition-Server an einem Zweigstellenstandort mit Partnerverbund am zentralen Standort bereitstellen, oder Sie möchten ein Survivable Branch Appliance oder ein Survivable Branch Server mit einem kleinen Gateway bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d5c7-134">Ausführliche Informationen zum verteilten SIP-Trunking finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">Branch Site SIP Trunking in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="6d5c7-135">Unterstützte Verbindungstypen für das SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="6d5c7-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="6d5c7-136">Lync Server unterstützt die folgenden Verbindungstypen für das SIP-Trunking:</span><span class="sxs-lookup"><span data-stu-id="6d5c7-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="6d5c7-p109">Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet, und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="6d5c7-p110">Eine private Verbindung ohne anderen Datenverkehr – beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung – stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="6d5c7-145">Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="6d5c7-146">Internet Verbindung ist die einzige lync Server SIP-Trunking-Verbindungstyp, der VPN erfordert.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="6d5c7-147">Auswählen eines Verbindungstyps</span><span class="sxs-lookup"><span data-stu-id="6d5c7-147">Selecting a Connection Type</span></span>

<span data-ttu-id="6d5c7-148">Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="6d5c7-p112">Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="6d5c7-151">Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).</span><span class="sxs-lookup"><span data-stu-id="6d5c7-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="6d5c7-152">Bei einem kleinen Unternehmen oder Zweigstellenstandort mit niedrigem Anrufvolumen ist die SIP-Trunkierung über das Internet möglicherweise die beste Wahl.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="6d5c7-153">Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="6d5c7-154">Erforderliche Bandbreite</span><span class="sxs-lookup"><span data-stu-id="6d5c7-154">Bandwidth Requirements</span></span>

<span data-ttu-id="6d5c7-p114">Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (die Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="6d5c7-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="6d5c7-158">Spitzenbandbreite für den SIP-Trunk = Max. gleichzeitige Anrufe x (64 KBit/s + Headergröße)</span><span class="sxs-lookup"><span data-stu-id="6d5c7-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d5c7-159">Die Headergröße beträgt maximal 20 Byte.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="6d5c7-160">Codec-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="6d5c7-160">Codec Support</span></span>

<span data-ttu-id="6d5c7-161">Lync Server 2013 unterstützt nur die folgenden Codecs:</span><span class="sxs-lookup"><span data-stu-id="6d5c7-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="6d5c7-162">G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)</span><span class="sxs-lookup"><span data-stu-id="6d5c7-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="6d5c7-163">G.711 µ-Law (wird in Nordamerika verwendet)</span><span class="sxs-lookup"><span data-stu-id="6d5c7-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="6d5c7-164">Anbieter von Internettelefoniediensten</span><span class="sxs-lookup"><span data-stu-id="6d5c7-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="6d5c7-165">Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="6d5c7-166">Informationen zur Bereitstellung erhalten Sie bei Ihrem Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="6d5c7-167">Eine Liste der zertifizierten SIP-Trunking-Dienstanbieter finden Sie unter [Microsoft Unified Communications Open Interoperability Program-Website](https://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="6d5c7-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="6d5c7-168">Ausführliche Informationen zu für Microsoft zertifizierten Anbietern von SIP-Trunking erhalten Sie bei Ihrem Microsoft-Ansprechpartner.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6d5c7-p116">Sie müssen einen für Microsoft zertifizierten Dienstanbieter nutzen, um sicherzustellen, dass Ihr Anbieter von Internettelefoniediensten sämtliche Funktionen unterstützt, die über den SIP-Trunk verarbeitet werden (z. B. das Einrichten und Verwalten von Sitzungen sowie die Unterstützung aller erweiterten VoIP-Dienste). Der technische Support von Microsoft kann nicht für Konfigurationen in Anspruch genommen werden, die nicht zertifizierte Anbieter verwenden. Wenn Sie gegenwärtig einen Internetdienstanbieter nutzen, der nicht für SIP-Trunking zertifiziert ist, können Sie diesen Anbieter weiterhin als ISP nutzen und sich für das SIP-Trunking für einen für Microsoft zertifizierten Anbieter entscheiden.</span><span class="sxs-lookup"><span data-stu-id="6d5c7-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

