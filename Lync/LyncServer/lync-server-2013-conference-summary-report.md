---
title: 'Lync Server 2013: Zusammenfassender Konferenzbericht'
TOCTitle: Zusammenfassender Konferenzbericht
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558656(v=OCS.15)
ms:contentKeyID: 49294201
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusammenfassender Konferenzbericht in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der "Zusammenfassende Konferenzbericht" gibt Ihnen einen Überblick über Ihre Onlinekonferenzsitzungen. Zu einer Konferenz gehören für gewöhnlich mehr als 2 Benutzer, und es ist die Nutzung der Konferenzdienste von Microsoft Lync Server 2013 erforderlich. Im Vergleich dazu sind an einer Peer-zu-Peer-Sitzung nur 2 Benutzer beteiligt, ohne dass die Konferenzdienste von Lync Server benötigt werden. Über Peer-zu-Peer-Aktivitäten wird in der [Zusammenfassender Bericht über Peer-zu-Peer-Aktivität in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) Bericht erstattet.

Der "Zusammenfassende Konferenzbericht" gibt nicht nur Aufschluss darüber, wie viele Konferenzen innerhalb eines bestimmten Zeitraums (stündlich, täglich, wöchentlich, monatlich) abgehalten wurden, sondern auch, wie viele Personen und wie viele eindeutige Konferenzorganisatoren an diesen Konferenzen beteiligt waren.

Ein "eindeutiger” Organisator kann jeder sein, der mindestens eine Konferenz plant. Wenn zum Beispiel Pilar Ackerman eine Konferenz plant, zählt sie als ein eindeutiger Organisator. Wenn Ken Myer 148 Konferenzen plant, zählt auch er als ein eindeutiger Organisator. So sind in der Tabelle unten 8 geplante Konferenzen aufgeführt, jedoch nur 3 eindeutige Organisatoren (Ken Myer, Pilar Ackerman und David Ahs).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Konferenzorganisator</th>
<th>Konferenzdatum</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Der "Zusammenfassende Konferenzbericht" zeigt auch an, bei wie vielen Konferenzen Audio- und/oder Videofunktionen genutzt wurden.

## Zugriff auf den "Zusammenfassenden Konferenzbericht"

Auf den "Zusammenfassenden Konferenzbericht" können Sie über die Startseite "Monitoring-Berichte" zugreifen. Sie können weiter zum Konferenzaktivitätsbericht aufschlüsseln, indem Sie auf eine der folgenden Metriken klicken:

  - Konferenzen insgesamt

  - Teilnehmer insgesamt

## Optimale Nutzung des "Zusammenfassenden Konferenzberichts"

Unten im Bericht können Sie die Gesamtwerte der meisten im "Zusammenfassenden Konferenzbericht" verwendeten Metriken finden. Führen Sie einen Bildlauf nach unten durch, wenn Sie zum Beispiel wissen möchten, wie viele Konferenzen insgesamt in einem bestimmten Zeitraum abgehalten wurden oder wie viele Personen an diesen Konferenzen teilgenommen haben. Eine Metrik, zu der es unten im Bericht keine Gesamtsumme gibt, ist die Zahl aller eindeutigen Konferenzorganisatoren. Der Grund dafür lautet: Angenommen, Sie schauen die Daten eines Monats durch. An einem Tag gab es 34 eindeutige Konferenzorganisatoren, an einem anderen dagegen 27. Bedeutet das nun, dass es in diesen zwei Tagen insgesamt 61 eindeutige Konferenzorganisatoren gab? Nicht unbedingt. Schließlich können einige oder alle der 27 Organisatoren des ersten Tages auch zu den 34 Personen gehören, die an dem zweiten Tag Konferenzen organisiert haben. So haben zum Beispiel in diesem einfachen Bericht die Organisatoren Ken Myer und Pilar Ackerman sowohl am 7/7/2012 als auch am 7/2/2012 Konferenzen geplant:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Konferenzorganisator</th>
<th>Konferenzdatum</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Wenn Sie genauer wissen möchten, wie viele eindeutige Konferenzorganisatoren es insgesamt gab, ändern Sie einfach den Zeitraum. Schauen Sie zum Beispiel die Daten nach Monaten anstatt nach Tagen aufgeschlüsselt durch.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Konferenzbericht festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Konferenzbericht verwenden können.

### Filter im Zusammenfassenden Konferenzbericht

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
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall &quot;Täglich&quot; mit dem Startdatum &quot;7/7/2012&quot; und dem Enddatum &quot;9/28/2012&quot; ausgewählt haben, werden Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2011 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Konferenzbericht angegeben werden.

### Metriken im Zusammenfassenden Konferenzbericht

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
<td><p>Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall &quot;Täglich&quot; verwenden und auf &quot;7/7/2012&quot; klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen (unabhängig vom Konferenztyp), die stattfanden. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Teilnehmer insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Personen, die an den Konferenzen teilnahmen. Wenn Sie auf dieses Element klicken, wird der Konferenzaktivitätsbericht für die ausgewählte Zeitspanne eingeblendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche Anzahl der Teilnehmer pro Konferenz</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Anzahl der Personen, die an einer Konferenz teilnahmen. Errechnet sich durch Dividieren der Gesamtzahl der Konferenzen durch die Gesamtzahl der Teilnehmer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V-Konferenzen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen mit Audio oder Video.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gesamtdauer der A/V-Konferenzen in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Minuten, die für Konferenzen mit Audio bzw. aufgewendet wurden.</p>
<p>Die Metrik „Gesamtdauer der A/V-Konferenzen in Minuten“ fasst alle Audio-/Videokonferenztypen zusammen, darunter: A/V-Konferenzen, Chatkonferenzen, Konferenzen mit Anwendungsfreigabe, Datenkonferenzen und PSTN-Konferenzen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Minuten, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Benutzer verbringt 5 Minuten in einer A/V-Konferenz, und ein zweiter Benutzer verbringt 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 5 + 3 = 8 Minuten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche Dauer der A/V-Konferenzen in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Anzahl der Minuten pro A/V-Konferenz.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Eindeutige Konferenzorganisatoren insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die mindestens eine Konferenz organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenznachrichten insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Sofortnachrichten, die während Konferenzen gesendet wurden.</p></td>
</tr>
</tbody>
</table>

