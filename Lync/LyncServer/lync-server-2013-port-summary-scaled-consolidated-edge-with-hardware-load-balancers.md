---
title: Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-04-27_

Die in dieser Szenario-Architektur beschriebene lync Server 2013-Edgeserver-Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde. Die bemerkenswerteste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP). Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edge-Server oder Edge-Pool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.

Neben IPv4 unterstützt der Edgeserver nun IPv6. Aus Gründen der Übersichtlichkeit wird in den Szenarien nur IPv4 verwendet.

**Skalierter konsolidierter Edge mithilfe des Hardware Lastenausgleichs**

![Edge-Server-Umkreisnetzwerk-Ports und-Protokolle] (images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge-Server-Umkreisnetzwerk-Ports und-Protokolle")

<div>

## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

Es wird empfohlen, nur die Ports zu öffnen, die erforderlich sind, um die Funktionalität zu unterstützen, für die Sie externen Zugriff bereitstellen.

Damit der Remotezugriff für jeden Edgedienst funktionieren kann, ist es zwingend erforderlich, dass der SIP-Datenverkehr bidirektional wie in der Abbildung des eingehenden/ausgehenden Edge-Traffics durchlaufen wird. Anders ausgedrückt: das SIP-Messaging zum und vom Access-Edgedienst ist an Instant Messaging (im), Anwesenheitsinformationen, Webkonferenzen, Audio/Video (A/V) und Föderation beteiligt.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Zusammenfassung der Firewall für den skalierten konsolidierten Edge, Hardware Lastenausgleich: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/http/TCP/80</p></td>
<td><p>Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</p></td>
<td><p>Beliebig</p></td>
<td><p>Zertifikatsperrung/CRL-Prüfung und-Abruf</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Edge-Server-A/V-Edgedienst-IP-Adresse</p></td>
<td><p>Beliebig</p></td>
<td><p>Erforderlich für die Föderation mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 ausführen.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</p></td>
<td><p>Beliebig</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, auf denen Office Communications Server 2007 ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</p></td>
<td><p>Beliebig</p></td>
<td><p>3478 Outbound wird verwendet, um die Version von Edgeserver zu ermitteln, mit der lync Server kommuniziert, sowie für Mediendatenverkehr vom Edge-Server-zu-Edge-Server. Erforderlich für den Verbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</p></td>
<td><p>Beliebig</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Zusammenfassung der Firewall für den skalierten konsolidierten Edge, Hardware Lastenausgleich: internes Interface, Knoten 1 und Knoten 2

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (kann als Front-End-Server Adresse oder virtuelle IP-Adresse des Front-End-Pools definiert werden, auf der der XMPP-Gatewayserver ausgeführt wird)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Ausgehender XMPP-Datenverkehr vom XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (kann als Front-End-Server-IP oder-Pool definiert werden, der den zentralen Verwaltungsspeicher enthält)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (kann als Director-IP, IP-Front-End-Server oder virtuelle Pool-IP-Adresse definiert werden)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Webkonferenzen-Datenverkehr von interner Bereitstellung zu interner Edge-Server Schnittstelle</p></td>
</tr>
<tr class="even">
<td><p>Stun/MSTURN/UDP/3478</p></td>
<td><p>Any (kann als Director-IP, IP-Front-End-Server oder virtuelle Pool-IP-Adresse definiert werden)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>Stun/MSTURN/TCP/443</p></td>
<td><p>Any (kann als Director-IP, IP-Front-End-Server oder virtuelle Pool-IP-Adresse definiert werden)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survival-Branch-Appliance oder einem Überlebenden Branch-Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
</tbody>
</table>


Hardware Lastenausgleichs haben bestimmte Anforderungen, wenn Sie bereitgestellt werden, um Verfügbarkeit und Lastenausgleich für lync Server bereitzustellen. Die Anforderungen sind in der folgenden Abbildung und in den Tabellen definiert. Drittanbieter verwenden möglicherweise unterschiedliche Terminologie für die hier festgelegten Anforderungen. Es ist erforderlich, die Anforderungen von lync Server den Features und Konfigurationsoptionen zuzuordnen, die vom Hersteller Ihres Hardwarelastenausgleichs bereitgestellt werden.

Bei der Konfiguration von Hardware-Lastenausgleichsgeräten sollten Sie die folgenden Anforderungen erfüllen:

  - Quell-Netzwerkadressübersetzung (SNAT) kann auf dem Hardware Load Balancer (HLB) für Access Edge Service und Web Conferencing Edge Service konfiguriert werden.

  - SNAT kann nicht auf dem a/v-Edgedienst konfiguriert werden – der a/v-Edgedienst muss mit der Adresse des realen Servers und nicht mit der virtuellen HLB-IP (VIP) Antworten, um eine einfache Durchquerung von UDP über NAT (Stun)-/Traversal mit Relay-NAT (Turn)/Federation Turn (FTURN) zu verwenden, um ordnungsgemäß zu funktionieren
    
      - Wenn der Client eine Anforderung an die HLB sendet, muss die Antwort vom HLB-VIP zurückkehren.
    
      - Wenn der Client eine Anforderung an den Edge sendet, muss die Antwort von der Edge-IP zurückkommen.

  - Öffentliche IP-Adressen werden auf jeder Server Schnittstelle und auf den VIPs der HLB verwendet, und Ihre Anforderungen an die öffentliche IP-Adresse sind N + 1, wobei für jede echte Server Schnittstelle eine öffentliche IP-Adresse und eine für jedes HLB-VIP vorhanden ist. Wenn im Pool zwei Edgeserver vorhanden sind, werden in 9 öffentliche IP-Adressen, wobei 3 für die HLB-VIPs und eine für jede Edgeserver-Schnittstelle verwendet werden (insgesamt sechs für die Server) angezeigt.

  - Bei Access Edge Service und Web Conferencing Edge Service (und Verwendung von NAT auf der HLB) kontaktiert der Client den VIP, der VIP ändert die Quell-IP-Adresse vom Client in seine eigene IP-Adresse. Die Server Schnittstelle adressiert die Absenderadresse an den VIP, der VIP ändert die Quelladresse von der IP-Adresse der Server Schnittstelle und sendet das Paket an den Client.

  - Für den A/V-Edgedienst darf der VIP die Quell-IP-Adresse nicht ändern, und die Adresse des realen Servers wird direkt an den Client zurückgegeben – Sie können NAT auf der HLB für AV-Datenverkehr nicht konfigurieren.
    
      - Wenn der Client eine Anfrage an das HLB-VIP sendet, muss die Antwort vom HLB-VIP zurückkommen.
    
      - Wenn der Client eine Anforderung an die Edge-IP-Adresse sendet, muss die Antwort von der Edge-IP-Adresse zurückgeliefert werden.

  - Bei AV behält die externe Firewall die öffentliche IP-Adresse des realen Servers für alle Pakete bei.

  - Nach der festgelegten Kommunikation des Client-zu-A/V-Edge-Diensts erfolgt die Kommunikation mit dem echten Server und nicht mit der HLB

  - Interner Edge-Server und-Clients müssen weitergeleitet werden, und für alle internen Netzwerke, die Server oder Clients hosten, werden permanente Routen festgesetzt.

  - Der HLB Access Edge Service VIP fungiert als Standardgateway für jede Edge-Server-Schnittstelle.

<div>


> [!NOTE]
> Weitere Informationen zur NAT-Planung und-Funktionalität finden Sie unter <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware Load Balancer Requirements for lync Server 2013</A>.



</div>

![Details zu Edge-Server-Ports und-Protokollen] (images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Details zu Edge-Server-Ports und-Protokollen")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Externe Port Einstellungen für skalierten konsolidierten Edge, Hardware Lastenausgleich: externe Schnittstelle, Virtuelles IPS

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Beliebig</p></td>
<td><p>XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</p></td>
<td><p>Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</p></td>
<td><p>Beliebig</p></td>
<td><p>Der XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-Föderationen</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)-/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Access Edge Service Public VIP-Adresse</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Beliebig</p></td>
<td><p>Access Edge Service Public VIP-Adresse</p></td>
<td><p>SIP-Signalisierungs-, Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Access Edge Service Public VIP-Adresse</p></td>
<td><p>Partnerverbund</p></td>
<td><p>SIP-Signalisierungs-, Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
<tr class="even">
<td><p>Web Conferencing/PSOM (TLS)/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-Webkonferenz-Edgedienst, öffentliche VIP-Adresse</p></td>
<td><p>Web-Konferenzmedien</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server A/V Edge Service Public VIP-Adresse</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server A/V Edge Service Public VIP-Adresse</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Zusammenfassung der Firewall für den skalierten konsolidierten Edge, Hardware Lastenausgleich: internes Interface, Virtuelles IPS

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Role/Protocol/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Any (kann als Director, Virtual IP address des Director-Pools, Front-End-Server oder virtuelle IP-Adresse des Front-End-Pools definiert werden)</p></td>
<td><p>Edge-Server-interne VIP-Oberfläche</p></td>
<td><p>Ausgehender SIP-Datenverkehr (von Director, Virtual IP address des Director-Pools, Front-End-Server oder virtuelle IP-Adresse des Front-End-Pools) zu interner Edge-VIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Edge-Server-interne VIP-Oberfläche</p></td>
<td><p>Any (kann als Director, Virtual IP address des Director-Pools, Front-End-Server oder virtuelle IP-Adresse des Front-End-Pools definiert werden)</p></td>
<td><p>Eingehende SIP-Datenverkehr (an Director, Virtual IP address des Director-Pools, virtuelle IP-Adresse des Front-End-Servers oder virtuelle IP-Adresse des Front-End-Pools) aus der internen</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (kann als Front-End-Server-IP-Adresse oder IP-Adresse des Front-End-Pools oder einer überlebensfähigen Branch-Appliance oder eines Überlebenden Branch-Servers mit diesem Edgeserver definiert werden)</p></td>
<td><p>Edge-Server-interne VIP-Oberfläche</p></td>
<td><p>Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) vom Front-End-Server oder der IP-Adresse des Front-End-Pools oder von einer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mit diesem Edgeserver</p></td>
</tr>
<tr class="even">
<td><p>Stun/MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-interne VIP-Oberfläche</p></td>
<td><p>Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern</p></td>
</tr>
<tr class="odd">
<td><p>Stun/MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-interne VIP-Oberfläche</p></td>
<td><p>Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern wenn keine UDP-Kommunikation eingerichtet werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Stun/MSTURN/TCP/443</p></td>
<td><p>Edge-Server-interne VIP-Oberfläche</p></td>
<td><p>Beliebig</p></td>
<td><p>Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern wenn keine UDP-Kommunikation eingerichtet werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

