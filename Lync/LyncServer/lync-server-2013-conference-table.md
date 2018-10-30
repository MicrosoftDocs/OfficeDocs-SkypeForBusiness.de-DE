---
title: 'Lync Server 2013: Conference-Tabelle'
TOCTitle: Conference-Tabelle
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425762(v=OCS.15)
ms:contentKeyID: 49293501
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conference-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Conference** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.


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
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Konferenzdatensatz identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Konferenz-URI bei einer Konferenz, DialogID bei einer Peer-zu-Peer-Sitzung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p>index</p></td>
<td><p>Prüfsumme der Konferenz-URI. Für interne Zwecke.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>Ausschließlich für interne Zwecke.</p></td>
</tr>
</tbody>
</table>

