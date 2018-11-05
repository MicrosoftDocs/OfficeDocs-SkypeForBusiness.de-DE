---
title: 'Lync Server 2013: Bericht über Anrufsteuerung'
TOCTitle: Bericht über Anrufsteuerung
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615043(v=OCS.15)
ms:contentKeyID: 49295784
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht über Anrufsteuerung bietet Informationen über Peer-zu-Peer- und Konferenzsitzungen, die unter Beschränkungen durchgeführt wurden, die von der Anrufsteuerung implementiert werden. Die in Microsoft Lync Server 2010 eingeführte Anrufsteuerung bietet Administratoren eine Möglichkeit, Kommunikationssitzungen auf der Grundlage von Bandbreitenbeschränkungen zuzulassen (oder nicht zuzulassen). Beispielsweise kann ein Administrator Richtlinien erstellen, die die verfügbare Bandbreite für Sprach- und Videoanrufe beschränken. Sobald diese Bandbreitengrenze erreicht ist, können keine neuen Sprach- oder Videoanrufe mehr getätigt werden, bis einer der aktuellen Anrufe beendet worden ist und damit die erforderlichen Netzwerkressourcen freigegeben worden sind.

## Öffnen des Berichts über Anrufsteuerung

Auf den Bericht über Anrufsteuerung greifen Sie über die Startseite **Monitoring Server-Berichte** zu. Von diesem Bericht aus können Sie einen Drilldown zu folgenden weiteren Berichten durchführen:

  - Konferenzdetailbericht - Zum Öffnen dieses Berichts klicken Sie auf die Metrik **Details** für eine Konferenzsitzung.

  - Detailbericht über Peer-zu-Peer-Sitzungen - Zum Öffnen dieses Berichts klicken Sie auf die Metrik **Details** für eine Peer-zu-Peer-Sitzung.

## Optimales Nutzen des Berichts über Anrufsteuerung

Zum Abrufen einer Liste der Anrufe, bei denen wegen nicht ausreichender Bandbreite ein Fehler auftrat, wählen Sie in der Dropdownliste **Anrufkategorie** den Eintrag **Anrufe, die aufgrund der Anrufsteuerung abgelehnt werden** aus. Die meisten der zurückgegebenen Anrufe haben wahrscheinlich die Diagnose-ID 5:

Nicht genügend Bandbreite zum Herstellen der Sitzung. PSTN-Umleitung wird versucht.

Dies weist darauf hin, dass Beschränkungen der Anrufsteuerung verhindert haben, dass der Anruf im VoIP-Netzwerk ausgeführt werden konnte.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der Anrufsteuerungsbericht ermöglicht Ihnen beispielsweise das Filtern von Anrufen nach dem Benutzer, der den Anruf initiiert hat oder nach dem angerufenen Benutzer. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Anrufsteuerungsbericht verwenden können.

### Anrufsteuerungsbericht - Filter

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
<p>17.7.2012 13:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>17.7.2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>13.07.2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>17.7.2012 13:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>17.7.2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>13.07.2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Aktivitätstyp. Wählen Sie eine der folgenden Aktivitäten aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Peer-zu-Peer</p></li>
<li><p>Konferenz</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufkategorie</strong></p></td>
<td><p>Gibt den Grund für die Verwendung der Anrufsteuerung bei einem Anruf an. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Anruf durch Anrufsteuerung abgelehnt</p></li>
<li><p>Anrufe durch Anrufsteuerung über PSTN umgeleitet</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metriken für Peer-zu-Peer-Sitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Peer-zu-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.

### Metriken für Peer-zu-Peer-Sitzungen

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
<td><p><strong>Detail</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, zeigt der Bericht einen detaillierten Peer-to-Peer-Sitzungsbericht für die angegebene Sitzung an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Von Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der den Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalitäten</strong></p></td>
<td><p>Ja</p></td>
<td><p>Kommunikationsmodalitäten (z. B. Audio und Video), die bei der Sitzung verwendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Einladung</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Sitzungseinladung an den Benutzer gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Antwortzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


## Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.

### Metriken für Konferenzsitzungen

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
<td><p><strong>Konferenz-URI</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht die einzelnen Konferenzteilnehmer an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisator</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Ja</p></td>
<td><p>In der Konferenz verwendeter Edgeserver.</p></td>
</tr>
<tr class="even">
<td><p><strong>Beginn</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</p></td>
</tr>
</tbody>
</table>


## Metriken für einzelne Konferenzteilnehmer

In der folgenden Tabelle sind die im Anrufsteuerungsbericht für einzelne Konferenzteilnehmer enthaltenen Informationen aufgeführt.

### Metriken für einzelne Konferenzteilnehmer

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
<td><p><strong>Rolle</strong></p></td>
<td><p>Nein</p></td>
<td><p>Rolle (z. B. Referent) des Konferenzteilnehmers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Teilnehmer</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Konferenzteilnehmers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Verbindung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Netzwerkverbindungen (in der Regel &quot;From Internal&quot; oder &quot;From External&quot;) des Teilnehmers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Konferenztyp (z. B. A/V-Konferenzen).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt des Beitritts</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zeitpunkt der Beendigung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>

