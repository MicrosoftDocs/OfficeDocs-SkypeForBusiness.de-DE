---
title: 'Lync Server 2013: technische Überlegungen für standortbasiertes Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89180087909b71bc9f53f24ee02bbc077d459a17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="015af-102">Technische Überlegungen zum standortbasierten Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="015af-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="015af-103">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="015af-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="015af-104">Bei der Planung des standortbasierten Routings sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="015af-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="015af-105">Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="015af-105">Disaster Recovery</span></span>

<span data-ttu-id="015af-106">Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen normaler Vorgänge für den primären Pool bleibt das standortbasierte Routing während eines Notfall-und Wiederherstellungsverfahrens zu jeder Zeit erzwungen.</span><span class="sxs-lookup"><span data-stu-id="015af-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="015af-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="015af-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="015af-108">Das Konfigurieren des standortbasierten Routings wirkt sich auf die Planung aus, in der Sie die Gateways bereitstellen, die ihren Survivable Branch Appliances zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="015af-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="015af-109">Das Gateway, das Ihrem SBA zugeordnet ist, muss sich am selben Netzwerkstandort befinden wie Ihr Survivable Branch Appliance; andernfalls dürfen Benutzer, die in Ihrem Survivable Branch Appliance verwaltet werden, keine ausgehenden Anrufe tätigen, wenn das standortbasierte Routing konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="015af-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="015af-110">Wenn die WAN-Verbindung zwischen Ihrem Survivable Branch Appliance und dem zentralen Standort nicht aktiv ist, bleiben standortbasierte Routing Einschränkungen bestehen.</span><span class="sxs-lookup"><span data-stu-id="015af-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="015af-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="015af-111">See Also</span></span>


[<span data-ttu-id="015af-112">Planen des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="015af-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

