---
title: Lync Server 2013 Anforderungen an das Hardwaregerät zum Lastenausgleich
description: Lync Server 2013 Anforderungen an das Hardwaregerät zum Lastenausgleich.
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
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552921"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="1d2f0-103">Anforderungen an das Hardware Gerät zum Lastenausgleich für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d2f0-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d2f0-104">_**Letztes Änderungsstand des Themas:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="1d2f0-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="1d2f0-105">Die lync Server 2013 skalierte konsolidierte Edge-Topologie ist für den DNS-Lastenausgleich für neue Bereitstellungen, die hauptsächlich mit anderen Organisationen mit lync Server zusammenfassen, optimiert.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="1d2f0-106">Wenn für eines der folgenden Szenarien hohe Verfügbarkeit erforderlich ist, muss ein Hardwaregerät zum Lastenausgleich in Edgeserver Pools für Folgendes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="1d2f0-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="1d2f0-107">Partnerverbund mit Organisationen, die Office Communications Server 2007 R2 oder Office Communications Server 2007 verwenden</span><span class="sxs-lookup"><span data-stu-id="1d2f0-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="1d2f0-108">Exchange um für Remotebenutzer, die Exchange um vor dem Exchange 2010 mit SP1 verwenden</span><span class="sxs-lookup"><span data-stu-id="1d2f0-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="1d2f0-109">Verbindung mit Benutzern öffentlicher Chatdienste</span><span class="sxs-lookup"><span data-stu-id="1d2f0-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1d2f0-p102">Es wird nicht unterstützt, für eine Schnittstelle den DNS-Lastenausgleich und für eine andere Schnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden. Sie müssen entweder für beide Schnittstellen ein Hardwaregerät zum Lastenausgleich oder für beide Schnittstellen den DNS-Lastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1d2f0-p103">Wenn Sie ein Hardwaregerät zum Lastenausgleich einsetzen, muss der Lastenausgleich für Verbindungen mit dem internen Netzwerk so konfiguriert werden, dass nur für den Datenverkehr zu Servern, auf denen der Zugriffs-Edgedienst und der A/V-Edgedienst ausgeführt werden, ein Lastenausgleich stattfindet. Es kann kein Lastenausgleich für den Datenverkehr zum internen Webkonferenz-Edgedienst oder zum internen XMPP-Proxydienst durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1d2f0-114">Die DSR-NAT (Direct Server Return) wird von lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="1d2f0-115">Informationen zum ermitteln, ob Ihr Hardwaregerät zum Lastenausgleich die für lync Server 2013 erforderlichen Features unterstützt, finden Sie unter "lync Server 2010 Lastenausgleichs Partner" unter [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="1d2f0-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="1d2f0-116">Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Edgeserver, auf denen der A/V-Edgedienst ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="1d2f0-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="1d2f0-117">Im folgenden finden Sie die Hardwareanforderungen für den Lastenausgleich für Edgeserver mit dem A/V-Edgedienst:</span><span class="sxs-lookup"><span data-stu-id="1d2f0-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="1d2f0-p104">Deaktivieren Sie den Nagle-Algorithmus für TCP sowohl für den internen als auch für den externen Port 443. Mit diesem Algorithmus werden mehrere kleine Pakete für eine effizientere Übermittlung zu einem einzigen, größeren Paket zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="1d2f0-120">Deaktivieren Sie den Nagle-Algorithmus für TCP für den Bereich der externen Ports 50.000 bis 59.999.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="1d2f0-121">Verwenden Sie keine Netzwerkadressenübersetzung für die interne oder externe Firewall.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="1d2f0-122">Die interne Edge-Schnittstelle muss sich in einem anderen Netzwerk befinden als die Edgeserver externe Schnittstelle und das Routing zwischen diesen muss deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="1d2f0-123">Die externe Schnittstelle des Edgeserver, auf dem der A/V-Edgedienst verwendet wird, muss öffentlich routingfähige IP-Adressen und keine NAT-oder Portübersetzung für eine externe IP-Adresse der Edge verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="1d2f0-124">Anforderungen an das Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="1d2f0-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="1d2f0-125">Die Anforderungen an die Cookie-basierte Affinität werden in lync Server 2013 für Webdienste stark reduziert.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="1d2f0-126">Wenn Sie lync Server 2013 bereitstellen und keine lync Server 2010-Front-End-Server oder Front-End-Pools beibehalten, benötigen Sie keine Cookie-basierte Persistenz.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="1d2f0-127">Wenn Sie jedoch lync Server 2010-Front-End-Server oder Front-End-Pools vorübergehend oder dauerhaft beibehalten, verwenden Sie weiterhin Cookie-basierte Persistenz, da Sie für lync Server 2010 bereitgestellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d2f0-128"><STRONG>Wenn Sie sich entscheiden, die cookiebasierte Persistenz zu verwenden, obwohl dies für Ihre </STRONG>-Bereitstellung nicht erforderlich ist, hat dies keine negative Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="1d2f0-129">Für Bereitstellungen, in denen die cookiebasierte Affinität **nicht verwendet** wird:</span><span class="sxs-lookup"><span data-stu-id="1d2f0-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="1d2f0-130">Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 4443 **Forward Hostheader** auf true fest.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-130">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="1d2f0-131">Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-131">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="1d2f0-132">Für Bereitstellungen, in denen die cookiebasierte Affinität **verwendet** wird:</span><span class="sxs-lookup"><span data-stu-id="1d2f0-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="1d2f0-133">Legen Sie in der Reverseproxy-Veröffentlichungsregel für Port 4443 **Forward Hostheader** auf true fest.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-133">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="1d2f0-134">Dadurch wird sichergestellt, dass die ursprüngliche URL weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-134">This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="1d2f0-135">Das Cookie für das Hardwaregerät zum Lastenausgleich DARF NICHT als "httpOnly" gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="1d2f0-136">Das Cookie für das Hardwaregerät zum Lastenausgleich DARF KEINE Ablaufzeit haben.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="1d2f0-137">Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS den Namen **MS-WSMAN** haben (dies ist der von den Webdiensten erwartete Wert, der nicht geändert werden kann).</span><span class="sxs-lookup"><span data-stu-id="1d2f0-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="1d2f0-p108">Das Cookie für das Hardwaregerät zum Lastenausgleich MUSS in jeder HTTP-Antwort festgelegt sein, für die die eingehende HTTP-Anforderung kein Cookie enthielt, unabhängig davon, ob für eine vorherige HTTP-Antwort für dieselbe TCP-Verbindung bereits ein Cookie abgerufen wurde. Wenn der Lastenausgleich das Einfügen von Cookies so optimiert, dass sie nur einmal pro TCP-Verbindung erfolgt, darf diese Optimierung NICHT verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d2f0-140">Typische Hardware Lastenausgleichskonfigurationen verwenden die Quell Adress Affinität und eine 20-minütige TCP-Sitzungslebensdauer, was für lync Server-und lync 2013-Clients in Ordnung ist, da der Sitzungsstatus über die Clientnutzung und/oder die Anwendungs Interaktion verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="1d2f0-141">Wenn Sie mobile Geräte bereitstellen, muss das Hardwaregerät zum Lastenausgleich in der Lage sein, einen Lastenausgleich für eine einzelne Anforderung in einer TCP-Sitzung vorzunehmen (tatsächlich muss es möglich sein, einen Lastenausgleich für eine einzelne Anforderung basierend auf der Ziel-IP-Adresse vorzunehmen).</span><span class="sxs-lookup"><span data-stu-id="1d2f0-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1d2f0-p109">F5-Hardwaregeräte zum Lastenausgleich sind mit einem Feature namens OneConnect ausgestattet, mit dem sichergestellt wird, dass für jede Anforderung in einer TCP-Verbindung ein individueller Lastenausgleich vorgenommen wird. Wenn Sie mobile Geräte bereitstellen, stellen Sie sicher, dass der Hersteller des Hardwaregeräts für den Lastenausgleich dieselbe Funktion unterstützt). Für die neuesten mobilen Apps für Apple iOS ist Transport Layer Security (TLS) Version 1.2 erforderlich. F5 stellt hierfür bestimmte Einstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="1d2f0-146">Ausführliche Informationen zu Lastenausgleichsgeräten von Drittanbietern finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="1d2f0-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="1d2f0-147">Im Folgenden sind die Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für Director- und Front-End-Pool-Webdienste aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="1d2f0-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="1d2f0-148">Für interne Webdienste VIPs legen Sie die Quell- \_ addr-Persistenz (interner Port 80, 443) auf dem Hardwaregerät zum Lastenausgleich fest.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="1d2f0-149">Für lync Server 2013 \_ bedeutet die Quell-addr-Persistenz, dass mehrere Verbindungen, die von einer einzelnen IP-Adresse stammen, immer an einen Server gesendet werden, um den Sitzungsstatus beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="1d2f0-150">Legen Sie ein TCP-Leerlauftimeout von 1.800 Sekunden fest.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="1d2f0-p111">Erstellen Sie für die Firewall zwischen dem Reverseproxy und dem Hardwaregerät zum Lastenausgleich des nächsten Hoppools eine Regel zum Zulassen von https:-Datenverkehr an Port 4443 – vom Reverseproxy zum Hardwaregerät zum Lastenausgleich. Das Hardwaregerät zum Lastenausgleich muss für die Überwachung der Ports 80, 443 und 4443 konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1d2f0-153">Weitere Informationen zur Konfiguration des Hardwaregerät zum Lastenausgleich finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Summary – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="1d2f0-154">Zusammenfassung der Affinitätsanforderungen an das Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="1d2f0-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d2f0-155">Client-/Benutzerstandort</span><span class="sxs-lookup"><span data-stu-id="1d2f0-155">Client/user location</span></span></th>
<th><span data-ttu-id="1d2f0-156">Affinitätsanforderungen an den externen Webdienste-FQDN</span><span class="sxs-lookup"><span data-stu-id="1d2f0-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="1d2f0-157">Affinitätsanforderungen an den internen Webdienste-FQDN</span><span class="sxs-lookup"><span data-stu-id="1d2f0-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d2f0-158">Lync Web App (interne und externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="1d2f0-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="1d2f0-159">Mobiles Gerät (interne und externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="1d2f0-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-160">Keine Affinität</span><span class="sxs-lookup"><span data-stu-id="1d2f0-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-161">Quelladressenaffinität</span><span class="sxs-lookup"><span data-stu-id="1d2f0-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d2f0-162">Lync Web App (nur externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="1d2f0-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="1d2f0-163">Mobiles Gerät (interne und externe Benutzer)</span><span class="sxs-lookup"><span data-stu-id="1d2f0-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-164">Keine Affinität</span><span class="sxs-lookup"><span data-stu-id="1d2f0-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-165">Quelladressenaffinität</span><span class="sxs-lookup"><span data-stu-id="1d2f0-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d2f0-166">Lync Web App (nur interne Benutzer)</span><span class="sxs-lookup"><span data-stu-id="1d2f0-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="1d2f0-167">Mobiles Gerät (nicht bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="1d2f0-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-168">Keine Affinität</span><span class="sxs-lookup"><span data-stu-id="1d2f0-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-169">Quelladressenaffinität</span><span class="sxs-lookup"><span data-stu-id="1d2f0-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="1d2f0-170">Portüberwachung für Hardwaregeräte zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="1d2f0-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="1d2f0-171">Sie definieren die Portüberwachung für Hardwaregeräte zum Lastenausgleich (Hardware Load Balancers, HLB), um festzustellen, wann bestimmte Dienste aufgrund von Hardware- oder Kommunikationsfehlern nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="1d2f0-172">Wenn beispielsweise der Front-End-Server Dienst (RTCSRV) angehalten wird, da die Front-End-Server oder Front-End-Pool fehlschlägt, sollte die HLB-Überwachung auch den Empfang von Datenverkehr auf dem Webdienste beenden.</span><span class="sxs-lookup"><span data-stu-id="1d2f0-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="1d2f0-173">Sie können die HLB-Portüberwachung implementieren, um Folgendes zu überwachen:</span><span class="sxs-lookup"><span data-stu-id="1d2f0-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="1d2f0-174">Front-End-Server Benutzer Pool – interne HLB-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d2f0-174">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="1d2f0-175">Virtuelle IP/Port</span><span class="sxs-lookup"><span data-stu-id="1d2f0-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="1d2f0-176">Knoten Port</span><span class="sxs-lookup"><span data-stu-id="1d2f0-176">Node Port</span></span></th>
<th><span data-ttu-id="1d2f0-177">Knoten Computer/Monitor</span><span class="sxs-lookup"><span data-stu-id="1d2f0-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="1d2f0-178">Persistenzprofil</span><span class="sxs-lookup"><span data-stu-id="1d2f0-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="1d2f0-179">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="1d2f0-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d2f0-180">&lt;Pool &gt; -int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="1d2f0-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="1d2f0-181">443</span><span class="sxs-lookup"><span data-stu-id="1d2f0-181">443</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-182">443</span><span class="sxs-lookup"><span data-stu-id="1d2f0-182">443</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-183">Front-End-</span><span class="sxs-lookup"><span data-stu-id="1d2f0-183">Front End</span></span></p>
<p><span data-ttu-id="1d2f0-184">5061</span><span class="sxs-lookup"><span data-stu-id="1d2f0-184">5061</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-185">Source</span><span class="sxs-lookup"><span data-stu-id="1d2f0-185">Source</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-186">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1d2f0-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d2f0-187">&lt;Pool &gt; -int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="1d2f0-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="1d2f0-188">80</span><span class="sxs-lookup"><span data-stu-id="1d2f0-188">80</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-189">80</span><span class="sxs-lookup"><span data-stu-id="1d2f0-189">80</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-190">Front-End-</span><span class="sxs-lookup"><span data-stu-id="1d2f0-190">Front End</span></span></p>
<p><span data-ttu-id="1d2f0-191">5061</span><span class="sxs-lookup"><span data-stu-id="1d2f0-191">5061</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-192">Source</span><span class="sxs-lookup"><span data-stu-id="1d2f0-192">Source</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-193">HTTP</span><span class="sxs-lookup"><span data-stu-id="1d2f0-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="1d2f0-194">Front-End-Server Benutzer Pool – externe HLB-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d2f0-194">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="1d2f0-195">Virtuelle IP/Port</span><span class="sxs-lookup"><span data-stu-id="1d2f0-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="1d2f0-196">Knoten Port</span><span class="sxs-lookup"><span data-stu-id="1d2f0-196">Node Port</span></span></th>
<th><span data-ttu-id="1d2f0-197">Knoten Computer/Monitor</span><span class="sxs-lookup"><span data-stu-id="1d2f0-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="1d2f0-198">Persistenzprofil</span><span class="sxs-lookup"><span data-stu-id="1d2f0-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="1d2f0-199">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="1d2f0-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d2f0-200">&lt;Pool &gt; web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="1d2f0-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="1d2f0-201">443</span><span class="sxs-lookup"><span data-stu-id="1d2f0-201">443</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-202">4443</span><span class="sxs-lookup"><span data-stu-id="1d2f0-202">4443</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-203">Front-End-</span><span class="sxs-lookup"><span data-stu-id="1d2f0-203">Front End</span></span></p>
<p><span data-ttu-id="1d2f0-204">5061</span><span class="sxs-lookup"><span data-stu-id="1d2f0-204">5061</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-205">Keine</span><span class="sxs-lookup"><span data-stu-id="1d2f0-205">None</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-206">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1d2f0-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d2f0-207">&lt;Pool &gt; web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="1d2f0-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="1d2f0-208">80</span><span class="sxs-lookup"><span data-stu-id="1d2f0-208">80</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-209">8080</span><span class="sxs-lookup"><span data-stu-id="1d2f0-209">8080</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-210">Front-End-</span><span class="sxs-lookup"><span data-stu-id="1d2f0-210">Front End</span></span></p>
<p><span data-ttu-id="1d2f0-211">5061</span><span class="sxs-lookup"><span data-stu-id="1d2f0-211">5061</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-212">Keine</span><span class="sxs-lookup"><span data-stu-id="1d2f0-212">None</span></span></p></td>
<td><p><span data-ttu-id="1d2f0-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="1d2f0-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

