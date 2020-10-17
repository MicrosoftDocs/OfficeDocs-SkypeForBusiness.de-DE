---
title: 'Lync Server 2013: AudioStream-Tabelle'
description: 'Lync Server 2013: AudioStream-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552341"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="e7b8a-103">AudioStream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7b8a-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7b8a-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e7b8a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e7b8a-105">Jeder Datensatz stellt einen Audiostream dar.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-105">Each record represents one audio stream.</span></span> <span data-ttu-id="e7b8a-106">Eine Audio-Medien Verbindung enthält normalerweise zwei Audiostreams.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7b8a-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e7b8a-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e7b8a-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e7b8a-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e7b8a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e7b8a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-116">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-116">int</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="e7b8a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-118"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="e7b8a-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-121">Primary</span><span class="sxs-lookup"><span data-stu-id="e7b8a-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-122"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-123"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-124">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-124">int</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-125">Primary</span><span class="sxs-lookup"><span data-stu-id="e7b8a-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-126">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-128">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-129">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="e7b8a-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-131">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-132">Maximaler Netzwerkjitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-134">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-135">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-137">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-138">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-139"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-140">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-141">Durchschnittliche Dichte des Paketverlusts bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-143">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-144">Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-146">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-147">Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-149">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-150">Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-152">Int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-153">Paketwert für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-154"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-155">Int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-156">Bandbreitenschätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-158">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-p102">Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-164">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-165">Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-167">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-168">Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-170">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-171">Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-173">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-173">int</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-174">Fremd</span><span class="sxs-lookup"><span data-stu-id="e7b8a-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e7b8a-175">Der für den Anruf verwendete Audiocodec, der von der PayloadDescription-Tabelle referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-177">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-178">Samplingrate für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-179"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-180">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-181">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="e7b8a-182">Für eine akzeptable Qualität sollte dies weniger als 100M sein.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-184">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-185">Maximale Roundtripzeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-187">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-188">Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="e7b8a-189">Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="e7b8a-190">Bereich ist [1,0 zu 5,0].</span><span class="sxs-lookup"><span data-stu-id="e7b8a-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-192">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-193">Die minimale Breitband-Netzwerk-Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-195">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-196">Die durchschnittliche vorhergesagte Wideband-Abhör-Mos-Bewertung für gesendete Audiodaten, einschließlich Sprachpegel, Rauschpegel und Eigenschaften von Aufnahmegeräten.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-198">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-199">Die minimale SendListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-201">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-202">Die durchschnittliche vorhergesagte Wideband-Abhör-Mos-Bewertung für vom Netzwerk empfangene Audiodaten, einschließlich Sprachpegel, Rauschen, Codec, Netzwerkbedingungen und Eigenschaften für das Capture-Gerät.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-204">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-205">Die minimale RecvListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-207">Bit</span><span class="sxs-lookup"><span data-stu-id="e7b8a-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-208">Flag, das angibt, ob Audio FEC für den Anruf verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-210">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-211">Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-213">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-214">Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-216">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e7b8a-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-217">Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-218"><strong>Eingehende</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-219">Bit</span><span class="sxs-lookup"><span data-stu-id="e7b8a-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-220">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-221"><strong>Ausgehende</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-222">Bit</span><span class="sxs-lookup"><span data-stu-id="e7b8a-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-223">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-225">Bit</span><span class="sxs-lookup"><span data-stu-id="e7b8a-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e7b8a-226">1 bedeutet, dass die Datenstrom Richtung vom Anrufer zum angerufenen stammt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="e7b8a-227">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-229">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-230">Standard Abweichung für Jitter-Ankunftszeiten.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="e7b8a-231">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-233">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-234">Maximales Verhältnis von Paketen, die vom Heiler verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="e7b8a-235">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-237">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-238">Standard Abweichung für das Verhältnis von Paketen, die vom Heiler verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="e7b8a-239">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-241">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-242">Verhältnis der Pakete, die vom Heiler zurückgegeben wurden, mit der Gesamtzahl der empfangenen Pakete.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="e7b8a-243">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-245">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-246">Verhältnis der verwendeten Forward-Fehlerkorrektur Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="e7b8a-247">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-249">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-250">Maximale Anzahl von Audiopaketen, die von der Heiler-Datei komprimiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="e7b8a-251">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-253">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-254">Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="e7b8a-255">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-257">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-258">Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="e7b8a-259">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-261">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-262">Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="e7b8a-263">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-265">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-266">Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e7b8a-267">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-269">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-270">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e7b8a-271">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-273">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-274">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e7b8a-275">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-277">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-278">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e7b8a-279">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-281">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p105">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-284">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-286">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p106">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-289">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-291">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p107">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-294">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-296">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p108">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-300">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-302">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p109">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-306">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-308">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p110">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-312">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-314">int</span><span class="sxs-lookup"><span data-stu-id="e7b8a-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p111">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-318">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-320">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p112">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-324">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-326">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-p113">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e7b8a-330">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-332">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-333">Prozentsatz des Anrufs, der als Stereo decodiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="e7b8a-334">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-336">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-337">Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="e7b8a-338">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-340">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-341">Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="e7b8a-342">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b8a-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-344">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-345">Prozentsatz des Anrufs, der als Stereo codiert ist.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="e7b8a-346">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b8a-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e7b8a-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b8a-348">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="e7b8a-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7b8a-349">Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="e7b8a-350">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7b8a-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

