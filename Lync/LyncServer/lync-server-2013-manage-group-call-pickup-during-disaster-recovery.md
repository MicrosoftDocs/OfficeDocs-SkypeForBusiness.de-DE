---
title: 'Lync Server 2013: Verwalten der gruppenanrufannahme während der Notfallwiederherstellung'
description: 'Lync Server 2013: Manage Group Call Pickup während der Notfallwiederherstellung.'
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
ms.openlocfilehash: 04d85bc83cfe35571c2b0f47f707c9dcd8037d80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555281"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="2d72d-103">Verwalten der gruppenanrufannahme während der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d72d-103">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d72d-104">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="2d72d-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2d72d-105">Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr verfügbar ist, wird ein Failover des Diensts an den Sicherungspool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d72d-105">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="2d72d-106">Während des Failovers auf den Sicherungspool werden Benutzer zum Sicherungspool umgeleitet und befinden sich im Ausfall Sicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="2d72d-106">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="2d72d-107">Im Ausfall Sicherheitsmodus können Benutzer keine Anrufe anderer Benutzer aufnehmen oder Ihre Anrufe von anderen Benutzern abholen lassen.</span><span class="sxs-lookup"><span data-stu-id="2d72d-107">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="2d72d-108">Nach Abschluss des Failovers können Benutzer die gruppenanrufannahme wie gewohnt wieder verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-108">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="2d72d-109">Während des Failback zum primären Pool werden Benutzer zum primären Pool umgeleitet und befinden sich erneut im Ausfall Sicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="2d72d-109">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="2d72d-110">Die Funktion für die gruppenanrufannahme ist erst verfügbar, wenn sich die Benutzer außerhalb des Ausfall Sicherheitsmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-110">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="2d72d-111">In diesem Abschnitt werden einige Überlegungen zur gruppenanrufannahme während der Notfallwiederherstellung erläutert, und es wird auch die Benutzeroberfläche beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d72d-111">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="2d72d-112">Überlegungen zur gruppenanrufannahme während der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="2d72d-112">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="2d72d-113">Während der Notfallwiederherstellung verwenden Benutzer, die als Teil des Failover-Prozesses zum Sicherungspool umgeleitet wurden, die Anwendung zum Parken von anrufen, die im Sicherungspool für die Nummern der Anrufannahme Gruppe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-113">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="2d72d-114">Unterstützung für die gruppenanrufannahme während der Notfallwiederherstellung erfordert daher, dass die Anwendung zum Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool bereitgestellt und aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="2d72d-114">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="2d72d-115">Die Gruppenanruf-Pickup-Nummernbereiche in der Tabelle "Parken von Anrufen" müssen nach Abschluss des Failover-Prozesses an den Sicherungspool an den Sicherungspool umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-115">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="2d72d-116">Die Nummernbereiche müssen zurück zum primären Pool umgeleitet werden, nachdem der Failback-Prozess für den primären Pool abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2d72d-116">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="2d72d-117">Verwenden Sie das Cmdlet "CsCallParkOrbit", um die Gruppenanruf **-** Abhol Bereiche umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="2d72d-117">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="2d72d-118">Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie alle Gruppenanruf Pickup-Nummernbereiche, die dem primären Pool zugeordnet sind, dem FQDN des neuen Pools zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2d72d-118">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="2d72d-119">Um Nummernbereiche dem neuen Pool neu zuzuweisen, können Sie das Cmdlet " **CsCallParkOrbit** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-119">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="2d72d-120">Ausführliche Informationen zum Cmdlet " **CsCallParkOrbit** " finden Sie unter [festlegen-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="2d72d-120">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="2d72d-121">Erfahrung bei der gruppenanrufannahme beim Pool Ausfall</span><span class="sxs-lookup"><span data-stu-id="2d72d-121">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="2d72d-122">Die folgende Tabelle enthält eine Zusammenfassung der Gruppenanruf-Pickup-Umgebung in den Phasen der Notfallwiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="2d72d-122">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="2d72d-123">Benutzererfahrung während der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="2d72d-123">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d72d-124">Anrufstatus</span><span class="sxs-lookup"><span data-stu-id="2d72d-124">Call state</span></span></th>
<th><span data-ttu-id="2d72d-125">Failover auf Sicherungspool</span><span class="sxs-lookup"><span data-stu-id="2d72d-125">Failover to backup pool</span></span></th>
<th><span data-ttu-id="2d72d-126">Failback zum primären Pool</span><span class="sxs-lookup"><span data-stu-id="2d72d-126">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d72d-127">Neue Anrufe</span><span class="sxs-lookup"><span data-stu-id="2d72d-127">New calls</span></span></p></td>
<td><p><span data-ttu-id="2d72d-128"><strong>Während des Failover-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-128"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-129">Gruppenanrufannahme für Benutzer im Ausfall Sicherheitsmodus nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="2d72d-129">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="2d72d-130"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-130"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-131">Gruppenanrufannahme verfügbar, wenn Benutzer aus Ausfallsicherheit und Gruppenanruf-Abhol Nummernbereiche an Sicherungspool umgeleitet werden</span><span class="sxs-lookup"><span data-stu-id="2d72d-131">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2d72d-132"><strong>Während des Failback-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-132"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-133">Gruppenanrufannahme für Benutzer im Ausfall Sicherheitsmodus nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="2d72d-133">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="2d72d-134"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-134"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-135">Die gruppenanrufannahme ist verfügbar, wenn Benutzer aus Ausfallsicherheit und Gruppenanruf-Pickup-Nummernbereichen zurück zum primären Pool umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-135">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d72d-136">Anrufe in der Warteschlange für die gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="2d72d-136">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="2d72d-137"><strong>Während des Failover-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-137"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-138">Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-138">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="2d72d-139"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-139"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-140">Keine Anrufe in diesem Zustand</span><span class="sxs-lookup"><span data-stu-id="2d72d-140">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2d72d-141"><strong>Während des Failback-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-141"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-142">Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-142">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="2d72d-143"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-143"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-144">Anrufe in der Warteschlange können nicht über die gruppenanrufannahme beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="2d72d-144">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d72d-145">Eingerichteter Anruf</span><span class="sxs-lookup"><span data-stu-id="2d72d-145">Established call</span></span></p></td>
<td><p><span data-ttu-id="2d72d-146"><strong>Während des Failover-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-146"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-147">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="2d72d-147">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="2d72d-148"><strong>Nach Abschluss des Failovers:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-148"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-149">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="2d72d-149">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2d72d-150"><strong>Während des Failback-Prozesses:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-150"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-151">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="2d72d-151">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="2d72d-152"><strong>Nach Abschluss des Failback:</strong></span><span class="sxs-lookup"><span data-stu-id="2d72d-152"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2d72d-153">Anrufe bleiben verbunden</span><span class="sxs-lookup"><span data-stu-id="2d72d-153">Calls stay connected</span></span></p></li>
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

