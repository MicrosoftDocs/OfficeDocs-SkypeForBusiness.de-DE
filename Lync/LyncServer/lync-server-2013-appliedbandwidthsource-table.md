---
title: 'Lync Server 2013: AppliedBandwidthSource-Tabelle'
TOCTitle: AppliedBandwidthSource-Tabelle
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425725(v=OCS.15)
ms:contentKeyID: 49293446
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AppliedBandwidthSource-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **AppliedBandwidthSource** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.


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
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diese Quelle identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthSource</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Dies ist die Quelle der vorgegebenen Bandbreitenbeschränkung. Sie beschreibt den Ursprung der Bandbreitenbeschränkung (z. B.&quot;Policy Server&quot;, &quot;TURN Server&quot; oder &quot;Modality&quot;).</p></td>
</tr>
</tbody>
</table>

