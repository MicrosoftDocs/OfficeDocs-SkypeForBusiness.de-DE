---
title: 'Lync Server 2013: Detailbericht über Peer-zu-Peer-Sitzungen'
TOCTitle: Detailbericht über Peer-zu-Peer-Sitzungen
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558659(v=OCS.15)
ms:contentKeyID: 49294315
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Detailbericht über Peer-zu-Peer-Sitzungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Detailbericht über Peer-zu-Peer-Sitzungen gibt detaillierte Informationen über eine Peer-zu-Peer-Sitzung zurück. Wenn Sie beispielsweise eine Sofortnachrichtensitzung auswählen, gibt der Bericht Ihnen die Anzahl an Nachrichten an, die jeweils von den beiden an der Sitzung beteiligten Benutzern gesendet wurden.

## Zugriff auf den Detailbericht über Peer-zu-Peer-Sitzungen

Sie können über die folgenden Berichte (die alle über die Startseite für Überwachungsberichte aufgerufen werden können) auf den Detailbericht über Peer-zu-Peer-Sitzungen zugreifen:

  - Inventurbericht über IP-Telefone

  - Bericht über Benutzeraktivität

  - Bericht über Anrufsteuerung

  - Fehlerlistenbericht

Innerhalb des Detailberichts über Peer-zu-Peer-Sitzungen können Sie auf den [Diagnosebericht in Lync Server 2013](lync-server-2013-diagnostic-report.md) zugreifen, indem Sie auf die Metrik des Diagnoseberichts (Details) klicken. Sie können zudem auf den Bericht über häufigste Fehler zugreifen, indem Sie auf eine der folgenden beiden Metriken klicken:

  - Reaktion

  - Diagnose-ID

## Optimale Verwendung des Detailberichts über Peer-zu-Peer-Sitzungen

Der Detailbericht über Peer-zu-Peer-Sitzungen enthält zahlreiche Metriken, mit denen die Systemadministratoren möglicherweise zum Teil nicht vertraut sind. Häufig können Sie jedoch ein Tooltip mit einer kurzen Beschreibung der Metrik anzeigen, indem Sie den Mauszeiger über die Bezeichnung der jeweiligen Metrik bewegen.

Beachten Sie, dass die tatsächlichen Metriken, die in einem bestimmten Bericht angezeigt werden, von der ausgewählten Peer-zu-Peer-Sitzung abhängen. So wird für eine Audio-/Videositzung ein anderer Satz an Metriken ausgegeben als für eine Sofortnachrichtensitzung.

Sie können den Mauszeiger auch über die Antwortcode- und Diagnose-ID-Metriken bewegen, um eine Beschreibung der folgenden Werte anzuzeigen:

## Filter

Keine. Der Detailbericht über Peer-zu-Peer-Sitzungen kann nicht gefiltert werden.

## Sitzungsinformationen - Metriken

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen angegeben werden.

### Sitzungsinformationen - Metriken

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
<td><p><strong>Pool-FQDN</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers in der Sitzung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zeitpunkt der Einladung</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzungseinladung ursprünglich gesendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortzeit</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Von Benutzer</strong></p></td>
<td><p>SIP-Adresse des Benutzers, der den Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Von Benutzer-Agent</strong></p></td>
<td><p>Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Von Benutzer intern</strong></p></td>
<td><p>Gibt an, ob der Benutzer, der die Sitzung initiiert hat, am internen Netzwerk angemeldet war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Von Benutzer mit Telefonapparat</strong></p></td>
<td><p>Gibt an, ob der Endpunkt des Benutzers, der die Sitzung initiiert hat, mit seinem Desktoptelefon integriert ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sitzungspriorität</strong></p></td>
<td><p>Die der Sitzung zugewiesene Priorität. Gültige Prioritäten umfassen &quot;Unbekannt&quot;, &quot;Nicht dringend&quot;, &quot;Normal&quot;, &quot;Dringend&quot; und &quot;Notfall&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Front-End</strong></p></td>
<td><p>Name des in der Konferenz verwendeten Front-End-Servers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Erfassung</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzungsinformationen erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endzeit</strong></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.</p></td>
</tr>
<tr class="odd">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>To user agent</strong> (An Benutzer-Agent)</p></td>
<td><p>Die vom Endpunkt des Benutzers verwendete Software, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>An Benutzer intern</strong></p></td>
<td><p>Gibt an, ob der Benutzer, der zur Teilnahme an der Sitzung eingeladen wurde, am internen Netzwerk angemeldet war.</p></td>
</tr>
<tr class="even">
<td><p><strong>An Benutzer mit Telefonapparat</strong></p></td>
<td><p>Gibt an, ob der Endpunkt des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde, mit seinem Desktoptelefon integriert ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Wiederholungsversuch der Sitzung</strong></p></td>
<td><p>Gibt an, ob die Sitzung ein Wiederholungsversuch einer zuvor fehlgeschlagenen Sitzung ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Halten Sie den Mauszeiger über die ID-Nummer, um zusätzliche Information zu dieser ID anzuzeigen.</p></td>
</tr>
</tbody>
</table>


## Metriken für Modalitäten

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen zu jeder Sitzungsmodalität angegeben werden.

### Metriken für Modalitäten

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
<td><p><strong>Modalitäten</strong></p></td>
<td><p>Nein</p></td>
<td><p>In der Sitzung verwendete Modalitäten, z. B. Chat, Audio oder Dateiübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nachrichten &quot;Von Benutzer&quot;</strong></p></td>
<td><p>Nein</p></td>
<td><p>Anzahl der gesendeten Nachrichten des Benutzers, der die Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nachrichten &quot;An Benutzer&quot;</strong></p></td>
<td><p>Nein</p></td>
<td><p>Anzahl der gesendeten Nachrichten des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</p></td>
</tr>
</tbody>
</table>


## Metriken für Diagnoseberichte

In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen zu jeden Diagnosebericht angegeben werden.

### Metriken für Diagnoseberichte

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
<td><p>Klicken Sie auf dieses Element, um den Diagnosebericht für die Sitzung anzuzeigen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Berichtszeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit der Aufzeichnung des Berichts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anforderung</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Anforderungstyp, z. B. INVITE oder BYE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die einer SIP-Nachricht angefügt ist, die häufig nützliche Informationen für die Problembehandlung von Fehlern bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Inhaltstyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>In der Konferenz verwendeter Medieninhaltstyp. Ein gängiger Inhaltstyp ist beispielsweise &quot;Application/sdp&quot;. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen des Multimediasitzungsaufbaus verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Berichtet von</strong></p></td>
<td><p>Nein</p></td>
<td><p>Computer (d. h. Client oder Server), der das Problem berichtet hat.</p></td>
</tr>
</tbody>
</table>

