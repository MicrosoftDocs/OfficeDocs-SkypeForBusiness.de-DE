---
title: 'Lync Server 2013: VideoClientEvent-Tabelle'
TOCTitle: VideoClientEvent-Tabelle
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399039(v=OCS.15)
ms:contentKeyID: 49295760
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VideoClientEvent-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz enthält Clientereignisse für einen Endpunkt in einem Videoanruf. In der Regel verfügt ein Anruf über zwei Datensätze, einer für den Anrufer und einer für den Angerufenen.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Verwiesen von der <a href="lync-server-2013-medialine-table.md">MediaLine-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>0: Daten des Angerufenen</p>
<p>1: Daten des Anrufers</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;LowBandwidth&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde. Die verfügbare Bandbreite ist nicht ausreichend für eine akzeptable VoIP-Qualität.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>Prozentsatz von Sitzungen, in denen das &quot;ReceiveSendQuality&quot;-Ereignis aufgrund eines ungültigen Status ausgelöst wurde.</p>
<p>Die Netzwerkqualität ist aufgrund von Jitter oder Paketverlusten schlecht und wirkt sich auf die Qualität der empfangenen Audiosignale aus.</p></td>
</tr>
</tbody>
</table>

