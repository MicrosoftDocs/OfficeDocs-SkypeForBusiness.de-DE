---
title: CodecDescription-Tabelle in Lync Server 2013
TOCTitle: CodecDescription-Tabelle in Lync Server 2013
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204797(v=OCS.15)
ms:contentKeyID: 49293645
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CodecDescription-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Tabelle **CodecDescription** sind eindeutige Codec-IDs dem entsprechenden Codec zugeordnet. Codecs werden verwendet, um digitale Signale für die Übertragung zu codieren und anschließend für die Wiedergabe zu decodieren. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>smallint</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutige ID, die dem Codec zugewiesen ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Eindeutige Beschreibung des Codecs, der dem <strong>CodecDescriptionKey</strong> entspricht.</p></td>
</tr>
</tbody>
</table>

