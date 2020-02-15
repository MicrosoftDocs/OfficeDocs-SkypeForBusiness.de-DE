---
title: 'Lync Server 2013: Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e53116879e194bca7d0ea4066bc5f10de38f7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="a24c8-102">Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a24c8-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a24c8-103">_**Letztes Änderungsstand des Themas:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="a24c8-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="a24c8-104">Für Instant Messaging (IM) und Anwesenheit sind nur diese Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a24c8-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="a24c8-p101">Die Front-End- oder Standard Edition-Server Ihrer Organisation. Instant Messaging- und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a24c8-p101">Your organization’s Front End Servers or Standard Edition servers. IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="a24c8-107">Ein Lastenausgleichsmodul, wenn Sie über ein Enterprise Edition-Front-End-Pool verfügen.</span><span class="sxs-lookup"><span data-stu-id="a24c8-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="a24c8-108">Weitere Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a24c8-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="a24c8-109">Planen der Bereitstellung von Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="a24c8-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="a24c8-110">In lync Server 2013 wurde Front-End-Pool Architektur geändert, und diese Änderungen wirken sich auf die Planung und Wartung Ihrer Front-End-Pools aus.</span><span class="sxs-lookup"><span data-stu-id="a24c8-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="a24c8-111">Es wird empfohlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server umfassen.</span><span class="sxs-lookup"><span data-stu-id="a24c8-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="a24c8-112">In lync Server verwendet die Architektur von Front-End-Pools ein Modell für verteilte Systeme, wobei die Daten der einzelnen Benutzer auf drei Front-End-Servern im Pool aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="a24c8-113">Weitere Informationen zu dieser neuen Architektur finden Sie unter [Topologie-Änderungen in lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="a24c8-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="a24c8-114">Wenn Sie keine drei Enterprise Edition-Front-End-Server bereitstellen möchten und eine Notfallwiederherstellung wünschen, sollten Sie lync Server Standard Edition verwenden und zwei Pools mit einer gepaarten Sicherungsbeziehung erstellen.</span><span class="sxs-lookup"><span data-stu-id="a24c8-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="a24c8-115">Dadurch wird eine Notfallwiederherstellungslösung mit nur zwei Servern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a24c8-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="a24c8-116">Weitere Informationen zu Hochverfügbarkeit und Notfall Wiederherstellungs Topologien und-Features finden Sie unter [Planning for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a24c8-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="a24c8-117">Planen der Verwaltung von Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="a24c8-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="a24c8-118">Für Front-End-Pools befolgen Sie die Richtlinien in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a24c8-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="a24c8-119">Sicherstellen, dass die Pools funktionsfähig sind</span><span class="sxs-lookup"><span data-stu-id="a24c8-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="a24c8-120">Mit dem neuen verteilten Modell für Front-End-Pools müssen bestimmte Nummern der Server eines Pools aktiv sein, damit der Pool funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a24c8-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="a24c8-121">Es gibt zwei Verlust Modi für einen Pool.</span><span class="sxs-lookup"><span data-stu-id="a24c8-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="a24c8-122">Quorum Verlust auf Routing Gruppenebene, der durch nicht genügend Replikatserver für eine bestimmte Routinggruppe verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="a24c8-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="a24c8-123">Eine Routinggruppe ist eine Aggregation einer Gruppe von Benutzern, die im Pool verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="a24c8-124">Jede Routinggruppe verfügt über drei Replikate im Pool: eine primäre und zwei sekundäre.</span><span class="sxs-lookup"><span data-stu-id="a24c8-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="a24c8-125">Quorum Verlust auf Poolebene, verursacht werden, wenn nicht genügend Seed-Server im Pool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="a24c8-126">Quorum Verlust auf Routing Gruppenebene</span><span class="sxs-lookup"><span data-stu-id="a24c8-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="a24c8-127">Wenn Sie ein neues Front-End-Pool zum ersten Mal starten, ist es wichtig, dass 85% der Serverbetriebs bereit sind, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a24c8-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="a24c8-128">Wenn weniger Server aktiv sind, können die Dienste möglicherweise in den Startzustand verfallen, und der Pool wird möglicherweise nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="a24c8-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a24c8-129">Gesamtanzahl der Server im Pool</span><span class="sxs-lookup"><span data-stu-id="a24c8-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="a24c8-130">Anzahl der Server, die ausgeführt werden müssen, damit der Pool beim ersten Mal gestartet wird</span><span class="sxs-lookup"><span data-stu-id="a24c8-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-131">2 </span><span class="sxs-lookup"><span data-stu-id="a24c8-131">2</span></span></p></td>
<td><p><span data-ttu-id="a24c8-132">1 </span><span class="sxs-lookup"><span data-stu-id="a24c8-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-133">3 </span><span class="sxs-lookup"><span data-stu-id="a24c8-133">3</span></span></p></td>
<td><p><span data-ttu-id="a24c8-134">3 </span><span class="sxs-lookup"><span data-stu-id="a24c8-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-135">4 </span><span class="sxs-lookup"><span data-stu-id="a24c8-135">4</span></span></p></td>
<td><p><span data-ttu-id="a24c8-136">3 </span><span class="sxs-lookup"><span data-stu-id="a24c8-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-137">5 </span><span class="sxs-lookup"><span data-stu-id="a24c8-137">5</span></span></p></td>
<td><p><span data-ttu-id="a24c8-138">4 </span><span class="sxs-lookup"><span data-stu-id="a24c8-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-139">6 </span><span class="sxs-lookup"><span data-stu-id="a24c8-139">6</span></span></p></td>
<td><p><span data-ttu-id="a24c8-140">5 </span><span class="sxs-lookup"><span data-stu-id="a24c8-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-141">7 </span><span class="sxs-lookup"><span data-stu-id="a24c8-141">7</span></span></p></td>
<td><p><span data-ttu-id="a24c8-142">5 </span><span class="sxs-lookup"><span data-stu-id="a24c8-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-143">8 </span><span class="sxs-lookup"><span data-stu-id="a24c8-143">8</span></span></p></td>
<td><p><span data-ttu-id="a24c8-144">6 </span><span class="sxs-lookup"><span data-stu-id="a24c8-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-145">9 </span><span class="sxs-lookup"><span data-stu-id="a24c8-145">9</span></span></p></td>
<td><p><span data-ttu-id="a24c8-146">7 </span><span class="sxs-lookup"><span data-stu-id="a24c8-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-147">10 </span><span class="sxs-lookup"><span data-stu-id="a24c8-147">10</span></span></p></td>
<td><p><span data-ttu-id="a24c8-148">8 </span><span class="sxs-lookup"><span data-stu-id="a24c8-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-149">11</span><span class="sxs-lookup"><span data-stu-id="a24c8-149">11</span></span></p></td>
<td><p><span data-ttu-id="a24c8-150">9 </span><span class="sxs-lookup"><span data-stu-id="a24c8-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-151">12</span><span class="sxs-lookup"><span data-stu-id="a24c8-151">12</span></span></p></td>
<td><p><span data-ttu-id="a24c8-152">10 </span><span class="sxs-lookup"><span data-stu-id="a24c8-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a24c8-153">Bei jedem nachfolgenden Start des Pools sollten 85% der Server gestartet werden (siehe obige Tabelle).</span><span class="sxs-lookup"><span data-stu-id="a24c8-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="a24c8-154">Wenn diese Anzahl von Servern nicht gestartet werden kann (es können jedoch genügend Server gestartet werden, damit Sie nicht auf der Ebene des Quorums auf der Poolebene sind), können Sie das Cmdlet **Reset-CsPoolRegistrarState – resettype QuorumLossRecovery** verwenden, um zu ermöglichen, dass der Pool von diesem Quorum Verlust auf Routinggruppen Ebene wiederhergestellt wird und Fortschritte macht.</span><span class="sxs-lookup"><span data-stu-id="a24c8-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="a24c8-155">Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="a24c8-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a24c8-156">Da lync Server die primäre SQL-Datenbank als Zeuge verwendet, wenn Sie die primäre Datenbank Herunterfahren und zur Spiegelkopie wechseln und genügend Front-End-Server herunterfahren, sodass nicht genügend entsprechend der oben aufgeführten Tabelle ausgeführt wird, wird der gesamte Pool nach unten gehen.</span><span class="sxs-lookup"><span data-stu-id="a24c8-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="a24c8-157">Weitere Informationen finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=393672">Datenbank-Spiegelungs Zeuge</A>.</span><span class="sxs-lookup"><span data-stu-id="a24c8-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="a24c8-158">Quorum Verlust auf Poolebene</span><span class="sxs-lookup"><span data-stu-id="a24c8-158">Pool-level quorum loss</span></span>

<span data-ttu-id="a24c8-159">Damit ein Front-End-Pool überhaupt funktioniert, kann es nicht auf dem Quorum Verlust auf Poolebene liegen.</span><span class="sxs-lookup"><span data-stu-id="a24c8-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="a24c8-160">Wenn die Anzahl der Server, die in der folgenden Tabelle aufgeführt sind, unter die Funktionsebene fällt, werden die restlichen Server im Pool alle lync Server Dienste beenden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="a24c8-161">Beachten Sie, dass die Nummern in der folgenden Tabelle davon ausgehen, dass die Back-End-Server im Pool aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="a24c8-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a24c8-162">Gesamtanzahl der Front-End-Server im Pool</span><span class="sxs-lookup"><span data-stu-id="a24c8-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="a24c8-163">Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen</span><span class="sxs-lookup"><span data-stu-id="a24c8-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-164">2 </span><span class="sxs-lookup"><span data-stu-id="a24c8-164">2</span></span></p></td>
<td><p><span data-ttu-id="a24c8-165">1 </span><span class="sxs-lookup"><span data-stu-id="a24c8-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-166">3-4</span><span class="sxs-lookup"><span data-stu-id="a24c8-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="a24c8-167">Any 2</span><span class="sxs-lookup"><span data-stu-id="a24c8-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-168">5-6</span><span class="sxs-lookup"><span data-stu-id="a24c8-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="a24c8-169">Beliebige 3</span><span class="sxs-lookup"><span data-stu-id="a24c8-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-170">7 </span><span class="sxs-lookup"><span data-stu-id="a24c8-170">7</span></span></p></td>
<td><p><span data-ttu-id="a24c8-171">Beliebige 4</span><span class="sxs-lookup"><span data-stu-id="a24c8-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a24c8-172">8-9</span><span class="sxs-lookup"><span data-stu-id="a24c8-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="a24c8-173">4 der ersten 7 Server</span><span class="sxs-lookup"><span data-stu-id="a24c8-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a24c8-174">10-12</span><span class="sxs-lookup"><span data-stu-id="a24c8-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="a24c8-175">5 der ersten 9 Server</span><span class="sxs-lookup"><span data-stu-id="a24c8-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a24c8-176">In der obigen Tabelle sind die "ersten Server" die Server, die zunächst chronologisch aufgelegt wurden, als der Pool zum ersten Mal gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a24c8-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="a24c8-177">Zum bestimmen dieser Server können Sie das Cmdlet **Get-CsComputer** mit der Option **– poolfqdn "** verwenden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="a24c8-178">Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der Sie in der Topologie angezeigt werden, und diejenigen, die sich oben in der Liste befinden, sind die ersten Server.</span><span class="sxs-lookup"><span data-stu-id="a24c8-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="a24c8-179">Front-End-Pools mit zwei Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="a24c8-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="a24c8-p112">Das Bereitstellen eines Front-End-Pools, der nur zwei Front-End-Server enthält, wird nicht empfohlen. Sollten Sie einen solchen Pool aber doch einmal erstellen müssen, halten Sie sich an folgende Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="a24c8-p112">We do not recommend deploying a Front End pool that contains only two Front End Servers. If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="a24c8-p113">Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den ausgefallenen Server so schnell wie möglich wieder in Betrieb zu bekommen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.</span><span class="sxs-lookup"><span data-stu-id="a24c8-p113">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="a24c8-184">Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="a24c8-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="a24c8-185">Die bewährte Methode besteht darin, beide Front-End-Server gleichzeitig neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="a24c8-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="a24c8-186">Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="a24c8-187">Falls Sie sie nicht in dieser Reihenfolge neu starten können, führen Sie das folgende Cmdlet aus, bevor Sie den Pool wieder hochfahren:</span><span class="sxs-lookup"><span data-stu-id="a24c8-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="a24c8-188">Zusätzliche Schritte zum Sicherstellen der Funktionsweise von Pools</span><span class="sxs-lookup"><span data-stu-id="a24c8-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="a24c8-189">Sie sollten sich einige andere Faktoren ansehen, um sicherzustellen, dass Ihre Front-End-Pools funktionsfähig bleiben.</span><span class="sxs-lookup"><span data-stu-id="a24c8-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="a24c8-190">Wenn Sie das erste Mal Benutzer in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="a24c8-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="a24c8-191">Wenn Sie eine Paarbeziehung zwischen diesem Pool und einem anderen Pool zum Zwecke der Notfallwiederherstellung konfigurieren, müssen Sie nach dem Erstellen dieser Beziehung sichergehen, dass in diesem Pool zu irgendeinem Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt werden, damit Daten korrekt mit dem Sicherungspool synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="a24c8-192">Weitere Informationen zu Pool Kopplung und Notfall Wiederherstellungsfeatures finden Sie unter [Planning for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a24c8-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="a24c8-193">Verbessern der Zuverlässigkeit von Pool Upgrades</span><span class="sxs-lookup"><span data-stu-id="a24c8-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="a24c8-194">Wenn Sie die Server in einem Front-End-Pool aktualisieren oder patchen müssen, befolgen Sie den in [Upgrade-oder Update-Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)angezeigten Workflow sowie die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="a24c8-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="a24c8-195">Wenn Sie für Upgrades von einer Upgrade-Domäne zu einer anderen wechseln (nach dem Workflow beim [Upgrade oder Aktualisieren der Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), verwenden Sie das Cmdlet **Get-cspoolupgradereadinessstate "** , und überprüfen Sie den Status bereit.</span><span class="sxs-lookup"><span data-stu-id="a24c8-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="a24c8-196">Wenn Sie eine Wartezeit von 20 Minuten zwischen jeder Upgrade-Domäne hinzufügen, nachdem Sie "Ready" erreicht hat, werden die Upgrades zuverlässiger.</span><span class="sxs-lookup"><span data-stu-id="a24c8-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="a24c8-197">Wenn es während dieser 20 Minuten **nicht** mehr verfügbar ist, starten Sie den 20-minütigen Timer neu.</span><span class="sxs-lookup"><span data-stu-id="a24c8-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="a24c8-198">Außerdem können Sie das Cmdlet **Get-CsPoolFabricState** vor und nach dem Start des 20-minütigen Intervalls ausführen und sicherstellen, dass keine Änderungen an den Vorwahlen und an den Hilfsgruppen von Routinggruppen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a24c8-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="a24c8-199">Wechseln Sie nicht zur nächsten Upgrade-Domäne, wenn einer der Server in der letzten gepatchten Upgrade-Domäne festgesteckt oder nicht neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a24c8-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="a24c8-200">Dies gilt auch, wenn einer der Server innerhalb eines Upgrades nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a24c8-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="a24c8-201">Führen **Sie Get-CsPoolFabricState** aus, um sicherzustellen, dass alle Routinggruppen über eine primäre und mindestens eine sekundäre Gruppe verfügen. Dadurch wird bestätigt, ob alle Benutzer über Dienst verfügen.</span><span class="sxs-lookup"><span data-stu-id="a24c8-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="a24c8-202">Wenn einige Benutzer über Dienste verfügen und andere nicht, führen **Sie Get-CsPoolFabricState** mit der Option – verbose aus, um nach Routinggruppen mit fehlenden Replikaten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a24c8-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="a24c8-203">Starten Sie den gesamten Pool nicht als ersten Schritt zur Problembehandlung neu.</span><span class="sxs-lookup"><span data-stu-id="a24c8-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="a24c8-204">Weitere Informationen zu diesem Cmdlet finden Sie unter [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="a24c8-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="a24c8-205">Stellen Sie sicher, dass alle Instanzen der Ereignisanzeige oder der System Monitor Fenster für Windows Fabric-Installationen/-Deinstallationen geschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="a24c8-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="a24c8-206">Ändern der Konfiguration eines Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="a24c8-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="a24c8-207">Wenn Sie in einem Pool Front-End-Server hinzufügen oder entfernen und die neue Topologie dann veröffentlichen, halten Sie folgende Richtlinien ein:</span><span class="sxs-lookup"><span data-stu-id="a24c8-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="a24c8-208">Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten.</span><span class="sxs-lookup"><span data-stu-id="a24c8-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="a24c8-209">Starten Sie die Server einen nach dem anderen neu.</span><span class="sxs-lookup"><span data-stu-id="a24c8-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="a24c8-210">Wenn während der Konfigurationsänderung der gesamte Pool heruntergefahren war, führen Sie nach dem Veröffentlichen der Topologie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="a24c8-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="a24c8-p119">Wenn ein Front-End-Server ausfällt und über mehrere Tage hinweg wahrscheinlich nicht ersetzt werden kann, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, sobald er wieder verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a24c8-p119">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

