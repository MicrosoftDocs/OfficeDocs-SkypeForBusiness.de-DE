---
title: Verwalten von lync Server Disaster Recovery, Hochverfügbarkeits-und Sicherungsdienst
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
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="e8714-102">Verwalten der Notfallwiederherstellung, der hohen Verfügbarkeit und des Sicherungsdiensts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8714-103">_**Letztes Änderungsdatum des Themas:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e8714-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e8714-104">Dieser Abschnitt enthält Verfahren für Wiederherstellungsvorgänge in Notfällen sowie für die Verwaltung des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="e8714-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="e8714-105">Disaster Recovery-Verfahren, sowohl Failover als auch Failback, sind manuell.</span><span class="sxs-lookup"><span data-stu-id="e8714-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="e8714-106">Wenn ein Notfall vorliegt, muss der Administrator die Failoververfahren manuell aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e8714-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="e8714-107">Das gleiche gilt für das Failback, nachdem der Pool repariert wurde.</span><span class="sxs-lookup"><span data-stu-id="e8714-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="e8714-108">Bei den Disaster Recovery-Verfahren im restlichen Abschnitt wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="e8714-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="e8714-109">Sie verfügen über eine Bereitstellung mit gekoppelten Front-End-Pools, die sich an verschiedenen Standorten befinden, wie unter [Planen der Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8714-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="e8714-110">Der Sicherungsdienst wurde in diesen gekoppelten Pools ausgeführt, um sie synchron zu halten.</span><span class="sxs-lookup"><span data-stu-id="e8714-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="e8714-111">Wenn der zentrale Verwaltungsspeicher in einem der Pools gehostet wird, wird er in beiden Pools installiert und ausgeführt, wobei einer dieser Pools den aktiven Master und den anderen Pool hostet, in dem sich der Standby-Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="e8714-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e8714-112">In den folgenden Verfahren bezieht sich der <EM>PoolFQDN</EM> -Parameter auf den FQDN des Pools, der von einem Notfall betroffen ist, nicht auf den Pool, von dem betroffene Benutzer umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e8714-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="e8714-113">Für denselben Satz betroffener Benutzer verweist er sowohl in Failover-als auch in Failback-Cmdlets auf denselben Pool (also auf den Pool, der zuerst die Benutzer vor dem Failover verwaltet hat).</span><span class="sxs-lookup"><span data-stu-id="e8714-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="e8714-114">Angenommen, ein Fall, in dem alle Benutzer, die sich in einem Pool P1 befanden, auf den Sicherungspool P2 umgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e8714-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="e8714-115">Wenn der Administrator alle Benutzer verschieben möchte, die von P2 aktuell gewartet werden, um von P1 gewartet zu werden, muss der Administrator die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="e8714-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="e8714-116">Führen Sie mithilfe des Failback-Cmdlets alle Benutzer, die sich ursprünglich auf P1 benetzten, von P2 zu P1 zurück.</span><span class="sxs-lookup"><span data-stu-id="e8714-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="e8714-117">In diesem Fall ist der <EM>PoolFQDN</EM> P1's-FQDN.</span><span class="sxs-lookup"><span data-stu-id="e8714-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="e8714-118">Über das Failover-Cmdlet können alle Benutzer, die sich ursprünglich auf P2 mit P1 befanden, einen Failover durchführen.</span><span class="sxs-lookup"><span data-stu-id="e8714-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="e8714-119">In diesem Fall ist der <EM>PoolFQDN</EM> P2-FQDN.</span><span class="sxs-lookup"><span data-stu-id="e8714-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="e8714-120">Wenn der Administrator später diese P2-Benutzer wieder in P2 zurücksetzen möchte, ist der <EM>PoolFQDN</EM> P2-FQDN.</span><span class="sxs-lookup"><span data-stu-id="e8714-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="e8714-121">Beachten Sie, dass Schritt 1 oben vor Schritt 2 ausgeführt werden muss, um die Pool Integrität beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="e8714-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="e8714-122">Wenn Sie Schritt 2 vor Schritt 1 versuchen, tritt das Cmdlet "Schritt 2" nicht auf.</span><span class="sxs-lookup"><span data-stu-id="e8714-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e8714-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e8714-123">In This Section</span></span>

  - [<span data-ttu-id="e8714-124">Konfigurieren und Überwachen des Sicherungsdiensts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="e8714-125">Ausführen eines Failovers für einen Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="e8714-126">Ausführen eines Failbacks für einen Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="e8714-127">Ausführen eines Failovers für eine gespiegelte Datenbank in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="e8714-128">Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e8714-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="e8714-129">Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e8714-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="e8714-130">Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e8714-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="e8714-131">Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="e8714-132">Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8714-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8714-133">See Also</span></span>


[<span data-ttu-id="e8714-134">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8714-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

