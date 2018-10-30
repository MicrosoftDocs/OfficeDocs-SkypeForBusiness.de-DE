---
title: 'Lync Server 2013: MediationServers-Tabelle'
TOCTitle: MediationServers-Tabelle
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412743(v=OCS.15)
ms:contentKeyID: 49294922
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MediationServers-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **MediationServers** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über einen Vermittlungsserver, der an Anrufen beteiligt ist, welche über Datensätze in der Datenbank verfügen.


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
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Vermittlungsserver identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>Name des Vermittlungsservers.</p></td>
</tr>
</tbody>
</table>

