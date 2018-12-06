---
title: 'Lync Server 2013: Gateways-Tabelle'
TOCTitle: Gateways-Tabelle
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412795(v=OCS.15)
ms:contentKeyID: 49295028
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gateways-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Gateways** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gateway, das an PSTN-Anrufen (Public Switched Telephone Network, Telefonfestnetz) beteiligt ist, welche über Datensätze in der Datenbank verfügen.


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
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die dieses Gateway identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>Gatewayname</p></td>
</tr>
</tbody>
</table>

