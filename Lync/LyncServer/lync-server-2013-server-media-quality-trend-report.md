---
title: Trendbericht über Medienqualität des Servers
TOCTitle: Trendbericht über Medienqualität des Servers
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205071(v=OCS.15)
ms:contentKeyID: 49294675
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Trendbericht über Medienqualität des Servers

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Mit dem "Trendbericht über Medienqualität des Servers" haben Sie die Möglichkeit, bis zu 5 Server anhand von Quality of Experience (QoE)-Metriken, wie beispielsweise Anrufvolumen, Prozentsatz der Anrufe schlechter Qualität, Paketverlust und Jitter grafisch zu vergleichen. Mithilfe dieser Möglichkeit ist es einfacher, die leistungsschwachen, unterausgelasteten oder die überbeanspruchten Server zu identifizieren.

## Zugreifen auf den "Trendbericht über Medienqualität des Servers"

Auf den "Trendbericht über Medienqualität des Servers" kann über einen der folgenden Berichte zugegriffen werden:

  - [Bericht über Serverleistung in Lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf die Trend-Metriken)

  - [Anrufdetailbericht in Lync Server 2013](lync-server-2013-call-detail-report.md) (durch Klicken auf die A/V-Edgeserver-Metriken. Wenn der Anrufer bzw. der Angerufene ein Server ist, kann der Trendbericht über Medienqualität des Servers auch durch Klicken auf den Endpunktnamen erreicht werden.)

## Optimale Nutzung des "Trendberichts über Medienqualität des Servers"

Wenn Sie auf die Trend-Metrik im [Bericht über Serverleistung in Lync Server 2013](lync-server-2013-server-performance-report.md) für einen bestimmten Server klicken, wird der "Trendbericht über Medienqualität des Servers" geöffnet. In diesem Bericht wird jedoch nur eine leere Instanz angezeigt. Der von Ihnen ausgewählte Server im Bericht über Serverleistung wird nicht auf dem Bildschirm angezeigt. Stattdessen müssen Sie den Server aus der Dropdownliste mit den Servern auswählen. Beachten Sie auch, dass in der Dropdownliste mit den Servern die Option "Alle auswählen" enthalten ist. Diese Option funktioniert nicht, wenn mehr als 5 Server vorhanden sind. Im "Trendbericht über Medienqualität des Servers" können nur Daten für maximal 5 Server gleichzeitig angezeigt werden.

In den Grafiken des "Trendberichts über Medienqualität des Servers" werden die mit "Anrufvolumen" und "Prozentsatz der Anrufe mit schlechter Qaulität" bezeichneten Punkte als Hotlinks angezeigt. Beim Klicken auf einen Punkt in der Grafik wird eine Instanz des [Anruflistenbericht in Lync Server 2013](lync-server-2013-call-list-report.md) geöffnet, in der die Gesamtanzahl der Anrufe (oder die Anrufe schlechter Qualität) für die angegebene Zeitspanne angezeigt wird.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im "Trendbericht über Medienqualität des Servers" verwenden können.

### Filter im "Trendbericht über Medienqualität des Servers"

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
<p>07.07.2012 13:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
</ul>
<p>Wenn die Start- und Enddaten die maximale Anzahl an zugelassenen Werten für das ausgewählte Intervall überschreiten, wird nur die maximale Anzahl an Werten (beginnend beim Startdatum) angezeigt. Wenn Sie beispielsweise das Intervall &quot;Täglich&quot; mit dem Startdatum 07.07.2012 und dem Enddatum 28.09.2012 wählen, werden die Daten für die Tage vom 07.08.2012 12:00 Uhr bis zum 07.09.2012 12:00 Uhr angezeigt (insgesamt also die Daten von 31 Tagen).</p></td>
</tr>
<tr class="even">
<td><p><strong>Servertyp</strong></p></td>
<td><p>Beim Anruf verwendeter Servertyp. Gültige Werte sind:</p>
<ul>
<li><p>Vermittlungsserver</p></li>
<li><p>A/V-Konferenzserver</p></li>
<li><p>A/V-Edgeserver</p></li>
<li><p>Gateway (Vermittlungsserver)</p></li>
<li><p>Gateway (Umgehung des Vermittlungsservers)</p></li>
<li><p>AS-Konferenzserver</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Servers</strong></p></td>
<td><p>Name des in der Sitzung verwendeten Servers. Diese Dropdownliste wird automatisch anhand des Werts des Servertypfilters aufgefüllt. Sie können bei der Erstellung eines Berichts bis zu 5 verschiedene Server auswählen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Gibt an, ob der Teilnehmer am internen oder am externen Netzwerk angemeldet wurde. Gültige Werte sind:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Internal</p></li>
<li><p>External</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Netzwerktyp</strong></p></td>
<td><p>Gibt den Typ des Netzwerks an, mit dem der Teilnehmer verbunden wurde. Gültige Werte sind:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Verkabelt</p></li>
<li><p>Funk</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Teilnehmer während der Sitzung eine VPN-Verbindung (Virtual Private Network) verwendete. Gültige Werte sind:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im "Trendbericht über Medienqualität des Servers" angegeben werden.

### Metriken im "Trendbericht über Medienqualität des Servers"

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Anrufvolumen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtanzahl der Anrufe</p></td>
</tr>
<tr class="even">
<td><p><strong>Beeinträchtigung (MOS)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Beeinträchtigung der Qualität, die gemäß MOS (Mean Opinion Score) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen &quot;0,0&quot; (schlecht) und &quot;5,0&quot; (gut). Ein Wert von &quot;0,5&quot; oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. Lync Server ermittelt anhand mehrerer Algorithmen, wie die Benutzer einen Anruf bewertet hätten.</p>
<p>Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</p></td>
</tr>
<tr class="even">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein Real-Time Transport Protocol-Paket (RTP) benötigt, um zu einem Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Paketverlust</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport Protocol). (Zu Paketverlusten kommt es, wenn RTP-Pakete (ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen.) Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das &quot;Zittern&quot; der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum &quot;Glätten&quot; der &quot;holprigen&quot; Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitter Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Streckungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitter Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Komprimierungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitter Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</p></td>
</tr>
</tbody>
</table>

