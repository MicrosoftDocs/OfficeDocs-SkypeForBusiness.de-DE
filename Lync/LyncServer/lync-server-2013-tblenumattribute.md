---
title: 'Lync Server 2013: tblEnumAttribute'
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558617(v=OCS.15)
ms:contentKeyID: 49293306
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblEnumAttribute in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"EnumAttribute" ist eine hardkodierte Tabelle, mit den Attributen "Visibility" und "Behavior", die in der "Node"-Tabelle verwendet werden.

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
<td><p>attributeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>ID des Attributs.</p></td>
</tr>
<tr class="even">
<td><p>attributeName</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Name des Attributs.</p></td>
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
<td><p>attributeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>


### Tabellenwerte

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>attributeID</th>
<th>attributeName</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Sichtbarkeit.</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Verhalten.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[tblNode in Lync Server 2013](lync-server-2013-tblnode.md)

