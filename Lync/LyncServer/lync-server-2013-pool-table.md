---
title: 'Lync Server 2013: Pool-Tabelle'
TOCTitle: Pool-Tabelle
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398746(v=OCS.15)
ms:contentKeyID: 49294768
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Pool-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Pool** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der Informationen über die verschiedenen Front-End-Pools gespeichert sind. Jeder Datensatz in der Tabelle steht für einen Pool.


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
<td><p><strong>PoolKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Pool identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Unique </p></td>
<td><p>Pool-FQDN</p></td>
</tr>
</tbody>
</table>

