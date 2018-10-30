---
title: 'Lync Server 2013: tblScopePrincipal'
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558639(v=OCS.15)
ms:contentKeyID: 49293816
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblScopePrincipal in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In "tblScopePrincipal" sind Bereiche enthalten, die Knoten zugeordnet sind.

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
<td><p>scopeNodeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID, auf die sich der Bereich bezieht.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>True, wenn Bereichstyp &quot;Verweigern&quot; ist; False wenn &quot;Zulassen&quot;.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der diesen Eintrag zuletzt aktualisiert hat.</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblNode.nodeID</strong> -Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblPrincipal.prinID</strong> -Tabelle.</p></td>
</tr>
</tbody>
</table>

