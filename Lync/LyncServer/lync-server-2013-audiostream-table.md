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
ms.openlocfilehash: 44f41dc95e1c7c39a0c9c2cc4dd0a3a2462083e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="fa690-102">AudioStream-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa690-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa690-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fa690-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fa690-104">Jeder Datensatz stellt einen Audiostream dar.</span><span class="sxs-lookup"><span data-stu-id="fa690-104">Each record represents one audio stream.</span></span> <span data-ttu-id="fa690-105">Eine Audio-Medien Verbindung enthält normalerweise zwei Audiostreams.</span><span class="sxs-lookup"><span data-stu-id="fa690-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa690-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fa690-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fa690-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fa690-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa690-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fa690-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fa690-112">Primary</span><span class="sxs-lookup"><span data-stu-id="fa690-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa690-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="fa690-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-115">int</span><span class="sxs-lookup"><span data-stu-id="fa690-115">int</span></span></p></td>
<td><p><span data-ttu-id="fa690-116">Primary</span><span class="sxs-lookup"><span data-stu-id="fa690-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa690-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="fa690-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="fa690-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fa690-120">Primary</span><span class="sxs-lookup"><span data-stu-id="fa690-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa690-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="fa690-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-122"><strong>Datenstrom-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-123">int</span><span class="sxs-lookup"><span data-stu-id="fa690-123">int</span></span></p></td>
<td><p><span data-ttu-id="fa690-124">Primary</span><span class="sxs-lookup"><span data-stu-id="fa690-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa690-125">Eindeutige ID innerhalb einer Medienzeile.</span><span class="sxs-lookup"><span data-stu-id="fa690-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-127">int</span><span class="sxs-lookup"><span data-stu-id="fa690-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-128">Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="fa690-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-130">int</span><span class="sxs-lookup"><span data-stu-id="fa690-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-131">Maximaler Netzwerkjitter während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="fa690-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-133">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fa690-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-134">Durchschnittliche Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="fa690-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-136">Decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fa690-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-137">Maximale Paketverlustrate während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="fa690-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-139">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="fa690-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-140">Durchschnittliche Dichte des Paketverlusts bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="fa690-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-142">int</span><span class="sxs-lookup"><span data-stu-id="fa690-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-143">Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="fa690-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-145">Decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="fa690-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-146">Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="fa690-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-148">int</span><span class="sxs-lookup"><span data-stu-id="fa690-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-149">Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.</span><span class="sxs-lookup"><span data-stu-id="fa690-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-151">Int</span><span class="sxs-lookup"><span data-stu-id="fa690-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-152">Paketwert für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="fa690-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-153"><strong>Bandbreite</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-154">Int</span><span class="sxs-lookup"><span data-stu-id="fa690-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-155">Bandbreitenschätzungen für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="fa690-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-157">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-p102">Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.</span><span class="sxs-lookup"><span data-stu-id="fa690-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-163">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-164">Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="fa690-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-166">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-167">Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.</span><span class="sxs-lookup"><span data-stu-id="fa690-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-169">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-170">Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.</span><span class="sxs-lookup"><span data-stu-id="fa690-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-172">int</span><span class="sxs-lookup"><span data-stu-id="fa690-172">int</span></span></p></td>
<td><p><span data-ttu-id="fa690-173">Fremd</span><span class="sxs-lookup"><span data-stu-id="fa690-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa690-174">Der für den Anruf verwendete Audiocodec, der von der PayloadDescription-Tabelle referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="fa690-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-176">int</span><span class="sxs-lookup"><span data-stu-id="fa690-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-177">Samplingrate für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="fa690-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-178"><strong>Roundtrip</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-179">int</span><span class="sxs-lookup"><span data-stu-id="fa690-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-180">Roundtripzeit aus RTCP-Statistik.</span><span class="sxs-lookup"><span data-stu-id="fa690-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="fa690-181">Für eine akzeptable Qualität sollte dies weniger als 100M sein.</span><span class="sxs-lookup"><span data-stu-id="fa690-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-183">int</span><span class="sxs-lookup"><span data-stu-id="fa690-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-184">Maximale Roundtripzeit für den Audiostream.</span><span class="sxs-lookup"><span data-stu-id="fa690-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-186">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-187">Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="fa690-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="fa690-188">Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec.</span><span class="sxs-lookup"><span data-stu-id="fa690-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="fa690-189">Bereich ist [1,0 zu 5,0].</span><span class="sxs-lookup"><span data-stu-id="fa690-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-191">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-192">Die minimale Breitband-Netzwerk-Mos für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="fa690-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-194">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-195">Die durchschnittliche vorhergesagte Wideband-Abhör-Mos-Bewertung für gesendete Audiodaten, einschließlich Sprachpegel, Rauschpegel und Eigenschaften von Aufnahmegeräten.</span><span class="sxs-lookup"><span data-stu-id="fa690-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-197">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-198">Die minimale SendListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="fa690-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-200">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-201">Die durchschnittliche vorhergesagte Wideband-Abhör-Mos-Bewertung für vom Netzwerk empfangene Audiodaten, einschließlich Sprachpegel, Rauschen, Codec, Netzwerkbedingungen und Eigenschaften für das Capture-Gerät.</span><span class="sxs-lookup"><span data-stu-id="fa690-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-203">Decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-204">Die minimale RecvListenMOS für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="fa690-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-206">Bit</span><span class="sxs-lookup"><span data-stu-id="fa690-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-207">Flag, das angibt, ob Audio FEC für den Anruf verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-209">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-210">Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="fa690-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-212">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-213">Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="fa690-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-215">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fa690-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-216">Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.</span><span class="sxs-lookup"><span data-stu-id="fa690-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-217"><strong>Eingehend</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-218">Bit</span><span class="sxs-lookup"><span data-stu-id="fa690-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-219">Datenstrom auf Empfängerseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="fa690-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-220"><strong>Ausgehend</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-221">Bit</span><span class="sxs-lookup"><span data-stu-id="fa690-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-222">Datenstrom auf Absenderseite wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="fa690-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-224">Bit</span><span class="sxs-lookup"><span data-stu-id="fa690-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fa690-225">1 bedeutet, dass die Datenstrom Richtung vom Anrufer zum angerufenen stammt.</span><span class="sxs-lookup"><span data-stu-id="fa690-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="fa690-226">0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</span><span class="sxs-lookup"><span data-stu-id="fa690-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-228">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-229">Standard Abweichung für Jitter-Ankunftszeiten.</span><span class="sxs-lookup"><span data-stu-id="fa690-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="fa690-230">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-232">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-233">Maximales Verhältnis von Paketen, die vom Heiler verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="fa690-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="fa690-234">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-236">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-237">Standard Abweichung für das Verhältnis von Paketen, die vom Heiler verborgen sind.</span><span class="sxs-lookup"><span data-stu-id="fa690-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="fa690-238">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-240">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-241">Verhältnis der Pakete, die vom Heiler zurückgegeben wurden, mit der Gesamtzahl der empfangenen Pakete.</span><span class="sxs-lookup"><span data-stu-id="fa690-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="fa690-242">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-244">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-245">Verhältnis der verwendeten Forward-Fehlerkorrektur Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.</span><span class="sxs-lookup"><span data-stu-id="fa690-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="fa690-246">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-248">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-249">Maximale Anzahl von Audiopaketen, die von der Heiler-Datei komprimiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fa690-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="fa690-250">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-252">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-253">Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</span><span class="sxs-lookup"><span data-stu-id="fa690-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="fa690-254">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-256">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-257">Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="fa690-258">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-260">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-261">Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</span><span class="sxs-lookup"><span data-stu-id="fa690-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="fa690-262">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-264">int</span><span class="sxs-lookup"><span data-stu-id="fa690-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-265">Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fa690-266">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-268">int</span><span class="sxs-lookup"><span data-stu-id="fa690-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-269">Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fa690-270">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-272">int</span><span class="sxs-lookup"><span data-stu-id="fa690-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-273">Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fa690-274">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-276">int</span><span class="sxs-lookup"><span data-stu-id="fa690-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-277">Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fa690-278">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-280">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p105">Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-283">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-285">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p106">Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-288">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-290">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p107">Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-293">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-295">int</span><span class="sxs-lookup"><span data-stu-id="fa690-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p108">Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-299">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-301">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p109">Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-305">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-307">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p110">Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-311">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-313">int</span><span class="sxs-lookup"><span data-stu-id="fa690-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p111">Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-317">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-319">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p112">Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-323">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-325">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-p113">Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</span><span class="sxs-lookup"><span data-stu-id="fa690-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fa690-329">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-331">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-332">Prozentsatz des Anrufs, der als Stereo decodiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="fa690-333">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-335">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-336">Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="fa690-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="fa690-337">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-339">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-340">Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="fa690-341">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa690-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-343">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-344">Prozentsatz des Anrufs, der als Stereo codiert ist.</span><span class="sxs-lookup"><span data-stu-id="fa690-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="fa690-345">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa690-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fa690-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fa690-347">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="fa690-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa690-348">Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="fa690-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="fa690-349">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fa690-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

