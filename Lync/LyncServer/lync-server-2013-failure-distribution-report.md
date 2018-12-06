---
title: 'Lync Server 2013: Bericht über Fehlerverteilung'
TOCTitle: Bericht über Fehlerverteilung
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558635(v=OCS.15)
ms:contentKeyID: 49293658
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über Fehlerverteilung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht über Fehlerverteilung ordnet Sitzungen, bei denen ein Fehler aufgetreten ist, in folgende Kategorien ein:

  - Häufigste Diagnosegründe

  - Häufigste Modalitäten

  - Häufigste Pools

  - Häufigste Quellen

  - Häufigste Komponenten

  - Häufigste Absenderbenutzer

  - Häufigste Empfängerbenutzer

  - Häufigste Absenderbenutzer-Agents

Anhand dieser Kategorien können Sie genau bestimmen, wo ein Problem aufgetreten ist und in einigen Fällen auch die Ursache feststellen. Angenommen, an einem Tag sind bei 242 Audio- und Videositzungen Fehler aufgetreten. Wenn Sie sich den Bericht über Fehlerverteilung ansehen, stellen Sie möglicherweise fest, dass 237 dieser gescheiterten Sitzungen im Dublin-Pool aufgetreten sind. Dies gibt Ihnen einen guten Ausgangspunkt zum Einkreisen der Ursache und Diagnostizieren dieser Fehler. Wenn Sie in der Kategorie **Häufigste Pools** auf den Dublin-Pool klicken, sehen Sie einen Bericht über Fehlerverteilung nur für diesen Pool. Sie können dann mit der Analyse des Dublin-Pools beginnen, um herauszufinden, warum es so viele Schwierigkeiten gab.

## Anzeigen des Berichts über Fehlerverteilung

Sie können auf den Bericht über Fehlerverteilung von einem beliebigen der folgenden Berichte zugreifen, indem Sie entweder auf die Metrik **Anzahl der erwarteten Fehler** oder **Anzahl der unerwarteten Fehler** klicken:

  - [Bericht über häufigste Fehler in Lync Server 2013](lync-server-2013-top-failures-report.md)

  - [Diagnosebericht über die Konferenz in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)

  - [Diagnosebericht über Peer-zu-Peer-Aktivität in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

Vom Bericht über Fehlerverteilung können Sie auf eine der folgenden Metriken klicken, um den [Fehlerlistenbericht in Lync Server 2013](lync-server-2013-failure-list-report.md) anzuzeigen:

  - Wichtigste Diagnosegründe (Sitzungen)

  - Wichtigste Modalitäten (Sitzungen)

  - Wichtigste Pools (Sitzungen)

  - Wichtigste Quellen (Sitzungen)

  - Wichtigste Komponenten (Sitzungen)

  - Wichtigste "Von Benutzer" (Sitzungen)

  - Wichtigste "An Benutzer" (Sitzungen)

  - Wichtigste "Von Benutzeragenten" (Sitzungen)

## Verwenden des Berichts über Fehlerverteilung

Je nach Ihrer Monitorgröße und Bildschirmauflösung werden einige Daten im Bericht über Fehlerverteilung möglicherweise abgeschnitten, wenn Sie auf dem Bildschirm angezeigt werden. Dies ist insbesondere bei Agent-Benutzern der Fall, die sehr lange Bezeichnungen haben können. Auf dem Bildschirm wird ein Benutzer-Agent mit dem Namen "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" z. B. nur teilweise angezeigt:

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...

Sie können aber die gesamte Bezeichnung anzeigen, indem Sie die Maus über den gekürzten Wert halten.

Eine interessante Metrik, nach der Sie im Bericht über Fehlerverteilung filtern können, ist die Diagnose-ID. Wenn Sie dieselbe Diagnose-ID auch in anderen Berichten sehen, können Sie nach dieser ID im Bericht über Fehlerverteilung filtern. Sie erhalten dann einen sehr detaillierten Einblick darüber, wo genau und wie oft diese ID in einer gescheiterten Sitzung gemeldet wurde.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Fehlerverteilung können Sie beispielsweise nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder nach der Diagnose-ID der jeweiligen fehlgeschlagenen Sitzung filtern.

In der folgenden Tabelle sind die Filter aufgeführt, die Sie im Bericht über Fehlerverteilung verwenden können.

### Bericht über Fehlerverteilung - Filter

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
<p>7/7/12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>3/7/12</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 PM</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>3/7/12</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) des Registrierungsstellenpools oder des Edgeserver. Sie können entweder einen einzelnen Pool auswählen oder auf <strong>[Alle]</strong> klicken, um Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Aktivitätstyp, nach dem gefiltert wird. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Peer-zu-Peer</p></li>
<li><p>Konferenz</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungskategorie</strong></p></td>
<td><p>Gibt an, ob die betreffende Aktivität erfolgreich war oder nicht. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Erfolg</p></li>
<li><p>Erwarteter Fehler</p></li>
<li><p>Unerwarteter Fehler</p></li>
</ul>
<p>Ein &quot;erwarteter Fehler&quot; ist ein Fehler, dessen Auftreten erwartet wird. Wenn beispielsweise ein Benutzer seinen Status auf <strong>Nicht stören</strong> festgelegt hat, ist zu erwarten, dass jeder Anruf an diesen Benutzer fehlschlägt. Ein &quot;unerwarteter Fehler&quot; ist ein Fehler, der in einem System auftritt, das abgesehen davon anscheinend intakt ist. Beispielsweise sollte ein Anruf nicht beendet werden, wenn der Anrufer in der Warteschleife platziert ist. Geschieht dies jedoch, würde dieser Vorgang als unerwarteter Fehler gekennzeichnet werden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten Diagnosegründe

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf der am häufigsten berichteten Diagnose-ID.

### Metriken für die wichtigsten Diagnosegründe

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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf Diagnose-IDs. Die Diagnose-ID ist eine eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste Diagnosegründe</strong></p></td>
<td><p>Nein</p></td>
<td><p>In einer Sitzung generierte Diagnose-ID.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der fehlgeschlagenen Sitzungen, für die die angegebene Diagnose-ID generiert wurde.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten Modalitäten

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Sitzungsmodalitäten, bei denen die meisten Fehler auftraten.

### Metriken für die wichtigsten Modalitäten

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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung basierend auf der gescheiterten Sitzung und auf dem Sitzungstyp (z. B. Audio-/Video-Konferenz oder Peer-zu-Peer-Dateiübertragungssitzung).</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste Modalitäten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Sitzungstyp</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der fehlgeschlagenen Sitzungen mit der angegebenen Modalität.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten Pools

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Pools, bei denen die meisten Fehler auftraten.

### Metriken für die wichtigsten Pools

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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung der gescheiterten Sitzungen basierend auf dem Registrierungsstellenpool-Pool oder Edgeserver, auf dem die Sitzung abgehalten wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste Pools</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name des Registrierungsstellenpools oder Edgeservers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der Sitzungen mit Fehlern pro Registrierungsstellenpool oder Edgeserver.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten Quellen

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Computern, bei denen die meisten Fehler auftraten.

### Metriken für die wichtigsten Quellen

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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung der fehlgeschlagenen Sitzungen pro Computer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste Quellen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name des Computers, auf dem die Sitzung fehlgeschlagen ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der fehlgeschlagenen Sitzungen pro Computer.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten Komponenten

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Microsoft Lync Server 2010-Komponenten, bei denen die meisten Fehler auftraten.

### Metriken für die wichtigsten Komponenten

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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung der Sitzungen mit Fehlern basierend auf der Lync Server 2010-Komponente (z. B. ExumRouting, GroupChat oder MediationServer).</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste Komponenten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name der für die fehlgeschlagene Sitzung verwendeten Komponente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der fehlgeschlagenen Sitzungen pro Komponente.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten "Von Benutzer"

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Benutzern, bei denen beim Versuch, jemanden anzurufen, die meisten Fehler auftraten (als "Von Benutzer" bezeichnet).

### Metriken für die wichtigsten "Von Benutzer"

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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf dem Benutzer, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste &quot;Von Benutzer&quot;</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der fehlgeschlagenen Sitzungen pro Benutzer.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten "An Benutzer"

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf den Benutzern, bei denen die meisten Fehler auftraten, wenn sie von einem anderen Benutzer angerufen wurden (als "An Benutzer" bezeichnet).


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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf dem Benutzer, der die Sitzung initiiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste &quot;An Benutzer&quot;</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers, der den Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der fehlgeschlagenen Sitzungen pro Benutzer.</p></td>
</tr>
</tbody>
</table>


## Metriken für die wichtigsten Benutzer-Agents

In der folgenden Tabelle sind die im Bericht über Fehlerverteilung enthaltenen Informationen aufgeführt, basierend auf der Endpunktsoftware, bei der die meisten Fehler auftraten.

### Metriken für die wichtigsten Benutzer-Agents

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
<td><p>Nein</p></td>
<td><p>Relative Rangordnung der fehlgeschlagenen Sitzungen basierend auf dem in der Sitzung verwendeten Benutzer-Agent (Software), z. B. RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>Wichtigste Benutzer-Agents</strong></p></td>
<td><p>Nein</p></td>
<td><p>Name des in der fehlgeschlagenen Sitzung verwendeten Benutzer-Agent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtanzahl der fehlgeschlagenen Sitzungen pro Benutzer-Agent.</p></td>
</tr>
</tbody>
</table>

