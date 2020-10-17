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
# <a name="audioclientevent-table-in-lync-server-2013"></a>AudioClientEvent-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-17_

Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audio-Anruf. Normalerweise verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den angerufenen.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Spalte</strong></th>
<th><strong>Datentyp</strong></th>
<th><strong>Schlüssel/Index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">In lync Server 2013 auf die Medientabelle</a>verwiesen.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>Bit</p></td>
<td><p>Primary</p></td>
<td><p>0: Daten des angerufenen</p>
<p>1: Daten des Anrufers</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das NetworkSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</p>
<p>Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der gesendeten Audiodaten.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "schlecht" ausgelöst wurde.</p>
<p>Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist gravierend und beeinträchtigt die Qualität der empfangenen Audiodaten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das Delay-Ereignis für den Zustand "schlecht" ausgelöst wurde. Die Netzwerkwartezeit ist schwerwiegend und beeinträchtigt die Erfahrung, indem interaktive Kommunikation verhindert wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "schlecht" ausgelöst wurde. Die verfügbare Bandbreite reicht für eine akzeptable Spracherfahrung nicht aus.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das unzureichende CPU-Ereignis für den Zustand "schlecht" ausgelöst wurde. Es gibt unzureichende CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Anwendungen, die verwendet werden. Dadurch werden Verzerrungen beim Audiokanal verursacht.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceHalfDuplexAEC-Ereignis für den Zustand "schlecht" ausgelöst wurde. Um Echo zu verhindern, hat das System die Eingabe Halbduplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceRenderNotFunctioning-Ereignis für den Zustand "schlecht" ausgelöst wurde. Das Rendering-Gerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß. Dies kann zu unidirektionalen Audioproblemen führen.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceCaptureNotFunctioning-Ereignis für den Zustand "schlecht" ausgelöst wurde. Das Aufnahmegerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß. Dies kann zu unidirektionalen Audioproblemen führen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceGlitches-Ereignis für den Zustand "schlecht" ausgelöst wurde. Es gibt schwere Störungen bei der Wiedergabe von Audio, die Verzerrungen verursacht. Diese Störungen können durch Treiber Probleme, verzögerte Prozeduraufrufe (DPC) Storm (Treiber) und eine hohe CPU-Auslastung verursacht werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceLowSNR-Ereignis für den Zustand "schlecht" ausgelöst wurde. Die Aufnahmequalität ist sehr schlecht, entweder sehr laut, oder der Benutzer redet zu weit vom Mikrofon entfernt. Dadurch werden Verzerrungen verursacht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceLowSpeechLevel-Ereignis für den Zustand "schlecht" ausgelöst wurde. Der Sprachpegel des Benutzers ist zu niedrig, und das System kann ihn nicht weiter erweitern. Dies kann entweder zu Verzerrungen führen oder als unidirektionale Audiodaten wahrgenommen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceClipping-Ereignis für den Zustand "schlecht" ausgelöst wurde.</p>
<p>Wenn das Mikrofon in der Nähe von Sprachclips abgespielt wird, hört die Verzerrung aufgrund des Clippings auf der Fernseite. Es ist wichtig, Near-End-Mikrofon Clipping zu vermeiden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das Echo Ereignis am-Ereignis für den Zustand "schlecht" ausgelöst wurde. Das Gerät oder Setup bewirkt, dass ECHO über die Fähigkeit des Systems hinaus kompensiert wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceNearEndToEchoRatio-Ereignis für den Zustand "schlecht" ausgelöst wurde. Die Sprache des Benutzers ist im Vergleich zu dem erfassten Echo zu niedrig, was sich auf die Benutzererfahrung auswirkt, da Sie die Benutzerfreundlichkeit beschränkt, die für die Unterbrechung eines Benutzers gilt. Verringern Sie die Lautsprecherlautstärke, und bringen Sie das Mikrofon näher an den Talker an.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Anzahl der Male während der Sitzung, für die das DeviceMultipleEndpoints-Ereignis für den Zustand "schlecht" ausgelöst wurde. Mehrere Endpunkte in derselben Sitzung wurden erkannt, und das System hat durch Reduzierung des Render-Volumens kompensiert.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Anzahl der Male während der Sitzung, für die das DeviceHowlingEvent-Ereignis für den Zustand "schlecht" ausgelöst wurde. Audiofeedback-Schleife erkannt (verursacht durch mehrere Endpunkte, die den Audiopfad gemeinsam nutzen).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceRenderZeroVolume-Ereignis ausgelöst wurde, weil es sich im Zustand "schlecht" befunden hat. Das Render-Gerät wurde auf NULL Volumen festgelegt.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, weil es sich im Zustand "schlecht" befunden hat. Das Render-Gerät wurde stumm geschaltet.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

