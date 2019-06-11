---
title: 'Lync Server 2013: AudioSignal-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="e5da6-102">AudioSignal-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5da6-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5da6-103">_**Letztes Änderungsdatum des Themas:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="e5da6-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="e5da6-104">Jeder Datensatz stellt die Metriken des Audiosignals für einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="e5da6-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="e5da6-105">In der Regel hat jeder Anruf zwei Datensätze, einer für den Anrufer und einer für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="e5da6-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5da6-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e5da6-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e5da6-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e5da6-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e5da6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5da6-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e5da6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5da6-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e5da6-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-115">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-115">int</span></span></p></td>
<td><p><span data-ttu-id="e5da6-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e5da6-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5da6-117">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e5da6-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5da6-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5da6-120">Primary</span><span class="sxs-lookup"><span data-stu-id="e5da6-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5da6-121">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e5da6-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-123">bit</span><span class="sxs-lookup"><span data-stu-id="e5da6-123">bit</span></span></p></td>
<td><p><span data-ttu-id="e5da6-124">Primary</span><span class="sxs-lookup"><span data-stu-id="e5da6-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5da6-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="e5da6-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="e5da6-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="e5da6-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-128">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-129">Stellt den Pegel des Audiosignals nach analoger Gain-Steuerung dar.</span><span class="sxs-lookup"><span data-stu-id="e5da6-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="e5da6-130">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5da6-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5da6-131">Für akzeptable Qualität sollte es mindestens 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5da6-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5da6-132">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e5da6-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-134">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-135">Siehe SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="e5da6-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-137">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-138">Stellt den Audio-Rauschpegel nach analoger Gain-Steuerung dar.</span><span class="sxs-lookup"><span data-stu-id="e5da6-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="e5da6-139">Die Einheit für diese Metrik lautet dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5da6-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5da6-140">Für akzeptable Qualität sollte es weniger als 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="e5da6-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5da6-141">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e5da6-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-143">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-144">Siehe SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="e5da6-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-146">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-147">Verbesserungs Metrik für ECHO-Rückerstattungs Verluste.</span><span class="sxs-lookup"><span data-stu-id="e5da6-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="e5da6-148">Die Einheit für diese Metrik ist DB.</span><span class="sxs-lookup"><span data-stu-id="e5da6-148">The unit for this metric is dB.</span></span> <span data-ttu-id="e5da6-149">Niedrigere Werte stellen weniger Echo dar.</span><span class="sxs-lookup"><span data-stu-id="e5da6-149">Lower values represent less echo.</span></span> <span data-ttu-id="e5da6-150">Diese Metrik wird vom A/V-Konferenz Server oder von IP-Telefonen nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e5da6-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-152">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-153">Durchschnittliche Störimpulse pro fünf Minuten für die Lautsprecher-Wiedergabe.</span><span class="sxs-lookup"><span data-stu-id="e5da6-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="e5da6-154">Für eine gute Qualität sollte dies weniger als eins pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="e5da6-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e5da6-155">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e5da6-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-157">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-158">Durchschnittliche Störimpulse pro fünf Minuten für die Aufnahme des Mikrofons.</span><span class="sxs-lookup"><span data-stu-id="e5da6-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="e5da6-159">Für eine gute Qualität sollte dies weniger als eine pro fünf Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="e5da6-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e5da6-160">Nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e5da6-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-162">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="e5da6-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-163">Clock-Drift Rate des Mikrofon Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="e5da6-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-165">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="e5da6-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-166">Clock-Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="e5da6-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-168">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="e5da6-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-169">Clock-Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="e5da6-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="e5da6-170">Durchschnittlicher Zeitstempel des Mikrofon-Datenstroms in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e5da6-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-172">Dezimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="e5da6-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-173">Durchschnittlicher Render-Datenstrom-Zeitstempel Fehler in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e5da6-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-175">smallint</span><span class="sxs-lookup"><span data-stu-id="e5da6-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-176">Voice-Switch ist ein Halbduplex-Modus mit verminderter Unterbrechungs Fähigkeit.</span><span class="sxs-lookup"><span data-stu-id="e5da6-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e5da6-177">Ursachen für den Sprachwechsel Eintrag:</span><span class="sxs-lookup"><span data-stu-id="e5da6-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="e5da6-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="e5da6-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="e5da6-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e5da6-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e5da6-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="e5da6-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="e5da6-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e5da6-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e5da6-182">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="e5da6-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="e5da6-183">ENTER_VS_FORCEORCONVERGENCE kann nur von der Registrierungsschlüssel für Testzwecke aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e5da6-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="e5da6-184">Der Datentyp für diese Spalte wurde in Microsoft lync Server 2013 geändert.</span><span class="sxs-lookup"><span data-stu-id="e5da6-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5da6-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-187">Ursachen für ein Echo-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="e5da6-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="e5da6-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="e5da6-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="e5da6-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e5da6-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e5da6-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="e5da6-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="e5da6-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e5da6-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e5da6-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="e5da6-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="e5da6-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="e5da6-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="e5da6-194">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="e5da6-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-196">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e5da6-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-p109">Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom Echo festgestellt wurde. In der Regel weisen Headsets oder Hörer niedrige Werte und Freisprechvorrichtungen oder eigenständige Lautsprecher höhere Werte auf. Bei Geräten, die eine integrierte akustische Echounterdrückung unterstützen, weisen hohe Werte auf eine Echoausbreitung hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="e5da6-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-202">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="e5da6-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-203">Prozentsatz der Zeit, zu der Echo in gesendetem Datenstrom erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="e5da6-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="e5da6-204">Ein großer Prozentsatz des Echos in Send-Streams zeigt einen Hinweis auf Echo Verluste.</span><span class="sxs-lookup"><span data-stu-id="e5da6-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-206">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-207">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway; Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="e5da6-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e5da6-208">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5da6-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5da6-209">Für eine gute Qualität sollte der zulässige Bereich [-30 bis-18] dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="e5da6-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-211">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-212">Empfangene Signalstufe auf dem Vermittlungs Server vom Gateway.</span><span class="sxs-lookup"><span data-stu-id="e5da6-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="e5da6-213">Dies gilt nur für den Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="e5da6-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e5da6-214">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="e5da6-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5da6-215">Für eine gute Qualität sollte der zulässige Bereich kleiner als-50 dBoV sein.</span><span class="sxs-lookup"><span data-stu-id="e5da6-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-217">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-218">Automatische Gain-Steuerung (AGC) auf der Mediation Server-Seite.</span><span class="sxs-lookup"><span data-stu-id="e5da6-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-220">float</span><span class="sxs-lookup"><span data-stu-id="e5da6-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5da6-221">Das Stamm mittelquadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="e5da6-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-223">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-224">Signal Pegel, wie er auf Kanal 1 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e5da6-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-227">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-228">Signal Pegel, wie er auf Kanal 2 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e5da6-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-231">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-232">Geräuschpegel, wie er auf Kanal 1 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e5da6-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-235">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-236">Rauschpegel, wie er auf Kanal 2 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e5da6-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-239">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-240">Signal Pegel, wie er auf Kanal 1 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e5da6-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-243">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-244">Signal Pegel, wie er auf Kanal 2 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e5da6-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5da6-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-247">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-248">Rauschpegel, wie er auf Kanal 1 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e5da6-249">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5da6-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e5da6-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e5da6-251">int</span><span class="sxs-lookup"><span data-stu-id="e5da6-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5da6-252">Rauschpegel, wie er auf Kanal 2 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5da6-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e5da6-253">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5da6-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

