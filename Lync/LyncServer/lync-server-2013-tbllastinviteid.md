---
title: 'Lync Server 2013: tblLastInviteId'
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558625(v=OCS.15)
ms:contentKeyID: 49293417
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblLastInviteId in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblLastInviteId" enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle) verwendet wurde.

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
<td><p>prinID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID</p></td>
</tr>
<tr class="even">
<td><p>lastInviteID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Zuletzt verwendete INVITE-ID.</p></td>
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
<td><p>prinID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblPrincipal.prinID</strong> -Tabelle.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[tblPrincipalInvites in Lync Server 2013](lync-server-2013-tblprincipalinvites.md)

