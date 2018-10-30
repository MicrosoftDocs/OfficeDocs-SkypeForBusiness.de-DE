---
title: McuJoinsAndLeaves-Ansicht
TOCTitle: McuJoinsAndLeaves-Ansicht
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49890787
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# McuJoinsAndLeaves-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die McuJoinsAndLeaves-Ansicht speichert Informationen zum Beitreten und Verlassen von Benutzern für einen Konferenzserver. Jeder Datensatz in dieser Ansicht enthält Anrufdetails über eine Kombination aus einem Benutzer, der einer Konferenz beitritt oder sie verlässt, und einem Konferenzserver. Die Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der Konferenzinstanz. Wird zusammen mit SessionIdSeq verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-conferences-table.md">Conferences-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Konferenzinstanz. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-conferences-table.md">Conferences-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der URI des Konferenzservers, mit dem sich der Benutzer verbunden hat. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>Der URI des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Die Version des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Der Client, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Der Name der Kategorie des Clients, der vom Benutzer, dessen Informationen zum Beitreten/Verlassen für den Konferenzserver erfasst wurden, verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Identifiziert die Kombination aus Benutzer/Gerät für Benutzer, die gleichzeitig auf mehreren Geräten angemeldet sind, eindeutig.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p>Bitwert, der angibt, ob ein Benutzer ein interner Benutzer ist oder nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit SessionIdSeq verwendet, um eine Sitzung eindeutig zu identifizieren.. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen erhalten Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>SIP-DialogID der Sitzung. Das Format lautet: dialog;from-tag;to-tag.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt, zu dem der Benutzer dem Konferenzserver beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt, zu dem der Benutzer den Konferenzserver verlassen hat.</p></td>
</tr>
</tbody>
</table>

