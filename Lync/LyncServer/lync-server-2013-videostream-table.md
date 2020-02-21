---
title: 'Lync Server 2013: Videostream-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Videostream-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-12-13_

Jeder Datensatz stellt einen Videodatenstrom dar. Eine Video Medien Verbindung enthält normalerweise zwei Videodatenströme.


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
<td><p>R, die von der <a href="lync-server-2013-medialine-table.md">medialinie-Tabelle in lync Server 2013</a>referenziert wird.</p></td>
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
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>Foreign, Primary</p></td>
<td><p>Beschreibung der Nutzlast. Weitere Informationen finden Sie <a href="lync-server-2013-payloaddescription-table.md">in der PayloadDescription-Tabelle in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittlicher Netzwerkjitter aus RTCP-Statistik (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximale Netzwerk Jitter während der Videositzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Roundtripzeit aus RTCP-Statistik.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximale Zeit für Roundtrips für den Videostream.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>Decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>Decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Maximale Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Paketwert für den Videostream (Real Time Transport Protocol, RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bandbreite</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Schätzungen der Bandbreite für den Videostream.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char (9)</p></td>
<td><p> </p></td>
<td><p>Auflösung des Videos in Pixel Breite x Höhe. Gemeldet als Zeichenfolge.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Bitrate des Videostreams.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>Decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Die empfangene Videoframerate.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>Decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Die gesendete Videobildrate.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Die maximale Video Bitrate während der Videositzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>Decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Nicht verfügbar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>Decimal (9, 4)</p></td>
<td></td>
<td><p>Der Prozentsatz der Gesamtzahl der Videoframes, die verloren gehen.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Der Prozentsatz des Anrufs, bei dem es sich um die CIF-Auflösung (Common Interchange Format) handelte.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Der Prozentsatz des Anrufs, bei dem es sich um eine VGA-Auflösung handelt.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Der Prozentsatz des Anrufs, bei dem die HD720-Auflösung stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Prozentsatz der Anrufdauer ohne Frame-Drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Prozentsatz der Anrufdauer mit B-Frame-Drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Prozentsatz der Anrufdauer mit dem BP-Frame-Drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Prozentsatz der Anrufdauer mit BPSP Frame Drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Prozentsatz der Anrufdauer mit BPSPI Frame Drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eingehend</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Datenstrom auf Empfängerseite wird empfangen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ausgehend</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>Datenstrom auf Absenderseite wird empfangen.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>Bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</p>
<p>0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Gibt den Prozentsatz der Zeit an, als sich der Anruf in einem Verlust Engpass Zustand befand.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Gibt den Prozentsatz des Anrufs an, in dem die Überlastung durch die verzögerte Ankunft von Netzwerkpaketen verursacht wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Gibt den Prozentsatz der Zeit an, als der Anruf um Netzwerkressourcen konkurrierte.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Minimaler Grad an Bandbreitenschätzung, der während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Maximale Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Standard Abweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Durchschnittliche Menge an Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, bei dem der Endpunkt festgestellt hat, dass die Netzwerkverbindung keine MultiView-Videounterstützung unterstützt.</p>
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
<td><p>int</p></td>
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
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>Decimal (9, 4)</p></td>
<td></td>
<td><p>Videpaketverlustrate.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Durchschnittliche für Video reservierte Bandbreite.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Fremd</p></td>
<td><p>Typ der Video Codecs, die vom Absender verwendet werden. Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vom Absender verwendete Auflösungsbreite.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vom Absender verwendete auflösungshöhe.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Durchschnittliche Übertragungsrate für Videoframes, die vom Absender verwendet wird.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Maximale Bitrate für den Absender.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Durchschnittliche Bitrate für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Maximale Anzahl der vom Absender verwendeten Videodatenströme.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Empfänger verwendete Video Codes. Weitere Informationen finden Sie <a href="lync-server-2013-codecdescription-table.md">in der CodecDescription-Tabelle in lync Server 2013</a> .</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Auflösung Breite, die vom Empfänger verwendet wird.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vom Empfänger verwendete auflösungshöhe.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Durchschnittliche Videobildrate, die vom Empfänger verwendet wird.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Maximale Bitrate für den Empfänger.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Durchschnittliche Bitrate für den Empfänger.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Maximale Anzahl von Videodatenströmen für den Empfänger.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Minimale Videodatenströme für den Empfänger.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Video Modus (beispielsweise Galerie oder einzelner Datenstrom) für den Empfänger.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Paketverlustrate, nachdem eine Vorwärts Fehlerkorrektur angewendet wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz der Zeit, die das Flag für dynamische Funktionen aktiv war.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char (9)</p></td>
<td></td>
<td><p>Minimale Auflösung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs unterhalb des Schwellenwerts mit niedriger Bitrate (70 Kbit/s).</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs unterhalb des Schwellenwerts für niedrige Frameraten (7,5 Frames pro Sekunde, eingehend).</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Prozentsatz des Anrufs, der bei der niedrigsten Auflösung aufgetreten ist.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>Gleitkommazahl</p></td>
<td></td>
<td><p>Die Dauer des Anrufs in Sekunden.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>Bit</p></td>
<td></td>
<td><p>Gibt an, ob die Daten aus mehreren Aufrufen aggregiert wurden.</p>
<p>Diese Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

