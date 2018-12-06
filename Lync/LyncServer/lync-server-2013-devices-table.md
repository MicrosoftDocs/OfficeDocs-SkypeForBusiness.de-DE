---
title: 'Lync Server 2013: Devices-Tabelle'
TOCTitle: Devices-Tabelle
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398351(v=OCS.15)
ms:contentKeyID: 49294011
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Devices-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Devices** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diese Hardwareversion identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Hersteller dieses Geräts. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-manufacturers-table.md">Manufacturers-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Hardwareversion dieses Geräts. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>MAC-Adresse</p></td>
</tr>
</tbody>
</table>

