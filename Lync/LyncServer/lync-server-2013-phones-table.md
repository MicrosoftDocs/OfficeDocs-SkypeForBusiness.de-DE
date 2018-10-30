---
title: 'Lync Server 2013: Phones-Tabelle'
TOCTitle: Phones-Tabelle
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425923(v=OCS.15)
ms:contentKeyID: 49293810
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Phones-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Phones** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz in der Tabelle speichert Informationen über eine an VoIP-Anrufen beteiligte Telefonnummer, welche über Datensätze in der Datenbank verfügen.


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die dieses Telefon identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>Rufnummer</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dateTime</p></td>
<td><p></p></td>
<td><p>Zeitstempel (nur zur internen Verwendung).</p>
<p>Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.</p></td>
</tr>
</tbody>
</table>

