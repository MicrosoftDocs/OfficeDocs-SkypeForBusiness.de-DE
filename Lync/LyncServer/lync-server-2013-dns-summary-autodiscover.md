---
title: 'Lync Server 2013: DNS-Zusammenfassung – AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e303ebecc42f03197f6502296c8a2708e97ebf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="4d2d9-102">DNS-Zusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d2d9-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d2d9-103">_**Letztes Änderungsdatum des Themas:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="4d2d9-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="4d2d9-104">Die AutoErmittlung ist ein flexibler Dienst, da Sie die Kommunikation über HTTP oder HTTPS akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="4d2d9-105">Um dies zu erreichen, müssen das Domain Name System (DNS) und die von Servern, die den AutoErmittlungsdienst hosten, verwendeten Zertifikate ordnungsgemäß konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="4d2d9-106">Die Zertifikatanforderungen werden in der [Zertifikats Zusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)behandelt.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4d2d9-107">Die DNS-Nachschlage Logik für die lync Server-Clients verwendet eine bestimmte Reihenfolge der Auflösung.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="4d2d9-108">Sie sollten immer die beiden lyncdiscoverinternal-Elemente angeben. &lt;Domäne&gt; und die lyncdiscover. &lt;Domäne&gt; in Ihrem DNS.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="4d2d9-109">Mit Ausnahme des lyncdiscoverinternal. &lt;der&gt; Domäneneintrag führt dazu, dass interne Clients keine Verbindung mit den vorgesehenen Diensten herstellen oder die falsche Antwort auf die AutoErmittlung erhalten.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="4d2d9-110">Interne DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="4d2d9-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d2d9-111">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="4d2d9-111">Record type</span></span></th>
<th><span data-ttu-id="4d2d9-112">Hostname</span><span class="sxs-lookup"><span data-stu-id="4d2d9-112">Host name</span></span></th>
<th><span data-ttu-id="4d2d9-113">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="4d2d9-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d2d9-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="4d2d9-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-115">Lyncdiscoverinternal. &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="4d2d9-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-116">Interner FQDN des Webdiensts für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d2d9-117">A (Host, wenn IPv6; AAAA)</span><span class="sxs-lookup"><span data-stu-id="4d2d9-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-118">lyncdiscoverinternal. &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="4d2d9-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-119">Interne Webdienste-IP-Adresse (virtuelle IP-Adresse (VIP-Adresse), wenn Sie ein Lastenausgleichsmodul verwenden) Ihres Director-Pools, falls vorhanden, oder des Front-End-Pools, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4d2d9-120">Sie müssen einen der folgenden externen DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="4d2d9-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="4d2d9-121">Externe DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="4d2d9-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d2d9-122">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="4d2d9-122">Record type</span></span></th>
<th><span data-ttu-id="4d2d9-123">Hostname</span><span class="sxs-lookup"><span data-stu-id="4d2d9-123">Host name</span></span></th>
<th><span data-ttu-id="4d2d9-124">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="4d2d9-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d2d9-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="4d2d9-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-126">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="4d2d9-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-127">Externer Webdienst-FQDN für Ihren Director-Pool, falls vorhanden, oder für Ihren Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d2d9-128">A (Host, wenn IPv6; AAAA)</span><span class="sxs-lookup"><span data-stu-id="4d2d9-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-129">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="4d2d9-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="4d2d9-130">Externe oder öffentliche IP-Adresse des Reverse-Proxys.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4d2d9-131">Externer Datenverkehr führt den Reverse-Proxy durch.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4d2d9-132">Clients für mobile Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) aus verschiedenen Domänen.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="4d2d9-133">Daher wird die CNAME-Umleitung zu verschiedenen Domänen nicht über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="4d2d9-134">Ein DNS-CNAME-Eintrag für lyncdiscover.contoso.com, der an eine Adresse von Director.contoso.net umgeleitet wird, wird beispielsweise nicht über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="4d2d9-135">In einer solchen Topologie muss ein Client für mobile Geräte http für die erste Anforderung verwenden, damit die CNAME-Umleitung über HTTP aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="4d2d9-136">Nachfolgende Anforderungen verwenden dann HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="4d2d9-137">Zur Unterstützung dieses Szenarios müssen Sie den Reverse-Proxy mit einer Webveröffentlichungsregel für Port 80 (http) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="4d2d9-138">Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="4d2d9-139">Die CNAME-Umleitung zur gleichen Domäne wird über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="4d2d9-140">In diesem Fall umfasst das Zertifikat der Zieldomäne die ursprüngliche Domäne.</span><span class="sxs-lookup"><span data-stu-id="4d2d9-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d2d9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d2d9-141">See Also</span></span>


[<span data-ttu-id="4d2d9-142">Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d2d9-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="4d2d9-143">Zertifikatzusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d2d9-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

