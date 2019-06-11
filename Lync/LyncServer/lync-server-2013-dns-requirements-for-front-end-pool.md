---
title: 'Lync Server 2013: DNS-Anforderungen für den Front-End-Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="58f39-102">DNS-Anforderungen für den Front-End-Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58f39-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58f39-103">_**Letztes Änderungsdatum des Themas:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="58f39-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="58f39-104">Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="58f39-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="58f39-105">Sie müssen die erforderlichen DNS-Einträge (Domain Name System) vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="58f39-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="58f39-106">Darüber hinaus sind einige der vollqualifizierten Domänennamen (FQDNs), die bei der Konfiguration einer lync Server 2013-Bereitstellung verwendet werden, logische und keine physischen Server-FQDNs, daher ist vor der Veröffentlichung eine zusätzliche DNS-Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58f39-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="58f39-107">Lync Server 2013 unterstützt keine Single-Labeling-Domänen.</span><span class="sxs-lookup"><span data-stu-id="58f39-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="58f39-108">Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne mit dem Namen <STRONG>contoso. local</STRONG> unterstützt, aber eine Stammdomäne mit dem Namen <STRONG>local</STRONG> wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58f39-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="58f39-109">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einer einzelnen Bezeichnung" unter <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="58f39-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="58f39-110">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="58f39-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="58f39-111">Standardmäßig ist der Computername eines Computers, der nicht zu einer Domäne gehört, ein kurzer Name und kein FQDN.</span><span class="sxs-lookup"><span data-stu-id="58f39-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="58f39-112">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="58f39-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="58f39-113"><STRONG>Nur Standardzeichen verwenden</STRONG> (einschließlich a – z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs Ihrer Server mit lync Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="58f39-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="58f39-114">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="58f39-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="58f39-115">Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen Zertifizierungsstellen (CAS) unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).</span><span class="sxs-lookup"><span data-stu-id="58f39-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="58f39-116">Bevor Sie die Topologie nach der Bereitstellung ausführen, stellen Sie sicher, dass die folgenden Active Directory-und DNS-Einträge erstellt werden (entsprechend Ihren Anforderungen für bestimmte Features):</span><span class="sxs-lookup"><span data-stu-id="58f39-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="58f39-117">Jede Serverrolle, die in der Topologie vorhanden sein wird, wird als Active Directory-Objekt veröffentlicht (die Verbindung zwischen dem Computer und der Domäne wird dies erreichen).</span><span class="sxs-lookup"><span data-stu-id="58f39-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="58f39-118">Für jeden Server ist ein DNS-a-Eintrag vorhanden.</span><span class="sxs-lookup"><span data-stu-id="58f39-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="58f39-119">Für jede SIP-Domäne ist ein DNS-SRV-Eintrag vorhanden, wenn Sie beabsichtigen, die automatische Anmeldung \_für\_Clients in Form von sipinternaltls TCP zu verwenden. \<SIP-\>Domäne.</span><span class="sxs-lookup"><span data-stu-id="58f39-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="58f39-120">Wenn Sie die manuelle Konfiguration für Clients verwenden, ist dieser Eintrag nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58f39-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="58f39-121">Ein DNS-a-Eintrag für jede konfigurierte einfache URL, von der in der Regel vier vorhanden sind: Meet, Dialin, LWA und Scheduler.</span><span class="sxs-lookup"><span data-stu-id="58f39-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="58f39-122">Darüber hinaus gibt es die einfache Administrator-URL, die eine spezielle URL für den Zugriff auf die lync Server 2013-Systemsteuerung ist.</span><span class="sxs-lookup"><span data-stu-id="58f39-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="58f39-123">Der Server, auf dem SQL Server ausgeführt wird, muss der Domäne angehören und von dem Computer erreichbar sein, von dem aus der Topologie-Generator veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="58f39-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="58f39-124">Die Tabelle folgt den Referenzarchitekturen, die im Abschnitt Planung vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="58f39-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="58f39-125">Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="58f39-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="58f39-126">Für den Front-End-Pool erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="58f39-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58f39-127">Ort</span><span class="sxs-lookup"><span data-stu-id="58f39-127">Location</span></span></th>
<th><span data-ttu-id="58f39-128">Typ</span><span class="sxs-lookup"><span data-stu-id="58f39-128">Type</span></span></th>
<th><span data-ttu-id="58f39-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="58f39-129">FQDN</span></span></th>
<th><span data-ttu-id="58f39-130">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="58f39-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58f39-131">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-132">A</span><span class="sxs-lookup"><span data-stu-id="58f39-132">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="58f39-134">Pool01 (DNS-Lastenausgleich).</span><span class="sxs-lookup"><span data-stu-id="58f39-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="58f39-135">Erfordert einen DNS-a-Eintrag für die IP-Adresse jedes Front-End-Servers innerhalb des Pools, der dem Pool-FQDN zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="58f39-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f39-136">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-137">A</span><span class="sxs-lookup"><span data-stu-id="58f39-137">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="58f39-139">Pool01 (Virtual IP (VIP) of Hardware Load Balancer).</span><span class="sxs-lookup"><span data-stu-id="58f39-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f39-140">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-141">A</span><span class="sxs-lookup"><span data-stu-id="58f39-141">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="58f39-143">FE02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="58f39-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="58f39-145">…</span><span class="sxs-lookup"><span data-stu-id="58f39-145"></span></span></p></td>
<td><p><span data-ttu-id="58f39-146">Pool01-Front-End-Server (Knoten 1).</span><span class="sxs-lookup"><span data-stu-id="58f39-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="58f39-147">Pool01-Front-End-Server (Knoten 2).</span><span class="sxs-lookup"><span data-stu-id="58f39-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="58f39-148">Pool01-Front-End-Server (Knoten 3).</span><span class="sxs-lookup"><span data-stu-id="58f39-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="58f39-149">…</span><span class="sxs-lookup"><span data-stu-id="58f39-149"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f39-150">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-151">A</span><span class="sxs-lookup"><span data-stu-id="58f39-151">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-152">FE02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="58f39-153">Pool01-Front-End-Server (Knoten 2).</span><span class="sxs-lookup"><span data-stu-id="58f39-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f39-154">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-155">A</span><span class="sxs-lookup"><span data-stu-id="58f39-155">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="58f39-157">Pool01 (VIP) für Client-to-Server-Webverkehr.</span><span class="sxs-lookup"><span data-stu-id="58f39-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f39-158">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-159">A</span><span class="sxs-lookup"><span data-stu-id="58f39-159">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="58f39-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="58f39-161">Pool01-Back-End-Server mit SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="58f39-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f39-162">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-163">A</span><span class="sxs-lookup"><span data-stu-id="58f39-163">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="58f39-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-165">Erforderlich für lync Phone Edition oder automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für strikte Domänenübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="58f39-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="58f39-166">In allen Fällen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58f39-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f39-167">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-168">A</span><span class="sxs-lookup"><span data-stu-id="58f39-168">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="58f39-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-170">Nimmt eine zweite SIP-Domäne an.</span><span class="sxs-lookup"><span data-stu-id="58f39-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="58f39-171">Erforderlich für lync Phone Edition, automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für strikte Domänenübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="58f39-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="58f39-172">In allen Fällen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58f39-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f39-173">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-174">A</span><span class="sxs-lookup"><span data-stu-id="58f39-174">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="58f39-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-176">Einfache URL für intern veröffentlichte Einwahlkonferenzen – der Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="58f39-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f39-177">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-178">A</span><span class="sxs-lookup"><span data-stu-id="58f39-178">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-179">Meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="58f39-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-180">Einfache URL für intern veröffentlichte Konferenzen – der Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="58f39-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f39-181">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-182">A</span><span class="sxs-lookup"><span data-stu-id="58f39-182">A</span></span></p></td>
<td><p><span data-ttu-id="58f39-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="58f39-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="58f39-184">admin</span><span class="sxs-lookup"><span data-stu-id="58f39-184">admin</span></span></p></td>
<td><p><span data-ttu-id="58f39-185">Optionaler Eintrag, einfache URL für lync Server 2013 Control Panel intern veröffentlicht-Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="58f39-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="58f39-186">Es wird nur Hostname (kein Domänenname) empfohlen.</span><span class="sxs-lookup"><span data-stu-id="58f39-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="58f39-187">VIP = virtuelle IP-Adresse für das Hardware Load Balancer</span><span class="sxs-lookup"><span data-stu-id="58f39-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="58f39-188">DNS-SRV-Einträge für den Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="58f39-188">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58f39-189">Ort</span><span class="sxs-lookup"><span data-stu-id="58f39-189">Location</span></span></th>
<th><span data-ttu-id="58f39-190">Typ</span><span class="sxs-lookup"><span data-stu-id="58f39-190">Type</span></span></th>
<th><span data-ttu-id="58f39-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="58f39-191">FQDN</span></span></th>
<th><span data-ttu-id="58f39-192">Ziel-FQDN</span><span class="sxs-lookup"><span data-stu-id="58f39-192">Target FQDN</span></span></th>
<th><span data-ttu-id="58f39-193">Port</span><span class="sxs-lookup"><span data-stu-id="58f39-193">Port</span></span></th>
<th><span data-ttu-id="58f39-194">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="58f39-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58f39-195">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-196">SRV</span><span class="sxs-lookup"><span data-stu-id="58f39-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="58f39-197">_sipinternaltls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="58f39-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="58f39-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-199">5061</span><span class="sxs-lookup"><span data-stu-id="58f39-199">5061</span></span></p></td>
<td><p><span data-ttu-id="58f39-200">Erforderlich für die automatische Konfiguration von lync 2013-Clients, um intern zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="58f39-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58f39-201">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-202">SRV</span><span class="sxs-lookup"><span data-stu-id="58f39-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="58f39-203">_sipinternaltls. _tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="58f39-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="58f39-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-205">5061</span><span class="sxs-lookup"><span data-stu-id="58f39-205">5061</span></span></p></td>
<td><p><span data-ttu-id="58f39-206">Erforderlich für die automatische Konfiguration von lync 2013-Clients, um intern zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="58f39-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58f39-207">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58f39-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="58f39-208">SRV</span><span class="sxs-lookup"><span data-stu-id="58f39-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="58f39-209">_ntp._udp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="58f39-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-210">DC01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="58f39-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="58f39-211">123</span><span class="sxs-lookup"><span data-stu-id="58f39-211">123</span></span></p></td>
<td><p><span data-ttu-id="58f39-212">Für Geräte, auf denen lync Phone Edition ausgeführt wird, ist eine NTP-Quelle (Network Time Protocol) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58f39-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="58f39-213">Intern sollte dies auf den Domänencontroller verweisen.</span><span class="sxs-lookup"><span data-stu-id="58f39-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="58f39-214">Wenn der Domänencontroller nicht definiert ist, wird versucht, den NTP-Server time.Windows.com zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="58f39-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

