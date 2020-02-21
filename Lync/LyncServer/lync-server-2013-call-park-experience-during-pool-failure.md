---
title: 'Lync Server 2013: Anruf parken-Erfahrung während des Pool Fehlers'
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
ms.openlocfilehash: 1834c9872dc9b8c1045c6e5e638f86f760b4ad4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="02396-102">Parken von Anrufen in lync Server 2013 beim Pool Ausfall</span><span class="sxs-lookup"><span data-stu-id="02396-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02396-103">_**Letztes Änderungsstand des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="02396-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="02396-104">Wenn ein Front-End-Pool aufgrund eines ungeplanten Vorfalls nicht mehr verfügbar ist, werden Anrufe, die geparkt, aber noch nicht abgerufen wurden, getrennt.</span><span class="sxs-lookup"><span data-stu-id="02396-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="02396-105">Während eines Failovers in einen Sicherungspool werden Benutzer zum Sicherungspool umgeleitet und befinden sich im Ausfall Sicherheitsmodus.</span><span class="sxs-lookup"><span data-stu-id="02396-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="02396-106">Im Ausfall Sicherheitsmodus können Benutzer keine Anrufe parken, aber Sie können Anrufe in der Warteschleife platzieren und übertragen.</span><span class="sxs-lookup"><span data-stu-id="02396-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="02396-107">Nach Abschluss des Failovers können Anrufe wieder wie gewohnt geparkt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="02396-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="02396-108">Während des Failback können Benutzer Anrufe erst dann Parken, wenn Sie den Ausfall Sicherheitsmodus verlassen.</span><span class="sxs-lookup"><span data-stu-id="02396-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="02396-109">Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failovers an den Sicherungspool umgeleitet wurden, die Anwendung zum Parken von anrufen, die im Sicherungspool bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="02396-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="02396-110">Benutzer, die zum Sicherungspool umgeleitet werden, verwenden daher die Einstellungen für das Parken von anrufen, die für den Anwendung zum Parken von Anrufen im Sicherungspool konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="02396-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="02396-111">In der folgenden Tabelle wird die Funktion zum Parken von Anrufen durch die Phasen der Notfallwiederherstellung zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="02396-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="02396-112">Benutzererfahrung während der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="02396-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02396-113">Anrufstatus</span><span class="sxs-lookup"><span data-stu-id="02396-113">Call state</span></span></th>
<th><span data-ttu-id="02396-114">Wenn ein Ausfall auftritt</span><span class="sxs-lookup"><span data-stu-id="02396-114">When outage occurs</span></span></th>
<th><span data-ttu-id="02396-115">Während des Failovers</span><span class="sxs-lookup"><span data-stu-id="02396-115">During failover</span></span></th>
<th><span data-ttu-id="02396-116">Während des Failbacks</span><span class="sxs-lookup"><span data-stu-id="02396-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02396-117">Anruf noch nicht geparkt</span><span class="sxs-lookup"><span data-stu-id="02396-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="02396-118">Der Anruf bleibt verbunden, kann aber nicht geparkt werden.</span><span class="sxs-lookup"><span data-stu-id="02396-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="02396-119">Während des Failovers kann der Anruf nicht geparkt werden, während sich die Benutzer im Ausfall Sicherheitsmodus befinden, aber Sie können in die Warteschleife gestellt und übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="02396-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="02396-120">Nach Abschluss des Failovers kann der Anruf geparkt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="02396-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="02396-121">Während des Failback kann der Anruf nicht geparkt werden, während sich die Benutzer im Ausfall Sicherheitsmodus befinden, aber Sie können in die Warteschleife gestellt und übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="02396-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="02396-122">Wenn das Failback abgeschlossen ist, kann der Anruf geparkt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="02396-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02396-123">Anruf geparkt, aber noch nicht abgerufen</span><span class="sxs-lookup"><span data-stu-id="02396-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="02396-124">Anruf wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="02396-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="02396-125">Keine Anrufe in diesem Zustand.</span><span class="sxs-lookup"><span data-stu-id="02396-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="02396-126">Der Anruf bleibt geparkt.</span><span class="sxs-lookup"><span data-stu-id="02396-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02396-127">Geparkter Anruf wurde bereits abgerufen.</span><span class="sxs-lookup"><span data-stu-id="02396-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="02396-128">Der Anruf bleibt verbunden.</span><span class="sxs-lookup"><span data-stu-id="02396-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="02396-129">Der Anruf bleibt verbunden.</span><span class="sxs-lookup"><span data-stu-id="02396-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="02396-130">Der Anruf bleibt verbunden.</span><span class="sxs-lookup"><span data-stu-id="02396-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

