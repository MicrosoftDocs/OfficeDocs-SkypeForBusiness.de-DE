---
title: 'Lync Server 2013: DNS-Zusammenfassung-AutoErmittlung'
description: 'Lync Server 2013: DNS-Zusammenfassung – AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574281"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="2b189-103">DNS-Zusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b189-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b189-104">_**Letztes Änderungsstand des Themas:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="2b189-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="2b189-105">Die AutoErmittlung ist ein flexibler Dienst, da Sie die Kommunikation über HTTP oder HTTPS übernimmt.</span><span class="sxs-lookup"><span data-stu-id="2b189-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="2b189-106">Um dies zu erreichen, müssen das DNS (Domain Name System) und die Zertifikate, die von Servern verwendet werden, die den AutoErmittlungsdienst hosten, ordnungsgemäß konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2b189-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="2b189-107">Zertifikatanforderungen werden in der [Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)behandelt.</span><span class="sxs-lookup"><span data-stu-id="2b189-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b189-108">Die DNS-Nachschlage Logik für die lync Server Clients verwendet eine bestimmte Lösungsreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="2b189-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="2b189-109">Sie sollten immer sowohl die "lyncdiscoverinternal"-als auch die. &lt; Domäne &gt; und lyncdiscover. &lt; Domäne &gt; in Ihrem DNS.</span><span class="sxs-lookup"><span data-stu-id="2b189-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="2b189-110">Ohne "lyncdiscoverinternal". &lt; der Domäneneintrag führt dazu, dass &gt; interne Clients nicht mit den vorgesehenen Diensten verbunden werden oder die falsche Auto Ermittlungs Antwort erhalten.</span><span class="sxs-lookup"><span data-stu-id="2b189-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="2b189-111">Interne DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="2b189-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b189-112">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="2b189-112">Record type</span></span></th>
<th><span data-ttu-id="2b189-113">Hostname</span><span class="sxs-lookup"><span data-stu-id="2b189-113">Host name</span></span></th>
<th><span data-ttu-id="2b189-114">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="2b189-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b189-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b189-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="2b189-116">"Lyncdiscoverinternal". &lt; Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="2b189-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="2b189-117">Interner Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="2b189-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b189-118">A (Host, wenn IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="2b189-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="2b189-119">"lyncdiscoverinternal". &lt; Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="2b189-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="2b189-120">Interne Webdienste IP-Adresse (virtuelle IP-Adresse (VIP), wenn Sie einen Lastenausgleich verwenden) Ihres Directorpool, wenn Sie einen haben, oder Ihrer Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="2b189-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2b189-121">Sie müssen einen der folgenden externen DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="2b189-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="2b189-122">Externe DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="2b189-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b189-123">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="2b189-123">Record type</span></span></th>
<th><span data-ttu-id="2b189-124">Hostname</span><span class="sxs-lookup"><span data-stu-id="2b189-124">Host name</span></span></th>
<th><span data-ttu-id="2b189-125">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="2b189-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b189-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="2b189-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="2b189-127">lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2b189-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="2b189-128">Externer Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="2b189-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b189-129">A (Host, wenn IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="2b189-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="2b189-130">lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="2b189-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="2b189-131">Externe oder öffentliche IP-Adresse des Reverse-Proxys.</span><span class="sxs-lookup"><span data-stu-id="2b189-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2b189-132">Externer Datenverkehr wird über den Reverseproxy geleitet.</span><span class="sxs-lookup"><span data-stu-id="2b189-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2b189-133">Clients mobiler Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) von verschiedenen Domänen.</span><span class="sxs-lookup"><span data-stu-id="2b189-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="2b189-134">Daher wird die CNAME-Umleitung an verschiedene Domänen nicht über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b189-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="2b189-135">Beispielsweise wird ein DNS-CNAME-Eintrag für "lyncdiscover.contoso.com", der eine Weiterleitung an eine Adresse von "director.contoso.net" vornimmt, nicht über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b189-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="2b189-136">In einer solchen Topologie muss ein Client für ein mobiles Gerät HTTP für die erste Anforderung verwenden, sodass die CNAME-Umleitung über HTTP aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2b189-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="2b189-137">Für die nachfolgenden Anforderungen wird dann HTTPS verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b189-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="2b189-138">Um dieses Szenario zu unterstützen, müssen Sie den Reverseproxy mit einer Webveröffentlichungsregel für Port 80 (HTTP) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2b189-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="2b189-139">Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2b189-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="2b189-140">Die CNAME-Umleitung an dieselbe Domäne wird über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b189-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="2b189-141">In diesem Fall deckt das Zertifikat der Zieldomäne die ursprüngliche Domäne ab.</span><span class="sxs-lookup"><span data-stu-id="2b189-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b189-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b189-142">See Also</span></span>


[<span data-ttu-id="2b189-143">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b189-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="2b189-144">Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b189-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

