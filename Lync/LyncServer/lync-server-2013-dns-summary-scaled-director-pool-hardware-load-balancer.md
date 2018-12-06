---
title: 'Lync Server 2013: DNS-Übersicht für skalierten Directorpool (Hardwarelastenausgleich)'
TOCTitle: DNS-Übersicht für skalierten Directorpool (Hardwarelastenausgleich)
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204655(v=OCS.15)
ms:contentKeyID: 49293098
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Übersicht für skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die folgende Tabelle enthält eine Übersicht über die DNS-Datensätze, die zur Unterstützung eines Director mit Hardwaregerät zum Lastenausgleich erforderlich sind. Für die Rolle des Director sind ähnliche DNS-Datensätze wie für den Front-End-Server erforderlich. Die Anzahl der erforderlichen Datensätze spiegelt sich in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen wider. Im Gegensatz zum Front-End-Server hostet der Directorpool keine Benutzerkonten oder Mobilitätsdienste.

### Für den Directorpool mit Hardwaregerät zum Lastenausgleich und DNS-Lastenausgleich erforderliche DNS-Datensätze

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
<td><p>Director-Hosteintrag für Replikation und Kommunikation zwischen Servern</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>VIP des Hardwaregeräts zum Lastenausgleichs des Directorpools</p></td>
<td><p>Hosteintrag für den Directorpool mit DNS-Lastenausgleich</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Directorpool HLB VIP</p></td>
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
<td><p>Vom externen Reverseproxy-Webticketdienst für den Directorpool veröffentlichter und definierter Lastenausgleich</p></td>
</tr>
</tbody>
</table>

