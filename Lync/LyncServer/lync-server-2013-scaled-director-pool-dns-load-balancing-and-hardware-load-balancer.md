---
title: Skalierte Directorpool-DNS-Lastenausgleich und Hardwaregerät zum Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af050cbef7c75bb7b403dc4ef74c4750a9e8b3c3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="30cc0-102">Skalierte Directorpool-DNS-Lastenausgleich und Hardwarelastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30cc0-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30cc0-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="30cc0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="30cc0-104">Eine skalierte Directorpool, in der mehrere Directors bereitgestellt werden, um zusätzliche Kapazität zu verarbeiten und hohe Verfügbarkeit bereitzustellen, erfordert Lastenausgleich, um die Client-und Server Kommunikation an alle Mitglieder des Pools zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="30cc0-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="30cc0-105">Ein Director hostet Webdienste ähnlich wie ein Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="30cc0-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="30cc0-106">Für die Bereitstellung des Lastenausgleichs können Sie entweder den Hardwarelastenausgleich oder DNS-Lastenausgleich (Domain Name System) und den Hardwarelastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="30cc0-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="30cc0-107">Der Hardwarelastenausgleich ist für die Webdienste erforderlich, und der DNS-Lastenausgleich allein bietet nicht die für Webdienste erforderlichen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="30cc0-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="30cc0-108">In den folgenden Themen werden die Planungsüberlegungen für die Bereitstellungeines Directorpool mithilfe des DNS-Lastenausgleichs in Verbindung mit dem Hardwarelastenausgleich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30cc0-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="30cc0-109">Wenn Sie den Hardwarelastenausgleich, jedoch nicht den DNS-Lastenausgleich für den Directorpool verwenden möchten, lesen Sie das Thema [skalierte Directorpool-Hardwaregerät zum Lastenausgleich in lync Server 2013, in](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) dem die Planungsanforderungen für diese Topologie beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="30cc0-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="30cc0-110">![Skalierter Directorpool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Skalierter Directorpool")</span><span class="sxs-lookup"><span data-stu-id="30cc0-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="30cc0-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="30cc0-111">In This Section</span></span>

  - [<span data-ttu-id="30cc0-112">Zertifikatzusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30cc0-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="30cc0-113">Port Zusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30cc0-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="30cc0-114">DNS-Zusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30cc0-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

