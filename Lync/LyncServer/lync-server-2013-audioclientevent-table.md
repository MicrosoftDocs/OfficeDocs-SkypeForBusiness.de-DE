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

# <a name="audioclientevent-table-in-lync-server-2013"></a>AudioClientEvent-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Jeder Datensatz enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einen für den Anrufer und einen für den aufgerufenen.


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
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Auf die <a href="lync-server-2013-medialine-table.md">in der Tabelle medialinie in lync Server 2013</a>verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>0: Daten des angerufenen</p>
<p>1: Daten des Anrufers</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das NetworkSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.</p>
<p>Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des gesendeten Audiosignals.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das ReceiveSendQuality-Ereignis für den Zustand "falsch" ausgelöst wurde.</p>
<p>Die Netzwerkqualität in Bezug auf Jitter oder Paketverlust ist schwerwiegend und beeinträchtigt die Qualität des empfangenen Audiosignals.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das Delay-Ereignis für den Zustand "falsch" ausgelöst wurde. Die Netzwerklatenz ist schwerwiegend und beeinträchtigt die Erfahrung, indem Sie die interaktive Kommunikation verhindert.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das LowBandwidth-Ereignis für den Zustand "falsch" ausgelöst wurde. Die verfügbare Bandbreite reicht für ein akzeptables Spracherlebnis nicht aus.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung das unzureichende CPU-Ereignis wurde für den Zustand "falsch" ausgelöst. Es gibt unzureichende CPU-Zyklen für die Verarbeitung mit den aktuellen Modalitäten und Anwendungen, die verwendet werden. Dies verursacht Verzerrungen beim Audiokanal.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceHalfDuplexAEC-Ereignis für den Zustand "falsch" ausgelöst wurde. Um Echo zu verhindern, hat das System die Eingabe Hälfte Duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceRenderNotFunctioning-Ereignis für den Zustand "falsch" ausgelöst wurde. Das Rendering-Gerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß. Dies kann zu einseitigen Audioproblemen führen.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceCaptureNotFunctioning-Ereignis für den Zustand "falsch" ausgelöst wurde. Das Aufnahmegerät, das derzeit für die Sitzung verwendet wird, funktioniert nicht ordnungsgemäß. Dies kann zu einseitigen Audioproblemen führen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceGlitches-Ereignis für den Zustand "falsch" ausgelöst wurde. Bei der Wiedergabe von Audio, die zu Verzerrungen führt, gibt es schwere Störungen. Diese Störungen können durch Treiber Probleme, verzögerte Prozeduraufrufe (DPC) Storm (Treiber) und eine höhere CPU-Auslastung verursacht werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceLowSNR-Ereignis für den Zustand "falsch" ausgelöst wurde. Die Aufnahmequalität ist sehr schlecht, entweder sehr laut oder der Nutzer spricht zu weit vom Mikrofon entfernt. Dies führt zu Verzerrungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceLowSpeechLevel-Ereignis für den Zustand "falsch" ausgelöst wurde. Der Sprachpegel des Benutzers ist zu gering, und das System kann ihn nicht weiter erhöhen. Dies kann entweder zu Verzerrungen führen oder als unidirektionale Audiowiedergabe wahrgenommen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceClipping-Ereignis für den Zustand "falsch" ausgelöst wurde.</p>
<p>Wenn das Mikrofon in der Nähe von Sprachausgabe Clips abgespielt wird, hören Sie Verzerrungen durch Clipping. Es ist wichtig, das Mikrofon-Clipping in der Nähe zu vermeiden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceEchoEvent-Ereignis für den Zustand "falsch" ausgelöst wurde. Gerät oder Setup verursacht Echo über die Fähigkeit des Systems hinaus, dies zu kompensieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Sitzung, für die das DeviceNearEndToEchoRatio-Ereignis für den Zustand "falsch" ausgelöst wurde. Die Sprache des Benutzers ist im Vergleich zu dem aufgenommenen Echo zu gering, was sich auf die Benutzererfahrung auswirkt, weil dadurch die Benutzerfreundlichkeit eingeschränkt wird. Verringern Sie die Lautstärke des Mikrofons, und bewegen Sie das Mikrofon näher an den Redner.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Häufigkeit, mit der während der Sitzung das DeviceMultipleEndpoints-Ereignis für den Zustand "falsch" ausgelöst wurde. Mehrere Audio-Endpunkte in derselben Sitzung wurden erkannt, und das System hat durch Reduzieren der rendermenge kompensiert.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Häufigkeit, mit der während der Sitzung das DeviceHowlingEvent-Ereignis für den Zustand "falsch" ausgelöst wurde. Audiofeedback-Schleife erkannt (verursacht durch mehrere Endpunkte, die einen Audiopfad freigeben).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Prozentsatz der Sitzung, für die das DeviceRenderZeroVolume-Ereignis ausgelöst wurde, weil es sich im Zustand "ungültig" befand. Das Render-Gerät wurde auf NULL Lautstärke eingestellt.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Der Prozentsatz der Sitzung, für die das DeviceRenderMute-Ereignis ausgelöst wurde, weil es sich im Zustand "ungültig" befand. Das Render-Gerät war stumm geschaltet.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

