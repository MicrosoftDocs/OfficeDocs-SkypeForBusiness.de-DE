---
title: 'Lync Server 2013: ProgressReport-Tabelle'
TOCTitle: ProgressReport-Tabelle
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425864(v=OCS.15)
ms:contentKeyID: 49293699
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ProgressReport-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Fortschrittsberichte basieren auf Daten, die vom Client nach Abschluss eines Anrufs oder einer Sitzung in die Datenbank hochgeladen werden. Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von Lync Server 2013 für die Diagnose als nützlich eingestuft werden.

Die Felder "ErrorTime", "ErrorReportSeq" und "ProgressReportSeq" verweisen nicht zwangsläufig auf Fehler, aber zu Meldungen, die den Status von Anrufen oder Nachrichten angeben.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Datum und Uhrzeit des Fortschrittsfehlerberichts, der diesen Fortschrittsbericht enthält (siehe <a href="lync-server-2013-errorreport-table.md">ErrorReport-Tabelle in Lync Server 2013</a>).</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID, die zusammen mit <strong>ErrorTime</strong> und <strong>ProgressReportSeq</strong> zur eindeutigen Identifizierung eines Fortschrittsberichts verwendet wird. Weitere Informationen finden Sie unter <a href="lync-server-2013-errorreport-table.md">ErrorReport-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Die ID zur Kennzeichnung des Fehlerberichts. <strong>ErrorReporSeq</strong> wird in Verbindung mit <strong>ErrorTime</strong> verwendet, um einen Fehlerbericht eindeutig zu identifizieren. Weitere Informationen finden Sie unter <a href="lync-server-2013-errorreport-table.md">ErrorReport-Tabelle in Lync Server 2013</a>.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ID zur Identifikation des Fortschrittsberichts. Wird zusammen mit <strong>ErrorTime</strong> und <strong>ErrorReportSeq</strong> zur eindeutigen Identifikation eines Fortschrittsberichts verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Die Diagnose-ID des Fortschrittberichts.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Server, der den Fehlerbericht gesendet hat (wenn der Bericht von einer Fehlerkomponente gesendet wurde). Weitere Informationen finden Sie unter <a href="lync-server-2013-servers-table.md">Servers-Tabelle in Lync Server 2013</a>. Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Der Lync Server-Vorgang, auf den sich der Bericht bezieht. Weitere Informationen finden Sie in der Anwendungstabelle.</p></td>
</tr>
<tr class="even">
<td><p><strong>Detail</strong></p></td>
<td><p>Bild</p></td>
<td><p></p></td>
<td><p>Einzelheiten über den Fortschrittsbericht, gespeichert im Binärformat, um Speicherplatz einzusparen. Diese Daten können mit der folgenden Syntax in ein Textformat konvertiert werden.</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Eindeutige ID, die Informationen zum Zeitpunkt des Konferenzbeitritts für die verschiedenen an der Konferenz beteiligten Komponenten korreliert.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Zeit (in Millisekunden) für den Konferenzbeitritt einer bestimmten Komponente.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

