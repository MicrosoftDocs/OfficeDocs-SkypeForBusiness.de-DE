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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Hier erfahren Teams, Office 365 Datenflüsse in verschiedenen Topologien sowie eindeutige Teamflüsse verwendet werden, die für die Peer-zu-Peer-Medienkommunikation verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f152caaa90562a5223590ebcf97623646237e40
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727844"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams-Anrufflüsse

> [!TIP]
> Schauen Sie sich diese Sitzung an, um zu erfahren, Teams Ihr Netzwerk nutzt und wie Sie optimale Netzwerkkonnektivität planen: [Teams Netzwerkplanung.](https://aka.ms/teams-networking)

## <a name="overview"></a>Übersicht

In diesem Artikel wird beschrieben Teams wie Microsoft 365 oder Office 365 in verschiedenen Topologien verwendet werden. Darüber hinaus werden eindeutige Datenflüsse Teams, die für die Peer-to-Peer-Medienkommunikation verwendet werden. In diesem Dokument werden diese Flüsse, ihr Zweck sowie ihr Ursprung und ihre Beendigung im Netzwerk beschrieben. Gehen Sie für die Zwecke dieses Artikels von Folgendes aus:

- Flow X wird vom lokalen Client verwendet, um mit dem Microsoft 365 oder Office 365 in der Cloud zu kommunizieren. Sie stammt aus dem Kundennetzwerk und endet als Endpunkt in Microsoft 365 oder Office 365.

- Flow Y wird vom lokalen Client verwendet, um mit einem Dienst im Internet zu kommunizieren, Microsoft 365 oder Office 365 eine Abhängigkeit besteht. Sie stammt aus dem Kundennetzwerk und endet als Endpunkt im Internet.

In diesem Artikel werden die folgenden Informationen behandelt:

- **Hintergrund.** Stellt Hintergrundinformationen wie Netzwerke, die sich durchlaufen können, Arten des Datenverkehrs, Konnektivitätsleitfaden vom Kundennetzwerk zu Microsoft 365- oder Office 365-Dienstendpunkten, Interoperabilität mit Drittanbieterkomponenten und Prinzipien zur Auswahl von Medienflüssen zur Verfügung, die von Teams verwendet werden.

- **Aufrufflüsse in verschiedenen Topologien**. Veranschaulicht die Verwendung von Anrufflüssen in verschiedenen Topologien. Für jede Topologie werden im Abschnitt alle unterstützten Flüsse aufgezählt und veranschaulicht, wie diese Flüsse in mehreren Verwendungsfällen verwendet werden. Für jeden Einsatzfall wird die Reihenfolge und Auswahl von Flüssen mithilfe eines Flussdiagramms beschrieben.

- **Teams ExpressRoute-Optimierung .** Beschreibt, wie diese Flüsse verwendet werden, wenn Express Route zur Optimierung bereitgestellt wird und dazu eine einfache Topologie verwendet wird.

## <a name="background"></a>Hintergrund

### <a name="network-segments"></a>Netzwerksegmente

**Kundennetzwerk.** Dies ist das Netzwerksegment, das Sie steuern und verwalten. Dies schließt alle Kundenverbindungen innerhalb von Kundenniederlassungen ein, ob verkabelt oder drahtlos, Verbindungen zwischen Bürogebäuden, Verbindungen zu lokalen Rechenzentren und Ihre Verbindungen mit Internetanbietern, Express Route oder beliebigen anderen privaten Peerings.

Normalerweise verfügt ein Kundennetzwerk über mehrere Netzwerkperimeter mit Firewalls und/oder Proxyservern, die die Sicherheitsrichtlinien Ihrer Organisation erzwingen und nur bestimmten Netzwerkdatenverkehr zulassen, den Sie eingerichtet und konfiguriert haben. Da Sie dieses Netzwerk verwalten, haben Sie direkte Kontrolle über die Leistung des Netzwerks, und wir empfehlen, Netzwerkbewertungen durchzuführen, um die Leistung sowohl innerhalb der Standorte in Ihrem Netzwerk als auch von Ihrem Netzwerk zum Microsoft 365- oder Office 365-Netzwerk zu überprüfen.

**Internet**. Dies ist das Netzwerksegment in Ihrem Gesamtnetzwerk, das von Benutzern verwendet wird, die eine Verbindung mit Microsoft 365 oder Office 365 außerhalb des Kundennetzwerks herstellen. Sie wird auch von einem Teil des Datenverkehrs aus dem Kundennetzwerk zu Microsoft 365 oder Office 365.

**Besuchtes privates Netzwerk oder privates Gastnetzwerk.** Dies ist das Netzwerksegment außerhalb Ihres Kundennetzwerks, jedoch nicht im öffentlichen Internet, das Ihre Benutzer und ihre Gäste besuchen können (z. B. ein privates Heimnetzwerk oder ein privates Unternehmensnetzwerk, das Teams nicht bereitgestellt wird, wo sich möglicherweise Ihre Benutzer und ihre Kunden befinden, die mit Teams-Diensten interagieren).

> [!NOTE]
> Die Konnektivität Microsoft 365 Oder Office 365 gilt auch für diese Netzwerke.

**Microsoft 365 oder Office 365**. Dies ist das Netzwerksegment, das Microsoft 365 oder Office 365 unterstützt. Es wird weltweit mit Kanten in der Nähe des Kundennetzwerks an den meisten Standorten verteilt. Zu den Funktionen gehören Transport Relay, Konferenzserver und Medienprozessor.

**ExpressRoute (optional)** Dies ist das Netzwerksegment, das Teil Ihres Gesamtnetzwerks ist, das Ihnen eine dedizierte private Verbindung mit dem Microsoft 365 oder Office 365 bietet.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

**Echtzeitmedien.** Daten, die in RTP (Real-Time Transport Protocol) gekapselt sind und Workloads für Audio, Video und Bildschirmfreigabe unterstützen. Im Allgemeinen ist der Medienverkehr hochgradig latenzempfindlich, daher möchten Sie, dass dieser Datenverkehr den direktesten Pfad verwendet und UDP und TCP als Transportschichtprotokoll verwendet. Dies ist aus Qualitätssicht am besten für interaktive Echtzeitmedien der beste Transport. (Beachten Sie, dass Medien als letzte Methode TCP/IP verwenden und auch innerhalb des HTTP-Protokolls ge tunnelt werden können. Dies wird aufgrund der schlechten Auswirkungen auf die Qualität jedoch nicht empfohlen.) RtP flow is secured using SRTP, in which only the payload is encrypted.

**Signalisieren .** Die Kommunikationsverknüpfung zwischen dem Client und dem Server oder anderen Clients, die zum Steuern von Aktivitäten (z. B. initiierte Anrufe) und zum Senden von Chatnachrichten verwendet werden. Für den meisten Signalisierungsverkehr werden HTTPS-basierte REST-Schnittstellen verwendet, in einigen Szenarien (z. B. bei der Verbindung zwischen Microsoft 365 oder Office 365 und einem Session Border Controller) wird jedoch das SIP-Protokoll verwendet. Es ist wichtig zu wissen, dass dieser Datenverkehr weniger anfällig für Latenz ist, aber möglicherweise zu Dienstausfällen oder Anruftimeouts führen kann, wenn die Latenz zwischen den Endpunkten mehrere Sekunden überschreitet.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Konnektivität mit Microsoft 365 oder Office 365

Teams muss [mit dem Internet verbunden sein.](/office365/enterprise/assessing-network-connectivity) Teams URLs und IP-Adressbereiche des Endpunkts sind in den [Office 365 URLs und IP-Adressbereichen aufgelistet.](/office365/enterprise/urls-and-ip-address-ranges) (Beachten Sie, dass eine offene Verbindung zu den TCP-Ports 80 und 443 sowie zu den UDP-Ports 3478 bis 3481 erforderlich ist.) Darüber hinaus Teams abhängigkeit von Skype for Business Online, das ebenfalls mit dem Internet verbunden sein muss.

Teams Konnektivität von Medienflüssen wird mithilfe standardmäßiger ICE-Verfahren (Interactive Connectivity Connectivity) implementiert.

### <a name="interoperability-restrictions"></a>Interoperabilitätseinschränkungen

**Media Relays von Drittanbietern.** Ein Teams-Medienfluss (d. h. von einem der Medienendpunkte Teams) kann nur über Teams oder Skype for Business systemeigene Medien relays durchlaufen. Interoperabilität mit Media Relay eines Drittanbieters wird nicht unterstützt. (Beachten Sie, dass ein Drittanbieter-SBC an der Grenze des PSTNs den RTP/RTCP-Stream beenden muss, der über SRTP gesichert wurde, und nicht an den nächsten Hop weitergegeben werden.)

**SIP-Proxyserver von Drittanbietern.** Ein Teams SIP-Dialogfeld mit einem Drittanbieter-SBC und/oder Gateway kann die Teams oder Skype for Business SIP-Proxys durchlaufen. Interoperabilität mit einem SIP-Proxy eines Drittanbieters wird nicht unterstützt.

**B2BUA (oder SBC) eines Drittanbieters.** Ein Teams zu und aus dem PSTN wird von einem Drittanbieter-SBC beendet. Die Interoperabilität mit einem Drittanbieter-SBC innerhalb des Teams-Netzwerks (wobei ein Drittanbieter-SBC zwei Teams- oder Skype for Business-Endpunkte vermittelt) wird jedoch nicht unterstützt.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Technologien, die in diesem Verfahren nicht Microsoft Teams

**VPN-Netzwerk.** Für Medienverkehr (oder Fluss 2' ) wird dies nicht empfohlen. Der VPN-Client sollte geteiltes Tunneln verwenden und Teams Medienverkehr wie alle externen Nicht-VPN-Benutzer routen, wie unter Aktivieren von Lync-Medien zum Umgehen eines [VPN-Tunnels angegeben.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)

> [!NOTE]
> Obwohl der Titel Lync angibt, gilt er auch für Teams Lync.

**Paket-Shaper**. Jede Art von Packet Snipper, Packet Inspection oder Packet Shaper-Geräten wird für Teams Mediendatenverkehr nicht empfohlen und kann die Qualität erheblich beeinträchtigen.

### <a name="principles"></a>Prinzipien

Es gibt vier allgemeine Prinzipien, die Sie beim Verständnis der Anrufflüsse für Microsoft Teams:

- Eine Microsoft Teams Konferenz wird von einem Microsoft 365 oder Office 365 in der region gehostet, in der auch der erste Teilnehmer beigetreten ist. (Beachten Sie, dass Ausnahmen von dieser Regel in einigen Topologien in diesem Dokument beschrieben und durch einen entsprechenden Aufruffluss veranschaulicht werden.)

- Ein Teams-Medienendpunkt in Microsoft 365 oder Office 365 wird basierend auf den Anforderungen an die Medienverarbeitung und nicht basierend auf dem Anruftyp verwendet. (Beispielsweise kann ein Punkt-zu-Punkt-Anruf einen Medienendpunkt in der Cloud verwenden, um Medien für Transkription oder Aufzeichnung zu verarbeiten, während eine Konferenz mit zwei Teilnehmern möglicherweise keinen Medienendpunkt in der Cloud verwendet.) Die meisten Konferenzen verwenden jedoch einen Medienendpunkt zum Mischen und Routing, der dem Ort zugeordnet ist, an dem die Konferenz gehostet wird. Der von einem Client an den Medienendpunkt gesendete Medienverkehr wird möglicherweise direkt geroutet oder in Microsoft 365 oder Office 365 ein Transport Relay verwendet, wenn dies aufgrund von Einschränkungen der Firewall des Kundennetzwerks erforderlich ist.

- Der Medienverkehr für Peer-to-Peer-Anrufe wird auf der direktesten verfügbaren Route verwendet, vorausgesetzt, für den Anruf wird kein Medienendpunkt in der Cloud benötigt (siehe vorheriges Prinzip). Die bevorzugte Route wird direkt an den Remote-Peer (Client) gesendet. Wenn diese Route jedoch nicht verfügbar ist, wird der Datenverkehr von einem oder mehreren Transportre relays weitergeroutet. Es wird empfohlen, dass der Medienverkehr keine Server wie Paket-Shaper, VPN-Server und so weiter transverse, da sich dies auf die Medienqualität auswirken wird.

- Der Signalisierungsverkehr geht immer an den Server, der dem Benutzer am nächsten kommt.

Weitere Informationen zu den Details des gewählten Medienpfads finden Sie unter Grundlegendes zu Medienflüssen in Microsoft Teams [– BRK4016.](https://www.youtube.com/watch?v=1tmHMIlAQdo)

## <a name="call-flows-in-various-topologies"></a>Anrufflüsse in verschiedenen Topologien

### <a name="teams-topology"></a>Teams-Topologie

Diese Topologie wird von Kunden verwendet, die Teams-Dienste aus der Cloud ohne lokale Bereitstellung nutzen, z. B. Skype for Business Server oder Telefonsystem Direct-Routing. Darüber hinaus wird die Schnittstelle zum Microsoft 365 oder Office 365 ohne Azure Express Route über das Internet ausgeführt.

[![Microsoft Teams Onlineanrufflüsse Abbildung 01.](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Abbildung 1: Teams Topologie*

Beachten Sie, dass:

- Die Richtung der Pfeile im obigen Diagramm spiegelt die Initiierungsrichtung der Kommunikation wider, die sich auf die Konnektivität in den Unternehmensperimetern auswirkt. Im Fall von UDP für Medien können die ersten Pakete in umgekehrter Richtung fließen, doch werden diese Pakete möglicherweise blockiert, bis Pakete in die andere Richtung fließen.
- Teams wird neben Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Benutzer" angezeigt.

Weitere Informationen zu den folgenden optionalen Topologien finden Sie weiter unten in diesem Artikel:

- Skype for Business lokale Bereitstellung wird in Teams **Hybridtopologie beschrieben.**
- Telefonsystem Direct Routing (für PSTN-Konnektivität) wird unter Verbindungen **Teams Direct-Routingtopologie beschrieben.**
- Express Route wird in der Teams **ExpressRoute-Optimierung beschrieben.**

**Flow Beschreibungen:**

- **Flow 2** – Stellt einen Fluss dar, der von einem Benutzer im Kundennetzwerk zum Internet als Teil der Benutzererfahrung Teams wird. Beispiele für diese Flüsse sind DNS und Peer-to-Peer-Medien.
- **Flow 2'** – Stellt einen Fluss dar, der von einem Remotebenutzer Teams mobilen Geräten mit VPN zum Kundennetzwerk initiiert wurde.
- **Flow 3** – Stellt einen Fluss dar, der von einem Remote-mobilen Benutzer Teams initiiert wurde, um Microsoft 365 oder Office 365/Teams-Endpunkte zu senden.
- **Flow 4** – Stellt einen Fluss dar, der von einem Benutzer im Kundennetzwerk initiiert wurde, um Microsoft 365 oder Office 365/Teams-Endpunkte zu erstellen.
- **Flow 5** – Stellt einen Peer-to-Peer-Medienfluss zwischen einem Teams-Benutzer und einem anderen Teams- oder Skype for Business-Benutzer innerhalb des Kundennetzwerks dar.
- **Flow 6** – Stellt einen Peer-to-Peer-Medienfluss zwischen einem Mobilen Teams-Remotebenutzer und einem anderen mobilen Remote-Teams oder Skype for Business-Benutzer über das Internet dar.

#### <a name="use-case-one-to-one"></a>Verwendungsfall: 1:1

1:1-Aufrufe verwenden ein gängiges Modell, in dem der Aufrufer eine Gruppe von Kandidaten erhält, die aus IP-Adressen/Ports bestehen, einschließlich lokaler, Relay- und Reflexiv-Kandidaten (öffentliche IP-Adresse des Clients wie vom Relay gesehen). Der Aufrufer sendet diese Kandidaten an die angerufene Partei. die aufgerufene Partei erhält ebenfalls eine ähnliche Gruppe von Kandidaten und sendet sie an den Anrufer. Meldungen der STUN-Konnektivitätsprüfung werden verwendet, um zu finden, welche Medienpfade von Anrufern/Angerufenen funktionieren, und es wird der beste Arbeitspfad ausgewählt. Medien (d. h. MIT SRTP gesicherte RTP/RTCP-Pakete) werden dann mit dem ausgewählten Kandidatenpaar gesendet. Das Transport-Relay wird als Teil Microsoft 365 Transport-Relays Office 365.

Wenn die lokalen IP-Adressen/Port-Kandidaten oder die Reflexiven Konnektivität haben, wird der direkte Pfad zwischen den Clients (oder die Verwendung eines NAT) für Medien ausgewählt. Wenn sich beide Clients im Kundennetzwerk befinden, sollte der direkte Pfad ausgewählt werden. Dies erfordert direkte UDP-Konnektivität innerhalb des Kundennetzwerks. Wenn es sich bei den Clients um benutzerische Cloudbenutzer handelt, verwenden Medien je nach NAT/Firewall möglicherweise direkte Konnektivität.

Wenn es sich um einen internen Client im Kundennetzwerk und einen externen Client (z. B. einen Benutzer in der mobilen Cloud) handelt, ist es unwahrscheinlich, dass die direkte Verbindung zwischen den lokalen Kandidaten oder Reflexiven Kandidaten funktioniert. In diesem Fall besteht eine Option in der Verwendung eines der Transport Relay-Kandidaten eines der Clients (z. B. hat der interne Client ein Relay-Kandidat aus dem Transport relay in Microsoft 365 oder Office 365 erhalten; der externe Client muss STUN-/RTP-/RTCP-Pakete an das Transport relay senden können). Eine weitere Option ist, dass der interne Client an den Relay-Kandidaten sendet, der vom Client für die mobile Cloud erworben wurde. Beachten Sie, dass UDP-Konnektivität für Medien zwar dringend empfohlen wird, TCP jedoch unterstützt wird.

**Schritte auf hoher Ebene:**

1. Teams Benutzer A löst DEN URL-Domänennamen (DNS) mithilfe von Flow 2 auf.
1. Teams Benutzer A ordnet einen Media Relay-Port auf Teams Transport Relay mithilfe von Flow 4 zu.
1. Teams Benutzer A sendet "Einladung" mit ICE-Kandidaten mit Flow 4 an Microsoft 365 oder Office 365.
1. Microsoft 365 oder Office 365 Benachrichtigung mithilfe von Flow 4 Teams An Benutzer B gesendet.
1. Teams Benutzer B weist über Flow 4 einen Media Relay-Port Teams Transport Relay zu.
1. Teams Benutzer B sendet "Antwort" mit ICE-Kandidaten mithilfe von Flow 4, der mithilfe von Flow 4 zurück an Teams Benutzer A weitergeleitet wird.
1. Teams Benutzer A und Teams Benutzer B rufen ICE-Verbindungstests auf, und der beste verfügbare Medienpfad ist ausgewählt (verschiedene Verwendungsfälle finden Sie unten in den Diagrammen).
1. Teams Benutzer senden Telemetrie Microsoft 365 Oder Office 365 Mithilfe von Flow 4 an andere Benutzer.

**Innerhalb des Kundennetzwerks:**

[![Microsoft Teams Onlineanrufflüsse Abbildung 02.](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Abbildung 2: Innerhalb eines Kundennetzwerks*

In Schritt 7 ist Peer-zu-Peer-Medienfluss 5 ausgewählt.

Die Medien sind bidirektional. Die Richtung von Fluss 5 gibt an, dass eine Seite die Kommunikation aus Konnektivitätsperspektive initiiert, die mit allen Flüssen in diesem Dokument konsistent ist. In diesem Fall spielt es keine Rolle, welche Richtung verwendet wird, da sich beide Endpunkte innerhalb des Kundennetzwerks befinden.

**Kundennetzwerk zu externem Benutzer (Medien, die von einem Transport relay Teams werden):**

[![Microsoft Teams Onlineanrufflüsse Abbildung 03.](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Abbildung 3: Kundennetzwerk zu externem Benutzer (Medien, die über Teams Transport Relay weitergemittelt werden)*

In Schritt 7 sind Flow 4, vom Kundennetzwerk zu Microsoft 365 oder Office 365 und Flow 3, vom Mobilen Remote-Teams-Benutzer zum Microsoft 365 oder Office 365 ausgewählt. Diese Datenströme werden von Teams Transport Relay innerhalb Microsoft 365 Oder Office 365.

Die Medien sind bidirektional, wobei die Richtung angibt, welche Seite die Kommunikation aus Konnektivitätsperspektive initiiert. In diesem Fall werden diese Flüsse für Signalisierung und Medien unter Verwendung verschiedener Transportprotokolle und Adressen verwendet.

**Kundennetzwerk für externen Benutzer (direkte Medien):**

[![Microsoft Teams Onlineanrufflüsse Abbildung 04.](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Abbildung 4: Kundennetzwerk für externen Benutzer (Direkte Medien)*

In Schritt 7 ist Flow 2 vom Kundennetzwerk zum Internet (Peer des Clients) ausgewählt.

- Direct-Medien mit remote mobilen Benutzern (nicht per Relay Microsoft 365 Oder Office 365) sind optional. Mit anderen Worten: Der Kunde kann diesen Pfad blockieren, um einen Medienpfad über Transport Relay in Microsoft 365 oder Office 365.

- Die Medien sind bidirektional. Die Richtung von Fluss 2 zu mobilen Remotebenutzern gibt an, dass eine Seite die Kommunikation aus Konnektivitätsperspektive initiiert.

**VPN-Benutzer für internen Benutzer (Medien, die über Teams Transport Relay gesendet werden)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 05.](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Abbildung 5: VPN-Benutzer für internen Benutzer (Medien, die über Teams Transport Relay weitergemittelt werden)*

Für die Signalisierung zwischen VPN und dem Kundennetzwerk wird Flow 2 verwendet. Für die Signalisierung zwischen dem Kundennetzwerk und Microsoft 365 oder Office 365 wird Flow 4 verwendet. Medien umgeht jedoch das VPN und wird über die Flüsse 3 und 4 über Teams Media Relay in Microsoft 365 oder Office 365.

**VPN-Benutzer für internen Benutzer (direkte Medien)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 06.](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Abbildung 6: VPN-Benutzer für internen Benutzer (Direkte Medien)*

Für die Signalisierung zwischen VPN und dem Kundennetzwerk wird Flow 2 verwendet. Für die Signalisierung zwischen dem Kundennetzwerk und Microsoft 365 oder Office 365 wird Flow 4 verwendet. Medien umgeht jedoch das VPN und wird mithilfe von Flow 2 vom Kundennetzwerk zum Internet geroutet.

Die Medien sind bidirektional. Die Richtung von Durchlauf 2 zum Mobilen Remotebenutzer gibt an, dass eine Seite die Kommunikation aus Konnektivitätsperspektive initiiert.

**VPN-Benutzer für externen Benutzer (direkte Medien)**

[![Microsoft Teams Anrufflüsse Abbildung 07.](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Abbildung 7: VPN-Benutzer für externen Benutzer (Direkte Medien)*

Bei der Signalisierung zwischen dem VPN-Benutzer und dem Kundennetzwerk wird Flow 2' und Flow 4 verwendet, Microsoft 365 oder Office 365. Medien umgeht jedoch VPN und wird mithilfe von Flow 6 geroutet.

Die Medien sind bidirektional. Die Richtung von Fluss 6 an den Remotebenutzer des mobilen Standorts gibt an, dass eine Seite die Kommunikation aus Konnektivitätsperspektive initiiert.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>Use Case: Teams über Microsoft 365 oder Office 365 PSTN

Microsoft 365 und Office 365 verfügen über ein Telefonsystem, das das Platzieren und Empfangen von Anrufen aus dem öffentlichen Telefonnetz (PSTN) ermöglicht. Wenn der PSTN-Trunk über den Telefonsystem-Anrufplan verbunden ist, gibt es für diesen Einsatzfall keine besonderen Konnektivitätsanforderungen. (Wenn Sie Ihren eigenen lokalen PSTN-Trunk mit Microsoft 365 oder Office 365 verbinden möchten, können Sie Telefonsystem Direct-Routing verwenden.)

[![Microsoft Teams Onlineanrufflüsse Abbildung 08.](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Abbildung 8: Teams des PSTN über Office 365 Trunk*

#### <a name="use-case-teams-meeting"></a>Verwendungsfall: Teams Besprechung

Der Audio-/Video-/Bildschirmfreigabeserver (VBSS) ist Bestandteil von Microsoft 365 und Office 365. Sie hat eine öffentliche IP-Adresse, die vom Kundennetzwerk aus erreichbar sein muss und über einen Kundenclient für die Cloud erreichbar sein muss. Jeder Client/Endpunkt muss in der Lage sein, eine Verbindung mit dem Konferenzserver herzustellen.

Interne Clients erhalten lokale, Reflexive und Relay-Kandidaten auf die gleiche Weise wie bei 1:1-Anrufen beschrieben. Die Clients senden diese Kandidaten in einer Einladung an den Konferenzserver. Da der Konferenzserver kein Relay verwendet, da er über eine öffentlich erreichbare IP-Adresse verfügt, reagiert er mit seinem lokalen IP-Adresskandidaten. Der Client und der Konferenzserver überprüfen die Konnektivität auf die gleiche Weise, die für 1:1-Anrufe beschrieben wird.

Beachten Sie, dass:

- Teams Kunden können nicht an Skype for Business Besprechungen teilnehmen, und Skype for Business Kunden können nicht an Teams teilnehmen.

- Je nach Bereitstellung von PSTN-Anruf und/oder Konferenzbereitstellung des Organisators kann ein PSTN-Benutzer optional "EINwählen" oder "AUSGEwählt" werden.

- Ein Gastbenutzer oder ein Kundenbenutzer kann über ein privates Gastnetzwerk beitreten, das durch FW/NAT durch strenge Regeln geschützt ist.

[![Microsoft Teams Onlineanrufflüsse Abbildung 09.](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Abbildung 9: Teams Besprechung*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Verwendungsfall: Verbund mit Skype for Business lokal

**Media relayed by Teams Transport Relay in Microsoft 365 or Office 365**

[![Microsoft Teams Onlineanrufflüsse Abbildung 10.](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Abbildung 10: Medien, die von einem transport relay Teams in Office 365*

Beachten Sie, dass:

- Der Verbund ist per Definition eine Kommunikation zwischen zwei Mandanten. In diesem Fall ist Mandant A, der Teams verwendet, Partner mit Mandant B, der die Skype for Business verwendet. Wenn man auch Mandant B Microsoft 365 oder Office 365 verwendet, hätte der Skype for Business-Client Flow 3 verwendet, um die Verbindung zu Microsoft 365 oder Office 365.

- Signalisierung und Medien vom Skype for Business-Client zu lokalen Skype for Business Server werden in diesem Dokument nicht angezeigt. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Die Signalisierung zwischen Teams und Skype for Business wird von einem Gateway überbrücken.

- Medien werden in diesem Fall über Teams Transport Relay an das Kundennetzwerk und den Remote-Skype for Business mithilfe von Flow 4 gesendet.

**Media relayed by Skype for Business Media Relay in federated tenant**

[![Microsoft Teams Onlineanrufflüsse Abbildung 11.](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Abbildung 11: Medien, die von einem Skype for Business Media Relay im Partner mandant weitergestrahlt werden*

Beachten Sie, dass:

- Signalisierung und Medien vom Skype for Business-Client zu einem lokalen Skype for Business Server sind nicht Teil dieses Dokuments. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Die Signalisierung zwischen Teams und Skype for Business wird von einem Gateway überbrücken.

- Medien werden in diesem Fall mithilfe von Flow 2 Skype for Business Media Relay an das Kundennetzwerk weiterge leitet. (Beachten Sie, dass der Datenverkehr vom Teams-Benutzer zum Remote-Media Relay im Partnernetzwerk zunächst vom Media Relay blockiert wird, bis der Datenverkehr in umgekehrter Richtung beginnt. Durch den bidirektionalen Fluss wird die Verbindung jedoch in beide Richtungen geöffnet.)

**Direkt (Peer-zu-Peer)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 12.](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Abbildung 12: Direkt (Peer-zu-Peer)*

### <a name="teams-hybrid-topology"></a>Teams Hybridtopologie

Diese Topologie umfasst Teams mit einer Skype for Business lokalen Bereitstellung.

[![Microsoft Teams Onlineanrufflüsse Abbildung 13.](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Abbildung 13: Teams Hybridtopologie*

- Die Richtung der Pfeile im obigen Diagramm spiegelt die Initiierungsrichtung der Kommunikation wider, die sich auf die Konnektivität in den Unternehmensperimetern auswirkt. Im Fall von UDP für Medien können die ersten Pakete in umgekehrter Richtung fließen, doch werden diese Pakete möglicherweise blockiert, bis Pakete in die andere Richtung fließen.

- Teams wird neben Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Benutzer" angezeigt.

Zusätzlicher Fluss (zusätzlich zur Teams Topologie):

- **Flow 5A** – Stellt einen Peer-to-Peer-Medienfluss zwischen einem Teams-Benutzer innerhalb des Kundennetzwerks und einem lokalen Skype for Business-Media Relay am Netzwerkrand des Kunden dar.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Use case: Teams to Skype for Business 1:1

**Hybrid im Kundennetzwerk**

[![Microsoft Teams Onlineanrufflüsse Abbildung 14.](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Abbildung 14: Hybrid innerhalb des Kundennetzwerks*

Die Signalisierung zwischen Teams und Skype for Business wird von einem Gateway überbrücken. Medien werden jedoch mithilfe von Flow 5 direkt von Peer-zu-Peer innerhalb des Kundennetzwerks geroutet.

**Hybrid-Kundennetzwerk mit externem Skype for Business – Weiterleitung per Microsoft 365 oder Office 365**

[![Microsoft Teams Onlineanrufflüsse Abbildung 15.](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Abbildung 15: Hybrides Kundennetzwerk mit externem Skype for Business über Office 365*

Beachten Sie, dass:

- Signalisierung und Medien vom Skype for Business-Client zu einem lokalen Skype for Business Server werden in diesem Dokument nicht angezeigt. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Die Signalisierung zwischen Teams und Skype for Business wird von einem Gateway überbrücken.

- Die Medien werden über Teams Transport Relay zum Kundennetzwerk über Flow 4 weiterviert.

**Hybrid-Kundennetzwerk mit externem Skype for Business – Weiterleitung über lokales Edge**

[![Microsoft Teams Onlineanrufflüsse Abbildung 16.](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Abbildung 16: Hybrid-Kundennetzwerk mit externem Skype for Business - Weiterleitung durch lokales Edge*

Beachten Sie, dass:

- Signalisierung und Medien vom Skype for Business-Client zu einem lokalen Skype for Business Server werden, werden in diesem Dokument nicht angezeigt. Aus Gründen der Übersichtlichkeit wird dies jedoch veranschaulicht.

- Die Signalisierung wird von einem Gateway überbrücken.

- Medien werden über Skype for Business Media Relay innerhalb Skype for Business lokalen Edge an den Teams mithilfe von Medienfluss 5A im Kundennetzwerk weitergeseniert.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams mit Telefonsystem Direct-Routingtopologie

Diese Topologie umfasst Teams mit Telefonsystem Direct-Routing.

Mit Direct Routing können Sie einen PstN-Dienstanbieter (Public Switched Telephone Network) eines Drittanbieters verwenden, indem Sie ein unterstütztes lokales, vom Kunden bereitgestelltes Hardwaregerät für Den Session Border Controller (SBC) mit Microsoft 365 oder Office 365 koppeln und dann den Telefoniestamm mit diesem Gerät verbinden.

Um dieses Szenario zu unterstützen, muss der Kunde von einem zertifizierten Microsoft-Partner einen zertifizierten SBC für Direct-Routing bereitstellen. Der SBC muss wie vom Anbieter empfohlen konfiguriert werden und für direkten UDP-Microsoft 365 oder Office 365 Routing routingfähig sein. Die Medien können direkt vom Teams- und/oder Skype for Business-Client zum SBC (unter Umgehung des Teams-Gateways) oder über das Teams-Gateway fließen. Die Konnektivität mit dem SBC basiert, wenn der Trunk so konfiguriert ist, dass er das Teams-Gateway umgehen kann, auf ICE, wo SBC ICE-Lite unterstützt, während der Teams/Skype for Business-Medienendpunkt ICE-Vollbild unterstützt.

[![Microsoft Teams Onlineanrufflüsse Abbildung 17.](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Abbildung 17: Teams mit Telefonsystem Direct-Routingtopologie

Beachten Sie, dass:

- Die Richtung der Pfeile im obigen Diagramm spiegelt die Initiierungsrichtung der Kommunikation wider, die sich auf die Konnektivität in den Unternehmensperimetern auswirkt. Im Fall von UDP für Medien können die ersten Pakete in umgekehrter Richtung fließen, doch werden diese Pakete möglicherweise blockiert, bis Pakete in die andere Richtung fließen.

- Teams wird neben Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Benutzer" angezeigt.

Zusätzliche Datenflüsse (zusätzlich zur Teams Onlinetopologie):

- **Flow 4'** – Stellt einen Fluss von Microsoft 365 oder Office 365 zum Kundennetzwerk dar, der verwendet wird, um eine Verbindung zwischen dem Teams-Medienserver in der Cloud und dem lokalen SBC herzustellen.
- **Flow 5B** – Stellt einen Medienfluss zwischen dem Teams-Benutzer innerhalb des Kundennetzwerks mit Dem Direct-Routing-SBC im Umgehungsmodus dar.
- **Flow 5C** – Stellt einen Medienfluss zwischen dem Direct-Routing-SBC und einem anderen Direct Routing-SBC im Umgehungsmodus des PSTN-Hairpin-Anrufs dar.

**Interner Benutzer mit Direct-Routing (Medien, die über Teams Transport Relay weiterleitet werden)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 18.](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Abbildung 18: Interner Benutzer mit Direct-Routing (Medien, die über Teams Transport Relay weitergeleitet werden)*

Beachten Sie, dass:

- Der SBC muss eine öffentliche IP-Adresse haben, die von einer Microsoft 365 oder einer Office 365.

- Für Signalisierung und Medien vom SBC zu Microsoft 365 oder Office 365 und umgekehrt wird Flow 4 und/oder Flow 4' verwendet.

- Signalisierung und Medien vom Client innerhalb des Kundennetzwerks, um Microsoft 365 oder Office 365 Flow 4 zu verwenden.

**Remotebenutzer mit Direct-Routing (Medien werden über einen Medienserver (MP) geroutet)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 19.](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Abbildung 19: Remotebenutzer mit Direct-Routing (Medien werden über einen Medienserver (MP) geroutet)*

Beachten Sie, dass:

- Der SBC muss eine öffentliche IP-Adresse haben, die von einer Microsoft 365 oder einer Office 365.

- Für Signalisierung und Medien vom SBC zu Microsoft 365 oder Office 365 und umgekehrt wird Flow 4 und/oder Flow 4' verwendet.

- Signalisierung und Medien vom Client im Internet, um Microsoft 365 oder Office 365 Flow 3 zu verwenden.

**Direktes Routing für interne Benutzer (Medienumgehung)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 20.](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Abbildung 20: Direktes Routing für internen Benutzer (Medienumgehung)*

Beachten Sie, dass:

- Der SBC muss eine öffentliche IP-Adresse haben, die von einer Microsoft 365 oder einer Office 365.

- Bei der Signalisierung von SBC Microsoft 365 oder Office 365 und umgekehrt wird Flow 4 und/oder Flow 4' verwendet.

- Signalisieren vom Client innerhalb des Kundennetzwerks Microsoft 365 oder Office 365 Verwendung von Flow 4.

- Medien vom Client innerhalb des Kundennetzwerks zu SBC innerhalb des Kundennetzwerks verwenden Flow 5B.

**Remotebenutzer mit Direct-Routing (Medienumgehung über Teams Transport Relay)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 21.](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Abbildung 21: Remotebenutzer mit Direct-Routing (Medienumgehung, die über Teams Transport Relay weitergeleitet wird)*

Beachten Sie, dass:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von einer Microsoft 365 über Office 365 und das Internet routingfähig ist.

- Für die Signalisierung von SBC zu Microsoft 365 oder Office 365 und umgekehrt wird Fluss 4 und/oder Fluss 4 verwendet.

- Bei der Signalisierung vom Client im Internet an Microsoft 365 oder Office 365 wird Flow 3 verwendet.

- Medien vom Client im Internet zum SBC innerhalb des Kundennetzwerks verwenden die Flüsse 3 und 4, die von Teams Transport Relay übertragen werden.

**Direct-Routing für Remotebenutzer (Medienumgehung direkt)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 22.](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Abbildung 22: Direct-Routing für Remotebenutzer (Medienumgehung direkt)*

Beachten Sie, dass:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die aus Microsoft 365 oder Office 365 internet routingfähig ist.

- Bei der Signalisierung vom SBC zu Microsoft 365 oder Office 365 und umgekehrt wird Fluss 4 und/oder Fluss 4 verwendet.

- Bei der Signalisierung vom Client im Internet an Microsoft 365 oder Office 365 wird Flow 3 verwendet.

- Für Medien vom Client im Internet zu SBC innerhalb des Kundennetzwerks wird Flow 2 verwendet.

**Direct Routing (Medienumgehung) – PstN-Hairpin-Anruf (aufgrund von Anruf weiterleiten/übertragen)**

[![Microsoft Teams Onlineanrufflüsse Abbildung 23.](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Abbildung 23: Direct Routing (Medienumgehung) – PstN-Hairpin-Anruf (aufgrund von Anruf weiterleiten/übertragen)*

Beachten Sie, dass:

- Der SBC muss eine öffentliche IP-Adresse haben, die von einer Microsoft 365 oder Office 365.

- Bei der Signalisierung vom SBC zu Microsoft 365 oder Office 365 und umgekehrt wird Fluss 4 und/oder Fluss 4 verwendet.

- Der Client befindet sich nicht mehr in der Signalisierungs- und Medienschleife, nachdem der Anruf von der PSTN-an die PSTN-Schleife gestiftet wurde.

- Für Medien von SBC-Instanz A innerhalb des Kundennetzwerks zu SBC-Instanz B innerhalb des Kundennetzwerks (wobei A und B dieselbe Instanz sein können) wird Flow 5C verwendet.

**Direct Routing (Media through Microsoft 365 or Office 365) – PSTN Hairpin Call across two Tenants**

[![Microsoft Teams Onlineanrufflüsse Abbildung 24.](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Abbildung 24: Direktes Routing (Medien über Microsoft 365 oder Office 365) – Anrufe über das Festnetz-Hairpin über zwei Mandanten*

Beachten Sie, dass:

- Der SBC muss eine öffentliche IP-Adresse haben, die von einer Microsoft 365 oder Office 365.

- Bei der Signalisierung vom SBC zu Microsoft 365 oder Office 365 und umgekehrt wird Fluss 4 und/oder Fluss 4 verwendet.

- Der Client befindet sich nicht mehr in der Signalisierungs- und Medienschleife, nachdem der Anruf von der PSTN-an die PSTN-Schleife gestiftet wurde.

- Medien von SBC-Instanz A innerhalb des Kundennetzwerks X zu SBC-Instanz B müssen über den Microsoft 365 oder Office 365 Media Server übertragen werden und können nicht den Umgehungsmodus verwenden.

## <a name="teams-with-express-route-optimization"></a>Teams ExpressRoute-Optimierung

[![Microsoft Teams Onlineanrufflüsse Abbildung 25.](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Abbildung 25: Teams ExpressRoute-Optimierung*

Wenn Express Route im Rechtfertigungs- und Bereitstellungsfall ist, können Teams-Datenströme von Fluss 4 auf Fluss 1 und von Fluss 4' auf Fluss 1' umgeroutet werden. Die Teams-Anwendung ist jedoch aufgrund der Flüsse 4 und 4 Microsoft 365 oder Datenfluss über Office 365 stark von anderen Datenströmen abhängig. daher dürfen diese Flüsse nicht blockiert werden.

Beachten Sie Skype for Business der Hybrid-Edgedatenverkehr an das Internet und nicht an ExpressRoute für die Kommunikation mit externen Benutzern und die Kommunikation mit anderen Mandanten geroutet wird.

Um asymmetrische Flüsse zu vermeiden, muss das Erneute Routing in beide Richtungen gehen. Mit anderen Worten: Eine Adresse innerhalb des Kundennetzwerks kann basierend auf der Optimierung entweder über das Internet oder über ExpressRoute routingfähig sein, jedoch nicht über beides.


**Kundennetzwerk zu externem Benutzer (Medien, die von einem Transport relay Teams werden):**

[![Microsoft Teams Onlineanrufflüsse Abbildung 26.](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Abbildung 26: Kundennetzwerk zu externem Benutzer (Medien, die über Teams Transport Relay weitergemittelt werden)*

**Schritte auf hoher Ebene:**

1. Teams Der Benutzer innerhalb des Kundennetzwerks löst den URL-Domänennamen (DNS) mithilfe von Flow2 auf.
1. Teams Benutzer innerhalb eines Kundennetzwerks weisen einen Media Relay-Port auf Teams Transport Relay mithilfe von Flow 1 zu.
1. Teams Ein Benutzer innerhalb eines Kundennetzwerks sendet "Einladung" mit ICE-Kandidaten, die Flow 1 verwenden, Microsoft 365 oder Office 365.
1. Microsoft 365 oder Office 365 Benachrichtigung an externe Benutzer Teams, die Flow 3 verwenden.
1. Teams externe Benutzer weisen über Flow 3 einen Media Relay-Port Teams Transport Relay zu.
1. Teams externe Benutzer sendet "Antwort" mit ICE-Kandidaten mithilfe von Flow 3, der mithilfe von 1 an Teams A zurück Flow wird.
1. Teams Benutzer A und Teams Benutzer B rufen ICE-Verbindungstests auf und wählen die Flüsse 1 und 3 aus, die von einem Transport relay Teams werden.
1. Teams Benutzer senden Telemetrie Microsoft 365 Daten Office 365 Datenströme 1 und 3.

> [!NOTE]
> Flow 4 muss aktiviert sein, um Abhängigkeiten von Teams von anderen Mikrodiensten zu unterstützen, für die Flow 4 vorgeschrieben ist.
