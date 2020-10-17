---
title: 'Lync Server 2013: AudioStream-Tabelle'
description: 'Lync Server 2013: AudioStream-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552341"
---
# <a name="audiostream-table-in-lync-server-2013"></a>AudioStream-Tabelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Jeder Datensatz stellt einen Audiostream dar. Eine Audio-Medien Verbindung enthält normalerweise zwei Audiostreams.


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
<td><p><strong>Datenstrom-Nr</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID innerhalb einer Medienzeile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximaler Netzwerkjitter während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>Decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>Decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Maximale Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>Decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dichte des Paketverlusts bei Bursts von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dauer an Paketverlusten bei Bursts von Verlusten während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>Decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dichte an Paketverlusten bei Lücken zwischen Bursts von Paketverlusten.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Dauer der Lücken zwischen Bursts von Paketverlusten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Paketwert für den Audiostream.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bandbreite</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Bandbreitenschätzungen für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Netzwerk-MOS-Beeinträchtigung für den gesamten Anruf. Der Bereich umfasst 0,0 bis 5,0.  Diese Metrik gibt an, um welche Menge der Netzwerk-MOS aufgrund von Jitter und Paketverlusten reduziert wurde. Der Wert sollte weniger als 0,5 betragen, um eine akzeptable Qualität zu bieten.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Maximale Netzwerk-MOS-Beeinträchtigung während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Netzwerk-MOS-Beeinträchtigung aufgrund von Jitter.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Netzwerk-MOS-Beeinträchtigung aufgrund von Paketverlust.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der für den Anruf verwendete Audiocodec, der von der PayloadDescription-Tabelle referenziert wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Samplingrate für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roundtrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Roundtripzeit aus RTCP-Statistik. Für eine akzeptable Qualität sollte dies weniger als 100M sein.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximale Roundtripzeit für den Audiostream.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Durchschnittlicher Breitband-Netzwerk-MOS für den Anruf. Diese Metrik ist abhängig vom Paketverlust, Jitter und dem verwendeten Codec. Bereich ist [1,0 zu 5,0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Die minimale Breitband-Netzwerk-Mos für den Anruf.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Die durchschnittliche vorhergesagte Wideband-Abhör-Mos-Bewertung für gesendete Audiodaten, einschließlich Sprachpegel, Rauschpegel und Eigenschaften von Aufnahmegeräten.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Die minimale SendListenMOS für den Anruf.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Die durchschnittliche vorhergesagte Wideband-Abhör-Mos-Bewertung für vom Netzwerk empfangene Audiodaten, einschließlich Sprachpegel, Rauschen, Codec, Netzwerkbedingungen und Eigenschaften für das Capture-Gerät.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>Decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Die minimale RecvListenMOS für den Anruf.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Flag, das angibt, ob Audio FEC für den Anruf verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Durchschnittliches Verhältnis zwischen ausgeblendeten Samples, generiert durch Audioreparatur, und Standardsamples.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Durchschnittliches Verhältnis zwischen gestreckten Samples, generiert durch Audioreparatur, und Standardsamples.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Durchschnittliches Verhältnis zwischen komprimierten Samples, generiert durch Audioreparatur, und Standardsamples.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Eingehende</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Datenstrom auf Empfängerseite wird empfangen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ausgehende</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Datenstrom auf Absenderseite wird empfangen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, dass die Datenstrom Richtung vom Anrufer zum angerufenen stammt.</p>
<p>0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Standard Abweichung für Jitter-Ankunftszeiten.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Maximales Verhältnis von Paketen, die vom Heiler verborgen sind.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Standard Abweichung für das Verhältnis von Paketen, die vom Heiler verborgen sind.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Verhältnis der Pakete, die vom Heiler zurückgegeben wurden, mit der Gesamtzahl der empfangenen Pakete.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Verhältnis der verwendeten Forward-Fehlerkorrektur Pakete im Vergleich zur Gesamtzahl der empfangenen Pakete.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Maximale Anzahl von Audiopaketen, die von der Heiler-Datei komprimiert wurden.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</p>
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
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der als Stereo decodiert wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo gerendert wird.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der als Stereo codiert ist.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der von der akustischen Echounterdrückung als Stereo erfasst wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

