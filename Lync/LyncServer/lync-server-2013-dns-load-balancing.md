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
ms.openlocfilehash: 79c2bb8e5bbcb9d00fe687d6f06ac6226a2edf6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528922"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="2a898-102">DNS-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a898-102">DNS load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a898-103">_**Letztes Änderungsstand des Themas:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="2a898-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="2a898-104">Lync Server aktiviert den DNS-Lastenausgleich, eine Softwarelösung, die den Verwaltungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich reduzieren kann.</span><span class="sxs-lookup"><span data-stu-id="2a898-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="2a898-105">Der DNS-Lastenausgleich balanciert den für lync Server eindeutigen Netzwerkdatenverkehr aus, beispielsweise SIP-Datenverkehr und Mediendatenverkehr.</span><span class="sxs-lookup"><span data-stu-id="2a898-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="2a898-106">Wenn Sie den DNS-Lastenausgleich bereitstellen, wird der Verwaltungsaufwand Ihrer Organisation für Hardwarelastenausgleich minimiert.</span><span class="sxs-lookup"><span data-stu-id="2a898-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="2a898-107">Darüber hinaus entfällt die komplexe Problembehandlung zur Beseitigung von Fehlern, die durch eine falsche Konfiguration des Lastenausgleichs für SIP-Datenverkehr entstehen.</span><span class="sxs-lookup"><span data-stu-id="2a898-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="2a898-108">Zudem können Sie Serververbindungen verhindern, sodass Sie Server offline schalten können.</span><span class="sxs-lookup"><span data-stu-id="2a898-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="2a898-109">Der DNS-Lastenausgleich stellt ferner sicher, dass sich durch Hardwarelastenausgleich hervorgerufene Probleme nicht auf den SIP-Datenverkehr auswirken, etwa auf die grundlegende Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="2a898-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="2a898-110">Wenn Sie DNS-Lastenausgleich verwenden, können Sie möglicherweise auch kostengünstigere Hardwaregeräte zum Lastenausgleich anschaffen, da diese nicht für alle Arten von Datenverkehr eingesetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2a898-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="2a898-111">Sie sollten Lastenausgleichsmodule verwenden, die Interoperabilitäts Qualifizierungstests mit lync Server bestanden haben.</span><span class="sxs-lookup"><span data-stu-id="2a898-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="2a898-112">Ausführliche Informationen zum Testen der Lastenausgleichsmodul-Interoperabilität finden Sie unter "lync Server 2010 Lastenausgleichs Partner" unter [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="2a898-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="2a898-113">Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Director-Pools und eigenständige Vermittlungsserverpools unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2a898-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="2a898-114">DNS-Lastenausgleich in Front-End-Pools und Director-Pools</span><span class="sxs-lookup"><span data-stu-id="2a898-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="2a898-p104">Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Director-Pools verwenden. Auch wenn Sie einen DNS-Lastenausgleich konfiguriert haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr von Client zu Server. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a898-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="2a898-118">Auch wenn für diese Pools weiterhin Hardwaregeräte zum Lastenausgleich benötigt werden, müssen diese vornehmlich für den HTTPS-Datenverkehr eingerichtet und verwaltet werden. Dies stellt für Administratoren von Hardwaregeräten zum Lastenausgleich jedoch eine gängige Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="2a898-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="2a898-119">DNS-Lastenausgleich und Unterstützung älterer Clients und Server</span><span class="sxs-lookup"><span data-stu-id="2a898-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="2a898-120">Der DNS-Lastenausgleich unterstützt das automatische Failover nur für Server, auf denen lync Server 2013 oder lync Server 2010 sowie für lync 2013-und lync 2010-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2a898-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="2a898-121">Frühere Versionen von Clients und Office Communications Server können weiterhin mit Pools mit dem DNS-Lastenausgleich verbunden werden, wenn Sie jedoch keine Verbindung mit dem ersten Server herstellen können, auf den der DNS-Lastenausgleich verweist, kann kein Failover auf einen anderen Server im Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2a898-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="2a898-122">Wenn Sie Exchange um verwenden, müssen Sie darüber hinaus mindestens Exchange 2010 SP1 verwenden, um Unterstützung für lync Server DNS-Lastenausgleich zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2a898-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="2a898-123">Wenn Sie eine frühere Version von Exchange verwenden, verfügen die Benutzer nicht über Failoverfunktionen für diese Exchange um Szenarien:</span><span class="sxs-lookup"><span data-stu-id="2a898-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="2a898-124">Wiedergeben von Enterprise-VoIP-Voicemail über ein Telefon</span><span class="sxs-lookup"><span data-stu-id="2a898-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="2a898-125">Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="2a898-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="2a898-126">Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="2a898-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="2a898-127">Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools</span><span class="sxs-lookup"><span data-stu-id="2a898-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="2a898-128">Für die Bereitstellung von DNS-Lastenausgleich in Front-End-Pools und Director-Pools müssen einige zusätzliche Schritte im Zusammenhang mit FQDNs und DNS-Einträgen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2a898-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="2a898-129">Ein Pool, der DNS-Lastenausgleich verwendet, muss über zwei FQDNs verfügen: den regulären Pool-FQDN (beispielsweise pool01.contoso.com), der vom DNS-Lastenausgleich verwendet und in die physischen IP-Adressen der Server im Pool aufgelöst wird, und einen weiteren FQDN für die Webdienste des Pools (z. B. web01.contoso.com), der in die virtuelle IP-Adresse des Pools aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2a898-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="2a898-130">Wenn Sie im Topologie-Generator den DNS-Lastenausgleich für einen Pool bereitstellen möchten, müssen Sie zum Erstellen dieses zusätzlichen FQDN für die Webdienste des Pools das Kontrollkästchen **internen Webdienste Pool-FQDN außer Kraft setzen** aktivieren und in der Seite **Webdienste-URLs für diesen Pool angeben** den FQDN eingeben.</span><span class="sxs-lookup"><span data-stu-id="2a898-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="2a898-p107">Um den vom DNS-Lastenausgleich verwendeten FQDN zu unterstützen, müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. pool01.contoso.com) in die IP-Adressen aller Server im Pool bereitstellen (z. B. 192.168.1.1, 192.168.1.2 usw.). Schließen Sie nur die IP-Adressen von Servern ein, die gegenwärtig bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="2a898-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2a898-133">Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="2a898-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="2a898-134">Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a898-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="2a898-135">Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2a898-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="2a898-136">Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2a898-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="2a898-137">DNS-Lastenausgleich in Edgeserverpools</span><span class="sxs-lookup"><span data-stu-id="2a898-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="2a898-p109">Sie können den DNS-Lastenausgleich in Edgeserverpools bereitstellen. In diesem Fall müssen einige Faktoren berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="2a898-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="2a898-140">Bei Verwendung des DNS-Lastenausgleichs auf Ihren Edgeservern verfügen Sie in den folgenden Szenarien nicht länger über eine Failoverfunktion:</span><span class="sxs-lookup"><span data-stu-id="2a898-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="2a898-141">Partnerverbund mit Organisationen, die Versionen von Office Communications Server, die vor lync Server 2010 veröffentlicht wurden, ausführt.</span><span class="sxs-lookup"><span data-stu-id="2a898-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="2a898-142">Instant Message Exchange mit Benutzern von öffentlichen Instant Messaging-Diensten (im) AOLand Yahoo \! , zusätzlich zu XMPP-basierten Anbietern und Servern wie Google Talk.</span><span class="sxs-lookup"><span data-stu-id="2a898-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="2a898-143">Google Talk ist derzeit der einzige unterstützte XMPP-Partner.</span><span class="sxs-lookup"><span data-stu-id="2a898-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="2a898-144">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2a898-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="2a898-145">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2a898-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="2a898-146">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="2a898-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="2a898-147">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2a898-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="2a898-148">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="2a898-148">has been announced.</span></span> <span data-ttu-id="2a898-149">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2a898-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="2a898-150">Diese Szenarien werden unterstützt, solange alle Edgeserver im Pool verfügbar sind und ausgeführt werden. Wenn jedoch einer der Edgeserver ausfällt, werden Anforderungen für diese Szenarien nicht an einen anderen Edgeserver weitergeleitet, sondern können nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2a898-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="2a898-151">Wenn Sie Exchange um verwenden, müssen Sie mindestens Exchange 2013 verwenden, um Unterstützung für lync Server DNS-Lastenausgleich auf Edge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2a898-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="2a898-152">Wenn Sie eine frühere Version von Exchange verwenden, verfügen die Remotebenutzer nicht über Failoverfunktionen für diese Exchange um Szenarien:</span><span class="sxs-lookup"><span data-stu-id="2a898-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="2a898-153">Wiedergeben von Enterprise-VoIP-Voicemail über ein Telefon</span><span class="sxs-lookup"><span data-stu-id="2a898-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="2a898-154">Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale</span><span class="sxs-lookup"><span data-stu-id="2a898-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="2a898-155">Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="2a898-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="2a898-p112">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a898-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="2a898-158">Bereitstellen von DNS-Lastenausgleich in Edgeserverpools</span><span class="sxs-lookup"><span data-stu-id="2a898-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="2a898-159">Zur Bereitstellung des DNS-Lastenausgleichs für die externe Schnittstelle Ihres Edgeserverpools benötigen Sie die folgenden DNS-Einträge:</span><span class="sxs-lookup"><span data-stu-id="2a898-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="2a898-160">Für den Zugriffs-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="2a898-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="2a898-161">Jeder Eintrag muss den FQDN des Zugriffs-Edgediensts (beispielsweise SIP.contoso.com) in die IP-Adresse des Zugriffs-Edgedienst auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="2a898-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="2a898-162">Für den Webkonferenz-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="2a898-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="2a898-163">Jeder Eintrag muss den FQDN des Webkonferenz-Edgediensts (beispielsweise webconf.contoso.com) in die IP-Adresse des Webkonferenz-Edgedienst auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="2a898-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="2a898-164">Für den Audio/Video-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="2a898-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="2a898-165">Jeder Eintrag muss den FQDN des Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des A/V-Edgedienst auf einem der Edgeserver im Pool auflösen.</span><span class="sxs-lookup"><span data-stu-id="2a898-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="2a898-166">Zur Bereitstellung des DNS-Lastenausgleichs für die interne Schnittstelle Ihres Edgeserverpools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edgeserverpools in die IP-Adressen der einzelnen Server innerhalb des Pools auflöst.</span><span class="sxs-lookup"><span data-stu-id="2a898-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="2a898-167">Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools</span><span class="sxs-lookup"><span data-stu-id="2a898-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="2a898-p116">Sie können den DNS-Lastenausgleich in eigenständigen Vermittlungsserverpools verwenden. Der gesamte SIP- und Mediendatenverkehr wird durch den DNS-Lastenausgleich verteilt.</span><span class="sxs-lookup"><span data-stu-id="2a898-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="2a898-170">Zur Bereitstellung des DNS-Lastenausgleichs in einem Vermittlungsserverpool müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. mediationpool1.contoso.com) in die IP-Adressen aller Server im Pool (z.<B. 192.168.1.1, 192.168.1.2 usw.) bereitstellen.
.</span><span class="sxs-lookup"><span data-stu-id="2a898-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="2a898-171">Blockieren des Datenverkehrs auf einem Server mit DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="2a898-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="2a898-172">Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr auf einem bestimmten Computer blockieren müssen, reicht es nicht aus, die IP-Adresseinträge aus dem Pool-FQDN einfach zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2a898-172">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="2a898-173">Sie müssen auch den DNS-Eintrag für den Computer entfernen.</span><span class="sxs-lookup"><span data-stu-id="2a898-173">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="2a898-174">Beachten Sie, dass lync Server 2013 für den Server-zu-Server-Datenverkehr einen Topologie-fähigen Lastenausgleich verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a898-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="2a898-175">Die Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs der Server in der Topologie zu erhalten und den Datenverkehr automatisch an die Server zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="2a898-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="2a898-176">Um zu verhindern, dass ein Server den Server-zu-Server-Datenverkehr empfängt, müssen Sie den Server aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="2a898-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

