---
title: Lync Server 2013 Anforderungen an die Netzwerkinfrastruktur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3571dba317998af4fe19f7d2dfd1677d3691f278
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="5633b-102">Anforderungen an die Netzwerkinfrastruktur für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5633b-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5633b-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5633b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5633b-104">Die Netzwerkadapterkarte jedes Servers in der lync Server 2013 Topologie muss mindestens 1 Gigabit pro Sekunde (Gbit/s) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5633b-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="5633b-105">Im Allgemeinen sollten Sie alle Serverrollen innerhalb der lync Server Topologie mit einer geringen Wartezeit und einer hohen Bandbreite für lokales Netzwerk (Local Area Network, LAN) verbinden.</span><span class="sxs-lookup"><span data-stu-id="5633b-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="5633b-106">Die Größe des LAN ist von der Größe der Topologie abhängig:</span><span class="sxs-lookup"><span data-stu-id="5633b-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="5633b-107">In Standard Edition-Topologien sollten sich die Server in einem Netzwerk befinden, das 1 Gbit/s-Ethernet oder eine gleichwertige unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5633b-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="5633b-108">In Front-End-Pool Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 Gbit/s unterstützt, insbesondere bei der Unterstützung von Audio/Video-Konferenzen und Anwendungsfreigaben (a/V).</span><span class="sxs-lookup"><span data-stu-id="5633b-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="5633b-109">Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.</span><span class="sxs-lookup"><span data-stu-id="5633b-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="5633b-110">Netzwerkanforderungen für die Audio/Video-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="5633b-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="5633b-111">Die Netzwerkanforderungen für Audio/Video (a/V) in einer lync Server-Bereitstellung umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5633b-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="5633b-112">Wenn Sie einen einzelnen Edgeserver oder einen Edgepool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die externe Firewall als NAT konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5633b-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="5633b-113">Sie können keine interne Firewall mit NAT konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5633b-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="5633b-114">Ausführliche Informationen zu diesen Anforderungen finden Sie unter [bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="5633b-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5633b-115">Wenn Sie über eine Edgepool verfügen und einen Hardwaregerät zum Lastenausgleich verwenden, müssen Sie auf jedem Edgeserver öffentliche IP-Adressen verwenden, und Sie können NAT nicht für die Server oder den Pool an Ihrem NAT-Gerät verwenden (beispielsweise die Firewall oder ein anderes Infrastruktur Gerät, das NAT inbou ND-oder ausgehenden Datenverkehr).</span><span class="sxs-lookup"><span data-stu-id="5633b-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="5633b-116">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Summary – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013</A> in der Dokumentation zur Planung externer Benutzerzugriffe.</span><span class="sxs-lookup"><span data-stu-id="5633b-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="5633b-117">Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="5633b-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="5633b-118">Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5633b-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="5633b-119">Ausführliche Informationen finden Sie unter [IPSec Exceptions in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="5633b-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="5633b-120">Mit folgenden Maßnahmen können Sie optimale Medienqualität sicherstellen:</span><span class="sxs-lookup"><span data-stu-id="5633b-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="5633b-p105">Richten Sie die Netzwerkverbindungen so ein, dass sie bei Spitzenauslastung einen Durchsatz von 65 KBit/s pro Audiostream und 500 KBit/s pro Videostream (sofern aktiviert) unterstützen. Eine bidirektionale Audio- oder Videositzung umfasst zwei Datenströme.</span><span class="sxs-lookup"><span data-stu-id="5633b-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="5633b-123">Um unerwartete Spitzenwerte im Datenverkehr oberhalb dieser Ebene und eine erhöhte Nutzung im Laufe der Zeit zu bewältigen, können sich lync Server Medien Endpunkte an unterschiedliche Netzwerkbedingungen anpassen und Lasten von dreimal so hoch wie der Durchsatz (siehe vorheriger Absatz) für Audio und Video, während die Beibehaltung annehmbarer Qualität.</span><span class="sxs-lookup"><span data-stu-id="5633b-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="5633b-124">Gehen Sie jedoch nicht davon aus, dass diese Anpassungsfähigkeit ein unter bereitgestelltes Netzwerk unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5633b-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="5633b-125">In einem untergeordneten Netzwerk wird die Fähigkeit der lync Server Medien Endpunkte, dynamische unterschiedliche Netzwerkbedingungen (beispielsweise ein vorübergehender hoher Paketverlust) zu bewältigen, reduziert.</span><span class="sxs-lookup"><span data-stu-id="5633b-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="5633b-126">Für Netzwerkverbindungen, deren Bereitstellung sehr kostspielig und aufwendig ist, können Sie eine Dimensionierung für ein niedrigeres Datenverkehrsaufkommen erwägen.</span><span class="sxs-lookup"><span data-stu-id="5633b-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="5633b-127">In diesem Szenario lassen Sie die Elastizität der lync Server Medien Endpunkte den Unterschied zwischen dem Datenverkehrsvolumen und der Spitzen Daten verkehrsstufe absorbieren, wobei sich die Sprachqualität verringert.</span><span class="sxs-lookup"><span data-stu-id="5633b-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="5633b-128">Gleichzeitig verringert sich der Puffer, der andernfalls zum Auffangen plötzlicher Datenspitzen zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="5633b-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="5633b-129">Bei Verbindungen, die kurzfristig nicht ausreichend dimensioniert werden können (beispielsweise an einem Standort mit sehr schlechten WAN-Verbindungen) kann es ratsam sein, die Videofunktion für bestimmte Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5633b-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="5633b-130">Stellen Sie bei der Netzwerkbereitstellung sicher, dass bei Spitzenauslastung eine maximale End-to-End-Verzögerung (Latenz) von 150 ms auftritt.</span><span class="sxs-lookup"><span data-stu-id="5633b-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="5633b-131">Latenz ist die einzige Netzwerk Schädigung, die lync Server Medienkomponenten nicht verringern können, und es ist wichtig, die Schwachstellen zu finden und zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="5633b-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="5633b-132">Schließen Sie für Server, auf denen Antivirensoftware ausgeführt wird, alle Server mit lync Server in der Ausnahmeliste ein, um optimale Leistung und Audioqualität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="5633b-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="5633b-133">Netzwerkanforderungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="5633b-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="5633b-134">Die Bandbreite, die zum Herunterladen von Konferenz Inhalten vom Internet Information Services (IIS) Server verwendet wird, hängt von der Größe der hochgeladenen Inhalte ab.</span><span class="sxs-lookup"><span data-stu-id="5633b-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

