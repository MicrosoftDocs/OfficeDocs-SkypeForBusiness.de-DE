---
title: 'Lync Server 2013: Diagnosebericht über Peer-zu-Peer-Aktivität'
TOCTitle: Diagnosebericht über Peer-zu-Peer-Aktivität
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558602(v=OCS.15)
ms:contentKeyID: 49292993
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Diagnosebericht über Peer-zu-Peer-Aktivität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Diagnosebericht über Peer-zu-Peer-Aktivitäten enthält Informationen dazu, ob die Peer-zu-Peer-Sitzungen erfolgreich waren oder ob Fehler aufgetreten sind. Beachten Sie, dass in Microsoft Lync Server 2013 zwischen unterschiedlichen Fehlerarten unterschieden wird:

  - **Erwarteter Fehler** : Ein erwarteter Fehler ist in der Regel nur im technischen Sinne ein Fehler. Angenommen, Sie rufen eine Person an, die jedoch nicht im Büro ist und den Anruf nicht annehmen kann. Da der Anruf nicht angenommen wurde, wird der Anruf im technischen Sinne als Fehler angesehen. Andererseits ist dies ein erwarteter Fehler: Microsoft Lync Server 2013 erwartet nicht, dass Sie Anrufe annehmen, wenn Sie dazu nicht in der Lage sind. Ebenso tritt ein erwarteter Fehler auf, wenn Sie versuchen, eine Chatnachricht an einen Benutzer zu senden, der gerade offline ist (oder nur über ein Telefon angemeldet ist, das keine Chatnachrichten unterstützt).

  - **Unerwarteter Fehler** : Ein unerwarteter Fehler ist genau das, was der Name aussagt: Ein Fehler, der gemessen an den Umständen nicht zu erwarten ist. Angenommen, Sie rufen eine Person an, und die Person kann den Anruf annehmen. Wenn Lync Server 2013 jedoch versucht, den Anruf an die Voicemail weiterzuleiten, tritt ein Fehler auf, da keine Verbindung mehr zu Exchange Unified Messaging besteht. Das ist ein unerwarteter Fehler: Es kann davon ausgegangen werden, dass Anrufe immer an die Voicemail weitergeleitet werden können. Allgemein gilt die Regel, dass unerwartete Fehler richtige Fehler sind: Es handelt sich dabei um Probleme, die durch Schulung der Benutzer oder ähnliche Maßnahmen nicht behoben werden können.

Beachten Sie, dass die Metriken für "Erfolg", "Erwarteter Fehler" und "Unerwarteter Fehler" nicht zwangsläufig identisch mit der Metrik unter "Sitzungen insgesamt" sind. In der obigen Abbildung sind beispielsweise die folgenden Werte enthalten:


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


Wenn Sie die Summe 2024 + 469 + 16 bilden, erhalten Sie ein Ergebnis von 2.509 Sitzungen. In der Spalte "Sitzungen insgesamt" sind jedoch 2.521 Sitzungen angegeben. Die "fehlenden" 12 Sitzungen sind Sitzungen, die vom System nicht als "erfolgreich" oder "nicht erfolgreich" eingestuft werden konnten. Dies kann vorkommen, wenn ein Drittanbieterprodukt einen neuen Diagnosecode einführt, der Lync Server nicht bekannt ist. In diesem Fall können Anrufe, die mit diesem Produkt getätigt und mit diesem Diagnosecode gemeldet werden, nicht immer als "Erfolg", "Erwarteter Fehler" oder "Unerwarteter Fehler" eingestuft werden.

## Zugreifen auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten

Auf den Diagnosebericht über Peer-zu-Peer-Aktivitäten greifen Sie über die Homepage für Überwachungsberichte zu. Sie können auf den [Bericht über Fehlerverteilung in Lync Server 2013](lync-server-2013-failure-distribution-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:

  - Anzahl der unerwarteten Fehler

  - Anzahl der erwarteten Fehler

## Optimales Verwenden des Diagnoseberichts über Peer-zu-Peer-Aktivitäten

Es gibt mehrere Möglichkeiten, wie Sie den Diagnosebericht über Peer-zu-Peer-Aktivitäten filtern können, aber die Filteroptionen sind standardmäßig ausgeblendet. Um die verfügbaren Filteroptionen anzuzeigen, klicken Sie im Berichtfenster oben rechts auf die Schaltfläche zum Ein- und Ausblenden der Parameter. Danach können Sie die Filteroptionen verwenden.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise ansehen. Beispielsweise können Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten nach Kriterien wie etwa Sitzungsmodalität (z. B. Sofortnachrichten, Dateiübertragung oder Anwendungsfreigabe) filtern. Sie können auch auswählen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle sind die Filter aufgelistet, die Sie im Diagnosebericht über Peer-zu-Peer-Aktivitäten verwenden können.

### Filter im Diagnosebericht über Peer-zu-Peer-Aktivitäten

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
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Modalität</strong></p></td>
<td><p>Gibt den Typ der Kommunikationsaktivität an, die stattgefunden hat. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Chat</p></li>
<li><p>Dateiübertragung</p></li>
<li><p>Anwendungsfreigabe</p></li>
<li><p>Audio</p></li>
<li><p>Video</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metrik (pro Modalität)

In der folgenden Tabelle sind die Metriken aufgelistet, die im Diagnosebericht über Peer-zu-Peer-Aktivitäten für jede Modalität angegeben werden.

### Metrik (pro Modalität)

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
<td><p>Die Gesamtzahl der erfolgreichen Peer-zu-Peer-Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erfolgreichen Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, die ohne nennenswerte Probleme ausgeführt wurden. Errechnet sich durch Dividieren der Anzahl der erfolgreichen Sitzungen durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, in denen ein &quot;erwarteter Fehler&quot; aufgetreten ist.</p>
<p>Ein erwarteter Fehler ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf <strong>Nicht stören</strong> festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der erwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein erwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der erwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anzahl der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, in denen ein &quot;unerwarteter Fehler&quot; aufgetreten ist.</p>
<p>Ein unerwarteter Fehler ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der unerwarteten Fehler</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein unerwarteter Fehler aufgetreten ist. Errechnet sich durch Dividieren der Anzahl der unerwarteten Fehler durch die Gesamtzahl der Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sitzungen, einschließlich Sitzungen ohne Fehler, Sitzungen mit Fehlern (sowohl erwarteten als auch unerwarteten) und nicht kategorisierten Sitzungen.</p></td>
</tr>
</tbody>
</table>

