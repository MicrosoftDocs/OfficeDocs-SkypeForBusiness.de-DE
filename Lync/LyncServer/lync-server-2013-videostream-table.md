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
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="ade2b-102">Videostream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ade2b-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ade2b-103">_**Letztes Änderungsstand des Themas:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="ade2b-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="ade2b-104">Jeder Datensatz stellt einen Videodatenstrom dar.</span><span class="sxs-lookup"><span data-stu-id="ade2b-104">Each record represents one video stream.</span></span> <span data-ttu-id="ade2b-105">Eine Video Medien Verbindung enthält normalerweise zwei Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="ade2b-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ade2b-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ade2b-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ade2b-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ade2b-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ade2b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ade2b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ade2b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ade2b-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="ade2b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-115">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-115">int</span></span></p></td>
<td><p><span data-ttu-id="ade2b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="ade2b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ade2b-117">R, die von der <a href="lync-server-2013-medialine-table.md">medialinie-Tabelle in lync Server 2013</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="ade2b-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ade2b-120">Primary</span><span class="sxs-lookup"><span data-stu-id="ade2b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="ade2b-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="ade2b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-122"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-123">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-123">int</span></span></p></td>
<td><p><span data-ttu-id="ade2b-124">Primary</span><span class="sxs-lookup"><span data-stu-id="ade2b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="ade2b-125">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="ade2b-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-127">smallint</span><span class="sxs-lookup"><span data-stu-id="ade2b-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="ade2b-128">Foreign, Primary</span><span class="sxs-lookup"><span data-stu-id="ade2b-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="ade2b-129">Beschreibung der Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="ade2b-129">Payload description.</span></span> <span data-ttu-id="ade2b-130">Weitere Informationen finden Sie <a href="lync-server-2013-payloaddescription-table.md">in der PayloadDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ade2b-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-132">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-133">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="ade2b-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-135">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-136">Maximale Netzwerk Jitter während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="ade2b-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-137"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-138">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-139">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="ade2b-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-141">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-142">Maximale Zeit für Roundtrips für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="ade2b-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-144">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ade2b-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-145">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="ade2b-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-147">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ade2b-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-148">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="ade2b-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-150">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-151">Paketwert für den Videostream (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="ade2b-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-152"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-153">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-154">Schätzungen der Bandbreite für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="ade2b-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="ade2b-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-p103">Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-160">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-161">Durchschnittliche Bitrate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="ade2b-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-163">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ade2b-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-164">Die empfangene Videoframerate.</span><span class="sxs-lookup"><span data-stu-id="ade2b-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-166">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ade2b-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-167">Die gesendete Videobildrate.</span><span class="sxs-lookup"><span data-stu-id="ade2b-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-169">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-170">Die maximale Video Bitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="ade2b-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-172">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ade2b-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-173">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="ade2b-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-175">Bit</span><span class="sxs-lookup"><span data-stu-id="ade2b-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-176">Nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ade2b-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-178">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ade2b-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-179">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="ade2b-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-182">Der Prozentsatz des Anrufs, bei dem es sich um die CIF-Auflösung (Common Interchange Format) handelte.</span><span class="sxs-lookup"><span data-stu-id="ade2b-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-185">Der Prozentsatz des Anrufs, bei dem es sich um eine VGA-Auflösung handelt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-188">Der Prozentsatz des Anrufs, bei dem die HD720-Auflösung stattfand.</span><span class="sxs-lookup"><span data-stu-id="ade2b-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-191">Prozentsatz der Anrufdauer ohne Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="ade2b-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-194">Prozentsatz der Anrufdauer mit B-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="ade2b-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-197">Prozentsatz der Anrufdauer mit dem BP-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="ade2b-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-200">Prozentsatz der Anrufdauer mit BPSP Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="ade2b-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="ade2b-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-203">Prozentsatz der Anrufdauer mit BPSPI Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="ade2b-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-204"><strong>Eingehend</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-205">Bit</span><span class="sxs-lookup"><span data-stu-id="ade2b-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-206">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="ade2b-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-207"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-208">Bit</span><span class="sxs-lookup"><span data-stu-id="ade2b-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-209">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="ade2b-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-211">Bit</span><span class="sxs-lookup"><span data-stu-id="ade2b-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ade2b-212">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="ade2b-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="ade2b-213">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="ade2b-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-215">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-216">Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="ade2b-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="ade2b-217">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-219">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-220">Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="ade2b-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="ade2b-221">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-223">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-224">Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</span><span class="sxs-lookup"><span data-stu-id="ade2b-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="ade2b-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-227">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-228">Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="ade2b-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ade2b-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-231">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-232">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="ade2b-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ade2b-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-235">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-236">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="ade2b-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ade2b-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-239">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-240">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="ade2b-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="ade2b-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-243">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-244">Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung keine MultiView-Videounterstützung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="ade2b-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-247">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p104">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-250">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-252">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p105">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-255">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-257">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p106">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-260">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-262">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p107">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-266">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-268">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p108">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-272">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-274">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p109">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-278">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-280">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p110">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-284">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-286">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p111">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-290">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-292">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-p112">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="ade2b-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="ade2b-296">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-298">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ade2b-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-299">Videpaketverlustrate.</span><span class="sxs-lookup"><span data-stu-id="ade2b-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="ade2b-300">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-302">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-303">Durchschnittliche für Video reservierte Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="ade2b-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="ade2b-304">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-306">smallint</span><span class="sxs-lookup"><span data-stu-id="ade2b-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="ade2b-307">Fremd</span><span class="sxs-lookup"><span data-stu-id="ade2b-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ade2b-308">Typ der Video Codecs, die vom Absender verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ade2b-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="ade2b-309">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ade2b-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ade2b-310">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-312">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-313">Vom Absender verwendete Auflösungsbreite.</span><span class="sxs-lookup"><span data-stu-id="ade2b-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="ade2b-314">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-316">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-317">Vom Absender verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="ade2b-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="ade2b-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-320">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-321">Durchschnittliche Übertragungsrate für Videoframes, die vom Absender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ade2b-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="ade2b-322">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-324">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-325">Maximale Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="ade2b-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="ade2b-326">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-328">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-329">Durchschnittliche Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="ade2b-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-331">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-332">Maximale Anzahl der vom Absender verwendeten Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="ade2b-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="ade2b-333">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-335">smallint</span><span class="sxs-lookup"><span data-stu-id="ade2b-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="ade2b-336">Fremd</span><span class="sxs-lookup"><span data-stu-id="ade2b-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ade2b-337">Vom Empfänger verwendete Video Codes.</span><span class="sxs-lookup"><span data-stu-id="ade2b-337">Video codes used by the receiver.</span></span> <span data-ttu-id="ade2b-338">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ade2b-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="ade2b-339">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-341">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-342">Auflösung Breite, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ade2b-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-343">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-345">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-346">Vom Empfänger verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="ade2b-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-347">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-349">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-350">Durchschnittliche Videobildrate, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ade2b-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-351">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-353">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-354">Maximale Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="ade2b-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-355">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-357">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-358">Durchschnittliche Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="ade2b-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-359">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-361">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-362">Maximale Anzahl von Videodatenströmen für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="ade2b-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-363">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-365">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-366">Minimale Videodatenströme für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="ade2b-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-367">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-369">int</span><span class="sxs-lookup"><span data-stu-id="ade2b-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-370">Video Modus (beispielsweise Galerie oder einzelner Datenstrom) für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="ade2b-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="ade2b-371">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-373">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-374">Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ade2b-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="ade2b-375">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-377">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-378">Prozentsatz der Zeit, die das Flag für dynamische Funktionen aktiv war.</span><span class="sxs-lookup"><span data-stu-id="ade2b-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="ade2b-379">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="ade2b-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-382">Minimale Auflösung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="ade2b-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="ade2b-383">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-385">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-386">Prozentsatz des Anrufs unterhalb des Schwellenwerts mit niedriger Bitrate (70 Kbit/s).</span><span class="sxs-lookup"><span data-stu-id="ade2b-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="ade2b-387">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-389">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-390">Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Frameraten (7,5 Frames pro Sekunde, eingehend).</span><span class="sxs-lookup"><span data-stu-id="ade2b-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="ade2b-391">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-393">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-394">Prozentsatz des Anrufs, der bei der niedrigsten Auflösung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ade2b-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="ade2b-395">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="ade2b-396">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade2b-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-398">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ade2b-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-399">Die Dauer des Anrufs in Sekunden.</span><span class="sxs-lookup"><span data-stu-id="ade2b-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="ade2b-400">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade2b-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="ade2b-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="ade2b-402">Bit</span><span class="sxs-lookup"><span data-stu-id="ade2b-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ade2b-403">Gibt an, ob die Daten aus mehreren Aufrufen aggregiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ade2b-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="ade2b-404">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ade2b-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

