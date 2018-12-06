---
title: 'Lync Server 2013: AudioClientEvent-Tabelle'
TOCTitle: AudioClientEvent-Tabelle
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413086(v=OCS.15)
ms:contentKeyID: 49296016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AudioClientEvent-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Eintrag enthält ein Clientereignis für einen Endpunkt in einem Audioanruf. In der Regel sind für einen Anruf zwei Einträge vorhanden, einer für den Anrufer und einer für den Angerufenen.


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
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>0: Daten des Angerufenen</p>
<p>1: Daten des Anrufers</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;NetworkSendQuality&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde.</p>
<p>Die Netzwerkqualität wird erheblich durch Jitter und Paketverlust beeinflusst, und die Qualität der gesendeten Audiodaten ist beeinträchtigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;ReceiveSendQuality&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde.</p>
<p>Die Netzwerkqualität wird erheblich durch Jitter und Paketverlust beeinflusst, und die Qualität der empfangenen Audiodaten ist beeinträchtigt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;Delay&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Die Leistung wird durch starke Netzwerklatenz beeinträchtigt, da keine interaktive Kommunikation möglich ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;LowBandwidth&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Die verfügbare Bandbreite ist nicht ausreichend für eine akzeptable VoIP-Qualität.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das Ereignis für unzureichende CPU aufgrund eines ungültigen Status ausgelöst wurde. Die CPU-Zyklen reichen nicht für die Verarbeitung der aktuellen Modalitäten und verwendeten Anwendungen aus, was Verzerrungen im Audiokanal zur Folge hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceHalfDuplexAEC&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Das System ist in den Halbduplexmodus gewechselt, um Echo zu vermeiden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceRenderNotFunctioning&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Das für die aktuelle Sitzung verwendete Darstellungsgerät funktioniert nicht ordnungsgemäß, was u. U. unidirektionale Audioprobleme zur Folge hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceCaptureNotFunctioning&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Das für die aktuelle Sitzung verwendete Aufnahmegerät funktioniert nicht ordnungsgemäß, was u. U. unidirektionale Audioprobleme zur Folge hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceGlitches&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Die Audiowiedergabe weist erhebliche Verzögerungen auf, die Verzerrungen zur Folge haben. Diese Verzögerungen werden möglicherweise durch Treiberprobleme, zahlreiche DPCs (Deferred Procedure Calls) und hohe CPU-Auslastung ausgelöst.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceLowSNR&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Sehr schlechte Aufnahmequalität, entweder durch Rauschen, oder der Benutzer ist beim Gespräch zu weit vom Mikrofon entfernt. Dies hat Verzerrungen zur Folge.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceLowSpeechLevel&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Der Sprachpegel des Benutzers ist zu niedrig und kann vom System nicht weiter verstärkt werden. Dies hat entweder Verzerrungen zur Folge, oder wird als unidirektionale Audioübertragung wahrgenommen.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceClipping&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde.</p>
<p>Wenn Sprache am nahen Ende zum Mikrofon abgeschnitten wird, treten beim entfernten Benutzer Verzerrungen auf. Daher sollten Abschneidungen am nahen Ende vermieden werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceEchoEvent&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Das Gerät oder die Einrichtung lösen ein Echo aus, das vom System nicht mehr kompensiert werden kann.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;DeviceNearEndToEchoRatio&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Die Sprache des Benutzers ist im Vergleich zum erfassten Echo zu leise. Dadurch wird die Qualität für Benutzer beeinträchtigt, da das problemlose Unterbrechen eines Benutzers eingeschränkt ist. Verringern Sie entweder die Lautstärke des Lautsprechers oder den Abstand des Mikrofons zum Sprecher.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Anzahl der &quot;DeviceMultipleEndpoints&quot;-Ereignisse, die während der Sitzung aufgrund eines ungültigen Status ausgelöst wurden. In derselben Sitzung wurden mehrere Audio-Endpunkte erkannt, was von System durch Verringern der Wiedergabelautstärke kompensiert wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Anzahl der &quot;DeviceHowlingEvent&quot;-Ereignisse, die während der Sitzung aufgrund eines ungültigen Status ausgelöst wurden. Eine Audiorückkopplungsschleife wurde erkannt (ausgelöst durch die gemeinsame Verwendung eines Audiopfads durch mehrere Endpunkte).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Sitzungen, in denen das &quot;DeviceRenderZeroVolume&quot;-Ereignis aufgrund des Status &quot;Ungültig&quot; ausgelöst wurde. Das Darstellungsgerät war auf Lautstärke Null eingestellt.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Sitzungen, in denen das &quot;DeviceRenderMute&quot;-Ereignis aufgrund des Status &quot;Ungültig&quot; ausgelöst wurde. Das Darstellungsgerät war stummgeschaltet.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

