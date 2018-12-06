---
title: 'Lync Server 2013: FocusJoinsAndLeaves-Tabelle'
TOCTitle: FocusJoinsAndLeaves-Tabelle
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399026(v=OCS.15)
ms:contentKeyID: 49295732
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# FocusJoinsAndLeaves-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz in dieser Tabelle enthält Informationen über die Aufzeichnung von Kommunikationsdatensätzen für einen Benutzer, der einer Konferenz beitritt oder sie verlässt. Jede Konferenz ist in dieser Tabelle durch einen Datensatz für einen Benutzer, der einer Konferenz beitritt oder sie verlässt, dargestellt.


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
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung. Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der <a href="lync-server-2013-dialogs-table.md">Dialogs-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert, auf die von der <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a> verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Wenn ein Benutzer auf mehreren Computern oder Geräten gleichzeitig angemeldet ist, wird <strong>UserInstance</strong> verwendet, um die Benutzer/Geräte-Kombination eindeutig zu identifizieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Tatsache, ob die Anmeldung des Benutzers intern erfolgte oder nicht.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Die Rolle des Benutzers bei der Konferenz, wie etwa Referent oder Teilnehmer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Zeitpunkt, zu dem dieser Benutzer der Konferenz beitritt.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Zeitpunkt, zu dem dieser Benutzer die Konferenz verlässt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Version der Clientsoftware des Benutzers; Verweis auf die <a href="lync-server-2013-clientversions-table.md">ClientVersions-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>GUID (Globally Unique Identifier) des bei der Konferenz verwendeten Endpunkts.</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

