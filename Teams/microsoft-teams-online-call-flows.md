---
title: Microsoft Teams-Anrufflüsse
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Beschreibt, wie Teams Office 365-Flows in verschiedenen Topologien verwenden.
ms.openlocfilehash: 91be46f556419dfd1ba8c52a99b8f06a19c63542
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573412"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams-Anrufflüsse

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams Ihr Netzwerk nutzen und wie Sie optimale Netzwerkkonnektivität planen: [Teams-Netzwerkplanung](https://aka.ms/teams-networking)

## <a name="overview"></a>Übersicht
In diesem Artikel wird beschrieben, wie Teams Office 365-Anruf Flüsse in verschiedenen Topologien verwenden. Darüber hinaus werden eindeutige Teams-Flows beschrieben, die für die Peer-to-Peer-Medien Kommunikation verwendet werden. Das Dokument beschreibt diese Flüsse, deren Zweck und deren Herkunft und Kündigung im Netzwerk. Für die Zwecke dieses Artikels gehen Sie folgendermaßen vor:

- Flow X wird vom lokalen Office 365-Client verwendet, um mit dem Office 365-Dienst in der Cloud zu kommunizieren. Sie stammt aus dem Kundennetzwerk und wird als Endpunkt in Office 365 beendet.

- Flow Y wird vom lokalen Office 365-Client verwendet, um mit einem Dienst im Internet zu kommunizieren, von dem Office 365 abhängig ist. Sie stammt aus dem Kundennetzwerk und wird als Endpunkt im Internet beendet.

Der Artikel enthält die folgenden Abschnitte:

- **Hintergrund** – bietet Hintergrundinformationen, wie etwa Netzwerke, die von Office 365 Flows möglicherweise durchlaufen werden, Art des Datenverkehrs, Verbindungs Anleitungen vom Kundennetzwerk zu Office 365-Dienstendpunkten, Interoperabilität mit Komponenten von Drittanbietern und Grundsätze, die von Teams zur Auswahl von Medienströmen verwendet werden.

- **Anruf Flüsse in verschiedenen Topologien** -veranschaulicht die Verwendung von Anruf strömen in verschiedenen Topologien. Für jede Topologie werden im Abschnitt alle unterstützten Flows aufgelistet, und es wird gezeigt, wie diese Flüsse über mehrere Anwendungsfälle verwendet werden. Für jeden Anwendungsfall werden die Reihenfolge und die Auswahl der Datenflüsse über ein Flussdiagramm beschrieben. 

- **Teams mit Express-Routenoptimierung** – beschreibt, wie diese Flows verwendet werden, wenn die Express Route zur Optimierung bereitgestellt wird, die über eine einfache Topologie dargestellt wird.

## <a name="background"></a>Hintergrund
### <a name="network-segments"></a>Netzwerksegmente
**Kundennetzwerk**: Dies ist das Netzwerksegment, das Sie steuern und verwalten. Dazu gehören alle Kundenverbindungen innerhalb von Kundenbüros, ob verkabelt oder drahtlos, zwischen Bürogebäuden, lokalen Rechenzentren und ihren Verbindungen mit Internet Anbietern, Express Route oder einem anderen privaten Peering. 

In der Regel verfügt ein Kundennetzwerk über mehrere Netzwerkperimeter mit Firewalls und/oder Proxyservern, die die Sicherheitsrichtlinien Ihrer Organisation erzwingen und nur bestimmten von Ihnen eingerichteten und konfigurierten Netzwerkdatenverkehr gestatten. Da Sie dieses Netzwerk verwalten, haben Sie direkte Kontrolle über die Leistung des Netzwerks, und es wird dringend empfohlen, dass Sie Netzwerkbewertungen durchführen, um die Leistung sowohl innerhalb von Websites in Ihrem Netzwerk als auch in Ihrem Netzwerk mit dem Office 365-Netzwerk zu überprüfen. 

**Internet**: Hierbei handelt es sich um das Netzwerksegment, das Teil des gesamten Netzwerks ist und von Benutzern verwendet wird, die eine Verbindung mit Office 365 von außerhalb des Kunden Netzwerks herstellen. Sie wird auch von einigen Datenverkehr vom Kundennetzwerk zu Office 365 verwendet. 

**Privates Netzwerk besucht/Gast**: Dies ist das Netzwerksegment außerhalb Ihres Kunden Netzwerks, aber nicht im öffentlichen Internet, das Ihre Nutzer und/oder Ihre Gäste besuchen können. Beispielsweise privates privates Netzwerk oder privates Unternehmensnetzwerk, in dem keine Teams bereitgestellt werden, in denen sich Ihre Benutzer und/oder deren Kunden, die mit den Team Diensten interagieren, befinden können.

>**Hinweis**: die Konnektivität zu Office 365 gilt auch für diese Netzwerke.

**Office 365**: Dies ist das Netzwerksegment, das die Office 365-Dienste unterstützt. Sie wird weltweit mit Kanten in der Nähe des Kunden Netzwerks an den meisten Standorten vertrieben. Zu den in diesem Dokument erwähnten Funktionen gehören Transport Relay, Konferenzserver und medienprozessor. 

**Express Route (optional)**: Hierbei handelt es sich um das Netzwerksegment, das Teil Ihres gesamten Netzwerks ist und Ihnen eine dedizierte, private Verbindung zum Office 365-Netzwerk bietet.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

**Echt Zeit Medien**: Daten, die in RTP (Real-Time Transport Protocol) gekapselt sind und die Audio-, Video-und Bildschirmfreigabe-Arbeitslasten unterstützen. Im Allgemeinen ist der Mediendatenverkehr in hohem Maße Latenz empfindlich, daher sollten Sie diesen Datenverkehr so verwenden, dass er den direktsten Pfad ermöglicht und UDP und TCP als Transportschichtprotokoll verwendet, das der beste Transport für interaktive Echt Zeit Medien aus einer qualitätsperspektive ist. . (Hinweis: als letztes Mittel können Medien TCP/IP verwenden und auch innerhalb des HTTP-Protokolls getunnelt werden, aber es wird nicht empfohlen, da die Auswirkungen auf schlechte Qualität zurückzuführen sind.) Der RTP-Fluss wird über SRTP gesichert, in dem nur die Nutzlast verschlüsselt ist.

**Signalisieren**: die Kommunikationsverbindungzwischen dem Client und dem Server oder anderen Clients, die zum Steuern von Aktivitäten verwendet werden (beispielsweise, wenn ein Anruf initiiert wird) und Sofortnachrichten übermitteln. Die meisten Signalisierungsdaten Verkehr verwendet die HTTPS-basierten Ruhe Schnittstellen, obwohl in einigen Szenarien (beispielsweise die Verbindung zwischen Office 365 und einem Session Border Controller) SIP-Protokoll verwendet wird. Es ist wichtig zu verstehen, dass dieser Datenverkehr viel weniger anfällig für Latenz ist, aber möglicherweise Dienstausfälle oder Anruf Timeouts verursacht, wenn die Wartezeit zwischen den Endpunkten mehrere Sekunden überschreitet. 

### <a name="connectivity-to-office-365"></a>Konnektivität zu Office 365

Für Teams ist eine [Internet Verbindung](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)erforderlich. Teams-Endpunkt-URLs und IP-Adressbereiche werden in [Office 365-URLs und IP-Adressbereichen](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)aufgelistet. (Hinweis: offene Verbindungen mit TCP-Anschlüssen 80 und 443 und UDP-Ports 3478 bis 3481 sind erforderlich.) Darüber hinaus hat Teams eine Abhängigkeit von Skype for Business Online, die ebenfalls mit dem Internet verbunden sein muss.

Die Konnektivität von Teams Media Flows wird über Standardverfahren für IETF Ice (Interactive Connectivity Establishment) implementiert.

### <a name="interoperability-restrictions"></a>Interoperabilitäts Einschränkungen
**Medien-Relays von Drittanbietern**: ein Media-Flow von Teams (also einer der Medien Endpunkte ist Teams) kann nur Teams oder Skype for Business-Medien Relais durchlaufen. Die Interoperabilität mit einem Medien Relais eines Drittanbieters wird nicht unterstützt. (Hinweis: ein Drittanbieter-SBC an der Grenze mit PSTN muss den RTP/RTCP-Datenstrom kündigen, der über SRTP gesichert ist, und nicht an den nächsten Hop weiterleiten.)

**SIP-Proxy Server von Drittanbietern**: ein Teams, das SIP-Dialog mit einem SBC-und/oder Gateway eines Drittanbieters signalisiert, kann Teams oder Skype for Business-SIP-Proxys durchlaufen. Die Interoperabilität mit einem SIP-Proxy eines Drittanbieters wird nicht unterstützt.

**Drittanbieter-B2BUA (also SBC)**: ein Media-Flow von Teams vom/zum PSTN wird von einem Drittanbieter-SBC beendet. Allerdings wird die Interoperabilität mit einem Drittanbieter-SBC innerhalb des Teams-Netzwerks (also eine Drittanbieter-SBC vermittelt zwei Teams/Skype for Business-Endpunkten) nicht unterstützt.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Technologien, die in Microsoft Teams nicht empfohlen werden

**VPN-Netzwerk**: Es wird nicht für Mediendatenverkehr (also Flow 2 ') empfohlen. Der VPN-Client sollte Split-VPN verwenden und Mediendatenverkehr wie alle externen nicht-VPN-Benutzer weiterleiten https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/, wie in angegeben.

>**Hinweis**: Obwohl der Titel lync ist, gilt er auch für Teams.

**Paket-shaper**: jede Art von Paket-Schnapper, Packet-Inspection oder Packet Shaper-Geräten wird nicht empfohlen, und die Qualität kann erheblich beeinträchtigt werden. 

### <a name="principles"></a>Prinzipien
Es gibt vier allgemeine Grundsätze, die Ihnen helfen, die Anruf Flüsse für Microsoft Teams zu verstehen:
 
1.  Eine Microsoft Teams-Konferenz wird von Office 365 in der gleichen Region gehostet, in der der erste Teilnehmer beigetreten ist. (Hinweis: Wenn in einigen Topologien Ausnahmen von dieser Regel vorhanden sind, werden Sie in diesem Dokument beschrieben und durch einen entsprechenden Anruffluss veranschaulicht.)

2.  Ein medienendpunkt für Teams in Office 365 wird basierend auf den Anforderungen der Medienverarbeitung und nicht auf der Grundlage des Anruf Typs verwendet. (Beispielsweise kann ein Punkt-zu-Punkt-Anruf einen medienendpunkt in der Cloud verwenden, um Medien für die Transkription und/oder Aufzeichnung zu verarbeiten, während eine Konferenz mit zwei Teilnehmern keinen medienendpunkt in der Cloud verwenden darf.) Die meisten Konferenzen verwenden jedoch einen medienendpunkt zu Misch-und Routingzwecken, der der Konferenz zugewiesen wird. Der Mediendatenverkehr, der von einem Client an den medienendpunkt gesendet wird, wird möglicherweise direkt weitergeleitet, oder es wird ein Transport Relay in Office 365 verwendet, wenn dies aufgrund von Einschränkungen des Kundennetzwerk Firewalls erforderlich ist. 

3.  Der Mediendatenverkehr für Peer-to-Peer-Anrufe nimmt den direkt verfügbaren Weg an, vorausgesetzt, dass der Anruf keinen medienendpunkt in der Cloud vorschreibt (siehe #2 oben). Die bevorzugte Route richtet sich direkt an den Remote-Peer (Client), wenn diese Route aber nicht verfügbar ist, wird ein oder mehrere Transport Relays den Datenverkehr weiterleiten. Es wird empfohlen, dass Mediendatenverkehr keine transversalen Server wie Paket-shaper, VPN-Server usw. enthält, da sich dies auf die Medienqualität auswirkt.

4.  Der Signalisierungs Datenverkehr geht immer an den nächstgelegenen Server des Benutzers. 

Weitere Informationen zu den Details des ausgewählten Medien Pfads finden Sie unter https://www.youtube.com/watch?v=1tmHMIlAQdo.

## <a name="call-flows-in-various-topologies"></a>Anruf Flüsse in verschiedenen Topologien
### <a name="teams-topology"></a>Teams-Topologie
Diese Topologie wird von Kunden verwendet, die Teams-Services aus der Cloud ohne lokale Bereitstellung nutzen, wie beispielsweise die direkte Weiterleitung von Skype for Business Server oder Phone System. Darüber hinaus erfolgt die Schnittstelle zu Office 365 über das Internet ohne Azure Express-Route. 

[![Microsoft Teams Online-Anruf Flüsse Abbildung 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Abbildung 1: Topologie der Teams*

Beachten Sie Folgendes:

- Die Richtung der Pfeile in der obigen Abbildung spiegelt die Initiierungs Richtung der Kommunikation wider, die sich auf die Konnektivität in den Umkreis des Unternehmens auswirkt. Im Fall von UDP für Medien können die ersten (n) Pakete in umgekehrter Richtung fließen, aber diese Pakete können blockiert werden, bis Pakete in der anderen Richtung fließen.
- Teams werden nebeneinander mit Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Nutzer" angezeigt.

Weitere Informationen zu den folgenden optionalen Topologien finden Sie weiter unten im Artikel:

- Die lokale Skype for Business-Bereitstellung wird in der **Hybrid Topologie von Teams**beschrieben.
- Das direkte Routing des Telefonsystems (für PSTN-Konnektivität) wird in **Teams mit direkter Routingtopologie**beschrieben.
- Express Route wird in **Teams mit Express Route Optimization**beschrieben.

**Fluss Beschreibungen**:
- **Flow 2** – stellt einen Fluss dar, der von einem Benutzer im Kundennetzwerk für das Internet als Teil der Team Erfahrung des Benutzers initiiert wurde. Beispiele für diese Datenströme sind DNS-und Peer-to-Peer-Medien.
- **Flow 2 '** – stellt einen Fluss dar, der von einem mobilen Remote Teams-Benutzer initiiert wird, mit VPN zum Kundennetzwerk. 
- **Flow 3** – stellt einen Fluss dar, der von einem mobilen Remoteteams-Benutzer zu Office 365/Teams-Endpunkten initiiert wurde. 
- **Flow 4** – stellt einen Fluss dar, der von einem Benutzer im Kundennetzwerk zu Office 365/Teams-Endpunkten initiiert wurde.
- **Flow 5** – stellt einen Peer-to-Peer-Medienfluss zwischen einem Teams-Benutzer und anderen Teams oder einem Skype for Business-Benutzer im Kundennetzwerk dar.
- **Flow 6** – stellt einen Peer-to-Peer-Medienfluss zwischen einem mobilen Remoteteams-Benutzer und einem anderen mobilen Remote Team oder einem Skype for Business-Benutzer über das Internet dar.

#### <a name="use-case-one-to-one"></a>Anwendungsfall: 1:1
1:1-Anrufe verwenden ein allgemeines Modell, bei dem der Anrufer eine Reihe von Kandidaten erhält, die aus IP-Adressen/Ports bestehen--einschließlich lokaler, Relay-und reflexiver (öffentliche IP-Adresse des Clients, wie Sie von den Relay-Kandidaten angezeigt werden). Der Anrufer sendet diese Kandidaten an den angerufenen Teilnehmer; der angerufene Teilnehmer erhält ebenfalls einen ähnlichen Satz von Kandidaten und sendet ihn an den Anrufer. Nachrichten zur Betäubungs Verbindungsüberprüfung werden verwendet, um zu ermitteln, welche Anrufer/angerufenen Medienpfade funktionieren, und es wird der beste Arbeitspfad ausgewählt. Medien (also RTP-RTCP-Pakete, die über SRTP gesichert wurden) werden dann mit dem ausgewählten Kandidaten paar gesendet. Das Transport Relay wird als Teil von Office 365 bereitgestellt.

Wenn die lokalen IP-Adressen/Port Kandidaten oder die reflexiven Kandidaten über eine Verbindung verfügen, wird der direkte Pfad zwischen den Clients (oder über ein NAT) für Medien ausgewählt. Wenn die Clients beide im Kundennetzwerk sind, sollte der direkte Pfad ausgewählt sein. Dies erfordert eine direkte UDP-Konnektivität innerhalb des Kunden Netzwerks. Wenn es sich bei den Clients sowohl um nomadische Cloud-Nutzer handelt, können Medien je nach NAT/Firewall direkte Verbindungen verwenden.

Wenn ein Client im Kundennetzwerk intern ist und ein Client extern ist (beispielsweise ein mobiler Cloud-Benutzer), ist es unwahrscheinlich, dass eine direkte Verbindung zwischen den lokalen oder reflexiven Kandidaten funktioniert. In diesem Fall besteht die Möglichkeit, einen der Transport Relay-Kandidaten von einem der beiden Clients zu verwenden (beispielsweise hat der interne Client einen Relay-Kandidaten vom Transport-Relay in Office 365 erhalten; der externe Client muss Stun/RTP/RTCP-Pakete an die Transport-Relay). Eine weitere Möglichkeit besteht darin, dass der interne Client an den vom mobilen Cloud-Client erhaltenen Relay-Kandidaten sendet. Beachten Sie, dass TCP unterstützt wird, obwohl die UDP-Konnektivität für Medien sehr empfehlenswert ist.

**Schritte auf höherer Ebene**:
1. Teams User A behebt URL-Domänennamen (DNS) über Cashflow2
2. Teams-Benutzer a ordnet einen Media Relay-Port im Teams-Transport-Relay über Flow 4 zu
3. Teams Benutzer A sendet "einladen" mit ICE-Kandidaten über Flow 4 an Office 365
4. Office 365 sendet eine Benachrichtigung an Teams Benutzer B über Flow 4
5. Teams Benutzer B ordnet einen Media Relay-Port im Teams-Transport-Relay über Flow 4 zu
6. Teams Benutzer B sendet "Antwort" mit ICE-Kandidaten über Flow 4, der über Flow 4 wieder an Teams-Benutzer weitergeleitet wird.
7. Teams Benutzer a und Teams Benutzer B rufen Ice-Verbindungstests auf, und der beste verfügbare Medienpfad ist ausgewählt (siehe Diagramme unten für verschiedene Anwendungsfälle).
8. Benutzer von Teams senden Telemetrie an Office 365 über Flow 4

**Im Kundennetzwerk:**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Abbildung 2: im Kundennetzwerk*
 
In Schritt 7 ist Peer-to-Peer Media Flow 5 ausgewählt.
 
Das Medium ist bidirektional. Die Richtung von Flow 5 gibt an, dass eine Seite die Kommunikation aus einer Verbindungs Perspektive initiiert, die mit allen Datenströmen in diesem Dokument konsistent ist. In diesem Fall ist es unerheblich, in welche Richtung die beiden Endpunkte im Kundennetzwerk eingesetzt werden.

**Kundennetzwerk für externe Benutzer (Medien, die von Teams-Transport-Relay weitergeleitet werden):**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Abbildung 3: Kundennetzwerk für externe Benutzer (Medien, die von Teams-Transport Relay weitergeleitet werden)*
 
In Schritt 7 sind Flow 4, vom Kundennetzwerk zu Office 365 und Flow 3, von Remote mobilen Teams Benutzer zu Office 365, ausgewählt. Diese Flows werden von Teams Transport Relay in Office 365 weitergeleitet.

Das Medium ist bidirektional, wobei Direction angibt, welche Seite die Kommunikation aus einer Verbindungs Perspektive initiiert. In diesem Fall werden diese Datenflüsse für Signalisierungen und Medien über verschiedene Transportprotokolle und-Adressen verwendet.

**Kundennetzwerk für externe Benutzer (direkt Medien):**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Abbildung 4: Kundennetzwerk für externe Benutzer (direkt Medien)*
 
In Schritt 7 wird Flow 2 vom Kundennetzwerk zu Internet (Client-Peer) ausgewählt.
- Das direkte Medium mit einem mobilen Remotebenutzer (der nicht über Office 365 weitergeleitet wird) ist optional. Anders ausgedrückt, kann der Kunde diesen Pfad blockieren, um einen Medienpfad durch Transport Relay in Office 365 zu erzwingen.

- Das Medium ist bidirektional. Die Flussrichtung 2 für den mobilen Remotebenutzer gibt an, dass eine Seite die Kommunikation aus einer Verbindungs Perspektive initiiert. 

**VPN-Benutzer zum internen Benutzer (Medien, die von Teams-Transport Relay weitergeleitet werden)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Abbildung 5: VPN-Benutzer zu internem Benutzer (Medien, die von Teams-Transport Relay weitergeleitet werden)*
 
Die Signalübertragung zwischen dem VPN und dem Kundennetzwerk erfolgt über Flow 2 '. Die Signalübertragung zwischen dem Kundennetzwerk und Office 365 erfolgt über Flow 4. Medien umgeht jedoch die VPN-Verbindung und wird über Flows 3 und 4 über Teams-Medien Relay in Office 365 weitergeleitet.

**VPN-Benutzer zum internen Benutzer (direkt Medien)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Abbildung 6: VPN-Benutzer zu internem Benutzer (direkt Medien)*

Die Signalübertragung zwischen dem VPN und dem Kundennetzwerk erfolgt über Flow 2 '. Die Signalübertragung zwischen dem Kundennetzwerk und Office 365 erfolgt über Flow 4. Medien umgeht jedoch das VPN und wird über Flow 2 vom Kundennetzwerk an das Internet weitergeleitet.

Das Medium ist bidirektional. Die Flussrichtung 2 für den mobilen Remotebenutzer gibt an, dass eine Seite die Kommunikation aus einer Verbindungs Perspektive initiiert.

**VPN-Benutzer für externen Benutzer (direkt Medien)**

[![Microsoft Teams-Anruf Flüsse, Abbildung 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Abbildung 7: VPN-Benutzer zu externem Benutzer (direkt Medien)*

Die Signalübertragung zwischen dem VPN-Benutzer und dem Kundennetzwerk erfolgt über Flow 2 und über Flow 4 an Office 365. Medien umgeht jedoch VPN und wird über Flow 6 weitergeleitet.

Das Medium ist bidirektional. Die Flussrichtung 6 für den mobilen Remotebenutzer gibt an, dass eine Seite die Kommunikation aus einer Verbindungs Perspektive initiiert.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Anwendungsfall: Teams zu PSTN über Office 365 trunk
Office 365 verfügt über ein Telefon System, das das platzieren und empfangen von Anrufen über das öffentlich geschaltete Telefonnetz (PSTN) ermöglicht. Wenn der PSTN-Stamm über den Telefon System-Anrufplan verbunden ist, gibt es keine besonderen Verbindungsanforderungen für diesen Anwendungsfall. (Wenn Sie Ihren eigenen lokalen PSTN-Stamm mit Office 365 verbinden möchten, können Sie das direkte Routing des Telefonsystems verwenden.)

[![Microsoft Teams Online-Anruf Flüsse Abbildung 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Abbildung 8 – Teams für PSTN über Office 365 trunk*

#### <a name="use-case-teams-meeting"></a>Anwendungsfall: Teams-Besprechung

Der schlechte VBSS-Konferenzserver (Audio/Video/Bildschirmfreigabe) ist Teil von Office 365. Sie hat eine öffentliche IP-Adresse, die vom Kundennetzwerk aus erreichbar sein muss und von einem nomadischen Cloud-Client aus erreichbar sein muss. Jeder Client/Endpunkt muss in der Lage sein, eine Verbindung mit dem Konferenzserver herzustellen.

Interne Clients erhalten lokale, reflexive und Relay-Kandidaten auf die gleiche Weise wie bei Einzelgesprächen beschrieben. Die Clients senden diese Kandidaten in einer Einladung an den Konferenzserver. Der Konferenzserver verwendet kein Relay, da er über eine öffentlich erreichbare IP-Adresse verfügt, sodass er mit seinem lokalen IP-Adressen Kandidaten antwortet. Der Client-und Konferenzserver überprüft die Konnektivität auf die gleiche Weise, die für Einzel Anrufe beschrieben wird. 

Beachten Sie Folgendes:

- Teams-Clients können nicht an Skype for Business-Besprechungen teilnehmen, und Skype for Business-Clients können nicht an Teambesprechungen teilnehmen.

- Ein PSTN-Benutzer kann je nach PSTN-Anruf und/oder Conferencing-Bereitstellung der Besprechung optional "Einwahl" oder "gewählt" wählen. 

- Ein Gastbenutzer oder ein Kunden Benutzer kann von einem privaten Gastnetzwerk teilnehmen, das über FW/NAT mit strengen Regeln geschützt ist.

[![Microsoft Teams Online-Anruf Flüsse Abbildung 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Abbildung 9 – Teams-Besprechung*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Anwendungsfall: Föderation mit Skype for Business vor Ort

**Medien, die von Teams Transport Relay in Office 365 weitergeleitet werden**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Abbildung 10 – Medien, die von Teams Transport Relay in Office 365 weitergeleitet werden*

Beachten Sie Folgendes:

- Föderation ist per Definition eine Kommunikation zwischen zwei Mandanten. In diesem Fall wird Mandant a, der Teams verwendet, mit dem Mandanten B zusammen, der Skype for Business lokal verwendet. Wenn Mandant B ebenfalls Office 365 verwendet, würde der Skype for Business-Client Flow 3 für die Verbindung mit Office 365 verwenden.

- Signalisierungs-und Medienübertragungen vom Partner-Skype for Business-Client zu lokalen Skype for Business-Servern liegen außerhalb des Umfangs dieses Dokuments. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Das signalisieren zwischen Teams und Skype for Business wird von einem Gateway in Office 365 überbrückt.

- In diesem Fall wird das Medium von Teams Transport Relay in Office 365 an das Kundennetzwerk und den Remote-Skype for Business-Client über Flow 4 weitergeleitet.

**Medien, die von Skype for Business-Medien Relay in Federated-Mandanten weitergeleitet werden**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Abbildung 11 – Medien, die von Skype for Business-Medien Relay in Federated-Mandanten weitergeleitet werden*

Beachten Sie Folgendes:

- Signalisierungs-und Medienübertragungen vom Partner-Skype for Business-Client zu einem lokalen Skype for Business-Server liegen außerhalb des Umfangs dieses Dokuments. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Das signalisieren zwischen Teams und Skype for Business wird von einem Gateway in Office 365 überbrückt.

- In diesem Fall wird das Medium von Skype for Business lokal über Flow 2 an das Kundennetzwerk weitergeleitet. (Beachten Sie, dass der Datenverkehr vom Team Benutzer zum Remotemedien Relay im Verbund Kundennetzwerk zunächst vom Medien Relay blockiert wird, bis der Verkehr in umgekehrter Richtung beginnt zu fließen. Der bidirektionale Fluss wird jedoch die Konnektivität in beide Richtungen öffnen.)

**Direkt (Peer-to-Peer)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Abbildung 12: direkt (Peer-to-Peer)*

### <a name="teams-hybrid-topology"></a>Hybrid Topologie für Teams
Diese Topologie umfasst Teams mit einer lokalen Bereitstellung von Skype for Business.

[![Microsoft Teams Online-Anruf Flüsse Abbildung 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Abbildung 13 – Hybrid Topologie für Teams*
 
- Die Richtung der Pfeile in der obigen Abbildung spiegelt die Initiierungs Richtung der Kommunikation wider, die sich auf die Konnektivität in den Umkreis des Unternehmens auswirkt. Im Fall von UDP für Medien können die ersten (n) Pakete in umgekehrter Richtung fließen, aber diese Pakete können blockiert werden, bis Pakete in der anderen Richtung fließen.

- Teams werden nebeneinander mit Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Nutzer" angezeigt.

Zusätzliche Flows (oben auf der Teams-Topologie):
- **Flow 5A** – stellt einen Peer-to-Peer-Medienfluss zwischen einem Team Benutzer innerhalb des Kunden Netzwerks und einem lokalen Skype for Business-Medien Relay am Kundennetzwerk Edge dar.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Anwendungsfall: Teams zu Skype für Unternehmen eins-zu-eins
**Hybrid innerhalb des Kunden Netzwerks**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Abbildung 14: Hybrid im Kundennetzwerk*
 
Das signalisieren zwischen Teams und Skype for Business wird von einem Gateway in Office 365 überbrückt. Medien werden jedoch über Flow 5 direkt im Kundennetzwerk weitergeleitet.

**Hybrid-Kundennetzwerk mit externem Skype for Business-Benutzer – Weitergeleitet von Office 365**

[![Microsoft Teams Online-Anruf Flüsse in Abbildung 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Abbildung 15: Hybrid-Kundennetzwerk mit externen Skype for Business-Benutzern, die von Office 365 weitergeleitet werden*

Beachten Sie Folgendes:

- Signalisierungs-und Medienübertragungen vom Skype for Business-Client zu einem lokalen Skype for Business-Server liegen außerhalb des Umfangs dieses Dokuments. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Das signalisieren zwischen Teams und Skype for Business wird von einem Gateway in Office 365 überbrückt.

- Medien werden über das Teams-Transport-Relay in Office 365 über Flow 4 an das Kundennetzwerk weitergeleitet.

**Hybrid-Kundennetzwerk mit externen Skype for Business-Benutzern – weitergeleitet durch lokales Edge**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Abbildung 16: Hybrid-Kundennetzwerk mit externen Skype for Business-Benutzern, die von lokal Edge weitergeleitet werden*
 
Beachten Sie Folgendes:

- Signalisierungs-und Medienübertragungen von Skype for Business-Client zu einem lokalen Skype for Business-Server liegen außerhalb des Umfangs dieses Dokuments. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Das signalisieren wird von einem Gateway in Office 365 überbrückt.

- Media wird von Skype for Business Media Relay innerhalb von Skype for Business lokal Edge an Teams-Nutzer innerhalb des Kunden Netzwerks über Media Flow 5A weitergeleitet.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams mit direkter Routing Topologie für das Telefon System
Diese Topologie umfasst Teams mit direktem Telefon System-Routing. 

Mithilfe des direkten Routings können Sie einen öffentlichen PSTN-Dienstanbieter (Public Switched Telephone Network) verwenden, indem Sie ein unterstütztes lokales Kunden-Hardwaregerät (SBC) mit Office 365 verbinden und dann den Telefon Stamm an Dieses Gerät. 

Zur Unterstützung dieses Szenarios muss der Kunde einen zertifizierten SBC für die direkte Weiterleitung von einem der von Microsoft zertifizierten Partner bereitstellen. Der SBC muss vom Hersteller als empfohlen konfiguriert und von Office 365 für direkten UDP-Datenverkehr geroutet werden können. Das Medium kann direkt von Teams und/oder dem Skype for Business-Client zum SBC (Bypassing des Teams-Gateways) oder durchqueren des Teams-Gateways fließen. Die Konnektivität mit dem SBC, wenn der trunk so konfiguriert ist, dass das Team-Gateway umgangen wird, basiert auf Ice, wobei SBC Ice-Lite unterstützt, während der Media-Endpunkt von Teams/Skype for Business Ice Full unterstützt. 

[![Microsoft Teams Online-Anruf Flüsse Abbildung 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* Abbildung 17 – Teams mit direkter Routing Topologie für das Telefon System

Beachten Sie Folgendes:

- Die Richtung der Pfeile in der obigen Abbildung spiegelt die Initiierungs Richtung der Kommunikation wider, die sich auf die Konnektivität in den Umkreis des Unternehmens auswirkt. Im Fall von UDP für Medien können die ersten (n) Pakete in umgekehrter Richtung fließen, aber diese Pakete können blockiert werden, bis Pakete in der anderen Richtung fließen.

- Teams werden nebeneinander mit Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Nutzer" angezeigt.

Zusätzliche Flows (oben auf der Team Online-Topologie):
- **Flow 4 '** – stellt einen Fluss von Office 365 in das Kundennetzwerk dar, der zum Herstellen einer Verbindung zwischen dem Medienserver der Teams in der Cloud und dem SBC lokal verwendet wird.
- **Flow 5B** – stellt einen Medienfluss zwischen dem Benutzer des Teams innerhalb des Kunden Netzwerks mit dem direkt Routing-SBC im Bypass-Modus dar.
- **Flow 5C** – stellt einen Medienfluss zwischen dem direkten Routing-SBC zu einem anderen direkten Routing-SBC in einem PSTN-kehr Modus dar.

**Interner Benutzer mit direktem Routing (Medien, die von Teams Transport Relay in Office 365 weitergeleitet werden)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Abbildung 18: interner Benutzer mit direktem Routing (Medien, die von Teams-Transport Relay in Office 365 weitergeleitet werden)*

Beachten Sie Folgendes:
 
- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Office 365 geroutet werden kann.

- Signalisieren und Medien vom SBC zu Office 365 und umgekehrt verwenden Sie Flow 4 und/oder Flow 4 ".

- Signalisieren und Medien vom Client im Kundennetzwerk zu Office 365 verwenden Flow 4.


**Remote Benutzer mit direktem Routing (Medien werden über einen Medienserver (MP) in Office 365 weitergeleitet)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Abbildung 19 – Remote Benutzer mit direktem Routing (Medien werden über einen Medienserver (MP) in Office 365 weitergeleitet)*
 
Beachten Sie Folgendes:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Office 365 geroutet werden kann.

- Signalisieren und Medien vom SBC zu Office 365 und umgekehrt verwenden Sie Flow 4 und/oder Flow 4 ".

- Signalisieren und Medien vom Client im Internet zu Office 365 verwenden Flow 3.

**Internes Benutzer-direkt Routing (medienumgehung)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Abbildung 20: Direktes Routing des internen Benutzers (medienumgehung)*
 
Beachten Sie Folgendes:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Office 365 geroutet werden kann.

- Signalisieren von SBC zu Office 365 und umgekehrt verwenden Sie Flow 4 und/oder Flow 4 ".

- Signalisierung vom Client im Kundennetzwerk zu Office 365 verwenden Sie Flow 4.

- Medien vom Client im Kundennetzwerk zu SBC innerhalb des Kunden Netzwerks verwenden Flow 5B.

**Remote Benutzer mit direktem Routing (medienumgehung, die von Teams Transport Relay in Office 365 weitergeleitet wird)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Abbildung 21: Remote Benutzer mit direktem Routing (medienumgehung, die von Teams-Transport Relay in Office 365 weitergeleitet wird)*

Beachten Sie Folgendes:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Office 365 und Internet geroutet werden kann.

- Das signalisieren vom SBC zu Office 365 und umgekehrt verwendet Flow 4 und/oder Flow 4 '.

- Das signalisieren vom Client im Internet zu Office 365 verwendet Flow 3.

- Medien vom Client im Internet an den SBC innerhalb des Kunden Netzwerks verwendet Flows 3 und 4, die von Teams Transport Relay in Office 365 weitergeleitet werden. 

**Direktes Routing für Remote Benutzer (medienumgehung direkt)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Abbildung 22 – Direktes Routing für Remote Benutzer (medienumgehung direkt)*
 
Beachten Sie Folgendes:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Office 365 und dem Internet geroutet werden kann.

- Das signalisieren vom SBC zu Office 365 und umgekehrt verwendet Flow 4 und/oder Flow 4 '.

- Das signalisieren vom Client im Internet zu Office 365 verwendet Flow 3.

- Medien vom Client im Internet zum SBC innerhalb des Kunden Netzwerks verwenden Flow 2.

**Direktes Routing (medienumgehung) – PSTN-Haarnadel-Anruf (aufgrund von Anrufweiterleitung/-Übertragung)**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Abbildung 23 – Direktes Routing (medienumgehung) – PSTN-Haarnadel-Anruf (aufgrund von Anrufweiterleitung/-Übertragung)*
 
Beachten Sie Folgendes:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Office 365 geroutet werden kann.

- Das signalisieren vom SBC zu Office 365 und umgekehrt verwendet Flow 4 und/oder Flow 4 '.

- Der Client befindet sich außerhalb der Signalisierungs-und Medien Schleife, nachdem der Anruf von PSTN zu PSTN hairpinned wurde.

- Medien aus SBC-Instanz A im Kundennetzwerk zu SBC instance B im Kundennetzwerk (wobei A und B dieselbe Instanz sein können) verwendet Flow 5c.

**Direktes Routing (Medien über Office 365) – PSTN-Haarnadel-Aufruf über zwei Mandanten**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Abbildung 24 – Direktes Routing (Medien über Office 365) – PSTN-Haarnadel-Aufruf über zwei Mandanten*
 
Beachten Sie Folgendes:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Office 365 geroutet werden kann.

- Das signalisieren vom SBC zu Office 365 und umgekehrt verwendet Flow 4 und/oder Flow 4 '.

- Der Client befindet sich außerhalb der Signalisierungs-und Medien Schleife, nachdem der Anruf von PSTN zu PSTN hairpinned wurde.

- Medien aus SBC-Instanz A innerhalb des Kunden Netzwerks X zu SBC Instanz B müssen über den Office 365-Medien Server weitergeleitet werden und können den Bypass-Modus nicht verwenden.

## <a name="teams-with-express-route-optimization"></a>Teams mit Express-Routenoptimierung

[![Microsoft Teams Online-Anruf Flüsse Abbildung 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Abbildung 25 – Teams mit Optimierung der Express Route*
 
Für den Fall, dass die Express-Route gerechtfertigt und bereitgestellt wird, können die Teams-Flows von Flow 4 zu Flow 1 und vom Flow 4 "zu Flow 1" umgeleitet werden. Die Teams-Anwendung hat jedoch eine harte Abhängigkeit von anderen Office 365-Flows über das Internet über Flows 4 und 4 '; Daher dürfen diese Ströme nicht blockiert werden. 

Beachten Sie, dass Skype for Business-Hybrid-Edge-Datenverkehr an das Internet weitergeleitet wird und nicht an eine Express Route, um mit externen Benutzern zu kommunizieren und mit anderen Mandanten zu verbünden. 

Um asymmetrische Ströme zu verhindern, muss die Umleitung in beide Richtungen erfolgen. Anders ausgedrückt: eine Adresse im Kundennetzwerk kann auf der Grundlage der Optimierung, aber nicht über beide über die Internet-oder Express Route geroutet werden.

Beispiel:

**Kundennetzwerk für externe Benutzer (Medien, die von Teams-Transport-Relay weitergeleitet werden):**

[![Microsoft Teams Online-Anruf Flüsse Abbildung 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Abbildung 26 – Kundennetzwerk für externe Benutzer (Medien, die von Teams-Transport Relay weitergeleitet werden)*
 
**Schritte auf hoher Ebene:**
1. Teams-Benutzer im Kundennetzwerk behebt URL-Domänennamen (DNS) über Cashflow2
2. Teams-Benutzer im Kundennetzwerk ordnet einen Media Relay-Port auf Teams-Transport-Relay über Flow 1 zu
3. Teams-Nutzer im Kundennetzwerk senden "einladen" mit ICE-Kandidaten über Flow 1 an Office 365
4. Office 365 sendet Benachrichtigungen an externe Teams über Flow 3
5. Teams externer Benutzer ordnet einen Media Relay-Port im Teams-Transport-Relay über Flow 3 zu
6. Teams externer Benutzer sendet "Antwort" mit ICE-Kandidaten über Flow 3, der wieder an Teams-Benutzer A über Flow 1 weitergeleitet wird.
7. Teams Benutzer a und Teams Benutzer B rufen die Ice-Verbindungstests auf und wählen Flows 1 und 3 aus, die von Teams Transport Relay in Office 365 weitergeleitet werden.
8. Benutzer von Teams senden Telemetrie an Office 365 über Flows 1 und 3

>**Hinweis**: Flow 4 muss aktiviert sein, um Abhängigkeiten der Teams-Anwendung auf anderen Mikro Diensten zu unterstützen, die Flow 4 beauftragen.
