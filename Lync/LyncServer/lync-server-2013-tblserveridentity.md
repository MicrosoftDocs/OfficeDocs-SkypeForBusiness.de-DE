---
title: 'Lync Server 2013: tblServerIdentity'
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558648(v=OCS.15)
ms:contentKeyID: 49294022
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblServerIdentity in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblServerIdentity enthält die aktiven Chatserver im Serverpool für beständigen Chat.

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
<td><p>serverID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Server-ID. Entspricht der Instanz-ID von zentraler Verwaltungsspeicher.</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar (256), nicht NULL</p></td>
<td><p>Serveradresse mit der Windows Communication Foundation-Adresse.</p></td>
</tr>
<tr class="odd">
<td><p>serverLastPingTime</p></td>
<td><p>datetime</p></td>
<td><p>Der letzte Zeitpunkt, zu dem der Kanalserver diese Zeile aktualisiert hat, um die Ausführung zu beweisen.</p></td>
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
<td><p>serverID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

