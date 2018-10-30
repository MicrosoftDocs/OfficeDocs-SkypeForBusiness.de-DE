---
title: 'Lync Server 2013: tblPrincipalInvites'
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558650(v=OCS.15)
ms:contentKeyID: 49294031
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipalInvites in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblPrincipalInvites enthält Einladungen für alle bereitgestellten Benutzer aller Knoten, für die die Funktion der automatischen Einladung (Auto-Invite) aktiviert ist.

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
<td><p>invID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Eindeutige fortlaufende Zahl (pro Prinzipal-ID), generiert von der tblLastInviteId-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID (nur Chatroom).</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>datetime, nicht NULL</p></td>
<td><p>Zeitpunkt des Erstellens.</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblPrincipal.prinID</strong> -Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblNode.nodeID</strong> -Tabelle.</p></td>
</tr>
</tbody>
</table>

