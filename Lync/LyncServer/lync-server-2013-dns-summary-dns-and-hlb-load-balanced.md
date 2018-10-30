---
title: 'Lync Server 2013: DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich'
TOCTitle: DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205273(v=OCS.15)
ms:contentKeyID: 49295492
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die folgende Tabelle enthält eine Übersicht über die erforderlichen DNS-Einträge, um einen Director mit DNS-Lastenausgleich und Hardwarelastenausgleich zu unterstützen. Die Rolle des Directors erfordert ähnliche DNS-Einträge wie der Front-End-Server. Die Anzahl der erforderlichen Einträge wird in den erforderlichen alternativen Antragstellernamen im Director-Zertifikat widergespiegelt. Im Gegensatz zu Front-End-Server hostet der Directorpool keine Benutzerkonten oder die Mobilitätsdienste.

### Für den Directorpool erforderliche DNS-Einträge bei Verwendung des DNS-Lastenausgleichs und des Hardwarelastenausgleichs

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/TYP/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Für die Replikation und zwischen Servern verwendeter Director-Hosteintrag</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Directorpool</p></td>
<td><p>Hosteintrag für den Directorpool mit DNS-Lastenausgleich zwischen Servern</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Directorpool</p></td>
<td><p>Ausgehendes SIP (Session Initiation Protocol) von der internen Schnittstelle des Edgeservers</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Directorpool HLB VIP</p></td>
<td><p>Veröffentlichte Dialin-Webdienste mit Hardwarelastenausgleich vom Reverseproxy</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Directorpool HLB VIP</p></td>
<td><p>Veröffentlichte Meet-Webdienste mit Hardwarelastenausgleich vom Reverseproxy</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Directorpool HLB VIP</p></td>
<td><p>Von den externen Webticket-Webdiensten des Reverseproxy mit Hardwarelastenausgleich veröffentlichter und definierter Reverseproxy für den Directorpool</p></td>
</tr>
</tbody>
</table>

