---
title: 'Lync Server 2013: DeRegisterType-Tabelle'
TOCTitle: DeRegisterType-Tabelle
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398142(v=OCS.15)
ms:contentKeyID: 49293105
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DeRegisterType-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **DeRegisterType** -Tabelle handelt es sich um eine statische Tabelle, die eine Liste der möglichen Typen für eine Aufhebung der Registrierung von Benutzern speichert, wie zum Beispiel "Aufhebung der Registrierung durch den Client", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>0 - Unbekannt</p></li>
<li><p>1 - Aufhebung der Registrierung durch den Client</p></li>
<li><p>2 - Registrierung abgelaufen</p></li>
<li><p>3 - Clientabsturz</p></li>
<li><p>4 - Benutzerattribute geändert</p></li>
<li><p>5 - Bevorzugte Registrierungsstelle geändert</p></li>
<li><p>6 - Legacyclient In Survival Mode</p></li>
</ul></td>
</tr>
</tbody>
</table>

