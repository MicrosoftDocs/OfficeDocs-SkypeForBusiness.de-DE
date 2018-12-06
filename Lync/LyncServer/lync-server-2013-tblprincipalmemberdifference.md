---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558612(v=OCS.15)
ms:contentKeyID: 49293140
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalMemberDifference in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"PrincipalMemberDifference" enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von späteren Synchronisierungsschritten der Active Directory-Domänendienste noch nicht verarbeitet wurden.

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
<td><p>Prinzipal-GUID der geänderten Gruppe.</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Distinguished Name (DN) des Mitglieds.</p></td>
</tr>
<tr class="odd">
<td><p>memberRemoved</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>FALSE, wenn das Mitglied hinzugefügt wurde. TRUE, wenn das Mitglied entfernt wurde.</p></td>
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
<td><p>&lt;prinGuid, memberADPath&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

