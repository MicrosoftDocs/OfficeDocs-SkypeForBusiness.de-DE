---
title: ProgressReport-Ansicht
TOCTitle: ProgressReport-Ansicht
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49890899
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ProgressReport-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die ProgressReport-Ansicht speichert Informationen über abgeschlossene Sitzungen. Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


> [!NOTE]
> Die Felder "ErrorTime", "ErrorReportSeq" und "ProgressReportSeq" verweisen nicht zwangsläufig auf Fehler, aber zu Meldungen, die den Status von Anrufen oder Nachrichten angeben.




<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt des Fehlers. Wird zusammen mit &quot;ErrorReportSeq&quot; verwendet, um einen Fehler eindeutig zu bestimmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit &quot;ErrorTime&quot; verwendet, um einen Fehler eindeutig zu bestimmen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zum Bestimmen des Fortschrittsberichts. Wird zum Unterscheiden von Fortschrittsberichten desselben Fehlerberichts verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Diagnose-ID für den Fehlerbericht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Zusätzliche Fehlerinformationen.</p></td>
</tr>
</tbody>
</table>

