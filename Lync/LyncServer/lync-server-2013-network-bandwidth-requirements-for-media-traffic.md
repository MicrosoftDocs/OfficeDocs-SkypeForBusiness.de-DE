---
title: Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr
TOCTitle: Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49890820
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr

 

_**Letztes Änderungsdatum des Themas:** 2015-09-24_

Bei der Netzwerkplanung ist es besonders wichtig sicherzustellen, dass Ihr Netzwerk den von Lync Server generierten Mediendatenverkehr verarbeiten kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr.

## Netzwerkbelegung durch Mediendatenverkehr

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung wird durch den verwendeten Codec und die Streamaktivität bestimmt, und beide Faktoren können in unterschiedlichen Szenarien variieren. In der folgenden Tabelle werden die in den Lync Server 2013-Szenarien typischerweise verwendeten Audiocodecs aufgeführt.

### Bandbreite für Audiocodec

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Audiocodec</th>
<th>Szenarien</th>
<th>Bitrate der Audionutzlast (KBit/s)</th>
<th>Bandbreite für Audionutzlast und IP-Header (KBit/s)</th>
<th>Bandbreite für Audionutzlast, IP-Header, UDP, RTP und SRTP (KBit/s)</th>
<th>Bandbreite für Audionutzlast, IP-Header, UDP, RTP, SRTP und Vorwärtsfehlerkorrektur (KBit/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio, Breitband</p></td>
<td><p>Peer-zu-Peer</p></td>
<td><p>29,0</p></td>
<td><p>45,0</p></td>
<td><p>57,0</p></td>
<td><p>86,0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio, Schmalband</p></td>
<td><p>Peer-zu-Peer, PSTN</p></td>
<td><p>11,8</p></td>
<td><p>27,8</p></td>
<td><p>39,8</p></td>
<td><p>51,6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>Konferenzen</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>G.722, Stereo</p></td>
<td><p>Peer-zu-Peer, Konferenzen</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>Telefonfestnetz (PSTN)</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>Konferenzen</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


Die Bandbreitenangaben in dieser Tabelle basieren auf einer Paketierung mit 20 ms (50 Pakete pro Sekunde), für Siren und G.722, einschließlich SRTP-Overhead (Secure Real-Time Transport Protocol) aus Konferenzszenarien, und setzen voraus, dass der Stream zu 100% aktiv ist. Die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) wird dynamisch eingesetzt, um bei einem Paketverlust in der Verbindung die Qualität des Audiostreams zu erhalten.

Die Stereoversion des G.722-Codec wird von Systemen verwendet, die auf der Lync-Raumsystem basieren. Auf diese Weise können Mikrofonaufnahmen in Stereoqualität vorgenommen werden, damit Zuhörer die unterschiedlichen Personen im Besprechungsraum besser voneinander unterscheiden können.

Videodaten werden standardmäßig mit dem H.264/MPEG-4 Part 10 Advanced Video Coding zusammen mit den entsprechenden skalierbaren Erweiterungen für eine temporäre Skalierbarkeit codiert. Um die Interoperabilität mit Lync 2010- oder Office Communicator 2007 R2-Clients sicherzustellen, wird der RTVideo-Codec noch immer für Peer-zu-Peer-Anrufe zwischen Lync 2013- und älteren Clients verwendet. In Konferenzsitzungen mit beiden, Lync 2013 und älteren Clients, kann der Lync 2013-Endpunkt das Video mit beiden Videocodecs codieren und den H.264-Bitstream an den Lync 2013-Client und den RTVideo-Bitstream an den Lync 2010- oder Office Communicator 2007 R2-Client senden.

Die erforderliche Bandbreite richtet sich nach der Auflösung, Qualität und Framerate. Bei jeder Auflösung sind zwei Bitraten von Interesse:

  - **Bitrate bei maximaler Nutzlast**   Diese Bitrate wird vom Lync 2013-Endpunkt zur Auflösung mit der maximal unterstützten Framerate für die jeweilige Auflösung eingesetzt. Dieser Wert ist von Interesse, da er die Übertragung von Videodaten mit höchster Qualität und maximaler Framerate ermöglicht.

  - **Bitrate bei minimaler Nutzlast**   Unterhalb dieser Bitrate wechselt der Lync 2013-Endpunkt zur nächstgeringeren Auflösung. Um eine bestimmte Auflösung zu gewährleisten, darf die verfügbare Videonutzlast-Bitrate nicht unter diese minimale Bitrate für die jeweilige Auflösung absinken. Diese Zahl ist von Interesse, da sie für Fälle, in denen die maximale Bitrate nicht verfügbar oder sinnvoll ist, den geringstmöglichen Wert angibt. Bedenken Sie jedoch bei Verwendung dieser Bitraten, dass für einige Benutzer eine derart niedrige Videoübertragungsrate möglicherweise nicht akzeptabel ist. Beachten Sie, dass die tatsächliche Bitrate bei Videoszenen mit nur wenigen oder keinen Bewegungen des Benutzers ebenfalls kurzfristig unter die minimale Bitrate absinken kann.

Lync 2013 bietet Unterstützung für viele Auflösungen. Auf diese Weise bestehen bessere Anpassungsmöglichkeiten an verschiedene Netzwerkbandbreiten und Kapazitäten von Empfängerclients. Außerdem wurde das standardmäßige Seitenverhältnis für Lync 2013 in 16:9 geändert. Das Seitenverhältnis 4:3 wird weiterhin für Webcams unterstützt, die keine Aufnahmen im Seitenverhältnis 16:9 erlauben.

### Bandbreite für Videoauflösung

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Videocodec</th>
<th>Auflösung und Seitenverhältnis</th>
<th>Bitrate bei maximaler Videonutzlast (KBit/s)</th>
<th>Bitrate bei minimaler Videonutzlast (KBit/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Wenn die Vorwärtsfehlerkorrektur eingesetzt wird, ist sie in der Videonutzlast enthalten, daher sind keine unterschiedlichen Werte mit und ohne Video-FEC vorhanden.

Endpunkte übertragen Audio- oder Videopakete nicht in einem kontinuierlichen Stream. Für jedes Szenario gibt es unterschiedliche Aktivitätsebenen, die angeben, wie häufig Pakete für einen Stream gesendet werden. Die Aktivität eines Streams richtet sich nach dem Medium und dem Szenario, nicht jedoch nach dem verwendeten Codec. In einem Peer-zu-Peer-Szenario gilt Folgendes:

  - Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

  - Beide Teilnehmer empfangen Audiostreams.

  - Wenn Videodaten übertragen werden, senden und empfangen beide Endpunkte Videostreams während der gesamten Kommunikation.

  - In Videoszenen mit wenigen oder gar keinen Bewegungen kann die tatsächliche Bitrate kurzfristig sehr gering sein, da der Videocodec die Codierung von Bereichen des Videos, in denen keine Änderungen auftreten, überspringt.

In einem Konferenzszenario gilt Folgendes:

  - Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

  - Alle Teilnehmer empfangen Audiostreams.

  - Bei der Verwendung von Video können alle Teilnehmer bis zu fünf Videostreams und ein Panoramavideo (z. B. mit einem Seitenverhältnis von 20:3) empfangen. Standardmäßig basieren die fünf Videostreams auf dem Verlauf aktiver Sprecher. Die Benutzer können jedoch die Teilnehmer auswählen, von denen sie einen Videostream empfangen möchten.

  - Jeder Teilnehmer, der das Senden von Videostreams aktiviert, sendet einen oder mehrere Videostreams. Lync 2013 bietet die Möglichkeit, bis zu fünf Videostreams zu senden, um die Videoqualität für alle Empfängerclients zu optimieren. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein älterer Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden.

Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale Bandbreite für RTCP dar und variieren aufgrund der Unterschiede in den Steuerungsdaten bei Audio- und Videostreams.

### RTCP-Bandbreite

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Medien</th>
<th>Maximale RTCP-Bandbreite (KBit/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>Video (es wird nur H.264 oder RTVideo gesendet/empfangen)</p></td>
<td><p>10</p></td>
</tr>
<tr class="odd">
<td><p>Video (H.264 und RTVideo werden gesendet/empfangen)</p></td>
<td><p>15</p></td>
</tr>
</tbody>
</table>


Für die Kapazitätsplanung sind die folgenden beiden Bandbreiten von Interesse:

  - **Maximale Bandbreite ohne FEC**   Die maximale Bandbreite, die ein Stream nutzt, einschließlich der typischen Aktivität des Streams und des in diesem Szenario verwendeten typischen Codecs ohne FEC. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und kein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur auslöst. Diese Angaben sind nützlich, um die für den Codec in einem bestimmten Szenario erforderliche Bandbreite zu berechnen.

  - **Maximale Bandbreite mit FEC**   Die maximale Bandbreite, die ein Stream nutzt, einschließlich der typischen Aktivität des Streams und des in diesem Szenario verwendeten typischen Codecs ohne FEC. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und ein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur zur Verbesserung der Qualität auslöst. Diese Angaben sind nützlich, um die Bandbreite zu berechnen, die für den Codec in einem bestimmten Szenario erforderlich ist und die Verwendung der Vorwärtsfehlerkorrektur zur Qualitätssicherung bei Paketverlusten ermöglicht.

In den folgenden Tabellen wird ein weiterer Bandbreitenwert aufgeführt, die **typische Bandbreite**. Hierbei handelt es sich um die durchschnittliche Bandbreite, die ein Stream benötigt, einschließlich der typischen Aktivität des Streams und dem typischen Codec für das Szenario. Anhand dieser Bandbreite können Sie ungefähr berechnen, wie viel Bandbreite zu einer bestimmten Zeit durch den Mediendatenverkehr genutzt wird. Verwenden Sie diesen Wert jedoch nicht zur Kapazitätsplanung, da einzelne Anrufe diese Bandbreite überschreiten, wenn die Aktivitätsebene über dem Durchschnitt liegt. Die typische Bandbreite für Videostreams in den nachfolgenden Tabellen basieren auf einer Mischung an verschiedenen Videoauflösungen, wie sie in gemessenen Kundendaten beobachtet wurden. In Peer-zu-Peer-Sitzungen nutzt der Großteil der Benutzer beispielsweise das standardmäßige Fenster zum Rendern von Videos, und nur ein kleiner Prozentsatz von Benutzern vergrößert oder maximiert die Lync-Anwendung, um höhere Videoauflösungen zu erlauben.

In den folgenden Tabellen finden Sie diese drei Bandbreitenwerte für die verschiedenen Szenarien.

### Planen der Audio/Videokapazität für Peer-zu-Peer-Sitzungen

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Medien</th>
<th>Codec</th>
<th>Typische Streambandbreite (KBit/s)</th>
<th>Maximale Streambandbreite ohne FEC</th>
<th>Maximale Streambandbreite mit FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>RTAudio, Breitband</p></td>
<td><p>39,8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>RTAudio, Schmalband</p></td>
<td><p>29,3</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
<tr class="odd">
<td><p>Hauptvideo beim Aufruf von Lync 2013-Endpunkten</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (für eine maximale Auflösung von 1920x1080)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Hauptvideo beim Aufruf von Lync 2010- oder Office Communicator 2007 R2-Endpunkten</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (für eine maximale Auflösung von 1280x720)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Panoramavideo beim Aufruf von Lync 2013-Endpunkten</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (für eine maximale Auflösung von 1920x288)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Panoramavideo beim Aufruf von Lync 2010- oder Office Communicator 2007 R2-Endpunkten</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (für eine maximale Auflösung von 960x144)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>


### Planen der Audio-/Videokapazität für Konferenzen

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Medien</th>
<th>Typischer Codec</th>
<th>Typische Streambandbreite (KBit/s)</th>
<th>Maximale Streambandbreite ohne FEC</th>
<th>Maximale Streambandbreite mit FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G.722</p></td>
<td><p>46,1</p></td>
<td><p>100,6</p></td>
<td><p>164,6</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Siren</p></td>
<td><p>25,5</p></td>
<td><p>52,6</p></td>
<td><p>68,6</p></td>
</tr>
<tr class="odd">
<td><p>Hauptvideo, Empfang</p></td>
<td><p>H.264 und/oder RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Hauptvideo, Senden</p></td>
<td><p>H.264 und/oder RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Panoramavideo, Empfang</p></td>
<td><p>H.264 und/oder RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (für eine maximale Auflösung von 1920x288)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Panoramavideo, Senden</p></td>
<td><p>H.264 und/oder RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (zum Senden von Bitstreams mit mehreren Auflösungen/Codecs)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>


Für das Hauptvideo besteht die typische und maximale Streambandbreite aus der aggregierten Bandbreite aller empfangenen bzw. gesendeten Videostreams. Selbst mit mehreren Videostreams ist die typische Videobandbreite kleiner als im Peer-zu-Peer-Szenario, da viele Videokonferenzen die Inhaltsfreigabe nutzen, wobei wesentlich kleinere Videofenster und somit auch niedrigere Videoauflösungen verwendet werden. Die maximal unterstützte aggregierte Bandbreite der Videonutzlast liegt bei 8000 KBit/s für das Senden und Empfangen von Streams, die zum Beispiel beim Empfang von zwei Streams mit je 1920x1080 zum Einsatz käme.

Die typische Streambandbreite für Panoramavideos basiert auf den aktuell verfügbaren Geräten, die nur Panoramavideos mit bis zu 960x144 streamen. Erst wenn Panoramavideos mit 1920x288 verfügbar sind, sollte sich die typische Bandbreite erhöhen.

### Planen der Audiokapazität für PSTN

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Medien</th>
<th>Typischer Codec</th>
<th>Typische Streambandbreite (KBit/s)</th>
<th>Maximale Streambandbreite ohne FEC</th>
<th>Maximale Streambandbreite mit FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G.711</p></td>
<td><p>64,8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>RTAudio, Schmalband</p></td>
<td><p>30,9</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
</tbody>
</table>


Die Angaben zur Netzwerkbandbreite in diesen Tabellen gelten nur für unidirektionalen Datenverkehr und beinhalten 5 KBit/s für RTCP-Overhead pro Stream. Bei Videodaten wird zur Berechnung des maximalen Streams die maximale Videobitrate verwendet.

