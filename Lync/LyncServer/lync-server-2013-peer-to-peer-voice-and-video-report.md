---
title: 'Lync Server 2013: Bericht über Peer-zu-Peer-Sprach- und Videoaktivität'
TOCTitle: Bericht über Peer-zu-Peer-Sprach- und Videoaktivität
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615040(v=OCS.15)
ms:contentKeyID: 49295674
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über Peer-zu-Peer-Sprach- und Videoaktivität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität bietet eine detaillierte Aufstellung der Sprach- und -Videoanrufe für einen bestimmten Zeitraum (z. B. Anrufe pro Stunde oder Anrufe pro Tag). Darüber hinaus können Sie mit diesem Bericht alle getätigten Sprach- und Videoanrufe oder aber nur die erfolgreichen bzw. fehlgeschlagenen Anrufe anzeigen. In diesem Bericht werden die Anrufinformationen in den folgenden Kategorien angezeigt:

  - Anrufe pro Pool

  - Anrufe pro Anruftyp (z. B. ein Lync-zu- Lync-Anruf bzw. ein Lync-Anruf bei einer Person im PSTN-Netzwerk)

  - Anrufe pro Zugriffstyp (beim internen Netzwerk angemeldete Benutzer bzw. beim externen Netzwerk angemeldete Benutzer)

  - Anrufe pro Vermittlungsserver

## So greifen Sie auf den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität zu

Auf den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität können Sie nur zugreifen, indem Sie den zusammenfassenden Bericht über Peer-zu-Peer-Aktivität öffnen und dann auf die folgenden Metriken klicken:

  - Peer-zu-Peer-Audiositzungen insgesamt

  - Gesamtdauer der Peer-zu-Peer-Audiositzung in Minuten

  - Peer-zu-Peer-Videositzungen insgesamt

  - Gesamtdauer der Peer-zu-Peer-Videositzung in Minuten

## So nutzen Sie den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität optimal

Es gibt eine Reihe von Möglichkeiten, um den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität zu filtern. Diese Filteroptionen sind jedoch standardmäßig ausgeblendet. Zum Anzeigen der verfügbaren Filteroptionen klicken Sie auf die Schaltfläche **Parameter ein-/ausblenden** in der oberen rechten Ecke des Berichtfensters.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität verwenden können.

### Filter im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität

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
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
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
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall <strong>Täglich</strong> mit dem Startdatum 8/7/2012 und dem Enddatum 9/28/2012 ausgewählt haben, werden Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Medientyp</strong></p></td>
<td><p>Gibt den Typ der in der Sitzung verwendeten Medien an. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Beide</p></li>
<li><p>Audio</p></li>
<li><p>Video</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufanordnung</strong></p></td>
<td><p>Gibt an, ob die Sitzung erfolgreich oder fehlerhaft war. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Erfolgreiche Anrufe</p></li>
<li><p>Fehlerhafte Anrufe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Bericht nach:</strong></p></td>
<td><p>Gibt die Werte an, die in dem Bericht verwendet werden sollen. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p><strong>Sitzungsanzahl</strong></p></li>
<li><p>Anrufminuten</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für jeden Pool angegeben werden.

### Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Pool

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
<td><p>Name des für den Anruf verwendeten Registrierungsstellenpools oder Edgeservers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


## Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Anruftyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für jeden Anruftyp angegeben werden.

### Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Anruftyp

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
<td><p><strong>Anruftyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt den Typ des Anrufs an, der ausgeführt wurde. Folgende Werte sind möglich:</p>
<ul>
<li><p>UC-zu-UC</p></li>
<li><p>UC-zu-PSTN</p></li>
<li><p>PSTN-zu-UC</p></li>
<li><p>PSTN-zu-PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


## Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Zugriffstyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für jeden Netzwerkzugriffstyp angegeben werden.

### Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Zugriffstyp

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
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt an, ob die Clients am internen oder am externen Netzwerk angemeldet wurden, als der Anruf getätigt wurde. Diese Metrik hat normalerweise einen der folgenden Werte:</p>
<ul>
<li><p>Intern</p></li>
<li><p>Extern</p></li>
<li><p>Gemischt</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>


## Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität für jeden Vermittlungsserver angegeben werden.

### Metriken für den Bericht über Peer-zu-Peer-Sprach- und -Videoaktivität nach Vermittlungsserver

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
<td><p><strong>Vermittlungsserver</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name des Vermittlungsservers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Sitzungen bzw. Gesamtzahl der Nachrichten.</p></td>
</tr>
</tbody>
</table>

