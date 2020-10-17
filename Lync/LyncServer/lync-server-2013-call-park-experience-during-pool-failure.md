---
title: 'Lync Server 2013: Anruf parken-Erfahrung während des Pool Fehlers'
description: 'Lync Server 2013: Anruf parken-Erfahrung während des Pool Fehlers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565271"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="9cb7f-103">Parken von Anrufen in lync Server 2013 beim Pool Ausfall</span><span class="sxs-lookup"><span data-stu-id="9cb7f-103">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cb7f-104">_**Letztes Änderungsstand des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="9cb7f-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="9cb7f-105">Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr verfügbar ist, werden Anrufe, die geparkt, aber noch nicht abgerufen wurden, getrennt.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-105">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="9cb7f-106">Während eines Failovers in einen Sicherungspool werden Benutzer zum Sicherungspool umgeleitet und befinden sich im Ausfall Sicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-106">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="9cb7f-107">Im Ausfall Sicherheitsmodus können Benutzer keine Anrufe parken, aber Sie können Anrufe in der Warteschleife platzieren und übertragen.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-107">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="9cb7f-108">Nach Abschluss des Failovers können Anrufe wieder wie gewohnt geparkt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-108">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="9cb7f-109">Während des Failback können Benutzer Anrufe erst dann Parken, wenn Sie den Ausfall Sicherheitsmodus verlassen.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-109">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="9cb7f-110">Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failovers an den Sicherungspool umgeleitet wurden, die Anwendung zum Parken von anrufen, die im Sicherungspool bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="9cb7f-111">Benutzer, die zum Sicherungspool umgeleitet werden, verwenden daher die Einstellungen für das Parken von anrufen, die für den Anwendung zum Parken von Anrufen im Sicherungspool konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-111">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="9cb7f-112">In der folgenden Tabelle wird die Funktion zum Parken von Anrufen durch die Phasen der Notfallwiederherstellung zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-112">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="9cb7f-113">Benutzererfahrung während der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="9cb7f-113">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cb7f-114">Anrufstatus</span><span class="sxs-lookup"><span data-stu-id="9cb7f-114">Call state</span></span></th>
<th><span data-ttu-id="9cb7f-115">Wenn ein Ausfall auftritt</span><span class="sxs-lookup"><span data-stu-id="9cb7f-115">When outage occurs</span></span></th>
<th><span data-ttu-id="9cb7f-116">Während des Failovers</span><span class="sxs-lookup"><span data-stu-id="9cb7f-116">During failover</span></span></th>
<th><span data-ttu-id="9cb7f-117">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="9cb7f-117">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cb7f-118">Anruf noch nicht geparkt</span><span class="sxs-lookup"><span data-stu-id="9cb7f-118">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="9cb7f-119">Der Anruf bleibt verbunden, kann aber nicht geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-119">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9cb7f-120">Während des Failovers kann der Anruf nicht geparkt werden, während sich die Benutzer im Ausfall Sicherheitsmodus befinden, aber Sie können in die Warteschleife gestellt und übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-120">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="9cb7f-121">Nach Abschluss des Failovers kann der Anruf geparkt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-121">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="9cb7f-122">Während des Failback kann der Anruf nicht geparkt werden, während sich die Benutzer im Ausfall Sicherheitsmodus befinden, aber Sie können in die Warteschleife gestellt und übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-122">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="9cb7f-123">Wenn das Failback abgeschlossen ist, kann der Anruf geparkt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-123">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cb7f-124">Anruf geparkt, aber noch nicht abgerufen</span><span class="sxs-lookup"><span data-stu-id="9cb7f-124">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="9cb7f-125">Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-125">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="9cb7f-126">Keine Anrufe in diesem Zustand.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-126">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="9cb7f-127">Der Anruf bleibt geparkt.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-127">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cb7f-128">Geparkter Anruf wurde bereits abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-128">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="9cb7f-129">Der Anruf bleibt verbunden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="9cb7f-130">Der Anruf bleibt verbunden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-130">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="9cb7f-131">Der Anruf bleibt verbunden.</span><span class="sxs-lookup"><span data-stu-id="9cb7f-131">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

