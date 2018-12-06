---
title: 'Lync Server 2013: tblComplianceState'
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615045(v=OCS.15)
ms:contentKeyID: 49295785
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblComplianceState in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

tblComplianceState enthält Informationen zum poolweiten Kompatibilitätsstatus.

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
<td><p>lastProcessedEntryID</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>ID des zuletzt verarbeiteten Kompatibilitätsereignisses.</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Kompatibilitätsservers, der die exklusive Sperre über die Datenbank ausübt, bzw. -1, wenn keiner.</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>datetime2, nicht NULL</p></td>
<td><p>Ablaufdatum und -uhrzeit der Sperre (wenn activeServerID nicht -1 ist).</p></td>
</tr>
</tbody>
</table>

