---
title: 'Lync Server 2013: tblADUpdates'
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615033(v=OCS.15)
ms:contentKeyID: 49295214
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADUpdates in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblADUpdates enthält Änderungen der Active Directory-Domänendienste, die von den nachfolgenden Active Directory-Synchronisierungsschritten noch nicht verarbeitet wurden.

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
<td><p>prinGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Prinzipal-GUID des geänderten Objekts.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384), nicht NULL</p></td>
<td><p>Distinguished Name (DN) des Objekts.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn sich mindestens ein Attribut des Objekts geändert hat.</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn sich die Mitgliedschaft geändert hat.</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>Nicht verwendet.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn das Objekt gelöscht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime, nicht NULL</p></td>
<td><p>Zeitstempel für den Zeitpunkt, an dem die Zeile eingefügt wurde.</p></td>
</tr>
</tbody>
</table>

