---
title: 'Lync Server 2013: Users-Tabelle'
TOCTitle: Users-Tabelle
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412791(v=OCS.15)
ms:contentKeyID: 49295026
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Users-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Users** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz in der Tabelle speichert Informationen über einen Benutzer, der an Anrufen oder Sitzungen teilnimmt, welche über Datensätze in der Datenbank verfügen.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Zeitstempel für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>Benutzer-URI</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Tenant-ID dieses Benutzers. Weitere Informationen finden Sie in der <a href="lync-server-2013-tenants-table.md">Tenants-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>URI-Typ dieses Benutzers. Weitere Informationen finden Sie in der <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

