---
title: 'Lync Server 2013: Zusammenfassender Bericht über Peer-zu-Peer-Aktivität'
TOCTitle: Zusammenfassender Bericht über Peer-zu-Peer-Aktivität
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615041(v=OCS.15)
ms:contentKeyID: 49295754
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusammenfassender Bericht über Peer-zu-Peer-Aktivität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der zusammenfassende Bericht über Peer-zu-Peer-Aktivität bietet eine Übersicht über Peer-zu-Peer-Kommunikationssitzungen. An Peer-zu-Peer-Sitzungen sind in der Regel nur zwei Benutzer beteiligt, und die Lync Server-Konferenzdienste sind nicht erforderlich. Im Vergleich dazu sind an einer Konferenz in der Regel mehr als zwei Benutzer beteiligt, und die Microsoft Lync Server 2013-Konferenzdienste sind erforderlich. Konferenzaktivität wird im zusammenfassenden Konferenzbericht gemeldet.

Der zusammenfassende Bericht über Peer-zu-Peer-Aktivität hilft Ihnen bei der Beantwortung der folgenden Fragen:

  - Wie viele Peer-zu-Peer-Chatnachrichten senden meine Benutzer an einem normalen Tag?

  - Nutzen meine Benutzer tatsächlich die Dateifreigabe- und Dateiübertragungsfunktionen von Lync Server?

  - Die Benutzer haben sich darüber beklagt, dass das Netzwerk zu bestimmten Tageszeiten langsam ist. Wie viele Minuten werden in diesen Zeiten für Peer-zu-Peer-Audio-/Videositzungen aufgewendet?

## Zugriff auf den zusammenfassenden Bericht über Peer-zu-Peer-Aktivität

Auf den zusammenfassenden Bericht über Peer-zu-Peer-Aktivität greifen Sie auf der Startseite Überwachungsberichte zu. Den [Bericht über Peer-zu-Peer-Chatnachrichten in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) öffnen Sie, indem Sie auf eine der folgenden Metriken klicken:

  - Peer-zu-Peer-Chatsitz-ungen insgesamt

  - Peer-zu-Peer-Chatnachrichten insgesamt

Entsprechend können Sie den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität öffnen, indem Sie auf eine der folgenden Metriken klicken:

  - Peer-zu-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-zu-Peer-Audiositzung in Minuten

  - Peer-zu-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-zu-Peer-Audiositzung in Minuten

## Optimale Nutzung des zusammenfassenden Berichts über Peer-zu-Peer-Aktivität

Im unteren Bereich des zusammenfassenden Berichts über Peer-zu-Peer-Aktivität finden Sie Gesamtwerte für Metriken wie z. B. Peer-zu-Peer-Chatsitzungen insgesamt und Peer-zu-Peer-Chatnachrichten insgesamt . Dies ermöglicht einen schnellen Überblick über die detaillierten Informationen im eigentlichen Bericht.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem zusammenfassenden Bericht über Peer-zu-Peer-Aktivität können Sie beispielsweise wählen, wie Daten gruppiert werden sollen. In diesem Fall werden die Aktivitäten nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im zusammenfassenden Bericht über Peer-zu-Peer-Aktivität verwenden können.

### Filter im zusammenfassenden Bericht über Peer-zu-Peer-Aktivität

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
<p>7/17/2012 1:00 PM</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 AM. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/17/2012 1:00 PM</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 PM. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 7/17/2012 und dem Enddatum 2/28/2012 ausgewählt haben, werden Daten für die Tage 8/7/2012 12:00 AM bis 9/7/2012 12:00 AM angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im zusammenfassenden Bericht über Peer-zu-Peer-Aktivität angegeben werden.

### Metriken im zusammenfassenden Bericht über Peer-zu-Peer-Aktivität

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
<td><p><strong>Stündlich</strong></p>
<p><strong>Täglich</strong></p>
<p><strong>Wöchentlich</strong></p>
<p><strong>Monatlich</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 7/17/2012 klicken, wird eine stündliche Übersicht der Benutzerregistrierungsaktivität für dieses Datum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-zu-Peer-Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der abgehaltenen Peer-zu-Peer-Sitzungen, unabhängig vom Sitzungstyp.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Peer-zu-Peer-Chatsitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-zu-Peer-Chatnachrichtensitzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-zu-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-zu-Peer-Chatnachrichten insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der in Peer-zu-Peer-Sitzungen gesendeten Chatnachrichten. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-zu-Peer-Chatnachrichten für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Peer-zu-Peer-Audiositzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-zu-Peer-Audioanrufe. Wenn Sie auf dieses Feld klicken, wird der Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gesamtdauer der Peer-zu-Peer-Audiositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtdauer der Peer-zu-Peer-Audiositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Durchschnittliche Dauer der Peer-zu-Peer-Audiositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Dauer einer Peer-zu-Peer-Audiositzung. Wird errechnet, indem die Gesamtdauer der Audiositzungen durch die Gesamtanzahl der Audiositzungen geteilt wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-zu-Peer-Videositzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-zu-Peer-Videoanrufe. Beachten Sie, dass Videositzungen auch als Audiositzungen zählen; jede Videositzung zählt als eine Videositzung und eine Audiositzung. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamtdauer der Peer-zu-Peer-Videositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtdauer der Peer-zu-Peer-Videositzungen. Wenn Sie auf dieses Element klicken, wird der Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für den gewählten Zeitraum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche Dauer der Peer-zu-Peer-Videositzung in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Dauer einer Peer-zu-Peer-Videositzung. Wird errechnet, indem die Gesamtdauer der Videositzungen durch die Gesamtanzahl der Videositzungen geteilt wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Peer-zu-Peer-Dateiübertragungssitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-zu-Peer-Sitzungen mit Dateiübertragungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Peer-zu-Peer-Anwendungsfreigabesitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Peer-zu-Peer-Sitzungen mit Anwendungsfreigabe.</p></td>
</tr>
</tbody>
</table>

