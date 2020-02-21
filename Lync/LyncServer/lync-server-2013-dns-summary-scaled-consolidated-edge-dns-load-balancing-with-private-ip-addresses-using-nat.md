---
title: 'Lync Server 2013: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 158dfa2954f331b4dce2407cb3bbee223f8e78ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="7cf50-102">DNS-Zusammenfassung – skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cf50-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cf50-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7cf50-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7cf50-104">Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="7cf50-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="7cf50-105">Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cf50-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="7cf50-106">Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf50-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="7cf50-107">Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013 Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf50-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="7cf50-108">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich ist, wie sie in der Abbildung „Topologie mit einem einzelnen konsolidierten Edgeserver“ gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7cf50-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="7cf50-109">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013 Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7cf50-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="7cf50-110">Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten Datensätze nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7cf50-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="7cf50-111">Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter</span><span class="sxs-lookup"><span data-stu-id="7cf50-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="7cf50-112">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7cf50-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="7cf50-113">Beispielsweise zeigt das Standardgateway, wie im Szenario "skalierte konsolidierte Edgeserver" im [skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), auf die externe Firewall hin.</span><span class="sxs-lookup"><span data-stu-id="7cf50-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="7cf50-114">Sie können auf jedem Ihrer Edgeserver wie folgt zwei Netzwerkadapter konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="7cf50-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="7cf50-115">**Netzwerkadapter 1 - Knoten 1 (Interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="7cf50-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="7cf50-116">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="7cf50-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="7cf50-117">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="7cf50-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="7cf50-118">Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7cf50-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="7cf50-119">**Netzwerkadapter 1 - Knoten 2 (Interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="7cf50-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="7cf50-120">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.11.</span><span class="sxs-lookup"><span data-stu-id="7cf50-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="7cf50-121">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="7cf50-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="7cf50-122">Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7cf50-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="7cf50-123">**Netzwerkadapter 2 - Knoten 1 (Externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="7cf50-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="7cf50-124">Diesem Netzwerkadapter sind drei private IP-Adressen zugeordnet, z. B. "10.45.16.10" für den Zugriffsedge, "10.45.16.20" für Webkonferenzedge und "10.45.16.30" für AV-Edge.</span><span class="sxs-lookup"><span data-stu-id="7cf50-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7cf50-p104">Das Verwenden einer einzigen IP-Adresse für alle drei Edgedienst-Schnittstellen ist zwar möglich, wird jedoch nicht empfohlen. Dadurch werden zwar IP-Adressen gespart, es sind jedoch für jeden Dienst verschiedene Portnummern erforderlich. Die Standardportnummer ist "443/TCP"; durch Verwendung dieser Nummer wird sichergestellt, dass die meisten Remotefirewalls den Datenverkehr zulassen. Das Ändern der Portwerte zu (z. B.) "5061/TCP" für den Zugriffsedge, "444/TCP" für den Webkonferenzedge und "443/TCP" für den AV-Edge verursacht u. U. Probleme für Remotebenutzer, wenn eine Firewall, hinter der sie sich befinden, den Datenverkehr über "5061/TCP" und "444/TCP" nicht zulässt. Zudem wird die Fehlerbehebung durch drei verschiedene IP-Adressen vereinfacht, da das Filtern nach IP-Adresse möglich ist.</span><span class="sxs-lookup"><span data-stu-id="7cf50-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="7cf50-130">Die öffentliche IP-Adresse des Zugriffs-Edgeservers ist als primär, das Standardgateway ist auf den integrierten Router festgelegt (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="7cf50-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="7cf50-131">Private Webkonferenz- und A/V-Edge-IP-Adressen sind zusätzliche IP-Adressen im Abschnitt **Erweitert** der Eigenschaften von \*\* 	Internetprotokoll Version 4 (TCP/IPv4)\*\* und **Internetprotokoll Version 6 (TCP/IPv6)** der **Eigenschaften von LAN-Verbindung** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7cf50-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="7cf50-132">**Netzwerkadapter 2 - Knoten 2 (Externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="7cf50-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="7cf50-133">Diesem Netzwerkadapter sind drei private IP-Adressen zugeordnet, z. B. "10.45.16.11" für den Zugriffsedge, "10.45.16.21" für Webkonferenzedge und "10.45.16.31" für AV-Edge.</span><span class="sxs-lookup"><span data-stu-id="7cf50-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="7cf50-134">Die öffentliche IP-Adresse des Zugriffs-Edgeservers ist als primär, das Standardgateway ist auf den integrierten Router festgelegt (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="7cf50-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="7cf50-135">Private Webkonferenz- und A/V-Edge-IP-Adressen sind zusätzliche IP-Adressen im Abschnitt **Erweitert** der Eigenschaften von \*\* 	Internetprotokoll Version 4 (TCP/IPv4)\*\* und **Internetprotokoll Version 6 (TCP/IPv6)** der **Eigenschaften von LAN-Verbindung** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7cf50-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7cf50-136">Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="7cf50-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="7cf50-137">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cf50-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="7cf50-138">Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7cf50-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="7cf50-139">Erforderliche DNS-Einträge für eine skalierte konsolidierte Edgetopologie, DNS-Lastenausgleich mit privaten IP-Adressen und Verwendung der Netzwerkadressenübersetzung (NAT) (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="7cf50-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cf50-140">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="7cf50-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="7cf50-141">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="7cf50-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="7cf50-142">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="7cf50-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="7cf50-143">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="7cf50-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cf50-144">Externer DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="7cf50-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7cf50-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-146">131.107.155.10 und 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="7cf50-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="7cf50-147">Externe Zugriffs-Edgeschnittstelle (Contoso); ggf. für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen</span><span class="sxs-lookup"><span data-stu-id="7cf50-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cf50-148">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="7cf50-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7cf50-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-150">131.107.155.20 und 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="7cf50-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="7cf50-151">Externe Webkonferenz-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cf50-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cf50-152">Externes DNS/A</span><span class="sxs-lookup"><span data-stu-id="7cf50-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7cf50-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-154">131.107.155.30 und 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="7cf50-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="7cf50-155">Externe Schnittstelle des A/V-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="7cf50-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cf50-156">Externe DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="7cf50-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="7cf50-157">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7cf50-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-159">Externe Schnittstelle des Zugriffs-Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="7cf50-159">Access Edge external interface.</span></span> <span data-ttu-id="7cf50-160">Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7cf50-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="7cf50-161">Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="7cf50-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cf50-162">Externes DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="7cf50-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="7cf50-163">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7cf50-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-p107">Externe SIP-Zugriffs-Edgeschnittstelle. Erforderlich für die automatische DNS-Suche von Verbundpartnern, bezeichnet als "Zugelassene SIP-Domäne" (in Vorgängerversionen als erweiterter Verbund bezeichnet). Wiederholen Sie den Vorgang ggf. für alle internen SIP-Domänen mit für Lync aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="7cf50-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cf50-168">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="7cf50-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7cf50-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7cf50-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7cf50-170">172.25.33.10 und 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="7cf50-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="7cf50-171">Interne Schnittstelle des konsolidierten Edgeservers</span><span class="sxs-lookup"><span data-stu-id="7cf50-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="7cf50-172">Für den Verbund erforderliche Einträge</span><span class="sxs-lookup"><span data-stu-id="7cf50-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cf50-173">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="7cf50-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="7cf50-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="7cf50-174">FQDN</span></span></th>
<th><span data-ttu-id="7cf50-175">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="7cf50-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="7cf50-176">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="7cf50-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cf50-177">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="7cf50-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="7cf50-178">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7cf50-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-180">Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche Ihres Partnerverbungs nach anderen Verbundpartnern, bezeichnet als „Zugelassene SIP-Domänen“ (in Vorgängerversionen als erweiterter Verbund bezeichnet). Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="7cf50-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="7cf50-181">Dieser SRV-Eintrag ist für die Mobilitätsfunktion und die Pushbenachrichtigung für Clearinghouse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7cf50-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="7cf50-182">DNS-Zusammenfassung – Verbindung mit öffentlichen Instant Messaging-Diensten (PIC)</span><span class="sxs-lookup"><span data-stu-id="7cf50-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cf50-183">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="7cf50-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="7cf50-184">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="7cf50-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="7cf50-185">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="7cf50-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="7cf50-186">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="7cf50-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cf50-187">Externer DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="7cf50-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7cf50-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-189">Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cf50-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="7cf50-190">Externe Schnittstelle des Zugriffs-Edgeservers (Contoso); bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen</span><span class="sxs-lookup"><span data-stu-id="7cf50-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="7cf50-191">DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="7cf50-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cf50-192">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="7cf50-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="7cf50-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="7cf50-193">FQDN</span></span></th>
<th><span data-ttu-id="7cf50-194">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="7cf50-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="7cf50-195">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="7cf50-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cf50-196">Externe DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="7cf50-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="7cf50-197">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="7cf50-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7cf50-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7cf50-199">Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie diese Schritte bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf den Lync-aktivierter Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7cf50-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="7cf50-200">Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7cf50-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="7cf50-201">Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="7cf50-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cf50-202">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="7cf50-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="7cf50-203">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="7cf50-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="7cf50-204">IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</span><span class="sxs-lookup"><span data-stu-id="7cf50-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="7cf50-205">Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten.</span><span class="sxs-lookup"><span data-stu-id="7cf50-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="7cf50-206">Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="7cf50-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

