---
title: 'Lync Server 2013: Konferenzaktivitätsbericht'
TOCTitle: Konferenzaktivitätsbericht
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558627(v=OCS.15)
ms:contentKeyID: 49293424
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konferenzaktivitätsbericht in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Mit dem Konferenzaktivitätsbericht können Fragen wie diese leicht beantwortet werden: Wie viele Konferenzen werden täglich gehalten, und wann werden diese Konferenzen gehalten? Derartige Informationen sind an sich nützlich und können außerdem für die Problembehandlung verwendet werden. Nehmen wir z. B. an, dass sich Benutzer darüber beschweren, dass das Netzwerk mittags besonders langsam zu sein scheint. Ein kurzer Blick in die Konferenzaktivitätsberichte zeigt Folgendes: Zwischen 10 Uhr und 14 Uhr finden weitaus mehr Konferenzen statt als zu anderen Zeiten.

Verursacht das langsame Netzwerk Probleme, können Sie Benutzern empfehlen, Konferenzen zu Tageszeiten mit weniger Datenauslastung abzuhalten.

## Zugreifen auf den Konferenzaktivitätsbericht

Auf den Konferenzaktivitätsbericht wird über den [Zusammenfassender Konferenzbericht in Lync Server 2013](lync-server-2013-conference-summary-report.md) zugegriffen. Klicken Sie dazu auf eine der folgenden Metriken:

  - Konferenzen insgesamt

  - Teilnehmer insgesamt

## Optimales Verwenden des Konferenzaktivitätsberichts

Standardmäßig wird im Konferenzaktivitätsbericht die Gesamtanzahl der Konferenzen für den angegebenen Zeitraum (z. B. die Gesamtanzahl der Konferenzen pro Tag oder die Gesamtanzahl der Konferenzen pro Stunde eines Tages). Sie können jedoch auch die Gesamtanzahl der Teilnehmer für den Zeitraum oder die Gesamtanzahl der Teilnehmerminuten anzeigen. Klicken Sie dazu auf die Schaltfläche zum Ein- und Ausblenden der Parameter, um die Filteroptionen anzuzeigen, und wählen Sie dann eine der folgenden Optionen aus der Dropdownliste "Bericht nach" aus:

  - Teilnehmeranzahl

  - Teilnehmerminuten

  - Konferenzanzahl

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Konferenzaktivitätsbericht verwenden können.

### Filter im Konferenzaktivitätsbericht

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
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall <strong>Täglich</strong> mit dem Startdatum 7/8/2012 und dem Enddatum 28/9/2012 ausgewählt haben, werden Daten für die Tage 7/8/2012 12:00 Uhr bis 7/9/2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Bericht nach:</strong></p></td>
<td><p>Gibt die Werte an, die in dem Bericht verwendet werden sollen. Sie können einen der folgenden Werte auswählen:</p>
<ul>
<li><p>Teilnehmeranzahl</p></li>
<li><p>Teilnehmerminuten</p></li>
<li><p>Konferenzanzahl</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metriken für Konferenzen nach Pool

In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Pool angegeben werden.

### Metriken für Konferenzen nach Pool

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
<td><p>Name des in der Konferenz verwendeten Registrierungspools oder Edgeservers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.</p></td>
</tr>
</tbody>
</table>


## Metriken für Konferenzen nach Servertyp

In der folgenden Tabelle werden die Metriken aufgelistet, die im Konferenzaktivitätsbericht für jeden Servertyp angegeben werden.

### Metriken für Konferenzen nach Servertyp

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
<td><p><strong>Konferenzservertyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Typ des Servers, der in der Konferenz verwendet wird, in der Regel einer der folgenden:</p>
<ul>
<li><p>Webkonferenzserver</p></li>
<li><p>Sofortnachrichten-Konferenzserver</p></li>
<li><p>Telefonkonferenzserver</p></li>
<li><p>A/V-Konferenzserver</p></li>
<li><p>Anwendungsfreigabe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Datum/Uhrzeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitpunkt (Datum und Uhrzeit), zu dem die Konferenz stattfand.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtzahl der Teilnehmer, der Teilnehmerminuten oder der Konferenzen.</p></td>
</tr>
</tbody>
</table>

