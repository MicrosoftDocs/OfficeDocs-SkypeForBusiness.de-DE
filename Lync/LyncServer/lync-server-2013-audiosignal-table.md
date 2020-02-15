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
ms.openlocfilehash: 9d7dcf9337dceded96679411e575abc888164618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="eedae-102">AudioSignal-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eedae-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eedae-103">_**Letztes Änderungsstand des Themas:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="eedae-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="eedae-104">Jeder Datensatz stellt Audiosignal-Metriken für einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="eedae-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="eedae-105">Normalerweise hat jeder Anruf zwei Datensätze, einer ist für den Anrufer und einer für den angerufenen.</span><span class="sxs-lookup"><span data-stu-id="eedae-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eedae-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eedae-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eedae-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eedae-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eedae-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="eedae-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="eedae-112">Primary</span><span class="sxs-lookup"><span data-stu-id="eedae-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="eedae-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="eedae-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-115">int</span><span class="sxs-lookup"><span data-stu-id="eedae-115">int</span></span></p></td>
<td><p><span data-ttu-id="eedae-116">Primary</span><span class="sxs-lookup"><span data-stu-id="eedae-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="eedae-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="eedae-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="eedae-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eedae-120">Primary</span><span class="sxs-lookup"><span data-stu-id="eedae-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="eedae-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="eedae-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-123">Bit</span><span class="sxs-lookup"><span data-stu-id="eedae-123">bit</span></span></p></td>
<td><p><span data-ttu-id="eedae-124">Primary</span><span class="sxs-lookup"><span data-stu-id="eedae-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="eedae-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="eedae-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="eedae-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="eedae-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-128">int</span><span class="sxs-lookup"><span data-stu-id="eedae-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-129">Stellt den Audio-Signalpegel nach dem analogen Gain-Regler dar.</span><span class="sxs-lookup"><span data-stu-id="eedae-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="eedae-130">Die Einheit für diese Metrik ist dBmo.</span><span class="sxs-lookup"><span data-stu-id="eedae-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="eedae-131">Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eedae-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="eedae-132">Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="eedae-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-134">int</span><span class="sxs-lookup"><span data-stu-id="eedae-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-135">Siehe SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="eedae-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-137">int</span><span class="sxs-lookup"><span data-stu-id="eedae-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-138">Stellt den audiorausch Pegel nach dem analogen Gain-Regler dar.</span><span class="sxs-lookup"><span data-stu-id="eedae-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="eedae-139">Die Einheit für diese Metrik ist dBmo.</span><span class="sxs-lookup"><span data-stu-id="eedae-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="eedae-140">Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen.</span><span class="sxs-lookup"><span data-stu-id="eedae-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="eedae-141">Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="eedae-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-143">int</span><span class="sxs-lookup"><span data-stu-id="eedae-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-144">Siehe SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="eedae-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-146">int</span><span class="sxs-lookup"><span data-stu-id="eedae-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-147">Metrik zur Verbesserung der Echo-Rückgabe Verlust.</span><span class="sxs-lookup"><span data-stu-id="eedae-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="eedae-148">Die Einheit für diese Metrik ist dB.</span><span class="sxs-lookup"><span data-stu-id="eedae-148">The unit for this metric is dB.</span></span> <span data-ttu-id="eedae-149">Niedrigere Werte bedeuten weniger Echo.</span><span class="sxs-lookup"><span data-stu-id="eedae-149">Lower values represent less echo.</span></span> <span data-ttu-id="eedae-150">Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="eedae-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-152">int</span><span class="sxs-lookup"><span data-stu-id="eedae-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-153">Durchschnittliche Störschübe pro fünf Minuten für das Lautsprecher Rendering.</span><span class="sxs-lookup"><span data-stu-id="eedae-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="eedae-154">Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten.</span><span class="sxs-lookup"><span data-stu-id="eedae-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="eedae-155">Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="eedae-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-157">int</span><span class="sxs-lookup"><span data-stu-id="eedae-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-158">Durchschnittliche Störschübe pro fünf Minuten für die Mikrofon Erfassung.</span><span class="sxs-lookup"><span data-stu-id="eedae-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="eedae-159">Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten.</span><span class="sxs-lookup"><span data-stu-id="eedae-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="eedae-160">Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="eedae-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-162">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="eedae-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-163">Clock Drift Rate des Mikrofon Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="eedae-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-165">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="eedae-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-166">Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="eedae-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-168">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="eedae-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-169">Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="eedae-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="eedae-170">Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="eedae-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-172">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="eedae-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-173">Durchschnittlicher Zeitstempel Fehler des Lautsprecher Rendering-Streams in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="eedae-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-175">smallint</span><span class="sxs-lookup"><span data-stu-id="eedae-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-176">Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="eedae-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="eedae-177">Ursachen des Sprachumschalter Eintrags:</span><span class="sxs-lookup"><span data-stu-id="eedae-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="eedae-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="eedae-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="eedae-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="eedae-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="eedae-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="eedae-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="eedae-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="eedae-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="eedae-182">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="eedae-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="eedae-183">ENTER_VS_FORCEORCONVERGENCE kann nur für Testzwecke von RegKey aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="eedae-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="eedae-184">Der Datentyp für diese Spalte wurde in Microsoft lync Server 2013 geändert.</span><span class="sxs-lookup"><span data-stu-id="eedae-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="eedae-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-187">Ursachen für ein Echo-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="eedae-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="eedae-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="eedae-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="eedae-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="eedae-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="eedae-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="eedae-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="eedae-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="eedae-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="eedae-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="eedae-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="eedae-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="eedae-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="eedae-194">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="eedae-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-196">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eedae-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-197">Prozentsatz der Zeit, als Echo im Mikrofon Erfassungsdaten Strom erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="eedae-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="eedae-198">Normalerweise sind die Werte für Headsets oder Mobiltelefone niedrig und für Lautsprecher Telefone oder eigenständige Lautsprecher höher.</span><span class="sxs-lookup"><span data-stu-id="eedae-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="eedae-199">Bei Geräten, die die akustische Echounterdrückung auf dem Mainboard unterstützen, deuten hohe Werte auf Echo Lecks hin.</span><span class="sxs-lookup"><span data-stu-id="eedae-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="eedae-200">Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="eedae-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-202">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eedae-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-203">Prozentsatz der Zeit, in der ECHO im gesendeten Stream erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="eedae-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="eedae-204">Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</span><span class="sxs-lookup"><span data-stu-id="eedae-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-206">int</span><span class="sxs-lookup"><span data-stu-id="eedae-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-207">Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway; Dies gilt nur für die Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="eedae-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="eedae-208">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="eedae-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="eedae-209">Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="eedae-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-211">int</span><span class="sxs-lookup"><span data-stu-id="eedae-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-212">Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway.</span><span class="sxs-lookup"><span data-stu-id="eedae-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="eedae-213">Dies betrifft nur den Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="eedae-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="eedae-214">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="eedae-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="eedae-215">Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="eedae-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-217">int</span><span class="sxs-lookup"><span data-stu-id="eedae-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-218">Automatische Gain-Steuerung (AGC) auf der Vermittlungsserver Seite.</span><span class="sxs-lookup"><span data-stu-id="eedae-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-220">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="eedae-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eedae-221">Das Hauptmittel Quadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="eedae-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-223">int</span><span class="sxs-lookup"><span data-stu-id="eedae-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-224">Signal Pegel, wie er auf Kanal 1 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="eedae-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="eedae-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-227">int</span><span class="sxs-lookup"><span data-stu-id="eedae-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-228">Signal Pegel, wie er auf Kanal 2 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="eedae-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="eedae-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-231">int</span><span class="sxs-lookup"><span data-stu-id="eedae-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-232">Auf Kanal 1 empfangenes Rauschniveau.</span><span class="sxs-lookup"><span data-stu-id="eedae-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="eedae-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-235">int</span><span class="sxs-lookup"><span data-stu-id="eedae-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-236">Auf Kanal 2 empfangenes Rauschniveau.</span><span class="sxs-lookup"><span data-stu-id="eedae-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="eedae-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-239">int</span><span class="sxs-lookup"><span data-stu-id="eedae-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-240">Signal Pegel, der auf Kanal 1 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="eedae-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="eedae-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-243">int</span><span class="sxs-lookup"><span data-stu-id="eedae-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-244">Signal Pegel, der auf Kanal 2 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="eedae-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="eedae-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedae-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-247">int</span><span class="sxs-lookup"><span data-stu-id="eedae-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-248">Auf Kanal 1 gesendeter Geräuschpegel.</span><span class="sxs-lookup"><span data-stu-id="eedae-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="eedae-249">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedae-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="eedae-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="eedae-251">int</span><span class="sxs-lookup"><span data-stu-id="eedae-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedae-252">Auf Kanal 2 gesendeter Geräuschpegel.</span><span class="sxs-lookup"><span data-stu-id="eedae-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="eedae-253">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eedae-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

