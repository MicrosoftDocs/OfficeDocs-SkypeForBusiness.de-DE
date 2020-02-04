---
title: 'Lync Server 2013: Verwalten der Gruppenanruf Abholung während der Disaster Recovery'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45ebe93ebc1711f49d4578a2a5d908104ca2a411
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="9c04b-102">Verwalten der Gruppenanruf Abholung während der Disaster Recovery in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c04b-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c04b-103">_**Letztes Änderungsdatum des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9c04b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9c04b-104">Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr zur Verfügung steht, ist der Dienst für den Sicherungspool nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9c04b-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="9c04b-105">Beim Failover zum Sicherungspool werden die Benutzer in den Sicherungspool umgeleitet und befinden sich im Widerstands Modus.</span><span class="sxs-lookup"><span data-stu-id="9c04b-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="9c04b-106">Im Resilienz-Modus können Benutzer keine Anrufe anderer Benutzer aufnehmen oder deren Anrufe von anderen Benutzern abgeholt werden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="9c04b-107">Nach Abschluss des Failovers können Benutzer die Gruppenanruf-Abholung wie gewohnt wieder verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="9c04b-108">Während des Failbacks an den primären Pool werden die Benutzer in den primären Pool umgeleitet und befinden sich wieder im Stabilitäts Modus.</span><span class="sxs-lookup"><span data-stu-id="9c04b-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="9c04b-109">Die Funktion für die Gruppenanruf Abholung steht erst zur Verfügung, wenn die Benutzer den Stabilitäts Modus verlassen.</span><span class="sxs-lookup"><span data-stu-id="9c04b-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="9c04b-110">In diesem Abschnitt werden einige Überlegungen zur Abholung von Gruppen anrufen während der Disaster Recovery erläutert und auch die Benutzeroberfläche beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c04b-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="9c04b-111">Überlegungen zur Abholung von Gruppen anrufen während der Disaster Recovery</span><span class="sxs-lookup"><span data-stu-id="9c04b-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="9c04b-112">Während der Disaster Recovery verwenden Benutzer, die im Rahmen des Failovers an den Backup-Pool umgeleitet wurden, die Anruf Park Anwendung, die im Backup-Pool für die Gruppennummern der Anruf Abholung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9c04b-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="9c04b-113">Daher erfordert die Unterstützung für die Gruppenanruf Abholung während der Disaster Recovery, dass die Anwendung "Parken" im primären Pool und im Backup-Pool bereitgestellt und aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="9c04b-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="9c04b-114">Die Nummernbereiche für den Gruppenanruf-Pickup in der Umlaufbahn Tabelle des Anruf Parks müssen nach Abschluss des Failovers an den Sicherungspool an den Sicherungspool umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="9c04b-115">Nach Abschluss des Failback-Vorgangs für den primären Pool müssen die Nummernbereiche wieder an den primären Pool umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="9c04b-116">Verwenden Sie das Cmdlet " **Satz-CsCallParkOrbit** ", um die Gruppenanruf-Abhol Bereiche umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="9c04b-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="9c04b-117">Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie dem FQDN des neuen Pools alle Nummernbereiche für die Gruppenanruf Abholung neu zuweisen, die dem primären Pool zugeordnet waren.</span><span class="sxs-lookup"><span data-stu-id="9c04b-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="9c04b-118">Wenn Sie dem neuen Poolnummern Bereiche erneut zuweisen möchten, können Sie das Cmdlet " **festlegen-CsCallParkOrbit** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="9c04b-119">Details zum Cmdlet " **setCsCallParkOrbit** " finden Sie unter [Satz-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="9c04b-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="9c04b-120">Gruppenanruf-Pickup-Erfahrung beim Pool-Fehler</span><span class="sxs-lookup"><span data-stu-id="9c04b-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="9c04b-121">In der folgenden Tabelle sind die Erfahrungen der Gruppenanruf Abholung in den Phasen der Disaster Recovery zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="9c04b-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="9c04b-122">Benutzererfahrung bei der Disaster Recovery</span><span class="sxs-lookup"><span data-stu-id="9c04b-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c04b-123">Anruf Zustand</span><span class="sxs-lookup"><span data-stu-id="9c04b-123">Call state</span></span></th>
<th><span data-ttu-id="9c04b-124">Failover zu Backup-Pool</span><span class="sxs-lookup"><span data-stu-id="9c04b-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="9c04b-125">Failback zu primärem Pool</span><span class="sxs-lookup"><span data-stu-id="9c04b-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c04b-126">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="9c04b-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="9c04b-127"><strong>Während des Failover-Vorgangs:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-128">Gruppenanruf Abholung für Benutzer im Resilienz-Modus nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="9c04b-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="9c04b-129"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-130">Gruppenanruf-Pickup verfügbar, wenn Benutzer, die aus der Widerstandsfähigkeit und dem Gruppenanruf-Nummernbereich abgeholt werden, in den Backup-Pool umgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="9c04b-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c04b-131"><strong>Während des Failback-Vorgangs:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-132">Gruppenanruf Abholung für Benutzer im Resilienz-Modus nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="9c04b-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="9c04b-133"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-134">Gruppenanruf-Abholung ist verfügbar, wenn Benutzer, die aus der Widerstandsfähigkeit und dem Gruppenanruf-Nummernbereich abgeholt werden, zurück zum primären Pool umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c04b-135">Anrufe in der Gruppenanruf-Pickup-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="9c04b-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="9c04b-136"><strong>Während des Failover-Vorgangs:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-137">Anrufe in der Warteschlange können nicht über die Gruppenanruf-Abholung beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="9c04b-138"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-139">Keine Anrufe in diesem Zustand</span><span class="sxs-lookup"><span data-stu-id="9c04b-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c04b-140"><strong>Während des Failback-Vorgangs:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-141">Anrufe in der Warteschlange können nicht über die Gruppenanruf-Abholung beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="9c04b-142"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-143">Anrufe in der Warteschlange können nicht über die Gruppenanruf-Abholung beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="9c04b-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c04b-144">Festgelegter Anruf</span><span class="sxs-lookup"><span data-stu-id="9c04b-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="9c04b-145"><strong>Während des Failover-Vorgangs:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-146">Anrufe bleiben in Verbindung</span><span class="sxs-lookup"><span data-stu-id="9c04b-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="9c04b-147"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-148">Anrufe bleiben in Verbindung</span><span class="sxs-lookup"><span data-stu-id="9c04b-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9c04b-149"><strong>Während des Failback-Vorgangs:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-150">Anrufe bleiben in Verbindung</span><span class="sxs-lookup"><span data-stu-id="9c04b-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="9c04b-151"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="9c04b-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="9c04b-152">Anrufe bleiben in Verbindung</span><span class="sxs-lookup"><span data-stu-id="9c04b-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

