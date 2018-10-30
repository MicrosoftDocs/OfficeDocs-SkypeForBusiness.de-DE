---
title: 'Lync Server 2013: Subnet-Tabelle'
TOCTitle: Subnet-Tabelle
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398582(v=OCS.15)
ms:contentKeyID: 49294459
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Subnet-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Subnet** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für ein Subnetz in der Netzwerkkonfigurationseinstellung.


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
<td><p>Ganzzahlige Darstellung der Subnetz-IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetMask</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Subnetzmaske</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-usersite-table.md">UserSite-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td><p></p></td>
<td><p>Beschreibung des Subnetzes.</p></td>
</tr>
</tbody>
</table>

