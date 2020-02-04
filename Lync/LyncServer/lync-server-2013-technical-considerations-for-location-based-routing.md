---
title: 'Lync Server 2013: Technische Überlegungen zum standortbasierten Routing'
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
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="85241-102">Technische Überlegungen zum standortbasierten Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85241-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85241-103">_**Letztes Änderungsdatum des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="85241-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="85241-104">Bei der Planung von Standort basiertem Routing sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="85241-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="85241-105">Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="85241-105">Disaster Recovery</span></span>

<span data-ttu-id="85241-106">Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen von normalen Vorgängen für den primären Pool bleibt das standortbasierte Routing während eines Disaster-und Wiederherstellungsverfahrens zu allen Zeiten erzwungen.</span><span class="sxs-lookup"><span data-stu-id="85241-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="85241-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="85241-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="85241-108">Die Konfiguration des standortbasierten Routings wirkt sich auf die Planung aus, in der Sie die Gateways bereitstellen, die ihren überlebenden Branch-Appliances zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="85241-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="85241-109">Das Gateway, das mit Ihrem SBA verbunden ist, muss sich im selben Netzwerkstandort wie Ihre Survivable Branch-Appliance befinden. Andernfalls ist es Benutzern, die auf Ihrer Survivable Branch-Appliance verwaltet werden, nicht möglich, ausgehende Anrufe zu tätigen, wenn standortbasiertes Routing konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="85241-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="85241-110">Wenn die WAN-Verbindung zwischen Ihrer Survivable Branch-Appliance und dem zentralen Standort ausgefallen ist, bleiben standortbasierte Routing Einschränkungen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="85241-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85241-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85241-111">See Also</span></span>


[<span data-ttu-id="85241-112">Planung des standortbasierten Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85241-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

