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
ms.openlocfilehash: de07393ef9f43346d0c1b4c96dcfdcf33f00513a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="34a61-102">AudioSignal-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34a61-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34a61-103">_**Letztes Änderungsstand des Themas:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="34a61-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="34a61-104">Jeder Datensatz stellt Audiosignal-Metriken für einen Endpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="34a61-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="34a61-105">Normalerweise hat jeder Anruf zwei Datensätze, einer ist für den Anrufer und einer für den angerufenen.</span><span class="sxs-lookup"><span data-stu-id="34a61-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34a61-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="34a61-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="34a61-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="34a61-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34a61-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="34a61-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="34a61-112">Primary</span><span class="sxs-lookup"><span data-stu-id="34a61-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="34a61-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="34a61-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-115">int</span><span class="sxs-lookup"><span data-stu-id="34a61-115">int</span></span></p></td>
<td><p><span data-ttu-id="34a61-116">Primary</span><span class="sxs-lookup"><span data-stu-id="34a61-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="34a61-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="34a61-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="34a61-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="34a61-120">Primary</span><span class="sxs-lookup"><span data-stu-id="34a61-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="34a61-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="34a61-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-123">Bit</span><span class="sxs-lookup"><span data-stu-id="34a61-123">bit</span></span></p></td>
<td><p><span data-ttu-id="34a61-124">Primary</span><span class="sxs-lookup"><span data-stu-id="34a61-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="34a61-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="34a61-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="34a61-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="34a61-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-128">int</span><span class="sxs-lookup"><span data-stu-id="34a61-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-129">Stellt den Audio-Signalpegel nach dem analogen Gain-Regler dar.</span><span class="sxs-lookup"><span data-stu-id="34a61-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="34a61-130">Die Einheit für diese Metrik ist dBmo.</span><span class="sxs-lookup"><span data-stu-id="34a61-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="34a61-131">Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34a61-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="34a61-132">Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="34a61-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-134">int</span><span class="sxs-lookup"><span data-stu-id="34a61-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-135">Siehe SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="34a61-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-137">int</span><span class="sxs-lookup"><span data-stu-id="34a61-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-138">Stellt den audiorausch Pegel nach dem analogen Gain-Regler dar.</span><span class="sxs-lookup"><span data-stu-id="34a61-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="34a61-139">Die Einheit für diese Metrik ist dBmo.</span><span class="sxs-lookup"><span data-stu-id="34a61-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="34a61-140">Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen.</span><span class="sxs-lookup"><span data-stu-id="34a61-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="34a61-141">Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="34a61-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-143">int</span><span class="sxs-lookup"><span data-stu-id="34a61-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-144">Siehe SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="34a61-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-146">int</span><span class="sxs-lookup"><span data-stu-id="34a61-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-147">Metrik zur Verbesserung der Echo-Rückgabe Verlust.</span><span class="sxs-lookup"><span data-stu-id="34a61-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="34a61-148">Die Einheit für diese Metrik ist dB.</span><span class="sxs-lookup"><span data-stu-id="34a61-148">The unit for this metric is dB.</span></span> <span data-ttu-id="34a61-149">Niedrigere Werte bedeuten weniger Echo.</span><span class="sxs-lookup"><span data-stu-id="34a61-149">Lower values represent less echo.</span></span> <span data-ttu-id="34a61-150">Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="34a61-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-152">int</span><span class="sxs-lookup"><span data-stu-id="34a61-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-153">Durchschnittliche Störschübe pro fünf Minuten für das Lautsprecher Rendering.</span><span class="sxs-lookup"><span data-stu-id="34a61-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="34a61-154">Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten.</span><span class="sxs-lookup"><span data-stu-id="34a61-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="34a61-155">Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="34a61-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-157">int</span><span class="sxs-lookup"><span data-stu-id="34a61-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-158">Durchschnittliche Störschübe pro fünf Minuten für die Mikrofon Erfassung.</span><span class="sxs-lookup"><span data-stu-id="34a61-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="34a61-159">Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten.</span><span class="sxs-lookup"><span data-stu-id="34a61-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="34a61-160">Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</span><span class="sxs-lookup"><span data-stu-id="34a61-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-162">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="34a61-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-163">Clock Drift Rate des Mikrofon Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="34a61-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-165">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="34a61-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-166">Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="34a61-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-168">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="34a61-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-169">Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</span><span class="sxs-lookup"><span data-stu-id="34a61-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="34a61-170">Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="34a61-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-172">Decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="34a61-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-173">Durchschnittlicher Zeitstempel Fehler des Lautsprecher Rendering-Streams in Millisekunden in den letzten 20 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="34a61-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-175">smallint</span><span class="sxs-lookup"><span data-stu-id="34a61-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-176">Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="34a61-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="34a61-177">Ursachen des Sprachumschalter Eintrags:</span><span class="sxs-lookup"><span data-stu-id="34a61-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="34a61-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="34a61-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="34a61-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="34a61-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="34a61-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="34a61-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="34a61-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="34a61-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="34a61-182">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="34a61-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="34a61-183">ENTER_VS_FORCEORCONVERGENCE kann nur für Testzwecke von RegKey aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="34a61-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="34a61-184">Der Datentyp für diese Spalte wurde in Microsoft lync Server 2013 geändert.</span><span class="sxs-lookup"><span data-stu-id="34a61-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="34a61-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-187">Ursachen für ein Echo-Ereignis:</span><span class="sxs-lookup"><span data-stu-id="34a61-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="34a61-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="34a61-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="34a61-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="34a61-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="34a61-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="34a61-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="34a61-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="34a61-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="34a61-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="34a61-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="34a61-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="34a61-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="34a61-194">Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</span><span class="sxs-lookup"><span data-stu-id="34a61-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-196">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="34a61-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-197">Prozentsatz der Zeit, als Echo im Mikrofon Erfassungsdaten Strom erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="34a61-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="34a61-198">Normalerweise sind die Werte für Headsets oder Mobiltelefone niedrig und für Lautsprecher Telefone oder eigenständige Lautsprecher höher.</span><span class="sxs-lookup"><span data-stu-id="34a61-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="34a61-199">Bei Geräten, die die akustische Echounterdrückung auf dem Mainboard unterstützen, deuten hohe Werte auf Echo Lecks hin.</span><span class="sxs-lookup"><span data-stu-id="34a61-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="34a61-200">Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="34a61-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-202">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="34a61-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-203">Prozentsatz der Zeit, in der ECHO im gesendeten Stream erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="34a61-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="34a61-204">Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</span><span class="sxs-lookup"><span data-stu-id="34a61-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-206">int</span><span class="sxs-lookup"><span data-stu-id="34a61-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-207">Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway; Dies gilt nur für die Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="34a61-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="34a61-208">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="34a61-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="34a61-209">Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="34a61-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-211">int</span><span class="sxs-lookup"><span data-stu-id="34a61-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-212">Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway.</span><span class="sxs-lookup"><span data-stu-id="34a61-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="34a61-213">Dies betrifft nur den Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="34a61-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="34a61-214">Die Einheit dieser Metrik ist dBoV.</span><span class="sxs-lookup"><span data-stu-id="34a61-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="34a61-215">Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</span><span class="sxs-lookup"><span data-stu-id="34a61-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-217">int</span><span class="sxs-lookup"><span data-stu-id="34a61-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-218">Automatische Gain-Steuerung (AGC) auf der Vermittlungsserver Seite.</span><span class="sxs-lookup"><span data-stu-id="34a61-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-220">Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="34a61-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="34a61-221">Das Hauptmittel Quadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="34a61-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-223">int</span><span class="sxs-lookup"><span data-stu-id="34a61-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-224">Signal Pegel, wie er auf Kanal 1 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="34a61-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="34a61-225">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-227">int</span><span class="sxs-lookup"><span data-stu-id="34a61-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-228">Signal Pegel, wie er auf Kanal 2 empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="34a61-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="34a61-229">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-231">int</span><span class="sxs-lookup"><span data-stu-id="34a61-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-232">Auf Kanal 1 empfangenes Rauschniveau.</span><span class="sxs-lookup"><span data-stu-id="34a61-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="34a61-233">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-235">int</span><span class="sxs-lookup"><span data-stu-id="34a61-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-236">Auf Kanal 2 empfangenes Rauschniveau.</span><span class="sxs-lookup"><span data-stu-id="34a61-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="34a61-237">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-239">int</span><span class="sxs-lookup"><span data-stu-id="34a61-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-240">Signal Pegel, der auf Kanal 1 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="34a61-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="34a61-241">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-243">int</span><span class="sxs-lookup"><span data-stu-id="34a61-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-244">Signal Pegel, der auf Kanal 2 gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="34a61-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="34a61-245">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a61-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-247">int</span><span class="sxs-lookup"><span data-stu-id="34a61-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-248">Auf Kanal 1 gesendeter Geräuschpegel.</span><span class="sxs-lookup"><span data-stu-id="34a61-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="34a61-249">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a61-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="34a61-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="34a61-251">int</span><span class="sxs-lookup"><span data-stu-id="34a61-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="34a61-252">Auf Kanal 2 gesendeter Geräuschpegel.</span><span class="sxs-lookup"><span data-stu-id="34a61-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="34a61-253">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="34a61-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

