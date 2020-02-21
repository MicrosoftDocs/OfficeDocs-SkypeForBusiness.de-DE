---
title: Lync Server 2013 Anforderungen an die Netzwerkbandbreite für den Mediendatenverkehr
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a89517fb83fa5cd0c7defd62b47f7ddf9b29a303
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Anforderungen an die Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-09-24_

Bei der Netzwerkplanung ist es besonders wichtig sicherzustellen, dass Ihr Netzwerk den von Lync Server generierten Mediendatenverkehr verarbeiten kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr.

<div>

## <a name="media-traffic-network-usage"></a>Netzwerkbelegung durch Mediendatenverkehr

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung wird durch den verwendeten Codec und die Streamaktivität bestimmt, und beide Faktoren können in unterschiedlichen Szenarien variieren. In der folgenden Tabelle sind die Audiocodecs aufgeführt, die häufig in lync Server 2013 Szenarien verwendet werden.

### <a name="audio-codec-bandwidth"></a>Bandbreite für Audiocodec

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
<td><p>Peer-to-Peer</p></td>
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
<td><p>G. 722</p></td>
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
<td><p>G. 711</p></td>
<td><p>PSTN, Konferenzen</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Sirene</p></td>
<td><p>Konferenzen</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


Die Bandbreitenangaben in dieser Tabelle basieren auf einer Paketierung mit 20 ms (50 Pakete pro Sekunde), für Siren und G.722, einschließlich SRTP-Overhead (Secure Real-Time Transport Protocol) aus Konferenzszenarien, und setzen voraus, dass der Stream zu 100% aktiv ist. Die Vorwärtsfehlerkorrektur (Forward Error Correction, FEC) wird dynamisch eingesetzt, um bei einem Paketverlust in der Verbindung die Qualität des Audiostreams zu erhalten.

Die Stereo-Version des G. 722-Codecs wird von Systemen verwendet, die auf dem lync-Raum System basieren, wodurch die Aufzeichnung von Stereomikrofonen ermöglicht wird, um mehrere sprechende im Besprechungsraum besser voneinander unterscheiden zu können.

Videodaten werden standardmäßig mit dem H.264/MPEG-4 Part 10 Advanced Video Coding zusammen mit den entsprechenden skalierbaren Erweiterungen für eine temporäre Skalierbarkeit codiert. Um die Interoperabilität mit lync 2010-oder Office Communicator 2007 R2-Clients aufrechtzuerhalten, wird der RTVideo-Codec weiterhin für Peer-to-Peer-Anrufe zwischen lync 2013-und Legacyclients verwendet. In Konferenzsitzungen mit lync 2013-und Legacyclients kann der lync 2013 Endpunkt das Video mit beiden Videocodecs codieren und die H. 264-Bitstream an den lync 2013 und das RTVideo Bitstream an lync 2010 oder Office Communicator 2007 R2 Clients senden.

Die erforderliche Bandbreite richtet sich nach der Auflösung, Qualität und Framerate. Bei jeder Auflösung sind zwei Bitraten von Interesse:

  - **Bitrate für maximale Nutzlast**   Dies ist die Bitrate, die ein lync 2013 Endpunkt für die Auflösung mit der für diese Lösung unterstützten maximalen Frame Rate verwendet wird. Dieser Wert ist von Interesse, da er die Übertragung von Videodaten mit höchster Qualität und maximaler Framerate ermöglicht.

  - **Bitrate für minimale Nutzlast**   Dies ist die Bitrate, unter der ein lync 2013-Endpunkt auf die nächst niedrigere Auflösung umgeschaltet wird. Um eine bestimmte Auflösung zu gewährleisten, darf die verfügbare Videonutzlast-Bitrate nicht unter diese minimale Bitrate für die jeweilige Auflösung absinken. Diese Zahl ist von Interesse, da sie für Fälle, in denen die maximale Bitrate nicht verfügbar oder sinnvoll ist, den geringstmöglichen Wert angibt. Bedenken Sie jedoch bei Verwendung dieser Bitraten, dass für einige Benutzer eine derart niedrige Videoübertragungsrate möglicherweise nicht akzeptabel ist. Beachten Sie, dass die tatsächliche Bitrate bei Videoszenen mit nur wenigen oder keinen Bewegungen des Benutzers ebenfalls kurzfristig unter die minimale Bitrate absinken kann.

Lync 2013 unterstützt viele weitere Auflösungen. Auf diese Weise bestehen bessere Anpassungsmöglichkeiten an verschiedene Netzwerkbandbreiten und Kapazitäten von Empfängerclients. Darüber hinaus wurde das standardmäßige Seitenverhältnis für lync 2013 zu 16:9 geändert. Das Seitenverhältnis 4:3 wird weiterhin für Webcams unterstützt, die keine Aufnahmen im Seitenverhältnis 16:9 erlauben.

### <a name="video-resolution-bandwidth"></a>Bandbreite für Videoauflösung

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
<td><p>H. 264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>424 x 240 (16:9))</p>
<p>320X240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>640 x 360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>1280X720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
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

  - Jeder Teilnehmer, der das Senden von Videostreams aktiviert, sendet einen oder mehrere Videostreams. Lync 2013 die Möglichkeit, bis zu fünf Videostreams zu senden, um die Videoqualität für alle empfangenden Clients zu optimieren. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein älterer Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden.

Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale Bandbreite für RTCP dar und variieren aufgrund der Unterschiede in den Steuerungsdaten bei Audio- und Videostreams.

### <a name="rtcp-bandwidth"></a>RTCP-Bandbreite

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
<td><p>10 </p></td>
</tr>
<tr class="odd">
<td><p>Video (H.264 und RTVideo werden gesendet/empfangen)</p></td>
<td><p>15 </p></td>
</tr>
</tbody>
</table>


Für die Kapazitätsplanung sind die folgenden beiden Bandbreiten von Interesse:

  - **Maximale Bandbreite ohne FEC**   die maximale Bandbreite, die ein Datenstrom verbraucht, einschließlich der typischen Aktivität des Streams und des typischen Codecs, der im Szenario ohne FEC verwendet wird.Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und kein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur auslöst.Diese Angaben sind nützlich, um die für den Codec in einem bestimmten Szenario erforderliche Bandbreite zu berechnen. 

  - **Maximale Bandbreite mit FEC**   die maximale Bandbreite, die ein Datenstrom benötigt, einschließlich der typischen Aktivität des Streams und des typischen Codecs, der im Szenario mit FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, die benötigt wird, wenn die Streamaktivität bei 100 % liegt und ein Paketverlust auftritt, der eine Vorwärtsfehlerkorrektur zur Verbesserung der Qualität auslöst. Diese Angaben sind nützlich, um die Bandbreite zu berechnen, die für den Codec in einem bestimmten Szenario erforderlich ist und die Verwendung der Vorwärtsfehlerkorrektur zur Qualitätssicherung bei Paketverlusten ermöglicht. 

Die folgende Tabelle listet auch einen zusätzlichen Bandbreitenwert, **typische Bandbreite**. Dies ist die durchschnittliche Bandbreite, die ein Datenstrom benötigt, einschließlich der typischen Aktivität des Streams und des typischen Codecs, der im Szenario verwendet wird. Diese Bandbreite kann verwendet werden, um zu erreichen, wie viel Bandbreite zu einem bestimmten Zeitpunkt vom Mediendatenverkehr verbraucht wird, aber nicht für die Kapazitätsplanung verwendet werden sollte, da einzelne Anrufe diesen Wert überschreiten, wenn die Aktivitätsebene höher als der Durchschnitt ist. Die typische Bandbreite der Videodatenströme in den folgenden Tabellen basiert auf einer Kombination verschiedener Videoauflösungen, die in den gemessenen Kundendaten beobachtet werden. In Peer-to-Peer-Sitzungen würde die Mehrzahl der Benutzer beispielsweise das standardmäßige Video Renderfenster verwenden, während ein Teil der Benutzer die lync-Anwendung erhöhen oder maximieren würde, um höhere Videoauflösungen zuzulassen.

In den folgenden Tabellen finden Sie diese drei Bandbreitenwerte für die verschiedenen Szenarien.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Planen der Audio/Videokapazität für Peer-zu-Peer-Sitzungen

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
<td><p>Hauptvideo beim Aufruf lync 2013 Endpunkten</p></td>
<td><p>H. 264</p></td>
<td><p>460</p></td>
<td><p>4010 (für eine maximale Auflösung von 1920x1080)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Hauptvideo beim Aufruf von lync 2010 oder Office Communicator 2007 R2 Endpunkten</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (für eine maximale Auflösung von 1280x720)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Panorama Video beim Aufruf lync 2013 Endpunkten</p></td>
<td><p>H. 264</p></td>
<td><p>190</p></td>
<td><p>2010 (für eine maximale Auflösung von 1920x288)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Panorama Video beim Aufruf von lync 2010 oder Office Communicator 2007 R2 Endpunkten</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (für eine maximale Auflösung von 960x144)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>Planen der Audio-/Videokapazität für Konferenzen

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
<td><p>G. 722</p></td>
<td><p>46,1</p></td>
<td><p>100,6</p></td>
<td><p>164,6</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Sirene</p></td>
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

### <a name="audio-capacity-planning-for-pstn"></a>Planen der Audiokapazität für PSTN

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
<td><p>G. 711 (Dies umfasst PSTN-Teilnehmer an Konferenzen)</p></td>
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

</div>

</div>

<span> </span>

</div>

</div>

</div>

