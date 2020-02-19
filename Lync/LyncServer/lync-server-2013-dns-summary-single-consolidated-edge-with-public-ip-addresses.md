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
ms.openlocfilehash: 802e256641f49cbd2cadc63a763e6f1152e56a6b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="e31cc-102">DNS-Zusammenfassung – einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e31cc-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e31cc-103">_**Letztes Änderungsstand des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="e31cc-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="e31cc-104">Die Anforderungen an den DNS-Eintrag für den Remotezugriff auf lync Server 2013 sind im Vergleich zu Zertifikaten und Ports relativ unkompliziert.</span><span class="sxs-lookup"><span data-stu-id="e31cc-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="e31cc-105">Außerdem sind viele Datensätze optional, je nachdem, wie Sie Clients, auf denen lync 2013 ausführt, konfigurieren und ob Sie den Verbund aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e31cc-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="e31cc-106">Ausführliche Informationen zu lync 2013 DNS-Anforderungen finden Sie unter [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e31cc-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="e31cc-107">Ausführliche Informationen zur automatischen Konfiguration von Clients, auf denen lync 2013, wenn das Split-Brain-DNS nicht konfiguriert ist, finden Sie unter "automatische Konfiguration ohne Split-Brain-DNS" in [bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e31cc-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="e31cc-108">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung einer Topologie mit einem einzelnen konsolidierten Edgeserver erforderlich ist, wie sie in der Abbildung „Topologie mit einem einzelnen konsolidierten Edgeserver“ gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e31cc-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="e31cc-109">Beachten Sie, dass bestimmte DNS-Einträge nur für die automatische Konfiguration von lync 2013 und lync 2010 Clients erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e31cc-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="e31cc-110">Wenn Sie planen, Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) zum Konfigurieren von lync-Clients zu verwenden, sind die zugeordneten automatischen Konfigurationseinträge nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e31cc-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="e31cc-111">Wichtig: Edgeserver Anforderungen an den Netzwerk Adapter</span><span class="sxs-lookup"><span data-stu-id="e31cc-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="e31cc-112">Um Routingprobleme zu vermeiden, stellen Sie sicher, dass sich mindestens zwei Netzwerkadapter in ihren Edgeserver befinden und dass das Standardgateway nur auf dem Netzwerkadapter festgelegt ist, der der externen Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e31cc-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="e31cc-113">Wie in der einzelnen konsolidierten Edge-Topologie mit öffentlichen IP-Adressen in einem [einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)gezeigt wird, verweist das Standardgateway auf den externen Router an Ihrem Internet Perimeter oder auf eine Firewall, die eine öffentliche IP-Adresse bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e31cc-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="e31cc-114">Die Netzwerkbeziehung für Edgeserver-Schnittstellen ist eine Routenbeziehung anstelle einer NAT-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="e31cc-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="e31cc-115">Sie können die zwei Netzwerkadapter auf Ihrem Edgeserver folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e31cc-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="e31cc-116">**Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="e31cc-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="e31cc-117">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="e31cc-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="e31cc-118">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="e31cc-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="e31cc-119">Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Edge-Schnittstelle zu Netzwerken mit Servern mit lync Server 2013 oder lync Server 2013 Clients (beispielsweise von 172.25.33.0 nach 192.168.10.0) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e31cc-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="e31cc-120">**Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="e31cc-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="e31cc-121">Diesem Netzwerkadapter sind drei öffentliche IP-Adressen zugewiesen, z. B. 131.107.155.10 für den Zugriffs-Edgeserver, 131.107.155.20 für den Webkonferenz-Edgeserver und 131.107.155.30 für den A/V-Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="e31cc-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e31cc-p104">Es ist möglich, wenn auch nicht empfohlen, eine einzelne IP-Adresse für alle drei Edgedienstschnittstellen zu verwenden. Sie sparen zwar auf diese Weise IP-Adressen, Sie müssen jedoch für jeden der Edgedienste eine andere Portnummer angeben. Die Standardportnummer lautet 443/TCP; sie stellt sicher, dass die meisten Remotefirewalls den Datenverkehr zulassen. Wenn Sie die Portwerte (beispielsweise) auf 5061/TCP für den Zugriffs-Edgedienst, 444/TCP für den Webkonferenz-Edgedienst und 443/TCP für den A/V-Edgedienst ändern, kann dies für Remotebenutzer zu Problemen führen, falls eine Firewall, hinter der sich die Benutzer befinden, keinen Datenverkehr über 5061/TCP und 444/TCP zulässt. Darüber hinaus erleichtern drei unterschiedliche IP-Adressen die Problembehandlung, da auf diese Weise eine Filterung nach der IP-Adresse möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e31cc-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="e31cc-127">Die öffentliche IP-Adresse des Zugriffs-Edgeservers ist als primär, das Standardgateway ist auf den öffentlichen Router (131.107.155.1) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e31cc-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="e31cc-128">Bei den öffentlichen IP-Adressen für den Webkonferenz- und A/V-Edgeserver handelt es sich um zusätzliche IP-Adressen im Abschnitt **Erweitert** der Eigenschaften von **Internetprotokoll Version 4 (TCP/IPv4)** und **Internetprotokoll Version 6 (TCP/IPv6)** der **Eigenschaften von LAN-Verbindung** in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e31cc-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="e31cc-129">Das Konfigurieren der Edgeserver mit zwei Netzwerkadaptern ist eine von zwei Optionen.</span><span class="sxs-lookup"><span data-stu-id="e31cc-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="e31cc-130">Die andere Option besteht darin, einen Netzwerkadapter für die interne Seite und drei Netzwerkadapter für die externe Seite des Edgeserver zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e31cc-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="e31cc-131">Der Hauptvorteil dieser Option ist ein gesonderter Netzwerkadapter pro Edgeserver Dienst und möglicherweise genauere Datenerfassung, wenn die Problembehandlung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e31cc-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="e31cc-132">Für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen erforderliche DNS-Einträge (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="e31cc-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e31cc-133">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="e31cc-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e31cc-134">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="e31cc-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="e31cc-135">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="e31cc-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="e31cc-136">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="e31cc-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31cc-137">Externer DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="e31cc-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e31cc-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e31cc-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="e31cc-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="e31cc-140">Externe Schnittstelle des Zugriffs-Edgeservers (Contoso); bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen</span><span class="sxs-lookup"><span data-stu-id="e31cc-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31cc-141">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="e31cc-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e31cc-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e31cc-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="e31cc-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="e31cc-144">Externe Schnittstelle des Edgeservers für Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="e31cc-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31cc-145">Externes DNS/A</span><span class="sxs-lookup"><span data-stu-id="e31cc-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e31cc-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e31cc-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="e31cc-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="e31cc-148">Externe Schnittstelle des A/V-Edgeservers</span><span class="sxs-lookup"><span data-stu-id="e31cc-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31cc-149">Externe DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="e31cc-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="e31cc-150">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="e31cc-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e31cc-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-152">Externe Schnittstelle des Zugriffs-Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="e31cc-152">Access Edge external interface.</span></span> <span data-ttu-id="e31cc-153">Für die automatische Konfiguration von lync 2013 und lync 2010 Clients für externe Arbeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e31cc-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="e31cc-154">Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="e31cc-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31cc-155">Externes DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="e31cc-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="e31cc-156">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="e31cc-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e31cc-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-158">Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche von Verbundpartnern, bezeichnet als „Zugelassene SIP-Domäne“ (in Vorgängerversionen als erweiterter Verbund bezeichnet). Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="e31cc-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31cc-159">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e31cc-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e31cc-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e31cc-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e31cc-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="e31cc-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="e31cc-162">Interne Schnittstelle des konsolidierten Edgeservers</span><span class="sxs-lookup"><span data-stu-id="e31cc-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="e31cc-163">Die in der vorangegangenen Tabelle aufgeführten Einträge sind entweder mit der Erweiterung <EM>.net</EM> oder der Erweiterung <EM>.com</EM> aufgeführt, um hervorzuheben, in welcher Zone sie platziert werden müssen, wenn kein Split-Brain-DNS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e31cc-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="e31cc-164">Bei Verwendung von Split-Brain-DNS befinden sich alle Einträge in derselben Zone und unterscheiden sich nur durch die interne oder externe Version.</span><span class="sxs-lookup"><span data-stu-id="e31cc-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="e31cc-165">Ausführliche Informationen finden Sie unter "Split-Brain DNS" in <A href="lync-server-2013-determine-dns-requirements.md">bestimmen der DNS-Anforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e31cc-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="e31cc-166">Für Partnerverbund erforderliche Datensätze</span><span class="sxs-lookup"><span data-stu-id="e31cc-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e31cc-167">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="e31cc-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e31cc-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="e31cc-168">FQDN</span></span></th>
<th><span data-ttu-id="e31cc-169">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="e31cc-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="e31cc-170">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="e31cc-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31cc-171">Externe DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="e31cc-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="e31cc-172">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="e31cc-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e31cc-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-174">Externe Schnittstelle des SIP-Zugriffs-Edgeservers. Erforderlich für die automatische DNS-Suche Ihres Partnerverbungs nach anderen Verbundpartnern, bezeichnet als „Zugelassene SIP-Domänen“ (in Vorgängerversionen als erweiterter Verbund bezeichnet). Bei Bedarf für alle SIP-Domänen mit für Lync aktivierten Benutzern wiederholen.</span><span class="sxs-lookup"><span data-stu-id="e31cc-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="e31cc-175">Dieser SRV-Eintrag ist für die Mobilitätsfunktion und die Pushbenachrichtigung für Clearinghouse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e31cc-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e31cc-176">DNS-Zusammenfassung für XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="e31cc-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e31cc-177">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="e31cc-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e31cc-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="e31cc-178">FQDN</span></span></th>
<th><span data-ttu-id="e31cc-179">IP-Adresse/FQDN-Hosteintrag</span><span class="sxs-lookup"><span data-stu-id="e31cc-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="e31cc-180">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="e31cc-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31cc-181">Externe DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="e31cc-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="e31cc-182">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="e31cc-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e31cc-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e31cc-184">Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie diese Schritte bei Bedarf für alle internen SIP-Domänen mit lync-aktivierten Benutzern, bei denen Kontakt mit XMPP-Kontakten über die Konfiguration der Richtlinie für den externen Zugriff über eine globale Richtlinie, eine Standortrichtlinie, in der sich der Benutzer befindet, oder auf die Benutzerrichtlinie angewendet wird, die auf den Lync-aktivierter Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e31cc-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="e31cc-185">Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e31cc-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="e31cc-186">Weitere Informationen finden Sie Unterthemen in <strong>Siehe auch</strong> .</span><span class="sxs-lookup"><span data-stu-id="e31cc-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31cc-187">Externe DNS/A</span><span class="sxs-lookup"><span data-stu-id="e31cc-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e31cc-188">xmpp.contoso.com (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="e31cc-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="e31cc-189">IP-Adresse Zugriffs-Edgedienst auf Ihrem Edgeserver oder Edgepool Hosting XMPP-Proxy</span><span class="sxs-lookup"><span data-stu-id="e31cc-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="e31cc-190">Verweist auf die Zugriffs-Edgedienst oder Edgepool, die den XMPP-Proxydienst hosten.</span><span class="sxs-lookup"><span data-stu-id="e31cc-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="e31cc-191">Der SRV-Eintrag, den Sie erstellen, verweist normalerweise auf diesen Hosteintrag (A oder AAAA).</span><span class="sxs-lookup"><span data-stu-id="e31cc-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

