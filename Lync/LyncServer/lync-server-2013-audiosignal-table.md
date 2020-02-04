---
title: 'Lync Server 2013: AudioSignal-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="3e62a-102">AudioSignal-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e62a-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e62a-103">_**Letztes Änderungsdatum des Themas:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="3e62a-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="3e62a-104">Jeder Datensatz stellt die Metriken des Audiosignals für einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="3e62a-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="3e62a-105">In der Regel hat jeder Anruf zwei Datensätze, einer für den Anrufer und einer für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="3e62a-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e62a-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3e62a-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3e62a-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3e62a-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="3e62a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3e62a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="3e62a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3e62a-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3e62a-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-115">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-115">int</span></span></p></td>
<td><p><span data-ttu-id="3e62a-116">Primary</span><span class="sxs-lookup"><span data-stu-id="3e62a-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="3e62a-117">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3e62a-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="3e62a-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3e62a-120">Primary</span><span class="sxs-lookup"><span data-stu-id="3e62a-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="3e62a-121">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3e62a-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-123">bit</span><span class="sxs-lookup"><span data-stu-id="3e62a-123">bit</span></span></p></td>
<td><p><span data-ttu-id="3e62a-124">Primary</span><span class="sxs-lookup"><span data-stu-id="3e62a-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="3e62a-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="3e62a-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="3e62a-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="3e62a-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-128">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-129">Stellt den Pegel des Audiosignals nach analoger Gain-Steuerung dar.</span><span class="sxs-lookup"><span data-stu-id="3e62a-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="3e62a-130">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="3e62a-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="3e62a-131">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="3e62a-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="3e62a-132">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3e62a-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-134">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-135">Siehe SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="3e62a-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-137">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-138">Stellt den Audio-Rauschpegel nach analoger Gain-Steuerung dar.</span><span class="sxs-lookup"><span data-stu-id="3e62a-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="3e62a-139">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="3e62a-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="3e62a-140">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="3e62a-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="3e62a-141">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3e62a-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-143">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-144">Siehe SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="3e62a-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-146">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-147">Verbesserungs Metrik für ECHO-Rückerstattungs Verluste.</span><span class="sxs-lookup"><span data-stu-id="3e62a-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="3e62a-148">Die Einheit für diese Metrik ist DB.</span><span class="sxs-lookup"><span data-stu-id="3e62a-148">The unit for this metric is dB.</span></span> <span data-ttu-id="3e62a-149">Niedrigere Werte stellen weniger Echo dar.</span><span class="sxs-lookup"><span data-stu-id="3e62a-149">Lower values represent less echo.</span></span> <span data-ttu-id="3e62a-150">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3e62a-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-152">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-153">Durchschnittliche Störimpulse pro fünf Minuten für die Lautsprecher-Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="3e62a-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="3e62a-154">Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="3e62a-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="3e62a-155">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3e62a-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-157">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-158">Durchschnittliche Störimpulse pro fünf Minuten für die Aufnahme des Mikrofons.</span><span class="sxs-lookup"><span data-stu-id="3e62a-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="3e62a-159">Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="3e62a-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="3e62a-160">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="3e62a-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-162">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="3e62a-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-163">Clock-Drift Rate des Mikrofon Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="3e62a-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-165">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="3e62a-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-166">Clock-Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="3e62a-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-168">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="3e62a-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-169">Clock-Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="3e62a-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="3e62a-170">Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="3e62a-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-172">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="3e62a-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-173">Durchschnittlicher Render-Datenstrom-Zeitstempel Fehler in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="3e62a-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-175">smallint</span><span class="sxs-lookup"><span data-stu-id="3e62a-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-176">Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit.</span><span class="sxs-lookup"><span data-stu-id="3e62a-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="3e62a-177">Ursachen für den Sprachwechsel Eintrag:</span><span class="sxs-lookup"><span data-stu-id="3e62a-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="3e62a-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="3e62a-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="3e62a-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="3e62a-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="3e62a-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="3e62a-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="3e62a-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="3e62a-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="3e62a-182">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="3e62a-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="3e62a-183">ENTER_VS_FORCEORCONVERGENCE können nur von der Registrierungsschlüssel für Testzwecke aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3e62a-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="3e62a-184">Der Datentyp für diese Spalte wurde in Microsoft lync Server 2013 geändert.</span><span class="sxs-lookup"><span data-stu-id="3e62a-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="3e62a-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-187">Ursachen für ein Echo-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="3e62a-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="3e62a-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="3e62a-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="3e62a-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="3e62a-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="3e62a-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="3e62a-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="3e62a-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="3e62a-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="3e62a-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="3e62a-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="3e62a-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="3e62a-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="3e62a-194">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="3e62a-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-196">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="3e62a-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-p109">Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom Echo festgestellt wurde. In der Regel weisen Headsets oder Hörer niedrige Werte und Freisprechvorrichtungen oder eigenständige Lautsprecher höhere Werte auf. Bei Geräten, die eine integrierte akustische Echounterdrückung unterstützen, weisen hohe Werte auf eine Echoausbreitung hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="3e62a-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-202">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="3e62a-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-203">Prozentsatz der Zeit, zu der Echo in gesendetem Datenstrom erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="3e62a-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="3e62a-204">Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</span><span class="sxs-lookup"><span data-stu-id="3e62a-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-206">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-207">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway; Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="3e62a-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="3e62a-208">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="3e62a-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="3e62a-209">Für eine gute Qualität sollte der zulässige Bereich [-30 bis-18] dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="3e62a-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-211">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-212">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway.</span><span class="sxs-lookup"><span data-stu-id="3e62a-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="3e62a-213">Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="3e62a-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="3e62a-214">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="3e62a-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="3e62a-215">Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="3e62a-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-217">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-218">Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite.</span><span class="sxs-lookup"><span data-stu-id="3e62a-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-220">float</span><span class="sxs-lookup"><span data-stu-id="3e62a-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3e62a-221">Das Stamm mittelquadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="3e62a-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-223">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-224">Signal Pegel, wie er auf Kanal 1 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="3e62a-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-227">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-228">Signal Pegel, wie er auf Kanal 2 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="3e62a-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-231">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-232">Geräuschpegel, wie er auf Kanal 1 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="3e62a-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-235">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-236">Rauschpegel, wie er auf Kanal 2 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="3e62a-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-239">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-240">Signal Pegel, wie er auf Kanal 1 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="3e62a-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-243">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-244">Signal Pegel, wie er auf Kanal 2 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="3e62a-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e62a-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-247">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-248">Rauschpegel, wie er auf Kanal 1 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="3e62a-249">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e62a-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="3e62a-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="3e62a-251">int</span><span class="sxs-lookup"><span data-stu-id="3e62a-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e62a-252">Rauschpegel, wie er auf Kanal 2 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="3e62a-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="3e62a-253">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e62a-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

