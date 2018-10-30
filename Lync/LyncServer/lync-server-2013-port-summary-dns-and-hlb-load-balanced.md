---
title: 'Lync Server 2013: Portzusammenfassung für DNS- und Hardwarelastenausgleich'
TOCTitle: Portzusammenfassung für DNS- und Hardwarelastenausgleich
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205179(v=OCS.15)
ms:contentKeyID: 49295109
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Anforderungen in Bezug auf Firewallports für einen einzelnen Director bestehen aus Ports, die zum Herstellen einer Verbindung mit dem Director der internen Schnittstelle oder des internen Netzwerks des Reverseproxys verwendet werden. Microsoft Lync Server 2013 erwartet standardmäßig, dass die Ports HTTP/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director, sowie des Front-End-Pools und des Front-End-Servers geöffnet sind. Zusätzlich muss eine Session Initiation-Protokoll-Verbindung (Session Initiation Protocol, SIP) von der internen Schnittstelle des Edgeservers zum Director und zum Front-End-Pool sowie zum Front-End-Server bestehen. Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und zum Front-End-Server. Zudem muss eine Regel erstellt werden, die die SIP-/MTLS-/TCP 5061-Kommunikation vom Director, Front-End-Pool und vom Front-End-Server zur internen Schnittstelle des Edgeserver ermöglicht.

### Einzelne Director-Ports und -Protokolle für Firewalldefinitionen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rolle/Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Virtuelle IP des Hardwaregeräts zum Lastenausgleich des Directors</p></td>
<td><p>Die zunächst von der externen Seite des Reverseproxys empfangene Kommunikation wird zur virtuellen IP des Hardwaregeräts zum Lastenausgleich von Director und zu den Webdiensten von Front-End-Server weitergeleitet.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Virtuelle IP des Hardwaregeräts zum Lastenausgleich des Directors</p></td>
<td><p>Die zunächst von der externen Seite des Reverseproxys empfangene Kommunikation wird zur virtuellen IP des Hardwaregeräts zum Lastenausgleich von Director und zu den Webdiensten von Front-End-Server weitergeleitet.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Front-End-Pool oder Front-End-Server</p></td>
<td><p>Serverübergreifende Kommunikation zwischen der virtuellen IP des Hardwaregeräts zum Lastenausgleich des Directors und der Front-End-Server oder dem Front-End-Server.</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Internal Clients</p></td>
<td><p>Virtuelle IP des Hardwaregeräts zum Lastenausgleich des Directors</p></td>
<td><p>Der Director stellt Webdienste für interne und externe Clients bereit.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Internal Clients</p></td>
<td><p>Virtuelle IP des Hardwaregeräts zum Lastenausgleich des Directors</p></td>
<td><p>Der Director stellt Webdienste für interne und externe Clients bereit.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Director</p></td>
<td><p>SIP-Kommunikation vom Edgeserver zum Director und zum Front-End-Server.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller (ClsController.exe) oder -Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller (ClsController.exe) oder -Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Director</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller (ClsController.exe) oder -Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
</tbody>
</table>

