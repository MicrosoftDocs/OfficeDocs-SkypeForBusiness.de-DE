---
title: 'Lync Server 2013: tblLastChatId'
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558616(v=OCS.15)
ms:contentKeyID: 49293302
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblLastChatId in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"LastChatId" enthält die zuletzt generierte (und in der tblChat-Tabelle verwendete) Chat-ID für jeden Benutzer.

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
<td><p>nodeID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID (nur Chatroom).</p></td>
</tr>
<tr class="even">
<td><p>lastChatID</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zuletzt verwendete Chat-ID.</p></td>
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
<td><p>&lt;nodeID, lastChatID&gt;</p></td>
<td><p>Primärschlüssel (für die Verarbeitung genügt <strong>nodeID</strong> ).</p></td>
</tr>
<tr class="even">
<td><p>nodeID</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>tblNode.nodeID</strong> -Tabelle.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[tblChat in Lync Server 2013](lync-server-2013-tblchat.md)

