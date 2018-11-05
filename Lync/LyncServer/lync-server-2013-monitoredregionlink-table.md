---
title: 'Lync Server 2013: MonitoredRegionLink-Tabelle'
TOCTitle: MonitoredRegionLink-Tabelle
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398874(v=OCS.15)
ms:contentKeyID: 49295449
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MonitoredRegionLink-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **MonitoredRegionLink** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Verknüpfung zwischen zwei Ländern/Regionen.


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
<td><p><strong>Region1Key</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-region-table.md">Region-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Region2Key</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-region-table.md">Region-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

