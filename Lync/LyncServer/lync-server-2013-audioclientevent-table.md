---
title: 'Lync Server 2013: AudioClientEvent-Tabelle'
description: 'Lync Server 2013: AudioClientEvent-Tabelle.'
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
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568781"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="97a30-103">AudioClientEvent-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97a30-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97a30-104">_**Letztes Änderungsstand des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="97a30-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="97a30-105">Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audio-Anruf.</span><span class="sxs-lookup"><span data-stu-id="97a30-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="97a30-106">Normalerweise verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den angerufenen.</span><span class="sxs-lookup"><span data-stu-id="97a30-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97a30-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="97a30-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="97a30-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="97a30-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97a30-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="97a30-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="97a30-113">Primary</span><span class="sxs-lookup"><span data-stu-id="97a30-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="97a30-114"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="97a30-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-116">int</span><span class="sxs-lookup"><span data-stu-id="97a30-116">int</span></span></p></td>
<td><p><span data-ttu-id="97a30-117">Primary</span><span class="sxs-lookup"><span data-stu-id="97a30-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="97a30-118"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="97a30-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="97a30-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="97a30-121">Primary</span><span class="sxs-lookup"><span data-stu-id="97a30-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="97a30-122"><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</span><span class="sxs-lookup"><span data-stu-id="97a30-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-124">Bit</span><span class="sxs-lookup"><span data-stu-id="97a30-124">bit</span></span></p></td>
<td><p><span data-ttu-id="97a30-125">Primary</span><span class="sxs-lookup"><span data-stu-id="97a30-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="97a30-126">0: Daten des angerufenen</span><span class="sxs-lookup"><span data-stu-id="97a30-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="97a30-127">1: Daten des Anrufers</span><span class="sxs-lookup"><span data-stu-id="97a30-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-129">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-130">Prozentsatz der Sitzung, für die das NetworkSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="97a30-131">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der gesendeten Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="97a30-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-133">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-134">Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="97a30-135">Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der empfangenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="97a30-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-137">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-138">Prozentsatz der Sitzung, für die das Delay-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-139">Die Netzwerkwartezeit ist schwerwiegend und beeinträchtigt die Erfahrung, indem interaktive Kommunikation verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="97a30-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-141">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-142">Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-143">Die verfügbare Bandbreite reicht für eine akzeptable Spracherfahrung nicht aus.</span><span class="sxs-lookup"><span data-stu-id="97a30-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-145">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-146">Prozentsatz der Sitzung, für die das unzureichende CPU-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-147">Es gibt unzureichende CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Anwendungen, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97a30-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="97a30-148">Dadurch werden Verzerrungen beim Audiokanal verursacht.</span><span class="sxs-lookup"><span data-stu-id="97a30-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-150">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-151">Prozentsatz der Sitzung, für die das DeviceHalfDuplexAEC-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-152">Um Echo zu verhindern, hat das System die Eingabe Halbduplex.</span><span class="sxs-lookup"><span data-stu-id="97a30-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-154">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-155">Prozentsatz der Sitzung, für die das DeviceRenderNotFunctioning-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-156">Das Rendering-Gerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="97a30-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="97a30-157">Dies kann zu unidirektionalen Audioproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="97a30-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-159">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-160">Prozentsatz der Sitzung, für die das DeviceCaptureNotFunctioning-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-161">Das Aufnahmegerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="97a30-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="97a30-162">Dies kann zu unidirektionalen Audioproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="97a30-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-164">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-165">Prozentsatz der Sitzung, für die das DeviceGlitches-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-166">Es gibt schwere Störungen bei der Wiedergabe von Audio, die Verzerrungen verursacht.</span><span class="sxs-lookup"><span data-stu-id="97a30-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="97a30-167">Diese Störungen können durch Treiber Probleme, verzögerte Prozeduraufrufe (DPC) Storm (Treiber) und eine hohe CPU-Auslastung verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="97a30-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-169">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-170">Prozentsatz der Sitzung, für die das DeviceLowSNR-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-171">Die Aufnahmequalität ist sehr schlecht, entweder sehr laut, oder der Benutzer redet zu weit vom Mikrofon entfernt.</span><span class="sxs-lookup"><span data-stu-id="97a30-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="97a30-172">Dadurch werden Verzerrungen verursacht.</span><span class="sxs-lookup"><span data-stu-id="97a30-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-174">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-175">Prozentsatz der Sitzung, für die das DeviceLowSpeechLevel-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-176">Der Sprachpegel des Benutzers ist zu niedrig, und das System kann ihn nicht weiter erweitern.</span><span class="sxs-lookup"><span data-stu-id="97a30-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="97a30-177">Dies kann entweder zu Verzerrungen führen oder als unidirektionale Audiodaten wahrgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="97a30-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-179">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-180">Prozentsatz der Sitzung, für die das DeviceClipping-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="97a30-181">Wenn das Mikrofon in der Nähe von Sprachclips abgespielt wird, hört die Verzerrung aufgrund des Clippings auf der Fernseite.</span><span class="sxs-lookup"><span data-stu-id="97a30-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="97a30-182">Es ist wichtig, Near-End-Mikrofon Clipping zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="97a30-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-184">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-185">Prozentsatz der Sitzung, für die das Echo Ereignis am-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-186">Das Gerät oder Setup bewirkt, dass ECHO über die Fähigkeit des Systems hinaus kompensiert wird.</span><span class="sxs-lookup"><span data-stu-id="97a30-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-188">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-189">Prozentsatz der Sitzung, für die das DeviceNearEndToEchoRatio-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-190">Die Sprache des Benutzers ist im Vergleich zu dem erfassten Echo zu niedrig, was sich auf die Benutzererfahrung auswirkt, da Sie die Benutzerfreundlichkeit beschränkt, die für die Unterbrechung eines Benutzers gilt.</span><span class="sxs-lookup"><span data-stu-id="97a30-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="97a30-191">Verringern Sie die Lautsprecherlautstärke, und bringen Sie das Mikrofon näher an den Talker an.</span><span class="sxs-lookup"><span data-stu-id="97a30-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-193">int</span><span class="sxs-lookup"><span data-stu-id="97a30-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="97a30-194">Anzahl der Male während der Sitzung, für die das DeviceMultipleEndpoints-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-195">Mehrere Endpunkte in derselben Sitzung wurden erkannt, und das System hat durch Reduzierung des Render-Volumens kompensiert.</span><span class="sxs-lookup"><span data-stu-id="97a30-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-197">int</span><span class="sxs-lookup"><span data-stu-id="97a30-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="97a30-198">Anzahl der Male während der Sitzung, für die das DeviceHowlingEvent-Ereignis für den Zustand "schlecht" ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="97a30-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="97a30-199">Audiofeedback-Schleife erkannt (verursacht durch mehrere Endpunkte, die den Audiopfad gemeinsam nutzen).</span><span class="sxs-lookup"><span data-stu-id="97a30-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97a30-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-201">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="97a30-202">Prozentsatz der Sitzung, für die das DeviceRenderZeroVolume-Ereignis ausgelöst wurde, weil es sich im Zustand "schlecht" befunden hat.</span><span class="sxs-lookup"><span data-stu-id="97a30-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="97a30-203">Das Render-Gerät wurde auf NULL Volumen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="97a30-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="97a30-204">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="97a30-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97a30-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="97a30-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="97a30-206">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="97a30-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="97a30-207">Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, weil es sich im Zustand "schlecht" befunden hat.</span><span class="sxs-lookup"><span data-stu-id="97a30-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="97a30-208">Das Render-Gerät wurde stumm geschaltet.</span><span class="sxs-lookup"><span data-stu-id="97a30-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="97a30-209">Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="97a30-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

