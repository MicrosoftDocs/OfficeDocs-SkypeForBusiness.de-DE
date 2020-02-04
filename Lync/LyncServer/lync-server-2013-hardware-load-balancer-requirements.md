---
title: 'Lync Server 2013: Anforderungen an das Hardwaregerät zum Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="7cadc-102">Anforderungen an das Hardwaregerät zum Lastenausgleich für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cadc-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cadc-103">_**Letztes Änderungsdatum des Themas:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="7cadc-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="7cadc-104">Die von lync Server 2013 skalierte konsolidierte Edge-Topologie ist für den DNS-Lastenausgleich für neue Bereitstellungen optimiert, die in erster Linie mit anderen Organisationen, die lync Server verwenden, verbündet sind.</span><span class="sxs-lookup"><span data-stu-id="7cadc-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="7cadc-105">Wenn für eines der folgenden Szenarien eine hohe Verfügbarkeit erforderlich ist, muss ein Hardware-Lastenausgleichsmodul für Edge-Server-Pools verwendet werden, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="7cadc-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="7cadc-106">Föderation mit Organisationen, die Office Communications Server 2007 R2 oder Office Communications Server 2007 verwenden</span><span class="sxs-lookup"><span data-stu-id="7cadc-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="7cadc-107">Exchange um für Remotebenutzer mit Exchange um vor Exchange 2010 mit SP1</span><span class="sxs-lookup"><span data-stu-id="7cadc-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="7cadc-108">Verbindung mit Benutzern öffentlicher Chatdienste</span><span class="sxs-lookup"><span data-stu-id="7cadc-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7cadc-p102">Das Verfahren, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden, wird nicht unterstützt. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cadc-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7cadc-p103">Wenn Sie ein Hardwaregerät zum Lastenausgleich einsetzen, muss der Lastenausgleich für Verbindungen mit dem internen Netzwerk so konfiguriert werden, dass nur für den Datenverkehr zu Servern, auf denen der Zugriffs-Edgedienst und der A/V-Edgedienst ausgeführt werden, ein Lastenausgleich stattfindet. Es kann kein Lastenausgleich für den Datenverkehr zum internen Webkonferenz-Edgedienst oder zum internen XMPP-Proxydienst durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7cadc-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7cadc-113">Die direkte Server Rückgabe (DSR)-NAT wird von lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7cadc-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="7cadc-114">Wenn Sie feststellen möchten, ob Ihr Hardwarelastenausgleich die erforderlichen Features unterstützt, die von lync Server 2013 benötigt werden, lesen Sie " [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)lync Server 2010 Load Balancer Partners" unter.</span><span class="sxs-lookup"><span data-stu-id="7cadc-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="7cadc-115">Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="7cadc-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="7cadc-116">Im folgenden finden Sie die Anforderungen des Hardwarelastenausgleichs für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="7cadc-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="7cadc-p104">Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443. Mit diesem Algorithmus werden mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="7cadc-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="7cadc-119">Deaktivieren Sie den Nagle-Algorithmus für TCP für den Bereich der externen Ports 50.000 bis 59.999.</span><span class="sxs-lookup"><span data-stu-id="7cadc-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="7cadc-120">Verwenden Sie keine Netzwerkadressenübersetzung für die interne oder externe Firewall.</span><span class="sxs-lookup"><span data-stu-id="7cadc-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="7cadc-121">Die interne Schnittstelle für Edge muss sich in einem anderen Netzwerk befinden als die externe Schnittstelle des Edge-Servers, und das Routing zwischen diesen muss deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="7cadc-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="7cadc-122">Die externe Schnittstelle des Edgeserver, auf dem der A/V-Edgedienst ausgeführt wird, muss öffentlich routingfähige IP-Adressen und keine NAT-oder Portübersetzung für beliebige externe IP-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cadc-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="7cadc-123">Anforderungen an das Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="7cadc-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="7cadc-124">Cookie-basierte Affinitäts Anforderungen werden in lync Server 2013 für Webdienste stark reduziert.</span><span class="sxs-lookup"><span data-stu-id="7cadc-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="7cadc-125">Wenn Sie lync Server 2013 bereitstellen und keine lync Server 2010-Front-End-Server oder Front-End-Pools beibehalten, benötigen Sie keine Cookie-basierte Persistenz.</span><span class="sxs-lookup"><span data-stu-id="7cadc-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="7cadc-126">Wenn Sie jedoch vorübergehend oder dauerhaft alle lync Server 2010-Front-End-Server oder Front-End-Pools behalten, verwenden Sie weiterhin Cookie-basierte Persistenz, während Sie für lync Server 2010 bereitgestellt und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7cadc-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cadc-127"><STRONG>Wenn Sie sich entscheiden, die cookiebasierte Persistenz zu verwenden, obwohl dies für Ihre</STRONG>-Bereitstellung nicht erforderlich ist, hat dies keine negative Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="7cadc-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="7cadc-128">Für Bereitstellungen, in denen die cookiebasierte Affinität **nicht verwendet** wird:</span><span class="sxs-lookup"><span data-stu-id="7cadc-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="7cadc-129">Legen Sie für die Veröffentlichungsregel des Reverseproxys für Port 4443 **Forward host header** auf „True“ fest.</span><span class="sxs-lookup"><span data-stu-id="7cadc-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="7cadc-130">Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7cadc-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="7cadc-131">Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:</span><span class="sxs-lookup"><span data-stu-id="7cadc-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="7cadc-p107">Legen Sie für die Veröffentlichungsregel des Reverseproxys für Port 4443 **Forward host header** auf „True“ fest. Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7cadc-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="7cadc-134">Das Cookie für das Hardwaregerät zum Lastenausgleich DARF NICHT als „httpOnly“ gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="7cadc-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="7cadc-135">Das Cookie für das Hardwaregerät zum Lastenausgleich DARF KEINE Ablaufzeit haben.</span><span class="sxs-lookup"><span data-stu-id="7cadc-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="7cadc-136">Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS den Namen **MS-WSMAN** haben (dies ist der von den Webdiensten erwartete Wert, der nicht geändert werden kann).</span><span class="sxs-lookup"><span data-stu-id="7cadc-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="7cadc-p108">Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS in jeder HTTP-Antwort festgelegt sein, für die die eingehende HTTP-Anforderung kein Cookie enthielt, unabhängig davon, ob für eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung bereits ein Cookie abgerufen wurde. Wenn der Lastenausgleich das Einfügen von Cookies so optimiert, dass sie nur einmal pro TCP-Verbindung erfolgt, darf diese Optimierung NICHT verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7cadc-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cadc-139">Typische Hardware-Lastenausgleichsmodul-Konfigurationen verwenden eine Quell Adress Affinität und eine 20-minütige TCP-Sitzungslebensdauer, was für lync Server-und lync 2013-Clients in Ordnung ist, da der Sitzungszustand über die Clientnutzung und/oder die Anwendungs Interaktion verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="7cadc-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="7cadc-140">Wenn Sie mobile Geräte bereitstellen, muss das Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).</span><span class="sxs-lookup"><span data-stu-id="7cadc-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7cadc-p109">F5-Hardwaregeräte zum Lastenausgleich sind mit einer Funktion namens OneConnect ausgestattet, mit der sichergestellt wird, dass für jede Anforderung in einer TCP-Verbindung ein individueller Lastenausgleich vorgenommen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass der Hersteller des Hardwaregeräts für den Lastenausgleich dieselbe Funktion unterstützt. Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich. F5 stellt hierfür bestimmte Einstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="7cadc-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="7cadc-145">Details zu Lastenausgleichsgeräten von Drittanbietern finden Sie unter<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="7cadc-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="7cadc-146">Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Director- und Front-End-Pool-Webdienste aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="7cadc-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="7cadc-147">Legen Sie für interne Webdienste VIPs\_die Quell-addr-Persistenz (interner Port 80, 443) auf dem Hardware-Lastenausgleichsmodul ab.</span><span class="sxs-lookup"><span data-stu-id="7cadc-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="7cadc-148">Bei lync Server 2013 bedeutet "\_Quell-addr-Persistenz", dass mehrere Verbindungen, die von einer einzelnen IP-Adresse stammen, immer an einen Server gesendet werden, um den Sitzungszustand beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="7cadc-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="7cadc-149">Legen Sie ein TCP-Leerlauftimeout von 1.800 Sekunden fest.</span><span class="sxs-lookup"><span data-stu-id="7cadc-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="7cadc-p111">Erstellen Sie für die Firewall zwischen dem Reverseproxy und dem Hardwaregerät zum Lastenausgleich des nächsten Hoppools eine Regel zum Zulassen von https:-Datenverkehr an Port 4443 – vom Reverseproxy zum Hardwaregerät zum Lastenausgleich. Das Hardwaregerät zum Lastenausgleich muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7cadc-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7cadc-152">Weitere Informationen zur Konfiguration des Hardwarelastenausgleichs finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Zusammenfassung – skalierter konsolidierter Edge mit Hardwarelastenausgleichs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7cadc-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="7cadc-153">Zusammenfassung der Affinitätsanforderungen an das Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="7cadc-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cadc-154">Client-/Benutzerstandort</span><span class="sxs-lookup"><span data-stu-id="7cadc-154">Client/user location</span></span></th>
<th><span data-ttu-id="7cadc-155">Affinitätsanforderungen an den externen Webdienste-FQDN</span><span class="sxs-lookup"><span data-stu-id="7cadc-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="7cadc-156">Affinitätsanforderungen an den internen Webdienste-FQDN</span><span class="sxs-lookup"><span data-stu-id="7cadc-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cadc-157">Lync Web App (interne und externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="7cadc-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="7cadc-158">Mobiles Gerät (interne und externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="7cadc-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="7cadc-159">Keine Affinität</span><span class="sxs-lookup"><span data-stu-id="7cadc-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="7cadc-160">Quelladressenaffinität</span><span class="sxs-lookup"><span data-stu-id="7cadc-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cadc-161">Lync Web App (nur externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="7cadc-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="7cadc-162">Mobiles Gerät (interne und externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="7cadc-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="7cadc-163">Keine Affinität</span><span class="sxs-lookup"><span data-stu-id="7cadc-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="7cadc-164">Quelladressenaffinität</span><span class="sxs-lookup"><span data-stu-id="7cadc-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cadc-165">Lync Web App (nur interne Benutzer)</span><span class="sxs-lookup"><span data-stu-id="7cadc-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="7cadc-166">Mobiles Gerät (nicht bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7cadc-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="7cadc-167">Keine Affinität</span><span class="sxs-lookup"><span data-stu-id="7cadc-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="7cadc-168">Quelladressenaffinität</span><span class="sxs-lookup"><span data-stu-id="7cadc-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="7cadc-169">Portüberwachung für Hardwaregeräte zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="7cadc-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="7cadc-170">Sie definieren die Portüberwachung für Hardwaregeräte zum Lastenausgleich (Hardware Load Balancers, HLB), um festzustellen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7cadc-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="7cadc-171">Wenn beispielsweise der Front-End-Server Dienst (RTCSRV) angehalten wird, weil der Front-End-Server oder der Front-End-Pool fehlschlägt, sollte die HLB-Überwachung auch den Empfang von Datenverkehr über die Webdienste beenden.</span><span class="sxs-lookup"><span data-stu-id="7cadc-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="7cadc-172">Sie können die HLB-Portüberwachung implementieren, um Folgendes zu überwachen:</span><span class="sxs-lookup"><span data-stu-id="7cadc-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="7cadc-173">Front-End-Server-Benutzer Pool – HLB-interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cadc-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cadc-174">Virtuelle IP/Port</span><span class="sxs-lookup"><span data-stu-id="7cadc-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="7cadc-175">Knoten Port</span><span class="sxs-lookup"><span data-stu-id="7cadc-175">Node Port</span></span></th>
<th><span data-ttu-id="7cadc-176">Knoten Computer/Monitor</span><span class="sxs-lookup"><span data-stu-id="7cadc-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="7cadc-177">Persistenzprofil</span><span class="sxs-lookup"><span data-stu-id="7cadc-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="7cadc-178">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cadc-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cadc-179">&lt;Pool&gt;Web-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="7cadc-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="7cadc-180">443</span><span class="sxs-lookup"><span data-stu-id="7cadc-180">443</span></span></p></td>
<td><p><span data-ttu-id="7cadc-181">443</span><span class="sxs-lookup"><span data-stu-id="7cadc-181">443</span></span></p></td>
<td><p><span data-ttu-id="7cadc-182">Front-End</span><span class="sxs-lookup"><span data-stu-id="7cadc-182">Front End</span></span></p>
<p><span data-ttu-id="7cadc-183">5061</span><span class="sxs-lookup"><span data-stu-id="7cadc-183">5061</span></span></p></td>
<td><p><span data-ttu-id="7cadc-184">Quelle</span><span class="sxs-lookup"><span data-stu-id="7cadc-184">Source</span></span></p></td>
<td><p><span data-ttu-id="7cadc-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="7cadc-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cadc-186">&lt;Pool&gt;Web-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="7cadc-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="7cadc-187">80</span><span class="sxs-lookup"><span data-stu-id="7cadc-187">80</span></span></p></td>
<td><p><span data-ttu-id="7cadc-188">80</span><span class="sxs-lookup"><span data-stu-id="7cadc-188">80</span></span></p></td>
<td><p><span data-ttu-id="7cadc-189">Front-End</span><span class="sxs-lookup"><span data-stu-id="7cadc-189">Front End</span></span></p>
<p><span data-ttu-id="7cadc-190">5061</span><span class="sxs-lookup"><span data-stu-id="7cadc-190">5061</span></span></p></td>
<td><p><span data-ttu-id="7cadc-191">Quelle</span><span class="sxs-lookup"><span data-stu-id="7cadc-191">Source</span></span></p></td>
<td><p><span data-ttu-id="7cadc-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="7cadc-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="7cadc-193">Front-End-Server-Benutzer Pool – HLB-externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cadc-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cadc-194">Virtuelle IP/Port</span><span class="sxs-lookup"><span data-stu-id="7cadc-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="7cadc-195">Knoten Port</span><span class="sxs-lookup"><span data-stu-id="7cadc-195">Node Port</span></span></th>
<th><span data-ttu-id="7cadc-196">Knoten Computer/Monitor</span><span class="sxs-lookup"><span data-stu-id="7cadc-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="7cadc-197">Persistenzprofil</span><span class="sxs-lookup"><span data-stu-id="7cadc-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="7cadc-198">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cadc-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cadc-199">&lt;Pool&gt;web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="7cadc-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="7cadc-200">443</span><span class="sxs-lookup"><span data-stu-id="7cadc-200">443</span></span></p></td>
<td><p><span data-ttu-id="7cadc-201">4443</span><span class="sxs-lookup"><span data-stu-id="7cadc-201">4443</span></span></p></td>
<td><p><span data-ttu-id="7cadc-202">Front-End</span><span class="sxs-lookup"><span data-stu-id="7cadc-202">Front End</span></span></p>
<p><span data-ttu-id="7cadc-203">5061</span><span class="sxs-lookup"><span data-stu-id="7cadc-203">5061</span></span></p></td>
<td><p><span data-ttu-id="7cadc-204">Keine</span><span class="sxs-lookup"><span data-stu-id="7cadc-204">None</span></span></p></td>
<td><p><span data-ttu-id="7cadc-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="7cadc-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cadc-206">&lt;Pool&gt;web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="7cadc-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="7cadc-207">80</span><span class="sxs-lookup"><span data-stu-id="7cadc-207">80</span></span></p></td>
<td><p><span data-ttu-id="7cadc-208">8080</span><span class="sxs-lookup"><span data-stu-id="7cadc-208">8080</span></span></p></td>
<td><p><span data-ttu-id="7cadc-209">Front-End</span><span class="sxs-lookup"><span data-stu-id="7cadc-209">Front End</span></span></p>
<p><span data-ttu-id="7cadc-210">5061</span><span class="sxs-lookup"><span data-stu-id="7cadc-210">5061</span></span></p></td>
<td><p><span data-ttu-id="7cadc-211">Keine</span><span class="sxs-lookup"><span data-stu-id="7cadc-211">None</span></span></p></td>
<td><p><span data-ttu-id="7cadc-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="7cadc-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

