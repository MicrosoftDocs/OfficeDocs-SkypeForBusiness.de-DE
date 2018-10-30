---
title: 'Lync Server 2013: Portzusammenfassung für einen einzelnen Director'
TOCTitle: Portzusammenfassung für einen einzelnen Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204648(v=OCS.15)
ms:contentKeyID: 49293080
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für einen einzelnen Director in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Anforderungen in Bezug auf Firewallports für einen einzelnen Director-Server bestehen aus den Ports, die zum Herstellen der Kommunikation mit dem Director von der internen Schnittstelle oder dem internen Netzwerk des Reverseproxys verwendet werden. Von Microsoft Lync Server 2013 wird standardmäßig erwartet, dass die Ports HTTP/TCP 8080 und HTTPS/TCP 4443 auf dem Reverseproxy zum Director sowie zum Front-End-Pool und Front-End-Server offen sind. Darüber hinaus muss SIP (Session Initiation Protocol)-Kommunikation zwischen der internen Edgeserver-Schnittstelle und dem Director, dem Front-End-Pool und Front-End-Server bestehen. Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 auf dem Edgeserver zum Front-End-Pool und Front-End-Server. Eine Regel, die die SIP/MTLS/TCP 5061-Kommunikation zwischen dem Director, Front-End-Pool und Front-End-Server und der internen Edgeserver-Schnittstelle ermöglicht, muss ebenfalls erstellt werden.

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
<td><p>Director</p></td>
<td><p>Die Kommunikation wird zunächst von der externen Seite des Reverseproxys empfangen und dann an die Webdienste Director und Front-End-Server gesendet.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interne Schnittstelle des Reverseproxys</p></td>
<td><p>Director</p></td>
<td><p>Die Kommunikation wird zunächst von der externen Seite des Reverseproxys empfangen und dann an die Webdienste Director und Front-End-Server gesendet.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Front-End-Server oder Front-End-Pool</p></td>
<td><p>Serverübergreifende Kommunikation zwischen dem Director und dem Front-End-Server</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Internal Clients</p></td>
<td><p>Director-Webdienste</p></td>
<td><p>Der Director stellt Webdienste für interne und externe Clients bereit.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Internal Clients</p></td>
<td><p>Director-Webdienste</p></td>
<td><p>Der Director stellt Webdienste für interne und externe Clients bereit.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Director</p></td>
<td><p>SIP-Kommunikation zwischen dem Edgeserver und dem Director sowie dem Front-End-Server.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst: Controller-Befehle (ClsController.exe) oder Agentbefehle (ClasAgent.exe) sowie Protokollerfassung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst: Controller-Befehle (ClsController.exe) oder Agentbefehle (ClasAgent.exe) sowie Protokollerfassung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst: Controller-Befehle (ClsController.exe) oder Agentbefehle (ClasAgent.exe) sowie Protokollerfassung</p></td>
</tr>
</tbody>
</table>

