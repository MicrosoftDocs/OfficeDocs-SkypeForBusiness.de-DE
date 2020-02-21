---
title: 'Lync Server 2013: DNS-Anforderungen für Front-End-Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0ace2b05b506b5bbf73177282747a66d212b38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="c2629-102">DNS-Anforderungen für Front-End-Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2629-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2629-103">_**Letztes Änderungsstand des Themas:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="c2629-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="c2629-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNS-Admins" beim Server oder bei der Domäne angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="c2629-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="c2629-105">Sie müssen die erforderlichen Domain Name System (DNS) Einträge vor dem Veröffentlichen Ihrer Topologie im Topologie-Generator konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c2629-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="c2629-106">Darüber hinaus sind einige der vollqualifizierten Domänennamen (FQDNs), die in der Konfiguration einer lync Server 2013-Bereitstellung verwendet werden, logische und keine physischen Server-FQDNs, daher ist vor der Veröffentlichung eine zusätzliche DNS-Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c2629-107">Lync Server 2013 bietet keine Unterstützung für Domänen mit einfacher Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="c2629-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="c2629-108">Beispielsweise wird eine Gesamtstruktur mit einer Stammdomäne namens <STRONG>contoso.local</STRONG> unterstützt, eine Stammdomäne namens <STRONG>local</STRONG> hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="c2629-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="c2629-109">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 300684, "Informationen zum Konfigurieren von Windows für Domänen mit DNS-Namen mit einfacher Bezeichnung" unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="c2629-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c2629-110">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c2629-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="c2629-111">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="c2629-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="c2629-112">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="c2629-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="c2629-113"><STRONG>Verwenden Sie nur Standardzeichen</STRONG> (einschließlich a – z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs Ihrer Server, auf denen lync Server, Edge-Server und Pools verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2629-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="c2629-114">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="c2629-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="c2629-115">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c2629-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="c2629-116">Stellen Sie vor dem Betrieb der Topologie nach der Bereitstellung sicher, dass die folgenden Active Directory-und DNS-Einträge erstellt wurden (entsprechend den Anforderungen bestimmter Features):</span><span class="sxs-lookup"><span data-stu-id="c2629-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="c2629-117">Jede Serverrolle, die in der Topologie vorhanden sein wird, wird als Active Directory Objekt veröffentlicht (das Hinzufügen des Computers zur Domäne wird dies erreichen).</span><span class="sxs-lookup"><span data-stu-id="c2629-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="c2629-118">Für jeden Server ist ein DNS-A-Eintrag vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c2629-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="c2629-119">Für jede SIP-Domäne ist ein DNS-SRV-Eintrag vorhanden, wenn Sie die automatische Anmeldung für Clients in \_Form\_von sipinternaltls TCP verwenden möchten. \<SIP-\>Domäne.</span><span class="sxs-lookup"><span data-stu-id="c2629-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="c2629-120">Wenn Sie für Clients eine manuelle Konfiguration verwenden, ist dieser Eintrag nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="c2629-121">Ein DNS-A-Eintrag für jede konfigurierte einfache URL, für die es im Allgemeinen vier Typen gibt: "Meet", "Dialin", "LWA" und "Scheduler".</span><span class="sxs-lookup"><span data-stu-id="c2629-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="c2629-122">Darüber hinaus gibt es die einfache admin-URL, die eine spezielle URL für den Zugriff auf die lync Server 2013-Systemsteuerung ist.</span><span class="sxs-lookup"><span data-stu-id="c2629-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="c2629-123">Der Server mit SQL Server muss der Domäne beigetreten sein und von dem Computer, auf dem der Topologie-Generator veröffentlicht wird, erreichbar sein.</span><span class="sxs-lookup"><span data-stu-id="c2629-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="c2629-124">Die Tabelle folgt den Referenzarchitekturen aus dem Abschnitt zur Planung.</span><span class="sxs-lookup"><span data-stu-id="c2629-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="c2629-125">Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c2629-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="c2629-126">Für die Front-End-Pool erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="c2629-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2629-127">Standort</span><span class="sxs-lookup"><span data-stu-id="c2629-127">Location</span></span></th>
<th><span data-ttu-id="c2629-128">Typ</span><span class="sxs-lookup"><span data-stu-id="c2629-128">Type</span></span></th>
<th><span data-ttu-id="c2629-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="c2629-129">FQDN</span></span></th>
<th><span data-ttu-id="c2629-130">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="c2629-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2629-131">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-132">A</span><span class="sxs-lookup"><span data-stu-id="c2629-132">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c2629-134">Pool01 (DNS-Lastenausgleich).</span><span class="sxs-lookup"><span data-stu-id="c2629-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="c2629-135">Erfordert einen DNS-a-Eintrag für die IP-Adresse der einzelnen Front-End-Server im Pool, die dem Pool-FQDN zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c2629-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2629-136">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-137">A</span><span class="sxs-lookup"><span data-stu-id="c2629-137">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c2629-139">Pool01 (virtuelle IP [VIP] des Hardwaregeräts für den Lastenausgleich)</span><span class="sxs-lookup"><span data-stu-id="c2629-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2629-140">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-141">A</span><span class="sxs-lookup"><span data-stu-id="c2629-141">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="c2629-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="c2629-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="c2629-145">…</span><span class="sxs-lookup"><span data-stu-id="c2629-145">…</span></span></p></td>
<td><p><span data-ttu-id="c2629-146">Pool01 Front-End-Server (Knoten 1).</span><span class="sxs-lookup"><span data-stu-id="c2629-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="c2629-147">Pool01 Front-End-Server (Knoten 2).</span><span class="sxs-lookup"><span data-stu-id="c2629-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="c2629-148">Pool01 Front-End-Server (Knoten 3).</span><span class="sxs-lookup"><span data-stu-id="c2629-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="c2629-149">…</span><span class="sxs-lookup"><span data-stu-id="c2629-149">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2629-150">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-151">A</span><span class="sxs-lookup"><span data-stu-id="c2629-151">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c2629-153">Pool01 Front-End-Server (Knoten 2).</span><span class="sxs-lookup"><span data-stu-id="c2629-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2629-154">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-155">A</span><span class="sxs-lookup"><span data-stu-id="c2629-155">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c2629-157">Pool01 (VIP) für Webdatenverkehr vom Client zum Server</span><span class="sxs-lookup"><span data-stu-id="c2629-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2629-158">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-159">A</span><span class="sxs-lookup"><span data-stu-id="c2629-159">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c2629-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c2629-161">Pool01-Back-End-Server mit SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="c2629-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2629-162">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-163">A</span><span class="sxs-lookup"><span data-stu-id="c2629-163">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c2629-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-165">Für lync-Phone Edition oder automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für eine strenge Domänenübereinstimmung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="c2629-166">Nicht in allen Fällen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2629-167">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-168">A</span><span class="sxs-lookup"><span data-stu-id="c2629-168">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c2629-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-170">Setzt eine zweite SIP-Domäne voraus.</span><span class="sxs-lookup"><span data-stu-id="c2629-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="c2629-171">Für lync-Phone Edition, automatische Anmeldung von Clients ohne DNS-SRV-Einträge und für eine strenge Domänenübereinstimmung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="c2629-172">Nicht in allen Fällen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2629-173">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-174">A</span><span class="sxs-lookup"><span data-stu-id="c2629-174">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c2629-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-176">Einfache URL für intern veröffentlichte Einwahlkonferenzen – Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c2629-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2629-177">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-178">A</span><span class="sxs-lookup"><span data-stu-id="c2629-178">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c2629-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-180">Einfache URL für intern veröffentlichte Konferenzen – Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c2629-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2629-181">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-182">A</span><span class="sxs-lookup"><span data-stu-id="c2629-182">A</span></span></p></td>
<td><p><span data-ttu-id="c2629-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c2629-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="c2629-184">admin</span><span class="sxs-lookup"><span data-stu-id="c2629-184">admin</span></span></p></td>
<td><p><span data-ttu-id="c2629-185">Optionaler Datensatz, einfache URL für lync Server 2013 Systemsteuerung, die intern veröffentlicht wird – Front-End-Server (oder Director, falls installiert) reagiert auf einfache URL-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c2629-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="c2629-186">Es wird empfohlen, nur Hostname (kein Domänenname) zu nennen.</span><span class="sxs-lookup"><span data-stu-id="c2629-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c2629-187">VIP = Virtuelle IP-Adresse für ein Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="c2629-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="c2629-188">DNS-SRV-Einträge für die Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="c2629-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="c2629-189">Standort</span><span class="sxs-lookup"><span data-stu-id="c2629-189">Location</span></span></th>
<th><span data-ttu-id="c2629-190">Typ</span><span class="sxs-lookup"><span data-stu-id="c2629-190">Type</span></span></th>
<th><span data-ttu-id="c2629-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="c2629-191">FQDN</span></span></th>
<th><span data-ttu-id="c2629-192">Ziel-FQDN</span><span class="sxs-lookup"><span data-stu-id="c2629-192">Target FQDN</span></span></th>
<th><span data-ttu-id="c2629-193">Port</span><span class="sxs-lookup"><span data-stu-id="c2629-193">Port</span></span></th>
<th><span data-ttu-id="c2629-194">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="c2629-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2629-195">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-196">SRV</span><span class="sxs-lookup"><span data-stu-id="c2629-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="c2629-197">_sipinternaltls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c2629-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c2629-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-199">5061</span><span class="sxs-lookup"><span data-stu-id="c2629-199">5061</span></span></p></td>
<td><p><span data-ttu-id="c2629-200">Für die automatische Konfiguration von lync 2013 Clients für die interne Verwendung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2629-201">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-202">SRV</span><span class="sxs-lookup"><span data-stu-id="c2629-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="c2629-203">_sipinternaltls. _tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="c2629-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c2629-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-205">5061</span><span class="sxs-lookup"><span data-stu-id="c2629-205">5061</span></span></p></td>
<td><p><span data-ttu-id="c2629-206">Für die automatische Konfiguration von lync 2013 Clients für die interne Verwendung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2629-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2629-207">Interne DNS-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c2629-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c2629-208">SRV</span><span class="sxs-lookup"><span data-stu-id="c2629-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="c2629-209">_ntp. _udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="c2629-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c2629-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c2629-211">123</span><span class="sxs-lookup"><span data-stu-id="c2629-211">123</span></span></p></td>
<td><p><span data-ttu-id="c2629-212">NTP-Quelle (Network Time Protocol) erforderlich für Geräte, die lync Phone Edition ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2629-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="c2629-213">Intern sollte dieser Eintrag auf den Domänencontroller verweisen.</span><span class="sxs-lookup"><span data-stu-id="c2629-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="c2629-214">Wenn der Domänencontroller nicht definiert ist, wird der NTP-Server "time.windows.com" verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2629-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

