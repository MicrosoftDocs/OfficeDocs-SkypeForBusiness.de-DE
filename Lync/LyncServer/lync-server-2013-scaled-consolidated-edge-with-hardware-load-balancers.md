---
title: 'Lync Server 2013: skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleich'
description: 'Lync Server 2013: skalierter konsolidierter Edgeserver mit Hardwaregerät zum Lastenausgleich.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 808c03e0d6f2836719599c6cad9ec83e1c96b207
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547651"
---
# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="13090-103">Skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleichssystemen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13090-103">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13090-104">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="13090-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="13090-105">In der Edgepool Topologie werden zwei oder mehr Edgeserver als Pool mit Lastenausgleich im Umkreisnetzwerk des Datencenters bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="13090-105">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="13090-106">Der Hardware Lastenausgleich wird für den Datenverkehr sowohl für die externe als auch für die interne Edgeserver Schnittstellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="13090-106">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="13090-107">Wenn Ihre Organisation Unterstützung für mehr als 15.000 Zugriffs-Edgedienst-Clientverbindungen, 1.000 Active Webkonferenz-Edgedienst-Clientverbindungen oder 500 gleichzeitige A/V-Edgedienst Sitzungen und hohe Verfügbarkeit der Edgeserver wichtig ist, bietet diese Topologie die Vorteile von Skalierbarkeit und Failover-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="13090-107">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="13090-108">In der Abbildung werden Directors, eine optionale Serverrolle, die im internen Netzwerk zwischen den Edgeserver und ihren Front-End-Pools oder-Servern bereitgestellt wird, nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="13090-108">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="13090-109">.</span><span class="sxs-lookup"><span data-stu-id="13090-109">.</span></span> <span data-ttu-id="13090-110">Ausführliche Informationen zur Topologie für Directors finden Sie unter [für den Director in lync Server 2013 erforderliche Komponenten](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="13090-110">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13090-111">Die Abbildung dient zur Orientierung und als Beispiel für die IP-Adressierung, soll aber nicht den tatsächlichen Kommunikationsfluss mit dem entsprechenden ein- und ausgehenden Datenverkehr darstellen.</span><span class="sxs-lookup"><span data-stu-id="13090-111">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="13090-112">Diese Abbildung stellt eine Übersicht über den möglichen Datenverkehr dar.</span><span class="sxs-lookup"><span data-stu-id="13090-112">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="13090-113">Details des eingehenden (zu den Überwachungsports) und ausgehenden (zu den Zielservern oder Clients) Datenverkehrsflusses sind im Portübersichtsdiagramm in jedem Szenario dargestellt.</span><span class="sxs-lookup"><span data-stu-id="13090-113">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="13090-114">TCP 443 ist beispielsweise nur eingehend (nur für den Edgeserver oder Reverseproxy) und stellt nur einen bidirektionalen Fluss aus einer Protokoll-(TCP-) Perspektive dar.</span><span class="sxs-lookup"><span data-stu-id="13090-114">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="13090-115">Darüber hinaus ist in der Abbildung dargestellt, wie sich der Datenverkehr ändert, wenn die Netzwerkadressenübersetzung (Network Address Translation, NAT) ausgeführt wird (die Zieladresse wird für eingehenden Datenverkehr geändert, die Quelladresse wird für ausgehenden Datenverkehr geändert).</span><span class="sxs-lookup"><span data-stu-id="13090-115">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="13090-116">Beispiele für externe und interne Firewalls sowie Serverschnittstelen dienen nur zu Referenzzwecken.</span><span class="sxs-lookup"><span data-stu-id="13090-116">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="13090-117">Schließlich sind soweit zutreffend Beispiele für Standardgateways und Routenbeziehungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="13090-117">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="13090-118">Beachten Sie auch, dass das Diagramm die <EM>. com</EM> -DNS-Zone verwendet, um die externe DNS-Zone für Reverse-Proxy-und Edgeserver darzustellen, und die <EM>.net</EM> -DNS-Zone auf die interne DNS-Zone verweist.</span><span class="sxs-lookup"><span data-stu-id="13090-118">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="13090-119">Neu in Microsoft lync Server 2013 ist die Unterstützung der IPv6-Adressierung.</span><span class="sxs-lookup"><span data-stu-id="13090-119">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="13090-120">Genauso wie bei IPv4-Adressierung müssen auch IPv6-Adressen so zugewiesen werden, dass sie zu Ihrem zugeordneten IPv6-Adressraum gehören.</span><span class="sxs-lookup"><span data-stu-id="13090-120">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="13090-121">Die in diesem Thema verwendeten IPv6-Adressen dienen nur zu Beispielzwecken.</span><span class="sxs-lookup"><span data-stu-id="13090-121">The addresses in this topic are for example only.</span></span> <span data-ttu-id="13090-122">Sie müssen sich richtige IPv6-Adressen besorgen, die in Ihrer Bereitstellung funktionieren, den korrekten Raum zuweisen und mit interner und externer Adressierung zusammenarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="13090-122">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="13090-123">Windows Server stellt ein Feature bereit, das für den IPv6-Übergangs Betrieb und die IPv4-zu-IPv6-Kommunikation mit dem Namen *Dual Stack*wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="13090-123">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="13090-124">Der Dual-Stack ist ein separater und jeweils eigener Netzwerkstapel für IPv4 und für IPv6.</span><span class="sxs-lookup"><span data-stu-id="13090-124">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="13090-125">Der Dual-Stack ermöglicht es Ihnen, sowohl IPv4- als auch IPv6-Adressen parallel zuzuweisen, und er ermöglicht es dem Server, mit anderen Hosts und Clients gemäß deren Anforderungen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="13090-125">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="13090-126">Typische Adresstypen, die Sie für die IPv6-Adressierung verwenden werden, sind die globalen IPv6-Adressen (vergleichbar mit öffentlichen IPv4-Adressen), eindeutige lokale IPv6-Adressen (vergleichbar mit den privaten IPv4-Adressbereichen) und lokale IPv6-Linkadressen (ähnlich wie bei automatischen privaten IP-Adressen in Windows Server für IPv4).</span><span class="sxs-lookup"><span data-stu-id="13090-126">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="13090-127">Es existieren NAT-Technologien für IPv6, die die Netzwerkadressübersetzung von IPv6 nach IPv4 (im Allgmeinen als NAT64 bezeichnet) und von IPv6 nach IPv6 (im Allgemeinen als NAT66 bezeichnet) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="13090-127">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="13090-128">Das vorhanden sein von NAT-Technologien bedeutet, dass die fünf Szenarien, die für lync Server Edgeserver angezeigt werden, noch gültig sind.</span><span class="sxs-lookup"><span data-stu-id="13090-128">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="13090-129">IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internet Anbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server-Ebene und auf der lync Server 2013 Ebene zuweisen, erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="13090-129">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="13090-130">Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie unter den Links am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="13090-130">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="13090-131">**Konfiguration des Hardwaregeräts zum Lastenausgleich**</span><span class="sxs-lookup"><span data-stu-id="13090-131">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="13090-132">Ausführliche Informationen finden Sie im Abschnitt "Anforderungen an das Hardware Gerät zum Lastenausgleich für A/V-Edge" in Komponenten, die [für den Zugriff durch externe Benutzer in lync Server 2013 erforderlich](lync-server-2013-components-required-for-external-user-access.md)sind.</span><span class="sxs-lookup"><span data-stu-id="13090-132">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="13090-133">**Skalierte konsolidierte Edgetopologie (Hardwarelastenausgleich)**</span><span class="sxs-lookup"><span data-stu-id="13090-133">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="13090-134">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="13090-134">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="13090-135">Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) verwenden, müssen Sie der internen Edgeserver-Schnittstelle weiterhin IPv4-Adressen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="13090-135">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="13090-136">Für CAC werden IPv4-Adressen verwendet, und sie müssen für den Betrieb verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="13090-136">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13090-137">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="13090-137">In This Section</span></span>

  - [<span data-ttu-id="13090-138">Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13090-138">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="13090-139">Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13090-139">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="13090-140">DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13090-140">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13090-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13090-141">See Also</span></span>


[<span data-ttu-id="13090-142">IP-Adressierungs Architektur der Version 6</span><span class="sxs-lookup"><span data-stu-id="13090-142">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="13090-143">Globales Unicast-Adress Format in IPv6</span><span class="sxs-lookup"><span data-stu-id="13090-143">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="13090-144">Eindeutige lokale IPv6-Unicast-Adressen</span><span class="sxs-lookup"><span data-stu-id="13090-144">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

