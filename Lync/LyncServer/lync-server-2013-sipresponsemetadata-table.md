---
title: SIPResponseMetaData-Tabelle
TOCTitle: SIPResponseMetaData-Tabelle
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205294(v=OCS.15)
ms:contentKeyID: 49295458
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIPResponseMetaData-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die SIPResponseMetaData-Tabelle enthält eine Liste der SIP-Antwortcodes und die Klassifizierung und Definition für jeden dieser Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die SIP-Geräte und SIP-Kommunikationssitzungen betreffen. Beispielsweise wird der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung ausstellt, aber der Server diese Anforderung ablehnt.

Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Primär</p></td>
<td><p>Numerischer Wert, der den SIP-Antwortcode repräsentiert.</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Allgemeine Klassifizierung für den Antwortcode. Es gibt folgende Klassifizierungen:</p>
<ul>
<li><p>1 – Informative Antworten</p></li>
<li><p>2 – Erfolgreiche Antworten</p></li>
<li><p>3 – Umleitungsantworten</p></li>
<li><p>4 – Clientfehlerantworten</p></li>
<li><p>5 – Serverfehlerantworten</p></li>
<li><p>6 – Globale Fehlerantworten</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Beschreibung des SIP-Antwortcodes. Beispielsweise gibt es für den Antwortcode 181 die folgende Beschreibung:</p>
<p>Anruf wird weitergeleitet</p></td>
</tr>
</tbody>
</table>

