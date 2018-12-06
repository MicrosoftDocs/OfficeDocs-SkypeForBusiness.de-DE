---
title: 'Lync Server 2013: ContentTypes-Tabelle'
TOCTitle: ContentTypes-Tabelle
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399007(v=OCS.15)
ms:contentKeyID: 49295699
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ContentTypes-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **ContentTypes** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste der in Peer-zu-Peer-Sitzungen und Konferenzsitzungen verwendeten Inhaltstypen gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Inhaltstyp.


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
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Inhaltstyp identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td> </td>
<td><p>Name des Inhaltstyps.</p></td>
</tr>
</tbody>
</table>

