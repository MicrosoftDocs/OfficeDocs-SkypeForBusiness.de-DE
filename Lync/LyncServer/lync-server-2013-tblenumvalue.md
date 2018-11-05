---
title: 'Lync Server 2013: tblEnumValue'
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615025(v=OCS.15)
ms:contentKeyID: 49294962
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblEnumValue in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblEnumValue" ist eine hardkodierte Tabelle mit den Werten "Visibility" und "Behavior" der Attribute, die in der "Node"-Tabelle verwendet werden.

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
<td><p>valueID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>ID des Werts.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>ID des Attributs.</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Name des Werts.</p></td>
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
<td><p>valueID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle &quot;tblEnumAttribute.attributeID&quot;.</p></td>
</tr>
</tbody>
</table>


### Tabellenwerte

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>privat</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>Bereich</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2</p></td>
<td><p>normal</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2</p></td>
<td><p>Auditorium</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>1</p></td>
<td><p>offen</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[tblNode in Lync Server 2013](lync-server-2013-tblnode.md)

