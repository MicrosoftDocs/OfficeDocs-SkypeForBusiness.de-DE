---
title: Microsoft-Teams, Online aufrufen fließt
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 06/08/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
description: Beschreibt, wie Teams Arbeitslast für Office 365 fließt in verschiedenen Topologien verwendet.
ms.openlocfilehash: 69b4deb078a0626c8a7cc4dce808825f2d038bac
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861817"
---
# <a name="microsoft-teams-online-call-flows"></a>Microsoft-Teams, Online aufrufen fließt

## <a name="overview"></a>Übersicht
In diesem Dokument wird beschrieben, wie Teams Arbeitslast für Office 365 fließt in verschiedenen Topologien verwendet. Darüber hinaus gibt es eindeutige Teams Abläufe, die für die Peer-to-Peer-medienkommunikation verwendet werden. Das Dokument listet diese Datenströme und beschreibt deren Zweck und ihren Ursprung-Beendigung Netzwerken. Beispielsweise Fluss X wird vom Office 365-Client lokal verwendet, um die Kommunikation mit Office 365-Dienst in der Cloud, stammt aus dem Netzwerk Kunden und durch einen Endpunkt in Office 365-Cloud beendet und Ablauf Y wird vom Office 365-Client lokal verwendet, um die Kommunikation mit ein Dienst auf dem Internet, die Office 365 abhängig, ist vom Netzwerk Kunden stammt, und wird durch einen Endpunkt im Internet beendet.

Das Dokument verfügt über drei Hauptbereiche. Die erste enthält eine Hintergrundinformationen, wie Netzwerke (die Office 365 Abläufe durchlaufen können), Datenverkehrstypen, Konnektivität-Leitfaden Kundennetzwerk zu Office 365-Endpunkten, die Interoperabilität mit Drittanbieter-Komponenten und Prinzipale, die werden von Teams, die zum Media fließt auswählen. Die zweite veranschaulicht die Verwendung der diese Datenflüsse in verschiedenen Topologien. Für jede Topologie Listet alle unterstützten Datenflüsse, und es wird veranschaulicht, wie diese Datenflüsse über verschiedene Anwendungsfälle verwendet werden. Für jeden Anwendungsfall beschreibt es die Sequenz und Auswahl von Datenströmen über ein Ablaufdiagramm. Die dritte wird beschrieben, wie diese Datenflüsse verwendet werden, wenn Express Route zur Optimierung der über eine einfache Topologie dargestellt bereitgestellt wird.

## <a name="background"></a>Hintergrund
### <a name="network-segments"></a>Netzwerksegmente
**Kundennetzwerk**: Dies ist das Netzwerksegment, die Teil des gesamten Netzwerks ist, die Sie verwalten und steuern. Dazu gehören alle Kunden Verbindungen innerhalb von Kunden Büros, ob verkabelten oder drahtlosen, zwischen Bürogebäude in lokalen Rechenzentren, und die Verbindung zu Internet-Anbieter, Express Route oder eine beliebige andere private peering. 

Ein Kundennetzwerk hat in der Regel mehrere Netzwerkperimeter mit Firewalls und/oder Proxyserver, die Sicherheitsrichtlinien einer Organisation erzwingen und, mit denen nur bestimmte Netzwerkdatenverkehr, die Sie eingerichtet und konfiguriert haben. Da der Kunde dieses Netzwerk verwaltet, der Kunde direkte Kontrolle über die Leistung des Netzwerks hat, und es dringend empfohlen wird, dass der Kunde vollständige Bewertung überprüfen Leistung innerhalb von Standorten in Ihrem Netzwerk und von Netzwerk Ihrer Netzwerk mit Office 365-Netzwerk. Skype für Unternehmen zur lokalen Bereitstellung und PSTN Session Border Controller, über das Netzwerk (d. h., direkte Routing) eine Verbindung mit PSTN sind optional.

**Internet**: Dies ist das Netzwerksegment, die Teil des gesamten Netzwerks ist, die von Benutzern verwendet werden, die Office 365-Cloud von außerhalb des Netzwerks Kunden verbunden sind. Es wird auch von einigen Datenverkehr aus dem Netzwerk Kunden in Office 365-Cloud verwendet. 

**Besuchter/Gast privates Netzwerk**: Dies ist das Netzwerksegment außerhalb Ihres Netzwerks Kunden, aber nicht in das öffentliche Internet, die Ihre Benutzer und/oder ihre Gäste besuchen können. Beispielsweise Teams home privates Netzwerk oder einem privaten Unternehmensnetzwerk, die nicht bereitgestellt werden, in denen Ihre Benutzer und/oder Kunden, die mit den Diensten Teams interagieren befinden kann.

>**Hinweis**: Verbindung mit Office 365b gilt auch für diese Netzwerke.

**Office 365-Cloud**: Dies ist das Netzwerksegment, die Office 365-Diensten unterstützt. Es wird weltweit mit Rändern in der Nähe des Kunden in den meisten Standorte verteilt. In diesem Dokument genannte Funktionen enthalten Transport Relay, Konferenzserver und Medienprozessor. 

**Express-Route (Optional)**: Dies ist das Netzwerksegment, die Teil des gesamten Netzwerks ist, die Sie eine dedizierte Verbindung mit dem Office 365-Netzwerk übergeben wird.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

**Real-Time Media**: innerhalb RTP (Real-Time Transport Protocol) und unterstützt Audio-, Video- und Bildschirmfreigabe Arbeitslasten gekapselten Daten. Im Allgemeinen ist Mediendatenverkehr hoher Wartezeit von Groß-und Kleinschreibung sollten Sie würden diesen Datenverkehr, den am häufigsten direkten Pfad mögliche nehmen und UDP und TCP als Transportprotokoll Layer verwenden, ist die beste Transport für interaktive Real Time Media aus Sicht der Qualität. (Hinweis: als letztes Mittel, Medien können TCP/IP, und auch im HTTP-Protokoll getunnelt werden, aber es wird nicht empfohlen, aufgrund ungültiger Qualität Auswirkungen.) RTP-Fluss ist über SRTP, gesichert, in dem nur die Nutzlast verschlüsselt werden.

**Signalisierung**: die Verbindung zwischen dem Client und Server oder andere Clients, die zur Steuerung der Aktivitäten (beispielsweise, wenn ein Anruf initiiert wird), und Übermitteln von Sofortnachrichten. Die meisten signaldatenverkehr verwendet die HTTPS-basierte REST-Schnittstellen, verwendet jedoch in einigen Szenarien (z. B.-Verbindung zwischen Office 365-Cloud und eines Session Border Controller) SIP-Protokoll. Es ist wichtig zu erkennen, dass dieser Datenverkehr einiges geringer Latenz beachtet wird jedoch kann dazu führen, dass Dienstausfälle oder rufen Sie Timeouts für die Wartezeit zwischen den Endpunkten einige Sekunden überschreiten. 

### <a name="connectivity-to-office-365"></a>Verbindung mit Office 365

Teams-Dienst erfordert die [Verbindung zum Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10). Teams Endpunkte URLs und IP-Adressbereichen sind in [Office 365-URLs und IP-Adressbereiche](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)aufgeführt. (Hinweis: Es erfordert Konnektivität für TCP-Ports 80 und 443 geöffnet und UDP-ports 3478 bis 3481.) Darüber hinaus Teams Service hat Abhängigkeit zu Skype für Business Onlinedienst, es ist daher erforderlich, um diesen Dienst auch mit dem Internet verbinden.

Teams fließt medienverbindung wird über Standardverfahren IETF ICE (Interactive Connectivity Establishment) implementiert.

### <a name="interoperability-restrictions"></a>Interoperabilität Einschränkungen
**Drittanbieter-Media-relays**: eine Teams Media Flow (d. h., einen der Endpunkte Media ist Teams) kann nur für Teams oder Skype für Business systemeigene Media Relays durchlaufen. Interoperabilität mit einem Drittanbieter-Mediarelay wird nicht unterstützt. (Hinweis: ein Drittanbieter SBC auf der Grenze mit PSTN müssen beendet RTP/RTCP-Streams, über SRTP, gesichert und leitet sie nicht an den nächsten Hop.)

**Drittanbieter SIP-Proxy-Server**: eine Teams Signale SIP-Dialog mit einem Drittanbieter SBC und/oder Gateway Teams oder Skype für systemeigene SIP-Proxys Business durchlaufen kann. Interoperabilität mit einem Drittanbieter SIP-Proxy wird nicht unterstützt.

**Drittanbieter B2BUA (d. h., SBC)**: eine Teams Media Fluss von/bis PSTN wird von einem Drittanbieter SBC beendet. Allerdings Interoperabilität mit dritte SBC innerhalb des Netzwerks Teams (d. h., Drittanbieter SBC vermittelt zwei Teams/Skype für Business-Endpunkte werden) wird nicht unterstützt.

### <a name="technologies-that-are-strongly-not-recommended-with-microsoft-teams"></a>Technologien, die mit Microsoft-Teams, stark nicht empfohlen werden

**VPN-Netzwerk**: Es wird dringend empfohlen nicht empfohlen für Mediendatenverkehr (d. h., Fluss 2"). VPN-Client sollten gemäß geteilten VPN- und Route Mediendatenverkehr wie jeder externen nicht-VPN-Benutzer verwenden.https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/ 

>**Hinweis**: zwar des Titels Lync, dies gilt für Teams sowie.

**Paket-Shaping**: beliebigen Paket Snippers, Paketinspektion oder Packet Shaper Geräte werden nicht dringend empfohlen, und Qualität kann erheblich beeinträchtigt werden. 

### <a name="principles"></a>Grundsätze
Es gibt vier grundlegenden Prinzipien, die Ihnen helfen verstehen Response für Microsoft-Teams. 
1.  Eine Microsoft-Teams Konferenz wird von Office 365-Cloud im selben Bereich gehostet, in dem der erste Teilnehmer beigetreten ist. (Hinweis: Wenn Ausnahmen zu dieser Regel in einige Topologien werden, werden sie in diesem Dokument, dargestellt durch eine entsprechende Anruffluss beschrieben werden.)
2.  Ein Teams Media-Endpunkt (VA) in Office 365-Cloud verwendet wird basierend auf Medien, die Verarbeitung von Anforderungen und nicht auf den Anruftyp basiert. (Beispielsweise kann ein Point-to-Point-Aufruf verwenden einen Endpunkt Medien in der Cloud zu Prozess Medien für Lautschrift und/oder aufzeichnen, während eine Konferenz mit zwei Teilnehmern in der Cloud keine Medien Endpunkt verwenden kann.) Die meisten Konferenzen verwendet jedoch ein VA für mischen und routing Zwecke zugewiesen, die Konferenz gehostet wird. Der von einem Client gesendet, um die VA Mediendatenverkehr möglicherweise direkt weitergeleitet werden oder Transport-Relay in Office 365-Cloud, verwenden Sie gegebenenfalls aufgrund einer Kundennetzwerk Firewall. 
3.  Mediendatenverkehr für Peer-zu-Peer-Anrufe, die direkte Route nutzen, die unter der Annahme, dass der Anruf ein VA in der Cloud erfordert nicht verfügbar ist (siehe #2 oben). Wenn diese Route nicht verfügbar ist, klicken Sie dann eine oder mehrere Transport Relays wird Verkehr die bevorzugte Route ist direkt zu dem remote-Peer (Client). Es wird empfohlen, dass Mediendatenverkehr nicht quer Server wie Paket Shaping, VPN-Server usw., darf da dies die Medienqualität auswirkt.
4.  Signaldatenverkehr immer wechselt zu den nächsten Server für den Benutzer. 

Weitere Einzelheiten zu den auf der Medienpfad, ausgewählt wird, finden Sie unter https://www.youtube.com/watch?v=aD5mUg2ZzLQ.

## <a name="call-flows-in-various-topologies"></a>Anrufflüssen in verschiedenen Topologien
### <a name="teams-online-pure-topology"></a>Teams Online ("reinen") – Topologie
Diese Topologie wird von Kunden verwendet, die Dienste von Teams aus der Cloud nutzen, ohne die Bereitstellung von beliebigen Servern wie Skype für Unternehmen und für die direkte Weiterleitung lokal SBC. Darüber hinaus ist die Schnittstelle zu Office 365 über das Internet ohne Azure Express Route durchgeführt. 

[![Microsoft-Teams Online Anruf fließt Abbildung 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Abbildung 1: Teams Online ('reine')-Topologie*

>**Notes**:
>- Die Richtung der Pfeile in der Abbildung wider Initiierung Richtung der Kommunikation, die Anbindung an die Enterprise-Perimeter wirkt sich auf. Im Fall von UDP für Medien die erste Paket(e) kann in umgekehrter Richtung flow, aber diese Pakete möglicherweise blockiert, bis die Pakete in der anderen Richtung positioniert werden.
>- Teams Online Anzeigemodus Skype für Business Online bereitgestellt wird, daher werden Clients als "Teams/SFB User" angezeigt.

- Optional Skype für Unternehmen zur lokalen Bereitstellung wird in diesem Dokument im Abschnitt **Teams Online Hybrid Topology** beschrieben.
- Optional direktes Routing für das PSTN wird in diesem Dokument im Abschnitt **Teams Online mit direkten Routingtopologie** beschrieben.
- Optional Express Route wird in diesem Dokument im Abschnitt **mit den Express-Route Optimierung Teams** beschrieben.

**Fließt Beschreibungen**:
- **Fluss 2** – stellt einen Fluss von einem Benutzer initiiert Customer-Netzwerk mit dem Internet als Teil seiner Teams wünschen. Beispiele für diese Datenflüsse sind DNS- und Peer-to-Peer-Medien.
- **Fluss 2"** – stellt einen Fluss von einem mobilen Teams Remotebenutzer, welche VPN zum Kundennetzwerk initiiert hat. 
- **Fluss 3** – stellt einen Fluss von einem mobilen Teams Remotebenutzer an Office 365-Teams Endpunkte initiiert hat. 
- **Fluss 4** – stellt einen Fluss von einem Benutzer im Netzwerk Kunden mit Office 365-Teams Endpunkten initiiert.
- **Fluss 5** – stellt einen Peer-to-Peer-Media-Fluss zwischen Teams Benutzer und einem anderen Teams oder Skype für Geschäftsbenutzer innerhalb des Kunden.
- **Fluss 6** – stellt eine Peer-to-Peer-medienfluss zwischen einem mobilen Teams Remotebenutzer und eine andere Remote mobilen Teams oder Skype für Geschäftsbenutzer, über das Internet.

#### <a name="use-case-one-to-one"></a>Verwenden von Case: 1: 1
1: 1-Anrufe verwenden ein gemeinsames Modell der Anrufer eine Reihe von Kandidaten bestehend aus IP-Adressen/Ports erhalten. lokale, Relay und reflexive (öffentliche IP-Adresse des Clients gesehen von Relay). Der Aufrufer sendet diese Kandidaten dem angerufenen einladen, des angerufenen auch einen ähnlichen Satz von Kandidaten erhält und sendet sie an den Anrufer. STUN Konnektivitätsprüfung, die Nachrichten verwendet werden, um Partei Medien, an denen Pfade arbeiten Suchen der Aufrufer/aufgerufen und die beste funktionierenden Pfad ausgewählt ist. Medien (d. h., RTP/RTCP-Pakete gesichert über SRTP) werden unter Verwendung des ausgewählten Kandidaten gesendet. Das Transport-Relay wird als Teil der Office 365-Cloud bereitgestellt.

Wenn die lokale IP-Adresse/externer Port haben Kandidaten oder die reflexiven Kandidaten Konnektivität, und klicken Sie dann der direkte Pfad zwischen den Clients (oder über ein NAT) für Medien ausgewählt wird. Wenn die Clients im Netzwerk Kunden sind, sollten der direkte Pfad ausgewählt sein. Dies erfordert eine direkte UDP-Konnektivität innerhalb des Netzwerks Kunden. Wenn die Clients beide mobiles Cloud-Benutzer sind, kann dann je nach der NAT/Firewall, direkte Verbindung verwenden.

Wenn ein Client ist ein interner im Netzwerk Kunden und einem Client extern (z. B. Cloud mobilen Benutzer), und es ist unwahrscheinlich, dass die direkte Verbindung zwischen der lokalen oder reflexiven Kandidaten funktionsfähig ist. Eine Option in diesem Fall ist die Verwendung eines der Transport Relay Kandidaten entweder Client aus (z. B. des interne Clients Relay Kandidat aus der Transport-Relay in Office 365-Cloud abgerufen, muss die externe Clients STUN/RTP/RTCP-Pakete zum Senden können die Transport-Relay). Eine weitere Option ist, dass der interne Client, erhält der Client mobilen Cloud Relay Kandidaten sendet. Beachten Sie, dass zwar UDP-Konnektivität für Medien wird dringend empfohlen, TCP unterstützt wird.

**Allgemeine Schritte**:
1. Benutzer A löst URL-Domänennamens (DNS) über flow2-Teams
2. Teams Benutzer A weist eine Media Relay-Anschluss auf Teams Transport Relay über den Datenfluss 4
3. Benutzer A sendet "einladen" mit ICE Kandidaten über den Datenfluss 4 zu Office 365-Teams
4. OFFICE 365 sendet eine Benachrichtigung über den Datenfluss 4 Teams Benutzer b
5. Teams Benutzer B weist eine Media Relay-Anschluss auf Teams Transport Relay über den Datenfluss 4
6. Teams Benutzer B sendet "Antwort" mit ICE Kandidaten über den Datenfluss 4, die zurück an Teams Benutzer A über Ablauf 4 weitergeleitet wird
7. Teams Benutzer A und B Teams ICE-Konnektivitätstests aufrufen und bewährte verfügbaren Medienpfad aktiviert ist (siehe folgenden Diagramme für verschiedene Anwendungsfälle)
8. Teams Benutzer senden Telemetrie zu Office 365, über den Datenfluss 4

**Innerhalb des Kunden:**

[![Microsoft-Teams Online Anruf fließt Abbildung 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Abbildung 2: innerhalb des Kunden*
 
In Schritt 7 ist "Peer-zu-Peer" Media Flow 5 ausgewählt. 
>**Hinweis**: Medien sind bidirektionale. Die Richtung des fortlaufenden 5 gibt an, dass eine Seite die Kommunikation Konnektivität im Hinblick auf konsistent mit alle Datenflüsse in diesem Dokument initiiert. In diesem Fall ist es unerheblich, welche Richtung verwendet wird, da beide Endpunkte innerhalb des Netzwerks Kunden sind.

**Kundennetzwerk an externe Benutzer (Media Relay von Teams Transport Relay):**

[![Microsoft-Teams Online Anruf fließt Abbildung 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Abbildung 3 – Kundennetzwerk an externe Benutzer (Media Relay von Teams Transport Relay)*
 
In Schritt 7 sind Fluss 4, aus dem Netzwerk zu Office 365, Kunden und Fluss 3, mobilen Teams-Remotebenutzer zu Office 365, ausgewählt. Diese Datenströme werden von Teams Transport Relay in Office 365 weitergeleitet.

>**Hinweis**: Medien sind bidirektionale, wobei Richtung gibt an, welcher Seite die Kommunikation aus Sicht der Konnektivität initiiert. In diesem Fall werden diese Datenströme für Signale und Medien, über die verschiedenen Transportprotokollen und Adressen verwendet.

**Kundennetzwerk an externe Benutzer (direct Medien):**

[![Microsoft-Teams Online Anruf fließt Abbildung 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Abbildung 4: Kundennetzwerk an externe Benutzer (direct Medien)*
 
In Schritt 7 ist Ablauf Kundennetzwerk an Internet (Peer des Clients), 2, aktiviert.
>**Notes**: 
>- Direkt-Medien mit mobilen Remotebenutzer (d. h., nicht weitergeleitet über Office 365-Cloud) ist optional. Kunden kann mit anderen Worten, Blockieren dieser Pfad und erzwingen Sie auf diese Weise eine Medienpfad über Transport-Relay in Office 365-Cloud.
>- Medien sind bidirektionale. Die Richtung des fortlaufenden 2 an mobile Remotebenutzer gibt an, dass eine Seite die Kommunikation aus Sicht der Konnektivität initiiert. 

**VPN-Benutzer an internen Benutzer (Media Relay von Teams Transport Relay)**

[![Microsoft-Teams Online Anruf fließt Abbildung 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Abbildung 5: VPN-Benutzer an internen Benutzer (Media Relay von Teams Transport Relay)*
 
Signale VPN zum Kundennetzwerk über Ablauf 2" und 4-Fluss zu Office 365. Jedoch "medienumgehung" VPN und über fließt 3 und 4 bis Teams Mediarelay in Office 365-Cloud weitergeleitet.

**VPN-Benutzer an internen Benutzer (direct Medien)**

[![Microsoft-Teams Online Anruf fließt Abbildung 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Abbildung 6: VPN-Benutzer an internen Benutzer (direct Medien)*

Signale VPN zum Kundennetzwerk über Fluss 2' auf Kundennetzwerk und Fluss 4 zu Office 365. Jedoch "medienumgehung" VPN und über den Datenfluss 2 aus Kundennetzwerk an das Internet weitergeleitet.

>**Hinweis**: Medien sind bidirektionale. Die Richtung des fortlaufenden 2 an mobile Remotebenutzer gibt an, dass eine Seite die Kommunikation aus Sicht der Konnektivität initiiert.

**VPN-Benutzer externe Benutzer (direct Medien)**

[![Microsoft-Teams Online Anruf fließt Abbildung 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Abbildung 7: VPN-Benutzer externe Benutzer (direct Medien)*

Signale VPN zum Kundennetzwerk über Fluss 2' auf Kundennetzwerk und Fluss 4 zu Office 365. Jedoch "medienumgehung" VPN und über den Datenfluss 6 weitergeleitet.

>**Hinweis**: Medien sind bidirektionale. Die Richtung des fortlaufenden 6 an mobile Remotebenutzer gibt an, dass eine Seite die Kommunikation aus Sicht der Konnektivität initiiert.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Anwendungsfall: Teams PSTN über Office 365-Trunk
Office 365-Cloud verfügt über ein Telefon-System, das tätigen und Empfangen von der Anrufe von Public Switched Telephone Network ermöglicht. Wenn Sie den PSTN-Trunk über Office 365-Cloud verbunden ist, sind keine besonderen Connectivity Anforderungen für diesen Anwendungsfall. Anderenfalls (direktes Routing bereitgestellt wird) finden Sie im Abschnitt **TBD**.

[![Microsoft-Teams Online Anruf fließt Abbildung 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Abbildung 8: PSTN über Office 365-Trunk-Teams*

#### <a name="use-case-teams-meeting"></a>Anwendungsfall: Teams Besprechung

Der Audio/Video/Bildschirmfreigabe (VBSS) ist Konferenzserver Bestandteil der Office 365-Cloud. Es wurde eine öffentliche IP-Adresse, die muss über das Netzwerk Kunden erreichbar sein und muss von einem Client mobiles Cloud erreichbar sein. Jeder Clientendpunkt muss an den Webkonferenz-Edgeserver herstellen können.

Interne Clients erhalten lokalen, reflexive und Relay Kandidaten auf die gleiche Weise wie für 1: 1-Anrufe beschrieben. Die Clients werden diese Kandidaten an den Konferenzserver in eine Einladung senden. Der Konferenzserver verwendet Relay nicht, da es eine öffentlich erreichbaren IP-Adresse verfügt, damit es mit nur die lokale IP-Adresse Candidate reagiert. Der Client- und Conferencing Server Überprüfen der Konnektivität auf die gleiche Weise für 1: 1-Anrufe beschrieben wird. 

>**Notes**:
>- Teams Clients können nicht Skype für Business-Besprechungen teilnehmen, und Skype für Business Clients kann nicht Teams Besprechungen teilnehmen.
>- PSTN-Benutzer optional "wählt IN" oder "Gewählte OUT", hängt davon ab, der Besprechung Organisator PSTN aufrufen und/oder Konferenzen bereitstellen. 
>- Gast oder von einem Kunden-Benutzer kann über ein privates Netzwerk Gast, Mitglied der über Firmware/NAT mit strenge Regeln geschützt ist.

[![Microsoft-Teams Online Anruf fließt Abbildung 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Abbildung 9: Teams, die Besprechung*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Anwendungsfall: Verbund mit Skype für Unternehmen lokal

**Media Relay von Teams Transport Relay in Office 365-Cloud**

[![Microsoft-Teams Online Anruf fließt Abbildung 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Abbildung 10: Media von Teams Transport Relay in Office 365-Cloud weitergeleitet*

>**Notes**: 
>- "Verbund" ist definitionsgemäß eine Kommunikation zwischen zwei Mandanten. In diesem Fall Verbindung Mandanten ein, den Teams Online verwendet wird, mit dem Mandanten B, den Skype für Unternehmen lokal verwendet wird. Wenn Mandanten B auch Office 365 verwendet werden, müsste klicken Sie dann Skype für Business Client Fluss 3 verwendet werden zum Herstellen der Verbindung mit Office 365.
>- Signalisierung und von föderierten Skype für Business-Client auf seine Skype für Unternehmen auf dem lokalen Server liegt außerhalb des Bereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

Signale zwischen Teams und Skype für Unternehmen ist "durch ein Gateway in Office 365-Cloud überbrückt".

Medien wird in diesem Fall von Teams Transport Relay in Office 365-Cloud Kundennetzwerk und Remote Skype für Business-Client über fließt 4 weitergeleitet.

**Media von Skype Business Mediarelay in federated Mandanten weitergeleitet**

[![Microsoft-Teams Online Anruf fließt Abbildung 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Abbildung 11: Media von Skype Business Mediarelay in federated Mandanten weitergeleitet*

>**Hinweis**: Signal- und medienprotokolle von föderierten Skype für Business-Client auf seine Skype für Unternehmen auf dem lokalen Server liegt außerhalb des Gültigkeitsbereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

Signale zwischen Teams und Skype für Unternehmen ist "durch ein Gateway in Office 365-Cloud überbrückt".

Medien wird in diesem Fall von Skype für Unternehmen lokal Media Relay an Kundennetzwerk über Ablauf 2 weitergeleitet. (Beachten Sie, dass Datenverkehr von Teams Benutzer an das remote Media Relay in federated Kundennetzwerk zunächst von der Media Relay blockiert wird, bis Datenverkehr in umgekehrter Richtung mit flow beginnt. Jedoch wird der bidirektionalen Datenfluss Connectivity in beide Richtungen geöffnet.)

**Direct (Peer-zu-Peer)**

[![Microsoft-Teams Online Anruf fließt Abbildung 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Abbildung 12: Direct (Peer-to-Peer)*

### <a name="teams-online-hybrid-topology"></a>Teams Online Hybridtopologie
Diese Topologie ist vergleichbar mit Teams Online Default ("reine"), aber "Fügt auf" Skype für Unternehmen lokal.

[![Microsoft-Teams Online Anruf fließt Abbildung 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Abbildung 13: Teams Online Hybridtopologie*
 
>**Notes**:
>- Die Richtung der Pfeile in der Abbildung wider Initiierung Richtung der Kommunikation, die Anbindung an die Enterprise-Perimeter wirkt sich auf. Im Fall von UDP für Medien die erste Paket(e) kann in umgekehrter Richtung flow, aber diese Pakete möglicherweise blockiert, bis die Pakete in der anderen Richtung positioniert werden.
>- Teams Online Anzeigemodus Skype für Business Online bereitgestellt wird, daher werden Clients als "Teams/SFB User" angezeigt.

Zusätzliche fließt (auf der Basis Teams Online "reinen" Topologie):
- **Fluss 5A** – stellt einen Peer-to-Peer-Media-Fluss zwischen Teams Benutzer innerhalb des Kunden mit einer Skype für Unternehmen auf Mediarelay am Rand des Kunden vor Ort.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Anwendungsfall: Skype für Unternehmen, die 1: 1-Teams
**Hybride innerhalb des Kunden**

[![Microsoft-Teams Online Anruf fließt Abbildung 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Abbildung 14: Hybrid innerhalb des Kunden*
 
Signale zwischen Teams und Skype für Business ist "durch ein Gateway in Office 365-Cloud überbrückt". Medien werden jedoch direkt "Peer-zu-Peer" innerhalb des Kunden über den Datenfluss 5 weitergeleitet.

**Hybride Kundennetzwerk mit externen Skype für Geschäftsbenutzer – von Office 365 weitergeleitet**

[![Microsoft-Teams Online Anruf fließt Abbildung 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Abbildung 15 - Kundennetzwerk mit externen Skype für Geschäftsbenutzer Hybrid - Relay von Office 365*
 
>**Hinweis**: Signale und Medien von Skype für Business-Client zu Skype für Unternehmen auf dem lokalen Server liegt außerhalb des Gültigkeitsbereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

Signale zwischen Teams und Skype für Unternehmen ist "durch ein Gateway in Office 365-Cloud überbrückt".

Medien wird über Teams Transport Relay in Office 365 zum Kundennetzwerk über fließt 4 weitergeleitet.

**Hybride Kundennetzwerk mit externen Skype für Geschäftsbenutzer – durch weitergeleitet werden, auf dem lokalen edge**

[![Microsoft-Teams Online Anruf fließt Abbildung 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Abbildung 16 - Kundennetzwerk mit externen Skype für Geschäftsbenutzer Hybrid - durch weitergeleitet werden, auf dem lokalen edge*
 
>**Hinweis**: Signale und Medien von Skype für Business-Client zu Skype für Unternehmen auf dem lokalen Server liegt außerhalb des Gültigkeitsbereichs dieses Dokuments. Es ist jedoch hier aus Gründen der Übersichtlichkeit dargestellt.

Signale ist "durch ein Gateway in Office 365-Cloud überbrückt".

Medien wird von Skype Business Mediarelay in Skype für Unternehmen lokal Edge Teams Benutzer innerhalb des Kunden über Media Fluss 5A weitergeleitet.

### <a name="teams-online-with-direct-routing-topology"></a>Teams Online mit "direkt" Routingtopologie
Diese Topologie ist vergleichbar mit Teams Online ("reine"), aber "Fügt auf" Direktes Routing. 

Direktes Routing, früher bekannt als BYOT (schalten Sie Ihren eigenen Trunk), mit einem Drittanbieter Public Switched Telephone Telefondienst Anbieter. Diese Methode kann durch eine Kopplung ein unterstütztes lokales im Besitz des Kunden Session Border Controller Hardwaregerät in Office 365-Cloud und Herstellen einer Verbindung mit dem Trunk Telefonie auf dem Gerät. 

Um dieses Szenario zu unterstützen, muss Kunden zertifizierten SBC(s) für die direkte Weiterleitung von einem Microsoft certified Partner bereitstellen. Der SBC muss wie vom Hersteller empfohlen ordnungsgemäß konfiguriert werden, und aus der Office 365-Cloud für direkte UDP-Datenverkehr routingfähig sein. Das Medium kann direkt von Teams/Skype für Business-Client zur SBC (Umgehung Teams Gateway (d. h., VA)) oder durchlaufen Teams Gateway übertragen werden. Die Konnektivität mit dem SBC Wenn Trunk konfiguriert ist, Teams Gateway umgehen ICE, basiert auf, in dem SBC ICE-Lite unterstützt, während Teams/Skype für Business Media Endpunkt ICE vollständig unterstützt. 

[![Microsoft-Teams Online Anruf fließt Abbildung 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Abbildung 17: Teams Online mit Topologie "Direktes Routing"*

>**Notes**:
>- Die Richtung der Pfeile in der Abbildung wider Initiierung Richtung der Kommunikation, die Anbindung an die Enterprise-Perimeter wirkt sich auf. Im Fall von UDP für Medien die erste Paket(e) kann in umgekehrter Richtung flow, aber diese Pakete möglicherweise blockiert, bis die Pakete in der anderen Richtung positioniert werden.
>- Teams Online Anzeigemodus Skype für Business Online bereitgestellt wird, daher werden Clients als "Teams/SFB User" angezeigt.

Zusätzliche fließt (auf der Basis Teams Online "reinen" Topologie):
- **Fluss 4'** - stellt eine fließt von Office 365-Cloud zur Kundennetzwerk, verwendet zum Herstellen einer Verbindungs zwischen Teams Medienserver in der Cloud mit den SBC lokal.
- **Fluss 5 b** – stellt einen Media-Fluss zwischen Teams Benutzer innerhalb des Netzwerks mit direkten Routing SBC Kunden im Modus "umgehen".
- **Fluss 5 C** – stellt einen Media-Fluss zwischen direkte Routing SBC beziehen, um eine andere direkte Routing SBC im PSTN Hairpin Anruf "umgehen"-Modus.

**Interne Benutzer direkten Routing (Media Relay von Teams Transport Relay in Office 365)**

[![Microsoft-Teams Online Anruf fließt Abbildung 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Abbildung 18: interne Benutzer direkten Routing (Media Relay von Teams Transport Relay in Office 365)*
 
>**Hinweis**: SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

Signalisierung und aus SBC zu Office 365 und umgekehrt verwenden Fluss 4 und/oder flow 4'.

Signalisierung und vom Client innerhalb des Kunden in Office 365-Cloud verwenden Fluss 4.


**Remote Benutzer direkten Routing (Media durch ein Medienserver (VA) in Office 365 weitergeleitet wird)**

[![Microsoft-Teams Online Anruf fließt Abbildung 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Abbildung 19: Remote Benutzer direkten Routing (Medien werden über ein Medienserver (VA) in Office 365 geleitet)*
 
>**Hinweis**: SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

Signalisierung und aus SBC zu Office 365 und umgekehrt verwenden Fluss 4 und/oder flow 4'.

Signalisierung und vom Client im Internet in Office 365-Cloud verwenden Fluss 3.

**Interne Benutzer direkten Routing (medienumgehung)**

[![Microsoft-Teams Online Anruf fließt Abbildung 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Abbildung 20 - interner Benutzer direkten Routing (medienumgehung)*
 
>**Hinweis**: SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

Verwenden von SBC zu Office 365 und umgekehrt Signale flow 4 und/oder flow 4'.

Signale vom Client innerhalb des Netzwerks für Kunden mit Office 365 Cloud Verwendung Ablauf 4.

Medien, vom Client innerhalb des Kunden für SBC innerhalb des Kunden verwenden Fluss 5 b.

**Remotebenutzer direkten Routing (medienumgehung von Teams Transport Relay in Office 365 weitergeleitet)**

[![Microsoft-Teams Online Anruf fließt Abbildung 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Abbildung 21 - Remotebenutzer direkten Routing (medienumgehung von Teams Transport Relay in Office 365 weitergeleitet)*
 
>**Hinweis**: SBC benötigen eine öffentliche IP-Adresse, die vom Office 365 und Internet geroutet werden kann.

Verwenden von SBC zu Office 365 und umgekehrt Signale flow 4 und/oder flow 4'.

Signale vom Client im Internet zu Office 365 Cloud Verwendung Fluss 3.

Medien vom Client im Internet SBC innerhalb des Kunden verwenden fließt 3 und 4, von Teams Transport Relay in Office 365-Cloud weitergeleitet. 

**Remotebenutzer direkten Routing (Direct medienumgehung)**

[![Microsoft-Teams Online Anruf fließt Abbildung 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Abbildung 22 - Remotebenutzer direkten Routing (Direct medienumgehung)*
 
>**Hinweis**: SBC benötigen eine öffentliche IP-Adresse, die vom Office 365 und Internet geroutet werden kann.

Verwenden von SBC zu Office 365 und umgekehrt Signale flow 4 und/oder flow 4'.

Signale vom Client im Internet zu Office 365 Cloud Verwendung Fluss 3.

Medien vom Client im Internet SBC innerhalb des Kunden verwenden Flow 2.

**Direktes Routing (medienumgehung) – PSTN HCR (aufgrund der Übertragung von weiterleiten/Aufruf)**

[![Microsoft-Teams Online Anruf fließt Abbildung 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Abbildung 23 - direkte Routing (medienumgehung) - PSTN-HCR (aufgrund der Übertragung von weiterleiten/Aufruf)*
 
>**Hinweis**: SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

Verwenden von SBC zu Office 365 und umgekehrt Signale flow 4 und/oder flow 4'.

Client liegt außerhalb des der Signale und Medien Schleife, nachdem der Anruf Hairpin über PSTN zu PSTN ist.

Medien von SBC-Instanz eine innerhalb des Kunden auf SBC Instanz B innerhalb des Kunden (wobei, A und B dieselbe Instanz sein können) verwenden Fluss 5 C.

**Direktes Routing (Medien über Office 365) – PSTN HCR zwei konstant**

[![Microsoft-Teams Online Anruf fließt Abbildung 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Abbildung 24 - direkte Routing (Medien über Office 365) – PSTN HCR zwei konstant*
 
>**Hinweis**: SBC benötigen eine öffentliche IP-Adresse, die von Office 365 routingfähig ist.

Verwenden von SBC zu Office 365 und umgekehrt Signale flow 4 und/oder flow 4'.

Client liegt außerhalb des der Signale und Medien Schleife, nachdem der Anruf Hairpin über PSTN zu PSTN ist.

Die von SBC-Instanz eine innerhalb von Kunden Netzwerk X SBC-Instanz B muss über Office 365-Media-Server weitergeleitet werden und kann nicht verwendet werden medienumgehung Modus.

## <a name="teams-w-express-route-optimization"></a>Teams mit Express Route Optimierung

[![Microsoft-Teams Online Anruf fließt Abbildung 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Abbildung 25 - Teams mit Express Route Optimierung*
 
Express Route ist ausgerichtet und bereitgestellt haben, und klicken Sie dann Teams fließt von erneut weitergeleitet werden konnte sollte das flow 4 zum flow 1 und Nachrichtenfluss von 4' 1' flow, um. Teams Anwendung hat jedoch harte Abhängigkeit auf anderen OFFICE 365 Abläufe über das Internet über fließt 4 und 4'; Diese Datenflüsse müssen daher nicht verhindert werden. 

Beachten Sie, dass Skype für Business Hybrid Edge-Datenverkehr mit dem Internet und nicht zum Express Route Kommunikation mit externen Benutzern und mit anderen Mandanten "Verbund" geleitet wird. 

Um asymmetrische Abläufe zu verhindern, muss die Umleitung in beide Richtungen. Anders ausgedrückt, ist eine Adresse innerhalb des Kunden routingfähige entweder über das Internet oder Express-weitergeleitet, basierend auf Optimierung, jedoch nicht über beide.

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
7. Teams Benutzer A und B Teams ICE-Konnektivitätstests aufzurufen, und wählt fließt 1 und 3, die von Teams Transport Relay in Office 365-Cloud weitergeleitet werden.
8. Teams Benutzer senden Telemetrie zu Office 365 über fließt 1 und 3

>**Hinweis**: Ablauf 4 muss zur Unterstützung von Teams Anwendung Abhängigkeiten in andere Micro-Dienste, dass Mandaten 4 flow aktiviert werden.
