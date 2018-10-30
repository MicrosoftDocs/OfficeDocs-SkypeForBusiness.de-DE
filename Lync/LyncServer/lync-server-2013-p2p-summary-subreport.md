---
title: Zusammenfassender Unterbericht über Peer-zu-Peer-Sitzungen
TOCTitle: Zusammenfassender Unterbericht über Peer-zu-Peer-Sitzungen
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205416(v=OCS.15)
ms:contentKeyID: 49296000
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusammenfassender Unterbericht über Peer-zu-Peer-Sitzungen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Zusammenfassende Unterbericht über Peer-zu-Peer-Sitzungen bietet eine allgemeine Übersicht über fehlerhafte Peer-zu-Peer-Kommunikationssitzungen.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Unterbericht über Peer-zu-Peer-Sitzungen verwenden können.

### Filter im Zusammenfassenden Unterbericht über Peer-zu-Peer-Sitzungen

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
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) des Registrierungsstellenpools oder des Edgeserver. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Unterbericht über Peer-zu-Peer-Sitzungen angegeben werden.

### Metriken im Zusammenfassenden Unterbericht über Peer-zu-Peer-Sitzungen

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
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fehlerrate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen nach Modalität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen, gruppiert nach Modalität (z.&amp;nbsp;B. Instant Messaging).</p></td>
</tr>
<tr class="even">
<td><p><strong>Fehlerrate nach Modalität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der fehlerhaften Sitzungen, gruppiert nach Modalität (z.&amp;nbsp;B. Instant Messaging).</p></td>
</tr>
</tbody>
</table>

