---
title: 'Lync Server 2013: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen'
description: 'Lync Server 2013: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca88043b76365508ea00ca840e9a9fdcb0e270be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558787"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="4cdbd-103">DNS-Zusammenfassung – skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cdbd-103">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cdbd-104">_**Letztes Änderungsstand des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="4cdbd-104">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="4cdbd-105">Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="4cdbd-106">Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="4cdbd-107">Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cdbd-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="4cdbd-108">Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013 Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cdbd-108">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="4cdbd-109">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich ist, wie sie in der Abbildung „Topologie mit einem einzelnen konsolidierten Edgeserver“ gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-109">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="4cdbd-110">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013 Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-110">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="4cdbd-111">Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten Datensätze nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="4cdbd-112">Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter</span><span class="sxs-lookup"><span data-stu-id="4cdbd-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="4cdbd-113">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="4cdbd-114">Beispielsweise zeigt das Standardgateway, wie im Szenario "skalierte konsolidierte Edgeserver" im [skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , auf die externe Firewall hin.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-114">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="4cdbd-115">Sie können auf jedem Ihrer Edgeserver wie folgt zwei Netzwerkadapter konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4cdbd-115">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="4cdbd-116">**Netzwerkadapter 1 - Knoten 1 (Interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="4cdbd-116">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="4cdbd-117">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="4cdbd-118">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="4cdbd-119">Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="4cdbd-120">**Netzwerkadapter 1 - Knoten 2 (Interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="4cdbd-120">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="4cdbd-121">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.11.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-121">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="4cdbd-122">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-122">No default gateway is defined.</span></span>
    
    <span data-ttu-id="4cdbd-123">Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-123">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="4cdbd-124">**Netzwerkadapter 2 - Knoten 1 (Externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="4cdbd-124">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="4cdbd-125">Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Zugriffs-Edgedienst, 131.107.155.20 für Webkonferenz-Edgedienst, 131.107.155.30 für A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-125">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="4cdbd-126">Die Zugriffs-Edgedienst öffentliche IP-Adresse ist primär, wobei das Standardgateway auf den öffentlichen Router (131.107.155.1) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-126">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="4cdbd-127">Webkonferenz-Edgedienst und A/V-Edgedienst private IP-Adressen sind zusätzliche IP-Adressen im Abschnitt **erweitert** der Eigenschaften von **Internetprotokoll Version 4 (TCP/IPv4)** und **Internetprotokoll Version 6 (TCP/IPv6)** der Eigenschaften für die **LAN-Verbindung** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-127">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4cdbd-128">Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-128">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="4cdbd-129">Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-129">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="4cdbd-130">Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-130">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="4cdbd-131">Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für die Zugriffs-Edgedienst, 444/TCP für die Webkonferenz-Edgedienst und 443/TCP für die A/V-Edgedienst kann Probleme für Remotebenutzer verursachen, bei denen eine Firewall, hinter der Sie sich befinden, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-131">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="4cdbd-132">Darüber hinaus wird durch drei eindeutige IP-Adressen die Problembehandlung vereinfacht, da nach der IP-Adresse gefiltert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-132">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="4cdbd-133">**Netzwerkadapter 2 – Knoten 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="4cdbd-133">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="4cdbd-134">Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 131.107.155.11 für Zugriffs-Edgedienst, 131.107.155.21 für Webkonferenz-Edgedienst, 131.107.155.31 für A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-134">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="4cdbd-135">Die Zugriffs-Edgedienst öffentliche IP-Adresse ist primär, wobei das Standardgateway auf den öffentlichen Router (131.107.155.1) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-135">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="4cdbd-136">Webkonferenz-Edgedienst und A/V-Edgedienst private IP-Adressen sind zusätzliche IP-Adressen im Abschnitt **erweitert** der Eigenschaften von **Internetprotokoll Version 4 (TCP/IPv4)** und **Internetprotokoll Version 6 (TCP/IPv6)** der Eigenschaften für die **LAN-Verbindung** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-136">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4cdbd-137">Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-137">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="4cdbd-138">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-138">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="4cdbd-139">Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-139">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="4cdbd-140">Erforderliche DNS-Einträge für einen skalierten konsolidierten Edge, DNS-Lastenausgleich mit öffentlichen IP-Adressen (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="4cdbd-140">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cdbd-141">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="4cdbd-141">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4cdbd-142">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="4cdbd-142">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="4cdbd-143">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="4cdbd-143">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="4cdbd-144">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="4cdbd-144">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cdbd-145">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="4cdbd-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-146">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-146">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-147">131.107.155.10 und 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="4cdbd-147">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-148">Zugriffs-Edgedienst externe Schnittstelle (Contoso) bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern wiederholen</span><span class="sxs-lookup"><span data-stu-id="4cdbd-148">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cdbd-149">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="4cdbd-149">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-150">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-150">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-151">131.107.155.20 und 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="4cdbd-151">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-152">Webkonferenz-Edgedienst externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cdbd-152">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cdbd-153">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="4cdbd-153">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-154">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-154">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-155">131.107.155.30 und 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="4cdbd-155">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-156">A/V-Edgedienst externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cdbd-156">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cdbd-157">Externe DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="4cdbd-157">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-158">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-158">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-160">Zugriffs-Edgedienst externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-160">Access Edge service external interface.</span></span> <span data-ttu-id="4cdbd-161">Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-161">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="4cdbd-162">Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-162">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cdbd-163">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="4cdbd-163">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-164">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-164">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-166">Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung von Verbundpartnern erforderlich ist, die als "zugelassene SIP-Domäne" bezeichnet werden (als erweiterter Verbund in früheren Versionen bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="4cdbd-166">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="4cdbd-167">Wiederholen bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern</span><span class="sxs-lookup"><span data-stu-id="4cdbd-167">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cdbd-168">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="4cdbd-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4cdbd-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-170">172.25.33.10 und 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="4cdbd-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-171">Interne Schnittstelle des konsolidierten Edgeservers</span><span class="sxs-lookup"><span data-stu-id="4cdbd-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="4cdbd-172">Für den Verbund erforderliche Einträge</span><span class="sxs-lookup"><span data-stu-id="4cdbd-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cdbd-173">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="4cdbd-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4cdbd-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="4cdbd-174">FQDN</span></span></th>
<th><span data-ttu-id="4cdbd-175">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="4cdbd-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="4cdbd-176">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="4cdbd-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cdbd-177">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="4cdbd-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-178">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-180">SIP Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung ihres Verbunds für andere potenzielle Verbundpartner erforderlich ist, und wird als "zugelassene SIP-Domänen" bezeichnet ("Enhanced Federation" in früheren Versionen genannt).</span><span class="sxs-lookup"><span data-stu-id="4cdbd-180">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="4cdbd-181">Wiederholen Sie diese Schritte bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push Notification-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-181">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4cdbd-182">DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="4cdbd-182">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cdbd-183">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="4cdbd-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4cdbd-184">FQDN</span><span class="sxs-lookup"><span data-stu-id="4cdbd-184">FQDN</span></span></th>
<th><span data-ttu-id="4cdbd-185">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="4cdbd-185">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="4cdbd-186">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="4cdbd-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cdbd-187">Externe DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="4cdbd-187">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-188">_xmpp-Server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-188">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-189">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4cdbd-189">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-190">Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie den Vorgang bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder eine auf den lync-aktivierten Benutzer angewendete Benutzerrichtlinie zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-190">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="4cdbd-191">Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-191">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="4cdbd-192">Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="4cdbd-192">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cdbd-193">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="4cdbd-193">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-194">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="4cdbd-194">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-195">IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</span><span class="sxs-lookup"><span data-stu-id="4cdbd-195">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="4cdbd-196">Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten.</span><span class="sxs-lookup"><span data-stu-id="4cdbd-196">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="4cdbd-197">Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="4cdbd-197">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

