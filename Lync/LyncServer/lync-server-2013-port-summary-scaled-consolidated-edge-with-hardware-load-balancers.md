---
title: 'Lync Server 2013: Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich'
TOCTitle: Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398739(v=OCS.15)
ms:contentKeyID: 49294751
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-04-27_

Die in dieser Szenarioarchitektur beschriebene Lync Server 2013-Edgeserverfunktion ist der, die in Lync Server 2010 implementiert war, sehr ähnlich. Die wichtigste Ergänzung besteht in Porteintrag **5269 über TCP** für XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder im Edgepool und den XMPP-Gatewayserver auf dem Front-End-Server oder im Front-End-Pool bereit.

Zusätzlich zu IPv4 unterstützt der Edgeserver jetzt IPv6. In den Szenarien wird zur Verdeutlichung ausschließlich IPv4 verwendet.

**Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich**

![Ports und Protokolle des Edgeserver-Umkreisnetzwerks](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Ports und Protokolle des Edgeserver-Umkreisnetzwerks")

## Port- und Protokolldetails

Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen möchten.

Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung "Skalierte konsolidierte Edgetopologie (Hardwarelastenausgleich)" gezeigt). Anders ausgedrückt: SIP-Messaging vom und zum Zugriffs-Edgedienst ist an Instant Messaging, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Verbund beteiligt.

### Firewallzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich: Externe Schnittstelle - Knoten 1 und Knoten 2 (Beispiel)

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
<td><p>Zugriff/HTTP/TCP/80</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des Zugriffs-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/DNS/TCP/53</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des Zugriffs-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über TCP</p></td>
</tr>
<tr class="odd">
<td><p>Zugriff/DNS/UDP/53</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des Zugriffs-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>Erforderlich für den Partnerverbund mit Organisationen, die Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 und Lync Server 2013 ausführen.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>Port 3478 (ausgehend) wird zum Ermitteln der Version des Edgeservers verwendet, mit der Lync Server kommuniziert, sowie für den Mediendatenverkehr von Edgeserver zu Edgeserver. Erforderlich für den Partnerverbund mit Lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 sowie dann, wenn mehrere Edgepools in einem Unternehmen bereitgestellt werden.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Öffentliche Edgeserver-IP-Adresse des A/V-Edgediensts</p></td>
<td><p>Beliebig</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### Firewallzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich: Interne Schnittstelle Knoten 1 und Knoten 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Beliebig (kann als Adresse für den Front-End-Server oder als virtuelle IP-Adresse für den Front-End-Pool definiert werden, in dem der XMPP-Gatewaydienst ausgeführt wird)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf dem Front-End-Server oder im Front-End-Pool ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Beliebig (kann als die Server-IP des Front-End-Servers oder als der Pool definiert werden, der den zentralen Verwaltungsspeicher enthält)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Replikation von Änderungen aus dem zentralen Verwaltungsspeicher auf dem Edgeserver</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Beliebig (kann als die IP des Directors, des Front-End-Servers oder die virtuelle Pool-IP definiert werden)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Datenverkehr von Webkonferenzen von der internen Bereitstellung zur internen Edgeserverschnittstelle</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Beliebig (kann als die IP des Directors, des Front-End-Servers oder die virtuelle Pool-IP definiert werden)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen internen Benutzern und externen Benutzern, Survivable Branch-Anwendung oder Survivable Branch-Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Beliebig (kann als die IP des Directors, des Front-End-Servers oder die virtuelle Pool-IP definiert werden)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, Survivable Branch-Anwendung oder Survivable Branch-Server, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller mithilfe der Lync Server-Verwaltungsshell und Zentraler Protokollierungsdienst-Cmdlets, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller mithilfe der Lync Server-Verwaltungsshell und Zentraler Protokollierungsdienst-Cmdlets, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller mithilfe der Lync Server-Verwaltungsshell und Zentraler Protokollierungsdienst-Cmdlets, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
</tbody>
</table>


Hardwaregeräte zum Lastenausgleich haben spezifische Anforderungen, wenn diese bereitgestellt werden, um für Verfügbarkeit und Lastenausgleich für Lync Server zu sorgen. Die Anforderungen sind in der folgenden Abbildung und den Tabellen aufgeführt. Andere Hersteller verwenden für die hier definierten Anforderungen möglicherweise andere Begriffe. Es ist notwendig, dass die Anforderungen von Lync Server den Funktionen und Konfigurationsoptionen des Herstellers ihres Hardwaregeräts für den Lastenausgleich zugeordnet werden.

Berücksichtigen Sie bei der Konfiguration von Hardwaregeräten für den Lastenausgleich folgende Anforderungen:

  - Die Netzwerkadressübersetzung (SNAT) kann auf dem Hardwaregerät für den Lastenausgleich für den Zugriffs-Edgedienst und den Webkonferenz-Edgedienst konfiguriert werden

  - SNAT kann nicht im A/V-Edgedienst konfiguriert werden - der A/V-Edgedienst muss mit der realen Serveradresse antworten, nicht mit der virtuellen IP (VIP) des Hardwaregeräts für den Lastenausgleich, damit STUN (Simple Traversal of UDP over NAT)/TURN (Traversal Using Relay NAT)/FTURN (Federation TURN) korrekt funktionieren

  - An allen Serverschnittstellen und für die virtuellen IP-Adressen des Hardwaregeräts für den Lastenausgleich werden öffentliche IP-Adressen verwendet und die erforderlichen öffentlichen IP-Adressen betragen N+1, da es eine öffentliche IP-Adresse für jede reale Serverschnittstelle und eine für jede virtuelle IP-Adresse des Hardwaregeräts für den Lastenausgleich gibt. Wenn sich im Pool 2 Edgeserver befinden, ergibt dies 9 öffentliche IP-Adressen, von denen 3 für die virtuellen IPs des Hardwaregeräts für den Lastenausgleich verwendet werden und eine pro Edgeserverschnittstelle (insgesamt sechs für die Server)

  - Für den Zugriffs-Edgedienst und den Webkonferenz-Edgedienst (und bei Verwendung von NAT auf dem Hardwaregerät für den Lastenausgleich) kontaktiert der Client die virtuelle IP, und die VIP ändert die Quell-IP-Adresse vom Client in ihre eigene IP-Adresse. Die Serverschnittstelle adressiert die Absenderadresse an die VIP, die VIP ändert die Quelladresse der Serverschnittstellen-IP-Adresse und sendet das Paket an den Client

  - Für den A/V-Edgedienst muss die VIP die Quell-IP-Adresse NICHT ändern, und es wird direkt die reale Serveradresse an den Client zurückgegeben - Sie können NAT auf dem Hardwaregerät für den Lastenausgleich nicht für AV-Datenverkehr konfigurieren

  - Für AV behält die externe Firewall die reale öffentliche IP-Adresse des Servers für alle Pakete

  - Nachdem die Verbindung hergestellt ist, läuft die Kommunikation vom Client zum A/V-Edgedienst an den realen Server und nicht an das Hardwaregerät für den Lastenausgleich

  - Interne Edge an interne Server und Clients muss weitergeleitet werden, und für alle Netzwerke, die Server oder Clients hosten, werden persistente Routen festgelegt

  - Die VIP des Zugriffs-Edgediensts des Hardwaregeräts für den Lastenausgleich agiert als Standardgateway für alle Edgeserverschnittstellen

![Details zu Edgeserverports und -protokollen](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Details zu Edgeserverports und -protokollen")

### Erforderliche Einstellungen für externe Ports für eine skalierte konsolidierte Edge, Hardwarelastenausgleich: Virtuelle IP-Adressen der externen Schnittstelle

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Beliebig</p></td>
<td><p>XMPP-Proxydienst (teilt die IP-Adresse mit dem Zugriffs-Edgedienst)</p></td>
<td><p>XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Verbünden</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP-Proxydienst (teilt die IP-Adresse mit dem Zugriffs-Edgedienst)</p></td>
<td><p>Beliebig</p></td>
<td><p>Der XMPP-Proxydienst sendet Datenverkehr an XMPP-Kontakte in festgelegten XMPP-Verbünden</p></td>
</tr>
<tr class="odd">
<td><p>Zugriff/SIP(TLS)/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche IP-Adresse des Zugriffs-Edgediensts</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche IP-Adresse des Zugriffs-Edgediensts</p></td>
<td><p>SIP-Signalisierung, Partnerverbundkonnektivität und die Verbindung mit öffentlichen Sofortnachrichtendiensten über SIP</p></td>
</tr>
<tr class="odd">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Öffentliche IP-Adresse des Zugriffs-Edgediensts</p></td>
<td><p>Verbundpartner</p></td>
<td><p>SIP-Signalisierung, Partnerverbundkonnektivität und die Verbindung mit öffentlichen Sofortnachrichtendiensten über SIP</p></td>
</tr>
<tr class="even">
<td><p>Webkonferenzen/PSOM(TLS)TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche Edgeserver-VIP-Adresse des Webkonferenz-Edgediensts</p></td>
<td><p>Webkonferenzmedien</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche Edgeserver-VIP-Adresse des A/V-Edgediensts</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Öffentliche Edgeserver-VIP-Adresse des A/V-Edgediensts</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### Firewallzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich: Virtuelle IPs der internen Schnittstelle

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
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Beliebig (kann als Director, als virtuelle Directorpool-IP-Adresse, als Front-End-Server oder als virtuelle Front-End-Pool-IP-Adresse definiert sein)</p></td>
<td><p>Interne VIP-Schnittstelle des Edgeservers</p></td>
<td><p>Ausgehender SIP-Datenverkehr (von Director, einer virtuellen Directorpool-IP-Adresse, Front-End-Server oder einer virtuellen Front-End-Pool-IP-Adresse) an die interne EDGE-VIP.</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Interne VIP-Schnittstelle des Edgeservers</p></td>
<td><p>Beliebig (kann als Director, als virtuelle Directorpool-IP-Adresse, als Front-End-Server oder als virtuelle Front-End-Pool-IP-Adresse definiert sein)</p></td>
<td><p>Eingehender SIP-Datenverkehr (an Director, eine Directorpool-IP-Adresse, Front-End-Server oder eine virtuelle Front-End-Pool-IP-Adresse) von der internen Edgeserver-Schnittstelle.</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Beliebig (kann als Front-End-Server-IP-Adresse, als Front-End-Pool-IP-Adresse, als Survivable Branch-Anwendung oder als Survivable Branch-Server definiert sein, der diesen Edgeserver verwendet)</p></td>
<td><p>Interne VIP-Schnittstelle des Edgeservers</p></td>
<td><p>Authentifizierung von A/V-Benutzern (A/V-Authentifizierungsdienst) von einer Front-End-Server- oder Front-End-Pool-IP-Adresse oder einem beliebigen Survivable Branch-Anwendung oder Survivable Branch-Server mit diesem Edgeserver</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne VIP-Schnittstelle des Edgeservers</p></td>
<td><p>Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen internen Benutzern und externen Benutzern</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne VIP-Schnittstelle des Edgeservers</p></td>
<td><p>Fallback-Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann. TCP wird für die Dateiübertragung und die Desktopfreigabe verwendet</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interne VIP-Schnittstelle des Edgeservers</p></td>
<td><p>Beliebig</p></td>
<td><p>Fallback-Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann. TCP wird für die Dateiübertragung und die Desktopfreigabe verwendet</p></td>
</tr>
</tbody>
</table>

