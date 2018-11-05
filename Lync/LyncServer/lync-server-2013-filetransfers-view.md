---
title: FileTransfers-Ansicht
TOCTitle: FileTransfers-Ansicht
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49890980
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# FileTransfers-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der FileTranfers-Ansicht werden Informationen zu Peer-zu-Peer-Dateiübertragungssitzungen gespeichert. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


> [!NOTE]
> Die FileTransfers-Ansicht enthält alle Spalten aus der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht</A> sowie die im Folgenden aufgelisteten Spalten.




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
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Name der übertragenen Datei.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner zum Unterscheiden zwischen Dateiübertragungen mit demselben Dateinamen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>bit</p></td>
<td><p>Kann TRUE oder NULL sein. Falls TRUE erhalten <strong>Reject</strong> und <strong>Cancel</strong> den Wert NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>bit</p></td>
<td><p>Kann TRUE oder NULL sein. Falls TRUE erhalten <strong>Accept</strong> und <strong>Cancel</strong> den Wert NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>bit</p></td>
<td><p>Kann TRUE oder NULL sein. Falls TRUE erhalten <strong>Accept</strong> und <strong>Reject</strong> den Wert NULL.</p></td>
</tr>
</tbody>
</table>

