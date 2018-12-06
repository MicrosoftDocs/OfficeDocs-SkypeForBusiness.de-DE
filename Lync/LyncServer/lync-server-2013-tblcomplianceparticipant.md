---
title: 'Lync Server 2013: tblComplianceParticipant'
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558655(v=OCS.15)
ms:contentKeyID: 49294141
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceParticipant in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>Kanal-URI (Uniform Resource Identifier).</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel des Ereignisses des Beitritts.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>NULL, wenn der Teilnehmer noch immer teilnimmt. Der Zeitstempel des Ereignisses des Verlassens des Kanals, sofern nicht NULL.</p>
<p>Diese Einträge werden schließlich entfernt, wenn das Ereignis von allen Konvertern verarbeitet wird.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>Benutzer-URI</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>Serveridentität (wie in tblServerIdentity.serverID).</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>Serversitzung. Zufallszahl, die nach jedem Starten eines Chatdiensts generiert wird. Wird zur Unterscheidung von Sitzungen verwendet, mit dem Zweck, verwaiste Teilnehmer zu identifizieren.</p></td>
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
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>

