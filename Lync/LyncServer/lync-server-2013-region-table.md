---
title: 'Lync Server 2013: Region-Tabelle'
TOCTitle: Region-Tabelle
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398235(v=OCS.15)
ms:contentKeyID: 49293300
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Region-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Region** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Land/eine Region in der Netzwerkkonfigurationseinstellung.


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
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die das Land/die Region identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegionName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Der Name des Lands/der Region.</p></td>
</tr>
</tbody>
</table>

