---
title: 'Lync Server 2013: Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT'
TOCTitle: Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412756(v=OCS.15)
ms:contentKeyID: 49294954
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die in dieser Szenarioarchitektur beschriebene Lync Server 2013-Edgeserverfunktion ist der, die in Lync Server 2010 implementiert war, sehr ähnlich. Die wichtigste Ergänzung besteht in Porteintrag **5269 über TCP** für XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder im Edgepool und den XMPP-Gatewayserver auf dem Front-End-Server oder im Front-End-Pool bereit.

Zusätzlich zu IPv4 unterstützt der Edgeserver jetzt IPv6. In den Szenarien wird zur Verdeutlichung ausschließlich IPv4 verwendet.

**Unternehmensumkreisnetzwerk für skalierten konsolidierten Edgeserver mit privaten IP-Adressen und Verwendung der Netzwerkadressenübersetzung (NAT)**

![Skalierter konsolidierter Edgeserver](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "Skalierter konsolidierter Edgeserver")

## Port- und Protokolldetails

Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen möchten.

Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt). Anders ausgedrückt: Der SIP-Nachrichtenverkehr zum und vom Zugriffs-Edgedienst ist an Instant Messaging, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbünden beteiligt.

### Firewallzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mit NAT: Externe Schnittstelle - Knoten 1 und Knoten 2 (Beispiel)

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
<td><p>Zugriff/HTTP/TCP/80</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/DNS/TCP/53</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über TCP</p></td>
</tr>
<tr class="odd">
<td><p>Zugriff/DNS/UDP/53</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über UDP</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/SIP(TLS)/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</p></td>
</tr>
<tr class="odd">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserverzugriff, Edgedienst</p></td>
<td><p>Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP</p></td>
</tr>
<tr class="odd">
<td><p>Webkonferenzen/PSOM(TLS)TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserver-Webkonferenz-Edgedienst</p></td>
<td><p>Webkonferenzmedien</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Erforderlich für den Partnerverbund mit Organisationen, die Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 und Lync Server 2013 ausführen.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Port 3478 (ausgehend) wird zum Ermitteln der Version des Edgeservers verwendet, mit der Lync Server kommuniziert, sowie für den Mediendatenverkehr von Edgeserver zu Edgeserver. Erforderlich für den Partnerverbund mit Lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 sowie dann, wenn mehrere Edgepools in einem Unternehmen bereitgestellt werden.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### Firewallzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mit NAT: Interne Schnittstelle - Knoten 1 und Knoten 2 (Beispiel)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Beliebig (kann als Adresse für den Front-End-Server oder als IP-Adresse für den Front-End-Pool definiert werden, in dem der XMPP-Gatewaydienst ausgeführt wird)</p></td>
<td><p>Interne IP-Adresse der Edgeserver-Schnittstelle</p></td>
<td><p>Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf dem Front-End-Server oder im Front-End-Pool ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Beliebig (kann definiert werden als Director, als Directorpool-IP-Adresse Front-End-Server oder als Front-End-Pool-IP-Adresse)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Ausgehender SIP-Datenverkehr (von Director, einer Directorpool-IP-Adresse, Front-End-Server oder einer Front-End-Pool-IP-Adresse) an die interne Edgeserver-Schnittstelle.</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Beliebig (kann definiert werden als Director, als Directorpool-IP-Adresse Front-End-Server oder als Front-End-Pool-IP-Adresse)</p></td>
<td><p>Eingehender SIP-Datenverkehr (an Director, eine Directorpool-IP-Adresse, Front-End-Server oder eine Front-End-Pool-IP-Adresse) von der internen Edgeserver-Schnittstelle.</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Beliebig (kann definiert werden als Front-End-Server-IP-Adresse oder jede Front-End-Server-IP-Adresse in einem Front-End-Pool)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Webkonferenzdatenverkehr von Front-End-Server oder jedem Front-End-Server (falls in einem Pool) an die interne Edgeserver-Schnittstelle.</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Beliebig (kann als Front-End-Server-IP-Adresse, als Front-End-Pool-IP-Adresse, als Survivable Branch-Anwendung oder als Survivable Branch-Server definiert sein, der diesen Edgeserver verwendet)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Authentifizierung von A/V-Benutzern (A/V-Authentifizierungsdienst) von einer Front-End-Server- oder Front-End-Pool-IP-Adresse oder einem beliebigen Survivable Branch-Anwendung oder Survivable Branch-Server mit diesem Edgeserver</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen internen Benutzern und externen Benutzern, Survivable Branch-Anwendung oder Survivable Branch-Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, Survivable Branch-Anwendung oder Survivable Branch-Server, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Beliebig (kann definiert werden als Front-End-Server-IP-Adresse oder Pool, der den zentralen Verwaltungsspeicher beinhaltet)</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Replikation von Änderungen aus dem zentralen Verwaltungsspeicher auf dem Edgeserver</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller mithilfe der Lync Server-Verwaltungsshell und Zentraler Protokollierungsdienst-Cmdlets, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller mithilfe der Lync Server-Verwaltungsshell und Zentraler Protokollierungsdienst-Cmdlets, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Schnittstelle des Edgeservers</p></td>
<td><p>Zentraler Protokollierungsdienst-Controller mithilfe der Lync Server-Verwaltungsshell und Zentraler Protokollierungsdienst-Cmdlets, ClsController-Befehlszeile (ClsController.exe) oder Agentbefehle (ClsAgent.exe) und Protokollerfassung</p></td>
</tr>
</tbody>
</table>


## Firewallzusammenfassung für den Partnerverbund


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
<td><p>Öffentliche IP-Adresse für den Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP</p></td>
</tr>
</tbody>
</table>


## Firewallzusammenfassung - Verbindungen mit öffentlichen Instant Messaging-Diensten


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
<td><p>Partner für Verbindungen mit öffentlichen Instant Messaging-Diensten</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP</p></td>
</tr>
<tr class="even">
<td><p>Zugriff/SIP(MTLS)/TCP/5061</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Partner für Verbindungen mit öffentlichen Instant Messaging-Diensten</p></td>
<td><p>Für Verbindungen mit Partnerverbünden und öffentlichen Instant Messaging-Diensten über SIP</p></td>
</tr>
<tr class="odd">
<td><p>Zugriff/SIP(TLS)/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Edgeserver-Zugriffs-Edgedienst</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn Verbindungen mit öffentlichen Instant Messaging-Diensten konfiguriert sind.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Für Verbindungen mit öffentlichen Instant Messaging-Diensten mit Windows Live Messenger erforderlich</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Edgeserver-A/V-Edgedienst</p></td>
<td><p>Für Verbindungen mit öffentlichen Instant Messaging-Diensten mit Windows Live Messenger erforderlich</p></td>
</tr>
</tbody>
</table>


## Firewallzusammenfassung für XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/TCP oder UDP/Port</th>
<th>Quelle (IP-Adresse)</th>
<th>Ziel (IP-Adresse)</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Beliebig</p></td>
<td><p>Edgeserver-IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP; erlaubt Kommunikation von XMPP-Verbundpartnern zum Edgeserver-XMPP-Proxy</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Edgeserver-IP-Adresse der Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Beliebig</p></td>
<td><p>Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP; erlaubt Kommunikation vom Edgeserver-XMPP-Proxy zu XMPP-Verbundpartnern</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Beliebig</p></td>
<td><p>Jede interne Edgeserver-Schnittstellen-IP</p></td>
<td><p>Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder im Front-End-Pool zur internen Edgeserver-IP-Adresse oder der internen IP-Adresse aller Edgepool-Member</p></td>
</tr>
</tbody>
</table>

