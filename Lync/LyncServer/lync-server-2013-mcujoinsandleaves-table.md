---
title: 'Lync Server 2013: McuJoinsAndLeaves-Tabelle'
TOCTitle: McuJoinsAndLeaves-Tabelle
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398316(v=OCS.15)
ms:contentKeyID: 49293956
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# McuJoinsAndLeaves-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz in dieser Tabelle enthält Anrufdetails über eine Kombination aus einem Benutzer, der einer Konferenz beitritt oder sie verlässt, und einem Konferenzserver. Wenn beispielsweise ein Benutzer einer Konferenz beitritt, die Webkonferenzen sowie Audio/Video-Elemente umfasst, wird ein Datensatz für den Beitritt des Benutzers zur Webkonferenz sowie ein Datensatz für den Beitritt des Benutzers zur Audio/Video-Konferenz erstellt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Konferenzinstanz. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-conferences-table.md">Conferences-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID zur Identifikation der Konferenzinstanz. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Konferenzinstanz eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-conferences-table.md">Conferences-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird die Benutzer/Geräte-Kombination eindeutig von <strong>McuUserInstance</strong> identifiziert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Gibt an, ob der Benutzer aus dem Festnetz beitritt oder nicht.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Eindeutige Zahl, die diesen Konferenzserver identifiziert. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-mcus-table.md">Mcus-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>ID zur Kennzeichnung der Sitzung. Gibt in Verbindung mit <strong>SessionIdTime</strong> eine Sitzung eindeutig an. Weitere Informationen finden Sie unter <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Zeitpunkt, zu dem dieser Benutzer dem Konferenzserver beitritt.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Zeitpunkt, zu dem dieser Benutzer dem Konferenzserver verlässt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Dieser Bezeichner gibt die Versionsnummer der Clientsoftware an, die in der Konferenz verwendet wird. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

