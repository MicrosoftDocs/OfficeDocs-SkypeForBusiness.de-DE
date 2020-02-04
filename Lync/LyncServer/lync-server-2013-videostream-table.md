---
title: 'Lync Server 2013: VideoStream-Tabelle'
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
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="93623-102">VideoStream-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93623-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93623-103">_**Letztes Änderungsdatum des Themas:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="93623-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="93623-104">Jeder Datensatz steht für einen Videostream.</span><span class="sxs-lookup"><span data-stu-id="93623-104">Each record represents one video stream.</span></span> <span data-ttu-id="93623-105">Eine Video medienzeile enthält in der Regel zwei Videostreams.</span><span class="sxs-lookup"><span data-stu-id="93623-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93623-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="93623-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="93623-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="93623-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="93623-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="93623-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="93623-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="93623-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93623-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="93623-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-111">datetime</span><span class="sxs-lookup"><span data-stu-id="93623-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="93623-112">Primary</span><span class="sxs-lookup"><span data-stu-id="93623-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="93623-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="93623-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="93623-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-115">int</span><span class="sxs-lookup"><span data-stu-id="93623-115">int</span></span></p></td>
<td><p><span data-ttu-id="93623-116">Primary</span><span class="sxs-lookup"><span data-stu-id="93623-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="93623-117">R, auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="93623-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="93623-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="93623-120">Primary</span><span class="sxs-lookup"><span data-stu-id="93623-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="93623-121">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="93623-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-122"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="93623-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-123">int</span><span class="sxs-lookup"><span data-stu-id="93623-123">int</span></span></p></td>
<td><p><span data-ttu-id="93623-124">Primary</span><span class="sxs-lookup"><span data-stu-id="93623-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="93623-125">Eindeutige ID innerhalb einer medienzeile</span><span class="sxs-lookup"><span data-stu-id="93623-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="93623-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-127">smallint</span><span class="sxs-lookup"><span data-stu-id="93623-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="93623-128">Fremd, primär</span><span class="sxs-lookup"><span data-stu-id="93623-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="93623-129">Nutzlast-Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="93623-129">Payload description.</span></span> <span data-ttu-id="93623-130">Weitere Informationen finden Sie <a href="lync-server-2013-payloaddescription-table.md">in der PayloadDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="93623-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="93623-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-132">int</span><span class="sxs-lookup"><span data-stu-id="93623-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-133">Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="93623-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-135">int</span><span class="sxs-lookup"><span data-stu-id="93623-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-136">Maximaler Netzwerk Jitter während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="93623-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="93623-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-138">int</span><span class="sxs-lookup"><span data-stu-id="93623-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-139">Roundtrip-Zeit von RTCP-Statistiken</span><span class="sxs-lookup"><span data-stu-id="93623-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-141">int</span><span class="sxs-lookup"><span data-stu-id="93623-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-142">Maximale Roundtrip-Zeit für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="93623-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="93623-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-144">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="93623-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-145">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="93623-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-147">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="93623-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-148">Maximaler Paketverlust während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="93623-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="93623-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-150">int</span><span class="sxs-lookup"><span data-stu-id="93623-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-151">Paketanzahl für den Videostream (Echt Zeit Transport Protokoll, RTP).</span><span class="sxs-lookup"><span data-stu-id="93623-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-152"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="93623-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-153">int</span><span class="sxs-lookup"><span data-stu-id="93623-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-154">Bandbreiten Schätzungen für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="93623-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="93623-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="93623-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-157">Auflösung des Videos in Pixel Breite multipliziert mit Höhe des Pixels.</span><span class="sxs-lookup"><span data-stu-id="93623-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="93623-158">Als Zeichenfolge gemeldet.</span><span class="sxs-lookup"><span data-stu-id="93623-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="93623-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-160">int</span><span class="sxs-lookup"><span data-stu-id="93623-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-161">Durchschnittliche Bitrate des Videodatenstroms.</span><span class="sxs-lookup"><span data-stu-id="93623-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="93623-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-163">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="93623-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-164">Die empfangene Videobildrate.</span><span class="sxs-lookup"><span data-stu-id="93623-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="93623-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-166">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="93623-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-167">Die Videobildrate wird gesendet.</span><span class="sxs-lookup"><span data-stu-id="93623-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-169">int</span><span class="sxs-lookup"><span data-stu-id="93623-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-170">Die maximale Video-Bitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="93623-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="93623-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-172">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="93623-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-173">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="93623-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="93623-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-175">bit</span><span class="sxs-lookup"><span data-stu-id="93623-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-176">Nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="93623-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="93623-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-178">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="93623-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-179">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="93623-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-182">Der Prozentsatz des Anrufs, der sich in der CIF-Auflösung (Common Interchange Format) befand.</span><span class="sxs-lookup"><span data-stu-id="93623-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-185">Der Prozentsatz des Anrufs mit VGA-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="93623-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-188">Der Prozentsatz des Anrufs, der mit der HD720-Auflösung erfolgte.</span><span class="sxs-lookup"><span data-stu-id="93623-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-191">Prozentsatz der Anrufdauer ohne Frame-Drop</span><span class="sxs-lookup"><span data-stu-id="93623-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-194">Prozentsatz der Anrufdauer mit B-Frame-Abwurf.</span><span class="sxs-lookup"><span data-stu-id="93623-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-197">Prozentsatz der Anrufdauer mit BP-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="93623-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-200">Prozentsatz der Anrufdauer mit BPSP Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="93623-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="93623-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="93623-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-203">Prozentsatz der Anrufdauer mit BPSPI Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="93623-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-204"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="93623-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-205">bit</span><span class="sxs-lookup"><span data-stu-id="93623-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-206">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="93623-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-207"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="93623-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-208">bit</span><span class="sxs-lookup"><span data-stu-id="93623-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-209">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="93623-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="93623-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-211">bit</span><span class="sxs-lookup"><span data-stu-id="93623-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93623-212">1 bedeutet, dass die Datenstrom Richtung vom Aufrufer zu aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="93623-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="93623-213">0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</span><span class="sxs-lookup"><span data-stu-id="93623-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="93623-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-215">float</span><span class="sxs-lookup"><span data-stu-id="93623-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-216">Gibt den Prozentsatz der Zeit an, zu der sich der Anruf in einem Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="93623-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="93623-217">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="93623-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-219">float</span><span class="sxs-lookup"><span data-stu-id="93623-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-220">Gibt den Prozentsatz des Anrufs an, während dessen Überlastung durch das verspätete Eintreffen von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="93623-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="93623-221">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="93623-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-223">float</span><span class="sxs-lookup"><span data-stu-id="93623-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-224">Gibt den Prozentsatz der Zeit an, zu der der Anruf im Wettbewerb um Netzwerkressourcen erfolgte.</span><span class="sxs-lookup"><span data-stu-id="93623-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="93623-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="93623-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-227">int</span><span class="sxs-lookup"><span data-stu-id="93623-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-228">Minimaler Grad der Bandbreitenschätzung, gemessen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="93623-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="93623-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-231">int</span><span class="sxs-lookup"><span data-stu-id="93623-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-232">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="93623-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="93623-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="93623-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-235">int</span><span class="sxs-lookup"><span data-stu-id="93623-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-236">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="93623-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="93623-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="93623-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-239">int</span><span class="sxs-lookup"><span data-stu-id="93623-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-240">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="93623-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="93623-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="93623-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-243">float</span><span class="sxs-lookup"><span data-stu-id="93623-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-244">Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung MultiView-Video nicht unterstützenkann.</span><span class="sxs-lookup"><span data-stu-id="93623-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="93623-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="93623-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-247">float</span><span class="sxs-lookup"><span data-stu-id="93623-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-248">Gesamtzahl der unidirektionalen Latenzzeit.</span><span class="sxs-lookup"><span data-stu-id="93623-248">Total amount of one-way latency.</span></span> <span data-ttu-id="93623-249">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-250">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="93623-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-252">float</span><span class="sxs-lookup"><span data-stu-id="93623-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-253">Durchschnittliche Anzahl der unidirektionalen Latenzzeit.</span><span class="sxs-lookup"><span data-stu-id="93623-253">Average amount of one-way latency.</span></span> <span data-ttu-id="93623-254">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-255">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-257">float</span><span class="sxs-lookup"><span data-stu-id="93623-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-258">Maximale Anzahl von unidirektionalen Latenzzeiten.</span><span class="sxs-lookup"><span data-stu-id="93623-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="93623-259">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-260">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="93623-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-262">int</span><span class="sxs-lookup"><span data-stu-id="93623-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-263">Gesamtzahl der einseitigen Burst-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="93623-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="93623-264">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="93623-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="93623-265">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-266">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="93623-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-268">int</span><span class="sxs-lookup"><span data-stu-id="93623-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-269">Totale unidirektionale Burst Dichte.</span><span class="sxs-lookup"><span data-stu-id="93623-269">Total one-way burst density.</span></span> <span data-ttu-id="93623-270">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="93623-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="93623-271">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-272">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="93623-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-274">float</span><span class="sxs-lookup"><span data-stu-id="93623-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-275">Gesamtdauer des einseitigen Bursts.</span><span class="sxs-lookup"><span data-stu-id="93623-275">Total one-way burst duration.</span></span> <span data-ttu-id="93623-276">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="93623-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="93623-277">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-278">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="93623-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-280">int</span><span class="sxs-lookup"><span data-stu-id="93623-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-281">Gesamtanzahl der einseitigen Lücken.</span><span class="sxs-lookup"><span data-stu-id="93623-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="93623-282">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="93623-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="93623-283">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-284">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="93623-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-286">float</span><span class="sxs-lookup"><span data-stu-id="93623-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-287">Gesamtdichte für einseitigen Abstand.</span><span class="sxs-lookup"><span data-stu-id="93623-287">Total one-way gap density.</span></span> <span data-ttu-id="93623-288">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="93623-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="93623-289">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-290">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="93623-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-292">float</span><span class="sxs-lookup"><span data-stu-id="93623-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-293">Gesamtdauer der einseitigen Lücke</span><span class="sxs-lookup"><span data-stu-id="93623-293">Total one-way gap duration.</span></span> <span data-ttu-id="93623-294">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="93623-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="93623-295">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="93623-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="93623-296">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="93623-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-298">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="93623-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-299">Die Rate, mit der Videopakete verloren gegangen sind.</span><span class="sxs-lookup"><span data-stu-id="93623-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="93623-300">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="93623-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-302">int</span><span class="sxs-lookup"><span data-stu-id="93623-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-303">Der durchschnittliche Umfang der für Video zugewiesenen Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="93623-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="93623-304">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="93623-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-306">smallint</span><span class="sxs-lookup"><span data-stu-id="93623-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="93623-307">Fremd</span><span class="sxs-lookup"><span data-stu-id="93623-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="93623-308">Der Typ der vom Absender verwendeten Video-Codecs.</span><span class="sxs-lookup"><span data-stu-id="93623-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="93623-309">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="93623-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="93623-310">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="93623-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-312">int</span><span class="sxs-lookup"><span data-stu-id="93623-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-313">Vom Absender verwendete Auflösungsbreite.</span><span class="sxs-lookup"><span data-stu-id="93623-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="93623-314">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="93623-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-316">int</span><span class="sxs-lookup"><span data-stu-id="93623-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-317">Die vom Absender verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="93623-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="93623-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="93623-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-320">float</span><span class="sxs-lookup"><span data-stu-id="93623-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-321">Durchschnittliche Übertragungsrate für Video-Frames, die vom Absender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="93623-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="93623-322">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="93623-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-324">int</span><span class="sxs-lookup"><span data-stu-id="93623-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-325">Die maximale Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="93623-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="93623-326">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="93623-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-328">int</span><span class="sxs-lookup"><span data-stu-id="93623-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-329">Durchschnittliche Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="93623-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-331">int</span><span class="sxs-lookup"><span data-stu-id="93623-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-332">Maximale Anzahl der vom Absender verwendeten Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="93623-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="93623-333">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="93623-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-335">smallint</span><span class="sxs-lookup"><span data-stu-id="93623-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="93623-336">Fremd</span><span class="sxs-lookup"><span data-stu-id="93623-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="93623-337">Vom Empfänger verwendete Video Codes.</span><span class="sxs-lookup"><span data-stu-id="93623-337">Video codes used by the receiver.</span></span> <span data-ttu-id="93623-338">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="93623-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="93623-339">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="93623-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-341">int</span><span class="sxs-lookup"><span data-stu-id="93623-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-342">Vom Empfänger verwendete Auflösungsbreite.</span><span class="sxs-lookup"><span data-stu-id="93623-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="93623-343">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="93623-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-345">int</span><span class="sxs-lookup"><span data-stu-id="93623-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-346">Vom Empfänger verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="93623-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="93623-347">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="93623-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-349">float</span><span class="sxs-lookup"><span data-stu-id="93623-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-350">Durchschnittliche Videobildrate, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="93623-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="93623-351">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="93623-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-353">int</span><span class="sxs-lookup"><span data-stu-id="93623-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-354">Maximale Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="93623-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="93623-355">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="93623-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-357">int</span><span class="sxs-lookup"><span data-stu-id="93623-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-358">Durchschnittliche Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="93623-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="93623-359">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="93623-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-361">int</span><span class="sxs-lookup"><span data-stu-id="93623-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-362">Maximale Videodatenströme für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="93623-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="93623-363">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="93623-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-365">int</span><span class="sxs-lookup"><span data-stu-id="93623-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-366">Minimale Videodatenströme für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="93623-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="93623-367">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="93623-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-369">int</span><span class="sxs-lookup"><span data-stu-id="93623-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-370">Video Modus (beispielsweise Katalog oder einzelner Datenstrom) für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="93623-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="93623-371">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="93623-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-373">float</span><span class="sxs-lookup"><span data-stu-id="93623-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-374">Die Paketverlustrate, nachdem die weiter Leitungsfehler Korrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="93623-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="93623-375">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="93623-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-377">float</span><span class="sxs-lookup"><span data-stu-id="93623-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-378">Der Prozentsatz der Zeit, zu der das Flag für dynamische Funktionen aktiv war.</span><span class="sxs-lookup"><span data-stu-id="93623-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="93623-379">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="93623-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="93623-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-382">Minimale Auflösung während des Anrufs gemessen.</span><span class="sxs-lookup"><span data-stu-id="93623-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="93623-383">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="93623-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-385">float</span><span class="sxs-lookup"><span data-stu-id="93623-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-386">Der Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Bitraten (70 Kbit/s).</span><span class="sxs-lookup"><span data-stu-id="93623-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="93623-387">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-388"><strong>Framerate (</strong></span><span class="sxs-lookup"><span data-stu-id="93623-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-389">float</span><span class="sxs-lookup"><span data-stu-id="93623-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-390">Der Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Bildrate (7,5 Frames pro Sekunde, eingehend).</span><span class="sxs-lookup"><span data-stu-id="93623-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="93623-391">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="93623-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-393">float</span><span class="sxs-lookup"><span data-stu-id="93623-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-394">Der Prozentsatz des Anrufs, der mit der niedrigsten Auflösung erfolgte.</span><span class="sxs-lookup"><span data-stu-id="93623-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="93623-395">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="93623-396">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93623-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="93623-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-398">float</span><span class="sxs-lookup"><span data-stu-id="93623-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-399">Die Länge des Anrufs in Sekunden.</span><span class="sxs-lookup"><span data-stu-id="93623-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="93623-400">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93623-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="93623-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="93623-402">bit</span><span class="sxs-lookup"><span data-stu-id="93623-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="93623-403">Gibt an, ob die Daten aus mehreren anrufen aggregiert wurden.</span><span class="sxs-lookup"><span data-stu-id="93623-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="93623-404">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="93623-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

