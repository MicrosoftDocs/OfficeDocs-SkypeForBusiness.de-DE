---
title: 'Lync Server 2013: tblConfig'
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558663(v=OCS.15)
ms:contentKeyID: 49294401
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblConfig in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblConfig enthält in einer Zeile einige von Server für beständigen Chat nicht unterstützte Konfigurationsoptionen.

### Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>configLabel</p></td>
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>Enthält „Pool“.</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>Inhalt der Konfiguration.</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Eindeutige ID der Datenbankinstanz.</p></td>
</tr>
</tbody>
</table>


### Schlüssel

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>configLabel</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

