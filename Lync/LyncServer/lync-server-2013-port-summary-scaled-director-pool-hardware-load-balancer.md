---
title: 'Lync Server 2013: Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich)'
TOCTitle: Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich)
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204983(v=OCS.15)
ms:contentKeyID: 49294309
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Anforderungen an die Firewallports für einen Directorpool bestehen aus den Ports, über die Kommunikationsverbindungen mit dem Director aus der internen Schnittstelle des Edgeserver oder der internen Schnittstelle des Reverseproxys hergestellt werden. Microsoft Lync Server 2013 erwartet in der Standardeinstellung, dass die Ports HTTP/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zu dem Director sowie dem Front-End-Pool und Front-End-Server geöffnet sind. Außerdem muss von der internen Edgeserver-Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server SIP-Kommunikation (Session Initiation Protocol) bestehen. Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server. Und es muss auch eine Regel erstellt sein, die SIP/MTLS/TCP 5061-Kommunikation vom Director, Front-End-Pool und Front-End-Server zur internen Edgeserver-Schnittstelle erlaubt.

### Director-Ports und -Protokolle für Firewall-Definitionen

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
<td><p>Ursprünglich von außerhalb beim Reverseproxy eingehende Kommunikationen werden an die VIP des Director-Hardwaregeräts zum Lastenausgleich und die Front-End-Server-Webdienste gesendet</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Virtuelle IP des Hardwaregeräts zum Lastenausgleich des Directors</p></td>
<td><p>Ursprünglich von außerhalb beim Reverseproxy eingehende Kommunikationen werden an die VIP des Director-Hardwaregeräts zum Lastenausgleich und die Front-End-Server-Webdienste gesendet</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Front-End-Server oder Front-End-Pool</p></td>
<td><p>Interserver-Kommunikation zwischen der VIP des Director-Hardwaregeräts zum Lastenausgleich und den Front-End-Server</p></td>
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
<td><p>Virtuelle IP des Hardwaregeräts zum Lastenausgleich des Directors</p></td>
<td><p>SIP-Kommunikation vom Edgeserver zum Director und Front-End-Server.</p></td>
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

