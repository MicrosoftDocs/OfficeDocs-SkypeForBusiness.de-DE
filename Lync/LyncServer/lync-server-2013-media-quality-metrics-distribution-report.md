---
title: 'Lync Server 2013: Verteilungs Bericht über Medien Qualitäts Metriken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16af6d17c78cb16ccf306234c7416aa6d6a75de5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Der Verteilungs Bericht zur Medien Qualitätsmetrik in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-06_

Der Bericht zur Verteilung von Medienqualität-Metriken ermöglicht Ihnen das Anzeigen eines Diagramms, in dem die Verteilungswerte für eine Metrik für die Qualität der Erfahrung wie Jitter oder Paketverlust angezeigt werden. Nehmen Sie beispielsweise an, dass Ihre Benutzer insgesamt 10 Telefonanrufe tätigen; bei diesen 10 aufrufen wird die folgende Roundtrip-Zeit gemeldet:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rufnummer</th>
<th>Roundtrip-Zeit (Millisekunden)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


Der Durchschnitt für diese Roundtrip-Zeiten beträgt 500 Millisekunden (5000 dividiert durch 10). 500 Millisekunden ist eine extrem große Roundtrip-Zeit; Daher glauben Sie möglicherweise, dass Sie ein ernstes Problem mit Netzwerküberlastung haben. (Lange Roundtrip-Zeiten sind normalerweise das Ergebnis von überladenen Netzwerken.)

In Wirklichkeit hatten natürlich 90% ihrer Anrufe ausgezeichnete roundtripzeiten; Sie haben lediglich einen schlechten Anruf gehabt, der die Gesamtergebnisse verzerrt hat. Wenn Sie nur die durchschnittliche Roundtripzeit betrachten, können Sie zu einer sehr falschen Schlussfolgerung springen.

Der Bericht zur Verteilung von Medienqualität-Metriken hilft Ihnen, zu falschen Schlussfolgerungen zu springen, indem eine grafische Verteilung einer bestimmten Metrik angezeigt wird (beispielsweise Roundtrip-Zeit). Diese Diagramme können Ihnen dabei helfen, deutlich zu machen, dass Sie neun sehr gute Anrufe und einen sehr schlechten Anruf hatten. Allerdings möchten Sie möglicherweise weiterhin diesen einen Anruf untersuchen; die Tatsache, dass 9 von 10 anrufen sehr gut waren, deutet jedoch darauf hin, dass es keinen Grund gibt, drastische Änderungen an Ihrem Netzwerk vorzunehmen, zumindest nicht zu diesem Zeitpunkt.

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem Verteilungs Bericht über Medienqualität verwenden können.

### <a name="media-quality-metrics-distribution-report-filters"></a>Medien Qualitäts Metriken Verteilungs Berichtsfilter

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ziel</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minimum in x-Achse</strong></p></td>
<td><p>Der niedrigste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</p></td>
</tr>
<tr class="even">
<td><p><strong>Maximum in x-Achse</strong></p></td>
<td><p>Der höchste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Intern</p></li>
<li><p>Extern</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Alle</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Netzwerktyp</strong></p></td>
<td><p>Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Alle</p></li>
<li><p>Wired</p></li>
<li><p>Drahtlos</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

