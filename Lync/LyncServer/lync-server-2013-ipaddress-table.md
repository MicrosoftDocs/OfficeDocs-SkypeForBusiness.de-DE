---
title: IPAddress-Tabelle
TOCTitle: IPAddress-Tabelle
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205077(v=OCS.15)
ms:contentKeyID: 49294715
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IPAddress-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Tabelle "IPAddress" werden IP-Adressen den eindeutigen IDs der IP-Adressen zugeordnet, die an anderer Stelle in der QoE-Datenbank verwendet werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutige ID der angegebenen IP-Adresse.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>varchar(50)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Eindeutige IP-Adresse (z. B. 189.168.1.1), die &quot;derm IpAddressKey&quot; zugeordnet ist. Dies kann entweder eine IPv4- oder eine IPv6-Adresse sein.</p></td>
</tr>
</tbody>
</table>

