---
title: 'Lync Server 2013: Videoanforderungen für den Lync-Client'
TOCTitle: Videoanforderungen für den Lync-Client
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49890837
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Videoanforderungen für den Lync-Client für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Abschnitt wird die Videohardwareunterstützung für Lync 2013-Videoanrufe zusammen mit einem Verfahren zur Ermittlung der zu erwartenden Videoqualität für verschiedene Computer-, Tablet- und Mobilgerätkonfigurationen beschrieben.

## Videoanforderungen und -funktionen für Windows-Desktops und -Tablets

In Lync 2013 wird eine Hardwarebeschleunigung für die Videocodierung und -decodierung eingeführt, die auf dem Standard H.264/MPEG-4 Teil 10 Advanced Video Coding basiert. Diese Funktion sorgt dafür, dass auch Computer mit geringeren CPU-Taktgeschwindigkeiten höher auflösende Videos codieren und decodieren können. Die Videohardware-Anforderungen hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.

## Videohardware-Anforderungen


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktion</th>
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
> Ausführliche Informationen zu den Decodierungsmodi finden Sie unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268530%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=268530&amp;clcid=0x407</A>.


</div></td>
</tr>
<tr class="even">
<td><p>Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen</p></td>
<td><p>Folgende hardwarebeschleunigte Videocodierungslösungen von Intel werden unterstützt:</p>
<ul>
<li><p>Intel HD Graphics 2000, 2500, 3000 und 4000 Chipsätze (oder aktuellere Versionen) der zweiten und dritten Generation mit integrierter Hardware-Videocodierung. Die Installation des Intel HD Graphics-Treibers 15.28.9.2884 oder des aktuellsten Treibers, der Folgendes enthält, ist erforderlich:</p>
<ul>
<li><p>Grafiktreiber 9.17.10.2884 oder den aktuellsten Treiber</p></li>
<li><p>HMFT (Hardware Media Foundation Transform), Version 3.12.10.31, oder der neueste HMFT</p></li>
</ul></li>
</ul>
<p>Die folgenden hardwarebeschleunigten Videocodierungslösungen von AMD werden unterstützt (die CU1-Updates für Lync Server 2013 sind erforderlich):</p>
<ul>
<li><p>AMD Video Codec Engine, die in einer Reihe diskreter Grafikkarten sowie in integrierten hardwarebeschleunigten CPUs der AMD A-Series Accelerated Processors verfügbar ist. Der AMD Video Codec Engine-Treiber 9.12.0.0 oder höher muss installiert sein.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen</p></td>
<td><p>USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.</p>
<div>

> [!NOTE]
> Lync 2013 unterstützt UVC 1.5-Kameras mit Windows 8 oder Windows 8.1, da Windows 8 UVC 1.5 unterstützt. Da Windows 7 UVC 1.5 nicht unterstützt, behandelt Lync 2013 UVC 1.5-Kameras als normale Kameras ohne Hardwarecodierung.


</div></td>
</tr>
<tr class="even">
<td><p>Hardwarebeschleunigte H.264-Decodierung mit DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>Die Grafikkarte muss DirectX 9.0 unterstützen und den Decodierungsmodus DXVA2_ModeH264_VLD_NoFGT beherrschen.</p></li>
<li><p>Der aktuellste Grafikkartentreiber muss installiert sein.</p></li>
</ul>
<div>

> [!NOTE]
> Ausführliche Informationen zu den Decodierungsmodi finden Sie unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=268530%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=268530&amp;clcid=0x407</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen</p></td>
<td><p>Folgende hardwarebeschleunigte Videocodierungslösungen von Intel werden unterstützt:</p>
<ul>
<li><p>Intel HD Graphics 2000, 2500, 3000 und 4000 Chipsätze (oder aktuellere Versionen) der zweiten und dritten Generation mit integrierter Hardware-Videocodierung. Die Installation des Intel HD Graphics-Treibers 15.28.9.2884 oder des aktuellsten Treibers, der Folgendes enthält, ist erforderlich:</p>
<ul>
<li><p>Grafiktreiber 9.17.10.2884 oder den aktuellsten Treiber</p></li>
<li><p>HMFT (Hardware Media Foundation Transform), Version 3.12.10.31, oder der neueste HMFT</p></li>
</ul></li>
</ul>
<p>Die folgenden hardwarebeschleunigten Videocodierungslösungen von AMD werden unterstützt (die CU1-Updates für Lync Server 2013 sind erforderlich):</p>
<ul>
<li><p>AMD Video Codec Engine, die in einer Reihe diskreter Grafikkarten sowie in integrierten hardwarebeschleunigten CPUs der AMD A-Series Accelerated Processors verfügbar ist. Der AMD Video Codec Engine-Treiber 9.12.0.0 oder höher muss installiert sein.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen</p></td>
<td><p>USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.</p>
<div>

> [!NOTE]
> Lync 2013 unterstützt UVC 1.5-Kameras mit Windows 8 oder Windows 8.1, da Windows 8 UVC 1.5 unterstützt. Da Windows 7 UVC 1.5 nicht unterstützt, behandelt Lync 2013 UVC 1.5-Kameras als normale Kameras ohne Hardwarecodierung.


</div></td>
</tr>
</tbody>
</table>


## Ermitteln der Fähigkeiten zur H.264-Videocodierung und -decodierung

In der Regel werden die maximalen Codierungs- und Decodierungsmöglichkeiten einer konkreten Computerkonfiguration durch vier Hauptfaktoren bestimmt:

  - Unterstützung einer hardwarebeschleunigten Decodierung mittels DXVA

  - Unterstützung einer hardwarebeschleunigten Codierung

  - Anzahl der physischen Kerne

  - Windows Experience Index (WEI)

Das Windows System Assessment Tool (WinSAT) ermittelt den WEI-Wert. Wenn Sie WinSAT ausführen, generiert das Tool auf dem Computer im Verzeichnis %windir%\\Performance\\WinSAT\\DataStore das XML-Dokument "Formal.Assessment". Diese XML-Datei enthält die beiden folgenden Bewertungen, die für die Ermittlung der Codierungs- und Decodierungsmöglichkeiten ausgesprochen wichtig sind:

  - Der Wert "VideoEncodeScore" gibt die softwarebasierte Videocodierungsfähigkeit des Computers an.

  - Der Wert "GraphicsScore" gibt die hardwarebeschleunigte Codierungsfähigkeit des Computers an.

Die folgenden drei Tabellen erläutern die maximale Codierungs- und Decodierungsfähigkeiten verschiedener PC-Typen in Abhängigkeit der unterstützten Hardwarebeschleunigung. Für Auflösungen von 640 x 360 und darüber beträgt die maximal unterstützte Framerate 30 Frames pro Sekunde (fps). Für Auflösungen unter 640 x 360 beträgt die maximal unterstützte Framerate 15 fps.

### Computer ohne DXVA und ohne hardwarebeschleunigten Codierer

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
<td><p>1 Kern und VideoEncodeScore = 4,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1280 x 720</p></td>
<td><p>2 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1280 x 720</p></td>
<td><p>4 Kerne und VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>424 x 240</p></td>
<td><p>424 x 240 (640 x 360 bei 15 fps für Szenarien bei denen nur empfangen wird)</p></td>
<td><p>1 Kern und VideoEncodeScore = 4,0</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1280 x 720</p></td>
<td><p>2 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1280 x 720</p></td>
<td><p>4 Kerne und VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


### Computer mit DXVA, aber ohne hardwarebeschleunigten Codierer

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
<td><p>1920 x 1080</p></td>
<td><p>1 Kern und VideoEncodeScore = 3,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960 x 540</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 Kerne und VideoEncodeScore = 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 8,2</p></td>
</tr>
<tr class="even">
<td><p>424 x 240</p></td>
<td><p>1920 x 1080</p></td>
<td><p>1 Kern und VideoEncodeScore = 3,0</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 Kerne und VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>960 x 540</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 Kerne und VideoEncodeScore = 6,0</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 6,7</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 Kerne und VideoEncodeScore = 8,2</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt. Die maximale Codierungsfähigkeit für einen Computer ohne hardwarebeschleunigten Codierer kann daher nur unter Windows 8 oder Windows 8.1 erreicht werden, wo der maximale WinSAT-Wert bei 9,9 liegt.



### Computer mit DXVA und mit durch Intel HD Graphics hardwarebeschleunigtem Codierer

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
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Alle Intel HD Graphics-Modelle der 2. und 3. Generation</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore = 5,0</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Alle Intel HD Graphics-Modelle der 2. und 3. Generation</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore = 5,0</p></td>
</tr>
</tbody>
</table>


## Videofunktionen für mobile Geräte

In der folgenden Tabelle sind die maximalen Videofunktionen für unterstützte mobile Geräte beschrieben. Weitere Informationen zur Unterstützung für mobile Geräte finden Sie unter [Planung für mobile Clients](lync-server-2013-planning-for-mobile-clients.md).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Funktion</th>
<th>Windows Phone</th>
<th>iPhone und iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Maximale H.264-Codierungsauflösung</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone 4: 192 x 144</p>
<p>iPad und alle anderen unterstützten iPhone-Modelle: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="even">
<td><p>Maximale H.264-Decodierungsauflösung</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone und iPad: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="odd">
<td><p>Maximale H.264-Codierungsauflösung</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone 4: 192 x 144</p>
<p>iPad und alle anderen unterstützten iPhone-Modelle: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="even">
<td><p>Maximale H.264-Decodierungsauflösung</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone und iPad: 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
</tbody>
</table>


1Für Android-Geräte mit einem Qualcomm Snapdragon S3- oder S4-Prozessor mit einem 8x60-Chipsatz wird das Senden und Empfangen mit einer Auflösung von 640 x 480 unterstützt.

