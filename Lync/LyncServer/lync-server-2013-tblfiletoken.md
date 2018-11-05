---
title: 'Lync Server 2013: tblFileToken'
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558646(v=OCS.15)
ms:contentKeyID: 49293912
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblFileToken in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

TblFileToken enthält temporäre Token für die Dateiübertragung.

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
<td><p>fileToken</p></td>
<td><p>nvarchar (50), nicht NULL</p></td>
<td><p>Eindeutiges Token (eine GUID).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der die Datei überträgt.</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>GUID des Chatroomknotens.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime, nicht NULL</p></td>
<td><p>Ablaufzeit. (Token laufen nach 30 Minuten ab, wenn sie nicht gebunden werden (siehe Beschreibungen in dieser Tabelle.)</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL der übertragenen Datei (für den Kompatibilitätsdienst).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL des Miniaturbilds der übertragenen Datei (für den Kompatibilitätsdienst).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>Zeitstempel für die tatsächliche Dateiübertragung (für den Kompatibilitätsdienst).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>bit</p></td>
<td><p>True bei Upload; False bei Download (für den Kompatibilitätsdienst).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>True, wenn das Token gebunden ist. Wird verwendet, um das Token in der Tabelle zu behalten, bis die relevanten Felder vom Kompatibilitätsdienst abgerufen werden konnten.</p></td>
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
<td><p>fileToken</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>Fremdschlüssel mit Abfrage der tblNode.nodeGuid-Tabelle.</p></td>
</tr>
</tbody>
</table>

