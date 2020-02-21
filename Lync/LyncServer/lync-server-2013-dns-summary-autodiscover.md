---
title: 'Lync Server 2013: DNS-Zusammenfassung-AutoErmittlung'
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
ms.openlocfilehash: b72e52927b8c84f5ad9cb869cd680f057e1618f8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="79e2f-102">DNS-Zusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e2f-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79e2f-103">_**Letztes Änderungsstand des Themas:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="79e2f-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="79e2f-104">Die AutoErmittlung ist ein flexibler Dienst, da Sie die Kommunikation über HTTP oder HTTPS übernimmt.</span><span class="sxs-lookup"><span data-stu-id="79e2f-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="79e2f-105">Um dies zu erreichen, müssen das DNS (Domain Name System) und die Zertifikate, die von Servern verwendet werden, die den AutoErmittlungsdienst hosten, ordnungsgemäß konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="79e2f-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="79e2f-106">Zertifikatanforderungen werden in der [Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)behandelt.</span><span class="sxs-lookup"><span data-stu-id="79e2f-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="79e2f-107">Die DNS-Nachschlage Logik für die lync Server Clients verwendet eine bestimmte Lösungsreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="79e2f-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="79e2f-108">Sie sollten immer sowohl die "lyncdiscoverinternal"-als auch die. &lt;Domäne&gt; und lyncdiscover. &lt;Domäne&gt; in Ihrem DNS.</span><span class="sxs-lookup"><span data-stu-id="79e2f-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="79e2f-109">Ohne "lyncdiscoverinternal". &lt;der&gt; Domäneneintrag führt dazu, dass interne Clients nicht mit den vorgesehenen Diensten verbunden werden oder die falsche Auto Ermittlungs Antwort erhalten.</span><span class="sxs-lookup"><span data-stu-id="79e2f-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="79e2f-110">Interne DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="79e2f-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79e2f-111">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="79e2f-111">Record type</span></span></th>
<th><span data-ttu-id="79e2f-112">Hostname</span><span class="sxs-lookup"><span data-stu-id="79e2f-112">Host name</span></span></th>
<th><span data-ttu-id="79e2f-113">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="79e2f-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79e2f-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="79e2f-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="79e2f-115">"Lyncdiscoverinternal". &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="79e2f-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="79e2f-116">Interner Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="79e2f-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79e2f-117">A (Host, wenn IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="79e2f-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="79e2f-118">"lyncdiscoverinternal". &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="79e2f-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="79e2f-119">Interne Webdienste IP-Adresse (virtuelle IP-Adresse (VIP), wenn Sie einen Lastenausgleich verwenden) Ihres Directorpool, wenn Sie einen haben, oder Ihrer Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="79e2f-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="79e2f-120">Sie müssen einen der folgenden externen DNS-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="79e2f-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="79e2f-121">Externe DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="79e2f-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79e2f-122">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="79e2f-122">Record type</span></span></th>
<th><span data-ttu-id="79e2f-123">Hostname</span><span class="sxs-lookup"><span data-stu-id="79e2f-123">Host name</span></span></th>
<th><span data-ttu-id="79e2f-124">Auflösung in</span><span class="sxs-lookup"><span data-stu-id="79e2f-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79e2f-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="79e2f-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="79e2f-126">lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="79e2f-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="79e2f-127">Externer Webdienste FQDN für Ihren Directorpool, wenn Sie einen haben, oder für Ihre Front-End-Pool, wenn Sie keinen Director haben.</span><span class="sxs-lookup"><span data-stu-id="79e2f-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79e2f-128">A (Host, wenn IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="79e2f-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="79e2f-129">lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="79e2f-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="79e2f-130">Externe oder öffentliche IP-Adresse des Reverse-Proxys.</span><span class="sxs-lookup"><span data-stu-id="79e2f-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="79e2f-131">Externer Datenverkehr wird über den Reverseproxy geleitet.</span><span class="sxs-lookup"><span data-stu-id="79e2f-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="79e2f-132">Clients mobiler Geräte unterstützen nicht mehrere SSL-Zertifikate (Secure Sockets Layer) von verschiedenen Domänen.</span><span class="sxs-lookup"><span data-stu-id="79e2f-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="79e2f-133">Daher wird die CNAME-Umleitung an verschiedene Domänen nicht über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="79e2f-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="79e2f-134">Beispielsweise wird ein DNS-CNAME-Eintrag für "lyncdiscover.contoso.com", der eine Weiterleitung an eine Adresse von "director.contoso.net" vornimmt, nicht über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="79e2f-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="79e2f-135">In einer solchen Topologie muss ein Client für ein mobiles Gerät HTTP für die erste Anforderung verwenden, sodass die CNAME-Umleitung über HTTP aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="79e2f-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="79e2f-136">Für die nachfolgenden Anforderungen wird dann HTTPS verwendet.</span><span class="sxs-lookup"><span data-stu-id="79e2f-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="79e2f-137">Um dieses Szenario zu unterstützen, müssen Sie den Reverseproxy mit einer Webveröffentlichungsregel für Port 80 (HTTP) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="79e2f-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="79e2f-138">Ausführliche Informationen finden Sie unter "So erstellen Sie eine Webveröffentlichungsregel für Port 80" unter <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="79e2f-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="79e2f-139">Die CNAME-Umleitung an dieselbe Domäne wird über HTTPS unterstützt.</span><span class="sxs-lookup"><span data-stu-id="79e2f-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="79e2f-140">In diesem Fall deckt das Zertifikat der Zieldomäne die ursprüngliche Domäne ab.</span><span class="sxs-lookup"><span data-stu-id="79e2f-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79e2f-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79e2f-141">See Also</span></span>


[<span data-ttu-id="79e2f-142">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e2f-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="79e2f-143">Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79e2f-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

