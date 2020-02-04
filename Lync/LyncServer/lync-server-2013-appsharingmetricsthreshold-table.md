---
title: 'Lync Server 2013: AppSharingMetricsThreshold-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>AppSharingMetricsThreshold-Tabelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-12-08_

Die AppSharingMetricsThreshold-Tabelle enthält optimale und akzeptable Werte für die Qualität der Erfahrungs Metrik, die bei der Anwendungsfreigabe verwendet wird. Diese Schwellenwerte werden verwendet, um festzustellen, ob die Anwendungsfreigabe Erfahrung als "schlecht" klassifiziert werden soll.

Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.


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
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Der Typ des Anrufs, der getätigt wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Optimale Bandbreitenbeschränkung bei der Anwendungsfreigabe. Der Standardwert ist 1 Million.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Zulässige Bandbreitenbeschränkung für die Anwendungsfreigabe. Der Standardwert ist 500000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>Optimaler Prozentsatz für "verwöhnte" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität. Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat. Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft. Der Standardwert ist 11 Prozent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>Dezimal (5; 2)</p></td>
<td></td>
<td><p>cceptable-Prozentsatz für "verdorbene" Kacheln für die Klassifizierung einer Anwendungsfreigabe Qualität. Dieser Wert ist der Prozentsatz des Inhalts des mitbenutzenden, der den Betrachter nicht erreicht hat. Inhalte werden möglicherweise verworfen (oder verdorben), wenn der mitbenutzende die Kacheln aus der grafikquelle abwirft oder die ASMCU-Kacheln Kacheln von Sharer abwirft. Der Standardwert ist 36 Prozent.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Diese Spalte wird in Microsoft lync Server 2013 nicht verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind. Dies ist ein Single-Hop-Latenzmaß. Der Standardwert ist 1,0 Sekunden.</p>
<p>Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Optimaler Wert für die relative unidirektionale Verzögerung zwischen den beiden Medien Endpunkten, die an der Anwendungsfreigabe beteiligt sind. Dies ist ein Single-Hop-Latenzmaß. Der Standardwert ist 1,75 Sekunden.</p>
<p>Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Optimaler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung. Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.</p>
<p>Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an. Der Standardwert ist 200M.</p>
<p>Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Akzeptabler Wert der durchschnittlichen Verarbeitungs Wartezeit für RDP-Kacheln auf dem AS-Konferenz Server über die Dauer der Anzeige Sitzung. Latenz ist der Zeitunterschied zwischen dem Codieren des Start Frames auf dem Server (Sharer oder MCU, je nach Szenario) und dem gleichen Start Frame im Viewer.</p>
<p>Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an. Der Standardwert ist 200M.</p>
<p>Die Spalte wurde in Microsoft lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

