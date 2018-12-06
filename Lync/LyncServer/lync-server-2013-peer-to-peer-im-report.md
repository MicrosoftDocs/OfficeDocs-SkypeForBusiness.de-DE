---
title: 'Lync Server 2013: Bericht über Peer-zu-Peer-Chatnachrichten'
TOCTitle: Bericht über Peer-zu-Peer-Chatnachrichten
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558620(v=OCS.15)
ms:contentKeyID: 49293327
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über Peer-zu-Peer-Chatnachrichten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht über Peer-zu-Peer-Sofortnachrichten enthält Trendinformationen zu den Peer-zu-Peer-Sofortnachrichtensitzungen, aufgeschlüsselt nach Pool und Authentifizierungstyp. Der Bericht kann entweder die Gesamtanzahl der im angegebenen Zeitraum abgehaltenen Sitzungen (z. B. nach Tag oder nach Stunden) oder die Gesamtanzahl der in diesem Zeitraum gesendeten Sofortnachrichten anzeigen.

## Zugreifen auf den Bericht über Peer-zu-Peer-Sofortnachrichten

Sie können auf den Bericht über Peer-zu-Peer-Sofortnachrichten nur zugreifen, indem Sie den [Zusammenfassender Bericht über Peer-zu-Peer-Aktivität in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) öffnen und dann auf eine der folgenden Metriken klicken:

  - Peer-zu-Peer-Chatsitzungen insgesamt

  - Peer-zu-Peer-Chatnachrichten insgesamt

## Optimales Verwenden des Berichts über Peer-zu-Peer-Sofortnachrichten

Standardmäßig wird im Bericht über Peer-zu-Peer-Sofortnachrichten die Anzahl der Nachrichten pro Stunde (oder, abhängig von Ihren Einstellungen, pro Tag) angezeigt. Sie können jedoch auch den Tag nach Sitzungen pro Stunde anzeigen. Klicken Sie dazu rechts oben im Fenster der Berichte auf die Schaltfläche zum Ein- und Ausblenden der Parameter , und klicken Sie dann in der Liste **Bericht nach** auf **Sitzungsanzahl** .

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-zu-Peer-Sofortnachrichten verwenden können.

### Filter im Bericht über Peer-zu-Peer-Sofortnachrichten

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
<p>7/7/2012 1:00 PM</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die Woche oder den Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 PM</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p><strong>Stündlich</strong> (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p><strong>Täglich</strong> (maximal 31 Tage können angezeigt werden)</p></li>
<li><p><strong>Wöchentlich</strong> (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p><strong>Monatlich</strong> (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall &quot;Täglich&quot; mit dem Startdatum 7/7/2012 und dem Enddatum 28/2/2011 ausgewählt haben, werden Daten für die Tage 7/8/2012 12:00 Uhr bis 7/9/2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Bericht nach:</strong></p></td>
<td><p>Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p><strong>Sitzungsanzahl</strong></p></li>
<li><p><strong>Nachrichtenanzahl</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sofortnachrichten enthalten sind.

### Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Pool

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
<td><p><strong>Pool</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name des Registrierungsstellenpools oder Edgeservers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


## Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sofortnachrichten für die einzelnen von den Teilnehmern in einer Peer-zu-Peer-Sitzung verwendeten Authentifizierungstypen angegeben werden.

### Metriken für den Bericht über Peer-zu-Peer-Sofortnachrichtensitzungen nach Authentifizierungstyp

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
<td><p><strong>Authentifizierungstyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der von den Sitzungsteilnehmern verwendete Authentifizierungstyp. Folgende Werte sind möglich:</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>Verbund</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem die Sitzungen stattfanden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>

