---
title: 'Lync Server 2013: Roles-Tabelle'
TOCTitle: Roles-Tabelle
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399043(v=OCS.15)
ms:contentKeyID: 49295762
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Roles-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Roles-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Konferenzrollen wie Teilnehmer und Referent gespeichert ist.


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
<td><p><strong>RoleId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Rolle</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>Unbekannt</p></li>
<li><p>Referent</p></li>
<li><p>Teilnehmer</p></li>
</ul></td>
</tr>
</tbody>
</table>

