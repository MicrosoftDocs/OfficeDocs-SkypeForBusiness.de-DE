---
title: 'Lync Server 2013: EdgeServers-Tabelle'
TOCTitle: EdgeServers-Tabelle
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412833(v=OCS.15)
ms:contentKeyID: 49295093
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# EdgeServers-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **EdgeServers** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über einen Edgeserver, der an Anrufen beteiligt ist, welche über Datensätze in der Datenbank verfügen.


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
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Edgeserver identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>Name des Edgeservers.</p></td>
</tr>
</tbody>
</table>

