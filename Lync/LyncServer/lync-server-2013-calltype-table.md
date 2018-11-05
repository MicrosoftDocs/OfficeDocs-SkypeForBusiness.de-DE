---
title: 'Lync Server 2013: CallType-Tabelle'
TOCTitle: CallType-Tabelle
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412752(v=OCS.15)
ms:contentKeyID: 49294945
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CallType-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die **CallType** -Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar</p></td>
<td><p></p></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>0 - Unbekannt</p></li>
<li><p>1 - Sofortnachrichten</p></li>
<li><p>2 - Anwendungsfreigabe</p></li>
<li><p>3 – Audio</p></li>
<li><p>4 - Audio und Video</p></li>
<li><p>5 - Dateiübertragung</p></li>
</ul></td>
</tr>
</tbody>
</table>

