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
ms.openlocfilehash: 59799e9b6feb076575d8187936a42a408d0dba2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="deddd-102">Videostream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="deddd-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deddd-103">_**Letztes Änderungsstand des Themas:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="deddd-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="deddd-104">Jeder Datensatz stellt einen Videodatenstrom dar.</span><span class="sxs-lookup"><span data-stu-id="deddd-104">Each record represents one video stream.</span></span> <span data-ttu-id="deddd-105">Eine Video Medien Verbindung enthält normalerweise zwei Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="deddd-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="deddd-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="deddd-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="deddd-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="deddd-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="deddd-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="deddd-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="deddd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="deddd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="deddd-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="deddd-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-115">int</span><span class="sxs-lookup"><span data-stu-id="deddd-115">int</span></span></p></td>
<td><p><span data-ttu-id="deddd-116">Primary</span><span class="sxs-lookup"><span data-stu-id="deddd-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="deddd-117">R, die von der <a href="lync-server-2013-medialine-table.md">medialinie-Tabelle in lync Server 2013</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="deddd-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="deddd-120">Primary</span><span class="sxs-lookup"><span data-stu-id="deddd-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="deddd-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="deddd-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-122"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-123">int</span><span class="sxs-lookup"><span data-stu-id="deddd-123">int</span></span></p></td>
<td><p><span data-ttu-id="deddd-124">Primary</span><span class="sxs-lookup"><span data-stu-id="deddd-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="deddd-125">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="deddd-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-127">smallint</span><span class="sxs-lookup"><span data-stu-id="deddd-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="deddd-128">Foreign, Primary</span><span class="sxs-lookup"><span data-stu-id="deddd-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="deddd-129">Beschreibung der Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="deddd-129">Payload description.</span></span> <span data-ttu-id="deddd-130">Weitere Informationen finden Sie <a href="lync-server-2013-payloaddescription-table.md">in der PayloadDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="deddd-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-132">int</span><span class="sxs-lookup"><span data-stu-id="deddd-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-133">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="deddd-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-135">int</span><span class="sxs-lookup"><span data-stu-id="deddd-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-136">Maximale Netzwerk Jitter während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="deddd-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-137"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-138">int</span><span class="sxs-lookup"><span data-stu-id="deddd-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-139">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="deddd-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-141">int</span><span class="sxs-lookup"><span data-stu-id="deddd-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-142">Maximale Zeit für Roundtrips für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="deddd-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-144">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="deddd-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-145">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="deddd-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-147">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="deddd-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-148">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="deddd-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-150">int</span><span class="sxs-lookup"><span data-stu-id="deddd-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-151">Paketwert für den Videostream (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="deddd-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-152"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-153">int</span><span class="sxs-lookup"><span data-stu-id="deddd-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-154">Schätzungen der Bandbreite für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="deddd-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="deddd-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-p103">Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="deddd-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-160">int</span><span class="sxs-lookup"><span data-stu-id="deddd-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-161">Durchschnittliche Bitrate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="deddd-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-163">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="deddd-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-164">Die empfangene Videoframerate.</span><span class="sxs-lookup"><span data-stu-id="deddd-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-166">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="deddd-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-167">Die gesendete Videobildrate.</span><span class="sxs-lookup"><span data-stu-id="deddd-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-169">int</span><span class="sxs-lookup"><span data-stu-id="deddd-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-170">Die maximale Video Bitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="deddd-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-172">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="deddd-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-173">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="deddd-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-175">Bit</span><span class="sxs-lookup"><span data-stu-id="deddd-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-176">Nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="deddd-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-178">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="deddd-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-179">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="deddd-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-182">Der Prozentsatz des Anrufs, bei dem es sich um die CIF-Auflösung (Common Interchange Format) handelte.</span><span class="sxs-lookup"><span data-stu-id="deddd-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-185">Der Prozentsatz des Anrufs, bei dem es sich um eine VGA-Auflösung handelt.</span><span class="sxs-lookup"><span data-stu-id="deddd-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-188">Der Prozentsatz des Anrufs, bei dem die HD720-Auflösung stattfand.</span><span class="sxs-lookup"><span data-stu-id="deddd-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-191">Prozentsatz der Anrufdauer ohne Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="deddd-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-194">Prozentsatz der Anrufdauer mit B-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="deddd-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-197">Prozentsatz der Anrufdauer mit dem BP-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="deddd-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-200">Prozentsatz der Anrufdauer mit BPSP Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="deddd-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="deddd-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-203">Prozentsatz der Anrufdauer mit BPSPI Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="deddd-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-204"><strong>Eingehend</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-205">Bit</span><span class="sxs-lookup"><span data-stu-id="deddd-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-206">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="deddd-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-207"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-208">Bit</span><span class="sxs-lookup"><span data-stu-id="deddd-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-209">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="deddd-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-211">Bit</span><span class="sxs-lookup"><span data-stu-id="deddd-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="deddd-212">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="deddd-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="deddd-213">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="deddd-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-215">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-216">Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="deddd-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="deddd-217">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-219">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-220">Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="deddd-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="deddd-221">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-223">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-224">Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</span><span class="sxs-lookup"><span data-stu-id="deddd-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="deddd-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-227">int</span><span class="sxs-lookup"><span data-stu-id="deddd-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-228">Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="deddd-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="deddd-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-231">int</span><span class="sxs-lookup"><span data-stu-id="deddd-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-232">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="deddd-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="deddd-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-235">int</span><span class="sxs-lookup"><span data-stu-id="deddd-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-236">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="deddd-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="deddd-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-239">int</span><span class="sxs-lookup"><span data-stu-id="deddd-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-240">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="deddd-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="deddd-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-243">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-244">Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung keine MultiView-Videounterstützung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="deddd-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="deddd-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-247">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p104">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-250">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-252">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p105">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-255">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-257">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p106">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-260">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-262">int</span><span class="sxs-lookup"><span data-stu-id="deddd-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p107">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-266">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-268">int</span><span class="sxs-lookup"><span data-stu-id="deddd-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p108">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-272">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-274">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p109">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-278">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-280">int</span><span class="sxs-lookup"><span data-stu-id="deddd-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p110">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-284">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-286">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p111">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-290">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-292">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-p112">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="deddd-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="deddd-296">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-298">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="deddd-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-299">Videpaketverlustrate.</span><span class="sxs-lookup"><span data-stu-id="deddd-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="deddd-300">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-302">int</span><span class="sxs-lookup"><span data-stu-id="deddd-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-303">Durchschnittliche für Video reservierte Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="deddd-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="deddd-304">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-306">smallint</span><span class="sxs-lookup"><span data-stu-id="deddd-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="deddd-307">Fremd</span><span class="sxs-lookup"><span data-stu-id="deddd-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="deddd-308">Typ der Video Codecs, die vom Absender verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="deddd-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="deddd-309">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="deddd-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="deddd-310">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-312">int</span><span class="sxs-lookup"><span data-stu-id="deddd-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-313">Vom Absender verwendete Auflösungsbreite.</span><span class="sxs-lookup"><span data-stu-id="deddd-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="deddd-314">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-316">int</span><span class="sxs-lookup"><span data-stu-id="deddd-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-317">Vom Absender verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="deddd-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="deddd-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-320">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-321">Durchschnittliche Übertragungsrate für Videoframes, die vom Absender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="deddd-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="deddd-322">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-324">int</span><span class="sxs-lookup"><span data-stu-id="deddd-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-325">Maximale Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="deddd-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="deddd-326">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-328">int</span><span class="sxs-lookup"><span data-stu-id="deddd-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-329">Durchschnittliche Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="deddd-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-331">int</span><span class="sxs-lookup"><span data-stu-id="deddd-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-332">Maximale Anzahl der vom Absender verwendeten Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="deddd-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="deddd-333">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-335">smallint</span><span class="sxs-lookup"><span data-stu-id="deddd-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="deddd-336">Fremd</span><span class="sxs-lookup"><span data-stu-id="deddd-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="deddd-337">Vom Empfänger verwendete Video Codes.</span><span class="sxs-lookup"><span data-stu-id="deddd-337">Video codes used by the receiver.</span></span> <span data-ttu-id="deddd-338">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="deddd-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="deddd-339">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-341">int</span><span class="sxs-lookup"><span data-stu-id="deddd-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-342">Auflösung Breite, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="deddd-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="deddd-343">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-345">int</span><span class="sxs-lookup"><span data-stu-id="deddd-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-346">Vom Empfänger verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="deddd-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="deddd-347">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-349">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-350">Durchschnittliche Videobildrate, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="deddd-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="deddd-351">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-353">int</span><span class="sxs-lookup"><span data-stu-id="deddd-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-354">Maximale Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="deddd-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="deddd-355">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-357">int</span><span class="sxs-lookup"><span data-stu-id="deddd-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-358">Durchschnittliche Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="deddd-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="deddd-359">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-361">int</span><span class="sxs-lookup"><span data-stu-id="deddd-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-362">Maximale Anzahl von Videodatenströmen für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="deddd-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="deddd-363">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-365">int</span><span class="sxs-lookup"><span data-stu-id="deddd-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-366">Minimale Videodatenströme für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="deddd-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="deddd-367">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-369">int</span><span class="sxs-lookup"><span data-stu-id="deddd-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-370">Video Modus (beispielsweise Galerie oder einzelner Datenstrom) für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="deddd-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="deddd-371">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-373">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-374">Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="deddd-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="deddd-375">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-377">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-378">Prozentsatz der Zeit, die das Flag für dynamische Funktionen aktiv war.</span><span class="sxs-lookup"><span data-stu-id="deddd-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="deddd-379">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="deddd-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-382">Minimale Auflösung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="deddd-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="deddd-383">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-385">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-386">Prozentsatz des Anrufs unterhalb des Schwellenwerts mit niedriger Bitrate (70 Kbit/s).</span><span class="sxs-lookup"><span data-stu-id="deddd-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="deddd-387">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-389">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-390">Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Frameraten (7,5 Frames pro Sekunde, eingehend).</span><span class="sxs-lookup"><span data-stu-id="deddd-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="deddd-391">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-393">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-394">Prozentsatz des Anrufs, der bei der niedrigsten Auflösung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="deddd-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="deddd-395">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="deddd-396">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="deddd-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-398">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="deddd-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-399">Die Dauer des Anrufs in Sekunden.</span><span class="sxs-lookup"><span data-stu-id="deddd-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="deddd-400">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="deddd-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="deddd-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="deddd-402">Bit</span><span class="sxs-lookup"><span data-stu-id="deddd-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="deddd-403">Gibt an, ob die Daten aus mehreren Aufrufen aggregiert wurden.</span><span class="sxs-lookup"><span data-stu-id="deddd-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="deddd-404">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="deddd-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

