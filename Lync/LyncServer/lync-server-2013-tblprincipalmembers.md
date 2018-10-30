---
title: 'Lync Server 2013: tblPrincipalMembers'
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615022(v=OCS.15)
ms:contentKeyID: 49294864
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMembers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblPrincipalMembers" enthält Prinzipalmitgliedschaften.

### Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar (384), nicht NULL</p></td>
<td><p>Distinguished Name (DN) eines Mitglieds. Ein Mitglied muss kein Prinzipal sein (in der Tabelle &quot;tblPrincipal&quot;).</p></td>
</tr>
</tbody>
</table>


### Schlüssel

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID, memberADPath&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Abfrage von <strong>tblPrincipal.prinID</strong> .</p></td>
</tr>
</tbody>
</table>

