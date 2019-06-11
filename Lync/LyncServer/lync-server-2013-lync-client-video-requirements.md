---
title: 'Lync Server 2013: Anforderungen für lync-Client Video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Video Anforderungen für lync-Clients für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-01-29_

In diesem Abschnitt wird die Videohardware Unterstützung für lync 2013-Videoanrufe beschrieben und es wird beschrieben, wie Sie die erwartete Videoqualität für verschiedene Computer-, Tablet-und Mobile Gerätekonfigurationen ermitteln können.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Anforderungen und Funktionen für Windows-Desktop-und-Tablet-Video

Lync 2013 führt die Hardwarebeschleunigung für die Videocodierung und-Decodierung auf Grundlage des H. 264/MPEG-4 Part 10 Advanced Video Coding Standard ein. Diese Funktion sorgt dafür, dass auch Computer mit geringeren CPU-Taktgeschwindigkeiten höher auflösende Videos codieren und decodieren können. Die Anforderungen an die Videohardware hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.

<div>

## <a name="video-hardware-requirements"></a>Hardware Anforderungen für Video


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Feature</th>
<th>Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hardwarebeschleunigte H.264-Decodierung mit DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>Die Grafikkarte muss DirectX 9.0 unterstützen und den Decodierungsmodus DXVA2_ModeH264_VLD_NoFGT beherrschen.</p></li>
<li><p>Der aktuellste Grafikkartentreiber muss installiert sein.</p></li>
</ul>
<div>

> [!NOTE]  
> Details zu den Decodierungs Modi finden <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>Sie unter.


</div></td>
</tr>
<tr class="even">
<td><p>Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen</p></td>
<td><p>Folgende hardwarebeschleunigte Videocodierungslösungen von Intel werden unterstützt:</p>
<ul>
<li><p>Intel HD-Grafik 2000, 2500, 3000 und 4000-Chipsätze (oder neuere Versionen) der zweiten und dritten Generation mit integrierten Hardware-Video-Encoder. Die Installation des Intel HD Graphics-Treibers 15.28.9.2884 oder des aktuellsten Treibers, der Folgendes enthält, ist erforderlich:</p>
<ul>
<li><p>Grafiktreiber 9.17.10.2884 oder der aktuellster Treiber</p></li>
<li><p>HMFT (Hardware Media Foundation Transform), Version 3.12.10.31, oder der neueste HMFT</p></li>
</ul></li>
</ul>
<p>Die folgenden AMD Hardware Accelerated Video Encoding-Lösungen werden unterstützt (erfordert CU1-Updates für lync Server 2013):</p>
<ul>
<li><p>AMD Video Codec Engine, die in einer Reihe diskreter Grafikkarten sowie in integrierten hardwarebeschleunigten CPUs der beschleunigten Prozessoren der Serie AMD A verfügbar ist. Der AMD Video Codec Engine-Treiber 9.12.0.0 oder höher muss installiert sein.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen</p></td>
<td><p>USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 unterstützt UVC 1,5-Kameras mit Windows 8 oder Windows 8,1, einschließlich Unterstützung für UVC 1,5. Da Windows 7 keine Unterstützung für UVC 1,5 enthält, behandelt lync 2013 UVC 1,5-Kameras als normale Kameras ohne Unterstützung für die Hardware Codierung.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Ermitteln von H. 264-Video Codierungs-und-Decodierungsfunktionen

In der Regel werden die maximalen Codierungs- und Decodierungsmöglichkeiten einer konkreten Computerkonfiguration durch vier Hauptfaktoren bestimmt:

  - Unterstützung einer hardwarebeschleunigten Decodierung mittels DXVA

  - Unterstützung einer hardwarebeschleunigten Codierung

  - Anzahl der physischen Kerne

  - Windows Experience Index (WEI)

Das Windows System Assessment Tool (WinSAT) ermittelt den WEI-Wert. Wenn Sie das WinSAT-Tool ausführen, wird auf dem Computer im\\\\WinSAT\\-DataStore-Verzeichnis von% windir% ein formales XML-Dokument für die Bewertung generiert. Diese XML-Datei enthält die beiden folgenden Bewertungen, die für die Ermittlung der Codierungs- und Decodierungsmöglichkeiten ausgesprochen wichtig sind:

  - Der Wert „VideoEncodeScore“ gibt die softwarebasierte Viedeocodierungsfähigkeit des Computers an.

  - Der Wert „GraphicsScore“ gibt die hardwarebeschleunigte Codierungsfähigkeit des Computers an.

Die folgenden drei Tabellen erläutern die maximalen Codierungs- und Decodierungsfähigkeiten verschiedener PC-Typen in Abhängigkeit von der unterstützten Hardwarebeschleunigung. Für Auflösungen von 640 x 360 und darüber beträgt die maximal unterstützte Framerate 30 Frames pro Sekunde (fps). Für Auflösungen unter 640 x 360 beträgt die maximal unterstützte Framerate 15 fps.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Computer ohne DXVA und ohne hardwarebeschleunigten Codierer

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mögliche Codiererauflösung</th>
<th>Mögliche Decodiererauflösung</th>
<th>Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>424 x 240 (640 x 360 bei 15 fps für Szenarien, bei denen nur empfangen wird)</p></td>
<td><p>1 Kern und VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 Kerne und VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 Kerne und VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>Computer mit DXVA, aber ohne hardwarebeschleunigten Codierer

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mögliche Codiererauflösung</th>
<th>Mögliche Decodiererauflösung</th>
<th>Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 Kern und VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 Kerne und VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960 x 540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 Kerne und VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt. Die maximale Codierungsfähigkeit für einen Computer ohne hardwarebeschleunigten Codierer kann daher nur unter Windows 8 oder Windows 8.1 erreicht werden, wo der maximale WinSAT-Wert bei 9,9 liegt.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Computer mit DXVA und mit durch Intel HD Graphics hardwarebeschleunigtem Codierer

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mögliche Codiererauflösung</th>
<th>Mögliche Decodiererauflösung</th>
<th>Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920x1080</p></td>
<td><p>Alle Intel HD Graphics-Modelle der 2. und 3. Generation</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Video Funktionen für mobile Geräte

In der folgenden Tabelle werden die maximalen Videofunktionen der unterstützten mobilen Geräte beschrieben. Weitere Informationen zur Unterstützung mobiler Geräte finden Sie unter [Planen mobiler Clients in lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


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
<th>Funktion</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Maximale Auflösung der H.264-Codierung</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S und höher</p></td>
<td><p>VGA: iPad 2 und höher/iPad mini 1 und höher</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro und höher</p></td>
<td><p>Bis zu VGA je nach Gerätemodell</p></td>
</tr>
<tr class="even">
<td><p>Maximale Auflösung der H.264-Decodierung</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S und höher</p></td>
<td><p>VGA: iPad 2 und höher/iPad mini 1 und höher</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro und höher</p></td>
<td><p>Bis zu VGA je nach Gerätemodell</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

