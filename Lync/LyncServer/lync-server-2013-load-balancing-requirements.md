---
title: Lync Server 2013 Anforderungen für den Lastenausgleich
description: Lync Server 2013 Anforderungen für den Lastenausgleich.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a768b2cbfe444e6915c932835d3cc2abaf6a98c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550031"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="d2e4c-103">Lastenausgleichsanforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2e4c-103">Load balancing requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2e4c-104">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d2e4c-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d2e4c-105">Wenn Sie über Front-End-Pools, Director-Pools oder Edgeserver Pools verfügen, müssen Sie den Lastenausgleich für diese Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-105">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="d2e4c-106">Beim Lastenausgleich wird der Datenverkehr auf die Server in einem Pool verteilt.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-106">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="d2e4c-107">Lync Server 2013 unterstützt zwei Arten von Lastenausgleichslösungen für den Client-zu-Server-Datenverkehr: Domain Name System (DNS) Lastenausgleich und Hardwarelastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-107">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="d2e4c-108">Der DNS-Lastenausgleich bietet mehrere Vorteile, einschließlich einer einfacheren Verwaltung, einer effizienteren Problembehandlung und der Möglichkeit, einen Großteil des lync Server Datenverkehrs von möglichen Problemen mit dem Hardwarelastenausgleich zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="d2e4c-109">Entscheiden Sie, welche Lösung für den Lastenausgleich für die einzelnen Pools in der Bereitstellung jeweils geeignet ist, und beachten Sie dabei die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="d2e4c-109">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="d2e4c-p103">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="d2e4c-p104">Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="d2e4c-115">Weitere Informationen zum Auswählen einer Lösung für das Hardwaregerät zum Lastenausgleich finden Sie unter [Hardware Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2e4c-115">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="d2e4c-116">Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-116">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="d2e4c-117">Beispielsweise ist das Konfigurieren des Hardwarelastenausgleichs einfacher, da nur der HTTP-und HTTPS-Datenverkehr verwaltet wird, während alle anderen Protokolle durch den DNS-Lastenausgleich verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-117">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="d2e4c-118">Ausführliche Informationen finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="d2e4c-118">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="d2e4c-119">Für den Server-zu-Server-Datenverkehr verwendet lync Server 2013 einen Topologie-fähigen Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-119">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="d2e4c-120">Die Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs der Server in der Topologie zu erhalten und den Datenverkehr automatisch an die Server zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-120">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="d2e4c-121">Administratoren müssen diese Art von Lastenausgleich nicht einrichten oder verwalten.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-121">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="d2e4c-122">Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr auf einem bestimmten Computer blockieren müssen, reicht es nicht aus, die IP-Adresseinträge aus dem Pool-FQDN einfach zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-122">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="d2e4c-123">Sie müssen auch den DNS-Eintrag für den Computer entfernen.</span><span class="sxs-lookup"><span data-stu-id="d2e4c-123">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

