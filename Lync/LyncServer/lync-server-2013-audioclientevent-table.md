---
title: 'Lync Server 2013: AudioClientEvent-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489777458838d5e77df1f8c82ed6ab8b6c295832
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="52c88-102">AudioClientEvent-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52c88-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52c88-103">_**Letztes Änderungsdatum des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="52c88-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="52c88-104">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf.</span><span class="sxs-lookup"><span data-stu-id="52c88-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="52c88-105">In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="52c88-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52c88-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="52c88-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="52c88-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="52c88-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52c88-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-111">datetime</span><span class="sxs-lookup"><span data-stu-id="52c88-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="52c88-112">Primary</span><span class="sxs-lookup"><span data-stu-id="52c88-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="52c88-113">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="52c88-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-115">int</span><span class="sxs-lookup"><span data-stu-id="52c88-115">int</span></span></p></td>
<td><p><span data-ttu-id="52c88-116">Primary</span><span class="sxs-lookup"><span data-stu-id="52c88-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="52c88-117">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="52c88-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="52c88-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="52c88-120">Primary</span><span class="sxs-lookup"><span data-stu-id="52c88-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="52c88-121">Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="52c88-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-123">bit</span><span class="sxs-lookup"><span data-stu-id="52c88-123">bit</span></span></p></td>
<td><p><span data-ttu-id="52c88-124">Primary</span><span class="sxs-lookup"><span data-stu-id="52c88-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="52c88-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="52c88-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="52c88-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="52c88-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-128">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-129">Prozentsatz der Sitzung, für die das NetworkSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="52c88-130">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des gesendeten Audiosignals.</span><span class="sxs-lookup"><span data-stu-id="52c88-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-132">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-133">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="52c88-134">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des empfangenen Audiosignals.</span><span class="sxs-lookup"><span data-stu-id="52c88-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-136">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-137">Prozentsatz der Sitzung, für die das Delay-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-138">Die Netzwerklatenz ist schwerwiegend und beeinträchtigt die Erfahrung, indem Sie die interaktive Kommunikation verhindert.</span><span class="sxs-lookup"><span data-stu-id="52c88-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-140">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-141">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-142">Die verfügbare Bandbreite reicht für ein akzeptables Spracherlebnis nicht aus.</span><span class="sxs-lookup"><span data-stu-id="52c88-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-144">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-145">Prozentsatz der Sitzung das unzureichende CPU-Ereignis wurde für den Zustand "falsch" ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="52c88-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-146">Es gibt unzureichende CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Anwendungen, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52c88-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="52c88-147">Dies verursacht Verzerrungen beim Audiokanal.</span><span class="sxs-lookup"><span data-stu-id="52c88-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-149">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-150">Prozentsatz der Sitzung, für die das DeviceHalfDuplexAEC-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-151">Um Echo zu verhindern, hat das System die Eingabe Hälfte Duplex.</span><span class="sxs-lookup"><span data-stu-id="52c88-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-153">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-154">Prozentsatz der Sitzung, für die das DeviceRenderNotFunctioning-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-155">Das Rendering-Gerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="52c88-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="52c88-156">Dies kann zu einseitigen Audioproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="52c88-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-158">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-159">Prozentsatz der Sitzung, für die das DeviceCaptureNotFunctioning-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-160">Das Aufnahmegerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="52c88-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="52c88-161">Dies kann zu einseitigen Audioproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="52c88-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-163">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-164">Prozentsatz der Sitzung, für die das DeviceGlitches-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-165">Bei der Wiedergabe von Audio, die zu Verzerrungen führt, gibt es schwere Störungen.</span><span class="sxs-lookup"><span data-stu-id="52c88-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="52c88-166">Diese Störungen können durch Treiber Probleme, verzögerte Prozeduraufrufe (DPC) Storm (Treiber) und eine höhere CPU-Auslastung verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="52c88-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-168">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-169">Prozentsatz der Sitzung, für die das DeviceLowSNR-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-170">Die Aufnahmequalität ist sehr schlecht, entweder sehr laut oder der Nutzer spricht zu weit vom Mikrofon entfernt.</span><span class="sxs-lookup"><span data-stu-id="52c88-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="52c88-171">Dies führt zu Verzerrungen.</span><span class="sxs-lookup"><span data-stu-id="52c88-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-173">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-174">Prozentsatz der Sitzung, für die das DeviceLowSpeechLevel-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-175">Der Sprachpegel des Benutzers ist zu gering, und das System kann ihn nicht weiter erhöhen.</span><span class="sxs-lookup"><span data-stu-id="52c88-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="52c88-176">Dies kann entweder zu Verzerrungen führen oder als unidirektionale Audiowiedergabe wahrgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="52c88-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-178">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-179">Prozentsatz der Sitzung, für die das DeviceClipping-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="52c88-180">Wenn das Mikrofon in der Nähe von Sprachausgabe Clips abgespielt wird, hören Sie Verzerrungen durch Clipping.</span><span class="sxs-lookup"><span data-stu-id="52c88-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="52c88-181">Es ist wichtig, das Mikrofon-Clipping in der Nähe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="52c88-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-183">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-184">Prozentsatz der Sitzung, für die das DeviceEchoEvent-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-185">Gerät oder Setup verursacht Echo über die Fähigkeit des Systems hinaus, dies zu kompensieren.</span><span class="sxs-lookup"><span data-stu-id="52c88-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-187">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-188">Prozentsatz der Sitzung, für die das DeviceNearEndToEchoRatio-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-189">Die Sprache des Benutzers ist im Vergleich zu dem aufgenommenen Echo zu gering, was sich auf die Benutzererfahrung auswirkt, weil dadurch die Benutzerfreundlichkeit eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="52c88-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="52c88-190">Verringern Sie die Lautstärke des Mikrofons, und bewegen Sie das Mikrofon näher an den Redner.</span><span class="sxs-lookup"><span data-stu-id="52c88-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-192">int</span><span class="sxs-lookup"><span data-stu-id="52c88-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52c88-193">Häufigkeit, mit der während der Sitzung das DeviceMultipleEndpoints-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-194">Mehrere Audio-Endpunkte in derselben Sitzung wurden erkannt, und das System hat durch Reduzieren der rendermenge kompensiert.</span><span class="sxs-lookup"><span data-stu-id="52c88-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-196">int</span><span class="sxs-lookup"><span data-stu-id="52c88-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="52c88-197">Häufigkeit, mit der während der Sitzung das DeviceHowlingEvent-Ereignis für den Zustand "falsch" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="52c88-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="52c88-198">Audiofeedback-Schleife erkannt (verursacht durch mehrere Endpunkte, die einen Audiopfad freigeben).</span><span class="sxs-lookup"><span data-stu-id="52c88-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52c88-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-200">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52c88-201">Der Prozentsatz der Sitzung, für die das DeviceRenderZeroVolume-Ereignis ausgelöst wurde, weil es sich im Zustand "ungültig" befand.</span><span class="sxs-lookup"><span data-stu-id="52c88-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="52c88-202">Das Render-Gerät wurde auf NULL Lautstärke eingestellt.</span><span class="sxs-lookup"><span data-stu-id="52c88-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="52c88-203">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="52c88-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52c88-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="52c88-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="52c88-205">Dezimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="52c88-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52c88-206">Der Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, weil es sich im Zustand "ungültig" befand.</span><span class="sxs-lookup"><span data-stu-id="52c88-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="52c88-207">Das Render-Gerät war stumm geschaltet.</span><span class="sxs-lookup"><span data-stu-id="52c88-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="52c88-208">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="52c88-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

