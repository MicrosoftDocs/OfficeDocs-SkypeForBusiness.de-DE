---
title: 'Lync Server 2013: technische Überlegungen zum Location-Based Routing'
description: 'Lync Server 2013: technische Überlegungen zum Location-Based Routing.'
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
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568051"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="87529-103">Technische Überlegungen für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87529-103">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87529-104">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="87529-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="87529-105">Bei der Planung Location-Based Routings sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="87529-105">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="87529-106">Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="87529-106">Disaster Recovery</span></span>

<span data-ttu-id="87529-107">Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen normaler Vorgänge für den primären Pool bleibt Location-Based Routing während eines Notfall-und Wiederherstellungsverfahrens zu jeder Zeit erzwungen.</span><span class="sxs-lookup"><span data-stu-id="87529-107">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="87529-108">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="87529-108">Survivable Branch Appliance</span></span>

<span data-ttu-id="87529-109">Das Konfigurieren Location-Based Routings wirkt sich auf die Planung aus, in der Sie die Gateways bereitstellen, die ihren Survivable Branch Appliances zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="87529-109">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="87529-110">Das Gateway, das Ihrem SBA zugeordnet ist, muss sich am selben Netzwerkstandort befinden wie Ihr Survivable Branch Appliance; andernfalls dürfen Benutzer, die in Ihrem Survivable Branch Appliance verwaltet werden, keine ausgehenden Anrufe tätigen, wenn Location-Based Routing konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="87529-110">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="87529-111">Wenn die WAN-Verbindung zwischen Ihrem Survivable Branch Appliance und dem zentralen Standort nicht aktiv ist, bleiben Location-Based Routing Einschränkungen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="87529-111">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87529-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87529-112">See Also</span></span>


[<span data-ttu-id="87529-113">Planen von Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87529-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

