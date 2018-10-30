---
title: 'Lync Server 2013: AudioSignal-Tabelle'
TOCTitle: AudioSignal-Tabelle
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398064(v=OCS.15)
ms:contentKeyID: 49292970
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AudioSignal-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Eintrag stellt Audiosignalmetriken für einen Endpunkt dar. In der Regel sind für jeden Anruf zwei Einträge vorhanden, einer für den Anrufer und einer für den Angerufenen.


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Stellt die Stärke des Audiosignals der postanalogen Verstärkung dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Siehe &quot;SendSignalLevel&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Stellt die Stärke des Audiogeräusches der postanalogen Verstärkung dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 35 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Siehe &quot;SendNoiseLevel&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Echodämpfungs-Verbesserungsmetrik. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Verzögerungen pro fünf Minuten für die Lautsprecherwiedergabe. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Verzögerungen pro fünf Minuten für die Mikrofonerfassung. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Driftrate der Uhr des Mikrofons, relativ zum CPU-Takt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Driftrate der Uhr des Lautsprechers, relativ zum CPU-Takt.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Driftrate der Uhr des Lautsprechers, relativ zum CPU-Takt.</p>
<p>Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Durchschnittlicher Zeitstempelfehler des Lautsprecherwiedergabe-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Ursachen für den Wechsel in den Sprachumschaltungsmodus:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>Die Ursache kann eine Kombination dieser einzelnen Ursachen sein. &quot;ENTER_VS_FORCEORCONVERGENCE&quot; kann von regkey nur zu Testzwecken aktiviert werden.</p>
<p>Der Datentyp für diese Spalte wurde in Microsoft Lync Server 2013 geändert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Ursachen für Echoereignis:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>Die Ursache kann eine Kombination dieser einzelnen Ursachen sein.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom Echo festgestellt wurde. In der Regel weisen Headsets oder Hörer niedrige Werte und Freisprechvorrichtungen oder eigenständige Lautsprecher höhere Werte auf. Bei Geräten, die eine integrierte akustische Echounterdrückung unterstützen, weisen hohe Werte auf eine Echoausbreitung hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu evaluieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Zeit, in der im gesendeten Datenstrom Echo festgestellt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway; betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Stärke des auf dem Vermittlungsserver empfangenen Signals vom Gateway. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Eingebauter Verstärker (AGC) auf der Vermittlungsserverseite.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>Quadratischer Mittelwert (RMS) des eingehenden Signals in den ersten 30 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 1 empfangene Signalstärke.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 2 empfangene Signalstärke.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 1 empfangenes Rauschen.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 2 empfangenes Rauschen.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 1 gesendete Signalstärke.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 2 gesendete Signalstärke.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 1 gesendetes Rauschen.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Auf Kanal 2 gesendetes Rauschen.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

