---
title: 'Lync Server 2013: Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20071cba55551a42ea6406723bb1f9ed55853afa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-04_

Die in dieser Szenario-Architektur beschriebene lync Server 2013-Edgeserver-Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde. Die bemerkenswerteste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP). Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edge-Server oder Edge-Pool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.

Neben IPv4 unterstützt der Edgeserver nun IPv6. Aus Gründen der Übersichtlichkeit wird in den Szenarien nur IPv4 verwendet.

**Unternehmens Umkreisnetzwerk für skalierten konsolidierten Edge mit privaten IP-Adressen mithilfe von NAT**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

Es wird empfohlen, nur die Ports zu öffnen, die erforderlich sind, um die Funktionalität zu unterstützen, für die Sie externen Zugriff bereitstellen.

Damit der Remotezugriff für jeden Edgedienst funktionieren kann, ist es zwingend erforderlich, dass der SIP-Datenverkehr bidirektional wie in der Abbildung des eingehenden/ausgehenden Edge-Traffics durchlaufen wird. Anders ausgedrückt: das SIP-Messaging zum und vom Access-Edgedienst ist an Instant Messaging (im), Anwesenheitsinformationen, Webkonferenzen, Audio/Video (A/V) und Föderation beteiligt.

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a>Zusammenfassung der Firewall für den konsolidierten skalierten Edge, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)

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
<td><p>Access/http/TCP/80</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Zertifikatsperrung/CRL-Prüfung und-Abruf</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>DNS-Abfrage über UDP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (TLS)-/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
<tr class="odd">
<td><p>Web Conferencing/PSOM (TLS)/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server-Webkonferenz-Edgedienst</p></td>
<td><p>Web-Konferenzmedien</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Erforderlich für die Föderation mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 ausführen.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, auf denen Office Communications Server 2007 ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>3478 Outbound wird verwendet, um die Version von Edgeserver zu ermitteln, mit der lync Server kommuniziert, sowie für Mediendatenverkehr vom Edge-Server-zu-Edge-Server. Erforderlich für den Verbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/TCP/443</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Beliebig</p></td>
<td><p>Betäubung/Turn Verhandlung von Kandidaten über TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a>Zusammenfassung der Firewall für den konsolidierten skalierten Edge, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: interne Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)

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
<td><p>Any (kann als Front-End-Server Adresse oder IP-Adresse des Front-End-Pools definiert werden, auf der der XMPP-Gatewayserver ausgeführt wird)</p></td>
<td><p>IP-Adresse des Edge-Server-internen Interfaces</p></td>
<td><p>Ausgehender XMPP-Datenverkehr vom XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools definiert werden)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Ausgehender SIP-Datenverkehr (von Director, Director-Pool-IP-Adresse, Front-End-Server oder IP-Adresse des Front-End-Pools) zu einer internen Schnittstelle</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools definiert werden)</p></td>
<td><p>Eingehende SIP-Datenverkehr (an Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools) aus der internen Schnittstelle</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (kann als Front-End-Server-IP-Adresse oder jede IP-Adresse eines Front-End-Servers in einem Front-End-Pool definiert werden)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Webkonferenzen-Datenverkehr vom Front-End-Server oder jedem Front-End-Server, falls in einem Pool, zu einer internen Schnittstelle des Edge-Servers</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (kann als Front-End-Server-IP-Adresse oder IP-Adresse des Front-End-Pools oder einer überlebensfähigen Branch-Appliance oder eines Überlebenden Branch-Servers mit diesem Edgeserver definiert werden)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) vom Front-End-Server oder der IP-Adresse des Front-End-Pools oder von einer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mit diesem Edgeserver</p></td>
</tr>
<tr class="even">
<td><p>Stun/MSTURN/UDP/3478</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>Stun/MSTURN/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survival-Branch-Appliance oder einem Überlebenden Branch-Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (kann als die IP-Adresse des Front-End-Servers oder-Pools definiert werden, der den zentralen Verwaltungsspeicher enthält)</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Beliebig</p></td>
<td><p>Interne Edge-Server-Schnittstelle</p></td>
<td><p>Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Zusammenfassung der Firewall für den Verbund


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
<td><p>Access Edge Service (öffentliche IP-Adresse)</p></td>
<td><p>Beliebig</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Zusammenfassung der Firewall – öffentliche Instant Messaging-Konnektivität


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
<td><p>Verbindungspartner für öffentliche Chats</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS)-/TCP/5061</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Verbindungspartner für öffentliche Chats</p></td>
<td><p>Für Verbund-und öffentliche Chat Verbindungen mit SIP</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS)-/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Edge-Server-Zugriffs-Edgedienst</p></td>
<td><p>Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn die Konnektivität für öffentliche Chats konfiguriert ist.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/Stun, MSTURN/UDP/3478</p></td>
<td><p>Live Messenger-Clients</p></td>
<td><p>Edge-Server A/V-Edgedienst</p></td>
<td><p>Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Zusammenfassung der Firewall für erweiterbares Messaging und Anwesenheits Protokoll


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
<td><p>IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</p></td>
<td><p>Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP. Ermöglicht die Kommunikation mit dem Edge-Server-XMPP-Proxy von Federated XMPP-Partnern</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</p></td>
<td><p>Beliebig</p></td>
<td><p>Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP. Ermöglicht die Kommunikation vom Edge Server XMPP-Proxy an Federated XMPP-Partner</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Beliebig</p></td>
<td><p>Jede interne Edge-Server-Schnittstellen-IP</p></td>
<td><p>Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zur internen IP-Adresse des Edge-Servers oder zur internen IP-Adresse jedes Edge-Pools</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

