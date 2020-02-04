---
title: 'Lync Server 2013: DNS-Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="d7238-102">DNS-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7238-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7238-103">_**Letztes Änderungsdatum des Themas:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="d7238-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="d7238-104">Lync Server ermöglicht den DNS-Lastenausgleich, eine Softwarelösung, die den Verwaltungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich verringern kann.</span><span class="sxs-lookup"><span data-stu-id="d7238-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="d7238-105">Der DNS-Lastenausgleich balanciert den Netzwerkdatenverkehr, der für lync Server eindeutig ist, wie etwa SIP-Datenverkehr und Mediendatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="d7238-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="d7238-106">Wenn Sie den DNS-Lastenausgleich bereitstellen, wird der Verwaltungsaufwand Ihres Unternehmens für Hardware-Lastenausgleichs Komponenten minimiert.</span><span class="sxs-lookup"><span data-stu-id="d7238-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="d7238-107">Darüber hinaus wird eine komplexe Problembehandlung von Problemen im Zusammenhang mit der Fehlkonfiguration von Last-Balancern für den SIP-Datenverkehr eliminiert.</span><span class="sxs-lookup"><span data-stu-id="d7238-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="d7238-108">Sie können auch Serververbindungen verhindern, damit Sie Server offline schalten können.</span><span class="sxs-lookup"><span data-stu-id="d7238-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="d7238-109">Durch den DNS-Lastenausgleich wird auch sichergestellt, dass die Probleme mit dem Hardwarelastenausgleich keine Auswirkungen auf Elemente des SIP-Datenverkehrs wie einfaches Anrufrouting haben.</span><span class="sxs-lookup"><span data-stu-id="d7238-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="d7238-110">Wenn Sie den DNS-Lastenausgleich verwenden, sind Sie möglicherweise auch in der Lage, kostengünstigere Hardwarelastenausgleichs zu erwerben, als wenn Sie den Hardwarelastenausgleich für alle Arten von Datenverkehr verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="d7238-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="d7238-111">Sie sollten Load-Balancer verwenden, die Interoperabilitäts Qualifizierungstests mit lync Server bestanden haben.</span><span class="sxs-lookup"><span data-stu-id="d7238-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="d7238-112">Ausführliche Informationen zum Testen der Lastenausgleichsmodul-Interoperabilität finden Sie unter "lync Server 2010 Load [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)Balancer Partners" unter.</span><span class="sxs-lookup"><span data-stu-id="d7238-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="d7238-113">Der DNS-Lastenausgleich wird für Front-End-Pools, Edge-Server-Pools, Director-Pools und eigenständige Vermittlungsserver Pools unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d7238-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="d7238-114">DNS-Lastenausgleich in Front-End-Pools und Director-Pools</span><span class="sxs-lookup"><span data-stu-id="d7238-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="d7238-115">Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Director-Pools verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7238-115">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="d7238-116">Wenn der DNS-Lastenausgleich bereitgestellt wird, müssen Sie weiterhin Hardwarelastenausgleichs für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="d7238-116">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="d7238-117">Das Hardware-Lastenausgleichsmodul wird für HTTPS-Datenverkehr von Clients über Ports 443 und 80 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7238-117">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="d7238-118">Obwohl Sie weiterhin Hardwarelastenausgleichs für diese Pools benötigen, werden deren Einrichtung und Verwaltung in erster Linie für den HTTPS-Datenverkehr verwendet, den die Administratoren von Hardwarelastenausgleich-Geräten gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="d7238-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="d7238-119">DNS-Lastenausgleich und Unterstützung älterer Clients und Server</span><span class="sxs-lookup"><span data-stu-id="d7238-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="d7238-120">Der DNS-Lastenausgleich unterstützt das automatische Failover nur für Server mit lync Server 2013 oder lync Server 2010 sowie für lync 2013-und lync 2010-Clients.</span><span class="sxs-lookup"><span data-stu-id="d7238-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="d7238-121">Frühere Versionen von Clients und Office Communications Server können weiterhin mit Pools verbunden werden, auf denen der DNS-Lastenausgleich ausgeführt wird, doch wenn Sie keine Verbindung mit dem ersten Server herstellen können, auf den der DNS-Lastenausgleich verweist, kann ein Failover zu einem anderen Server im Pool nicht durchgeführt werden. .</span><span class="sxs-lookup"><span data-stu-id="d7238-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="d7238-122">Wenn Sie Exchange um verwenden, müssen Sie darüber hinaus mindestens Exchange 2010 SP1 verwenden, um Unterstützung für den DNS-Lastenausgleich von lync Server zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d7238-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="d7238-123">Wenn Sie eine frühere Version von Exchange verwenden, verfügen Ihre Benutzer nicht über Failoverfunktionen für diese Exchange um-Szenarien:</span><span class="sxs-lookup"><span data-stu-id="d7238-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="d7238-124">Wiedergeben Ihrer Enterprise-Voicemail auf dem Telefon</span><span class="sxs-lookup"><span data-stu-id="d7238-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="d7238-125">Übertragen von Anrufen von einer automatischen Exchange UM-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="d7238-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="d7238-126">Alle anderen Exchange um-Szenarien funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="d7238-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="d7238-127">Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools</span><span class="sxs-lookup"><span data-stu-id="d7238-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="d7238-128">Für die Bereitstellung des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools müssen Sie einige zusätzliche Schritte mit FQDNs und DNS-Einträgen durchführen.</span><span class="sxs-lookup"><span data-stu-id="d7238-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="d7238-129">Ein Pool, der den DNS-Lastenausgleich verwendet, muss zwei FQDNs aufweisen: den regulären Pool-FQDN, der vom DNS-Lastenausgleich (wie pool01.contoso.com) verwendet wird, und er wird in die physischen IPS der Server im Pool aufgelöst, und ein anderer FQDN für die Webdienste des Pools (wie web01.contoso.com), der in die virtuelle IP-Adresse des Pools aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d7238-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="d7238-130">Wenn Sie im Topologie-Generator den DNS-Lastenausgleich für einen Pool bereitstellen möchten, müssen Sie zum Erstellen dieses zusätzlichen FQDN für die Webdienste des Pools das Kontrollkästchen **FQDN des internen Webdienste-Pool außer Kraft setzen** aktivieren und den FQDN in der Seite **Geben Sie die Webdienste-URLs für diesen Pool angeben** ein.</span><span class="sxs-lookup"><span data-stu-id="d7238-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="d7238-131">Zur Unterstützung des vom DNS-Lastenausgleich verwendeten FQDN müssen Sie DNS bereitstellen, um den Pool-FQDN (wie pool01.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.).</span><span class="sxs-lookup"><span data-stu-id="d7238-131">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="d7238-132">Sie sollten nur die IP-Adressen der Server einbeziehen, die derzeit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d7238-132">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d7238-133">Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="d7238-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d7238-134">Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7238-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="d7238-135">Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="d7238-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="d7238-136">Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="d7238-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="d7238-137">DNS-Lastenausgleich auf Edgeserver-Pools</span><span class="sxs-lookup"><span data-stu-id="d7238-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="d7238-138">Sie können den DNS-Lastenausgleich auf Edgeserver-Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d7238-138">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="d7238-139">Wenn Sie dies tun, müssen Sie sich mit einigen Überlegungen vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="d7238-139">If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="d7238-140">Die Verwendung des DNS-Lastenausgleichs auf Ihren Edge-Servern führt in den folgenden Szenarien zu einem Verlust der Failover-Fähigkeit:</span><span class="sxs-lookup"><span data-stu-id="d7238-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="d7238-141">Föderation mit Organisationen, die Versionen von Office Communications Server ausführen, die vor lync Server 2010 veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="d7238-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="d7238-142">Direkter Nachrichtenaustausch mit Benutzern von öffentlichen Instant Messaging-Diensten (im) AOLand\!Yahoo, zusätzlich zu XMPP-basierten Anbietern und Servern wie Google Talk.</span><span class="sxs-lookup"><span data-stu-id="d7238-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="d7238-143">Google Talk ist derzeit der einzige unterstützte XMPP-Partner.</span><span class="sxs-lookup"><span data-stu-id="d7238-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d7238-144">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d7238-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d7238-145">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="d7238-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d7238-146">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="d7238-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="d7238-147">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="d7238-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d7238-148">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="d7238-148">has been announced.</span></span> <span data-ttu-id="d7238-149">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d7238-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="d7238-150">Diese Szenarien funktionieren so lange, wie alle Edgeserver im Pool ausgeführt werden, aber wenn ein Edgeserver nicht verfügbar ist, werden alle Anforderungen für diese Szenarien, die an ihn gesendet werden, nicht mehr an einen anderen Edgeserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d7238-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="d7238-151">Wenn Sie Exchange um verwenden, müssen Sie mindestens Exchange 2013 verwenden, um Unterstützung für den lync Server-DNS-Lastenausgleich auf Edge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d7238-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="d7238-152">Wenn Sie eine frühere Version von Exchange verwenden, verfügen die Remotebenutzer nicht über Failoverfunktionen für diese Exchange um-Szenarien:</span><span class="sxs-lookup"><span data-stu-id="d7238-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="d7238-153">Wiedergeben Ihrer Enterprise-Voicemail auf dem Telefon</span><span class="sxs-lookup"><span data-stu-id="d7238-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="d7238-154">Übertragen von Anrufen von einer automatischen Exchange UM-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="d7238-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="d7238-155">Alle anderen Exchange um-Szenarien funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="d7238-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="d7238-156">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7238-156">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="d7238-157">Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7238-157">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="d7238-158">Bereitstellen des DNS-Lastenausgleichs auf Edgeserver-Pools</span><span class="sxs-lookup"><span data-stu-id="d7238-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="d7238-159">Zum Bereitstellen des DNS-Lastenausgleichs auf der externen Schnittstelle Ihres Edge-Server Pools benötigen Sie die folgenden DNS-Einträge:</span><span class="sxs-lookup"><span data-stu-id="d7238-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="d7238-160">Für den Access Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="d7238-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="d7238-161">Jeder Eintrag muss den FQDN des Access-Edgedienst (beispielsweise SIP.contoso.com) in die IP-Adresse des Access Edge-Diensts auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="d7238-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="d7238-162">Für den Web Conferencing Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="d7238-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="d7238-163">Jeder Eintrag muss den FQDN des Webkonferenz-Edgedienst (beispielsweise webconf.contoso.com) in die IP-Adresse des Webkonferenz-Edgedienst auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="d7238-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="d7238-164">Für den Audio/Video Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="d7238-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="d7238-165">Jeder Eintrag muss den FQDN des Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des A/V Edge-Diensts auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="d7238-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="d7238-166">Zum Bereitstellen des DNS-Lastenausgleichs auf der internen Schnittstelle Ihres Edge-Server Pools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edge-Server Pools in die IP-Adresse jedes Servers im Pool auflöst.</span><span class="sxs-lookup"><span data-stu-id="d7238-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="d7238-167">Verwenden des DNS-Lastenausgleichs in Vermittlungs Server Pools</span><span class="sxs-lookup"><span data-stu-id="d7238-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="d7238-168">Sie können den DNS-Lastenausgleich für eigenständige Vermittlungs Server Pools verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7238-168">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="d7238-169">Der gesamte SIP-und Mediendatenverkehr wird durch den DNS-Lastenausgleich ausgeglichen.</span><span class="sxs-lookup"><span data-stu-id="d7238-169">All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="d7238-170">Zum Bereitstellen des DNS-Lastenausgleichs in einem Vermittlungs Server Pool müssen Sie DNS bereitstellen, um den Pool-FQDN (beispielsweise mediationpool1.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.).</span><span class="sxs-lookup"><span data-stu-id="d7238-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="d7238-171">Blockieren des Datenverkehrs auf einem Server mit DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="d7238-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="d7238-p117">Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen.</span><span class="sxs-lookup"><span data-stu-id="d7238-p117">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="d7238-174">Beachten Sie, dass lync Server 2013 für den Server-zu-Server-Datenverkehr Topologie-bewusste Lastenverteilung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7238-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="d7238-175">Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie abzurufen und den Datenverkehr automatisch auf die Server zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="d7238-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="d7238-176">Wenn Sie verhindern möchten, dass ein Server Server-zu-Server-Datenverkehr empfängt, müssen Sie den Server aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="d7238-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

