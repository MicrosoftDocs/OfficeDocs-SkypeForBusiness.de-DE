---
title: 'Lync Server 2013: AudioSignal-Tabelle'
description: 'Lync Server 2013: AudioSignal-Tabelle.'
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
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568761"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="d182a-103">AudioSignal-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d182a-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d182a-104">_**Letztes Änderungsstand des Themas:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="d182a-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="d182a-105">Jeder Datensatz stellt Audiosignal-Metriken für einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="d182a-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="d182a-106">Normalerweise hat jeder Anruf zwei Datensätze, einer ist für den Anrufer und einer für den angerufenen.</span><span class="sxs-lookup"><span data-stu-id="d182a-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d182a-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d182a-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d182a-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d182a-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d182a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d182a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d182a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d182a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d182a-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d182a-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-116">int</span><span class="sxs-lookup"><span data-stu-id="d182a-116">int</span></span></p></td>
<td><p><span data-ttu-id="d182a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d182a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d182a-118"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d182a-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d182a-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d182a-121">Primary</span><span class="sxs-lookup"><span data-stu-id="d182a-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="d182a-122"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d182a-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-124">Bit</span><span class="sxs-lookup"><span data-stu-id="d182a-124">bit</span></span></p></td>
<td><p><span data-ttu-id="d182a-125">Primary</span><span class="sxs-lookup"><span data-stu-id="d182a-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="d182a-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="d182a-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="d182a-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="d182a-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-129">int</span><span class="sxs-lookup"><span data-stu-id="d182a-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-130">Stellt den Audio-Signalpegel nach dem analogen Gain-Regler dar.</span><span class="sxs-lookup"><span data-stu-id="d182a-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="d182a-131">Die Einheit für diese Metrik ist dBmo.</span><span class="sxs-lookup"><span data-stu-id="d182a-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d182a-132">Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d182a-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="d182a-133">Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="d182a-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-135">int</span><span class="sxs-lookup"><span data-stu-id="d182a-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-136">Siehe SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="d182a-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-138">int</span><span class="sxs-lookup"><span data-stu-id="d182a-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-139">Stellt den audiorausch Pegel nach dem analogen Gain-Regler dar.</span><span class="sxs-lookup"><span data-stu-id="d182a-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="d182a-140">Die Einheit für diese Metrik ist dBmo.</span><span class="sxs-lookup"><span data-stu-id="d182a-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="d182a-141">Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen.</span><span class="sxs-lookup"><span data-stu-id="d182a-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="d182a-142">Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="d182a-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-144">int</span><span class="sxs-lookup"><span data-stu-id="d182a-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-145">Siehe SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="d182a-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-147">int</span><span class="sxs-lookup"><span data-stu-id="d182a-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-148">Metrik zur Verbesserung der Echo-Rückgabe Verlust.</span><span class="sxs-lookup"><span data-stu-id="d182a-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="d182a-149">Die Einheit für diese Metrik ist dB.</span><span class="sxs-lookup"><span data-stu-id="d182a-149">The unit for this metric is dB.</span></span> <span data-ttu-id="d182a-150">Niedrigere Werte bedeuten weniger Echo.</span><span class="sxs-lookup"><span data-stu-id="d182a-150">Lower values represent less echo.</span></span> <span data-ttu-id="d182a-151">Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="d182a-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-153">int</span><span class="sxs-lookup"><span data-stu-id="d182a-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-154">Durchschnittliche Störschübe pro fünf Minuten für das Lautsprecher Rendering.</span><span class="sxs-lookup"><span data-stu-id="d182a-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="d182a-155">Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten.</span><span class="sxs-lookup"><span data-stu-id="d182a-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="d182a-156">Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="d182a-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-158">int</span><span class="sxs-lookup"><span data-stu-id="d182a-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-159">Durchschnittliche Störschübe pro fünf Minuten für die Mikrofon Erfassung.</span><span class="sxs-lookup"><span data-stu-id="d182a-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="d182a-160">Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten.</span><span class="sxs-lookup"><span data-stu-id="d182a-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="d182a-161">Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="d182a-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-163">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d182a-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-164">Clock Drift Rate des Mikrofon Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="d182a-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-166">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d182a-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-167">Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="d182a-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-169">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d182a-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-170">Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="d182a-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="d182a-171">Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d182a-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-173">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d182a-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-174">Durchschnittlicher Zeitstempel Fehler des Lautsprecher Rendering-Streams in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d182a-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-176">smallint</span><span class="sxs-lookup"><span data-stu-id="d182a-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-177">Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="d182a-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="d182a-178">Ursachen des Sprachumschalter Eintrags:</span><span class="sxs-lookup"><span data-stu-id="d182a-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="d182a-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="d182a-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="d182a-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d182a-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d182a-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="d182a-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="d182a-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d182a-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d182a-183">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="d182a-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="d182a-184">ENTER_VS_FORCEORCONVERGENCE kann nur für Testzwecke von RegKey aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d182a-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="d182a-185">Der Datentyp für diese Spalte wurde in Microsoft lync Server 2013 geändert.</span><span class="sxs-lookup"><span data-stu-id="d182a-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="d182a-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-188">Ursachen für ein Echo-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="d182a-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="d182a-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="d182a-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="d182a-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="d182a-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="d182a-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="d182a-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="d182a-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="d182a-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="d182a-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="d182a-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="d182a-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="d182a-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="d182a-195">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="d182a-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-197">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d182a-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-198">Prozentsatz der Zeit, als Echo im Mikrofon Erfassungsdaten Strom erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="d182a-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="d182a-199">Normalerweise sind die Werte für Headsets oder Mobiltelefone niedrig und für Lautsprecher Telefone oder eigenständige Lautsprecher höher.</span><span class="sxs-lookup"><span data-stu-id="d182a-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="d182a-200">Bei Geräten, die die akustische Echounterdrückung auf dem Mainboard unterstützen, deuten hohe Werte auf Echo Lecks hin.</span><span class="sxs-lookup"><span data-stu-id="d182a-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="d182a-201">Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="d182a-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-203">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d182a-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-204">Prozentsatz der Zeit, in der ECHO im gesendeten Stream erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="d182a-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="d182a-205">Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</span><span class="sxs-lookup"><span data-stu-id="d182a-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-207">int</span><span class="sxs-lookup"><span data-stu-id="d182a-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-208">Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway; Dies gilt nur für die Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="d182a-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="d182a-209">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="d182a-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d182a-210">Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="d182a-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-212">int</span><span class="sxs-lookup"><span data-stu-id="d182a-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-213">Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway.</span><span class="sxs-lookup"><span data-stu-id="d182a-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="d182a-214">Dies betrifft nur den Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="d182a-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="d182a-215">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="d182a-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="d182a-216">Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="d182a-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-218">int</span><span class="sxs-lookup"><span data-stu-id="d182a-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-219">Automatische Gain-Steuerung (AGC) auf der Vermittlungsserver Seite.</span><span class="sxs-lookup"><span data-stu-id="d182a-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-221">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="d182a-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d182a-222">Das Hauptmittel Quadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="d182a-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-224">int</span><span class="sxs-lookup"><span data-stu-id="d182a-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-225">Signal Pegel, wie er auf Kanal 1 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d182a-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d182a-226">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-228">int</span><span class="sxs-lookup"><span data-stu-id="d182a-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-229">Signal Pegel, wie er auf Kanal 2 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d182a-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d182a-230">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-232">int</span><span class="sxs-lookup"><span data-stu-id="d182a-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-233">Auf Kanal 1 empfangenes Rauschniveau.</span><span class="sxs-lookup"><span data-stu-id="d182a-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="d182a-234">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-236">int</span><span class="sxs-lookup"><span data-stu-id="d182a-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-237">Auf Kanal 2 empfangenes Rauschniveau.</span><span class="sxs-lookup"><span data-stu-id="d182a-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="d182a-238">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-240">int</span><span class="sxs-lookup"><span data-stu-id="d182a-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-241">Signal Pegel, der auf Kanal 1 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d182a-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d182a-242">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-244">int</span><span class="sxs-lookup"><span data-stu-id="d182a-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-245">Signal Pegel, der auf Kanal 2 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d182a-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d182a-246">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d182a-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-248">int</span><span class="sxs-lookup"><span data-stu-id="d182a-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-249">Auf Kanal 1 gesendeter Geräuschpegel.</span><span class="sxs-lookup"><span data-stu-id="d182a-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="d182a-250">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d182a-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="d182a-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="d182a-252">int</span><span class="sxs-lookup"><span data-stu-id="d182a-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d182a-253">Auf Kanal 2 gesendeter Geräuschpegel.</span><span class="sxs-lookup"><span data-stu-id="d182a-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="d182a-254">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d182a-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

