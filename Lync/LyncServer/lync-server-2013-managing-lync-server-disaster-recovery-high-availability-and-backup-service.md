---
title: Verwalten von lync Server Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst
description: Verwalten von lync Server Notfallwiederherstellung, Hochverfügbarkeit und Sicherungsdienst.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e440c8c72ab5e66d27a86dfce963368dff804bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569411"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="8f41e-103">Verwalten von lync Server 2013 Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst</span><span class="sxs-lookup"><span data-stu-id="8f41e-103">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f41e-104">_**Letztes Änderungsstand des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="8f41e-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="8f41e-105">Dieser Abschnitt enthält Verfahren für Notfall Wiederherstellungsvorgänge sowie für die Verwaltung des Sicherungsdiensts, der die Daten in paarweise gepaarten Front-End-Pools synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="8f41e-105">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="8f41e-106">Notfallwiederherstellungsverfahren, sowohl Failover als auch Failback, sind manuell.</span><span class="sxs-lookup"><span data-stu-id="8f41e-106">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="8f41e-107">Wenn ein Notfall vorliegt, muss der Administrator die Failover-Verfahren manuell aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8f41e-107">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="8f41e-108">Gleiches gilt für das Failback, nachdem der Pool repariert wurde.</span><span class="sxs-lookup"><span data-stu-id="8f41e-108">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="8f41e-109">Für die Notfallwiederherstellungsverfahren im Rest dieses Abschnitts wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="8f41e-109">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="8f41e-110">Sie verfügen über eine Bereitstellung mit paarweise gepaarten Front-End-Pools, die sich an unterschiedlichen Standorten befinden, wie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f41e-110">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="8f41e-111">Der Sicherungsdienst wurde für diese gepaarten Pools ausgeführt, damit Sie synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="8f41e-111">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="8f41e-112">Wenn der zentrale Verwaltungsspeicher in einem der Pools gehostet wird, wird er auf beiden Pools installiert und ausgeführt, wobei einer der Pools, die den aktiven Master hosten, und der andere Pool, der den Standby hostet.</span><span class="sxs-lookup"><span data-stu-id="8f41e-112">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8f41e-113">In den folgenden Verfahren bezieht sich der Parameter <EM>poolfqdn "</EM> auf den FQDN des Pools, der vom Notfall betroffen ist, und nicht auf den Pool, von dem betroffene Benutzer umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8f41e-113">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="8f41e-114">Für dieselbe Gruppe betroffener Benutzer bezieht sich dieser auf denselben Pool sowohl in Failover-als auch in Failback-Cmdlets (also im Pool, der zuerst die Benutzer vor dem Failover verwaltet hat).</span><span class="sxs-lookup"><span data-stu-id="8f41e-114">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="8f41e-115">Nehmen wir beispielsweise an, dass alle Benutzer, die in einem Pool P1 verwaltet werden, ein Failover auf den Sicherungspool P2 durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="8f41e-115">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="8f41e-116">Wenn der Administrator alle Benutzer, die derzeit von P2 gewartet werden, von P1 migrieren möchte, muss der Administrator die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="8f41e-116">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="8f41e-117">Zurücksetzen aller Benutzer, die ursprünglich unter P1 von P2 auf P1 verwaltet wurden, mithilfe des Failback-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="8f41e-117">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="8f41e-118">In diesem Fall ist die <EM>poolfqdn "</EM> P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="8f41e-118">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="8f41e-119">Führen Sie einen Failover für alle Benutzer aus, die ursprünglich mit dem Cmdlet Failover auf P2 auf P1 verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="8f41e-119">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="8f41e-120">In diesem Fall ist die <EM>poolfqdn "</EM> P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="8f41e-120">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="8f41e-121">Wenn der Administrator später diese P2-Benutzer wieder auf P2 zurückführen möchte, ist die <EM>poolfqdn "</EM> P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="8f41e-121">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="8f41e-122">Beachten Sie, dass Schritt 1 vor Schritt 2 ausgeführt werden muss, um die Integrität des Pools beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="8f41e-122">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="8f41e-123">Wenn Sie Schritt 2 vor Schritt 1 versuchen, tritt beim Schritt 2-Cmdlet ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="8f41e-123">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8f41e-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8f41e-124">In This Section</span></span>

  - [<span data-ttu-id="8f41e-125">Konfigurieren und Überwachen des Sicherungsdiensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f41e-125">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="8f41e-126">Failover eines Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f41e-126">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="8f41e-127">Zurückschlagen eines Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f41e-127">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="8f41e-128">Failover einer gespiegelten Datenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f41e-128">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="8f41e-129">Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="8f41e-129">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="8f41e-130">Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="8f41e-130">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="8f41e-131">Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Verbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="8f41e-131">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="8f41e-132">Ändern des Edgepool, das einem Front-End-Pool in lync Server 2013 zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="8f41e-132">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="8f41e-133">Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f41e-133">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8f41e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f41e-134">See Also</span></span>


[<span data-ttu-id="8f41e-135">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f41e-135">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

