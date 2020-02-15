---
title: DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleich
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
ms.openlocfilehash: 95ab0c9b68d21af782570c850642ce7e83b996d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="37326-102">DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37326-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37326-103">_**Letztes Änderungsstand des Themas:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="37326-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="37326-104">Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="37326-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="37326-105">Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.</span><span class="sxs-lookup"><span data-stu-id="37326-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="37326-106">Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37326-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="37326-107">Ausführliche Informationen zum Konfigurieren der automatischen Konfiguration von lync 2013 Clients, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie im Abschnitt "automatische Konfiguration ohne geteilten Brain-DNS" unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37326-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="37326-108">Die folgende Tabelle zeigt eine Übersicht über die DNS-Einträge, die erforderlich sind, um die in der Abbildung "Skalierte konsolidierte Edgetopologie (mit Hardwarelastenausgleich)" gezeigte Topologie zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="37326-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="37326-109">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration für lync-Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="37326-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="37326-110">Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten Datensätze nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37326-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="37326-111">Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter</span><span class="sxs-lookup"><span data-stu-id="37326-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="37326-112">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="37326-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="37326-113">Beispielsweise zeigt das Standardgateway wie im Szenario skalierte konsolidierte Edgeserver in [skaliertem konsolidierten Edgeserver mit Hardwarelastenausgleichs in lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)auf die externe Firewall hin.</span><span class="sxs-lookup"><span data-stu-id="37326-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="37326-114">Sie können zwei Netzwerkadapter auf jedem ihrer Edgeserver wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="37326-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="37326-115">**Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="37326-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="37326-116">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="37326-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="37326-117">Kein Standardgateway.</span><span class="sxs-lookup"><span data-stu-id="37326-117">No default gateway.</span></span>
    
    <span data-ttu-id="37326-118">Stellen Sie sicher, dass es eine Route vom Netzwerk mit der Edgeserver internen Schnittstelle zu Netzwerken gibt, die lync Server Clients oder Server mit lync Server (beispielsweise von 172.25.33.0 nach 192.168.10.0) enthalten.</span><span class="sxs-lookup"><span data-stu-id="37326-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="37326-119">**Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="37326-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="37326-120">Diesem Netzwerkadapter werden drei öffentliche IP-Adressen zugewiesen, beispielsweise 131.107.155.10 für Zugriffs-Edgedienst, 131.107.155.20 für Webkonferenz-Edgedienst, 131.107.155.30 für A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="37326-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="37326-121">Die IP-Adressen, die den tatsächlichen externen Netzwerkschnittstellen des Edgeserver zugewiesen werden, hängen möglicherweise von dem von Ihnen ausgewählten Hardwaregerät für den Lastenausgleich ab.</span><span class="sxs-lookup"><span data-stu-id="37326-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="37326-122">Lesen Sie in der Dokumentation zum Hardwaregerät zum Lastenausgleich nach, um die tatsächlichen Anforderungen an IP-Adressen zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="37326-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="37326-123">Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="37326-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="37326-124">Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben.</span><span class="sxs-lookup"><span data-stu-id="37326-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="37326-125">Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="37326-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="37326-126">Das Ändern der Portwerte in (zum Beispiel) 5061/TCP für die Zugriffs-Edgedienst, 444/TCP für die Webkonferenz-Edgedienst und 443/TCP für die A/V-Edgedienst kann Probleme für Remotebenutzer verursachen, bei denen eine Firewall, hinter der Sie sich befinden, den Datenverkehr über 5061/TCP und 444/TCP nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="37326-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="37326-127">Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da auf diese Weise eine Filterung nach der IP-Adresse möglich ist.</span><span class="sxs-lookup"><span data-stu-id="37326-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="37326-128">Zugriffs-Edgedienst IP-Adresse ist primär, wobei das Standardgateway auf den Internet-Router (131.107.155.1) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="37326-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="37326-129">Webkonferenz-Edgedienst-und A/V-Edgedienst-IP-Adressen sekundär.</span><span class="sxs-lookup"><span data-stu-id="37326-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="37326-130">Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="37326-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="37326-131">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="37326-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="37326-132">Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="37326-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="37326-133">Erforderliche DNS-Einträge für eine skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="37326-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37326-134">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="37326-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="37326-135">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="37326-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="37326-136">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="37326-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="37326-137">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="37326-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37326-138">Externer DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="37326-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37326-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37326-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37326-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="37326-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="37326-141">Zugriffs-Edgedienst externe Schnittstelle (Contoso).</span><span class="sxs-lookup"><span data-stu-id="37326-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="37326-142">Wiederholen bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern</span><span class="sxs-lookup"><span data-stu-id="37326-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37326-143">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="37326-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37326-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37326-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37326-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="37326-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="37326-146">Webkonferenz-Edgedienst externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37326-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37326-147">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="37326-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37326-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37326-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37326-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="37326-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="37326-150">A/V-Edgedienst externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37326-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37326-151">Externe DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="37326-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="37326-152">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="37326-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37326-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37326-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37326-154">Zugriffs-Edgedienst externe Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="37326-154">Access Edge service external interface.</span></span> <span data-ttu-id="37326-155">Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37326-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="37326-156">Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="37326-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37326-157">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="37326-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="37326-158">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="37326-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37326-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37326-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37326-160">SIP Zugriffs-Edgedienst externe Schnittstelle, die für die automatische DNS-Ermittlung von Verbundpartnern erforderlich ist, die als "zugelassene SIP-Domäne" bezeichnet werden (als erweiterter Verbund in früheren Versionen bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="37326-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="37326-161">Wiederholen Sie diese Schritte bei Bedarf für alle SIP-Domänen mit lync-aktivierten Benutzern und Microsoft lync Mobile-Clients, die entweder den Push-Benachrichtigungsdienst oder den Apple Push Notification-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="37326-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37326-162">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="37326-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37326-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="37326-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="37326-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="37326-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="37326-165">Interne Schnittstelle des konsolidierten Edgeservers</span><span class="sxs-lookup"><span data-stu-id="37326-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

