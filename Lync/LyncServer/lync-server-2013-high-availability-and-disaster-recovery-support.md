---
title: 'Lync Server 2013: Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung'
description: 'Lync Server 2013: Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552791"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="86cde-103">Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86cde-103">High availability and disaster recovery support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86cde-104">_**Letztes Änderungsstand des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="86cde-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="86cde-105">Lync Server 2013 bietet hohe Verfügbarkeit durch Server Redundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="86cde-105">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="86cde-106">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="86cde-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="86cde-107">Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="86cde-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="86cde-108">Ausführliche Informationen zu Serverrollen finden Sie unter [Server Roles in lync Server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="86cde-108">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="86cde-109">Lync Server 2013 bietet auch Maßnahmen zur Notfallwiederherstellung, indem die Pool Kopplung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="86cde-109">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="86cde-110">Wenn Sie diese Topologie bereitstellen, bestimmen Sie Paare von Front-End-Pools, wobei sich jeder Pool in einem Paar in einem separaten Datencenter und in einem separaten geografischen Bereich befindet.</span><span class="sxs-lookup"><span data-stu-id="86cde-110">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="86cde-111">Wenn ein Pool oder eine Website ausfällt, können Sie die Benutzer dieses Pools umleiten, um den anderen Pool im Paar mit minimaler Unterbrechung des Diensts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="86cde-111">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="86cde-112">Lync Server 2013 unterstützt auch die hohe Verfügbarkeit von Back-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="86cde-112">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="86cde-113">Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für eine Front-End-Pool bereitstellen und synchrone SQL Server Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausführen.</span><span class="sxs-lookup"><span data-stu-id="86cde-113">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="86cde-114">Ausführliche Informationen zur Pool Kopplung und zur Back-End-Server Spiegelung finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="86cde-114">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="86cde-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86cde-115">See Also</span></span>


[<span data-ttu-id="86cde-116">Server Rollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86cde-116">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="86cde-117">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86cde-117">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

