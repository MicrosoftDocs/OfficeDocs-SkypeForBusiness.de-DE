---
title: 'Lync Server 2013: AudioStream-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>AudioStream-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Jeder Datensatz steht für einen Audiostream. Eine Audio-Media-Zeile enthält in der Regel zwei Audiostreams.


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
<td><p><strong>Datenstrom-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID innerhalb einer medienzeile</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittlicher Netzwerk-Jitter aus RTCP-Statistiken (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximaler Netzwerk Jitter während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>Dezimal (5; 4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>Dezimal (5; 4)</p></td>
<td><p> </p></td>
<td><p>Maximaler Paketverlust während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>Dezimal (9; 4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dichte des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dauer des Paketverlusts während des Ausbruchs von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>Dezimal (9; 4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dichte des Paketverlusts bei Lücken zwischen Bursts des Paketverlusts.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dauer von Lücken zwischen Bursts des Paketverlusts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Die Anzahl der Pakete für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bandbreite</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Bandbreiten Schätzungen für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Netzwerk-Mos-Verschlechterung für den gesamten Anruf. Der Bereich ist 0,0 bis 5,0. Diese Metrik zeigt die Menge, die das Netzwerk Mos aufgrund von Jitter und Paketverlust reduziert wurde. Für akzeptable Qualität sollte es weniger als 0,5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Maximaler Netzwerk-Mos-Abbau während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Netzwerk-Mos-Beeinträchtigung durch Jitter.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Netzwerk-Mos-Beeinträchtigung durch Paketverlust.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der für den Anruf verwendete Audiocodec, auf den von der PayloadDescription-Tabelle verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Abtastrate für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Roundtrip-Zeit von RTCP-Statistiken Bei akzeptabler Qualität sollte dies weniger als 100M betragen.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximale Roundtrip-Zeit für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Breitband-Netzwerk-Mos für den Anruf. Diese Metrik hängt vom verwendeten Paketverlust, Jitter und Codec ab. Bereich ist [1,0 bis 5,0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Das Mindest-Breitband-Netzwerk Mos für den Anruf.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Der durchschnittliche prognostizierte Breitband-Abhör-Mos-Score für gesendete Audiodaten, einschließlich der Eigenschaften für Sprachpegel, Geräuschpegel und Aufnahmegeräte.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Die Mindest-SendListenMOS für den Anruf.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Der durchschnittliche prognostizierte Breitband-Abhör-Mos-Score für vom Netzwerk empfangene Audiosignale, einschließlich Sprachpegel, Geräuschpegel, Codec, Netzwerkbedingungen und Merkmale des Aufnahmegeräts.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>Dezimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Die Mindest-RecvListenMOS für den Anruf.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Flag, das angibt, ob Audio FEC für den Anruf verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Durchschnittliches Verhältnis der verborgenen Samples, die von der audioheilung an typische Samples generiert wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Durchschnittliches Verhältnis von gedehnten Samples, die von der audioheilung zu typischen Samples generiert wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Durchschnittliches Verhältnis von komprimierten Samples, die von der audioheilung zu typischen Samples generiert wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Datenstrom auf Empfängerseite wird empfangen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ausgehend</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Datenstrom auf Absenderseite wird empfangen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, dass die Datenstrom Richtung vom Aufrufer an den aufgerufenen gesendet wird.</p>
<p>0 bedeutet, dass die Datenstrom Richtung vom aufgerufenen zum Aufrufer ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Standard Abweichung für Jitter-Ankunftszeiten.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Maximales Verhältnis von Paketen, die vom Heiler verborgen sind.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Standard Abweichung für das Verhältnis von Paketen, die vom Heiler verborgen sind.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Das Verhältnis der vom Heiler abgegebenen Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Verhältnis der verwendeten Forward-Fehlerkorrektur Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Die maximale Anzahl von Audiopaketen, die vom Heiler komprimiert wurden.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Gibt den Prozentsatz der Zeit an, zu der sich der Anruf in einem Engpass Zustand befand.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Gibt den Prozentsatz des Anrufs an, während dessen Überlastung durch das verspätete Eintreffen von Netzwerkpaketen verursacht wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Gibt den Prozentsatz der Zeit an, zu der der Anruf im Wettbewerb um Netzwerkressourcen erfolgte.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Minimaler Grad der Bandbreitenschätzung, gemessen während des Anrufs.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Gesamtzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Durchschnittliche Anzahl der unidirektionalen Latenzzeit. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Maximale Anzahl von unidirektionalen Latenzzeiten. Die relative unidirektionale Latenz misst die Verzögerung zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gesamtzahl der einseitigen Burst-Ereignisse. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Totale unidirektionale Burst Dichte. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Gesamtdauer des einseitigen Bursts. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Gesamtanzahl der einseitigen Lücken. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Gesamtdichte für einseitigen Abstand. Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Gesamtdauer der einseitigen Lücke Eine "bursty"-Übertragung ist eine Übertragung, bei der Daten in unvorhersehbaren Bursts im Gegensatz zu einem unveränderlichen Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der als Stereo decodiert wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo gerendert wird.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Die Paketverlustrate, nachdem die weiter Leitungsfehler Korrektur angewendet wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Prozentsatz des als Stereo codierten Anrufs.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo aufgenommen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

