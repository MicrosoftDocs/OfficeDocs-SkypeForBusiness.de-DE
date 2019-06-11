---
title: 'Lync Server 2013: Verteilungs Bericht zur Medien Qualitätsmetrik'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Der Verteilungs Bericht zur Medien Qualitätsmetrik in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Mit dem Bericht über die Metrikverteilung der Medienqualität wird ein Diagramm mit den Verteilungswerten für eine QoE-Metrik (Quality of Experience) wie z. B. Jitter oder Paketverlust angezeigt. Angenommen, Ihre Benutzer tätigen insgesamt 10 Telefonanrufe, für die die folgenden Roundtripzeiten gemeldet werden:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Anrufnummer</th>
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
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


Der Mittelwert für diese Roundtrip-Zeiten beträgt 500 Millisekunden (5000 dividiert durch 10). 500 Millisekunden ist eine extrem große Roundtrip-Zeit; aus diesem Grund glauben Sie vielleicht, dass Sie ein schwerwiegendes Problem mit Netzwerküberlastung haben. (Lange Roundtrip-Zeiten sind in der Regel das Ergebnis von überladenen Netzwerken.)

In Wirklichkeit hatten 90% ihrer Anrufe hervorragende Roundtrip-Zeiten; Sie hatten lediglich einen schlechten Anruf, der die Gesamtergebnisse verzerrt hat. Wenn Sie nur die durchschnittliche Roundtrip-Zeit sehen, können Sie zu einer sehr falschen Schlussfolgerung springen.

Der Bericht über die Metrikverteilung der Medienqualität hilft Ihnen, falsche Schlussfolgerungen zu vermeiden, indem die grafische Verteilung einer angegebenen Metrik (z. B. Roundtripzeit) angezeigt wird. Anhand dieser Diagramme lässt sich erkennen, dass es neun Anrufe mit sehr guten Werten und einen Anruf mit einem sehr schlechten Wert gibt. Zugegebenermaßen sollten Sie diesen einen Anruf weiter analysieren. Die Tatsache jedoch, dass 9 der 10 Anrufe sehr gute Werte aufweisen, ist ein Hinweis darauf, dass es keinen Grund gibt, drastische Änderungen an Ihrem Netzwerk vorzunehmen. Zumindest nicht zu diesem Zeitpunkt.

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über die Metrikverteilung der Medienqualität verwenden können.

### <a name="media-quality-metrics-distribution-report-filters"></a>Filter im Bericht über die Metrikverteilung der Medienqualität

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
<td><p><strong>Von</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minimum in X-Achse</strong></p></td>
<td><p>Der niedrigste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</p></td>
</tr>
<tr class="even">
<td><p><strong>Maximum in X-Achse</strong></p></td>
<td><p>Der höchste Wert, der auf der X-Achse des Diagramms angezeigt werden soll.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Intern</p></li>
<li><p>Extern</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Netzwerktyp</strong></p></td>
<td><p>Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Verkabelt</p></li>
<li><p>Funk</p></li>
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

