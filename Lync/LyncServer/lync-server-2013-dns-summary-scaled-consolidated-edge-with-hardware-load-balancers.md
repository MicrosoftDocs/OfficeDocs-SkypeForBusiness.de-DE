---
title: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleich
description: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59581f435267a7db607e03a8cbf52d21f70897f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570661"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="70db2-103">DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70db2-103">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70db2-104">_**Letztes Änderungsstand des Themas:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="70db2-104">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="70db2-105">Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="70db2-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="70db2-106">Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.</span><span class="sxs-lookup"><span data-stu-id="70db2-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="70db2-107">Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70db2-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="70db2-108">Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013 Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70db2-108">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="70db2-109">Die folgende Tabelle zeigt eine Übersicht über die DNS-Einträge, die erforderlich sind, um die in der Abbildung "Skalierte konsolidierte Edgetopologie (mit Hardwarelastenausgleich)" gezeigte Topologie zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="70db2-109">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="70db2-110">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration für lync-Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="70db2-110">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="70db2-111">Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten Datensätze nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="70db2-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="70db2-112">Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter</span><span class="sxs-lookup"><span data-stu-id="70db2-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="70db2-113">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="70db2-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="70db2-114">Beispielsweise zeigt das Standardgateway wie im Szenario skalierte konsolidierte Edgeserver in [skaliertem konsolidierten Edgeserver mit Hardwarelastenausgleichs in lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)auf die externe Firewall hin.</span><span class="sxs-lookup"><span data-stu-id="70db2-114">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="70db2-115">Sie können zwei Netzwerkadapter auf jedem ihrer Edgeserver wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="70db2-115">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="70db2-116">**Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="70db2-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="70db2-117">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="70db2-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="70db2-118">Kein Standardgateway.</span><span class="sxs-lookup"><span data-stu-id="70db2-118">No default gateway.</span></span>
    
    <span data-ttu-id="70db2-119">Stellen Sie sicher, dass es eine Route vom Netzwerk mit der Edgeserver internen Schnittstelle zu Netzwerken gibt, die lync Server Clients oder Server mit lync Server (beispielsweise von 172.25.33.0 nach 192.168.10.0) enthalten.</span><span class="sxs-lookup"><span data-stu-id="70db2-119">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="70db2-120">**Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="70db2-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="70db2-121">Diesem Netzwerkadapter werden drei öffentliche IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Zugriffs-Edgedienst, 131.107.155.20 für Webkonferenz-Edgedienst, 131.107.155.30 für A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="70db2-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="70db2-122">Die IP-Adressen, die den tatsächlichen externen Netzwerkschnittstellen des Edgeserver zugewiesen werden, hängen möglicherweise von dem von Ihnen ausgewählten Hardwaregerät für den Lastenausgleich ab.</span><span class="sxs-lookup"><span data-stu-id="70db2-122">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="70db2-123">Lesen Sie in der Dokumentation zum Hardwaregerät zum Lastenausgleich nach, um die tatsächlichen Anforderungen an IP-Adressen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="70db2-123">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="70db2-124">Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="70db2-124">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="70db2-125">Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben.</span><span class="sxs-lookup"><span data-stu-id="70db2-125">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="70db2-126">Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="70db2-126">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="70db2-127">Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für die Zugriffs-Edgedienst, 444/TCP für die Webkonferenz-Edgedienst und 443/TCP für die A/V-Edgedienst kann Probleme für Remotebenutzer verursachen, bei denen eine Firewall, hinter der Sie sich befinden, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="70db2-127">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="70db2-128">Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da auf diese Weise eine Filterung nach der IP-Adresse möglich ist.</span><span class="sxs-lookup"><span data-stu-id="70db2-128">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="70db2-129">Zugriffs-Edgedienst IP-Adresse ist primär, wobei das Standardgateway auf den Internet-Router (131.107.155.1) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="70db2-129">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="70db2-130">Webkonferenz-Edgedienst-und A/V-Edgedienst-IP-Adressen sekundär.</span><span class="sxs-lookup"><span data-stu-id="70db2-130">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="70db2-131">Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="70db2-131">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="70db2-132">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="70db2-132">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="70db2-133">Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="70db2-133">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="70db2-134">Erforderliche DNS-Einträge für eine skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="70db2-134">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70db2-135">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="70db2-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="70db2-136">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="70db2-136">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="70db2-137">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="70db2-137">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="70db2-138">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="70db2-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70db2-139">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="70db2-139">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70db2-140">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70db2-140">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70db2-141">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="70db2-141">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="70db2-142">Zugriffs-Edgedienst externe Schnittstelle (Contoso).</span><span class="sxs-lookup"><span data-stu-id="70db2-142">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="70db2-143">Wiederholen bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern</span><span class="sxs-lookup"><span data-stu-id="70db2-143">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70db2-144">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="70db2-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70db2-145">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70db2-145">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70db2-146">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="70db2-146">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="70db2-147">Webkonferenz-Edgedienst externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70db2-147">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70db2-148">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="70db2-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70db2-149">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70db2-149">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70db2-150">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="70db2-150">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="70db2-151">A/V-Edgedienst externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70db2-151">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70db2-152">Externe DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="70db2-152">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="70db2-153">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="70db2-153">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70db2-154">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70db2-154">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70db2-155">Zugriffs-Edgedienst externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="70db2-155">Access Edge service external interface.</span></span> <span data-ttu-id="70db2-156">Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="70db2-156">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="70db2-157">Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="70db2-157">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70db2-158">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="70db2-158">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="70db2-159">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="70db2-159">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70db2-160">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="70db2-160">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="70db2-161">SIP Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung von Verbundpartnern erforderlich ist, die als "zugelassene SIP-Domäne" bezeichnet werden (als erweiterter Verbund in früheren Versionen bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="70db2-161">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="70db2-162">Wiederholen Sie diese Schritte bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push Notification-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="70db2-162">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70db2-163">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="70db2-163">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="70db2-164">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="70db2-164">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="70db2-165">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="70db2-165">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="70db2-166">Interne Schnittstelle des konsolidierten Edgeservers</span><span class="sxs-lookup"><span data-stu-id="70db2-166">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

