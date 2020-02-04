---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT'
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
ms.openlocfilehash: 6a7836a8d9ce998a8de9185de7aeb12eb088f190
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="83f20-102">DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83f20-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83f20-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="83f20-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="83f20-104">Die Anforderungen für den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="83f20-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="83f20-105">Darüber hinaus sind viele Datensätze optional, je nachdem, wie Sie Clients mit lync 2013 konfigurieren und ob Sie die Föderation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="83f20-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="83f20-106">Details zu den DNS-Anforderungen von lync 2013 finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83f20-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="83f20-107">Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013-Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83f20-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="83f20-108">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die für die Unterstützung der einzelnen konsolidierten Edge-Topologie erforderlich sind, die in der einzelnen konsolidierten Edge-Topologie-Abbildung dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="83f20-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="83f20-109">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013-Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="83f20-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="83f20-110">Wenn Sie beabsichtigen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugehörigen Datensätze nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="83f20-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="83f20-111">Wichtig: Anforderungen des Edge-Server-Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="83f20-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="83f20-112">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass Ihre Edgeserver mindestens zwei Netzwerkadapter aufweisen und dass das Standardgateway nur auf dem Netzwerkadapter festgesetzt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="83f20-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="83f20-113">Beispielsweise würde das Standardgateway auf die externe Firewall verweisen, wie es in der Szenariogröße des skalierten konsolidierten Rands in der [skalierten konsolidierten Kante, dem DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="83f20-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="83f20-114">Sie können zwei Netzwerkadapter auf jedem Edgeserver wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="83f20-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="83f20-115">**Netzwerkadapter 1 – Knoten 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="83f20-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="83f20-116">Interne Schnittstelle mit zugewiesenem 172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="83f20-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="83f20-117">Es wurde kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="83f20-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="83f20-118">Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit lync Server 2013-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="83f20-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="83f20-119">**Netzwerkadapter 1 – Knoten 2 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="83f20-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="83f20-120">Interne Schnittstelle mit zugewiesenem 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="83f20-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="83f20-121">Es wurde kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="83f20-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="83f20-122">Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit lync Server 2013-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="83f20-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="83f20-123">**Netzwerkadapter 2 Knoten 1 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="83f20-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="83f20-124">Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 10.45.16.10 für Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 für AV Edge.</span><span class="sxs-lookup"><span data-stu-id="83f20-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83f20-125">Es ist jedoch möglich, eine einzige IP-Adresse für alle drei Edge-Service-Interfaces zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="83f20-125">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="83f20-126">Obwohl dadurch IP-Adressen gespeichert werden, sind für jeden Dienst unterschiedliche Portnummern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="83f20-126">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="83f20-127">Die Standardportnummer ist 443/TCP, wodurch sichergestellt wird, dass die meisten Remote Firewalls den Datenverkehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="83f20-127">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="83f20-128">Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für den Access-Edge, 444/TCP für den Webkonferenz-Edge und 443/TCP für den AV-Edge kann zu Problemen bei Remotebenutzern führen, bei denen eine Firewall, die Sie behindern, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="83f20-128">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="83f20-129">Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da Sie nach IP-Adressen filtern können.</span><span class="sxs-lookup"><span data-stu-id="83f20-129">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="83f20-130">Die öffentliche IP-Adresse des Zugriffs Rands ist primär mit dem Standardgateway auf den integrierten Router (10.45.16.1) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="83f20-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="83f20-131">Private IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche IP-Adressen im Abschnitt **erweitert** der Eigenschaften von **Internet Protocol Version 4 (TCP/IPv4)** und **Internet Protocol Version 6 (TCP/IPv6)** der Eigenschaften für den **lokalen Verbindungsbereich** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="83f20-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="83f20-132">**Netzwerkadapter 2 Knoten 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="83f20-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="83f20-133">Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 10.45.16.11 für Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 für AV Edge.</span><span class="sxs-lookup"><span data-stu-id="83f20-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="83f20-134">Die öffentliche IP-Adresse des Zugriffs Rands ist primär mit dem Standardgateway auf den integrierten Router (10.45.16.1) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="83f20-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="83f20-135">Private IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche IP-Adressen im Abschnitt **erweitert** der Eigenschaften von **Internet Protocol Version 4 (TCP/IPv4)** und **Internet Protocol Version 6 (TCP/IPv6)** der Eigenschaften für den **lokalen Verbindungsbereich** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="83f20-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="83f20-136">Die Konfiguration des Edge-Servers mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="83f20-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="83f20-137">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edge-Servers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="83f20-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="83f20-138">Der Hauptvorteil dieser Option ist ein eindeutiger Netzwerkadapter pro Edgeserver und eine potenziell genauere Datensammlung, wenn eine Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="83f20-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="83f20-139">DNS-Einträge für den skalierten konsolidierten Edge, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="83f20-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83f20-140">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="83f20-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="83f20-141">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="83f20-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="83f20-142">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="83f20-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="83f20-143">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="83f20-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83f20-144">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="83f20-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="83f20-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-146">131.107.155.10 und 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="83f20-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="83f20-147">Access Edge External Interface (Contoso) wiederholen Sie diese nach Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="83f20-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f20-148">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="83f20-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="83f20-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-150">131.107.155.20 und 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="83f20-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="83f20-151">Externe Schnittstelle für Webkonferenz-Edge</span><span class="sxs-lookup"><span data-stu-id="83f20-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f20-152">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="83f20-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="83f20-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-154">131.107.155.30 und 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="83f20-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="83f20-155">Externe Schnittstelle A/V Edge</span><span class="sxs-lookup"><span data-stu-id="83f20-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f20-156">Externer DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="83f20-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="83f20-157">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-159">Access Edge-externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="83f20-159">Access Edge external interface.</span></span> <span data-ttu-id="83f20-160">Erforderlich für die automatische Konfiguration von lync 2013-und lync 2010-Clients, um extern zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="83f20-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="83f20-161">Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="83f20-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83f20-162">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="83f20-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="83f20-163">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-165">Externe SIP-Access-Edge-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="83f20-165">SIP Access Edge external interface.</span></span> <span data-ttu-id="83f20-166">Erforderlich für die automatische DNS-Ermittlung von Verbundpartnern, die als "zugelassene SIP-Domäne" bezeichnet werden (genannt Enhanced Federation in früheren Versionen).</span><span class="sxs-lookup"><span data-stu-id="83f20-166">Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="83f20-167">Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="83f20-167">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f20-168">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="83f20-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="83f20-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="83f20-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="83f20-170">172.25.33.10 und 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="83f20-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="83f20-171">Konsolidierte Edge-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83f20-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="83f20-172">Für den Verbund erforderliche Datensätze</span><span class="sxs-lookup"><span data-stu-id="83f20-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83f20-173">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="83f20-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="83f20-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="83f20-174">FQDN</span></span></th>
<th><span data-ttu-id="83f20-175">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="83f20-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="83f20-176">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="83f20-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83f20-177">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="83f20-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="83f20-178">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-180">Die externe SIP-Schnittstelle für die automatische DNS-Erkennung Ihres Verbandes zu anderen potenziellen Verbundpartnern ist erforderlich und wird als "zugelassene SIP-Domänen" bezeichnet (so genannte erweiterte Föderation in früheren Versionen). Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="83f20-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="83f20-181">Dieser SRV-Eintrag ist für Mobilität und das Clearinghaus für Push-Benachrichtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="83f20-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="83f20-182">DNS-Zusammenfassung – öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="83f20-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83f20-183">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="83f20-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="83f20-184">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="83f20-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="83f20-185">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="83f20-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="83f20-186">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="83f20-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83f20-187">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="83f20-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="83f20-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-189">Access Edge Service-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83f20-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="83f20-190">Access Edge External Interface (Contoso) wiederholen Sie diese nach Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="83f20-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="83f20-191">DNS-Zusammenfassung für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="83f20-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83f20-192">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="83f20-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="83f20-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="83f20-193">FQDN</span></span></th>
<th><span data-ttu-id="83f20-194">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="83f20-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="83f20-195">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="83f20-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83f20-196">Externer DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="83f20-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="83f20-197">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83f20-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83f20-199">XMPP-Proxy-externe Schnittstelle im Access Edge-Dienst oder Edge-Pool. Wiederholen Sie diese Schritte für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen der Kontakt mit XMPP-Kontakten durch die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Website Richtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf die Lync-fähiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="83f20-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="83f20-200">Eine zulässige XMPP-Domäne muss auch in der XMPP-Föderationspartner-Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="83f20-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="83f20-201">Weitere Informationen finden Sie in den Themen unter <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="83f20-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83f20-202">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="83f20-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="83f20-203">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="83f20-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="83f20-204">IP-Adresse des Zugriffs-Edgedienst auf dem Edgeserver oder Edge-Pool, der XMPP-Proxy hostet</span><span class="sxs-lookup"><span data-stu-id="83f20-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="83f20-205">Verweist auf den Access Edge-Dienst oder den Edge-Pool, der den XMPP-Proxydienst hostet.</span><span class="sxs-lookup"><span data-stu-id="83f20-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="83f20-206">In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Host-Eintrag (a oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="83f20-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

