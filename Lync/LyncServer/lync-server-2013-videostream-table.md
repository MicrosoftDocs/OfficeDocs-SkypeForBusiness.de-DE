---
title: 'Lync Server 2013: Videostream-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00abc61fc7ba83b94f3228de91eb9fa6810fc93c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="d12be-102">Videostream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d12be-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d12be-103">_**Letztes Änderungsstand des Themas:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="d12be-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="d12be-104">Jeder Datensatz stellt einen Videodatenstrom dar.</span><span class="sxs-lookup"><span data-stu-id="d12be-104">Each record represents one video stream.</span></span> <span data-ttu-id="d12be-105">Eine Video Medien Verbindung enthält normalerweise zwei Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="d12be-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d12be-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d12be-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d12be-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d12be-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d12be-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d12be-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d12be-112">Primary</span><span class="sxs-lookup"><span data-stu-id="d12be-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d12be-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d12be-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-115">int</span><span class="sxs-lookup"><span data-stu-id="d12be-115">int</span></span></p></td>
<td><p><span data-ttu-id="d12be-116">Primary</span><span class="sxs-lookup"><span data-stu-id="d12be-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="d12be-117">R, die von der <a href="lync-server-2013-medialine-table.md">medialinie-Tabelle in lync Server 2013</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="d12be-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d12be-120">Primary</span><span class="sxs-lookup"><span data-stu-id="d12be-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="d12be-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d12be-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-122"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-123">int</span><span class="sxs-lookup"><span data-stu-id="d12be-123">int</span></span></p></td>
<td><p><span data-ttu-id="d12be-124">Primary</span><span class="sxs-lookup"><span data-stu-id="d12be-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="d12be-125">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="d12be-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-127">smallint</span><span class="sxs-lookup"><span data-stu-id="d12be-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="d12be-128">Foreign, Primary</span><span class="sxs-lookup"><span data-stu-id="d12be-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="d12be-129">Beschreibung der Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="d12be-129">Payload description.</span></span> <span data-ttu-id="d12be-130">Weitere Informationen finden Sie <a href="lync-server-2013-payloaddescription-table.md">in der PayloadDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d12be-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-132">int</span><span class="sxs-lookup"><span data-stu-id="d12be-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-133">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="d12be-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-135">int</span><span class="sxs-lookup"><span data-stu-id="d12be-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-136">Maximale Netzwerk Jitter während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="d12be-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-137"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-138">int</span><span class="sxs-lookup"><span data-stu-id="d12be-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-139">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="d12be-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-141">int</span><span class="sxs-lookup"><span data-stu-id="d12be-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-142">Maximale Zeit für Roundtrips für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="d12be-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-144">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d12be-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-145">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d12be-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-147">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d12be-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-148">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d12be-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-150">int</span><span class="sxs-lookup"><span data-stu-id="d12be-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-151">Paketwert für den Videostream (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="d12be-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-152"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-153">int</span><span class="sxs-lookup"><span data-stu-id="d12be-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-154">Schätzungen der Bandbreite für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="d12be-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="d12be-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-p103">Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d12be-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-160">int</span><span class="sxs-lookup"><span data-stu-id="d12be-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-161">Durchschnittliche Bitrate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="d12be-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-163">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d12be-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-164">Die empfangene Videoframerate.</span><span class="sxs-lookup"><span data-stu-id="d12be-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-166">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d12be-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-167">Die gesendete Videobildrate.</span><span class="sxs-lookup"><span data-stu-id="d12be-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-169">int</span><span class="sxs-lookup"><span data-stu-id="d12be-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-170">Die maximale Video Bitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="d12be-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-172">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d12be-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-173">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="d12be-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-175">Bit</span><span class="sxs-lookup"><span data-stu-id="d12be-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-176">Nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d12be-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-178">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d12be-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-179">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="d12be-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-182">Der Prozentsatz des Anrufs, bei dem es sich um die CIF-Auflösung (Common Interchange Format) handelte.</span><span class="sxs-lookup"><span data-stu-id="d12be-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-185">Der Prozentsatz des Anrufs, bei dem es sich um eine VGA-Auflösung handelt.</span><span class="sxs-lookup"><span data-stu-id="d12be-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-188">Der Prozentsatz des Anrufs, bei dem die HD720-Auflösung stattfand.</span><span class="sxs-lookup"><span data-stu-id="d12be-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-191">Prozentsatz der Anrufdauer ohne Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="d12be-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-194">Prozentsatz der Anrufdauer mit B-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="d12be-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-197">Prozentsatz der Anrufdauer mit dem BP-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="d12be-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-200">Prozentsatz der Anrufdauer mit BPSP Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="d12be-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="d12be-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-203">Prozentsatz der Anrufdauer mit BPSPI Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="d12be-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-204"><strong>Eingehend</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-205">Bit</span><span class="sxs-lookup"><span data-stu-id="d12be-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-206">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="d12be-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-207"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-208">Bit</span><span class="sxs-lookup"><span data-stu-id="d12be-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-209">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="d12be-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-211">Bit</span><span class="sxs-lookup"><span data-stu-id="d12be-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d12be-212">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="d12be-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="d12be-213">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="d12be-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-215">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-216">Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="d12be-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="d12be-217">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-219">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-220">Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="d12be-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="d12be-221">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-223">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-224">Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</span><span class="sxs-lookup"><span data-stu-id="d12be-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="d12be-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-227">int</span><span class="sxs-lookup"><span data-stu-id="d12be-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-228">Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="d12be-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d12be-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-231">int</span><span class="sxs-lookup"><span data-stu-id="d12be-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-232">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="d12be-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d12be-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-235">int</span><span class="sxs-lookup"><span data-stu-id="d12be-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-236">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="d12be-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d12be-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-239">int</span><span class="sxs-lookup"><span data-stu-id="d12be-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-240">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="d12be-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="d12be-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-243">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-244">Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung keine MultiView-Videounterstützung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d12be-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="d12be-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-247">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p104">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-250">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-252">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p105">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-255">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-257">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p106">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-260">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-262">int</span><span class="sxs-lookup"><span data-stu-id="d12be-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p107">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-266">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-268">int</span><span class="sxs-lookup"><span data-stu-id="d12be-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p108">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-272">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-274">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p109">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-278">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-280">int</span><span class="sxs-lookup"><span data-stu-id="d12be-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p110">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-284">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-286">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p111">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-290">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-292">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-p112">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="d12be-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="d12be-296">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-298">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d12be-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-299">Videpaketverlustrate.</span><span class="sxs-lookup"><span data-stu-id="d12be-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="d12be-300">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-302">int</span><span class="sxs-lookup"><span data-stu-id="d12be-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-303">Durchschnittliche für Video reservierte Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="d12be-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="d12be-304">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-306">smallint</span><span class="sxs-lookup"><span data-stu-id="d12be-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="d12be-307">Fremd</span><span class="sxs-lookup"><span data-stu-id="d12be-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d12be-308">Typ der Video Codecs, die vom Absender verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d12be-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="d12be-309">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d12be-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="d12be-310">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-312">int</span><span class="sxs-lookup"><span data-stu-id="d12be-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-313">Vom Absender verwendete Auflösungsbreite.</span><span class="sxs-lookup"><span data-stu-id="d12be-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="d12be-314">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-316">int</span><span class="sxs-lookup"><span data-stu-id="d12be-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-317">Vom Absender verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="d12be-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="d12be-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-320">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-321">Durchschnittliche Übertragungsrate für Videoframes, die vom Absender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d12be-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="d12be-322">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-324">int</span><span class="sxs-lookup"><span data-stu-id="d12be-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-325">Maximale Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="d12be-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="d12be-326">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-328">int</span><span class="sxs-lookup"><span data-stu-id="d12be-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-329">Durchschnittliche Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="d12be-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-331">int</span><span class="sxs-lookup"><span data-stu-id="d12be-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-332">Maximale Anzahl der vom Absender verwendeten Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="d12be-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="d12be-333">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-335">smallint</span><span class="sxs-lookup"><span data-stu-id="d12be-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="d12be-336">Fremd</span><span class="sxs-lookup"><span data-stu-id="d12be-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d12be-337">Vom Empfänger verwendete Video Codes.</span><span class="sxs-lookup"><span data-stu-id="d12be-337">Video codes used by the receiver.</span></span> <span data-ttu-id="d12be-338">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d12be-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="d12be-339">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-341">int</span><span class="sxs-lookup"><span data-stu-id="d12be-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-342">Auflösung Breite, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d12be-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="d12be-343">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-345">int</span><span class="sxs-lookup"><span data-stu-id="d12be-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-346">Vom Empfänger verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="d12be-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="d12be-347">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-349">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-350">Durchschnittliche Videobildrate, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d12be-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="d12be-351">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-353">int</span><span class="sxs-lookup"><span data-stu-id="d12be-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-354">Maximale Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="d12be-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="d12be-355">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-357">int</span><span class="sxs-lookup"><span data-stu-id="d12be-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-358">Durchschnittliche Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="d12be-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="d12be-359">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-361">int</span><span class="sxs-lookup"><span data-stu-id="d12be-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-362">Maximale Anzahl von Videodatenströmen für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="d12be-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="d12be-363">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-365">int</span><span class="sxs-lookup"><span data-stu-id="d12be-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-366">Minimale Videodatenströme für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="d12be-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="d12be-367">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-369">int</span><span class="sxs-lookup"><span data-stu-id="d12be-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-370">Video Modus (beispielsweise Galerie oder einzelner Datenstrom) für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="d12be-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="d12be-371">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-373">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-374">Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d12be-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="d12be-375">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-377">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-378">Prozentsatz der Zeit, die das Flag für dynamische Funktionen aktiv war.</span><span class="sxs-lookup"><span data-stu-id="d12be-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="d12be-379">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="d12be-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-382">Minimale Auflösung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="d12be-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="d12be-383">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-385">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-386">Prozentsatz des Anrufs unterhalb des Schwellenwerts mit niedriger Bitrate (70 Kbit/s).</span><span class="sxs-lookup"><span data-stu-id="d12be-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="d12be-387">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-389">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-390">Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Frameraten (7,5 Frames pro Sekunde, eingehend).</span><span class="sxs-lookup"><span data-stu-id="d12be-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="d12be-391">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-393">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-394">Prozentsatz des Anrufs, der bei der niedrigsten Auflösung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d12be-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="d12be-395">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="d12be-396">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d12be-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-398">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d12be-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-399">Die Dauer des Anrufs in Sekunden.</span><span class="sxs-lookup"><span data-stu-id="d12be-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="d12be-400">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d12be-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="d12be-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="d12be-402">Bit</span><span class="sxs-lookup"><span data-stu-id="d12be-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d12be-403">Gibt an, ob die Daten aus mehreren Aufrufen aggregiert wurden.</span><span class="sxs-lookup"><span data-stu-id="d12be-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="d12be-404">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d12be-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

