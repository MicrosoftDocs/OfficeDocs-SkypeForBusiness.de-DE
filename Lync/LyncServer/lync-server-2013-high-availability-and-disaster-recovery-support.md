---
title: 'Lync Server 2013: Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="e706e-102">Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e706e-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e706e-103">_**Letztes Änderungsdatum des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="e706e-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="e706e-104">Lync Server 2013 bietet eine höhere Verfügbarkeit durch Server Redundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="e706e-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="e706e-105">Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen.</span><span class="sxs-lookup"><span data-stu-id="e706e-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="e706e-106">Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="e706e-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="e706e-107">Details zu Serverrollen finden Sie unter [Serverrollen in lync Server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e706e-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="e706e-108">Lync Server 2013 bietet auch Disaster Recovery-Maßnahmen, indem die Pool-Kopplung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e706e-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="e706e-109">Wenn Sie diese Topologie bereitstellen, definieren Sie Paare von Front-End-Pools, wobei sich jeder Pool in einem Paar in einem separaten Rechenzentrum und in einem separaten geografischen Bereich befindet.</span><span class="sxs-lookup"><span data-stu-id="e706e-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="e706e-110">Wenn ein Pool oder eine Website nicht mehr zur Verfügung steht, können Sie die Benutzer dieses Pools umleiten, um den anderen Pool des Paars mit minimaler Dienstunterbrechung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e706e-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="e706e-111">Lync Server 2013 unterstützt auch die höchst Verfügbarkeit von Back-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="e706e-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="e706e-112">Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für einen Front-End-Pool bereitstellen und die synchrone SQL Server-Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e706e-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="e706e-113">Details zur Pool Kopplung und zur Back-End-Server Spiegelung finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e706e-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e706e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e706e-114">See Also</span></span>


[<span data-ttu-id="e706e-115">Serverrollen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e706e-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="e706e-116">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e706e-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

