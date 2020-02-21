---
title: 'Lync Server 2013: Auswählen einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc30881da768d8dad9f952df37bdf1accdf091b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="211bc-102">Auswählen einer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211bc-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="211bc-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="211bc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="211bc-104">Bei der Auswahl einer Topologie können Sie eine der folgenden unterstützten Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="211bc-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="211bc-105">Wenn Sie Erfahrung mit Microsoft lync Server 2010 haben, werden Sie, sofern nicht anders angegeben, die Anleitung hier weitgehend unverändert finden.</span><span class="sxs-lookup"><span data-stu-id="211bc-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="211bc-106">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211bc-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="211bc-107">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211bc-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="211bc-108">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211bc-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="211bc-109">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211bc-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="211bc-110">Skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleichssystemen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="211bc-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="211bc-p101">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="211bc-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="211bc-113">In der folgenden Tabelle sind die Funktionen zusammengefasst, die mit den unterstützten Microsoft lync Server 2013 Topologien verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="211bc-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="211bc-114">Die Spaltenüberschriften geben die Funktionalität an, die für eine bestimmte Edgekonfigurationsoption zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="211bc-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="211bc-115">Beispielsweise ist für die skalierte Edgetopologie (DNS-Lastenausgleich) angegeben, dass sie hohe Verfügbarkeit unterstützt, nicht routingfähige private IP-Adressen (mit NAT) oder routingfähige öffentliche IP-Adressen verwenden kann, die externen Edgeschnittstellen zugewiesen sind, und die Kosten senkt, da kein Hardwaregerät zum Lastenausgleich erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="211bc-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="211bc-116">Unterstützte Edge-Failover-Szenarien bei DNS-Lastenausgleich sind lync-to-lync-Punkte-zu-Ort-Sitzungen, lync-Konferenzsitzungen, lync-zu-PSTN-Sitzungen und Office 365.</span><span class="sxs-lookup"><span data-stu-id="211bc-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="211bc-117">Edge-Failover-Szenarien, die nicht vom DNS-Lastenausgleich profitieren, sind Failover für Remotebenutzer Exchange Unified Messaging (um) (vor Exchange 2010 SP1), für die Verbindung mit öffentlichen Instant Messaging-Diensten (im) und für den Verbund mit Servern mit Office-Kommunikation. Server.</span><span class="sxs-lookup"><span data-stu-id="211bc-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="211bc-118">Zusammenfassung der Topologieoptionen für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="211bc-118">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="211bc-119">Topologie</span><span class="sxs-lookup"><span data-stu-id="211bc-119">Topology</span></span></th>
<th><span data-ttu-id="211bc-120">Hohe Verfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="211bc-120">High availability</span></span></th>
<th><span data-ttu-id="211bc-121">Zusätzliche DNS-A-Einträge für externe Edgeserver im Edgepool erforderlich</span><span class="sxs-lookup"><span data-stu-id="211bc-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="211bc-122">Edge-Failover für lync-zu-lync-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="211bc-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="211bc-123">Edge-Failover für lync-zu-lync-EUM/PIC/OCS-Verbund Sitzungen</span><span class="sxs-lookup"><span data-stu-id="211bc-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="211bc-124">Einzelner Edgeserver mit Netzwerkadressenübersetzung (Network Address Translation, NAT)</span><span class="sxs-lookup"><span data-stu-id="211bc-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="211bc-125">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-125">No</span></span></p></td>
<td><p><span data-ttu-id="211bc-126">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-126">No</span></span></p></td>
<td><p><span data-ttu-id="211bc-127">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-127">No</span></span></p></td>
<td><p><span data-ttu-id="211bc-128">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211bc-129">Einzelner Edgeserver mit öffentlicher IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="211bc-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="211bc-130">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-130">No</span></span></p></td>
<td><p><span data-ttu-id="211bc-131">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-131">No</span></span></p></td>
<td><p><span data-ttu-id="211bc-132">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-132">No</span></span></p></td>
<td><p><span data-ttu-id="211bc-133">Nein</span><span class="sxs-lookup"><span data-stu-id="211bc-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211bc-134">Skalierter Edgeserver (DNS-Lastenausgleich) mit NAT</span><span class="sxs-lookup"><span data-stu-id="211bc-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="211bc-135">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="211bc-136">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="211bc-137">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211bc-138">Skalierter Edgeserver (DNS-Lastenausgleich) mit öffentlicher IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="211bc-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="211bc-139">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="211bc-140">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="211bc-141">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211bc-142">Skalierter Edgeserver (Hardwarelastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="211bc-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="211bc-143">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="211bc-144">Nein (ein DNS A-Eintrag pro VIP)</span><span class="sxs-lookup"><span data-stu-id="211bc-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="211bc-145">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="211bc-146">Ja</span><span class="sxs-lookup"><span data-stu-id="211bc-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="211bc-147">**\*** Failover für die Verbindung mit öffentlichen Instant Messaging-Verbindungen und Verbund mit Servern mit Office Communications Server ist mit dem DNS-Lastenausgleich nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="211bc-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="211bc-148">Für Exchange um (Remotebenutzer)-Failover mithilfe des DNS-Lastenausgleichs ist Exchange Server 2010 SP1 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="211bc-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="211bc-149">Für Topologien mit einem einzelnen Edgeserver und mit einem skalierten Edgeserver (mit DNS-Lastenausgleich) kann Folgendes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="211bc-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="211bc-150">Routingfähige öffentliche IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="211bc-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="211bc-151">Nicht routingfähige private IP-Adresse, wenn die symmetrische Netzwerkadressübersetzung (NAT) verwendet wird</span><span class="sxs-lookup"><span data-stu-id="211bc-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="211bc-152">Wenn Sie die öffentliche IP-Adresse oder private IP-Adresse mit NAT verwenden, verwenden Sie weiterhin die gleiche Anzahl von IP-Adressen basierend auf Ihrer Konfigurationsoption im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="211bc-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="211bc-153">Sie können die Edgeserver so konfigurieren, dass eine einzelne IP-Adresse mit verschiedenen Ports pro Dienst verwendet wird, oder Sie verwenden unterschiedliche IP-Adressen pro Dienst, verwenden jedoch denselben Port (standardmäßig TCP 443).</span><span class="sxs-lookup"><span data-stu-id="211bc-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="211bc-154">Wenn Sie sich für die Verwendung von nicht routingfähigen privaten IP-Adressen mit NAT entscheiden:</span><span class="sxs-lookup"><span data-stu-id="211bc-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="211bc-155">Sie müssen routingfähige private IP-Adressen für alle drei externen Schnittstellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="211bc-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="211bc-156">Sie müssen ein symmetrisches NAT-Gerät für eingehenden und ausgehenden Datenverkehr konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="211bc-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="211bc-157">Für eine Topologie mit skaliertem Edgeserver (mit Hardwarelastenausgleich) müssen öffentliche IP-Adressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="211bc-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="211bc-158">Lync Server 2013 unterstützt das Platzieren von Zugriffs-, Webkonferenz-und a/V-Edge-Schnittstellen hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeserver Topologien ausführt.</span><span class="sxs-lookup"><span data-stu-id="211bc-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="211bc-p106">Bei Verwendung der Netzwerkadressenübersetzung für alle externen Edgeschnittstellen muss der DNS-Lastenausgleich implementiert werden. Im Vergleich mit der Verwendung eines Hardwarelastenausgleichs ermöglicht die Verwendung von DNS-Lastenausgleich die Reduzierung der Anzahl von öffentlichen IP-Adressen pro Edgeserver in einem Edgepool, wie in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="211bc-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="211bc-161">Lync Server 2013 skalierter konsolidierter Edgeserver (DNS-Lastenausgleich) erfordert drei öffentliche IP-Adressen für jeden Edgeserver in einem Edgepool.</span><span class="sxs-lookup"><span data-stu-id="211bc-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="211bc-162">Lync Server 2013 skalierten konsolidierten Edgeserver (Hardwarelastenausgleich) erfordert drei öffentliche IP-Adressen für die virtuellen IP-Adressen des Lastenausgleichs (eine einmalige Anforderung, die nicht erhöht wird, wenn dem Pool weitere Edgeserver hinzugefügt werden) sowie drei öffentliche IP-Adressen pro Edgeserver in einem Pool.</span><span class="sxs-lookup"><span data-stu-id="211bc-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="211bc-163">IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (IP-Adresse pro Rolle)</span><span class="sxs-lookup"><span data-stu-id="211bc-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="211bc-164">Anzahl von Edgeservern pro Pool</span><span class="sxs-lookup"><span data-stu-id="211bc-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="211bc-165">Anzahl erforderlicher IP-Adressen lync Server 2013 (DNS-Lastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="211bc-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="211bc-166">Anzahl erforderlicher IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="211bc-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="211bc-167">2</span><span class="sxs-lookup"><span data-stu-id="211bc-167">2</span></span></p></td>
<td><p><span data-ttu-id="211bc-168">6 </span><span class="sxs-lookup"><span data-stu-id="211bc-168">6</span></span></p></td>
<td><p><span data-ttu-id="211bc-169">3 (1 pro VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="211bc-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211bc-170">3</span><span class="sxs-lookup"><span data-stu-id="211bc-170">3</span></span></p></td>
<td><p><span data-ttu-id="211bc-171">9 </span><span class="sxs-lookup"><span data-stu-id="211bc-171">9</span></span></p></td>
<td><p><span data-ttu-id="211bc-172">3 (1 pro VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="211bc-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211bc-173">4</span><span class="sxs-lookup"><span data-stu-id="211bc-173">4</span></span></p></td>
<td><p><span data-ttu-id="211bc-174">12</span><span class="sxs-lookup"><span data-stu-id="211bc-174">12</span></span></p></td>
<td><p><span data-ttu-id="211bc-175">3 (1 pro VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="211bc-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211bc-176">5</span><span class="sxs-lookup"><span data-stu-id="211bc-176">5</span></span></p></td>
<td><p><span data-ttu-id="211bc-177">15 </span><span class="sxs-lookup"><span data-stu-id="211bc-177">15</span></span></p></td>
<td><p><span data-ttu-id="211bc-178">3 (1 pro VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="211bc-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="211bc-179">IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (eine IP-Adresse für alle Rollen)</span><span class="sxs-lookup"><span data-stu-id="211bc-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="211bc-180">Anzahl von Edgeservern pro Pool</span><span class="sxs-lookup"><span data-stu-id="211bc-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="211bc-181">Anzahl erforderlicher IP-Adressen lync Server 2013 (DNS-Lastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="211bc-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="211bc-182">Anzahl erforderlicher IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="211bc-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="211bc-183">2</span><span class="sxs-lookup"><span data-stu-id="211bc-183">2</span></span></p></td>
<td><p><span data-ttu-id="211bc-184">2</span><span class="sxs-lookup"><span data-stu-id="211bc-184">2</span></span></p></td>
<td><p><span data-ttu-id="211bc-185">1 (1 pro VIP) + 2</span><span class="sxs-lookup"><span data-stu-id="211bc-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211bc-186">3</span><span class="sxs-lookup"><span data-stu-id="211bc-186">3</span></span></p></td>
<td><p><span data-ttu-id="211bc-187">3</span><span class="sxs-lookup"><span data-stu-id="211bc-187">3</span></span></p></td>
<td><p><span data-ttu-id="211bc-188">1 (1 pro VIP) + 3</span><span class="sxs-lookup"><span data-stu-id="211bc-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="211bc-189">4</span><span class="sxs-lookup"><span data-stu-id="211bc-189">4</span></span></p></td>
<td><p><span data-ttu-id="211bc-190">4</span><span class="sxs-lookup"><span data-stu-id="211bc-190">4</span></span></p></td>
<td><p><span data-ttu-id="211bc-191">1 (1 pro VIP) + 4</span><span class="sxs-lookup"><span data-stu-id="211bc-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="211bc-192">5</span><span class="sxs-lookup"><span data-stu-id="211bc-192">5</span></span></p></td>
<td><p><span data-ttu-id="211bc-193">5</span><span class="sxs-lookup"><span data-stu-id="211bc-193">5</span></span></p></td>
<td><p><span data-ttu-id="211bc-194">1 (1 pro VIP) + 5</span><span class="sxs-lookup"><span data-stu-id="211bc-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="211bc-p107">Die wichtigsten Aspekte bei der Topologieauswahl sind hohe Verfügbarkeit und Lastenausgleich. Die Anforderung zur Bereitstellung hoher Verfügbarkeit kann sich auf die Entscheidung zum Lastenausgleich auswirken.</span><span class="sxs-lookup"><span data-stu-id="211bc-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="211bc-197">**Hohe Verfügbarkeit**   Wenn Sie hohe Verfügbarkeit benötigen, stellen Sie mindestens zwei Edgeserver in einem Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="211bc-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="211bc-198">Bei einem einzelnen Edgepool werden bis zu zwölf Edgeserver unterstützt.</span><span class="sxs-lookup"><span data-stu-id="211bc-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="211bc-199">Wenn mehr Kapazität benötigt wird, können Sie mehrere Edgepools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="211bc-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="211bc-200">Als allgemeine Regel benötigen 10% der Benutzer externen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="211bc-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="211bc-201">Mit dem Topologie-Generator können Sie bis zu zwanzig Edgeserver in einem einzigen Edgepool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="211bc-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="211bc-202">Die getestete und unterstützte maximale Anzahl von Edgeserver in einem Pool ist zwölf, und der Topologie-Generator, der eine Zahl größer als zwölf zulässt, sollte nicht als implizierte Unterstützung für mehr als zwölf Edgeserver in einem einzigen Edgepool ausgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="211bc-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="211bc-203">**Hardware Lastenausgleich**   Hardware Lastenausgleich wird für den Lastenausgleich lync Server 2013 Edgeserver unterstützt, wenn öffentlich routingfähige IP-Adressen für die externen Edge-Schnittstellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="211bc-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="211bc-204">Beispielsweise würden Sie diesen Ansatz in Situationen wählen, in denen ein Failover für eine der folgenden Anwendungen erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="211bc-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="211bc-205">Verbindung mit öffentlichen Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="211bc-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="211bc-206">Partnerverbund mit Microsoft Office Communications Server 2007 oder Microsoft Office Communications Server 2007 R2 ausführenden Unternehmen</span><span class="sxs-lookup"><span data-stu-id="211bc-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="211bc-207">Externer Zugriff auf Exchange 2007 Unified Messaging (UM) oder Exchange 2010 UM</span><span class="sxs-lookup"><span data-stu-id="211bc-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="211bc-208">Der DNS-Lastenausgleich für Exchange 2010 SP1 und neuer wird für Exchange um unterstützt.</span><span class="sxs-lookup"><span data-stu-id="211bc-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="211bc-p111">Diese drei Anwendungen funktionieren weiterhin, bieten jedoch keine Unterstützung für den DNS-Lastenausgleich und stellen nur eine Verbindung mit dem ersten Edgeserver im Pool her. Wenn dieser Server nicht verfügbar ist, kann keine Verbindung hergestellt werden. Wenn beispielsweise mehrere Edgeserver in einem Pool bereitgestellt werden, um den Datenverkehr für den Partnerverbund zu verarbeiten, empfängt nur ein Zugriffsproxy Daten, während die anderen Proxys sich im Leerlauf befinden.</span><span class="sxs-lookup"><span data-stu-id="211bc-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="211bc-212">Die Verwendung des DNS-Lastenausgleichs wird empfohlen, wenn Sie mit lync Server 2010 und Microsoft Office 365 einen Verbund mit Unternehmen durchsetzen.</span><span class="sxs-lookup"><span data-stu-id="211bc-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="211bc-213">Beachten Sie, dass erhebliche Leistungseinbußen zu verzeichnen sind, wenn die meisten Verbundpartner Office Communications Server 2007 oder Office Communications Server 2007 R2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="211bc-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="211bc-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="211bc-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

