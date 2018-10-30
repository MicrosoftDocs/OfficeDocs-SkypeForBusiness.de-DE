---
title: 'Lync Server 2013: ErrorDef-Tabelle'
TOCTitle: ErrorDef-Tabelle
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398503(v=OCS.15)
ms:contentKeyID: 49294303
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ErrorDef-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die **ErrorDef** -Tabelle speichert Informationen über alle möglichen Fehlertypen, die auftreten können. Jeder Datensatz steht für einen Fehlertyp.


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID, die diesen Fehlertyp identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>SIP-Standardantwortcode, der diesem Fehler zugeordnet ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Microsoft-Diagnose-ID</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Der Typ des Anrufs. Weitere Informationen dazu finden Sie in der <a href="lync-server-2013-calltype-table.md">CallType-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary(33)</p></td>
<td><p> </p></td>
<td><p>Typ der nicht erfolgreichen Anforderung.</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary(257)</p></td>
<td><p> </p></td>
<td><p>Inhaltstyp der nicht erfolgreichen Anforderung.</p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

