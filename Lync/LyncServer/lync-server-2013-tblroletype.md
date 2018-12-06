---
title: 'Lync Server 2013: tblRoleType'
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558623(v=OCS.15)
ms:contentKeyID: 49293380
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblRoleType in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblRoleType" ist eine statische Nachschlagetabelle mit Rollentypen und deren zugeordneten Berechtigungssätzen.

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
<td><p>rtypeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Rollentyps.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Beschreibung des Rollentyps. Vier Rollen sind verfügbar:</p>
<ul>
<li><p>Mitglied: Chatroommitglied</p></li>
<li><p>Manager: Chatroommanager</p></li>
<li><p>Leitend: Referent für einen Auditoriumchatroom</p></li>
<li><p>Ersteller: Kann Chatrooms erstellen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Berechtigungssatz für die Rolle. Folgende Bits werden verwendet:</p>
<ul>
<li><p>2: True, wenn die Rolle Knoten verwalten kann.</p></li>
<li><p>4: True, wenn die Rolle untergeordnete Knoten erstellen kann.</p></li>
<li><p>7: True, wenn die Rolle einen Chatroom betreten kann (oder untergeordnete Chatrooms einer Kategorie).</p></li>
<li><p>8: True, wenn die Rolle in einem Chatroom chatten kann (oder in untergeordneten Chatrooms einer Kategorie).</p></li>
<li><p>10: True, wenn die Rolle den Chatverlauf lesen kann, auch wenn sie einen Chatroom nicht betreten hat.</p></li>
<li><p>11: True, wenn die Rolle den Chatroom sehen kann. (Dies wird anhand von Faktoren wie Bereich und Sichtbarkeit präzisiert.)</p></li>
<li><p>12: True, wenn die Rolle in einem Auditoriumchatroom chatten kann.</p></li>
<li><p>13: True, wenn die Rolle beim Anzeigen von Knoten Sichtbarkeitsregeln umgehen kann.</p></li>
</ul></td>
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
<td><p>rtypeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

