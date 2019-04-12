---
title: Microsoft-Teams, rufen Sie Abläufe
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: Beschreibt, wie Teams Office 365 fließt in verschiedenen Topologien verwendet.
ms.openlocfilehash: ecdeb6dc4e1e7219dc8c01c710877437661e0ceb
ms.sourcegitcommit: 856793c99fc02fb016383d0b6f8411c386d78886
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "31828937"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft-Teams, rufen Sie Abläufe

> [!Tip]
> Sehen Sie sich die folgenden Sitzung um erfahren, wie Teams nutzt Ihr Netzwerk und Planen Sie eine optimale Netzwerkkonnektivität: [Teams Netzwerkplanung](https://aka.ms/teams-networking)

## <a name="overview"></a>Übersicht
In diesem Artikel wird beschrieben, wie Teams verwendet Office 365 fließt in verschiedenen Topologien aufrufen. Darüber hinaus beschreibt es eindeutige Teams Abläufe, die für die Peer-zu-Peer-medienkommunikation verwendet werden. Das Dokument wird diese Datenflüsse, deren Zweck und ihren Ursprung und Beendigung im Netzwerk beschrieben. Aus Gründen der in diesem Artikel wird davon ausgegangen Sie Folgendes:

- Flow X wird vom lokalen Office 365-Client zur Kommunikation mit Office 365-Dienst in der Cloud. Es stammt aus dem Kundennetzwerk, und er als ein Endpunkt in Office 365 beendet wird.

- Fluss Y wird vom lokalen Office 365-Client mit einem Dienst über das Internet zu kommunizieren, die Office 365 verfügt über eine Abhängigkeit für verwendet. Es stammt aus dem Kundennetzwerk, und er als Endpunkt im Internet beendet wird.

Der Artikel enthält die folgenden Abschnitte:

- **Hintergrund** - enthält Hintergrundinformationen wie Netzwerken, in denen Office 365 Abläufe durchlaufen können, Art des Datenverkehrs, Konnektivität-Leitfaden der Kundennetzwerk zu Office 365-Endpunkten, die Interoperabilität mit Drittanbieter-Komponenten, und mit den Prinzipien, die zum Auswählen von Medien fließt von Teams, die verwendet werden.

- **Rufen Sie die Abläufe in verschiedenen Topologien** - veranschaulicht die Verwendung von anrufflüssen in verschiedenen Topologien. Für jede Topologie im Abschnitt listet alle unterstützten Datenflüsse und veranschaulicht, wie diese Datenflüsse über verschiedene Anwendungsfälle verwendet werden. Für jeden Anwendungsfall beschreibt es die Sequenz und Auswahl von Datenströmen über ein Ablaufdiagramm. 

- **Teams mit Express Route Optimierung** - wird beschrieben, wie diese Datenflüsse verwendet werden, wenn Express Route zur Optimierung der über eine einfache Topologie dargestellt bereitgestellt wird.

## <a name="background"></a>Hintergrund
### <a name="network-segments"></a>Netzwerksegmenten
**Kundennetzwerk**: Dies ist das Netzwerksegment, die Sie verwalten und steuern. Dazu gehören alle Kunden Verbindungen innerhalb von Kunden Büros, ob verkabelten oder drahtlosen, zwischen Bürogebäude in lokalen Rechenzentren, und die Verbindung zu Internetanbieter, Express Route oder eine beliebige andere private peering. 

Ein Kundennetzwerk hat in der Regel mehrere Netzwerkperimeter mit Firewalls und/oder Proxyserver, die Sicherheitsrichtlinien Ihrer Organisation erzwingen und, mit denen nur bestimmte Netzwerkdatenverkehr, die Sie eingerichtet und konfiguriert haben. Da Sie dieses Netzwerk verwalten, Sie direkte Kontrolle über die Leistung des Netzwerks haben und es dringend empfohlen wird, führen Sie Netzwerk-Bewertungen um Leistung sowohl innerhalb von Standorten in Ihrem Netzwerk und aus dem Netzwerk, mit dem Office 365-Netzwerk zu überprüfen. 

**Internet**: Dies ist das Netzwerksegment, die Teil des gesamten Netzwerks ist, die von Benutzern verwendet werden, die außerhalb des Netzwerks Kunden mit Office 365 aus herstellen. Es wird auch von einigen Datenverkehr aus dem Kundennetzwerk zu Office 365 verwendet werden. 

**Besuchter/Gast privates Netzwerk**: Dies ist das Netzwerksegment außerhalb Ihres Netzwerks Kunden, aber nicht in das öffentliche Internet, die Ihre Benutzer und/oder ihre Gäste besuchen können. Beispielsweise Teams home privates Netzwerk oder einem privaten Unternehmensnetzwerk, die nicht bereitgestellt werden, in denen Ihre Benutzer und/oder Kunden, die Interaktion mit Diensten Teams befinden können.

>**Hinweis**: Verbindung mit Office 365 gilt auch für diese Netzwerke.

**Office 365**: Dies ist das Netzwerksegment, die Office 365-Diensten unterstützt. Es wird mit Rändern in das Kundennetzwerk in den meisten Speicherorten in der Nähe weltweit verteilt. In diesem Dokument genannte Funktionen umfassen Transport Relay, Konferenzserver und Medienprozessor. 

**Express-Route (optional)**: Dies ist das Netzwerksegment, die Teil des gesamten Netzwerks ist, die Sie eine dedizierte Verbindung mit dem Office 365-Netzwerk übergeben wird.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

**Real-Time Media**: innerhalb RTP (Real-Time Transport Protocol), die von Audio-, Video- und Bildschirmfreigabe Arbeitslasten unterstützt gekapselten Daten. Im Allgemeinen ist Mediendatenverkehr hoher Wartezeit von Groß-und Kleinschreibung sollten Sie würden diesen Datenverkehr, den am häufigsten direkten Pfad mögliche nehmen und UDP und TCP als Transportprotokoll Layer verwenden, ist die beste Transport für interaktive Real Time Media aus Sicht der Qualität . (Hinweis: als letztes Mittel, Medien können TCP/IP, und auch im HTTP-Protokoll getunnelt werden, aber es wird nicht empfohlen, aufgrund ungültiger Qualität Auswirkungen.) RTP-Fluss ist über SRTP, gesichert, in dem nur die Nutzlast verschlüsselt werden.

**Signalisierung**: die Verbindung zwischen dem Client und Server oder andere Clients, die zur Steuerung der Aktivitäten (beispielsweise, wenn ein Anruf initiiert wird), und Übermitteln von Sofortnachrichten. Die meisten signaldatenverkehr verwendet die HTTPS-basierte REST-Schnittstellen, obwohl in einigen Szenarien (z. B. Verbindung zwischen Office 365 und eines Session Border Controller) sie SIP-Protokoll verwendet. Es ist wichtig zu verstehen, dass dieser Datenverkehr einiges geringer Latenz vertrauliche ist jedoch möglicherweise Dienstausfälle oder Timeouts aufrufen, wenn die Wartezeit zwischen den Endpunkten einige Sekunden überschreitet. 

### <a name="connectivity-to-office-365"></a>Verbindung mit Office 365

Teams erfordert eine [Verbindung mit dem Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10). Endpunkt-URLs und IP-Adressbereichen Teams sind in [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)aufgeführt. (Hinweis: Öffnen Sie die Konnektivität für TCP-Ports 80 und 443, und UDP-Ports 3478 über 3481 erforderlich ist.) Darüber hinaus Teams ist abhängig von Skype für Business Online und auch mit dem Internet verbunden sein muss.

Teams fließt medienverbindung wird über Standardverfahren IETF ICE (Interactive Connectivity Establishment) implementiert.

### <a name="interoperability-restrictions"></a>Interoperabilität Einschränkungen
**Drittanbieter-Media-relays**: eine Teams Media Flow (d. h., einen der Endpunkte Media ist Teams) kann nur für Teams oder Skype für Business systemeigene Media Relays durchlaufen. Interoperabilität mit einem Drittanbieter-Mediarelay wird nicht unterstützt. (Hinweis: ein Drittanbieter SBC auf der Grenze mit PSTN müssen beendet RTP/RTCP-Streams, über SRTP, gesichert und leitet sie nicht an den nächsten Hop.)

**Dritten Partei SIP-Proxy-Server**: eine Teams Signale SIP-Dialog mit einem Drittanbieter SBC und/oder Gateway Teams oder Skype für systemeigene SIP-Proxys Business durchlaufen kann. Interoperabilität mit einem Drittanbieter-SIP-Proxy wird nicht unterstützt.

**Drittanbieter B2BUA (d. h., SBC)**: eine Teams Media Fluss von/an das Telefonfestnetz wird von einem Drittanbieter SBC beendet. Jedoch Interoperabilität mit einer dritten Partei SBC innerhalb des Netzwerks Teams (d. h., ein Drittanbieter SBC vermittelt zwei Teams/Skype für Business-Endpunkte werden) wird nicht unterstützt.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Technologien, die nicht, mit Microsoft-Teams empfohlen werden

**VPN-Netzwerk**: Es wird nicht empfohlen für Mediendatenverkehr (d. h., Fluss 2"). Der VPN-Client sollte geteilten VPN- und Route Mediendatenverkehr wie jeder Benutzer externe nicht-VPN-verwenden Sie gemäß https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.

>**Hinweis**: zwar des Titels Lync, dies gilt für Teams sowie.

**Paket-Shaping**: beliebigen Paket Snippers, Paketinspektion oder Packet Shaper Geräte werden nicht empfohlen und Qualität kann erheblich beeinträchtigt werden. 

### <a name="principles"></a>Grundsätze
Es gibt vier grundlegenden Prinzipien, die Ihnen helfen verstehen Response für Microsoft-Teams:
 
1.  Eine Microsoft-Teams Konferenz wird von Office 365 im selben Bereich gehostet, in dem der erste Teilnehmer beigetreten ist. (Hinweis: Wenn Ausnahmen zu dieser Regel in einige Topologien werden, sie werden in diesem Dokument beschriebenen, und durch eine entsprechende Anruffluss dargestellt.)

2.  Eine Teams Media-Endpunkt in Office 365 verwendeten basierend auf Medien, die Verarbeitung von Anforderungen und nicht auf den Anruftyp basiert. (Beispielsweise kann Gespräch Point verwenden einen Endpunkt Medien in der Cloud zu Prozess Medien für Lautschrift und/oder aufzeichnen, während eine Konferenz mit zwei Teilnehmern in der Cloud keine Medien Endpunkt verwenden kann.) Die meisten Konferenzen verwendet jedoch einen Media-Endpunkt für mischen und routing Zwecke zugewiesen, die Konferenz gehostet wird. Der Mediendatenverkehr an den Endpunkt Medien von einem Client gesendet möglicherweise direkt weitergeleitet oder Transport Relay in Office 365 verwenden, wenn aufgrund einer Customer Netzwerk Firewall erforderlich. 

3.  Mediendatenverkehr für Peer-zu-Peer-Anrufe, die direkte Route nutzen, die unter der Annahme, dass der Anruf einen Endpunkt Medien in der Cloud erfordert nicht verfügbar ist (siehe #2 oben). Wenn diese Route nicht verfügbar ist, klicken Sie dann eine oder mehrere Transport Relays wird Verkehr die bevorzugte Route ist direkt zu dem remote-Peer (Client). Es wird empfohlen, dass Mediendatenverkehr nicht quer Server wie Paket Shaping, VPN-Server und So weiter, darf da dies die Medienqualität auswirkt.

4.  Signaldatenverkehr immer wechselt zu den nächsten Server für den Benutzer. 

Weitere Einzelheiten zu den auf der Medienpfad, ausgewählt wird, finden Sie unter https://www.youtube.com/watch?v=1tmHMIlAQdo.

## <a name="call-flows-in-various-topologies"></a>Anrufflüssen in verschiedenen Topologien
### <a name="teams-topology"></a>Teams-Topologie
Diese Topologie wird von Kunden verwendet, die Dienste aus der Cloud ohne alle lokalen Bereitstellung, wie etwa Skype für Business Server oder Telefon System direkten Routing Teams nutzen. Darüber hinaus ist die Schnittstelle zu Office 365 über das Internet ohne Azure Express Route durchgeführt. 

[![Microsoft-Teams Online Anruf fließt Abbildung 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Abbildung 1: Teams Topologie*

Beachten Sie Folgendes:

- Die Richtung der Pfeile in der Abbildung wider Initiierung Richtung der Kommunikation, die Anbindung an die Enterprise-Perimeter wirkt sich auf. Im Fall von UDP für Medien die erste Paket(e) kann in umgekehrter Richtung flow, aber diese Pakete möglicherweise blockiert, bis die Pakete in der anderen Richtung positioniert werden.
- Teams Anzeigemodus Skype für Business Online bereitgestellt wird, daher werden Clients als "Teams/SFB User" angezeigt.

Weitere Informationen über die folgenden optionalen Topologien finden später in diesem Artikel:

- Skype für Unternehmen in der lokalen Bereitstellung in **Teams hybridtopologie**beschrieben wird.
- Telefon System direktes Routing (für PSTN-Anbindung) wird in **Teams mit direktem Routing Topologie**beschrieben.
- Express Route wird in **Teams mit Express Route Optimierung**beschrieben.

**Flow Beschreibungen**:
- **Fluss 2** – stellt einen Fluss von einem Benutzer im Netzwerk Kunden mit dem Internet als Teil des Benutzers Teams Erfahrung initiiert hat. Beispiele für diese Datenflüsse sind DNS- und Peer-zu-Peer-Medien.
- **Fluss 2"** – stellt einen Fluss von einem mobilen Teams Remotebenutzer, mit VPN an das Kundennetzwerk initiiert hat. 
- **Fluss 3** – stellt einen Fluss von einem mobilen Teams Remotebenutzer an Office 365-Teams Endpunkte initiiert hat. 
- **Fluss 4** – stellt einen Fluss von einem Benutzer im Netzwerk Kunden mit Office 365-Teams Endpunkten initiiert.
- **Fluss 5** – stellt einen Peer-zu-Peer-Media-Fluss zwischen Teams Benutzer und einem anderen Teams oder Skype für Benutzer innerhalb des Netzwerks Customer Business.
- **Fluss 6** – stellt einen Peer-zu-Peer-Media-Fluss zwischen einer mobilen Teams Remotebenutzer an und einem anderen Remote mobilen Teams oder Skype für Geschäftsbenutzer über das Internet.

#### <a name="use-case-one-to-one"></a>Verwenden von Case: 1: 1
1: 1-Anrufe verwenden ein gemeinsames Modell, in dem der Aufrufer eine Reihe von Kandidaten bestehend aus IP-Adressen/Ports – einschließlich lokalen, Relay und reflexive (öffentliche IP-Adresse des Clients gesehen von Relay) Kandidaten erhält. Der Aufrufer sendet diese Kandidaten an des angerufenen. der angerufene auch erhält eine ähnliche Reihe von Kandidaten und sendet sie an den Anrufer. STUN Konnektivitätsprüfung, die Nachrichten verwendet werden, um Partei Medien, an denen Pfade arbeiten Suchen der Aufrufer/aufgerufen und die beste funktionierenden Pfad ausgewählt ist. Medien (d. h., RTP/RTCP-Pakete gesichert über SRTP) werden unter Verwendung des ausgewählten Kandidaten gesendet. Das Transport-Relay wird als Bestandteil von Office 365 bereitgestellt.

Wenn die lokale IP-Adresse/externer Port haben Kandidaten oder die reflexiven Kandidaten Konnektivität, und klicken Sie dann der direkte Pfad zwischen den Clients (oder über ein NAT) für Medien ausgewählt wird. Wenn die Clients im Netzwerk Kunden sind, sollten der direkte Pfad ausgewählt sein. Dies erfordert eine direkte UDP-Konnektivität innerhalb des Netzwerks Kunden. Wenn die Clients beide mobiles Cloud-Benutzer sind, kann dann je nach der NAT/Firewall, direkte Verbindung verwenden.

Wenn ein Client im Netzwerk Kunden interne ist und einen Client (z. B. mobile Cloud-), externe können, ist es unwahrscheinlich, dass die direkte Verbindung zwischen der lokalen oder reflexiven Kandidaten funktionsfähig ist. Eine Option in diesem Fall ist die Verwendung eines der Transport Relay Kandidaten entweder Client aus (beispielsweise der interne Client erhalten Relay Kandidat aus der Transport-Relay in Office 365; STUN/RTP/RTCP-Pakete zum Senden können externe Clients muss die Transport-Relay). Eine weitere Option ist, dass der interne Client, erhält der Client mobilen Cloud Relay Kandidaten sendet. Beachten Sie, dass zwar UDP-Konnektivität für Medien wird dringend empfohlen, TCP unterstützt wird.

**Allgemeine Schritte aus**:
1. Benutzer A löst URL-Domänennamens (DNS) über flow2-Teams
2. Teams Benutzer A weist eine Media Relay-Anschluss auf Teams Transport Relay über den Datenfluss 4
3. Benutzer A sendet "einladen" mit ICE Kandidaten über den Datenfluss 4 zu Office 365-Teams
4. Office 365 sendet eine Benachrichtigung über den Datenfluss 4 Teams Benutzer b
5. Teams Benutzer B weist eine Media Relay-Anschluss auf Teams Transport Relay über den Datenfluss 4
6. Teams Benutzer B sendet "Antwort" mit ICE Kandidaten über den Datenfluss 4, die zurück an Teams Benutzer A über Ablauf 4 weitergeleitet wird
7. Teams Benutzer A und B Teams ICE-Konnektivitätstests aufrufen und bewährte verfügbaren Medienpfad aktiviert ist (siehe folgenden Diagramme für verschiedene Anwendungsfälle)
8. Teams Benutzer senden Telemetrie zu Office 365, über den Datenfluss 4

**Innerhalb des Kunden:**

[![Microsoft-Teams Online Anruf fließt Abbildung 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Abbildung 2: innerhalb des Kunden*
 
Peer-zu-Peer-Media-Fluss 5 ist Schritt 7 ausgewählt.
 
Medien sind bidirektionale. Die Richtung des fortlaufenden 5 gibt an, dass eine Seite die Kommunikation Konnektivität im Hinblick auf konsistent mit alle Datenflüsse in diesem Dokument initiiert. In diesem Fall ist es unerheblich, welche Richtung verwendet wird, da beide Endpunkte innerhalb des Netzwerks Kunden sind.

**Kundennetzwerk an externe Benutzer (Media Relay von Teams Transport Relay):**

[![Microsoft-Teams Online Anruf fließt Abbildung 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Abbildung 3 – Kundennetzwerk an externe Benutzer (Media Relay von Teams Transport Relay)*
 
In Schritt 7 sind Fluss 4, aus dem Netzwerk zu Office 365, Kunden und Fluss 3, mobilen Teams-Remotebenutzer zu Office 365, ausgewählt. Diese Datenströme werden von Teams Transport Relay in Office 365 weitergeleitet.

Medien sind bidirektionale, wobei Richtung gibt an, welche Seite die Kommunikation aus Sicht der Konnektivität initiiert. In diesem Fall werden diese Datenströme für Signale und Medien, über die verschiedenen Transportprotokollen und Adressen verwendet.

**Kundennetzwerk an externe Benutzer (direct Medien):**

[![Microsoft-Teams Online Anruf fließt Abbildung 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Abbildung 4: Kundennetzwerk an externe Benutzer (direct Medien)*
 
In Schritt 7 ist Ablauf Kundennetzwerk an Internet (Peer des Clients), 2, aktiviert.
- Direkte Medien mit mobilen Remotebenutzer (, die nicht über Office 365 weitergeleitet wird,) ist optional. Kunden kann mit anderen Worten, diesen Pfad zum Erzwingen der ein Medienpfad über Transport-Relay in Office 365 blockieren.

- Medien sind bidirektionale. Die Richtung des fortlaufenden 2 an mobile Remotebenutzer gibt an, dass eine Seite die Kommunikation aus Sicht der Konnektivität initiiert. 

**VPN-Benutzer an internen Benutzer (Media Relay von Teams Transport Relay)**

[![Microsoft-Teams Online Anruf fließt Abbildung 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Abbildung 5: VPN-Benutzer an internen Benutzer (Media Relay von Teams Transport Relay)*
 
Zwischen dem VPN an das Kundennetzwerk Signale per Flow 2' ist. Zwischen dem Kundennetzwerk und Office 365 Signale per Flow 4 ist. Allerdings Media umgeht das VPN und über fließt 3 und 4 bis Mediarelay in Office 365 Teams weitergeleitet wird.

**VPN-Benutzer an internen Benutzer (direct Medien)**

[![Microsoft-Teams Online Anruf fließt Abbildung 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Abbildung 6: VPN-Benutzer an internen Benutzer (direct Medien)*

Zwischen dem VPN an das Kundennetzwerk Signale per Flow 2' ist. Zwischen dem Kundennetzwerk und Office 365 Signale per Flow 4 ist. Allerdings Media umgeht das VPN und über den Datenfluss 2 aus dem Kundennetzwerk mit dem Internet weitergeleitet wird.

Medien sind bidirektionale. Die Richtung des fortlaufenden 2 an den remote mobilen Benutzer gibt an, dass eine Seite die Kommunikation aus Sicht der Konnektivität initiiert.

**VPN-Benutzer externe Benutzer (direct Medien)**

[![Microsoft-Teams, rufen Sie fließt Abbildung 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Abbildung 7: VPN-Benutzer externe Benutzer (direct Medien)*

Zwischen dem VPN-Benutzer an das Kundennetzwerk Signale ist über Ablauf 2" und über 4-Fluss zu Office 365. Allerdings Media umgeht VPN und über den Datenfluss 6 weitergeleitet wird.

Medien sind bidirektionale. Die Richtung des fortlaufenden 6 an den remote mobilen Benutzer gibt an, dass eine Seite die Kommunikation aus Sicht der Konnektivität initiiert.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Anwendungsfall: Teams PSTN über Office 365-Trunk
Office 365 verfügt über ein Telefon-System, das tätigen und annehmen von Anrufen aus im Public Switched Telephone Network, (PSTN) ermöglicht. Wenn Sie der PSTN-Trunk über das Telefon System aufrufen planen verbunden ist, sind keine besonderen Connectivity Anforderungen für diesen Anwendungsfall. (Wenn Sie Ihre eigene lokale PSTN-Trunk mit Office 365 verbinden möchten, können Sie Phone System direkten Routing verwenden.)

[![Microsoft-Teams Online Anruf fließt Abbildung 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Abbildung 8: PSTN über Office 365-Trunk-Teams*

#### <a name="use-case-teams-meeting"></a>Anwendungsfall: Teams Besprechung

Der Audio/Video/Bildschirmfreigabe (VBSS) ist Konferenzserver Bestandteil von Office 365. Es wurde eine öffentliche IP-Adresse, die muss über das Kundennetzwerk erreichbar sein und muss von einem Client mobiles Cloud erreichbar sein. Jeder Clientendpunkt muss an den Webkonferenz-Edgeserver herstellen können.

Interne Clients erhalten lokalen, reflexive und Relay Kandidaten auf die gleiche Weise wie für 1: 1-Anrufe beschrieben. Die Clients werden diese Kandidaten an den Webkonferenz-Edgeserver in eine Einladung senden. Der Konferenzserver verwendet Relay nicht, da es eine öffentlich erreichbaren IP-Adresse verfügt, damit es mit der lokalen IP-Adresse Candidate reagiert. Der Client- und Conferencing Server Überprüfen der Konnektivität auf die gleiche Weise für 1: 1-Anrufe beschrieben wird. 

Beachten Sie Folgendes:

- Teams Clients können nicht Skype für Business-Besprechungen teilnehmen, und Skype für Business Clients kann nicht Teams Besprechungen teilnehmen.

- Ein PSTN-Benutzer optional "wählt IN" oder "Gewählte OUT", je nach den Aufruf von PSTN Besprechungsorganisator und/oder Konferenzen bereitstellen. 

- Gast oder von einem Kunden-Benutzer kann über ein privates Netzwerk Gast, Mitglied der über Firmware/NAT mit strenge Regeln geschützt ist.

[![Microsoft-Teams Online Anruf fließt Abbildung 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Abbildung 9: Teams, die Besprechung*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Anwendungsfall: Verbund mit Skype für Unternehmen lokal

**Media Relay von Teams Transport Relay in Office 365**

[![Microsoft-Teams Online Anruf fließt Abbildung 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Abbildung 10: Media Relay von Teams Transport Relay in Office 365*

Beachten Sie Folgendes:

- Verbund bezeichnet per Definition eine Kommunikation zwischen zwei Mandanten. In diesem Fall Verbindung Mandanten ein, den Teams verwendet wird, mit dem Mandanten B, den Skype für Unternehmen lokal verwendet wird. Wenn Mandanten B auch Office 365 verwendet werden, müsste klicken Sie dann die Skype für Business Client Fluss 3 verwendet werden zum Herstellen der Verbindung mit Office 365.

- Signalisierung und aus der Sammelsuche Skype für Business-Client auf lokale Skype für Business Server liegt außerhalb des Bereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

- Signale zwischen Teams und Skype für Unternehmen wird durch ein Gateway in Office 365 überbrückt werden.

- Medien wird in diesem Fall mit dem Kundennetzwerk und remote Skype für Business-Client über den Datenfluss 4 von Teams Transport Relay in Office 365 weitergeleitet.

**Media von Skype Business Mediarelay in federated Mandanten weitergeleitet**

[![Microsoft-Teams Online Anruf fließt Abbildung 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Abbildung 11: Media von Skype Business Mediarelay in federated Mandanten weitergeleitet*

Beachten Sie Folgendes:

- Signalisierung und aus der Sammelsuche Skype für Business-Client auf einem lokalen Skype für Business Server liegt außerhalb des Bereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

- Signale zwischen Teams und Skype für Unternehmen wird durch ein Gateway in Office 365 überbrückt werden.

- Medien wird in diesem Fall von Skype Business lokalen Mediarelay an das Kundennetzwerk über Ablauf 2 weitergeleitet. (Beachten Sie, dass Datenverkehr von Teams Benutzer an das remote Media Relay im Kundennetzwerk verbundenen durch die Mediarelay bis Datenverkehr in umgekehrter Richtung um flow startet zunächst blockiert werden. Jedoch wird der bidirektionalen Datenfluss Connectivity in beide Richtungen geöffnet.)

**Direct (Peer-zu-Peer)**

[![Microsoft-Teams Online Anruf fließt Abbildung 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Abbildung 12: Direct (Peer-zu-Peer)*

### <a name="teams-hybrid-topology"></a>Teams hybridtopologie
Diese Topologie enthält Teams mit einer Skype für Business lokale Bereitstellung.

[![Microsoft-Teams Online Anruf fließt Abbildung 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Abbildung 13: Teams hybridtopologie*
 
- Die Richtung der Pfeile in der Abbildung wider Initiierung Richtung der Kommunikation, die Anbindung an die Enterprise-Perimeter wirkt sich auf. Im Fall von UDP für Medien die erste Paket(e) kann in umgekehrter Richtung flow, aber diese Pakete möglicherweise blockiert, bis die Pakete in der anderen Richtung positioniert werden.

- Teams Anzeigemodus Skype für Business Online bereitgestellt wird, daher werden Clients als "Teams/SFB User" angezeigt.

Zusätzliche fließt (auf der Basis Teams Topologie):
- **Fluss 5A** – stellt einen Peer-zu-Peer-Media-Fluss zwischen Teams Benutzer innerhalb des Netzwerks Kunden und einen Skype Business lokalen Mediarelay am Rand Kunden-Netzwerks.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Anwendungsfall: Skype für Unternehmen, die 1: 1-Teams
**Hybride innerhalb des Netzwerks Kunden**

[![Microsoft-Teams Online Anruf fließt Abbildung 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Abbildung 14: Hybrid innerhalb des Kunden*
 
Signale zwischen Teams und Skype für Unternehmen wird durch ein Gateway in Office 365 überbrückt werden. Medien werden jedoch weitergeleitet, direkt Peer-zu-Peer innerhalb der Kunde Netzwerk über den Datenfluss 5.

**Hybride Kundennetzwerk mit externen Skype für Geschäftsbenutzer – von Office 365 weitergeleitet**

[![Microsoft-Teams Online Anruf fließt Abbildung 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Abbildung 15 - Kundennetzwerk mit externen Skype für Geschäftsbenutzer Hybrid - Relay von Office 365*

Beachten Sie Folgendes:

- Signalisierung und aus der Skype für Business-Client auf einem lokalen Skype für Business Server liegt außerhalb des Bereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

- Signale zwischen Teams und Skype für Unternehmen wird durch ein Gateway in Office 365 überbrückt werden.

- Medien wird an das Kundennetzwerk über Ablauf 4 über Teams Transport Relay in Office 365 weitergeleitet.

**Hybride Kundennetzwerk mit externen Skype für Geschäftsbenutzer – vom lokalen Edge weitergeleitet**

[![Microsoft-Teams Online Anruf fließt Abbildung 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Abbildung 16 - Kundennetzwerk mit externen Skype für Geschäftsbenutzer Hybrid - weitergeleitet werden lokale Rand*
 
Beachten Sie Folgendes:

- Signalisierung und von Skype für Business-Client auf einem lokalen Skype für Business Server liegt außerhalb des Bereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

- Signale wird durch ein Gateway in Office 365 überbrückt werden.

- Medien wird von Skype Business Mediarelay in Skype für Business lokalen Edge für Benutzer innerhalb des Netzwerks Kunden über Media Fluss 5A Teams weitergeleitet.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams mit Phone System direkten Routing-Topologie
Diese Topologie enthält Teams mit Phone System direktem Routing. 

Direktes Routing können Sie einen Dienstanbieter für Drittanbieter-(Public Switched Telephone Network, PSTN) verwenden, indem Sie eine Kopplung ein unterstütztes lokales im Besitz des Kunden Session Border Controller (SBC) Hardwaregerät zu Office 365, und klicken Sie dann Verbinden des Telefonie-Trunks an das Gerät. 

Um dieses Szenario zu unterstützen, muss der Kunde einen zertifizierten SBC für die direkte Weiterleitung von einem Microsoft certified Partner bereitstellen. Der SBC muss konfiguriert werden, wie vom Hersteller empfohlen, und für direkte UDP-Datenverkehr von Office 365 routingfähig sein. Die Medien flow direkt von Teams und/oder die Skype für Business-Client auf den SBC (Umgehung des Teams Gateways) oder über das Gateway Teams durchlaufen. Die Konnektivität mit dem SBC bei der Trunk konfiguriert ist, das Gateway Teams umgehen ICE, basiert auf, in dem SBC ICE-Lite unterstützt, während die Teams/Skype für Business Media Endpunkt ICE vollständig unterstützt. 

[![Microsoft-Teams Online Anruf fließt Abbildung 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* Abbildung 17 - Teams mit Phone System direkten Routing-Topologie

Beachten Sie Folgendes:

- Die Richtung der Pfeile in der Abbildung wider Initiierung Richtung der Kommunikation, die Anbindung an die Enterprise-Perimeter wirkt sich auf. Im Fall von UDP für Medien die erste Paket(e) kann in umgekehrter Richtung flow, aber diese Pakete möglicherweise blockiert, bis die Pakete in der anderen Richtung positioniert werden.

- Teams Anzeigemodus Skype für Business Online bereitgestellt wird, daher werden Clients als "Teams/SFB User" angezeigt.

Zusätzliche fließt (auf der Basis Teams online Topologie):
- **Fluss 4'** - stellt einen Fluss von Office 365 mit dem Kundennetzwerk, das zum Herstellen eine Verbindung zwischen den Teams Medienserver in der Cloud mit den SBC lokal verwendet.
- **Fluss 5 b** – stellt einen Media-Fluss zwischen der Teams Benutzer innerhalb des Netzwerks Kunden mit der direkten Routing SBC im Umgehungsmodus.
- **Fluss 5 C** – stellt einen Media-Fluss zwischen den direkten Routing SBC zu einer anderen direkte Routing SBC in einem PSTN Hairpin Anruf Bypass-Modus.

**Interne Benutzer mit direktem Routing (Media Relay von Teams Transport Relay in Office 365)**

[![Microsoft-Teams Online Anruf fließt Abbildung 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Abbildung 18: interne Benutzer mit direktem Routing (Media Relay von Teams Transport Relay in Office 365)*

Beachten Sie Folgendes:
 
- Der SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

- Signalisierung und aus dem SBC zu Office 365 und umgekehrt verwenden Fluss 4 und/oder flow 4'.

- Signalisierung und vom Client innerhalb des Netzwerks Kunden zu Office 365 verwenden Fluss 4.


**Remotebenutzer mit direktem Routing (Medien werden über ein Medienserver (VA) in Office 365 geleitet)**

[![Microsoft-Teams Online Anruf fließt Abbildung 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Abbildung 19 - Remotebenutzer mit direktem Routing (Medien werden über ein Medienserver (VA) in Office 365 geleitet)*
 
Beachten Sie Folgendes:

- Der SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

- Signalisierung und aus dem SBC zu Office 365 und umgekehrt verwenden Fluss 4 und/oder flow 4'.

- Signalisierung und vom Client im Internet zu Office 365 verwenden Fluss 3.

**Interne Benutzer direkten Routing (medienumgehung)**

[![Microsoft-Teams Online Anruf fließt Abbildung 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Abbildung 20 - interner Benutzer direkten Routing (medienumgehung)*
 
Beachten Sie Folgendes:

- Der SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

- Verwenden von SBC zu Office 365 und umgekehrt Signale flow 4 und/oder flow 4'.

- Signale vom Client innerhalb des Netzwerks Kunden mit Office 365 verwenden Ablauf 4.

- Medien vom Client innerhalb des Netzwerks Kunden SBC innerhalb des Netzwerks Kunden verwenden Fluss 5 b.

**Remotebenutzer mit direktem Routing (medienumgehung von Teams Transport Relay in Office 365 weitergeleitet)**

[![Microsoft-Teams Online Anruf fließt Abbildung 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Abbildung 21 - Remotebenutzer mit direktem Routing (medienumgehung von Teams Transport Relay in Office 365 weitergeleitet)*

Beachten Sie Folgendes:

- Der SBC benötigen eine öffentliche IP-Adresse, die vom Office 365 und Internet geroutet werden kann.

- Aus den SBC zu Office 365 und umgekehrt Signale verwendet Fluss 4 und/oder Fluss 4'.

- Vom Client im Internet zu Office 365 Signale verwendet Fluss 3.

- Medien, vom Client im Internet für die SBC innerhalb des Netzwerks Kunden verwendet fließt 3 und 4, von Teams Transport Relay in Office 365 weitergeleitet. 

**Remotebenutzer direkten Routing (Direct medienumgehung)**

[![Microsoft-Teams Online Anruf fließt Abbildung 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Abbildung 22 - Remotebenutzer direkten Routing (Direct medienumgehung)*
 
Beachten Sie Folgendes:

- Der SBC benötigen eine öffentliche IP-Adresse, die vom Office 365 und dem Internet geroutet werden kann.

- Aus den SBC zu Office 365 und umgekehrt Signale verwendet Fluss 4 und/oder Fluss 4'.

- Vom Client im Internet zu Office 365 Signale verwendet Fluss 3.

- Medien, vom Client im Internet für die SBC innerhalb des Netzwerks Kunden verwendet Flow 2.

**Direktes Routing (medienumgehung) – PSTN HCR (aufgrund der Übertragung von weiterleiten/Aufruf)**

[![Microsoft-Teams Online Anruf fließt Abbildung 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Abbildung 23 - direkte Routing (medienumgehung) - PSTN-HCR (aufgrund der Übertragung von weiterleiten/Aufruf)*
 
Beachten Sie Folgendes:

- Der SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

- Aus den SBC zu Office 365 und umgekehrt Signale verwendet Fluss 4 und/oder Fluss 4'.

- Der Client ist nicht genügend die Signale und Medien Schleife, nachdem der Anruf Hairpinned über PSTN zu PSTN ist.

- Medien von SBC-Instanz eine innerhalb des Netzwerks Kunden SBC Instanz B innerhalb des Kunden Netzwerks (wobei, A und B dieselbe Instanz sein können) wird verwendet, Fluss 5 C.

**Direktes Routing (Medien über Office 365) – PSTN HCR zwei konstant**

[![Microsoft-Teams Online Anruf fließt Abbildung 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Abbildung 24 - direkte Routing (Medien über Office 365) – PSTN HCR zwei konstant*
 
Beachten Sie Folgendes:

- Der SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

- Aus den SBC zu Office 365 und umgekehrt Signale verwendet Fluss 4 und/oder Fluss 4'.

- Der Client ist nicht genügend die Signale und Medien Schleife, nachdem der Anruf Hairpinned über PSTN zu PSTN ist.

- Die von SBC-Instanz eine innerhalb des Netzwerks Kunden X SBC-Instanz B muss über Office 365-Media-Server weitergeleitet werden und kann nicht verwendet werden medienumgehung Modus.

## <a name="teams-with-express-route-optimization"></a>Teams mit Express Route Optimierung

[![Microsoft-Teams Online Anruf fließt Abbildung 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Abbildung 25 - Teams mit Express Route Optimierung*
 
Express Route ist ausgerichtet und bereitgestellt haben, und klicken Sie dann Teams fließt von erneut weitergeleitet werden konnte sollte das flow 4 zum flow 1 und Nachrichtenfluss von 4' 1' flow, um. Teams Anwendung hat jedoch eine harte Abhängigkeit auf anderen Office 365 Abläufe über das Internet über fließt 4 und 4'; Diese Datenflüsse müssen daher nicht verhindert werden. 

Beachten Sie, dass Skype für Business hybride Edge-Datenverkehr geleitet wird, mit dem Internet und nicht zum Express Route zur Kommunikation mit externen Benutzern und Verbund mit anderen Mandanten. 

Um asymmetrische Abläufe zu verhindern, muss die Umleitung in beide Richtungen. Anders ausgedrückt, ist eine Adresse innerhalb des Netzwerks Kunden routingfähige entweder über das Internet oder Express-weitergeleitet, basierend auf Optimierung, jedoch nicht über beide.

Beispiel:

**Kundennetzwerk an externe Benutzer (Media Relay von Teams Transport Relay):**

[![Microsoft-Teams Online Anruf fließt in Abbildung 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*In Abbildung 26 - Kundennetzwerk an externe Benutzer (Media Relay von Teams Transport Relay)*
 
**Allgemeine Schritte:**
1. Teams Benutzer innerhalb des Kunden löst URL Domänennamen (DNS) über flow2
2. Teams Benutzer innerhalb des Kunden weist eine Media Relay-Anschluss auf Teams Transport Relay über Fluss 1
3. Teams Benutzer innerhalb des Kunden sendet "einladen" mit ICE Kandidaten über Fluss 1 zu Office 365
4. OFFICE 365 sendet eine Benachrichtigung an externen Teams Benutzer über den Ablauf 3
5. Teams externer Benutzer weist eine Media Relay-Anschluss auf Teams Transport Relay über den Datenfluss 3
6. Teams externer Benutzer sendet "Antwort" mit ICE Kandidaten über den Datenfluss 3, die zurück an Teams Benutzer A über Ablauf 1 weitergeleitet wird
7. Teams Benutzer A und B Teams ICE-Konnektivitätstests aufrufen und wählt fließt 1 und 3, die von Teams Transport Relay in Office 365 weitergeleitet werden
8. Teams Benutzer senden Telemetrie zu Office 365 über fließt 1 und 3

>**Hinweis**: Ablauf 4 muss zur Unterstützung von Teams Anwendung Abhängigkeiten in andere Micro-Dienste, dass Mandaten 4 flow aktiviert werden.
