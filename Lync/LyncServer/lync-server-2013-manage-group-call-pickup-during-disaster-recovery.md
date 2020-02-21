---
title: 'Lync Server 2013: Verwalten der gruppenanrufannahme während der Notfallwiederherstellung'
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
ms.openlocfilehash: f58894a00c853f04d5d4c6f995edc17683b12e9f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="87d46-102">Verwalten der gruppenanrufannahme während der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87d46-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87d46-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="87d46-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="87d46-104">Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr verfügbar ist, wird ein Failover des Diensts an den Sicherungspool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="87d46-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="87d46-105">Während des Failovers auf den Sicherungspool werden Benutzer zum Sicherungspool umgeleitet und befinden sich im Ausfall Sicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="87d46-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="87d46-106">Im Ausfall Sicherheitsmodus können Benutzer keine Anrufe anderer Benutzer aufnehmen oder Ihre Anrufe von anderen Benutzern abholen lassen.</span><span class="sxs-lookup"><span data-stu-id="87d46-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="87d46-107">Nach Abschluss des Failovers können Benutzer die gruppenanrufannahme wie gewohnt wieder verwenden.</span><span class="sxs-lookup"><span data-stu-id="87d46-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="87d46-108">Während des Failback zum primären Pool werden Benutzer zum primären Pool umgeleitet und befinden sich erneut im Ausfall Sicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="87d46-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="87d46-109">Die Funktion für die gruppenanrufannahme ist erst verfügbar, wenn sich die Benutzer außerhalb des Ausfall Sicherheitsmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="87d46-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="87d46-110">In diesem Abschnitt werden einige Überlegungen zur gruppenanrufannahme während der Notfallwiederherstellung erläutert, und es wird auch die Benutzeroberfläche beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87d46-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="87d46-111">Überlegungen zur gruppenanrufannahme während der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="87d46-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="87d46-112">Während der Notfallwiederherstellung verwenden Benutzer, die als Teil des Failover-Prozesses zum Sicherungspool umgeleitet wurden, die Anwendung zum Parken von anrufen, die im Sicherungspool für die Nummern der Anrufannahme Gruppe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="87d46-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="87d46-113">Unterstützung für die gruppenanrufannahme während der Notfallwiederherstellung erfordert daher, dass die Anwendung zum Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool bereitgestellt und aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="87d46-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="87d46-114">Die Gruppenanruf-Pickup-Nummernbereiche in der Tabelle "Parken von Anrufen" müssen nach Abschluss des Failover-Prozesses an den Sicherungspool an den Sicherungspool umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="87d46-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="87d46-115">Die Nummernbereiche müssen zurück zum primären Pool umgeleitet werden, nachdem der Failback-Prozess für den primären Pool abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="87d46-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="87d46-116">Verwenden Sie das Cmdlet "CsCallParkOrbit", um die Gruppenanruf **-** Abhol Bereiche umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="87d46-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="87d46-117">Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie alle Gruppenanruf Pickup-Nummernbereiche, die dem primären Pool zugeordnet sind, dem FQDN des neuen Pools zuweisen.</span><span class="sxs-lookup"><span data-stu-id="87d46-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="87d46-118">Um Nummernbereiche dem neuen Pool neu zuzuweisen, können Sie das Cmdlet " **CsCallParkOrbit** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="87d46-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="87d46-119">Ausführliche Informationen zum Cmdlet " **CsCallParkOrbit** " finden Sie unter [festlegen-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="87d46-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="87d46-120">Erfahrung bei der gruppenanrufannahme beim Pool Ausfall</span><span class="sxs-lookup"><span data-stu-id="87d46-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="87d46-121">Die folgende Tabelle enthält eine Zusammenfassung der Gruppenanruf-Pickup-Umgebung in den Phasen der Notfallwiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="87d46-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="87d46-122">Benutzererfahrung während der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="87d46-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87d46-123">Anrufstatus</span><span class="sxs-lookup"><span data-stu-id="87d46-123">Call state</span></span></th>
<th><span data-ttu-id="87d46-124">Failover auf Sicherungspool</span><span class="sxs-lookup"><span data-stu-id="87d46-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="87d46-125">Failback zum primären Pool</span><span class="sxs-lookup"><span data-stu-id="87d46-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87d46-126">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="87d46-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="87d46-127"><strong>Während des Failover-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-128">Gruppenanrufannahme für Benutzer im Ausfall Sicherheitsmodus nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="87d46-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="87d46-129"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-130">Gruppenanrufannahme verfügbar, wenn Benutzer aus Ausfallsicherheit und Gruppenanruf-Abhol Nummernbereiche an Sicherungspool umgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="87d46-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87d46-131"><strong>Während des Failback-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-132">Gruppenanrufannahme für Benutzer im Ausfall Sicherheitsmodus nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="87d46-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="87d46-133"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-134">Die gruppenanrufannahme ist verfügbar, wenn Benutzer aus Ausfallsicherheit und Gruppenanruf-Pickup-Nummernbereichen zurück zum primären Pool umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="87d46-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87d46-135">Anrufe in der Warteschlange für die gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="87d46-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="87d46-136"><strong>Während des Failover-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-137">Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="87d46-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="87d46-138"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-139">Keine Anrufe in diesem Zustand</span><span class="sxs-lookup"><span data-stu-id="87d46-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87d46-140"><strong>Während des Failback-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-141">Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="87d46-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="87d46-142"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-143">Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="87d46-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87d46-144">Eingerichteter Anruf</span><span class="sxs-lookup"><span data-stu-id="87d46-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="87d46-145"><strong>Während des Failover-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-146">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="87d46-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="87d46-147"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-148">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="87d46-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87d46-149"><strong>Während des Failback-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-150">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="87d46-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="87d46-151"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="87d46-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="87d46-152">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="87d46-152">Calls stay connected</span></span></p></li>
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

