---
title: AppSharingStream-Tabelle
TOCTitle: AppSharingStream-Tabelle
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204808(v=OCS.15)
ms:contentKeyID: 49293702
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AppSharingStream-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Tabelle **AppSharingStream** enthält QoE-Metriken (Quality of Experience) für die Netzwerkdatenströme, die bei der Anwendungsfreigabe verwendet werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p>dateTime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Datum und Uhrzeit des Sitzungsbeginns.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Sequenzielle ID, anhand der zwischen Sitzungen unterschieden wird, die an denselben Tag und zur derselben Uhrzeit gestartet wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Stellt den Typ der im Anruf verwendeten Videoleitung dar. Gültige Werte sind:</p>
<ul>
<li><p>0 – Audio</p></li>
<li><p>1 – Video</p></li>
<li><p>2 – Panoramavideo</p></li>
<li><p>3 – Anwendungs-/Desktopfreigabe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutige ID des Anwendungsfreigabe-Datenstroms.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das &quot;Zittern&quot; der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Der maximale Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das &quot;Zittern&quot; der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Die maximale Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Die maximale Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Die Anzahl der gesendeten Pakete.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Die geschätzte unidirektionale Bandbreite, die am Ende der Sitzung verfügbar ist (in Bits pro Sekunde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Beschreibung der Anwendungsfreigabe-Nutzlast.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Undirektionale Burstvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Undirektionale Burstdichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Undirektionale Burstdauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Undirektionale Lückenvorkommen insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Undirektionale Lückendichte insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Undirektionale Lückendauer insgesamt. Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden. Die Lücken kennzeichnen die Verzögerungen zwischen diesen Bursts. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar(256)</p></td>
<td><p></p></td>
<td><p>Anwendungsrolle (Freigebender Benutzer oder Betrachter) und Inhaltstyp.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gesamte Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximale Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Eine Übertragung mit Bursts ist eine Übertragung, bei der Daten in unvorhersehbaren Datenblöcken anstatt in einem regelmäßigen Datenstrom übertragen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je geringer die Lückendichte, desto besser das Wiedergabeerlebnis.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je kürzer die Lückendauer, desto besser das Wiedergabeerlebnis.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gesamtrate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximale Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gesamtprozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittlicher Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximaler Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Gesamtanzahl der Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Anzahl der Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximale Anzahl der Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen in den Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte in den Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer in den Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen in den Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte in den Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer in den Scrapingframes aus der Grafikquelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Rate eingehender Kacheln, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Rate ausgehender Kacheln insgesamt für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximale Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen in der Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte in der Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer in der Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen in der Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte in der Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer in der Rate ausgehender Kacheln für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Rate ausgehender Frames insgesamt für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Maximale Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Burstvorkommen in der Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdichte in der Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Burstdauer in der Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Lückenvorkommen in der Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendichte in der Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>Lückendauer in der Rate ausgehender Frames für den Absender.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Höhe der Videoauflösung in Pixeln.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Breite der Videoauflösung in Pixeln.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Framerate (in Frames pro Sekunde) für eingehende Übertragungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Durchschnittliche Framerate (in Frames pro Sekunde) für ausgehende Übertragungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.</p>
<p>0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.</p></td>
</tr>
</tbody>
</table>

