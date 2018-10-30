---
title: 'Lync Server 2013: MediaList-Tabelle'
TOCTitle: MediaList-Tabelle
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398279(v=OCS.15)
ms:contentKeyID: 49293383
ms.date: 07/12/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MediaList-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-07-12_

Die **MediaList** -Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>1 – Sofortnachrichten</p></li>
<li><p>2 – Dateiübertragung</p></li>
<li><p>3 – Remoteunterstützung</p></li>
<li><p>4 – Anwendungsfreigabe</p></li>
<li><p>5 – Audio</p></li>
<li><p>6 – Video</p></li>
<li><p>7 – Anwendungseinladung</p></li>
</ul></td>
</tr>
</tbody>
</table>

