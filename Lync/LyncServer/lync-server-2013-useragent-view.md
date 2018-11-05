---
title: UserAgent-Ansicht
TOCTitle: UserAgent-Ansicht
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49890910
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UserAgent-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die UserAgent-Ansicht speichert Informationen über die Benutzeragenten, die an Sitzungen teilgenommen haben und die über Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Zeichenfolge des Benutzer-Agents.</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>smallint</p></td>
<td><p>Benutzeragententyp. Weitere Informationen erhalten Sie unter <a href="lync-server-2013-useragent-table.md">UserAgent-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Kategorie, zu der der Benutzeragent gehört. Zum Beispiel gehört der Benutzeragent Conferencing_Attendant_1.0 zur UACategory CAA.</p></td>
</tr>
</tbody>
</table>

