---
title: 'Lync Server 2013: EndpointSubnet-Tabelle'
TOCTitle: EndpointSubnet-Tabelle
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398933(v=OCS.15)
ms:contentKeyID: 49295543
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# EndpointSubnet-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **EndpointSubnet** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein von Endpunkten erfasstes Subnetz.


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Ganzzahlige Darstellung des Subnetzes.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
</tbody>
</table>

