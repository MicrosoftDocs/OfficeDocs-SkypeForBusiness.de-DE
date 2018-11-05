---
title: 'Lync Server 2013: Mcus-Tabelle'
TOCTitle: Mcus-Tabelle
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425742(v=OCS.15)
ms:contentKeyID: 49293479
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mcus-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Mcus** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über einen Konferenzdienst. Dies kann den Sofortnachrichten-Konferenzdienst und den Telefonkonferenzdienst (die als Vorgänge auf Front-End-Servern ausgeführt werden) sowie den Webkonferenzdienst und den A/V-Konferenzdienst einschließen.


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
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Konferenzserver identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>McuTypeId</strong></p></td>
<td><p>inyint</p></td>
<td><p>Fremd</p></td>
<td><p>Konferenzservertyp, z. B. <strong>conf:chat</strong> (für IMs) oder <strong>conf:audio-video</strong> . Weitere Informationen finden Sie unter <a href="lync-server-2013-uritypes-table.md">UriTypes-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

