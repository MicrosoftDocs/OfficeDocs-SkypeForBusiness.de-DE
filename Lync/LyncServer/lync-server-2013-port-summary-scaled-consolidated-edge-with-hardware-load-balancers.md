---
title: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardware-Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78196bab17af69d83bbeacf636b4b2ba4e972121
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-04-27_

Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde. Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP). Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.

Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6. In den Szenarios wird jedoch nur IPv4 verwendet.

**Skalierter konsolidierter Edgeserver mit Hardware Lastenausgleich**

![Edgeserver Umkreisnetzwerk-Ports und-Protokolle](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edgeserver Umkreisnetzwerk-Ports und-Protokolle")

<div>

## <a name="port-and-protocol-details"></a>Port-und Protokoll Details

Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen.

Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt). Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Lastenausgleich für Hardware: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)

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
<td><p>Access/http/TCP/80</p></td>
<td><p>Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Any</p></td>
<td><p>Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Any</p></td>
<td><p>DNS-Abfrage über TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Any</p></td>
<td><p>DNS-Abfrage über UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Edgeserver A/V-Edgedienst IP-Adresse</p></td>
<td><p>Any</p></td>
<td><p>Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Any</p></td>
<td><p>Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Any</p></td>
<td><p>3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver. Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche IP-Adresse</p></td>
<td><p>Any</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: interne Schnittstelle Knoten 1 und Knoten 2

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
<td><p>Any (kann als Front-End-Server Adresse definiert werden oder Front-End-Pool virtuelle IP-Adresse, die den XMPP-Gatewaydienst ausführt)</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (kann als Front-End-Server Server-IP oder-Pool definiert werden, der den zentralen Verwaltungsspeicher umfasst)</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Webkonferenz Datenverkehr von der internen Bereitstellung zur internen Edgeserver-Schnittstelle</p></td>
</tr>
<tr class="even">
<td><p>Stun/MSTURN/UDP/3478</p></td>
<td><p>Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>Stun/MSTURN/TCP/443</p></td>
<td><p>Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver interne Schnittstelle</p></td>
<td><p>Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
</tbody>
</table>


Hardware Geräte zum Lastenausgleich haben spezifische Anforderungen, wenn Sie bereitgestellt werden, um Verfügbarkeit und Lastenausgleich für lync Server bereitzustellen. Die Anforderungen sind in der folgenden Abbildung und den Tabellen definiert. Drittanbieter verwenden möglicherweise unterschiedliche Terminologie für die hier definierten Anforderungen. Es ist erforderlich, die Anforderungen von lync Server den Features und Konfigurationsoptionen Ihres Hardware-Lastenausgleichs Anbieters zuzuordnen.

Berücksichtigen Sie beim Konfigurieren von Hardware-Lastenausgleichsmodulen die folgenden Anforderungen:

  - Die Quellnetzwerk Adressübersetzung (SNAT) kann für Zugriffs-Edgedienst und Webkonferenz-Edgedienst auf dem Hardwaregerät zum Lastenausgleich konfiguriert werden.

  - SNAT kann nicht auf dem A/V-Edgedienst konfiguriert werden – der A/V-Edgedienst muss mit der realen Serveradresse und nicht mit der virtuellen HLB-IP (VIP), für einfaches Traversieren von UDP über NAT (Stun)/Traversal mit Relay NAT (Turn)/Federation Turn (FTURN) ordnungsgemäß funktionieren.
    
      - Wenn der Client eine Anforderung an die HLB sendet, muss die Antwort vom HLB-VIP zurückkommen.
    
      - Wenn der Client eine Anforderung an den Edge sendet, muss die Antwort von der Edge-IP zurückkommen.

  - Öffentliche IP-Adressen werden auf jeder Server Schnittstelle und den VIPs der HLB verwendet, und Ihre Anforderungen an die öffentliche IP-Adresse lauten N + 1, wobei es eine öffentliche IP-Adresse für jede reale Server Schnittstelle und eine für jede HLB-VIP gibt. Wenn Sie 2 Edgeserver im Pool haben, ergeben sich 9 öffentliche IP-Adressen, wobei 3 für die HLB-VIPs und eine für jede Edge-Server-Schnittstelle (insgesamt sechs für die Server) verwendet werden.

  - Für Zugriffs-Edgedienst und Webkonferenz-Edgedienst (und Verwenden von NAT auf der HLB) kontaktiert der Client den VIP, der VIP ändert die Quell-IP-Adresse vom Client in seine eigene IP-Adresse. Die Server Schnittstelle adressiert die Absenderadresse an den VIP, der VIP ändert die Quelladresse von der IP-Adresse der Server Schnittstelle und sendet das Paket an den Client.

  - Für den A/V-Edgedienst darf der VIP die Quell-IP-Adresse nicht ändern, und die reale Serveradresse wird direkt an den Client zurückgegeben – Sie können NAT nicht für den Datenverkehr in der HLB konfigurieren.
    
      - Wenn der Client eine Anforderung an den HLB-VIP sendet, muss die Antwort vom HLB-VIP zurückkommen.
    
      - Wenn der Client eine Anforderung an die Edge-IP sendet, muss die Antwort von der Edge-IP zurückkommen.

  - Für AV behält die externe Firewall die öffentliche IP-Adresse des realen Servers für alle Pakete bei.

  - Nach der festgelegten Meldung erfolgt der Client für A/V-Edgedienst Kommunikation mit dem realen Server und nicht mit der HLB.

  - Interner Edgeserver für interne Server und Clients müssen weitergeleitet werden, und für alle internen Netzwerke, die Server oder Clients hosten, werden persistente Routen festgelegt.

  - Das HLB Zugriffs-Edgedienst VIP fungiert als Standardgateway für jede Edge-Server-Schnittstelle.

<div>


> [!NOTE]
> Weitere Informationen zur NAT-Planung und-Funktionalität finden Sie unter <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware Lastenausgleichsanforderungen für lync Server 2013</A>.



</div>

![Details zu Edgeserver Ports und Protokollen](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Details zu Edgeserver Ports und Protokollen")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Erforderliche Einstellungen für externe Ports für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: virtuelle IPS für externe Schnittstellen

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
<td><p>Any</p></td>
<td><p>XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</p></td>
<td><p>XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</p></td>
<td><p>Any</p></td>
<td><p>XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-verbünden</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)-/TCP/443</p></td>
<td><p>Any</p></td>
<td><p>Zugriffs-Edgedienst öffentliche VIP-Adresse</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Any</p></td>
<td><p>Zugriffs-Edgedienst öffentliche VIP-Adresse</p></td>
<td><p>SIP-Signalisierungs-, Verbund-und öffentliche Instant Messaging-Konnektivität mit SIP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Zugriffs-Edgedienst öffentliche VIP-Adresse</p></td>
<td><p>Verbundpartner</p></td>
<td><p>SIP-Signalisierungs-, Verbund-und öffentliche Instant Messaging-Konnektivität mit SIP</p></td>
</tr>
<tr class="even">
<td><p>Webkonferenz-PSOM (TLS)/TCP/443</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver Webkonferenz-Edgedienst öffentliche VIP-Adresse</p></td>
<td><p>Webkonferenzmedien</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche VIP-Adresse</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver A/V-Edgedienst öffentliche VIP-Adresse</p></td>
<td><p>STUN/TURN-Aushandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: virtuelle IP-Adressen der internen Schnittstelle

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
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Any (kann als Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse definiert werden)</p></td>
<td><p>Edgeserver interne VIP-Schnittstelle</p></td>
<td><p>Ausgehender SIP-Datenverkehr (vom Director, Directorpool virtuellen IP-Adresse, Front-End-Server oder Front-End-Pool virtuellen IP-Adresse) zu einem internen VIP-Edge-Ausgang</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Edgeserver interne VIP-Schnittstelle</p></td>
<td><p>Any (kann als Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse definiert werden)</p></td>
<td><p>Eingehender SIP-Datenverkehr (an Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse) aus Edgeserver internen Schnittstelle</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</p></td>
<td><p>Edgeserver interne VIP-Schnittstelle</p></td>
<td><p>Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</p></td>
</tr>
<tr class="even">
<td><p>Stun/MSTURN/UDP/3478</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver interne VIP-Schnittstelle</p></td>
<td><p>Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen internen Benutzern und externen Benutzern</p></td>
</tr>
<tr class="odd">
<td><p>Stun/MSTURN/TCP/443</p></td>
<td><p>Any</p></td>
<td><p>Edgeserver interne VIP-Schnittstelle</p></td>
<td><p>Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</p></td>
</tr>
<tr class="even">
<td><p>Stun/MSTURN/TCP/443</p></td>
<td><p>Edgeserver interne VIP-Schnittstelle</p></td>
<td><p>Any</p></td>
<td><p>Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

