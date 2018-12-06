---
title: Bericht über die Metrikverteilung der Medienqualität
TOCTitle: Bericht über die Metrikverteilung der Medienqualität
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205262(v=OCS.15)
ms:contentKeyID: 49295473
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über die Metrikverteilung der Medienqualität

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Mit dem Bericht über die Metrikverteilung der Medienqualität wird ein Diagramm mit den Verteilungswerten für eine QoE-Metrik (Quality of Experience) wie z. B. Jitter oder Paketverlust angezeigt. Angenommen, Ihre Benutzer tätigen insgesamt 10 Telefonanrufe, für die die folgenden Roundtripzeiten gemeldet werden:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Anrufnummer</th>
<th>Roundtripzeit (Millisekunden)</th>
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


Der Durchschnittswert für diese Roundtripzeiten beträgt 500 Millisekunden (5000 geteilt durch 10). Fünfhundert Millisekunden ist eine extrem lange Roundtripzeit. Sie könnten deshalb daraus folgern, dass ein schwerwiegendes Netzwerküberlastungsproblem vorliegt. (Lange Roundtripzeiten sind in der Regel auf überlastete Netzwerke zurückzuführen.)

In Wirklichkeit hatten natürlich 90 % Ihrer Anrufe hervorragende Roundtripzeiten. Es gab nur einen Anruf mit einem sehr schlechten Wert, durch den das Gesamtergebnis verfälscht wurde. Wenn Sie nur die durchschnittliche Roundtripzeit betrachten, könnten Sie ganz falsche Schlussfolgerungen ziehen.

Der Bericht über die Metrikverteilung der Medienqualität hilft Ihnen, falsche Schlussfolgerungen zu vermeiden, indem die grafische Verteilung einer angegebenen Metrik (z. B. Roundtripzeit) angezeigt wird. Anhand dieser Diagramme lässt sich erkennen, dass es neun Anrufe mit sehr guten Werten und einen Anruf mit einem sehr schlechten Wert gibt. Zugegebenermaßen sollten Sie diesen einen Anruf weiter analysieren. Die Tatsache jedoch, dass 9 der 10 Anrufe sehr gute Werte aufweisen, ist ein Hinweis darauf, dass es keinen Grund gibt, drastische Änderungen an Ihrem Netzwerk vorzunehmen. Zumindest nicht zu diesem Zeitpunkt.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über die Metrikverteilung der Medienqualität verwenden können.

### Filter im Bericht über die Metrikverteilung der Medienqualität

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
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.2012</p>
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
<li><p>Internal</p></li>
<li><p>External</p></li>
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

