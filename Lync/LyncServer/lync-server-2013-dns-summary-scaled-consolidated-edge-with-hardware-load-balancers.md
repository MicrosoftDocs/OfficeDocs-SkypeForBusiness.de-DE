---
title: DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="2a1a7-102">DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a1a7-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a1a7-103">_**Letztes Änderungsdatum des Themas:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="2a1a7-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="2a1a7-104">Die Anforderungen für den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="2a1a7-105">Darüber hinaus sind viele Datensätze optional, je nachdem, wie Sie Clients mit lync 2013 konfigurieren und ob Sie die Föderation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="2a1a7-106">Details zu den DNS-Anforderungen von lync 2013 finden Sie unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a1a7-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="2a1a7-107">Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013-Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [Ermitteln der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a1a7-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="2a1a7-108">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die erforderlich sind, um die skalierte konsolidierte Edge-Topologie (Hardware Load Balanced) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="2a1a7-109">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration für lync-Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="2a1a7-110">Wenn Sie beabsichtigen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugehörigen Datensätze nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="2a1a7-111">Wichtig: Anforderungen des Edge-Server-Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="2a1a7-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="2a1a7-112">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass Ihre Edgeserver mindestens zwei Netzwerkadapter aufweisen und dass das Standardgateway nur auf dem Netzwerkadapter festgesetzt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="2a1a7-113">Beispielsweise würde das Standardgateway auf die externe Firewall verweisen, wie es in der Szenariogröße des skalierten konsolidierten Edges im [skalierten konsolidierten Edge mit Hardwarelastenausgleichs in lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="2a1a7-114">Sie können zwei Netzwerkadapter auf allen Edge-Servern wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2a1a7-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="2a1a7-115">**Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="2a1a7-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="2a1a7-116">Interne Schnittstelle mit zugewiesenem 172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="2a1a7-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="2a1a7-117">Kein Standardgateway.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-117">No default gateway.</span></span>
    
    <span data-ttu-id="2a1a7-118">Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Schnittstelle des Edge-Servers zu allen Netzwerken vorhanden ist, die lync Server-Clients oder-Server mit lync Server (beispielsweise von 172.25.33.0 bis 192.168.10.0) enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="2a1a7-119">**Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="2a1a7-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="2a1a7-120">Diesem Netzwerkadapter werden drei öffentliche IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Access Edge Service, 131.107.155.20 for Web Conferencing Edge Service, 131.107.155.30 für A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2a1a7-121">Die IP-Adressen, die den tatsächlichen externen Netzwerkschnittstellen des Edge-Servers zugewiesen sind, hängen möglicherweise davon ab, welches Hardware Lastenausgleichsmodul Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="2a1a7-122">Informationen zu den tatsächlichen IP-Adressen Anforderungen finden Sie in der Dokumentation Ihres Hardwarelastenausgleichs.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="2a1a7-123">Es ist jedoch möglich, eine einzige IP-Adresse für alle drei Edge-Service-Interfaces zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="2a1a7-124">Obwohl dadurch IP-Adressen gespeichert werden, sind für jeden Dienst unterschiedliche Portnummern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="2a1a7-125">Die Standardportnummer ist 443/TCP, wodurch sichergestellt wird, dass die meisten Remote Firewalls den Datenverkehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="2a1a7-126">Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für den Access-Edgedienst, 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst kann zu Problemen bei Remotebenutzern führen, bei denen eine Firewall, die Sie behindern, den Datenverkehr nicht zulässt. 5061/TCP und 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="2a1a7-127">Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da Sie nach IP-Adressen filtern können.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="2a1a7-128">Die IP-Adresse des Zugriffs-Edge-Diensts ist primär mit dem Standardgateway auf Internet-Facing Router (131.107.155.1) eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="2a1a7-129">Web Conferencing Edge Service und A/V Edge Service-IP-Adressen sekundär.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="2a1a7-130">Die Konfiguration des Edge-Servers mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="2a1a7-131">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edge-Servers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="2a1a7-132">Der Hauptvorteil dieser Option ist ein eindeutiger Netzwerkadapter pro Edgeserver und eine potenziell genauere Datensammlung, wenn eine Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="2a1a7-133">DNS-Einträge, die für den skalierten konsolidierten Edge erforderlich sind, Hardware Lastenausgleich (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="2a1a7-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a1a7-134">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="2a1a7-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2a1a7-135">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="2a1a7-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="2a1a7-136">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="2a1a7-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="2a1a7-137">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="2a1a7-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a1a7-138">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="2a1a7-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a1a7-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="2a1a7-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-141">Access Edge Service External Interface (Contoso).</span><span class="sxs-lookup"><span data-stu-id="2a1a7-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="2a1a7-142">Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a1a7-143">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="2a1a7-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a1a7-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="2a1a7-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-146">Web Conferencing Edge Service-externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a1a7-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a1a7-147">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="2a1a7-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a1a7-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="2a1a7-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-150">Externe Schnittstelle A/V Edge Service</span><span class="sxs-lookup"><span data-stu-id="2a1a7-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a1a7-151">Externer DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="2a1a7-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-152">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a1a7-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a1a7-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-154">Access Edge Service-externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-154">Access Edge service external interface.</span></span> <span data-ttu-id="2a1a7-155">Erforderlich für die automatische Konfiguration von lync 2013-und lync 2010-Clients, um extern zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="2a1a7-156">Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a1a7-157">Externer DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="2a1a7-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-158">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a1a7-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a1a7-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-160">SIP Access Edge Service-externe Schnittstelle für die automatische DNS-Ermittlung von Verbundpartnern, die als "zugelassene SIP-Domäne" bezeichnet werden (genannt Enhanced Federation in früheren Versionen).</span><span class="sxs-lookup"><span data-stu-id="2a1a7-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="2a1a7-161">Wiederholen Sie diese Schritte für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push-Benachrichtigungsdienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a1a7-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a1a7-162">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="2a1a7-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2a1a7-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="2a1a7-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="2a1a7-165">Konsolidierte Edge-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a1a7-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

