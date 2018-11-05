---
title: 'Lync Server 2013: DeviceDriver-Tabelle'
TOCTitle: DeviceDriver-Tabelle
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398844(v=OCS.15)
ms:contentKeyID: 49295406
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DeviceDriver-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **DeviceDriver** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Treiber, der entweder von einem Aufnahmegerät oder einem Darstellungsgerät verwendet wird.


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
<td><p><strong>DeviceDriverKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Gerätetreiberdatensatz identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Name des Gerätetreibers.</p></td>
</tr>
</tbody>
</table>

