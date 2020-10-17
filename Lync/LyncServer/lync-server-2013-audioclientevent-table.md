---
title: 'Lync Server 2013: AudioClientEvent-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fff3c143f06fe7a71d10b65bd281be4619cb8942
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533522"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="cd22c-102">AudioClientEvent-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd22c-102">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd22c-103">_**Letztes Änderungsstand des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="cd22c-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="cd22c-104">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audio-Anruf.</span><span class="sxs-lookup"><span data-stu-id="cd22c-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="cd22c-105">Normalerweise verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den angerufenen.</span><span class="sxs-lookup"><span data-stu-id="cd22c-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd22c-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="cd22c-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="cd22c-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="cd22c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="cd22c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="cd22c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="cd22c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd22c-113"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="cd22c-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-115">int</span><span class="sxs-lookup"><span data-stu-id="cd22c-115">int</span></span></p></td>
<td><p><span data-ttu-id="cd22c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="cd22c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd22c-117"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="cd22c-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="cd22c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="cd22c-120">Primary</span><span class="sxs-lookup"><span data-stu-id="cd22c-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd22c-121"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="cd22c-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-123">Bit</span><span class="sxs-lookup"><span data-stu-id="cd22c-123">bit</span></span></p></td>
<td><p><span data-ttu-id="cd22c-124">Primary</span><span class="sxs-lookup"><span data-stu-id="cd22c-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd22c-125">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="cd22c-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="cd22c-126">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="cd22c-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-128">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-129">Prozentsatz der Sitzung, für die das NetworkSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="cd22c-130">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der gesendeten Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="cd22c-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-132">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-133">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="cd22c-134">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der empfangenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="cd22c-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-136">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-137">Prozentsatz der Sitzung, für die das Delay-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-138">Die Netzwerkwartezeit ist schwerwiegend und beeinträchtigt die Erfahrung, indem interaktive Kommunikation verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="cd22c-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-140">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-141">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-142">Die verfügbare Bandbreite reicht für eine akzeptable Spracherfahrung nicht aus.</span><span class="sxs-lookup"><span data-stu-id="cd22c-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-144">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-145">Prozentsatz der Sitzung, für die das unzureichende CPU-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-146">Es gibt unzureichende CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Anwendungen, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd22c-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="cd22c-147">Dadurch werden Verzerrungen beim Audiokanal verursacht.</span><span class="sxs-lookup"><span data-stu-id="cd22c-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-149">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-150">Prozentsatz der Sitzung, für die das DeviceHalfDuplexAEC-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-151">Um Echo zu verhindern, hat das System die Eingabe Halbduplex.</span><span class="sxs-lookup"><span data-stu-id="cd22c-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-153">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-154">Prozentsatz der Sitzung, für die das DeviceRenderNotFunctioning-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-155">Das Rendering-Gerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="cd22c-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="cd22c-156">Dies kann zu unidirektionalen Audioproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="cd22c-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-158">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-159">Prozentsatz der Sitzung, für die das DeviceCaptureNotFunctioning-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-160">Das Aufnahmegerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="cd22c-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="cd22c-161">Dies kann zu unidirektionalen Audioproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="cd22c-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-163">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-164">Prozentsatz der Sitzung, für die das DeviceGlitches-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-165">Es gibt schwere Störungen bei der Wiedergabe von Audio, die Verzerrungen verursacht.</span><span class="sxs-lookup"><span data-stu-id="cd22c-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="cd22c-166">Diese Störungen können durch Treiber Probleme, verzögerte Prozeduraufrufe (DPC) Storm (Treiber) und eine hohe CPU-Auslastung verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="cd22c-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-168">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-169">Prozentsatz der Sitzung, für die das DeviceLowSNR-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-170">Die Aufnahmequalität ist sehr schlecht, entweder sehr laut, oder der Benutzer redet zu weit vom Mikrofon entfernt.</span><span class="sxs-lookup"><span data-stu-id="cd22c-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="cd22c-171">Dadurch werden Verzerrungen verursacht.</span><span class="sxs-lookup"><span data-stu-id="cd22c-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-173">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-174">Prozentsatz der Sitzung, für die das DeviceLowSpeechLevel-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-175">Der Sprachpegel des Benutzers ist zu niedrig, und das System kann ihn nicht weiter erweitern.</span><span class="sxs-lookup"><span data-stu-id="cd22c-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="cd22c-176">Dies kann entweder zu Verzerrungen führen oder als unidirektionale Audiodaten wahrgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="cd22c-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-178">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-179">Prozentsatz der Sitzung, für die das DeviceClipping-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="cd22c-180">Wenn das Mikrofon in der Nähe von Sprachclips abgespielt wird, hört die Verzerrung aufgrund des Clippings auf der Fernseite.</span><span class="sxs-lookup"><span data-stu-id="cd22c-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="cd22c-181">Es ist wichtig, Near-End-Mikrofon Clipping zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="cd22c-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-183">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-184">Prozentsatz der Sitzung, für die das Echo Ereignis am-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-185">Das Gerät oder Setup bewirkt, dass ECHO über die Fähigkeit des Systems hinaus kompensiert wird.</span><span class="sxs-lookup"><span data-stu-id="cd22c-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-187">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-188">Prozentsatz der Sitzung, für die das DeviceNearEndToEchoRatio-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-189">Die Sprache des Benutzers ist im Vergleich zu dem erfassten Echo zu niedrig, was sich auf die Benutzererfahrung auswirkt, da Sie die Benutzerfreundlichkeit beschränkt, die für die Unterbrechung eines Benutzers gilt.</span><span class="sxs-lookup"><span data-stu-id="cd22c-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="cd22c-190">Verringern Sie die Lautsprecherlautstärke, und bringen Sie das Mikrofon näher an den Talker an.</span><span class="sxs-lookup"><span data-stu-id="cd22c-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-192">int</span><span class="sxs-lookup"><span data-stu-id="cd22c-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd22c-193">Anzahl der Male während der Sitzung, für die das DeviceMultipleEndpoints-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-194">Mehrere Endpunkte in derselben Sitzung wurden erkannt, und das System hat durch Reduzierung des Render-Volumens kompensiert.</span><span class="sxs-lookup"><span data-stu-id="cd22c-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-196">int</span><span class="sxs-lookup"><span data-stu-id="cd22c-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22c-197">Anzahl der Male während der Sitzung, für die das DeviceHowlingEvent-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="cd22c-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="cd22c-198">Audiofeedback-Schleife erkannt (verursacht durch mehrere Endpunkte, die den Audiopfad gemeinsam nutzen).</span><span class="sxs-lookup"><span data-stu-id="cd22c-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22c-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-200">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd22c-201">Prozentsatz der Sitzung, für die das DeviceRenderZeroVolume-Ereignis ausgelöst wurde, weil es sich im Zustand "schlecht" befunden hat.</span><span class="sxs-lookup"><span data-stu-id="cd22c-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="cd22c-202">Das Render-Gerät wurde auf NULL Volumen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cd22c-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="cd22c-203">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cd22c-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22c-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cd22c-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22c-205">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cd22c-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd22c-206">Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, weil es sich im Zustand "schlecht" befunden hat.</span><span class="sxs-lookup"><span data-stu-id="cd22c-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="cd22c-207">Das Render-Gerät wurde stumm geschaltet.</span><span class="sxs-lookup"><span data-stu-id="cd22c-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="cd22c-208">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cd22c-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

