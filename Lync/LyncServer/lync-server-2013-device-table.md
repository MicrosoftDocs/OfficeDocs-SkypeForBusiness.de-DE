---
title: 'Lync Server 2013: Device-Tabelle'
TOCTitle: Device-Tabelle
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398930(v=OCS.15)
ms:contentKeyID: 49295534
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Device-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Device** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der Informationen über die verschiedenen Aufnahme- oder Darstellungsgeräte gespeichert sind. Jeder Datensatz in der Tabelle steht für ein Gerät.


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
<td><p><strong>DeviceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die dieses Gerät identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p><strong>DeviceName</strong> + <strong>DeviceType</strong> ist <strong>unique</strong></p></td>
<td><p>Gerätename</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceType</strong></p></td>
<td><p>bit</p></td>
<td><p><strong>DeviceName</strong> + <strong>DeviceType</strong> ist <strong>unique</strong></p></td>
<td><p>Gerätetyp. 1 ist ein Aufnahmegerät, 0 ist ein Darstellungsgerät.</p></td>
</tr>
</tbody>
</table>

