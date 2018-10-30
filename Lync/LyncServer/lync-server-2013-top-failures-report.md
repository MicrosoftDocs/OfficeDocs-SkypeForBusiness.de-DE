---
title: 'Lync Server 2013: Bericht über häufigste Fehler'
TOCTitle: Bericht über häufigste Fehler
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558640(v=OCS.15)
ms:contentKeyID: 49293836
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über häufigste Fehler in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht über häufigste Fehler bietet einen Überblick über die am häufigsten gemeldeten Fehler mit Trenddarstellung.

  - **Diagnose-ID** . Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.

  - **Antwortcode** . Antwortcodes werden in SIP-Kommunikationssitzungen verwendet, um auf SIP-Anforderungen zu reagieren. Angenommen, Ken Myer sendet die INVITE-Anfrage an Pilar Ackerman (d. h., Ken Myer ruft Pilar Ackerman an). Wenn Pilar antwortet, sendet ihr Telefon den Antwortcode 200 (OK) und teilt Kens Telefon dadurch mit, dass Pilar geantwortet hat. Der Bericht über häufigste Fehler beinhaltet nur Antwortcodes, die als Reaktion auf einen fehlerhaften Anruf gesendet wurden. Lync Server verfolgt nicht alle Antwortcodes, die während eines Anrufs ausgegeben werden.

Informationen werden nicht nur für die Gesamtzahl an Sitzungen, in denen ein Fehler aufgetreten ist, gemeldet, sondern auch für die Gesamtzahl der Benutzer, die von den Fehlern betroffen waren.

## Zugriff auf den Bericht über häufigste Fehler

Der Zugriff auf den Bericht über häufigste Fehler erfolgt von der Überwachungsberichte-Startseite aus. Durch Klicken auf die Metrik "Gemeldete Sitzungen" gelangen Sie zum [Bericht über Fehlerverteilung in Lync Server 2013](lync-server-2013-failure-distribution-report.md).

## Beste Nutzung des Berichts häufigster Fehler

Der Bericht häufigster Fehler ist in einer Hinsicht ungewöhnlich: Er ermöglicht Ihnen gleichzeitig, nach bis zu 5 Diagnose-IDs zu filtern (normalerweise kann nur nach einem Element gleichzeitig gefiltert werden, z. B. nach der SIP-Adresse des Benutzers). Um nach mehreren Diagnose-IDs zu filtern, geben Sie einfach alle IDs durch Kommas getrennt in das Feld "Diagnose-IDs" ein (Sie können, müssen aber nicht nach jedem Komma ein Leerzeichen einfügen). Beispiel:

1011, 2412, 1033, 52116, 1008

Wenn Sie dies tun, werden nur fehlerhafte Anrufe, die mindestens eine dieser fünf Diagnose-IDs gemeldet haben, angezeigt.

Wenn Sie Ihre Maus über einen Antwortcode bewegen, wird eine QuickInfo angezeigt, die Ihnen mitteilt, was der jeweilige Antwortcode bedeutet. Wenn Sie beispielsweise die Maus über den Antwortcode 486 bewegen, wird folgende Meldung angezeigt:

Ausgelastet.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie die zurückgegebenen Daten im Bericht über häufigste Fehler nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder dem SIP-Antwortcode für die fehlgeschlagene Sitzung filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Ereignisse nach Stunde, Tag, Woche oder Monat zusammengefasst

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über häufigste Fehler verwenden können.

### Filter im Bericht über häufigste Fehler

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
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Peer-zu-Peer</p></li>
<li><p>Konferenz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalität</strong></p></td>
<td><p>Derzeit ist nur die Option <strong>[Alle]</strong> verfügbar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Kategorie</strong></p></td>
<td><p>Der Typ des aufgetretenen Fehlers. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Erwartete und unerwartete Fehler</p></li>
<li><p>Unerwarteter Fehler</p></li>
</ul>
<p>Ein &quot;erwarteter Fehler&quot; ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf <strong>Nicht stören</strong> festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt. Ein &quot;unerwarteter Fehler&quot; ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>Der SIP-Antwortcode, der gesendet wird, wenn die Konferenz fehlschlägt. Geben Sie den vollständigen Antwortcode ein. Beispiel:</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über häufigste Fehler angegeben werden.

### Metriken im Bericht über häufigste Fehler

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
<td><p><strong>Rang</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der relative Rang basierend auf der Anzahl der gemeldeten Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gemeldete Sitzungen</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die Gesamtzahl der fehlerhaften Sitzungen basierend auf der Diagnose-ID und dem SIP-Antwortcode.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Betroffene Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die Gesamtzahl der Benutzer, die von der fehlerhaften Sitzung betroffen waren.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fehlerinformationen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Genaue Angaben zu dem Fehler, u. a. die Diagnose-ID, der SIP-Antwortcode und eine Beschreibung der Ursache des Sitzungsfehlers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Trend in der Vergangenheit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eine grafische Darstellung der fehlerhaften Sitzungen über einen bestimmten Zeitraum.</p></td>
</tr>
</tbody>
</table>

