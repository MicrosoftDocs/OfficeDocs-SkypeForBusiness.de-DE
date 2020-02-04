---
title: DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3578bc7b1668bf8cb2268ed079e558e1cf1761
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="14ac4-102">DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ac4-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14ac4-103">_**Letztes Änderungsdatum des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="14ac4-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="14ac4-104">Die Anforderungen für den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="14ac4-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="14ac4-105">Darüber hinaus sind viele Datensätze optional, je nachdem, wie Sie Clients mit lync 2013 konfigurieren und ob Sie die Föderation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="14ac4-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="14ac4-106">Details zu den DNS-Anforderungen von lync 2013 finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14ac4-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="14ac4-107">Details zur automatischen Konfiguration von Clients, auf denen lync 2013 ausgeführt wird, wenn "Split-Brain DNS" nicht konfiguriert ist, finden Sie unter "automatische Konfiguration ohne Split-Brain-DNS" unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14ac4-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="14ac4-108">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die für die Unterstützung der einzelnen konsolidierten Edge-Topologie erforderlich sind, die in der einzelnen konsolidierten Edge-Topologie-Abbildung dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="14ac4-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="14ac4-109">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013-und lync 2010-Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="14ac4-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="14ac4-110">Wenn Sie beabsichtigen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugehörigen automatischen Konfigurationseinträge nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14ac4-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="14ac4-111">Wichtig: Anforderungen des Edge-Server-Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="14ac4-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="14ac4-112">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass Ihre Edgeserver mindestens zwei Netzwerkadapter aufweisen und dass das Standardgateway nur auf dem Netzwerkadapter festgesetzt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="14ac4-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="14ac4-113">Wie in der einzigen konsolidierten Edge-Topologie mit öffentlichen IP-Adressen in [einem einzigen konsolidierten Edge mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)gezeigt wird, verweist das Standardgateway auf den externen Router an Ihrem Internet Perimeter oder in der Firewall, der öffentliche IP-Adressen bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="14ac4-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="14ac4-114">Die Netzwerkbeziehung für Edgeserver-Schnittstellen ist eine Routenbeziehung anstelle einer NAT-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="14ac4-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="14ac4-115">Sie können zwei Netzwerkadapter auf dem Edgeserver wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="14ac4-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="14ac4-116">**Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="14ac4-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="14ac4-117">Interne Schnittstelle mit zugewiesenem 172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="14ac4-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="14ac4-118">Es wurde kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="14ac4-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="14ac4-119">Stellen Sie sicher, dass eine Route vom Netzwerk mit der Edge-internen Schnittstelle zu allen Netzwerken vorhanden ist, die Server mit lync Server 2013-oder lync Server 2013-Clients enthalten (beispielsweise von 172.25.33.0 bis 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="14ac4-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="14ac4-120">**Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="14ac4-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="14ac4-121">Diesem Netzwerkadapter werden drei öffentliche IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 für AV Edge.</span><span class="sxs-lookup"><span data-stu-id="14ac4-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="14ac4-122">Es ist jedoch möglich, eine einzige IP-Adresse für alle drei Edge-Service-Interfaces zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="14ac4-122">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="14ac4-123">Obwohl dadurch IP-Adressen gespeichert werden, sind für jeden Dienst unterschiedliche Portnummern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14ac4-123">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="14ac4-124">Die Standardportnummer ist 443/TCP, wodurch sichergestellt wird, dass die meisten Remote Firewalls den Datenverkehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="14ac4-124">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="14ac4-125">Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für den Access-Edge, 444/TCP für den Webkonferenz-Edge und 443/TCP für den AV-Edge kann zu Problemen bei Remotebenutzern führen, bei denen eine Firewall, die Sie behindern, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="14ac4-125">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="14ac4-126">Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da Sie nach IP-Adressen filtern können.</span><span class="sxs-lookup"><span data-stu-id="14ac4-126">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="14ac4-127">Die öffentliche IP-Adresse des Zugriffs Rands ist primär mit dem Standardgateway auf den öffentlichen Router (131.107.155.1) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="14ac4-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="14ac4-128">Öffentliche IP-Adressen für Webkonferenzen und A/V-Edge sind zusätzliche IP-Adressen im Abschnitt **erweitert** der Eigenschaften von **Internet Protocol Version 4 (TCP/IPv4)** und **Internet Protocol Version 6 (TCP/IPv6)** der Eigenschaften für den **lokalen Verbindungsbereich** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="14ac4-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="14ac4-129">Die Konfiguration des Edge-Servers mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="14ac4-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="14ac4-130">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edge-Servers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="14ac4-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="14ac4-131">Der Hauptvorteil dieser Option ist ein eindeutiger Netzwerkadapter pro Edgeserver und eine potenziell genauere Datensammlung, wenn eine Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="14ac4-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="14ac4-132">DNS-Einträge, die für einen einzelnen konsolidierten Edge mit öffentlichen IP-Adressen erforderlich sind (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="14ac4-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14ac4-133">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="14ac4-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="14ac4-134">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="14ac4-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="14ac4-135">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="14ac4-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="14ac4-136">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="14ac4-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14ac4-137">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="14ac4-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14ac4-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="14ac4-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="14ac4-140">Access Edge External Interface (Contoso) wiederholen Sie diese nach Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="14ac4-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14ac4-141">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="14ac4-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14ac4-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="14ac4-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="14ac4-144">Externe Schnittstelle für Webkonferenz-Edge</span><span class="sxs-lookup"><span data-stu-id="14ac4-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14ac4-145">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="14ac4-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14ac4-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="14ac4-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="14ac4-148">Externe Schnittstelle A/V Edge</span><span class="sxs-lookup"><span data-stu-id="14ac4-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14ac4-149">Externer DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="14ac4-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="14ac4-150">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-152">Access Edge-externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="14ac4-152">Access Edge external interface.</span></span> <span data-ttu-id="14ac4-153">Erforderlich für die automatische Konfiguration von lync 2013-und lync 2010-Clients, um extern zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="14ac4-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="14ac4-154">Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="14ac4-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14ac4-155">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="14ac4-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="14ac4-156">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-158">Für die automatische DNS-Ermittlung von Verbundpartnern, die als "zugelassene SIP-Domäne" bezeichnet werden (genannt Enhanced Federation in früheren Versionen), ist eine externe SIP-Access-Edge-Schnittstelleerforderlich. Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="14ac4-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14ac4-159">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="14ac4-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14ac4-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="14ac4-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="14ac4-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="14ac4-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="14ac4-162">Konsolidierte Edge-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14ac4-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="14ac4-163">Die in der vorhergehenden Tabelle aufgelisteten Datensätze werden entweder mit einer <EM>.net</EM> -Erweiterung oder einer <EM>com</EM> -Erweiterung angezeigt, um die Zone hervorzuheben, in der Sie sich befinden müssen, wenn Sie nicht das DNS von Split-Brain verwenden.</span><span class="sxs-lookup"><span data-stu-id="14ac4-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="14ac4-164">Wenn Sie das Split-Brain-DNS verwenden, befinden sich alle Datensätze in der gleichen Zone, wobei der einzige Unterschied darin besteht, ob Sie sich in der internen oder externen Version befinden.</span><span class="sxs-lookup"><span data-stu-id="14ac4-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="14ac4-165">Ausführliche Informationen finden Sie unter "Split-Brain DNS" unter <A href="lync-server-2013-determine-dns-requirements.md">Ermitteln der DNS-Anforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="14ac4-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="14ac4-166">Für den Verbund erforderliche Datensätze</span><span class="sxs-lookup"><span data-stu-id="14ac4-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14ac4-167">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="14ac4-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="14ac4-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="14ac4-168">FQDN</span></span></th>
<th><span data-ttu-id="14ac4-169">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="14ac4-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="14ac4-170">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="14ac4-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14ac4-171">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="14ac4-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="14ac4-172">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-174">Die externe SIP-Schnittstelle für die automatische DNS-Erkennung Ihres Verbandes zu anderen potenziellen Verbundpartnern ist erforderlich und wird als "zugelassene SIP-Domänen" bezeichnet (so genannte erweiterte Föderation in früheren Versionen). Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="14ac4-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="14ac4-175">Dieser SRV-Eintrag ist für Mobilität und das Clearinghaus für Push-Benachrichtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14ac4-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="14ac4-176">DNS-Zusammenfassung für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="14ac4-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14ac4-177">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="14ac4-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="14ac4-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="14ac4-178">FQDN</span></span></th>
<th><span data-ttu-id="14ac4-179">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="14ac4-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="14ac4-180">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="14ac4-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14ac4-181">Externer DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="14ac4-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="14ac4-182">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="14ac4-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="14ac4-184">XMPP-Proxy-externe Schnittstelle im Access Edge-Dienst oder Edge-Pool. Wiederholen Sie diese Schritte für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen der Kontakt mit XMPP-Kontakten durch die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Website Richtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf die Lync-fähiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="14ac4-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="14ac4-185">Eine zulässige XMPP-Domäne muss auch in der XMPP-Föderationspartner-Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="14ac4-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="14ac4-186">Weitere Informationen finden Sie in den Themen unter <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="14ac4-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14ac4-187">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="14ac4-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="14ac4-188">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="14ac4-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="14ac4-189">IP-Adresse des Zugriffs-Edgedienst auf dem Edgeserver oder Edge-Pool, der XMPP-Proxy hostet</span><span class="sxs-lookup"><span data-stu-id="14ac4-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="14ac4-190">Verweist auf den Access Edge-Dienst oder den Edge-Pool, der den XMPP-Proxydienst hostet.</span><span class="sxs-lookup"><span data-stu-id="14ac4-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="14ac4-191">In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Host-Eintrag (a oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="14ac4-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

