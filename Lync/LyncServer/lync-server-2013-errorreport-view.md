---
title: ErrorReport-Ansicht
TOCTitle: ErrorReport-Ansicht
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49890942
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ErrorReport-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der ErrorReport-Ansicht werden Informationen über gemeldete Fehler gespeichert. Jeder Eintrag entspricht einem Fehlervorkommen. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p>Der Zeitpunkt, zu dem der Fehler aufgetreten ist. Wird zusammen mit ErrorReportSeq verwendet, um einen Fehler eindeutig zu identifizieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID zur Identifizierung des Fehlers. Wird zusammen mit ErrorTime verwendet, um einen Fehler eindeutig zu identifizieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>Die Diagnose-ID für den Fehlerbericht.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, der den Fehler ausgelöst hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der URI-Typ des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Mandant des Benutzers, der den Fehler ausgelöst hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI des Benutzers, der das Ziel des Fehlerberichts war.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der URI-Typ des Benutzers, der das Ziel des Fehlerberichts war. Weitere Informationen finden Sie in der UriTypes-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Mandant des Benutzers, der das Ziel des Fehlerberichts war. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Der URI der Konferenz, die das Ziel des Fehlerberichts war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der URI-Typ der Konferenz, die das Ziel des Fehlerberichts war. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Der Zeitpunkt der Sitzungsanforderung, die den Fehlerbericht ausgelöst hat. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Die ID zur Identifikation der Sitzungsanforderung, die den Fehlerbericht ausgelöst hat. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>Die SIP-Dialog-ID der Sitzung, die den Fehler ausgelöst hat. Das Format lautet:</p>
<p><strong>dialog;from-tag;to-tag</strong></p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Die Clientversion, die von dem Benutzer verwendet wird, der den Fehler ausgelöst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Der Client, der von dem Benutzer verwendet wird, der den Fehler ausgelöst hat. Weitere Informationen finden Sie in der <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Der Name der Clientkategorie, die von dem Benutzer verwendet wird, der den Fehler ausgelöst hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Name des Servers, der den Fehler ausgelöst hat (falls der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Name der Anwendung, die den Fehler ausgelöst hat (falls der Bericht von einer Serverkomponente gesendet wurde).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Der SIP-Antwortcode für die Sitzung der SIP-Nachricht, die den Fehlerbericht enthält.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Typ der nicht erfolgreichen Anforderung.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Inhaltstyp der nicht erfolgreichen Anforderung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Der Sitzungstyp. Weitere Informationen finden Sie in der <a href="lync-server-2013-calltype-table.md">CallType-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Der eindeutige Bezeichner, mit dem die Informationen zum Zeitpunkt des Beitritts der verschiedenen Komponenten, die an einer Konferenz beteiligt sind, zugeordnet werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Die Zeit (in Millisekunden), die eine bestimmte Komponente benötigt, um einer Konferenz beizutreten.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Gibt an, ob der Fehlerbericht vom KDS-Agent generiert wurde, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Für die zukünftige Verwendung reserviert.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>Zusätzliche Informationen zu dem Fehler.</p></td>
</tr>
</tbody>
</table>

