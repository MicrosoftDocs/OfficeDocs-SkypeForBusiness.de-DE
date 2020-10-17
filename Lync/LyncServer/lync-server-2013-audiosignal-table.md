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
ms.openlocfilehash: 2605bfbd3e1d4023c013557aea2bcf75404fb23c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533512"
---
# <a name="audiosignal-table-in-lync-server-2013"></a>AudioSignal-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-12_

Jeder Datensatz stellt Audiosignal-Metriken für einen Endpunkt dar. Normalerweise hat jeder Anruf zwei Datensätze, einer ist für den Anrufer und einer für den angerufenen.


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Stellt den Audio-Signalpegel nach dem analogen Gain-Regler dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität sind mindestens 30 dBmo erforderlich. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Siehe SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Stellt den audiorausch Pegel nach dem analogen Gain-Regler dar. Die Einheit für diese Metrik ist dBmo. Zum Erzielen einer akzeptablen Qualität muss der Wert unter 35 dBmo liegen. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Siehe SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Metrik zur Verbesserung der Echo-Rückgabe Verlust. Die Einheit für diese Metrik ist dB. Niedrigere Werte bedeuten weniger Echo. Diese Metrik wird nicht vom A/V-Konferenzserver oder von IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Störschübe pro fünf Minuten für das Lautsprecher Rendering. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Störschübe pro fünf Minuten für die Mikrofon Erfassung. Um eine gute Qualität zu erzielen, sollte höchstens eine Verzögerung pro fünf Minuten auftreten. Wird nicht von A/V-Konferenzservern, Vermittlungsservern oder IP-Telefonen berichtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Clock Drift Rate des Mikrofon Geräts relativ zur CPU-Uhr.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Clock Drift Rate des Lautsprecher Geräts relativ zur CPU-Uhr.</p>
<p>Durchschnittlicher Zeitstempelfehler des Mikrofonaufnahme-Datenstroms in Millisekunden, in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>Decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Durchschnittlicher Zeitstempel Fehler des Lautsprecher Rendering-Streams in Millisekunden in den letzten 20 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Bei der Sprachumschaltung handelt es sich um einen Halbduplexmodus mit der Fähigkeit, Unterbrechungen zu reduzieren. Ursachen des Sprachumschalter Eintrags:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>Die Ursache kann eine Kombination dieser einzelnen Ursachen sein. ENTER_VS_FORCEORCONVERGENCE kann nur für Testzwecke von RegKey aktiviert werden.</p>
<p>Der Datentyp für diese Spalte wurde in Microsoft lync Server 2013 geändert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Ursachen für ein Echo-Ereignis:</p>
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
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der Zeit, als Echo im Mikrofon Erfassungsdaten Strom erkannt wurde. Normalerweise sind die Werte für Headsets oder Mobiltelefone niedrig und für Lautsprecher Telefone oder eigenständige Lautsprecher höher. Bei Geräten, die die akustische Echounterdrückung auf dem Mainboard unterstützen, deuten hohe Werte auf Echo Lecks hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität auszuwerten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Prozentsatz der Zeit, in der ECHO im gesendeten Stream erkannt wird. Ein hoher Echoprozentsatz in gesendeten Datenströmen deutet auf eine Beeinträchtigung durch Echo hin.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway; Dies gilt nur für die Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich zwischen [-30 und -18] dBoV liegen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Empfangene Signalpegel auf dem Vermittlungsserver vom Gateway. Dies betrifft nur den Vermittlungsserver. Die Einheit dieser Metrik ist dBoV. Zum Erzielen einer guten Qualität sollte der akzeptable Bereich unter -50 dBoV liegen.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Automatische Gain-Steuerung (AGC) auf der Vermittlungsserver Seite.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td><p> </p></td>
<td><p>Das Hauptmittel Quadrat (RMS) des eingehenden Signals von bis zu den ersten 30 Sekunden des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Signal Pegel, wie er auf Kanal 1 empfangen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Signal Pegel, wie er auf Kanal 2 empfangen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Auf Kanal 1 empfangenes Rauschniveau.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Auf Kanal 2 empfangenes Rauschniveau.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Signal Pegel, der auf Kanal 1 gesendet wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Signal Pegel, der auf Kanal 2 gesendet wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Auf Kanal 1 gesendeter Geräuschpegel.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Auf Kanal 2 gesendeter Geräuschpegel.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

