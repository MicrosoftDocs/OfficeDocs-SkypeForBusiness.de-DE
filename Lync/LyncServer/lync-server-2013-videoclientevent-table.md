---
title: 'Lync Server 2013: Video Client Event-Tabelle'
description: 'Lync Server 2013: Video Client Event-Tabelle.'
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
ms.openlocfilehash: ae73ac2548e838241febe60a2d31f80983b01de5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568491"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="85406-103">Video Client Event-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85406-103">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85406-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="85406-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="85406-105">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="85406-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="85406-106">Normalerweise verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den angerufenen.</span><span class="sxs-lookup"><span data-stu-id="85406-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85406-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="85406-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="85406-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="85406-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="85406-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="85406-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="85406-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="85406-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85406-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="85406-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85406-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="85406-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="85406-113">Primary</span><span class="sxs-lookup"><span data-stu-id="85406-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="85406-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="85406-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85406-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="85406-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="85406-116">int</span><span class="sxs-lookup"><span data-stu-id="85406-116">int</span></span></p></td>
<td><p><span data-ttu-id="85406-117">Primary</span><span class="sxs-lookup"><span data-stu-id="85406-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="85406-118"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="85406-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85406-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="85406-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="85406-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="85406-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="85406-121">Primary</span><span class="sxs-lookup"><span data-stu-id="85406-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="85406-122"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="85406-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85406-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="85406-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="85406-124">Bit</span><span class="sxs-lookup"><span data-stu-id="85406-124">bit</span></span></p></td>
<td><p><span data-ttu-id="85406-125">Primary</span><span class="sxs-lookup"><span data-stu-id="85406-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="85406-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="85406-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="85406-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="85406-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85406-128"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="85406-128"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="85406-129">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="85406-129">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="85406-130">Die verfügbare Bandbreite reicht für eine akzeptable Spracherfahrung nicht aus.</span><span class="sxs-lookup"><span data-stu-id="85406-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85406-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="85406-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="85406-132">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="85406-132">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="85406-133">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der empfangenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="85406-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

