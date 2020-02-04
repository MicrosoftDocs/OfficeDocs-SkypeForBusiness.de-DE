---
title: 'Lync Server 2013: AudioStream-Tabelle'
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="71fb5-102">AudioStream-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71fb5-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71fb5-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="71fb5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="71fb5-104">Jeder Datensatz steht für einen Audiostream.</span><span class="sxs-lookup"><span data-stu-id="71fb5-104">Each record represents one audio stream.</span></span> <span data-ttu-id="71fb5-105">Eine Audio-Media-Zeile enthält in der Regel zwei Audiostreams.</span><span class="sxs-lookup"><span data-stu-id="71fb5-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71fb5-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="71fb5-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="71fb5-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="71fb5-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="71fb5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="71fb5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="71fb5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="71fb5-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="71fb5-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-115">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-115">int</span></span></p></td>
<td><p><span data-ttu-id="71fb5-116">Primary</span><span class="sxs-lookup"><span data-stu-id="71fb5-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="71fb5-117">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="71fb5-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="71fb5-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71fb5-120">Primary</span><span class="sxs-lookup"><span data-stu-id="71fb5-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="71fb5-121">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="71fb5-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-122"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-123">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-123">int</span></span></p></td>
<td><p><span data-ttu-id="71fb5-124">Primary</span><span class="sxs-lookup"><span data-stu-id="71fb5-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="71fb5-125">Eindeutige ID innerhalb einer medienzeile</span><span class="sxs-lookup"><span data-stu-id="71fb5-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-127">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-128">Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="71fb5-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-130">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-131">Maximaler Netzwerk Jitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-133">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="71fb5-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-134">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-136">Dezimal (5; 4)</span><span class="sxs-lookup"><span data-stu-id="71fb5-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-137">Maximaler Paketverlust während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-139">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="71fb5-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-140">Durchschnittliche Dichte des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-142">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-143">Durchschnittliche Dauer des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-145">Dezimal (9; 4)</span><span class="sxs-lookup"><span data-stu-id="71fb5-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-146">Durchschnittliche Dichte des Paketverlusts bei Lücken zwischen Bursts des Paketverlusts.</span><span class="sxs-lookup"><span data-stu-id="71fb5-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-148">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-149">Durchschnittliche Dauer von Lücken zwischen Bursts des Paketverlusts.</span><span class="sxs-lookup"><span data-stu-id="71fb5-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-151">Int</span><span class="sxs-lookup"><span data-stu-id="71fb5-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-152">Die Anzahl der Pakete für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="71fb5-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-153"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-154">Int</span><span class="sxs-lookup"><span data-stu-id="71fb5-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-155">Bandbreiten Schätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="71fb5-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-157">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-158">Netzwerk-Mos-Verschlechterung für den gesamten Anruf.</span><span class="sxs-lookup"><span data-stu-id="71fb5-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="71fb5-159">Der Bereich ist 0,0 bis 5,0.</span><span class="sxs-lookup"><span data-stu-id="71fb5-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="71fb5-160">Diese Metrik zeigt die Menge, die das Netzwerk Mos aufgrund von Jitter und Paketverlust reduziert wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="71fb5-161">Für akzeptable Qualität sollte es weniger als 0,5.</span><span class="sxs-lookup"><span data-stu-id="71fb5-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-163">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-164">Maximaler Netzwerk-Mos-Abbau während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-166">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-167">Netzwerk-Mos-Beeinträchtigung durch Jitter.</span><span class="sxs-lookup"><span data-stu-id="71fb5-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-169">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-170">Netzwerk-Mos-Beeinträchtigung durch Paketverlust.</span><span class="sxs-lookup"><span data-stu-id="71fb5-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-172">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-172">int</span></span></p></td>
<td><p><span data-ttu-id="71fb5-173">Fremd</span><span class="sxs-lookup"><span data-stu-id="71fb5-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71fb5-174">Der für den Anruf verwendete Audiocodec, auf den von der PayloadDescription-Tabelle verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="71fb5-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-176">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-177">Abtastrate für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="71fb5-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-179">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-180">Roundtrip-Zeit von RTCP-Statistiken</span><span class="sxs-lookup"><span data-stu-id="71fb5-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="71fb5-181">Bei akzeptabler Qualität sollte dies weniger als 100M betragen.</span><span class="sxs-lookup"><span data-stu-id="71fb5-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-183">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-184">Maximale Roundtrip-Zeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="71fb5-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-186">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-187">Durchschnittliche Breitband-Netzwerk-Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="71fb5-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="71fb5-188">Diese Metrik hängt vom verwendeten Paketverlust, Jitter und Codec ab.</span><span class="sxs-lookup"><span data-stu-id="71fb5-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="71fb5-189">Bereich ist [1,0 bis 5,0].</span><span class="sxs-lookup"><span data-stu-id="71fb5-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-191">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-192">Das Mindest-Breitband-Netzwerk Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="71fb5-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-194">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-195">Der durchschnittliche prognostizierte Breitband-Abhör-Mos-Score für gesendete Audiodaten, einschließlich der Eigenschaften für Sprachpegel, Geräuschpegel und Aufnahmegeräte.</span><span class="sxs-lookup"><span data-stu-id="71fb5-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-197">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-198">Die Mindest-SendListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="71fb5-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-200">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-201">Der durchschnittliche prognostizierte Breitband-Abhör-Mos-Score für vom Netzwerk empfangene Audiosignale, einschließlich Sprachpegel, Geräuschpegel, Codec, Netzwerkbedingungen und Merkmale des Aufnahmegeräts.</span><span class="sxs-lookup"><span data-stu-id="71fb5-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-203">Dezimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-204">Die Mindest-RecvListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="71fb5-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-206">bit</span><span class="sxs-lookup"><span data-stu-id="71fb5-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-207">Flag, das angibt, ob Audio FEC für den Anruf verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-209">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-210">Durchschnittliches Verhältnis der verborgenen Samples, die von der audioheilung an typische Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="71fb5-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-212">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-213">Durchschnittliches Verhältnis von gedehnten Samples, die von der audioheilung zu typischen Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="71fb5-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-215">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="71fb5-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-216">Durchschnittliches Verhältnis von komprimierten Samples, die von der audioheilung zu typischen Samples generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="71fb5-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-217"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-218">bit</span><span class="sxs-lookup"><span data-stu-id="71fb5-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-219">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="71fb5-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-220"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-221">bit</span><span class="sxs-lookup"><span data-stu-id="71fb5-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-222">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="71fb5-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-224">bit</span><span class="sxs-lookup"><span data-stu-id="71fb5-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71fb5-225">1 bedeutet, dass die Datenstrom Richtung vom Aufrufer an den aufgerufenen gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="71fb5-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="71fb5-226">0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</span><span class="sxs-lookup"><span data-stu-id="71fb5-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-228">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-229">Standard Abweichung für Jitter-Ankunftszeiten.</span><span class="sxs-lookup"><span data-stu-id="71fb5-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="71fb5-230">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-232">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-233">Maximales Verhältnis von Paketen, die vom Heiler verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="71fb5-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="71fb5-234">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-236">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-237">Standard Abweichung für das Verhältnis von Paketen, die vom Heiler verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="71fb5-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="71fb5-238">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-240">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-241">Das Verhältnis der vom Heiler abgegebenen Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.</span><span class="sxs-lookup"><span data-stu-id="71fb5-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="71fb5-242">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-244">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-245">Verhältnis der verwendeten Forward-Fehlerkorrektur Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.</span><span class="sxs-lookup"><span data-stu-id="71fb5-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="71fb5-246">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-248">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-249">Die maximale Anzahl von Audiopaketen, die vom Heiler komprimiert wurden.</span><span class="sxs-lookup"><span data-stu-id="71fb5-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="71fb5-250">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-252">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-253">Gibt den Prozentsatz der Zeit an, zu der sich der Anruf in einem Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="71fb5-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="71fb5-254">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-256">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-257">Gibt den Prozentsatz des Anrufs an, während dessen Überlastung durch das verspätete Eintreffen von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="71fb5-258">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-260">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-261">Gibt den Prozentsatz der Zeit an, zu der der Anruf im Wettbewerb um Netzwerkressourcen erfolgte.</span><span class="sxs-lookup"><span data-stu-id="71fb5-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="71fb5-262">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-264">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-265">Minimaler Grad der Bandbreitenschätzung, gemessen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="71fb5-266">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-268">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-269">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="71fb5-270">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-272">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-273">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="71fb5-274">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-276">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-277">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="71fb5-278">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-280">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-281">Gesamtzahl der unidirektionalen Latenzzeit.</span><span class="sxs-lookup"><span data-stu-id="71fb5-281">Total amount of one-way latency.</span></span> <span data-ttu-id="71fb5-282">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-283">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-285">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-286">Durchschnittliche Anzahl der unidirektionalen Latenzzeit.</span><span class="sxs-lookup"><span data-stu-id="71fb5-286">Average amount of one-way latency.</span></span> <span data-ttu-id="71fb5-287">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-288">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-290">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-291">Maximale Anzahl von unidirektionalen Latenzzeiten.</span><span class="sxs-lookup"><span data-stu-id="71fb5-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="71fb5-292">Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-293">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-295">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-296">Gesamtzahl der einseitigen Burst-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="71fb5-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="71fb5-297">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="71fb5-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="71fb5-298">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-299">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-301">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-302">Totale unidirektionale Burst Dichte.</span><span class="sxs-lookup"><span data-stu-id="71fb5-302">Total one-way burst density.</span></span> <span data-ttu-id="71fb5-303">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="71fb5-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="71fb5-304">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-305">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-307">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-308">Gesamtdauer des einseitigen Bursts.</span><span class="sxs-lookup"><span data-stu-id="71fb5-308">Total one-way burst duration.</span></span> <span data-ttu-id="71fb5-309">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen.</span><span class="sxs-lookup"><span data-stu-id="71fb5-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="71fb5-310">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-311">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-313">int</span><span class="sxs-lookup"><span data-stu-id="71fb5-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-314">Gesamtanzahl der einseitigen Lücken.</span><span class="sxs-lookup"><span data-stu-id="71fb5-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="71fb5-315">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="71fb5-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="71fb5-316">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-317">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-319">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-320">Gesamtdichte für einseitigen Abstand.</span><span class="sxs-lookup"><span data-stu-id="71fb5-320">Total one-way gap density.</span></span> <span data-ttu-id="71fb5-321">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="71fb5-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="71fb5-322">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-323">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-325">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-326">Gesamtdauer der einseitigen Lücke</span><span class="sxs-lookup"><span data-stu-id="71fb5-326">Total one-way gap duration.</span></span> <span data-ttu-id="71fb5-327">Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin.</span><span class="sxs-lookup"><span data-stu-id="71fb5-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="71fb5-328">Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="71fb5-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="71fb5-329">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-331">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-332">Prozentsatz des Anrufs, der als Stereo decodiert wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="71fb5-333">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-335">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-336">Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="71fb5-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="71fb5-337">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-339">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-340">Die Paketverlustrate, nachdem die weiter Leitungsfehler Korrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="71fb5-341">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71fb5-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-343">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-344">Prozentsatz des als Stereo codierten Anrufs.</span><span class="sxs-lookup"><span data-stu-id="71fb5-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="71fb5-345">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71fb5-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="71fb5-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="71fb5-347">float</span><span class="sxs-lookup"><span data-stu-id="71fb5-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71fb5-348">Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo aufgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="71fb5-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="71fb5-349">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="71fb5-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

