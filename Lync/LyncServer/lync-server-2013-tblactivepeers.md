---
title: 'Lync Server 2013: tblActivePeers'
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615030(v=OCS.15)
ms:contentKeyID: 49295152
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblActivePeers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chatdiensten.

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
<td><p>aplServerID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Servers, der den Eintrag bereitgestellt hat.</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Peers, mit dem der bereitstellende Server verbunden ist.</p></td>
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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>Fremdschlüssel mit Abfrage der Tabelle &quot;tblServerIdentity.serverID&quot;.</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>Fremdschlüssel mit Abfrage der Tabelle &quot;tblServerIdentity.serverID&quot;.</p></td>
</tr>
</tbody>
</table>

