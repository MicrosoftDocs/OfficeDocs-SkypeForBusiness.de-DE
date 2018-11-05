---
title: 'Lync Server 2013: UserSite-Tabelle'
TOCTitle: UserSite-Tabelle
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398256(v=OCS.15)
ms:contentKeyID: 49293348
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UserSite-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **UserSite** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Benutzerstandort in der Netzwerkkonfigurationseinstellung.


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
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die den Benutzerstandort identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Name des Benutzerstandorts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-region-table.md">Region-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

