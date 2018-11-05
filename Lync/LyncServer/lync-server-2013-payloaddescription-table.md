---
title: 'Lync Server 2013: PayloadDescription-Tabelle'
TOCTitle: PayloadDescription-Tabelle
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412971(v=OCS.15)
ms:contentKeyID: 49295337
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PayloadDescription-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **PayloadDescription** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Codec, der in einer Audio- oder Videositzung verwendet wird.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Spalte</strong></th>
<th><strong>Datentyp</strong></th>
<th><strong>Schlüssel/Index</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PayloadDescriptionKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die den Codec identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>PayloadDescription</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Name des Codecs.</p></td>
</tr>
</tbody>
</table>

