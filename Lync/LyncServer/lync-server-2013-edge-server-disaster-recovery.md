---
title: 'Lync Server 2013: Edgeserver Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 519243475f5452cebc6fff82cc54f267bb8b36fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="07c0d-102">Edgeserver Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07c0d-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07c0d-103">_**Letztes Änderungsstand des Themas:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="07c0d-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="07c0d-p101">Wie bei anderen Serverrollen wird die hohe Verfügbarkeit für Ihre Edgeserver am besten durch die Bereitstellung mehrerer Edgeserver in Pools an den einzelnen Standorten gewährleistet. Fällt ein Edgeserver aus, stellen die anderen Server im Pool weiterhin Edgedienste bereit.</span><span class="sxs-lookup"><span data-stu-id="07c0d-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="07c0d-p102">Zur Ermöglichung von Notfallwiederherstellungsprozeduren müssen Sie separate Edgeserver an verschiedenen Standorten bereitstellen. Sie müssen Edgepools nicht wie Front-End-Pools explizit zusammenfassen. Bei mehreren Edgepools besteht jedoch die Möglichkeit, die Arbeit fortzusetzen, falls ein Edgepool ausfällt. Die folgenden Abschnitte enthalten ausführliche Informationen zur Notfallwiederherstellung der verschiedenen Funktionen von Edgeservern.</span><span class="sxs-lookup"><span data-stu-id="07c0d-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="07c0d-109">Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="07c0d-109">Remote Access</span></span>

<span data-ttu-id="07c0d-110">Wenn Sie über mehrere Standorte verfügen, die jeweils einen Pool mit Edgeserver haben und ein ganzer Edgepool fehlschlägt, funktionieren die RAS-Dienste weiterhin, ohne dass Administratoraktionen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="07c0d-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="07c0d-111">Wenn Sie Edge-Pools an unterschiedlichen Standorten erstellen, können Sie nicht den gleichen FQDN verwenden.</span><span class="sxs-lookup"><span data-stu-id="07c0d-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="07c0d-112">Jeder Edgepool muss über eindeutige FQDNs (intern und extern) verfügen.</span><span class="sxs-lookup"><span data-stu-id="07c0d-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="07c0d-113">In den Edge-Pools werden keine Reverseproxy-Veröffentlichungsregeln verwendet, um mit den Front-End-Servern zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="07c0d-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="07c0d-114">Das automatische Failover erfolgt, wenn der Client die RAS-DNS-Diensteinträge erneut fragt und Remotebenutzer an die Edgeserver an einem anderen Standort weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="07c0d-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="07c0d-115">Der Client versucht jeden externen Edge-FQDN entsprechend der Priorität der DNS-SRV-Einträge.</span><span class="sxs-lookup"><span data-stu-id="07c0d-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07c0d-116">Damit ein Failover reibungslos funktioniert, müssen Sie sicherstellen, dass die Firewall den Front-End-Servern in jedem Pool die Kommunikation mit allen Edge-Servern ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="07c0d-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="07c0d-117">Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="07c0d-117">Federation</span></span>

<span data-ttu-id="07c0d-118">Für Verbundbeziehungen mit anderen Organisationen, die lync Server ausgeführt werden, funktionieren eingehende Verbund Anforderungen weiterhin so lange, wie Sie Lösungen wie Geo-DNS-preiswert haben.</span><span class="sxs-lookup"><span data-stu-id="07c0d-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="07c0d-119">Beachten Sie, dass das Verbund Failover kein Failover mit Priorität in SRV-Einträgen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="07c0d-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="07c0d-120">Eine frühere Lösung kann Ihnen bei der Bereitstellung von Notfallwiederherstellungsfunktionen für den eingehenden Verbund helfen.</span><span class="sxs-lookup"><span data-stu-id="07c0d-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="07c0d-121">Der ausgehende Partnerverbund wird immer über einen veröffentlichten Edgepool oder Edgeserver in der Organisation eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="07c0d-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="07c0d-122">Fällt dieser Edgepool aus, müssen Sie mit dem Topologie-Generator die ausgehende Partnerverbundroute ändern, sodass sie einen Edgepool verwendet, der noch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="07c0d-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="07c0d-123">Ausführliche Informationen finden Sie unter [Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="07c0d-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="07c0d-124">XMPP-Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="07c0d-124">XMPP Federation</span></span>

<span data-ttu-id="07c0d-125">Beim XMPP-Partnerverbund treten beim ausgehenden und eingehenden Datenverkehr Fehler auf, wenn der als XMPP-Verbundpartner-Gateway festgelegte Edgepool ausfällt.</span><span class="sxs-lookup"><span data-stu-id="07c0d-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="07c0d-126">Damit der XMPP-Partnerverbund wieder funktioniert, müssen Sie die Verwendung eines anderen Edgepools durch den XMPP-Partnerverbund festlegen.</span><span class="sxs-lookup"><span data-stu-id="07c0d-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="07c0d-127">Ausführliche Informationen finden Sie unter [Failover des Edgepool für XMPP-Verbund in lync Server 2013 verwendet](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="07c0d-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="07c0d-128">Ausfall des Edgepools bei weiterer Ausführung des Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="07c0d-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="07c0d-129">Falls ein Edgepool an einem Standort ausfällt, der Front-End-Pool an diesem Standort jedoch weiterhin ausgeführt wird, müssen Sie den Front-End-Pool so ändern, dass er einen anderen Edgepool an einem anderen Standort verwendet, während der erste Edgepool nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="07c0d-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="07c0d-130">Weitere Informationen finden Sie unter [Ändern der Edgepool, die einem Front-End-Pool in lync Server 2013 zugeordnet sind](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="07c0d-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

