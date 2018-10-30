---
title: TraceRoute-Tabelle
TOCTitle: TraceRoute-Tabelle
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205205(v=OCS.15)
ms:contentKeyID: 49295203
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# TraceRoute-Tabelle

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Datum und Uhrzeit des Beginns des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Eindeutige ID, die zur Unterscheidung zwischen mehreren Anrufen verwendet wird, die möglicherweise zum gleichen Datum und zur gleichen Uhrzeit begonnen haben.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primär, Fremd</p></td>
<td><p>Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:</p>
<ul>
<li><p>0 – Audio</p></li>
<li><p>1 – Video</p></li>
<li><p>2 -- Panoramavideo</p></li>
<li><p>3 – Anwendungs-/Desktopfreigabe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primär</p></td>
<td><p>Endpunkt, der den Anruf getätigt hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hop</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Netzwerk-Hop/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Fremd</p></td>
<td><p>Eindeutige ID für die IP-Adresse. IP-Adressinformationen werden in der <a href="lync-server-2013-ipaddress-table.md">IPAddress-Tabelle</a> gespeichert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Paketumlaufzeit (Roundtrip time). Die Paketumlaufzeit misst die Zeit, die ein Sprachpaket benötigt, um zu seinem Ziel zu gelangen und eine Benachrichtigung über den Empfang zu senden.</p></td>
</tr>
</tbody>
</table>

