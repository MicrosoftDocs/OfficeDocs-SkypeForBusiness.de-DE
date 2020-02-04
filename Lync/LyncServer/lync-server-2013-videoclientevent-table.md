---
title: 'Lync Server 2013: VideoClientEvent-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ff9e19288aaaa09b8c72f857f3cfcf4e5331dd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="bc21e-102">VideoClientEvent-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc21e-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc21e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bc21e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bc21e-104">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="bc21e-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="bc21e-105">In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="bc21e-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc21e-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bc21e-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bc21e-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bc21e-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc21e-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bc21e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bc21e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bc21e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="bc21e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="bc21e-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bc21e-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc21e-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bc21e-115">int</span><span class="sxs-lookup"><span data-stu-id="bc21e-115">int</span></span></p></td>
<td><p><span data-ttu-id="bc21e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="bc21e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="bc21e-117">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bc21e-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc21e-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="bc21e-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="bc21e-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bc21e-120">Primary</span><span class="sxs-lookup"><span data-stu-id="bc21e-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="bc21e-121">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bc21e-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc21e-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="bc21e-123">bit</span><span class="sxs-lookup"><span data-stu-id="bc21e-123">bit</span></span></p></td>
<td><p><span data-ttu-id="bc21e-124">Primary</span><span class="sxs-lookup"><span data-stu-id="bc21e-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="bc21e-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="bc21e-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="bc21e-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="bc21e-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc21e-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bc21e-128">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="bc21e-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="bc21e-129">Die verfügbare Bandbreite reicht für ein akzeptables Spracherlebnis nicht aus.</span><span class="sxs-lookup"><span data-stu-id="bc21e-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc21e-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bc21e-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bc21e-131">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="bc21e-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="bc21e-132">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des empfangenen Audiosignals.</span><span class="sxs-lookup"><span data-stu-id="bc21e-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

