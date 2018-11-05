---
title: 'Lync Server 2013: VideoStream-Tabelle'
TOCTitle: VideoStream-Tabelle
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425928(v=OCS.15)
ms:contentKeyID: 49293823
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VideoStream-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz stellt einen Videostream dar. Eine Videomedienzeile enthält in der Regel zwei Videostreams.


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
<td><p>Verweis von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID innerhalb einer Medienzeile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>Fremd, Primär</p></td>
<td><p>Nutzlastbeschreibung. Weitere Informationen finden Sie in der <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription-Tabelle in Lync Server 2013</a>.</p></td>
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
<td><p>Maximaler Netzwerkjitter während der Videositzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Roundtripzeit aus RTCP-Statistik.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximale Roundtripzeit für den Videostream.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>Durchschnittliche Paketverlustrate während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal(5,4)</p></td>
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
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Bandbreitenschätzwerte für den Videostream.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char(9)</p></td>
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
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Empfangene Framerate des Videostreams.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Gesendete Framerate des Videostreams.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maximale Videobitrate während der Videositzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>Prozentsatz der gesamten verlorenen Videoframes.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Nicht verfügbar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p></p></td>
<td><p>Prozentsatz der gesamten verlorenen Videoframes.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz des Anrufs in CIF-Auflösung (Common Interchange Format).</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz des Anrufs in VGA-Auflösung.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz des Anrufs in HD720-Auflösung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Anrufdauer ohne Frame-Löschung.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Anrufdauer mit B-Frame-Löschung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Anrufdauer mit BP-Frame-Löschung.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Anrufdauer mit BPSP-Frame-Löschung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Anrufdauer mit BPSPI-Frame-Löschung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Streamdaten empfangen auf Empfängerseite.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Streamdaten empfangen auf Senderseite.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</p>
<p>0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gibt den Prozentsatz der Zeit an, während der sich der Anruf im Status &quot;Verlust durch Überlastung&quot; befunden hat.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gibt den Prozentsatz der Zeit des Anrufs an, während der eine Überlastung durch die verspätete Ankunft von Netzwerkpaketen verursacht wurde.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gibt den Prozentsatz der Zeit an, während der sich der Anruf im Wettbewerb um Netzwerkressourcen befunden hat.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Mindest-Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Höchste Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Standardabweichung der Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Bandbreitenschätzung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Prozentsatz des Anrufs, für den der Endpunkt festgelegt hat, dass die Netzwerkverbindung MultiView-Video nicht unterstützen kann.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p></p></td>
<td><p>Rate, bei der Videopakete verlorengingen.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Durchschnittliche reservierte Bandbreite für Videodaten</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Absender verwendeter Videocodec-Typ. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-codecdescription-table.md">CodecDescription-Tabelle in Lync Server 2013</a>.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Vom Absender verwendete Auflösungsbreite.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Vom Absender verwendete Auflösungshöhe.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Vom Absender verwendete durchschnittliche Videoframerate bei der Übertragung.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Maximale Bitrate des Absenders.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Bitrate des Absenders.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Maximale Anzahl der vom Absender verwendeten Videostreams.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Fremd</p></td>
<td><p>Vom Anrufempfänger verwendete Videocodecs. Weitere Informationen finden Sie in der <a href="lync-server-2013-codecdescription-table.md">CodecDescription-Tabelle in Lync Server 2013</a>.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Vom Anrufempfänger verwendete Auflösungsbreite.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Vom Anrufempfänger verwendete Auflösungshöhe.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Vom Anrufempfänger verwendete durchschnittliche Videoframerate.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Maximale Bitrate des Anrufempfängers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Bitrate des Anrufempfängers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Maximale Anzahl an Videostreams des Anrufempfängers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Minimale Anzahl an Videostreams des Anrufempfängers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Videomodus (z. B. Galerie oder einzelner Stream) des Anrufempfängers.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Paketverlustrate nach Anwendung der Vorwärtsfehlerkorrektur.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Prozentsatz der Zeit, während der das Kennzeichen für dynamische Funktionen aktiv war.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char(9)</p></td>
<td><p></p></td>
<td><p>Minimale Auflösung, die während des Anrufs gemessen wurde.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Prozentsatz des Anrufs, der unter dem Schwellenwert für geringe Bandbreite (70 KBit/s) lag.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Prozentsatz des Anrufs, der unter dem Schwellenwert für geringe Framerate (7,5 Frames pro Sekunde, eingehend) lag.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Prozentsatz des Anrufs bei geringster Auflösung.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Dauer des Anrufs in Sekunden.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Gibt an, ob die Daten aus mehreren Anrufen zusammengefasst wurden.</p>
<p>Diese Spalte wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

