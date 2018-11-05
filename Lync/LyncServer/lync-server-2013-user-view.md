---
title: User-Ansicht
TOCTitle: User-Ansicht
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49890801
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# User-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Benutzeransicht werden Informationen über Benutzer gespeichert, die an Anrufen oder Sitzungen teilnehmen, welche über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p>UserId</p></td>
<td><p>int</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert.</p></td>
</tr>
<tr class="even">
<td><p>UserUri</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI des Benutzers</p></td>
</tr>
<tr class="odd">
<td><p>TenantKey</p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Mandant des Benutzers. Weitere Informationen finden Sie unter <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>UriType</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Benutzer-URI-Typ. Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

