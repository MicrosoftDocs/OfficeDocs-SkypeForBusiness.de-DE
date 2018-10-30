---
title: 'Lync Server 2013: UriTypes-Tabelle'
TOCTitle: UriTypes-Tabelle
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398587(v=OCS.15)
ms:contentKeyID: 49294446
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UriTypes-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-06-16_

In der UriTypes-Tabelle sind die unterschiedlichen URI-Typen (Uniform Resource Identifier) enthalten, die in Microsoft Lync Server 2013 überwacht werden.


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
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige ID, die einem URI-Typ zugewiesen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Beschreibungen zu verschiedenen URI-Typen. Gültige Werte sind:</p>
<ul>
<li><p>0 – Phone Uri</p></li>
<li><p>1 – User Uri</p></li>
</ul></td>
</tr>
</tbody>
</table>

