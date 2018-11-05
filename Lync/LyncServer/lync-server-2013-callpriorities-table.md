---
title: 'Lync Server 2013: CallPriorities-Tabelle'
TOCTitle: CallPriorities-Tabelle
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398093(v=OCS.15)
ms:contentKeyID: 49293026
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CallPriorities-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Aufrufprioritäten wie "emergency", "urgent" oder "normal" gespeichert ist.


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
<td><p><strong>PriorityId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Priorität</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>Unbekannt</p></li>
<li><p>1 – Nicht dringend</p></li>
<li><p>2 - Normal</p></li>
<li><p>3 - Dringend</p></li>
<li><p>4 - Notfall</p></li>
</ul></td>
</tr>
</tbody>
</table>

