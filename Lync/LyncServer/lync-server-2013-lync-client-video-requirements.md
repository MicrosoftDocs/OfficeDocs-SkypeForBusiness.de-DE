---
title: 'Lync Server 2013: Video Anforderungen für lync-Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c15eb698babcce1cd104dd7206c037b95d402992
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Video Anforderungen für lync-Clients für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-01-29_

In diesem Abschnitt wird die Videohardware Unterstützung für lync 2013 Videoanrufe beschrieben, und es wird beschrieben, wie Sie die erwartete Videoqualität für verschiedene Computer-, Tablet-und Mobile Gerätekonfigurationen bestimmen.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows-Desktop-und Tablet-Video Anforderungen und-Funktionen

Lync 2013 bietet eine Einführung in die Hardwarebeschleunigung für Videocodierung und-Decodierung basierend auf dem Standard H. 264/MPEG-4 Part 10 Advanced Video Coding. Diese Funktion sorgt dafür, dass auch Computer mit geringeren CPU-Taktgeschwindigkeiten höher auflösende Videos codieren und decodieren können. Die Videohardware-Anforderungen hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.

<div>

## <a name="video-hardware-requirements"></a>Videohardware-Anforderungen


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
> Ausführliche Informationen zu den Decodierungs Modi <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>finden Sie unter.


</div></td>
</tr>
<tr class="even">
<td><p>Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen</p></td>
<td><p>Die folgenden Intel hardwarebeschleunigten Video Codierungs Lösungen werden unterstützt:</p>
<ul>
<li><p>Intel HD Graphics 2000, 2500, 3000 und 4000 Chipsätze (oder aktuellere Versionen) der zweiten und dritten Generation mit integrierter Hardware-Videocodierung. Die Installation des Intel HD-Grafiktreibers 15.28.9.2884 oder des neuesten Treibers, der Folgendes enthält, ist erforderlich:</p>
<ul>
<li><p>Anzeigen des Treibers 9.17.10.2884 oder des neuesten Treibers</p></li>
<li><p>Hardware Media Foundation Transform (HMFT) Version 3.12.10.31 oder die neueste HMFT</p></li>
</ul></li>
</ul>
<p>Die folgenden AMD-hardwarebeschleunigten Video Codierungs Lösungen werden unterstützt (erfordert ku1-Updates für lync Server 2013):</p>
<ul>
<li><p>AMD Video Codec Engine, die in mehreren diskreten Grafikkarten und in integrierten beschleunigten Verarbeitungseinheiten von AMD A-Series Accelerated Processors verfügbar ist. Der AMD Video Codec Engine Driver 9.12.0.0 oder höher muss installiert sein.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen</p></td>
<td><p>USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 unterstützt UVC 1,5-Kameras mit Windows 8 oder Windows 8.1, einschließlich Unterstützung für UVC 1,5. Da Windows 7 UVC 1.5 nicht unterstützt, behandelt Lync 2013 UVC 1.5-Kameras als normale Kameras ohne Hardwarecodierung.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Ermitteln der Fähigkeiten zur H.264-Videocodierung und -decodierung

In der Regel werden die maximalen Codierungs- und Decodierungsmöglichkeiten einer konkreten Computerkonfiguration durch vier Hauptfaktoren bestimmt:

  - Unterstützung einer hardwarebeschleunigten Decodierung mittels DXVA

  - Unterstützung einer hardwarebeschleunigten Codierung

  - Anzahl der physischen Kerne

  - Windows Experience Index (WEI)

Das Windows System Assessment Tool (WinSAT) ermittelt den WEI-Wert. Wenn Sie das WinSAT-Tool ausführen, generiert es ein formal. Assessment XML-Dokument auf dem Computer im WinSAT\\\\\\-DataStore-Verzeichnis "% windir% Performance". Diese XML-Datei enthält die beiden folgenden Bewertungen, die für die Ermittlung der Codierungs- und Decodierungsmöglichkeiten ausgesprochen wichtig sind:

  - Der Wert "VideoEncodeScore" gibt die softwarebasierte Viedeocodierungsfähigkeit des Computers an.

  - Der Wert "GraphicsScore" gibt die hardwarebeschleunigte Codierungsfähigkeit des Computers an.

Die folgenden drei Tabellen erläutern die maximale Codierungs- und Decodierungsfähigkeiten verschiedener PC-Typen in Abhängigkeit der unterstützten Hardwarebeschleunigung. Für Auflösungen von 640 x 360 und darüber beträgt die maximal unterstützte Framerate 30 Frames pro Sekunde (fps). Für Auflösungen unter 640 x 360 beträgt die maximal unterstützte Framerate 15 fps.

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
<td><p>424 x 240</p></td>
<td><p>424 x 240 (640 x 360 bei 15 fps für Szenarien bei denen nur empfangen wird)</p></td>
<td><p>1 Kern und VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 Kerne und VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1280X720</p></td>
<td><p>2 Kerne und VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280X720</p></td>
<td><p>1280X720</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280X720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Nicht zutreffend</p></td>
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
<td><p>424 x 240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 Kern und VideoEncodeScore = 3,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 Kerne und VideoEncodeScore = 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280X720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt. Die Codierungsfunktion für einen Computer ohne einen hardwarebeschleunigten Encoder kann daher nur auf Windows 8 oder Windows 8.1 erreicht werden, wobei die maximale WinSAT-Punktzahl 9,9 beträgt.



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
<td><p>1280X720</p></td>
<td><p>1920x1080</p></td>
<td><p>Alle Intel HD Graphics-Modelle der 2. und 3. Generation</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Video Funktionen für mobile Geräte

In der folgenden Tabelle werden die maximalen Videofunktionen für unterstützte mobile Geräte beschrieben. Weitere Informationen zur Unterstützung mobiler Geräte finden Sie unter [Planning for Mobile Clients in lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


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
<th>Feature</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Maximale Auflösung der H. 264-Codierung</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S und höher</p></td>
<td><p>VGA: iPad 2 und höher/iPad Mini 1 und höher</p>
<p>720p: iPad Air/iPad Mini 2/iPad pro und höher</p></td>
<td><p>Je nach Gerätemodell bis zu VGA</p></td>
</tr>
<tr class="even">
<td><p>H. 264-Decodierungs maximale Auflösung</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S und höher</p></td>
<td><p>VGA: iPad 2 und höher/iPad Mini 1 und höher</p>
<p>720p: iPad Air/iPad Mini 2/iPad pro und höher</p></td>
<td><p>Je nach Gerätemodell bis zu VGA</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

