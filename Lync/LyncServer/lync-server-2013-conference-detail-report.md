---
title: Konferenzdetailbericht
TOCTitle: Konferenzdetailbericht
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204728(v=OCS.15)
ms:contentKeyID: 49293361
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konferenzdetailbericht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.

## Zugreifen auf den detaillierten Konferenzbericht

Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:

  - [Bericht über Anrufsteuerung in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (durch Klicken auf die Metrik "Detail" für eine Konferenz)

  - [Fehlerlistenbericht in Lync Server 2013](lync-server-2013-failure-list-report.md) (durch Klicken auf die Metrik "Konferenz")

  - [Bericht über Benutzeraktivität in Lync Server 2013](lync-server-2013-user-activity-report.md) (durch Klicken auf die Metrik "Konferenz-URI")

Über den detaillierten Konferenzbericht können Sie auf den [Diagnosebericht in Lync Server 2013](lync-server-2013-diagnostic-report.md) zugreifen, indem Sie auf die Metrik für den Diagnosebericht (Detail) klicken.

## Filter

Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.

## Metriken

In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.

### Konferenzinformationen – Metriken

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
<td><p></p></td>
<td><p>Der Konferenz zugewiesener URI. Beispiel:</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool-FQDN</strong></p></td>
<td><p></p></td>
<td><p>Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beginn</strong></p></td>
<td><p></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisator</strong></p></td>
<td><p></p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeit</strong></p></td>
<td><p></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.

### Konferenzteilnahme – Metriken

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
<td><p><strong>User</strong></p></td>
<td><p></p></td>
<td><p>SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong></p></td>
<td><p></p></td>
<td><p>Rolle (z. B. Referent) des Konferenzteilnehmers.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Verbindung</strong></p></td>
<td><p></p></td>
<td><p>Netzwerkverbindungen (in der Regel &quot;From Internal&quot; oder &quot;From External&quot;) des Teilnehmers.</p></td>
</tr>
<tr class="even">
<td><p>Zeitpunkt des Beitritts</p></td>
<td><p></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Beendigung</strong></p></td>
<td><p></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Benutzer-Agent</strong></p></td>
<td><p></p></td>
<td><p>ID für die vom Endpunkt des Teilnehmers verwendete Software.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnoseberichte</strong></p></td>
<td><p></p></td>
<td><p>Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzmodalitäten des detaillierten Konferenzberichts aufgeführt.

### Konferenzmodalitäten – Metriken

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
<td><p><strong>User</strong></p></td>
<td><p></p></td>
<td><p>SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zeitpunkt des Beitritts</strong></p></td>
<td><p></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Beendigung</strong></p></td>
<td><p></p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzserver-URI</strong></p></td>
<td><p></p></td>
<td><p>URI für den in der Konferenz verwendeten Konferenzserver.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnoseberichte</strong></p></td>
<td><p></p></td>
<td><p>Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</p></td>
</tr>
</tbody>
</table>

