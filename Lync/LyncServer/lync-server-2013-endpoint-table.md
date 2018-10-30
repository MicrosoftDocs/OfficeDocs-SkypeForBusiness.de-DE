---
title: 'Lync Server 2013: Endpoint-Tabelle'
TOCTitle: Endpoint-Tabelle
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398327(v=OCS.15)
ms:contentKeyID: 49293980
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Endpoint-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Endpoint** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin werden Informationen über die Endpunkte gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Endpunkt.


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
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Endpunkt identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Name des Endpunkts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p> </p></td>
<td><p>Betriebssystem des Endpunkts.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p></p></td>
<td><p>Prozessorname des Endpunkts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Anzahl der Prozessorkerne des Endpunkts.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Prozessorgeschwindigkeit des Endpunkts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Bitflag, das angibt, ob das System in einer virtualisierten Umgebung ausgeführt wird:</p>
<ul>
<li><p>0x0000 - None</p></li>
<li><p>0x0001 - HyperV</p></li>
<li><p>0x0002 - VMWare</p></li>
<li><p>0x0004 - Virtual PC</p></li>
<li><p>0x0008 - Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>

