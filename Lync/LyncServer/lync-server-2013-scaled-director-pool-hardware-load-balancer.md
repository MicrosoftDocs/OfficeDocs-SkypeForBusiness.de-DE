---
title: 'Lync Server 2013: skalierte Directorpool-Hardwaregerät zum Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c812f1276a4f8ac9a23298e3b747e9ba97085378
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510952"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="26d79-102">Skaliertes Directorpool-Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d79-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d79-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="26d79-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="26d79-104">Eine skalierte Directorpool, bei der mehr als ein Director bereitgestellt wird, um zusätzliche Kapazität zu verarbeiten und hohe Verfügbarkeit bereitzustellen, erfordert Lastenausgleich, um die Client-und Server Kommunikation an alle Mitglieder des Pools zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="26d79-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="26d79-105">Ein Director hostet Webdienste ähnlich wie ein Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="26d79-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="26d79-106">Der Hardwarelastenausgleich ist für die Webdienste erforderlich.</span><span class="sxs-lookup"><span data-stu-id="26d79-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="26d79-107">In den folgenden Themen werden die Planungsüberlegungen für die Bereitstellungeines Directorpool mithilfe von Hardwarelastenausgleich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26d79-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="26d79-108">Wenn Sie den Hardwarelastenausgleich und den DNS-Lastenausgleich für den Directorpool verwenden möchten, lesen Sie das Thema [skalierte Directorpool-DNS-Lastenausgleich und Hardwarelastenausgleich in lync Server 2013, in](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) dem die Planungsanforderungen für diese Topologie beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="26d79-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="26d79-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="26d79-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26d79-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="26d79-110">In This Section</span></span>

  - [<span data-ttu-id="26d79-111">Zertifikatzusammenfassung für skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d79-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="26d79-112">Port Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d79-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="26d79-113">DNS-Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d79-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

