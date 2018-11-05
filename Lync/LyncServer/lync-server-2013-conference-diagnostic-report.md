---
title: 'Lync Server 2013: Diagnosebericht über die Konferenz'
TOCTitle: Diagnosebericht über die Konferenz
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615042(v=OCS.15)
ms:contentKeyID: 49295780
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Diagnosebericht über die Konferenz in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Diagnosebericht über die Konferenz bietet Informationen zu erfolgreich durchgeführten Konferenzsitzungen und Fehlern bei Konferenzsitzungen. Beachten Sie, dass in Microsoft Lync Server zwischen verschiedenen Fehlern unterschieden wird:

  - **Erwarteter Fehler** . Ein erwarteter Fehler ist typischerweise ein rein technischer Fehler. Ein Beispiel: Angenommen, eine Person startet eine Konferenz, legt aber auf, bevor andere Personen der Konferenz beigetreten sind. Das ist technisch gesehen ein Fehler: die Konferenz wurde initiiert, aber nicht abgeschlossen. Allerdings wäre das ein Fehler, den Sie durchaus erwarten würden. Bricht nämlich der Organisator die Konferenz ab, bevor andere Personen teilnehmen können, würden Sie die Konferenz nicht als abgeschlossen betrachten.

  - **Unerwarteter Fehler** . Wie der Name schon sagt, ist ein unerwarteter Fehler ein Fehler, dessen Auftreten Sie in den gegebenen Umständen nicht erwarten würden. Ein Beispiel: Angenommen, eine Konferenz konnte nicht durchgeführt werden, weil die Besprechungsrichtlinie des Organisators nicht abgerufen werden konnte. Das ist ein unerwarteter Fehler, denn die Besprechungsrichtlinie eines Benutzers sollte grundsätzlich immer abgerufen werden können.

Beachten Sie, dass die Summe aus den Werten für Erfolge, erwartete Fehler und unerwartete Fehler nicht immer mit der Angabe für **Sitzungen insgesamt** übereinstimmt. Beispielsweise können in dem Bericht folgende Werte angegeben werden:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Erfolge</th>
<th>Erwartete Fehler</th>
<th>Unerwartete Fehler</th>
<th>Sitzungen insgesamt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Wenn Sie 2.024 + 469 + 16 addieren, ergibt das insgesamt 2.509 Sitzungen, aber in der Spalte **Sitzungen insgesamt** wird 2.521 angezeigt. Die "fehlenden" 12 Sitzungen sind Sitzungen, die vom System nicht als erfolgreich oder fehlerhaft kategorisiert werden konnten. Das ist manchmal der Fall, wenn von einem Drittanbieterprodukt ein neuer Diagnosecode eingeführt wird, der im Monitoring Server nicht bekannt ist. In einer solchen Situation können Aufrufe, die mit diesem Produkt ausgeführt werden und für die dieser Diagnosecode gemeldet wird, nicht immer eindeutig als Erfolg, erwarteter Fehler oder unerwarteter Fehler kategorisiert werden.

## Öffnen des Diagnoseberichts über die Konferenz

Auf den Diagnosebericht über die Konferenz greifen Sie über die Startseite **Monitoring Server-Berichte** zu. Den [Bericht über Fehlerverteilung in Lync Server 2013](lync-server-2013-failure-distribution-report.md) können Sie öffnen, indem Sie auf eine der folgenden Metriken klicken:

  - Anzahl der unerwarteten Fehler

  - Anzahl der erwarteten Fehler

## Optimales Nutzen des Diagnoseberichts über die Konferenz

Der Diagnosebericht über die Konferenz enthält eine Reihe von Diagrammen. Jede der Spalten in einem Diagramm ist ein Hyperlink. Wenn Sie auf eine Spalte klicken, rufen Sie einen [Bericht über Fehlerverteilung in Lync Server 2013](lync-server-2013-failure-distribution-report.md) mit einer Aufschlüsselung für diese Zeitspanne und diesen Konferenztyp auf.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die Daten im Diagnosebericht über Konferenzen nach Kriterien wie etwa dem Konferenztyp (z. B. Konferenzzustandsobjekt-Sitzung) oder dem für die Konferenz verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Diagnosebericht über die Konferenz verwenden können.

### Filter im Diagnosebericht über die Konferenz

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
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall <strong>Täglich</strong> mit dem Startdatum 8/7/2012 und dem Enddatum 9/28/2012 ausgewählt haben, werden Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konferenzsitzungen</strong></p></td>
<td><p>Gibt den Typ der Konferenzsitzung an. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Konferenzzustandsobjekt-Sitzungen</p></li>
<li><p>Alle MCU-Sitzungen</p></li>
<li><p>Sofortnachrichtenkonferenzen</p></li>
<li><p>Anwendungsfreigabe</p></li>
<li><p>A/V-Konferenzen</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Diagnosebericht über die Konferenz für jeden Konferenzsitzungstyp angegeben werden.

### Metriken im Diagnosebericht über die Konferenz

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
<td><p><strong>Anzahl der erfolgreichen Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der erfolgreich durchgeführten Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erfolgreichen Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Konferenzen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, in denen ein &quot;erwarteter Fehler&quot; aufgetreten ist.</p>
<p>Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf <strong>Nicht stören</strong> festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Konferenzen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, in denen ein &quot;unerwarteter Fehler&quot; aufgetreten ist.</p>
<p>Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Konferenzen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, einschließlich Konferenzen ohne Fehler, Konferenzen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Konferenzen.</p></td>
</tr>
</tbody>
</table>

