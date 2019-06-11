---
title: 'Lync Server 2013: Auswählen einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="35b60-102">Auswählen einer Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35b60-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="35b60-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="35b60-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="35b60-104">Wenn Sie eine Topologie auswählen, können Sie eine der folgenden unterstützten Topologie-Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="35b60-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="35b60-105">Wenn Sie über Erfahrungen mit Microsoft lync Server 2010 verfügen, finden Sie, sofern nicht anders angegeben, die Anleitungen hier weitgehend unverändert.</span><span class="sxs-lookup"><span data-stu-id="35b60-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="35b60-106">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35b60-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="35b60-107">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35b60-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="35b60-108">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35b60-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="35b60-109">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35b60-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="35b60-110">Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35b60-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="35b60-111">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35b60-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="35b60-112">Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="35b60-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="35b60-113">In der folgenden Tabelle sind die Funktionen zusammengefasst, die mit den unterstützten Microsoft lync Server 2013-Topologien verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="35b60-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="35b60-114">Die Spaltenüberschriften geben die Funktionalität an, die für eine bestimmte Edge-Konfigurationsoption verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="35b60-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="35b60-115">Wenn Sie beispielsweise die Option skalierten Edge (DNS Load Balanced) verwenden, können Sie sehen, dass Sie eine hohe Verfügbarkeit unterstützt, nicht routingfähige private IP-Adressen (mit NAT) oder routingfähige öffentliche IP-Adressen verwenden, die den Edge-externen Schnittstellen zugewiesen sind, und die Kosten reduzieren, da eine das Hardware-Lastenausgleichsmodul ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35b60-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="35b60-116">Edge-Failover-Szenarien, die beim DNS-Lastenausgleich unterstützt werden, sind lync-zu-Punkt-Sitzungen, lync-Konferenzsitzungen, lync-zu-PSTN-Sitzungen und Office 365.</span><span class="sxs-lookup"><span data-stu-id="35b60-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="35b60-117">Edge-Failover-Szenarien, die nicht vom DNS-Lastenausgleich profitieren, sind Failover für Remotebenutzer Exchange Unified Messaging (um) (vor Exchange 2010 SP1), öffentliche Instant Messaging (im)-Konnektivität und Verbund mit Servern, auf denen Office Communications ausgeführt wird. Server.</span><span class="sxs-lookup"><span data-stu-id="35b60-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="35b60-118">Zusammenfassung der Optionen für die Edgeserver-Topologie</span><span class="sxs-lookup"><span data-stu-id="35b60-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="35b60-119">Topologie</span><span class="sxs-lookup"><span data-stu-id="35b60-119">Topology</span></span></th>
<th><span data-ttu-id="35b60-120">Hochverfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="35b60-120">High availability</span></span></th>
<th><span data-ttu-id="35b60-121">Zusätzliche DNS-A-Einträge für externen Edgeserver im Edge-Pool erforderlich</span><span class="sxs-lookup"><span data-stu-id="35b60-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="35b60-122">Edge-Failover für lync-zu-lync-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="35b60-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="35b60-123">Edge-Failover für lync-zu-lync-EUM/PIC/OCS-Verbund Sitzungen</span><span class="sxs-lookup"><span data-stu-id="35b60-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35b60-124">Single Edge mit NAT</span><span class="sxs-lookup"><span data-stu-id="35b60-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="35b60-125">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-125">No</span></span></p></td>
<td><p><span data-ttu-id="35b60-126">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-126">No</span></span></p></td>
<td><p><span data-ttu-id="35b60-127">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-127">No</span></span></p></td>
<td><p><span data-ttu-id="35b60-128">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b60-129">Single Edge mit öffentlicher IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="35b60-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="35b60-130">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-130">No</span></span></p></td>
<td><p><span data-ttu-id="35b60-131">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-131">No</span></span></p></td>
<td><p><span data-ttu-id="35b60-132">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-132">No</span></span></p></td>
<td><p><span data-ttu-id="35b60-133">Nein</span><span class="sxs-lookup"><span data-stu-id="35b60-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b60-134">Skalierte Kante (DNS Load Balanced) mithilfe von NAT</span><span class="sxs-lookup"><span data-stu-id="35b60-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="35b60-135">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="35b60-136">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="35b60-137">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b60-138">Skalierter Edge (DNS Load Balanced) mit öffentlicher IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="35b60-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="35b60-139">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="35b60-140">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="35b60-141">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b60-142">Lastenausgleich für skalierte Edge-Hardware</span><span class="sxs-lookup"><span data-stu-id="35b60-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="35b60-143">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="35b60-144">Nein (ein DNS A-Eintrag pro VIP)</span><span class="sxs-lookup"><span data-stu-id="35b60-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="35b60-145">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="35b60-146">Ja</span><span class="sxs-lookup"><span data-stu-id="35b60-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="35b60-147">**\*** Failover für öffentliche Instant Messaging (im)-Konnektivität und Föderation mit Servern, auf denen Office Communications Server ausgeführt wird, ist im DNS-Lastenausgleich nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35b60-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="35b60-148">Exchange um-Failover (Remotebenutzer) mithilfe des DNS-Lastenausgleichs erfordert Exchange Server 2010 SP1 oder höher.</span><span class="sxs-lookup"><span data-stu-id="35b60-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="35b60-149">Topologien mit einem Edge und einem skalierten Edge (DNS Load Balanced) können verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="35b60-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="35b60-150">Routingfähige öffentliche IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="35b60-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="35b60-151">Nicht routingfähige private IP-Adresse, wenn eine symmetrische Netzwerkadressübersetzung (Network Address Translation, NAT) verwendet wird</span><span class="sxs-lookup"><span data-stu-id="35b60-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="35b60-152">Wenn Sie die öffentliche IP-Adresse oder private IP-Adresse mit NAT verwenden, verwenden Sie weiterhin die gleiche Anzahl von IP-Adressen basierend auf Ihrer Konfigurationswahl im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="35b60-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="35b60-153">Sie können den Edgeserver so konfigurieren, dass eine einzelne IP-Adresse mit unterschiedlichen Ports pro Dienst verwendet wird, oder Sie können unterschiedliche IP-Adressen pro Dienst verwenden, aber denselben Port verwenden (standardmäßig TCP 443).</span><span class="sxs-lookup"><span data-stu-id="35b60-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="35b60-154">Wenn Sie sich entschließen, nicht routingfähige private IP-Adressen mit NAT zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="35b60-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="35b60-155">Sie müssen routingfähige private IP-Adressen für alle drei externen Schnittstellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="35b60-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="35b60-156">Sie müssen symmetrische NAT für eingehenden und ausgehenden Datenverkehr konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="35b60-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="35b60-157">Die Topologie für skalierte Kanten (Hardwarelastenausgleich) muss öffentliche IP-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="35b60-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="35b60-158">Lync Server 2013 unterstützt das Platzieren von Access-, Webkonferenz-und a/V-Edge-externen Schnittstellen hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) sowohl für einzelne als auch für skalierte konsolidierte Edge-Server-Topologien ausführt.</span><span class="sxs-lookup"><span data-stu-id="35b60-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="35b60-159">Die Verwendung von NAT für alle externen Edge-Schnittstellen erfordert die Verwendung des DNS-Lastenausgleichs.</span><span class="sxs-lookup"><span data-stu-id="35b60-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="35b60-160">Im Vergleich zur Verwendung von Hardwarelastenausgleichs können Sie mithilfe des DNS-Lastenausgleichs ohne NAT die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edge-Pool reduzieren, wie in der folgenden Liste beschrieben:</span><span class="sxs-lookup"><span data-stu-id="35b60-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="35b60-161">Der von lync Server 2013 skalierte konsolidierte Edge (DNS Load Balanced) erfordert drei öffentliche IP-Adressen für jeden Edgeserver in einem Edge-Pool.</span><span class="sxs-lookup"><span data-stu-id="35b60-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="35b60-162">Der von lync Server 2013 skalierte konsolidierte Edge (Hardwarelastenausgleich) erfordert drei öffentliche IP-Adressen für virtuelle IP-Adressen des Lastenausgleichs (eine einmalige Anforderung, die nicht inkrementiert, wenn dem Pool weitere Edgeserver hinzugefügt werden) sowie drei öffentliche IP-Adressen pro Edgeserver in einem Pool.</span><span class="sxs-lookup"><span data-stu-id="35b60-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="35b60-163">IP-Adressen Anforderungen für den skalierten konsolidierten Edge (IP-Adresse pro Rolle)</span><span class="sxs-lookup"><span data-stu-id="35b60-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35b60-164">Anzahl der Edgeserver pro Pool</span><span class="sxs-lookup"><span data-stu-id="35b60-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="35b60-165">Anzahl der erforderlichen IP-Adressen lync Server 2013 (DNS Load Balanced)</span><span class="sxs-lookup"><span data-stu-id="35b60-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="35b60-166">Anzahl der erforderlichen IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="35b60-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35b60-167">2</span><span class="sxs-lookup"><span data-stu-id="35b60-167">2</span></span></p></td>
<td><p><span data-ttu-id="35b60-168">6</span><span class="sxs-lookup"><span data-stu-id="35b60-168">6</span></span></p></td>
<td><p><span data-ttu-id="35b60-169">3 (1 pro VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="35b60-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b60-170">3</span><span class="sxs-lookup"><span data-stu-id="35b60-170">3</span></span></p></td>
<td><p><span data-ttu-id="35b60-171">9</span><span class="sxs-lookup"><span data-stu-id="35b60-171">9</span></span></p></td>
<td><p><span data-ttu-id="35b60-172">3 (1 pro VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="35b60-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b60-173">4</span><span class="sxs-lookup"><span data-stu-id="35b60-173">4</span></span></p></td>
<td><p><span data-ttu-id="35b60-174">12</span><span class="sxs-lookup"><span data-stu-id="35b60-174">12</span></span></p></td>
<td><p><span data-ttu-id="35b60-175">3 (1 pro VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="35b60-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b60-176">5</span><span class="sxs-lookup"><span data-stu-id="35b60-176">5</span></span></p></td>
<td><p><span data-ttu-id="35b60-177">15</span><span class="sxs-lookup"><span data-stu-id="35b60-177">15</span></span></p></td>
<td><p><span data-ttu-id="35b60-178">3 (1 pro VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="35b60-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="35b60-179">IP-Adressen Anforderungen für skalierten konsolidierten Edge (einzelne IP-Adresse für alle Rollen)</span><span class="sxs-lookup"><span data-stu-id="35b60-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35b60-180">Anzahl der Edgeserver pro Pool</span><span class="sxs-lookup"><span data-stu-id="35b60-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="35b60-181">Anzahl der erforderlichen IP-Adressen lync Server 2013 (DNS Load Balanced)</span><span class="sxs-lookup"><span data-stu-id="35b60-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="35b60-182">Anzahl der erforderlichen IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="35b60-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35b60-183">2</span><span class="sxs-lookup"><span data-stu-id="35b60-183">2</span></span></p></td>
<td><p><span data-ttu-id="35b60-184">2</span><span class="sxs-lookup"><span data-stu-id="35b60-184">2</span></span></p></td>
<td><p><span data-ttu-id="35b60-185">1 (1 pro VIP) + 2</span><span class="sxs-lookup"><span data-stu-id="35b60-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b60-186">3</span><span class="sxs-lookup"><span data-stu-id="35b60-186">3</span></span></p></td>
<td><p><span data-ttu-id="35b60-187">3</span><span class="sxs-lookup"><span data-stu-id="35b60-187">3</span></span></p></td>
<td><p><span data-ttu-id="35b60-188">1 (1 pro VIP) + 3</span><span class="sxs-lookup"><span data-stu-id="35b60-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35b60-189">4</span><span class="sxs-lookup"><span data-stu-id="35b60-189">4</span></span></p></td>
<td><p><span data-ttu-id="35b60-190">4</span><span class="sxs-lookup"><span data-stu-id="35b60-190">4</span></span></p></td>
<td><p><span data-ttu-id="35b60-191">1 (1 pro VIP) + 4</span><span class="sxs-lookup"><span data-stu-id="35b60-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35b60-192">5</span><span class="sxs-lookup"><span data-stu-id="35b60-192">5</span></span></p></td>
<td><p><span data-ttu-id="35b60-193">5</span><span class="sxs-lookup"><span data-stu-id="35b60-193">5</span></span></p></td>
<td><p><span data-ttu-id="35b60-194">1 (1 pro VIP) + 5</span><span class="sxs-lookup"><span data-stu-id="35b60-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="35b60-195">Die primären Entscheidungspunkte für die Topologie-Auswahl sind hohe Verfügbarkeit und Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="35b60-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="35b60-196">Die Voraussetzung für hohe Verfügbarkeit kann die Entscheidung über den Lastenausgleich beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="35b60-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="35b60-197">**Höhere Verfügbarkeit**   Wenn Sie eine höhere Verfügbarkeit benötigen, müssen Sie mindestens zwei Edgeserver in einem Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="35b60-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="35b60-198">Ein einzelner Edge-Pool unterstützt bis zu zwölf Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="35b60-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="35b60-199">Wenn mehr Kapazität erforderlich ist, können Sie mehrere Edge-Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="35b60-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="35b60-200">In der Regel benötigen 10% einer bestimmten Nutzerbasis externen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="35b60-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="35b60-201">Mit dem Topology Builder können Sie bis zu zwanzig Edgeserver in einem einzigen Edge-Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="35b60-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="35b60-202">Die getestete und unterstützte maximale Anzahl von Edgeserver in einem Pool ist zwölf, und der Topologie-Generator, der eine Zahl größer als zwölf zulässt, sollte nicht als implizierte Unterstützung für mehr als zwölf Edgeserver in einem einzigen Edge-Pool ausgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="35b60-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="35b60-203">**Hardware Lastenausgleich**   Der Hardware Lastenausgleich wird für den Lastenausgleich von lync Server 2013-Edgeserver unterstützt, wenn öffentlich routingfähige IP-Adressen für die externen Edge-Schnittstellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35b60-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="35b60-204">Diese Vorgehensweise wird beispielsweise in Situationen verwendet, in denen ein Failover für eine der folgenden Anwendungen erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="35b60-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="35b60-205">Verbindung mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="35b60-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="35b60-206">Föderation mit Unternehmen, auf denen Microsoft Office Communications Server 2007 oder Microsoft Office Communications Server 2007 R2 ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="35b60-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="35b60-207">Externer Zugriff auf Exchange 2007 Unified Messaging (um) oder Exchange 2010 um</span><span class="sxs-lookup"><span data-stu-id="35b60-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="35b60-208">Der DNS-Lastenausgleich für Exchange 2010 SP1 und höher wird für Exchange um unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35b60-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="35b60-209">Diese drei Anwendungen funktionieren weiterhin, sind aber nicht für den DNS-Lastenausgleich bekannt und stellen nur eine Verbindung mit dem ersten Edgeserver im Pool her.</span><span class="sxs-lookup"><span data-stu-id="35b60-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="35b60-210">Wenn dieser Server nicht verfügbar ist, schlägt die Verbindung fehl.</span><span class="sxs-lookup"><span data-stu-id="35b60-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="35b60-211">Wenn beispielsweise mehrere Edgeserver in einem Pool bereitgestellt werden, um die Auslastung des Federated-Datenverkehrs zu behandeln, erhält nur ein Zugriffsproxy tatsächlich Datenverkehr, während die anderen Server im Leerlauf sind.</span><span class="sxs-lookup"><span data-stu-id="35b60-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="35b60-212">Die Verwendung des DNS-Lastenausgleichs wird empfohlen, wenn Sie mit Unternehmen zusammenarbeiten, die lync Server 2010 und Microsoft Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="35b60-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="35b60-213">Beachten Sie, dass es erhebliche Auswirkungen auf die Leistung gibt, wenn die meisten ihrer Verbundpartner Office Communications Server 2007 oder Office Communications Server 2007 R2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="35b60-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="35b60-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="35b60-214"></span></span></div>

