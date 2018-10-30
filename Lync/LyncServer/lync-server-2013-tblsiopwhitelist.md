---
title: 'Lync Server 2013: tblSiopWhiteList'
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558607(v=OCS.15)
ms:contentKeyID: 49293056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblSiopWhiteList in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei "tblSiopWhiteList" handelt es sich um die Liste der registrierten Add-Ins, die mit Knoten verknüpft werden können.

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
<td><p>siopID</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>GUID des Add-Ins.</p></td>
</tr>
<tr class="even">
<td><p>siopName</p></td>
<td><p>nvarchar (50), nicht NULL</p></td>
<td><p>Anzeigename des Add-Ins.</p></td>
</tr>
<tr class="odd">
<td><p>siopUrl</p></td>
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>URL des Add-Ins.</p></td>
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
<td><p>siopID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

