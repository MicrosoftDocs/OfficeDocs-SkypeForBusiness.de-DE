---
title: 'Lync Server 2013: Video Client Event-Tabelle'
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
ms.openlocfilehash: a687e503b9dfd02c296e1e96d88b93c716d7c54b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="f16ce-102">Video Client Event-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f16ce-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f16ce-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f16ce-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f16ce-104">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Videoanruf.</span><span class="sxs-lookup"><span data-stu-id="f16ce-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="f16ce-105">Normalerweise verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den angerufenen.</span><span class="sxs-lookup"><span data-stu-id="f16ce-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f16ce-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f16ce-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f16ce-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f16ce-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f16ce-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f16ce-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f16ce-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f16ce-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f16ce-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f16ce-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="f16ce-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f16ce-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f16ce-115">int</span><span class="sxs-lookup"><span data-stu-id="f16ce-115">int</span></span></p></td>
<td><p><span data-ttu-id="f16ce-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f16ce-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f16ce-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="f16ce-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f16ce-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f16ce-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f16ce-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f16ce-120">Primary</span><span class="sxs-lookup"><span data-stu-id="f16ce-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f16ce-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="f16ce-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f16ce-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="f16ce-123">Bit</span><span class="sxs-lookup"><span data-stu-id="f16ce-123">bit</span></span></p></td>
<td><p><span data-ttu-id="f16ce-124">Primary</span><span class="sxs-lookup"><span data-stu-id="f16ce-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f16ce-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="f16ce-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="f16ce-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="f16ce-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f16ce-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f16ce-128">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f16ce-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f16ce-129">Die verfügbare Bandbreite reicht für eine akzeptable Spracherfahrung nicht aus.</span><span class="sxs-lookup"><span data-stu-id="f16ce-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f16ce-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f16ce-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f16ce-131">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f16ce-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f16ce-132">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der empfangenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="f16ce-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

