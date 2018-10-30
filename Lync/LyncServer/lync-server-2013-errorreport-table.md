---
title: 'Lync Server 2013: ErrorReport-Tabelle'
TOCTitle: ErrorReport-Tabelle
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412826(v=OCS.15)
ms:contentKeyID: 49295084
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ErrorReport-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

In der **ErrorReport** -Tabelle werden Informationen über aufgetretene Fehler gespeichert. Jeder Datensatz entspricht einem Fehlervorkommen. Die Fehler werden entweder vom KDS-Agent erfasst, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet.


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
<td><p>Primary</p></td>
<td><p>Datum und Uhrzeit des Auftretens des Fehlers.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Die ID zur Kennzeichnung des Fehlerberichts. Gibt in Verbindung mit <strong>ErrorTime</strong> einen Fehlerbericht eindeutig an.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die eindeutige ID des Fehlertyps. Siehe die <a href="lync-server-2013-errordef-table.md">ErrorDef-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Benutzer, von dem die Anforderung stammt, die den Fehler verursachte. Siehe die <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Zielbenutzer für die Anforderung, die den Fehler verursachte. Weitere Informationen finden Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Konferenz-URI im Zusammenhang mit dem Fehler. Weitere Informationen finden Sie unter <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris-Tabelle in Lync Server 2013</a>. Wenn &quot;ConferenceUriId&quot; nicht null ist, dann ist normalerweise entweder &quot;FromUserId&quot; oder &quot;ToUserId&quot; null.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fremd</p></td>
<td><p>Gibt in Verbindung mit <strong>SessionIdSeq</strong> eine Sitzung eindeutig an. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID zur Kennzeichnung der Sitzung. Gibt in Verbindung mit <strong>SessionIdTime</strong> eine Sitzung eindeutig an. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Server, der den Fehlerbericht gesendet hat (falls der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie unter <a href="lync-server-2013-servers-table.md">Servers-Tabelle in Lync Server 2013</a>.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Server, der den Fehlerbericht gesendet hat (falls der Bericht von einer Serverkomponente gesendet wird). Weitere Informationen finden Sie unter <a href="lync-server-2013-application-table.md">Application-Tabelle in Lync Server 2013</a>.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>Bild</p></td>
<td><p> </p></td>
<td><p>Weitere Informationen zu dem Fehler.</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Die Clientversion des Endpunkts, der den Fehlerbericht sendet. Weitere Informationen fnden Sie unter <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Gibt an, ob der Fehlerbericht vom KDS-Agent generiert wurde, der auf dem Front-End-Server ausgeführt wird, oder vom Client gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Für die zukünftige Verwendung reserviert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>Der eindeutige Bezeichner, mit dem die Informationen zum Zeitpunkt des Beitritts der verschiedenen Komponenten, die an einer Konferenz beteiligt sind, zugeordnet werden.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Die Zeit (in Millisekunden), die eine bestimmte Komponente benötigt, um einer Konferenz beizutreten.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Stellt den vollqualifizierten Domänennamen des Servers dar, der den Fehlerbericht generiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Stellt den vollqualifizierten Domänennamen des Pools dar, in dem der Fehlerbericht generiert wurde.</p></td>
</tr>
</tbody>
</table>

