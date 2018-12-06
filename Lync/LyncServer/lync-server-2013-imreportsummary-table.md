---
title: IMReportSummary-Tabelle
TOCTitle: IMReportSummary-Tabelle
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204753(v=OCS.15)
ms:contentKeyID: 49293483
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IMReportSummary-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Tabelle **IMReportSummary** stellt einen Gesamtbericht zu den in einer Organisation durchgeführten Chatsitzungen bereit. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Chatsitzung begann.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimePeriod</strong></p></td>
<td><p>char(1)</p></td>
<td><p>Primär</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (257)</p></td>
<td><p>Primär</p></td>
<td><p>Vollqualifizierter Domänenname des Pools, der die Sitzung hostet.</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Priorität (z. B. dringend oder nicht dringend) des Anrufs. Die Prioritätsinformationen werden in der <a href="lync-server-2013-callpriorities-table.md">CallPriorities-Tabelle in Lync Server 2013</a> gespeichert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>Die Gesamtzahl der Chatnachrichten, die während der Sitzung ausgetauscht wurden.</p></td>
</tr>
</tbody>
</table>

