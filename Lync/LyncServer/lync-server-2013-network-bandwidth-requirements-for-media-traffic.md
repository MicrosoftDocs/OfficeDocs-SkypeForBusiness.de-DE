---
title: Anforderungen an die Netzwerkbandbreite von lync Server 2013 für Mediendatenverkehr
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
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Anforderungen an die Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-09-24_

Ein wichtiger Bestandteil der Netzwerkplanung besteht darin, sicherzustellen, dass Ihr Netzwerk den von lync Server generierten Mediendatenverkehr verarbeiten kann. Dieser Abschnitt hilft Ihnen bei der Planung für diesen Mediendatenverkehr.

<div>

## <a name="media-traffic-network-usage"></a>Netzwerkauslastung des Medien Verkehrs

Aufgrund der Vielzahl an verschiedenen Faktoren, wie z. B. Codecverwendung, Auflösung und Aktivitätsgrad kann es schwierig sein, die Bandbreite für Mediendatenverkehr zu berechnen. Die Bandbreitennutzung ist eine Funktion des verwendeten Codecs und der Aktivität des Datenstroms, die beide zwischen Szenarien variieren. In der folgenden Tabelle sind die in lync Server 2013-Szenarien häufig verwendeten Audiocodecs aufgeführt.

### <a name="audio-codec-bandwidth"></a>Audiocodec-Bandbreite

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
<th>Bitrate für Audio-Nutzlast (Kbit/s)</th>
<th>Bandbreite für Audionutzlast und IP-Header (KBit/s)</th>
<th>Bandbreite für Audionutzlast, IP-Header, UDP, RTP und SRTP (KBit/s)</th>
<th>Bandbreite für Audionutzlast, IP-Header, UDP, RTP, SRTP und Vorwärtsfehlerkorrektur (KBit/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio, Breitband</p></td>
<td><p>Peer-to-Peer</p></td>
<td><p>29.0</p></td>
<td><p>45.0</p></td>
<td><p>57.0</p></td>
<td><p>86.0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio, Schmalband</p></td>
<td><p>Peer-to-Peer, PSTN</p></td>
<td><p>11.8</p></td>
<td><p>27.8</p></td>
<td><p>39.8</p></td>
<td><p>51.6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>Konferenzen</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G.722 Stereo</p></td>
<td><p>Peer-zu-Peer-Konferenzen</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>PSTN, Konferenzen</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>Konferenzen</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


Die Bandbreiten Nummern in der vorhergehenden Tabelle beruhen auf der 20ms-Paketierung (50-Pakete pro Sekunde) und für Siren und G. 722 den zusätzlichen, SRTP-Overhead (Secure Real-Time Transport Protocol) aus Konferenzszenarien und gehen davon aus, dass der Datenstrom 100% aktiv ist. Die Forward-Fehlerkorrektur (FEC) wird dynamisch verwendet, wenn auf dem Link Paketverlust vorhanden ist, um die Qualität des Audiostreams zu gewährleisten.

Die Stereo-Version des G. 722-Codecs wird von Systemen verwendet, die auf dem lync-Raum System basieren und die Stereo-Mikrofonaufnahme ermöglichen, damit die Hörer mehrere Gesprächspartner im Besprechungsraum besser unterscheiden können.

Für Video ist der Standard-Codec der H. 264/MPEG-4 Part 10 Advanced Video Coding Standard zusammen mit seinen skalierbaren Video Codierungs Erweiterungen für zeitliche Skalierbarkeit. Um die Interoperabilität mit lync 2010-oder Office Communicator 2007 R2-Clients aufrechtzuerhalten, wird der RTVideo-Codec weiterhin für Peer-to-Peer-Anrufe zwischen lync 2013 und Legacy-Clients verwendet. In Konferenzsitzungen mit lync 2013-und Legacy-Clients kann der lync 2013-Endpunkt das Video mit beiden Video-Codecs kodieren und den H. 264-Bitstream an lync 2013 und den RTVideo Bitstream an lync 2010-oder Office Communicator 2007 R2-Clients senden.

Die erforderliche Bandbreite hängt von der Auflösung, der Qualität und der Bildwiederholrate ab. Für jede Auflösung gibt es zwei interessante Bitraten:

  - **Maximale Nutzlast-Bitrate**   hierbei handelt es sich um die Bitrate, die ein lync 2013-Endpunkt für die Auflösung mit der für diese Auflösung unterstützten maximalen Frame Rate verwendet. Dieser Wert ist interessant, da er das Video mit der höchsten Qualität und Bildwiederholrate ermöglicht.

  - **Minimale Nutzlast-Bitrate**   Dies ist die Bitrate, unter der ein lync 2013-Endpunkt auf die nächst niedrigere Auflösung umgeschaltet wird. Um eine bestimmte Auflösung zu gewährleisten, darf die verfügbare Bitrate für Video Nutzlast nicht unter diese minimale Bitrate für diese Auflösung fallen. Dieser Wert ist interessant, damit Sie den niedrigsten möglichen Wert verstehen können, wenn die maximale Bitrate nicht verfügbar oder praktisch ist. Bei einigen Benutzern kann ein solches Video mit einer geringen Bitrate als nicht akzeptables Videoerlebnis angesehen werden, also seien Sie vorsichtig, wenn Sie diese Mindest-Video Nutzlast-Bitraten in Betracht ziehen. Beachten Sie, dass für Videoszenen mit wenig oder gar keiner Bewegung des Benutzers die tatsächliche Bitrate auch vorübergehend unter die minimale Bitrate fallen kann.

Lync 2013 unterstützt viele weitere Auflösungen. Auf diese Weise können Sie sich besser an die unterschiedliche Netzwerkbandbreite anpassen und die Clientfunktionen empfangen. Darüber hinaus wurde das standardmäßige Seitenverhältnis für lync 2013 in 16:9 geändert. Das 4:3-Seitenverhältnis wird weiterhin für Webcams unterstützt, bei denen die Aufnahme im 16:9-Seitenverhältnis nicht zulässig ist.

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
<th>Maximale Video Nutzlast-Bitrate (Kbit/s)</th>
<th>Minimale Bitrate für Video Nutzlast (Kbit/s)</th>
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


Video FEC ist in der Video Nutzlast-Bitrate enthalten, wenn es verwendet wird, sodass keine separaten Werte mit Video FEC und ohne Video FEC vorhanden sind.

Endpunkte übertragen Audio- oder Videopakete nicht in einem kontinuierlichen Stream. Für jedes Szenario gibt es unterschiedliche Aktivitätsebenen, die angeben, wie häufig Pakete für einen Stream gesendet werden. Die Aktivität eines Streams richtet sich nach dem Medium und dem Szenario, nicht jedoch nach dem verwendeten Codec. In einem Peer-to-Peer-Szenario gilt Folgendes:

  - Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

  - Beide Teilnehmer empfangen Audiostreams.

  - Wenn Video verwendet wird, senden und empfangen beide Endpunkte Videodatenströme während des gesamten Anrufs.

  - Bei Videoszenen mit wenig oder gar keiner Bewegung kann die tatsächliche Bitrate vorübergehend sehr gering sein, da der Videocodec die Codierungs Bereiche des Videos ohne Änderung überspringt.

In einem Konferenzszenario gilt Folgendes:

  - Endpunkte senden Audiostreams nur, wenn der Benutzer spricht.

  - Alle Teilnehmer empfangen Audiostreams.

  - Wenn Video verwendet wird, können alle Teilnehmer bis zu fünf Video-Streams empfangen und einen Panorama-Videostream (beispielsweise Seitenverhältnis 20:3) empfangen. Standardmäßig basieren die fünf empfangenen Videostreams auf dem aktiven Sprecher Verlauf, aber Benutzer können auch die Teilnehmer, aus denen Sie einen Videostream empfangen möchten, manuell auswählen.

  - Jeder Teilnehmer, der das Senden von Videostreams aktiviert, sendet einen oder mehrere Videostreams. Lync 2013 bietet die Möglichkeit, bis zu fünf Videodatenströme zu senden, um die Videoqualität für alle empfangenden Clients zu optimieren. Die tatsächliche Anzahl an gesendeten Videostreams wird vom Sender basierend auf CPU-Leistung, verfügbarer Uplink-Bandbreite und der Anzahl an Empfängerclients, die einen bestimmten Videostream angefordert haben, bestimmt. Üblicherweise wird ein H.264- und ein RTVideo-Stream gesendet, wenn ein Vorversions-Client an der Konferenz teilnimmt. Bei einem anderen typischen Szenario werden mehrere H.264-Videostreams (z. B. mit verschiedenen Auflösungen) gesendet, um verschiedenen Empfängeranforderungen gerecht zu werden.

Zusätzlich zu der Bandbreite, die für den RTP-Datenverkehr (Real-Time Transport Protocol) für Audio- und Videomedien erforderlich ist, wird auch Bandbreite für RTCP-Datenverkehr (Real-Time Transport Control Protocol) benötigt. RTCP wird zum Generieren von Statistiken und zur Out-of-Band-Steuerung des RTP-Streams genutzt. Verwenden Sie zur Planung die Bandbreitenangaben in der folgenden Tabelle für RTCP-Datenverkehr. Diese Werte stellen die maximale für RTCP verwendete Bandbreite dar und unterscheiden sich aufgrund von Unterschieden in den Steuerelementen zwischen Audio-und Videodatenströmen.

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
<td><p>10</p></td>
</tr>
<tr class="odd">
<td><p>Video (H.264 und RTVideo werden gesendet/empfangen)</p></td>
<td><p>15</p></td>
</tr>
</tbody>
</table>


Zur Kapazitätsplanung sind die folgenden beiden Bandbreiten von Interesse:

  - **Maximale Bandbreite ohne FEC**   die maximale Bandbreite, die ein Datenstrom verbraucht, einschließlich der typischen Aktivität des Datenstroms und des typischen Codecs, der im Szenario ohne FEC verwendet wird.Hierbei handelt es sich um die Bandbreite, wenn sich der Datenstrom bei einer Aktivität von 100% befindet und kein Paketverlust die Verwendung von FEC auslöst.Dies ist interessant für die Berechnung, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann. 

  - **Maximale Bandbreite mit FEC**   die maximale Bandbreite, die ein Datenstrom beansprucht, einschließlich der typischen Aktivität des Datenstroms und des typischen Codecs, der im Szenario mit FEC verwendet wird. Hierbei handelt es sich um die Bandbreite, wenn sich der Datenstrom bei einer Aktivität von 100% befindet und ein Paketverlust die Verwendung von FEC zur Verbesserung der Qualität auslöst. Dies ist für die Berechnung interessant, wie viel Bandbreite zugewiesen werden muss, damit der Codec in einem bestimmten Szenario verwendet werden kann, und die Verwendung von FEC, um die Qualität unter Paketverlust Bedingungen zu gewährleisten. 

In den folgenden Tabellen wird auch ein zusätzlicher Bandbreitenwert, **typische Bandbreite**, aufgeführt. Hierbei handelt es sich um die durchschnittliche Bandbreite, die ein Datenstrom beansprucht, einschließlich der typischen Aktivität des Datenstroms und des typischen Codecs, der im Szenario verwendet wird. Diese Bandbreite kann verwendet werden, um zu ermitteln, wie viel Bandbreite zu einem bestimmten Zeitpunkt vom Mediendatenverkehr beansprucht wird, aber nicht für die Kapazitätsplanung verwendet werden sollte, da einzelne Anrufe diesen Wert überschreiten, wenn die Aktivitätsstufe höher als der Durchschnitt ist. Die typische Videostream-Bandbreite in den nachfolgenden Tabellen basiert auf einer Kombination verschiedener Videoauflösungen, wie Sie in gemessenen Kundendaten beobachtet werden. In Peer-zu-Peer-Sitzungen würde die Mehrheit der Benutzer beispielsweise das standardmäßige videowiedergabefenster verwenden, während einige Prozent der Benutzer die lync-Anwendung erhöhen oder maximieren, um höhere Videoauflösungen zu ermöglichen.

In den folgenden Tabellen werden diese drei Bandbreitenwerte für die verschiedenen Szenarien bereitgestellt.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Planen der Audio/Videokapazität für Peer-to-Peer-Sitzungen

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
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>RTAudio, Schmalband</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>Hauptvideo beim Aufrufen von lync 2013-Endpunkten</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (für eine maximale Auflösung von 1920x1080)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Hauptvideo beim Aufrufen von lync 2010-oder Office Communicator 2007 R2-Endpunkten</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (für eine maximale Auflösung von 1280x720)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Panorama Video beim Aufrufen von lync 2013-Endpunkten</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (für eine maximale Auflösung von 1920x288)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Panorama Video beim Aufrufen von lync 2010-oder Office Communicator 2007 R2-Endpunkten</p></td>
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
<td><p>G.722</p></td>
<td><p>46.1</p></td>
<td><p>100.6</p></td>
<td><p>164.6</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Siren</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>Hauptvideo, Empfang</p></td>
<td><p>H. 264 und/oder RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Hauptvideo, Senden</p></td>
<td><p>H. 264 und/oder RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Panoramavideo, Empfang</p></td>
<td><p>H. 264 und/oder RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (für eine maximale Auflösung von 1920x288)</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Panoramavideo, Senden</p></td>
<td><p>H. 264 und/oder RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (für das Senden von Bitstreams mit mehreren Auflösungen/Codecs</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
</tbody>
</table>


Für das Hauptvideo ist die typische und maximale Datenstrom Bandbreite die aggregierte Bandbreite über alle empfangenen Videostreams und über alle Videodatenströme senden. Auch bei mehreren Videostreams ist die typische Videobandbreite kleiner als im Peer-to-Peer-Szenario, da viele Videokonferenzen die Inhaltsfreigabe verwenden, die zu wesentlich kleineren Videofenstern und damit zu kleineren Videoauflösungen führt. Die maximal unterstützte Gesamtbandbreite für aggregierte Video Nutzlast beträgt 8000 kBit/s für sowohl Sende-als auch Empfangsdaten Ströme, die beispielsweise verwendet werden, wenn es zwei eingehende 1920x1080p-Videostreams gibt.

Die typische Datenstrom Bandbreite für Panorama Video basiert auf derzeit verfügbaren Geräten, die nur bis zu 960x144 Panorama Video streamen. Sobald Geräte mit 1920x288-Panorama Video verfügbar werden, wird die typische Datenstrom Bandbreite erwartet.

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
<td><p>G. 711 (Dies umfasst PSTN-Teilnehmer in Konferenzen)</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>RTAudio, Schmalband</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


Die Angaben zur Netzwerkbandbreite in diesen Tabellen gelten nur für unidirektionalen Datenverkehr und beinhalten 5 KBit/s für RTCP-Overhead pro Stream. Für Video wird die maximale Video-Bitrate für die Berechnung des maximalen Datenstroms verwendet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

