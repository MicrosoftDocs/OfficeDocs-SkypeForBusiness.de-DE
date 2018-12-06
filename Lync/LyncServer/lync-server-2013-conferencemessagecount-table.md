---
title: 'Lync Server 2013: ConferenceMessageCount-Tabelle'
TOCTitle: ConferenceMessageCount-Tabelle
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398590(v=OCS.15)
ms:contentKeyID: 49294461
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceMessageCount-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Jeder Datensatz in dieser Tabelle stellt einen Benutzer in einer Sofortnachrichtenkonferenz dar und schließt die Anzahl der von diesem Benutzer gesendeten Nachrichten ein. Jede Konferenz wird durch mehrere Datensätze in dieser Tabelle mit jeweils einem Datensatz für jeden Benutzer dargestellt.


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
<td><p>Fremd</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer identifiziert, auf die von der <a href="lync-server-2013-users-table.md">Users-Tabelle in Lync Server 2013</a> verwiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Die Anzahl der während dieser Konferenz von diesem Benutzer gesendeten Nachrichten.</p></td>
</tr>
</tbody>
</table>

