---
title: NetworkConnectionDetail-Tabelle
TOCTitle: NetworkConnectionDetail-Tabelle
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205185(v=OCS.15)
ms:contentKeyID: 49295148
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# NetworkConnectionDetail-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Netzwerkverbindungstyp, der NetworkConnectionDetailKey entspricht. Gültige Werte sind:</p>
<ol>
<li><p>0 – Wired</p></li>
<li><p>1 – WiFi</p></li>
<li><p>2 – Ethernet</p></li>
</ol></td>
</tr>
</tbody>
</table>

