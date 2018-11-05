---
title: FocusJoinsAndLeaves-Ansicht
TOCTitle: FocusJoinsAndLeaves-Ansicht
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49890659
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# FocusJoinsAndLeaves-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der FocusJoinsAndLeaves-Ansicht werden Informationen zum Beitreten und Verlassen für eine Konferenz gespeichert. Alle Konferenzen werden in dieser Ansicht durch einen Datensatz dargestellt, der jedes Mal beim Beitreten bzw. Verlassen eines Benutzer für eine Konferenz geschrieben wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p>Zeitpunkt der Konferenzinstanz. Wird in Verbindung mit &quot;SessionIdSeq&quot; verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie unter <a href="lync-server-2013-conferences-table.md">Conferences-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID zur Identifikation der Konferenzinstanz. Wird zusammen mit SessionIdTime verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-conferences-table.md">Conferences-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Typ des URIs des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden. Weitere Informationen finden Sie in der Dokumentation zum <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Mandant des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden. Weitere Informationen finden Sie in der Dokumentation zum <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version des Client des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client, der vom Benutzer verwendet wurde, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-useragentdef-table.md">UserAgentDef-Tabelle</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Name der Kategorie des Clients des Benutzers, dessen Informationen zum Beitreten/Verlassen einer Konferenz erfasst wurden.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Bit, das angibt, ob es sich beim Benutzer um einen internen Benutzer handelt.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird in Verbindung mit &quot;SessionIdSeq&quot; verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird UserInstance verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>SIP-Dialog-ID der Sitzung. Format: dialog;from-tag;to-tag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt, zu dem dieser Benutzer der Konferenz beitrat.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt, zu dem dieser Benutzer die Konferenz verließ.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Die Rolle des Benutzers bei der Konferenz, wie etwa Referent oder Teilnehmer.</p></td>
</tr>
</tbody>
</table>

