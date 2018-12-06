---
title: ErrorCategory-Tabelle
TOCTitle: ErrorCategory-Tabelle
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204675(v=OCS.15)
ms:contentKeyID: 49293198
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ErrorCategory-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Tabelle "ErrorCategory" enthält den Anzeigenamen für jede Microsoft Lync Server 2013-Diagnoseklassifizierung. Lync Server 2013 verwendet standardmäßig die folgenden Klassifizierungen:

  - 0 -- Erfolg

  - 1 -- erwarteter Fehler

  - 2 – unerwarteter Fehler

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
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primär</p></td>
<td><p>Eindeutiger Bezeichner für die Klassifikation</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Der Klassifizierung zugeordneter Wert und Anzeigename. Gültige Werte sind:</p>
<ul>
<li><p>0 -- Erfolg</p></li>
<li><p>1 -- erwarteter Fehler</p></li>
<li><p>2 – unerwarteter Fehler</p></li>
</ul></td>
</tr>
</tbody>
</table>

