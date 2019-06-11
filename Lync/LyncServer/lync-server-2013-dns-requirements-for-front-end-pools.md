---
title: 'Lync Server 2013: DNS-Anforderungen für Front-End-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="4f209-102">DNS-Anforderungen für Front-End-Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f209-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f209-103">_**Letztes Änderungsdatum des Themas:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="4f209-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="4f209-104">In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die für die Bereitstellung von Front-End-Pools erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4f209-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="4f209-105">DNS-Einträge für Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="4f209-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="4f209-106">In der folgenden Tabelle sind die DNS-Anforderungen für eine lync Server 2013-Front-End-Pool Bereitstellung angegeben.</span><span class="sxs-lookup"><span data-stu-id="4f209-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="4f209-107">DNS-Anforderungen für einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="4f209-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f209-108">Bereitstellungsszenario</span><span class="sxs-lookup"><span data-stu-id="4f209-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="4f209-109">DNS-Anforderung</span><span class="sxs-lookup"><span data-stu-id="4f209-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f209-110">Front-End-Pool mit mehreren Front-End-Servern und einem Hardware-Lastenausgleichsmodul (unabhängig davon, ob der DNS-Lastenausgleich auch in diesem Pool bereitgestellt wird)</span><span class="sxs-lookup"><span data-stu-id="4f209-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="4f209-111">Bei Verwendung des DNS-Lastenausgleichs und eines Hardware Lastenausgleichs müssen Sie (a)-Datensätze hosten.</span><span class="sxs-lookup"><span data-stu-id="4f209-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="4f209-112">Erstellen Sie einen internen A-Eintrag, der den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools für den DNS-Lastenausgleich behebt.</span><span class="sxs-lookup"><span data-stu-id="4f209-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="4f209-113">Erstellen Sie einen internen Host (A)-Eintrag für die internen Webdienste an die virtuelle IP-Adresse (VIP) des Load Balancer.</span><span class="sxs-lookup"><span data-stu-id="4f209-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="4f209-114">Sie müssen den internen Webdienste-Namen verwenden, wie in Topology Builder definiert.</span><span class="sxs-lookup"><span data-stu-id="4f209-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="4f209-115">Wenn Sie beispielsweise sowohl den DNS-Lastenausgleich als auch den Hardwarelastenausgleich verwenden, verfügen Sie über einen a-Eintrag für jeden Front-End-Server in einem Pool für den DNS-Lastenausgleich und einen a-Eintrag für die internen Webdienste, die auf die virtuelle IP des Hardwarelastenausgleichs verweisen. :</span><span class="sxs-lookup"><span data-stu-id="4f209-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f209-116">DNS-Lastenausgleich: Pool01.contoso.NET IP-Adresse des Pool-10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="4f209-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="4f209-117">Für jeden Front-End-Server gibt es auch einen eindeutigen a-Eintrag:</span><span class="sxs-lookup"><span data-stu-id="4f209-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="4f209-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="4f209-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="4f209-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="4f209-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="4f209-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="4f209-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="4f209-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="4f209-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="4f209-122">Hardware Lastenausgleich: WebInternal.contoso.NET IP address of HLB VIP 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="4f209-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="4f209-123">Für den gesamten Datenverkehr mit Ausnahme des HTTP/HTTPS-Datenverkehrs wird der Pool01.contoso.net-Eintrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="4f209-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="4f209-124">Der HTTP/HTTPS-Datenverkehr verwendet die definierte interne Webdienste-Adresse von 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="4f209-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f209-125">Front-End-Pool mit Bereitstellung des DNS-Lastenausgleichs</span><span class="sxs-lookup"><span data-stu-id="4f209-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="4f209-126">Eine Gruppe interner a-Datensätze, die den FQDN des Pools in die IP-Adresse jedes Servers im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="4f209-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="4f209-127">Für jeden Server im Pool muss ein Eintrag vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4f209-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f209-128">Front-End-Pool mit Bereitstellung des DNS-Lastenausgleichs</span><span class="sxs-lookup"><span data-stu-id="4f209-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="4f209-129">Eine Gruppe interner a-Datensätze, die den FQDN jedes Servers im Pool in die IP-Adresse dieses Servers auflösen.</span><span class="sxs-lookup"><span data-stu-id="4f209-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="4f209-130">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-load-balancing.md">DNS-Lastenausgleich in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4f209-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f209-131">Front-End-Pool mit einem einzelnen Front-End-Server und einer dedizierten Back-End-Datenbank, aber ohne Lastenausgleichsmodul</span><span class="sxs-lookup"><span data-stu-id="4f209-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="4f209-132">Ein interner A-Eintrag, der den FQDN des Front-End-Pools in die IP-Adresse des Single Enterprise Edition-Front-End-Servers auflöst.</span><span class="sxs-lookup"><span data-stu-id="4f209-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f209-133">Automatische Clientanmeldung</span><span class="sxs-lookup"><span data-stu-id="4f209-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="4f209-134">Für jede unterstützte SIP-Domäne einen SRV-Eintrag für _sipinternaltls. _tcp. &lt;Domäne&gt; über Port 5061, die dem FQDN des Front-End-Pools zugeordnet ist, der Clientanforderungen für die Anmeldung authentifiziert und umleitet.</span><span class="sxs-lookup"><span data-stu-id="4f209-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="4f209-135">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4f209-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f209-136">Device Update-Webdienst Ermittlung durch Unified Communications (UC)-Geräte</span><span class="sxs-lookup"><span data-stu-id="4f209-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="4f209-137">Ein interner A-Eintrag mit dem Namen ucupdates-r2. &lt;SIP-&gt; Domäne, die in die IP-Adresse des Front-End-Pools aufgelöst wird, der den Geräte Update-Webdienst hostet.</span><span class="sxs-lookup"><span data-stu-id="4f209-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="4f209-138">In der Situation, in der ein UC-Gerät aktiviert ist, sich ein Benutzer aber noch nie beim Gerät angemeldet hat, ermöglicht der a-Eintrag dem Gerät das Erkennen des Front-End-Pools, auf dem der Geräte Update-Webdienst gehostet wird, und das Abrufen von Updates.</span><span class="sxs-lookup"><span data-stu-id="4f209-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="4f209-139">Andernfalls erhalten Geräte diese Informationen zwar in-Band-Bereitstellung, wenn sich der Benutzer zum ersten Mal anmeldet.</span><span class="sxs-lookup"><span data-stu-id="4f209-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="4f209-140">Wenn Sie über eine vorhandene Bereitstellung des Geräte Update-Webdiensts in lync Server 2010 verfügen, haben Sie bereits einen internen A-Eintrag mit dem Namen ucupdates erstellt. &lt;SIP-&gt;Domäne.</span><span class="sxs-lookup"><span data-stu-id="4f209-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="4f209-141">Für Microsoft Office Communications Server 2007 R2 müssen Sie einen zusätzlichen DNS-A-Eintrag mit dem Namen ucupdates-R2 erstellen. &lt;SIP-&gt;Domäne.</span><span class="sxs-lookup"><span data-stu-id="4f209-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f209-142">Ein Reverse-Proxy zur Unterstützung des HTTP-Datenverkehrs</span><span class="sxs-lookup"><span data-stu-id="4f209-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="4f209-143">Ein externer A-Eintrag, der den FQDN der externen Webfarm in die externe IP-Adresse des Reverse-Proxys auflöst.</span><span class="sxs-lookup"><span data-stu-id="4f209-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="4f209-144">Clients und UC-Geräte verwenden diesen Eintrag, um eine Verbindung mit dem Reverse-Proxy herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4f209-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="4f209-145">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-determine-dns-requirements.md">Ermitteln der DNS-Anforderungen für lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4f209-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f209-146">Die folgende Tabelle zeigt ein Beispiel für die DNS-Einträge, die für den FQDN der internen Webfarm erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4f209-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="4f209-147">Beispiel-DNS-Einträge für den FQDN der internen Webfarm</span><span class="sxs-lookup"><span data-stu-id="4f209-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f209-148">Interner FQDN der Webfarm</span><span class="sxs-lookup"><span data-stu-id="4f209-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="4f209-149">Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="4f209-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="4f209-150">DNS-A-Eintrag (e)</span><span class="sxs-lookup"><span data-stu-id="4f209-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f209-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f209-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4f209-152">EE-Pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f209-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4f209-153">DNS einen Eintrag für den EE-Pool.contoso.com, der in die VIP-Adresse des Load Balancer der Front-End-Server aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4f209-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="4f209-154">DNS-A-Eintrag für webcon.contoso.com, der in die VIP-Adresse des Load Balancer der Front-End-Server aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4f209-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f209-155">EE-Pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f209-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4f209-156">EE-Pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4f209-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4f209-157">DNS-A-Eintrag für EE-Pool.contoso.com, der in die virtuelle IP-Adresse (VIP) des Load Balancer aufgelöst wird, der von den Front-End-Servern der Enterprise Edition im Front-End-Pool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f209-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="4f209-158">Beachten Sie, dass bei Verwendung des DNS-Lastenausgleichs in diesem Pool der Front-End-Pool und die interne Webfarm nicht den gleichen FQDN aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="4f209-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

