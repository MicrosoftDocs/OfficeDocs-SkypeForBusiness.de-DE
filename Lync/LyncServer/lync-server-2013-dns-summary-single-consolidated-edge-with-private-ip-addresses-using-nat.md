---
title: DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71395e8107c2a1fcb5bd999bd49ef73ea556fa13
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="47219-102">DNS-Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47219-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47219-103">_**Letztes Änderungsstand des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="47219-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="47219-104">Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="47219-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="47219-105">Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.</span><span class="sxs-lookup"><span data-stu-id="47219-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="47219-106">Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47219-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="47219-107">Ausführliche Informationen zur automatischen Konfiguration von Clients, auf denen lync 2013, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie unter "automatische Konfiguration ohne Split-Brain-DNS" in [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47219-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="47219-108">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich ist, wie sie in der Abbildung „Topologie mit einem einzelnen konsolidierten Edgeserver“ gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="47219-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="47219-109">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013 und lync 2010 Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="47219-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="47219-110">Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten automatischen Konfigurationseinträge nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="47219-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="47219-111">Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter</span><span class="sxs-lookup"><span data-stu-id="47219-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="47219-112">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="47219-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="47219-113">Beispielsweise würde das Standardgateway wie in der einzelnen konsolidierten Edge-Topologie in [einem einzelnen konsolidierten Edgeserver mit privaten IP-Adressen und NAT in lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)zeigt auf die externe Firewall (10.45.16.1) zeigen.</span><span class="sxs-lookup"><span data-stu-id="47219-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="47219-114">Sie können die zwei Netzwerkadapter auf Ihrem Edgeserver folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="47219-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="47219-115">**Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="47219-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="47219-116">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="47219-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="47219-117">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="47219-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="47219-118">Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="47219-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="47219-119">**Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="47219-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="47219-120">Diesem Netzwerkadapter werden drei private IP-Adressen zugewiesen, beispielsweise 10.45.16.10 für Access Edge, 10.45.16.20 für Webkonferenz-Edge, 10.45.16.30 für AV-Edge</span><span class="sxs-lookup"><span data-stu-id="47219-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="47219-p104">Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden. Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben. Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen. Wenn Sie die Portwerte (beispielsweise) auf 5061/TCP für den Zugriffs-Edgedienst, 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst ändern, kann dies für Remotebenutzer zu Problemen führen, falls eine Firewall, hinter der sich die Benutzer befinden, keinen Datenverkehr über 5061/TCP und 444/TCP zulässt. Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da auf diese Weise eine Filterung nach der IP-Adresse möglich ist.</span><span class="sxs-lookup"><span data-stu-id="47219-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="47219-126">Die Zugriffs-Edge-IP-Adresse ist primär, wobei Standardgateway auf integrierter Router (10.45.16.1) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="47219-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="47219-127">Webkonferenz-und A/V-Edge-IP-Adressen sekundär.</span><span class="sxs-lookup"><span data-stu-id="47219-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="47219-128">Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="47219-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="47219-129">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="47219-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="47219-130">Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="47219-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="47219-131">Erforderliche DNS-Einträge für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="47219-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47219-132">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="47219-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="47219-133">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="47219-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="47219-134">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="47219-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="47219-135">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="47219-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47219-136">Externer DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="47219-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="47219-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="47219-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="47219-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="47219-139">Externe Schnittstelle des Zugriffs-Edgeservers (Contoso); bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen</span><span class="sxs-lookup"><span data-stu-id="47219-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47219-140">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="47219-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="47219-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="47219-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="47219-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="47219-143">Externe Schnittstelle des Edgeservers für Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="47219-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47219-144">Externes DNS/A</span><span class="sxs-lookup"><span data-stu-id="47219-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="47219-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="47219-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="47219-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="47219-147">Externe Schnittstelle des A/V-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="47219-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47219-148">Externe DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="47219-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="47219-149">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="47219-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="47219-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-151">Externe Schnittstelle des Zugriffs-Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="47219-151">Access Edge external interface.</span></span> <span data-ttu-id="47219-152">Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="47219-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="47219-153">Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="47219-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47219-154">Externes DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="47219-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="47219-155">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="47219-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="47219-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-157">Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche von Verbundpartnern, bezeichnet als „Zugelassene SIP-Domäne“ (in Vorgängerversionen als erweiterter Verbund bezeichnet). Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="47219-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47219-158">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="47219-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="47219-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="47219-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="47219-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="47219-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="47219-161">Interne Schnittstelle des konsolidierten Edgeservers</span><span class="sxs-lookup"><span data-stu-id="47219-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="47219-162">Die in der vorangegangenen Tabelle aufgeführten Einträge sind entweder mit der Erweiterung <EM>.net</EM> oder der Erweiterung <EM>.com</EM> aufgeführt, um hervorzuheben, in welcher Zone sie platziert werden müssen, wenn kein Split-Brain-DNS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="47219-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="47219-163">Wenn Sie das Split-Brain-DNS verwenden, befinden sich alle Datensätze in derselben <EM>. com</EM> -Zone, wobei die einzige Unterscheidung darin besteht, ob Sie sich in der internen oder externen DNS-Zonenversion befinden.</span><span class="sxs-lookup"><span data-stu-id="47219-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="47219-164">Ausführliche Informationen finden Sie unter "Split-Brain DNS" in <A href="lync-server-2013-determine-dns-requirements.md">bestimmen der DNS-Anforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="47219-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="47219-165">Für Partnerverbund erforderliche Datensätze</span><span class="sxs-lookup"><span data-stu-id="47219-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47219-166">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="47219-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="47219-167">FQDN</span><span class="sxs-lookup"><span data-stu-id="47219-167">FQDN</span></span></th>
<th><span data-ttu-id="47219-168">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="47219-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="47219-169">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="47219-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47219-170">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="47219-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="47219-171">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="47219-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="47219-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-173">Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche Ihres Partnerverbungs nach anderen Verbundpartnern, bezeichnet als „Zugelassene SIP-Domänen“ (in Vorgängerversionen als erweiterter Verbund bezeichnet). Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="47219-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="47219-174">Dieser SRV-Eintrag ist für die Mobilitätsfunktion und die Pushbenachrichtigung für Clearinghouse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="47219-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="47219-175">DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="47219-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47219-176">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="47219-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="47219-177">FQDN</span><span class="sxs-lookup"><span data-stu-id="47219-177">FQDN</span></span></th>
<th><span data-ttu-id="47219-178">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="47219-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="47219-179">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="47219-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47219-180">Externe DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="47219-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="47219-181">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="47219-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="47219-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="47219-183">Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie diese Schritte bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf den Lync-aktivierter Benutzer.</span><span class="sxs-lookup"><span data-stu-id="47219-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="47219-184">Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="47219-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="47219-185">Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="47219-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47219-186">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="47219-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="47219-187">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="47219-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="47219-188">IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</span><span class="sxs-lookup"><span data-stu-id="47219-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="47219-189">Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten.</span><span class="sxs-lookup"><span data-stu-id="47219-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="47219-190">Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="47219-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

