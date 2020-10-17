---
title: 'Lync Server 2013: Videostream-Tabelle'
description: 'Lync Server 2013: Videostream-Tabelle.'
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567991"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="66e36-103">Videostream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66e36-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66e36-104">_**Letztes Änderungsstand des Themas:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="66e36-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="66e36-105">Jeder Datensatz stellt einen Videodatenstrom dar.</span><span class="sxs-lookup"><span data-stu-id="66e36-105">Each record represents one video stream.</span></span> <span data-ttu-id="66e36-106">Eine Video Medien Verbindung enthält normalerweise zwei Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="66e36-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66e36-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="66e36-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="66e36-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="66e36-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66e36-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="66e36-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="66e36-113">Primary</span><span class="sxs-lookup"><span data-stu-id="66e36-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="66e36-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="66e36-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-116">int</span><span class="sxs-lookup"><span data-stu-id="66e36-116">int</span></span></p></td>
<td><p><span data-ttu-id="66e36-117">Primary</span><span class="sxs-lookup"><span data-stu-id="66e36-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="66e36-118">R, die von der <a href="lync-server-2013-medialine-table.md">medialinie-Tabelle in lync Server 2013</a>referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="66e36-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="66e36-121">Primary</span><span class="sxs-lookup"><span data-stu-id="66e36-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="66e36-122"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="66e36-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-123"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-124">int</span><span class="sxs-lookup"><span data-stu-id="66e36-124">int</span></span></p></td>
<td><p><span data-ttu-id="66e36-125">Primary</span><span class="sxs-lookup"><span data-stu-id="66e36-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="66e36-126">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="66e36-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-128">smallint</span><span class="sxs-lookup"><span data-stu-id="66e36-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="66e36-129">Foreign, Primary</span><span class="sxs-lookup"><span data-stu-id="66e36-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="66e36-130">Beschreibung der Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="66e36-130">Payload description.</span></span> <span data-ttu-id="66e36-131">Weitere Informationen finden Sie <a href="lync-server-2013-payloaddescription-table.md">in der PayloadDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e36-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-133">int</span><span class="sxs-lookup"><span data-stu-id="66e36-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-134">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="66e36-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-136">int</span><span class="sxs-lookup"><span data-stu-id="66e36-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-137">Maximale Netzwerk Jitter während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="66e36-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-138"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-139">int</span><span class="sxs-lookup"><span data-stu-id="66e36-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-140">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="66e36-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-142">int</span><span class="sxs-lookup"><span data-stu-id="66e36-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-143">Maximale Zeit für Roundtrips für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="66e36-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-145">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="66e36-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-146">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="66e36-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-148">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="66e36-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-149">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="66e36-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-151">int</span><span class="sxs-lookup"><span data-stu-id="66e36-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-152">Paketwert für den Videostream (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="66e36-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-153"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-154">int</span><span class="sxs-lookup"><span data-stu-id="66e36-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-155">Schätzungen der Bandbreite für den Videostream.</span><span class="sxs-lookup"><span data-stu-id="66e36-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-157">char (9)</span><span class="sxs-lookup"><span data-stu-id="66e36-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-p103">Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="66e36-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-161">int</span><span class="sxs-lookup"><span data-stu-id="66e36-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-162">Durchschnittliche Bitrate des Videostreams.</span><span class="sxs-lookup"><span data-stu-id="66e36-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-164">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66e36-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-165">Die empfangene Videoframerate.</span><span class="sxs-lookup"><span data-stu-id="66e36-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-167">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66e36-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-168">Die gesendete Videobildrate.</span><span class="sxs-lookup"><span data-stu-id="66e36-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-170">int</span><span class="sxs-lookup"><span data-stu-id="66e36-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-171">Die maximale Video Bitrate während der Videositzung.</span><span class="sxs-lookup"><span data-stu-id="66e36-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-173">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66e36-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-174">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="66e36-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-176">Bit</span><span class="sxs-lookup"><span data-stu-id="66e36-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-177">Nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="66e36-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-179">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66e36-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-180">Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="66e36-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-183">Der Prozentsatz des Anrufs, bei dem es sich um die CIF-Auflösung (Common Interchange Format) handelte.</span><span class="sxs-lookup"><span data-stu-id="66e36-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-186">Der Prozentsatz des Anrufs, bei dem es sich um eine VGA-Auflösung handelt.</span><span class="sxs-lookup"><span data-stu-id="66e36-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-189">Der Prozentsatz des Anrufs, bei dem die HD720-Auflösung stattfand.</span><span class="sxs-lookup"><span data-stu-id="66e36-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-192">Prozentsatz der Anrufdauer ohne Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="66e36-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-195">Prozentsatz der Anrufdauer mit B-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="66e36-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-198">Prozentsatz der Anrufdauer mit dem BP-Frame-Drop.</span><span class="sxs-lookup"><span data-stu-id="66e36-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-201">Prozentsatz der Anrufdauer mit BPSP Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="66e36-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="66e36-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-204">Prozentsatz der Anrufdauer mit BPSPI Frame Drop.</span><span class="sxs-lookup"><span data-stu-id="66e36-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-205"><strong>Eingehende</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-206">Bit</span><span class="sxs-lookup"><span data-stu-id="66e36-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-207">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="66e36-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-208"><strong>Ausgehende</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-209">Bit</span><span class="sxs-lookup"><span data-stu-id="66e36-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-210">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="66e36-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-212">Bit</span><span class="sxs-lookup"><span data-stu-id="66e36-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66e36-213">1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</span><span class="sxs-lookup"><span data-stu-id="66e36-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="66e36-214">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="66e36-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-216">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-217">Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="66e36-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="66e36-218">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-220">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-221">Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="66e36-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="66e36-222">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-224">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-225">Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</span><span class="sxs-lookup"><span data-stu-id="66e36-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="66e36-226">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-228">int</span><span class="sxs-lookup"><span data-stu-id="66e36-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-229">Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="66e36-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66e36-230">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-232">int</span><span class="sxs-lookup"><span data-stu-id="66e36-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-233">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="66e36-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66e36-234">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-236">int</span><span class="sxs-lookup"><span data-stu-id="66e36-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-237">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="66e36-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66e36-238">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-240">int</span><span class="sxs-lookup"><span data-stu-id="66e36-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-241">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="66e36-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="66e36-242">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-244">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-245">Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung keine MultiView-Videounterstützung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66e36-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="66e36-246">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-248">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p104">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-251">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-253">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p105">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-256">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-258">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p106">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-261">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-263">int</span><span class="sxs-lookup"><span data-stu-id="66e36-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p107">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-267">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-269">int</span><span class="sxs-lookup"><span data-stu-id="66e36-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p108">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-273">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-275">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p109">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-279">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-281">int</span><span class="sxs-lookup"><span data-stu-id="66e36-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p110">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-285">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-287">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p111">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-291">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-293">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-p112">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="66e36-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="66e36-297">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-299">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="66e36-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-300">Videpaketverlustrate.</span><span class="sxs-lookup"><span data-stu-id="66e36-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="66e36-301">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-303">int</span><span class="sxs-lookup"><span data-stu-id="66e36-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-304">Durchschnittliche für Video reservierte Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="66e36-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="66e36-305">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-307">smallint</span><span class="sxs-lookup"><span data-stu-id="66e36-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="66e36-308">Fremd</span><span class="sxs-lookup"><span data-stu-id="66e36-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66e36-309">Typ der Video Codecs, die vom Absender verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66e36-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="66e36-310">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e36-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="66e36-311">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-313">int</span><span class="sxs-lookup"><span data-stu-id="66e36-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-314">Vom Absender verwendete Auflösungsbreite.</span><span class="sxs-lookup"><span data-stu-id="66e36-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="66e36-315">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-317">int</span><span class="sxs-lookup"><span data-stu-id="66e36-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-318">Vom Absender verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="66e36-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="66e36-319">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-321">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-322">Durchschnittliche Übertragungsrate für Videoframes, die vom Absender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66e36-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="66e36-323">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-325">int</span><span class="sxs-lookup"><span data-stu-id="66e36-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-326">Maximale Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="66e36-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="66e36-327">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-329">int</span><span class="sxs-lookup"><span data-stu-id="66e36-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-330">Durchschnittliche Bitrate für den Absender.</span><span class="sxs-lookup"><span data-stu-id="66e36-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-332">int</span><span class="sxs-lookup"><span data-stu-id="66e36-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-333">Maximale Anzahl der vom Absender verwendeten Videodatenströme.</span><span class="sxs-lookup"><span data-stu-id="66e36-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="66e36-334">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-336">smallint</span><span class="sxs-lookup"><span data-stu-id="66e36-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="66e36-337">Fremd</span><span class="sxs-lookup"><span data-stu-id="66e36-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66e36-338">Vom Empfänger verwendete Video Codes.</span><span class="sxs-lookup"><span data-stu-id="66e36-338">Video codes used by the receiver.</span></span> <span data-ttu-id="66e36-339">Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="66e36-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="66e36-340">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-342">int</span><span class="sxs-lookup"><span data-stu-id="66e36-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-343">Auflösung Breite, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66e36-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="66e36-344">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-346">int</span><span class="sxs-lookup"><span data-stu-id="66e36-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-347">Vom Empfänger verwendete auflösungshöhe.</span><span class="sxs-lookup"><span data-stu-id="66e36-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="66e36-348">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-350">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-351">Durchschnittliche Videobildrate, die vom Empfänger verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66e36-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="66e36-352">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-354">int</span><span class="sxs-lookup"><span data-stu-id="66e36-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-355">Maximale Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="66e36-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="66e36-356">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-358">int</span><span class="sxs-lookup"><span data-stu-id="66e36-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-359">Durchschnittliche Bitrate für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="66e36-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="66e36-360">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-362">int</span><span class="sxs-lookup"><span data-stu-id="66e36-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-363">Maximale Anzahl von Videodatenströmen für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="66e36-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="66e36-364">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-366">int</span><span class="sxs-lookup"><span data-stu-id="66e36-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-367">Minimale Videodatenströme für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="66e36-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="66e36-368">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-370">int</span><span class="sxs-lookup"><span data-stu-id="66e36-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-371">Video Modus (beispielsweise Galerie oder einzelner Datenstrom) für den Empfänger.</span><span class="sxs-lookup"><span data-stu-id="66e36-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="66e36-372">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-374">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-375">Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="66e36-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="66e36-376">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-378">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-379">Prozentsatz der Zeit, die das Flag für dynamische Funktionen aktiv war.</span><span class="sxs-lookup"><span data-stu-id="66e36-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="66e36-380">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-382">char (9)</span><span class="sxs-lookup"><span data-stu-id="66e36-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-383">Minimale Auflösung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="66e36-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="66e36-384">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-386">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-387">Prozentsatz des Anrufs unterhalb des Schwellenwerts mit niedriger Bitrate (70 Kbit/s).</span><span class="sxs-lookup"><span data-stu-id="66e36-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="66e36-388">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-390">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-391">Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Frameraten (7,5 Frames pro Sekunde, eingehend).</span><span class="sxs-lookup"><span data-stu-id="66e36-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="66e36-392">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-394">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-395">Prozentsatz des Anrufs, der bei der niedrigsten Auflösung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="66e36-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="66e36-396">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="66e36-397">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66e36-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-399">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="66e36-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-400">Die Dauer des Anrufs in Sekunden.</span><span class="sxs-lookup"><span data-stu-id="66e36-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="66e36-401">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66e36-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="66e36-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="66e36-403">Bit</span><span class="sxs-lookup"><span data-stu-id="66e36-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66e36-404">Gibt an, ob die Daten aus mehreren Aufrufen aggregiert wurden.</span><span class="sxs-lookup"><span data-stu-id="66e36-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="66e36-405">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="66e36-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

