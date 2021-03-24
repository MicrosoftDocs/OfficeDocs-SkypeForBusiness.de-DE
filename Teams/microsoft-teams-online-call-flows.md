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
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Erfahren Sie, wie Teams Office 365-Flüsse in verschiedenen Topologien sowie eindeutige Teamflüsse verwendet, die für die Peer-zu-Peer-Medienkommunikation verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a720838958fa249674f6216cbc24ade5134127bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098481"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams-Anrufflüsse

> [!TIP]
> Schauen Sie sich diese Sitzung an, um zu erfahren, wie Teams Ihr Netzwerk nutzt und wie Sie optimale Netzwerkkonnektivität planen: [Teams Network Planning](https://aka.ms/teams-networking).

## <a name="overview"></a>Übersicht

In diesem Artikel wird beschrieben, wie Microsoft 365- oder Office 365-Anrufflüsse in verschiedenen Topologien verwendet werden. Darüber hinaus werden eindeutige Teams-Flüsse beschrieben, die für die Peer-to-Peer-Medienkommunikation verwendet werden. Im Dokument werden diese Flüsse, deren Zweck sowie derEn Ursprung und Beendigung im Netzwerk beschrieben. Gehen Sie für die Zwecke dieses Artikels wie folgt vor:

- Flow X wird vom lokalen Client verwendet, um mit dem Microsoft 365- oder Office 365-Dienst in der Cloud zu kommunizieren. Sie stammt aus dem Kundennetzwerk und endet als Endpunkt in Microsoft 365 oder Office 365.

- Flow Y wird vom lokalen Client verwendet, um mit einem Dienst im Internet zu kommunizieren, von dem Microsoft 365 oder Office 365 abhängig ist. Sie stammt aus dem Kundennetzwerk und wird als Endpunkt im Internet beendet.

In diesem Artikel werden die folgenden Informationen behandelt:

- **Hintergrund**. Enthält Hintergrundinformationen, z. B. Netzwerke, die die Flüsse durchlaufen können, Arten von Datenverkehr, Konnektivitätsleitfäden vom Kundennetzwerk zu Microsoft 365- oder Office 365-Dienstendpunkten, Interoperabilität mit Komponenten von Drittanbietern und Prinzipien, die von Teams zum Auswählen von Medienflüssen verwendet werden.

- **Aufrufflüsse in verschiedenen Topologien**. Veranschaulicht die Verwendung von Anrufflüssen in verschiedenen Topologien. Für jede Topologie werden im Abschnitt alle unterstützten Flüsse aufgezählt und veranschaulicht, wie diese Flüsse in mehreren Verwendungsfällen verwendet werden. Für jeden Einsatzfall werden die Reihenfolge und Auswahl von Flüssen mithilfe eines Flussdiagramms beschrieben.

- **Teams mit Expressroutenoptimierung**. Beschreibt, wie diese Flüsse verwendet werden, wenn Express Route zur Optimierung bereitgestellt wird, dargestellt anhand einer einfachen Topologie.

## <a name="background"></a>Hintergrund

### <a name="network-segments"></a>Netzwerksegmente

**Kundennetzwerk**. Dies ist das Netzwerksegment, das Sie steuern und verwalten. Dies umfasst alle Kundenverbindungen innerhalb von Kundenbüros, ob drahtgebunden oder drahtlos, Verbindungen zwischen Bürogebäuden, Verbindungen zu lokalen Rechenzentren und Ihre Verbindungen zu Internetanbietern, Express Route oder anderen privaten Peerings.

Normalerweise verfügt ein Kundennetzwerk über mehrere Netzwerkperimeter mit Firewalls und/oder Proxyservern, die die Sicherheitsrichtlinien Ihrer Organisation erzwingen und nur bestimmten Netzwerkdatenverkehr zulassen, den Sie eingerichtet und konfiguriert haben. Da Sie dieses Netzwerk verwalten, haben Sie die direkte Kontrolle über die Leistung des Netzwerks, und es wird empfohlen, Netzwerkbewertungen durchzuführen, um die Leistung sowohl innerhalb von Websites in Ihrem Netzwerk als auch von Ihrem Netzwerk bis zum Microsoft 365- oder Office 365-Netzwerk zu überprüfen.

**Internet**. Dies ist das Netzwerksegment, das Teil Ihres Gesamtnetzwerks ist und von Benutzern verwendet wird, die eine Verbindung mit Microsoft 365 oder Office 365 außerhalb des Kundennetzwerks herstellen. Sie wird auch von einigen Datenverkehrsverbindungen aus dem Kundennetzwerk zu Microsoft 365 oder Office 365 verwendet.

**Privates Netzwerk besucht oder gastiert.** Dies ist das Netzwerksegment außerhalb Ihres Kundennetzwerks, aber nicht im öffentlichen Internet, das Ihre Benutzer und ihre Gäste besuchen können (z. B. ein privates Heimnetzwerk oder ein privates Unternehmensnetzwerk, in dem Teams nicht bereitgestellt wird, in dem sich Ihre Benutzer und ihre Kunden befinden, die mit Teams-Diensten interagieren).

> [!NOTE]
> Die Konnektivität mit Microsoft 365 oder Office 365 gilt auch für diese Netzwerke.

**Microsoft 365 oder Office 365**. Dies ist das Netzwerksegment, das Microsoft 365- oder Office 365-Dienste unterstützt. Es wird weltweit mit Kanten in der Nähe des Kundennetzwerks an den meisten Standorten verteilt. Zu den Funktionen gehören Transport Relay, Konferenzserver und Medienprozessor.

**Expressroute (optional)**. Dies ist das Netzwerksegment, das Teil Ihres Gesamtnetzwerks ist und Ihnen eine dedizierte, private Verbindung mit dem Microsoft 365- oder Office 365-Netzwerk bietet.

### <a name="types-of-traffic"></a>Arten von Datenverkehr

**Medien in Echtzeit**. Daten, die im RtP (Real-time Transport Protocol) gekapselt sind und Arbeitsauslastungen für Audio, Video und Bildschirmfreigabe unterstützen. Im Allgemeinen ist der Mediendatenverkehr hochlatenzempfindlich, daher möchten Sie, dass dieser Datenverkehr den möglichst direkten Pfad einschlagen und UDP und TCP als Transportschichtprotokoll verwendet, das aus Qualitätssicht der beste Transport für interaktive Echtzeitmedien ist. (Beachten Sie, dass Medien als letztes Mittel TCP/IP verwenden und auch innerhalb des HTTP-Protokolls ge tunnelt werden können, es aufgrund von Auswirkungen auf die Qualität jedoch nicht empfohlen wird.) Der RTP-Fluss wird mithilfe von SRTP gesichert, bei dem nur die Nutzlast verschlüsselt wird.

**Signalisierung**. Die Kommunikationsverbindung zwischen Client und Server oder anderen Clients, die zum Steuern von Aktivitäten (z. B. zum Starten eines Anrufs) und zum Senden von Chatnachrichten verwendet werden. Für den meisten Signalisierungsverkehr werden die HTTPS-basierten REST-Schnittstellen verwendet, in einigen Szenarien (z. B. verbindung zwischen Microsoft 365 oder Office 365 und einem Session Border Controller) wird jedoch das SIP-Protokoll verwendet. Es ist wichtig zu wissen, dass dieser Datenverkehr wesentlich weniger auf Latenz reagiert, aber dienstausfälle oder Anruftimeouts verursachen kann, wenn die Latenz zwischen den Endpunkten mehrere Sekunden überschreitet.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Konnektivität mit Microsoft 365 oder Office 365

Teams erfordert [eine Verbindung mit dem Internet.](/office365/enterprise/assessing-network-connectivity) Endgeräte-URLs und IP-Adressbereiche von Teams werden in [Office 365-URLs und -IP-Adressbereichen aufgelistet.](/office365/enterprise/urls-and-ip-address-ranges) (Beachten Sie, dass eine offene Verbindung mit den TCP-Ports 80 und 443 und den UDP-Ports 3478 bis 3481 erforderlich ist.) Darüber hinaus ist Teams von Skype for Business Online abhängig, das ebenfalls mit dem Internet verbunden sein muss.

Die Konnektivität von Teams-Medienflüssen wird mithilfe von IETF Interactive Connectivity Establishment (ICE)-Standardverfahren implementiert.

### <a name="interoperability-restrictions"></a>Interoperabilitätseinschränkungen

**Medienrelais von Drittanbietern**. Ein Medienfluss von Teams (d. h., einer der Medienendpunkte ist Teams) kann nur teams- oder skype for Business-native Medienrelais durchlaufen. Die Interoperabilität mit einem Medienrelais eines Drittanbieters wird nicht unterstützt. (Beachten Sie, dass ein Drittanbieter-SBC an der Grenze zu PSTN den RTP/RTCP-Stream beenden muss, der mit SRTP gesichert ist, und ihn nicht an den nächsten Hop weiterverteilen muss.)

**SIP-Proxyserver von Drittanbietern**. Ein Sip-Signaldialogfeld von Teams mit einem Drittanbieter-SBC und/oder Gateway kann teams- oder skype for Business-native SIP-Proxys durchlaufen. Die Interoperabilität mit einem SIP-Proxy eines Drittanbieters wird nicht unterstützt.

**B2BUA (oder SBC) von Drittanbietern**. Ein Teams-Medienfluss zum und aus dem PSTN wird von einem Drittanbieter-SBC beendet. Die Interoperabilität mit einem Drittanbieter-SBC innerhalb des Teams-Netzwerks (in dem ein Drittanbieter-SBC zwei Teams- oder Skype for Business-Endpunkte vermittelt) wird jedoch nicht unterstützt.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Technologien, die mit Microsoft Teams nicht empfohlen werden

**VPN-Netzwerk .** Es wird nicht für den Medienverkehr (oder Flow 2') empfohlen. Der VPN-Client sollte geteiltes VPN verwenden und Mediendatenverkehr wie alle externen Nicht-VPN-Benutzer weiterverteilen, wie unter Aktivieren von Lync-Medien zum Umgehen eines [VPN-Tunnels angegeben.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)

> [!NOTE]
> Obwohl der Titel Lync angibt, gilt er auch für Teams.

**Paketformer**. Jede Art von Paketschnippern, Paketinspektion oder Paketformergeräten wird nicht empfohlen und kann die Qualität erheblich beeinträchtigen.

### <a name="principles"></a>Prinzipien

Es gibt vier allgemeine Prinzipien, die Ihnen helfen, Anrufflüsse für Microsoft Teams zu verstehen:

- Eine Microsoft Teams-Konferenz wird von Microsoft 365 oder Office 365 in der Region gehostet, in der der erste Teilnehmer beigetreten ist. (Beachten Sie, dass ausnahmen von dieser Regel in einigen Topologien in diesem Dokument beschrieben und durch einen geeigneten Aufruffluss veranschaulicht werden.)

- Ein Microsoft 365- oder Office 365-Medienendpunkt wird basierend auf den Anforderungen an die Medienverarbeitung und nicht basierend auf dem Anruftyp verwendet. (Beispielsweise kann ein Punkt-zu-Punkt-Anruf einen Medienendpunkt in der Cloud verwenden, um Medien zur Transkription oder Aufzeichnung zu verarbeiten, während eine Konferenz mit zwei Teilnehmern möglicherweise keinen Medienendpunkt in der Cloud verwendet.) Die meisten Konferenzen verwenden jedoch einen Medienendpunkt zum Mischen und Routing, der dem Ort zugeordnet ist, an dem die Konferenz gehostet wird. Der von einem Client an den Medienendpunkt gesendete Mediendatenverkehr kann aufgrund von Einschränkungen der Firewall des Kundennetzwerks direkt geleitet oder ein Transport relay in Microsoft 365 oder Office 365 verwendet werden.

- Der Mediendatenverkehr für Peer-zu-Peer-Anrufe nimmt die direkteste Route ein, die verfügbar ist, vorausgesetzt, der Anruf erfordert keinen Medienendpunkt in der Cloud (siehe vorheriges Prinzip). Die bevorzugte Route wird direkt an den Remote-Peer (Client) gesendet, aber wenn diese Route nicht verfügbar ist, leitet ein oder mehrere Transportrelais den Datenverkehr weiter. Es wird empfohlen, dass der Mediendatenverkehr keine Server wie Paket-Shaper, VPN-Server und so weiter transversalt, da sich dies auf die Medienqualität auswirken wird.

- Der Signalisierungsverkehr wird immer an den Server gesendet, der dem Benutzer am nächsten kommt.

Weitere Informationen zu den Details des ausgewählten Medienpfads finden Sie unter Grundlegendes zu [Medienflüssen in Microsoft Teams – BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).

## <a name="call-flows-in-various-topologies"></a>Anrufflüsse in verschiedenen Topologien

### <a name="teams-topology"></a>Teams-Topologie

Diese Topologie wird von Kunden verwendet, die Teams-Dienste aus der Cloud ohne lokale Bereitstellung nutzen, z. B. Skype for Business Server oder Telefonsystem Direct Routing. Darüber hinaus erfolgt die Schnittstelle zu Microsoft 365 oder Office 365 über das Internet ohne Azure Express Route.

[![Microsoft Teams Online-Anrufflüsse Abbildung 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Abbildung 1: Topologie von Teams*

Beachten Sie:

- Die Richtung der Pfeile im obigen Diagramm spiegelt die Initiierungsrichtung der Kommunikation wider, die sich auf die Konnektivität an den Unternehmensperimetern auswirkt. Bei UDP für Medien können die ersten Pakete in umgekehrter Richtung fließen, diese Pakete werden jedoch möglicherweise blockiert, bis Pakete in der anderen Richtung fließen.
- Teams wird nebeneinander mit Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Benutzer" angezeigt.

Weitere Informationen zu den folgenden optionalen Topologien finden Sie weiter unten im Artikel:

- Die lokale Skype for Business-Bereitstellung wird in **der Hybridtopologie** von Teams beschrieben.
- Telefonsystem-Direct-Routing (für PSTN-Konnektivität) wird in **Teams mit Direct Routing-Topologie beschrieben.**
- Expressroute wird in **Teams mit Expressroute-Optimierung beschrieben.**

**Flussbeschreibungen**:

- **Fluss 2** – Stellt einen Fluss dar, der von einem Benutzer im Kundennetzwerk in das Internet als Teil der Teamerfahrung des Benutzers initiiert wurde. Beispiele für diese Flüsse sind DNS- und Peer-zu-Peer-Medien.
- **Flow 2'** – Stellt einen Fluss dar, der von einem mobilen Remotebenutzer von Teams mit VPN an das Kundennetzwerk initiiert wurde.
- **Flow 3** – Stellt einen Fluss dar, der von einem mobilen Remotebenutzer von Teams an Microsoft 365- oder Office 365/Teams-Endpunkte initiiert wurde.
- **Flow 4** – Stellt einen Fluss dar, der von einem Benutzer im Kundennetzwerk zu Microsoft 365- oder Office 365/Teams-Endpunkten initiiert wurde.
- **Flow 5** – Stellt einen Peer-to-Peer-Medienfluss zwischen einem Teams-Benutzer und einem anderen Teams- oder Skype for Business-Benutzer innerhalb des Kundennetzwerks dar.
- **Flow 6** – Stellt einen Peer-to-Peer-Medienfluss zwischen einem mobilen Remotebenutzer von Teams und einem anderen mobilen Remotebenutzer von Teams oder Skype for Business über das Internet dar.

#### <a name="use-case-one-to-one"></a>Use Case: 1:1

1:1-Anrufe verwenden ein gängiges Modell, in dem der Anrufer eine Reihe von Kandidaten erhält, die aus IP-Adressen/Ports bestehen, einschließlich lokaler, relay- und reflexiver (öffentlicher IP-Adresse des Clients, wie von den Relay-Kandidaten gesehen). Der Anrufer sendet diese Kandidaten an die angerufene Partei. die aufgerufene Partei erhält auch eine ähnliche Gruppe von Kandidaten und sendet sie an den Anrufer. Meldungen zur STUN-Konnektivitätsprüfung werden verwendet, um zu finden, welche Anrufer-/so genannten Partymedienpfade funktionieren, und der beste Arbeitspfad ist ausgewählt. Medien (d. h. RTP/RTCP-Pakete, die mit SRTP gesichert sind) werden dann mit dem ausgewählten Kandidatenpaar gesendet. Das Transportrelais wird als Teil von Microsoft 365 und Office 365 bereitgestellt.

Wenn die lokale IP-Adresse/port-Kandidaten oder die reflexiven Kandidaten Konnektivität haben, wird der direkte Pfad zwischen den Clients (oder mithilfe eines NAT) für Medien ausgewählt. Wenn sich die Clients beide im Kundennetzwerk befinden, sollte der direkte Pfad ausgewählt sein. Dies erfordert eine direkte UDP-Konnektivität innerhalb des Kundennetzwerks. Wenn es sich bei den Clients sowohl um benutzerische Cloudbenutzer als auch je nach NAT/Firewall handelt, verwenden Medien möglicherweise eine direkte Konnektivität.

Wenn sich ein Client intern im Kundennetzwerk befindet und ein Client extern ist (z. B. ein mobiler Cloudbenutzer), ist es unwahrscheinlich, dass die direkte Verbindung zwischen den lokalen oder reflexiven Kandidaten funktioniert. In diesem Fall besteht eine Option in der Verwendung eines der #A0 von einem der Clients (z. B. hat der interne Client einen Relaykandidaten aus dem Transportrelais in Microsoft 365 oder Office 365 erhalten; der externe Client muss in der Lage sein, STUN/RTP/RTCP-Pakete an das Transportrelais zu senden). Eine weitere Option ist, dass der interne Client an den Vom mobilen Cloudclient erhaltenen Relaykandidat sendet. Beachten Sie, dass zwar die UDP-Konnektivität für Medien dringend empfohlen wird, TCP jedoch unterstützt wird.

**Schritte auf hoher Ebene:**

1. Teams User A löst den URL-Domänennamen (DNS) mit Fluss 2 auf.
1. Teams User A weist einen Media Relay-Port in Teams Transport Relay mithilfe von Flow 4 zu.
1. Teams Benutzer A sendet "Einladung" mit ICE-Kandidaten mit Flow 4 an Microsoft 365 oder Office 365.
1. Microsoft 365 oder Office 365 sendet mithilfe von Flow 4 Benachrichtigungen an Teams User B.
1. Teams Benutzer B weist einen Media Relay-Port in Teams Transport Relay mithilfe von Fluss 4 zu.
1. Teams Benutzer B sendet "Antwort" mit ICE-Kandidaten mithilfe von Flow 4, der mithilfe von Flow 4 zurück an Teams User A weitergeleitet wird.
1. Teams User A und Teams User B rufen ICE-Konnektivitätstests auf, und der beste verfügbare Medienpfad ist ausgewählt (siehe Diagramme unten für verschiedene Verwendungsfälle).
1. Teams Benutzer senden Telemetrie mithilfe von Fluss 4 an Microsoft 365 oder Office 365.

**Innerhalb des Kundennetzwerks:**

[![Microsoft Teams Online-Anrufflüsse Abbildung 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Abbildung 2: Innerhalb des Kundennetzwerks*

In Schritt 7 ist Peer-zu-Peer-Medienfluss 5 ausgewählt.

Medien sind bidirektional. Die Richtung von Fluss 5 gibt an, dass eine Seite die Kommunikation aus der Perspektive der Konnektivität initiiert, die mit allen Flüssen in diesem Dokument konsistent ist. In diesem Fall spielt es keine Rolle, welche Richtung verwendet wird, da sich beide Endpunkte innerhalb des Kundennetzwerks befinden.

**Kundennetzwerk an externen Benutzer (Medien, die von Teams Transport Relay weiterviert werden):**

[![Microsoft Teams Online–Anrufflüsse Abbildung 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Abbildung 3: Kundennetzwerk an externe Benutzer (Medien, die von Teams Transport Relay weitervermittelt werden)*

In Schritt 7 werden Flow 4, vom Kundennetzwerk zu Microsoft 365 oder Office 365 und Flow 3 von mobilen Remotebenutzern zu Microsoft 365 oder Office 365 ausgewählt. Diese Flüsse werden von Teams Transport Relay innerhalb von Microsoft 365 oder Office 365 weiterviert.

Medien sind bidirektional, wobei die Richtung angibt, welche Seite die Kommunikation aus Konnektivitätsperspektive initiiert. In diesem Fall werden diese Flüsse für Signalisierung und Medien mithilfe verschiedener Transportprotokolle und Adressen verwendet.

**Kundennetzwerk für externe Benutzer (direkte Medien):**

[![Microsoft Teams Online-Anrufflüsse Abbildung 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Abbildung 4: Kundennetzwerk für externen Benutzer (direkte Medien)*

In Schritt 7 ist Flow 2 aus dem Kundennetzwerk in das Internet (Peer des Clients) ausgewählt.

- Direkte Medien mit mobilen Remotebenutzern (nicht über Microsoft 365 oder Office 365 weitervermittelt) sind optional. Anders ausgedrückt: Der Kunde kann diesen Pfad blockieren, um einen Medienpfad über Transport Relay in Microsoft 365 oder Office 365 zu erzwingen.

- Medien sind bidirektional. Die Richtung von Fluss 2 zu mobilen Remotebenutzern gibt an, dass eine Seite die Kommunikation aus Konnektivitätsperspektive initiiert.

**VPN-Benutzer an internen Benutzer (medienrelaised by Teams Transport Relay)**

[![Microsoft Teams Online–Anrufflüsse Abbildung 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Abbildung 5: VPN-Benutzer an internen Benutzer (medienrelaised by Teams Transport Relay)*

Die Signalisierung zwischen dem VPN und dem Kundennetzwerk wird mithilfe von Flow 2' verwendet. Die Signalisierung zwischen dem Kundennetzwerk und Microsoft 365 oder Office 365 verwendet Fluss 4. Medien umgeht jedoch das VPN und wird mithilfe von Flows 3 und 4 über Das Medienrelais von Teams in Microsoft 365 oder Office 365 geroutet.

**VPN-Benutzer für internen Benutzer (direkte Medien)**

[![Microsoft Teams Online-Anrufflüsse Abbildung 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Abbildung 6: VPN-Benutzer für internen Benutzer (direkte Medien)*

Die Signalisierung zwischen dem VPN und dem Kundennetzwerk wird mithilfe von Flow 2' verwendet. Die Signalisierung zwischen dem Kundennetzwerk und Microsoft 365 oder Office 365 verwendet Fluss 4. Medien umgeht jedoch das VPN und wird mithilfe von Fluss 2 vom Kundennetzwerk an das Internet geroutet.

Medien sind bidirektional. Die Richtung von Fluss 2 zum mobilen Remotebenutzer gibt an, dass eine Seite die Kommunikation aus Konnektivitätsperspektive initiiert.

**VPN-Benutzer für externe Benutzer (direkte Medien)**

[![Microsoft Teams-Anrufflüsse Abbildung 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Abbildung 7: VPN-Benutzer für externe Benutzer (direkte Medien)*

Die Signalisierung zwischen dem VPN-Benutzer und dem Kundennetzwerk verwendet Fluss 2' und Fluss 4 zu Microsoft 365 oder Office 365. Medien umgeht jedoch VPN und wird mithilfe von Fluss 6 geroutet.

Medien sind bidirektional. Die Richtung von Fluss 6 an den mobilen Remotebenutzer gibt an, dass eine Seite die Kommunikation aus Konnektivitätsperspektive initiiert.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>Use Case: Teams to PSTN through Microsoft 365 or Office 365 Trunk

Microsoft 365 und Office 365 verfügen über ein Telefonsystem, mit dem Anrufe aus dem PstN (Public Switched Telephone Network) platziert und empfangen werden können. Wenn der PSTN-Trunk über den Telefonsystemanrufplan verbunden ist, gibt es für diesen Fall keine speziellen Verbindungsanforderungen. (Wenn Sie Ihren eigenen lokalen PSTN-Trunk mit Microsoft 365 oder Office 365 verbinden möchten, können Sie das direkte Telefonsystemrouting verwenden.)

[![Microsoft Teams Online-Anrufflüsse Abbildung 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Abbildung 8: Teams zu PSTN über Office 365 Trunk*

#### <a name="use-case-teams-meeting"></a>Einsatzfall: Teams-Besprechung

Der Audio-/Video-/Bildschirmfreigabeserver (VBSS) ist Teil von Microsoft 365 und Office 365. Sie verfügt über eine öffentliche IP-Adresse, die über das Kundennetzwerk erreichbar sein muss und über einen Client für die cloudnomatische Welt erreichbar sein muss. Jeder Client/Endpunkt muss eine Verbindung mit dem Konferenzserver herstellen können.

Interne Clients erhalten lokale, reflexive und Relaykandidaten auf die gleiche Weise wie bei 1:1-Anrufen beschrieben. Die Clients senden diese Kandidaten in einer Einladung an den Konferenzserver. Der Konferenzserver verwendet kein Relay, da er über eine öffentlich erreichbare IP-Adresse verfügt, sodass er mit seinem lokalen IP-Adresskandidaten antwortet. Der Client- und Konferenzserver überprüft die Konnektivität auf die gleiche Weise, die für 1:1-Anrufe beschrieben wird.

Beachten Sie:

- Teams-Clients können nicht an Skype for Business-Besprechungen teilnehmen, und Skype for Business-Clients können nicht an Teams-Besprechungen teilnehmen.

- Ein PSTN-Benutzer wählt optional "Einwählen" oder ist "Ausgewählt", abhängig von der Bereitstellung von PSTN-Anrufen und/oder Konferenzen des Organisators der Besprechung.

- Ein Gastbenutzer oder ein Kundenbenutzer kann aus einem privaten Gastnetzwerk beitreten, das mit FW/NAT mit strengen Regeln geschützt ist.

[![Microsoft Teams Online-Anrufflüsse Abbildung 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Abbildung 9: Teams-Besprechung*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Use Case: Federation with Skype for Business on premises

**Medien, die von Teams Transport Relay in Microsoft 365 oder Office 365 relayed werden**

[![Microsoft Teams Online–Anrufflüsse Abbildung 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Abbildung 10: Medien, die von Teams Transport Relay in Office 365 weitervermittelt werden*

Beachten Sie:

- Verbund ist definitionsgemäß eine Kommunikation zwischen zwei Mandanten. In diesem Fall arbeitet Mandant A, der Teams verwendet, mit Mandant B zusammen, der Skype for Business lokal verwendet. Wenn Mandant B auch Microsoft 365 oder Office 365 verwendet, hätte der Skype for Business-Client Flow 3 verwendet, um eine Verbindung mit Microsoft 365 oder Office 365 herzustellen.

- Signalisierung und Medien vom Skype for Business-Partnerclient zum lokalen Skype for Business Server sind in diesem Dokument nicht verfügbar. Es wird hier jedoch zur Übersichtlichkeit dargestellt.

- Die Signalisierung zwischen Teams und Skype for Business wird über ein Gateway überbrücken.

- Medien werden in diesem Fall mithilfe von Flow 4 von Teams Transport Relay an das Kundennetzwerk und den Skype for Business-Remoteclient weitertransportiert.

**Medien, die von Skype for Business Media Relay im Verbund-Mandanten weitergeschaltet werden**

[![Microsoft Teams Online–Anrufflüsse Abbildung 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Abbildung 11: Medien, die von Skype for Business Media Relay im Verbund-Mandanten weitervermittelt werden*

Beachten Sie:

- Signalisierung und Medien vom Skype for Business-Partnerclient zu einem lokalen Skype for Business Server sind nicht in diesem Dokument verfügbar. Es wird hier jedoch zur Übersichtlichkeit dargestellt.

- Die Signalisierung zwischen Teams und Skype for Business wird über ein Gateway überbrücken.

- Medien werden in diesem Fall mithilfe von Flow 2 vom lokalen Media Relay von Skype for Business an das Kundennetzwerk weitervermittelt. (Beachten Sie, dass der Datenverkehr vom Teams-Benutzer zum Remotemedienrelais im Verbundkundennetzwerk zunächst vom Medienrelais blockiert wird, bis der Datenverkehr in umgekehrter Richtung fließt. Der bidirektionale Fluss öffnet jedoch die Konnektivität in beide Richtungen.)

**Direkt (Peer-zu-Peer)**

[![Microsoft Teams Online-Anrufflüsse Abbildung 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Abbildung 12: Direkt (Peer-zu-Peer)*

### <a name="teams-hybrid-topology"></a>Hybridtopologie von Teams

Diese Topologie umfasst Teams mit einer lokalen Skype for Business-Bereitstellung.

[![Microsoft Teams Online-Anrufflüsse Abbildung 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Abbildung 13: Hybridtopologie von Teams*

- Die Richtung der Pfeile im obigen Diagramm spiegelt die Initiierungsrichtung der Kommunikation wider, die sich auf die Konnektivität an den Unternehmensperimetern auswirkt. Bei UDP für Medien können die ersten Pakete in umgekehrter Richtung fließen, diese Pakete werden jedoch möglicherweise blockiert, bis Pakete in der anderen Richtung fließen.

- Teams wird nebeneinander mit Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Benutzer" angezeigt.

Zusätzlicher Fluss (zusätzlich zur Teams-Topologie):

- **Flow 5A** – Stellt einen Peer-to-Peer-Medienfluss zwischen einem Teams-Benutzer innerhalb des Kundennetzwerks und einem lokalen Skype for Business-Medienrelais am Rand des Kundennetzwerks dar.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Use Case: Teams to Skype for Business one-to-one

**Hybrid im Kundennetzwerk**

[![Microsoft Teams Online-Anrufflüsse Abbildung 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Abbildung 14: Hybrid im Kundennetzwerk*

Die Signalisierung zwischen Teams und Skype for Business wird über ein Gateway überbrücken. Medien werden jedoch mithilfe von Flow 5 direkt peer-to-peer innerhalb des Kundennetzwerks geroutet.

**Hybridkundennetzwerk mit externem Skype for Business-Benutzer – von Microsoft 365 oder Office 365 relayed**

[![Microsoft Teams Online-Anrufflüsse Abbildung 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Abbildung 15: Hybrides Kundennetzwerk mit externem Skype for Business-Benutzer – von Office 365 relayed*

Beachten Sie:

- Signalisierung und Medien vom Skype for Business-Client zu einem lokalen Skype for Business Server sind in diesem Dokument nicht verfügbar. Es wird hier jedoch zur Übersichtlichkeit dargestellt.

- Die Signalisierung zwischen Teams und Skype for Business wird über ein Gateway überbrücken.

- Medien werden über das Teams Transport Relay über Flow 4 an das Kundennetzwerk weitertransportiert.

**Hybridkundennetzwerk mit externem Skype for Business-Benutzer – von lokalem Edge weiterverteilt**

[![Microsoft Teams Online-Anrufflüsse Abbildung 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Abbildung 16: Hybrides Kundennetzwerk mit externem Skype for Business-Benutzer – vom lokalen Edge weiterverteilt*

Beachten Sie:

- Signalisierung und Medien vom Skype for Business-Client zu einem lokalen Skype for Business Server sind in diesem Dokument nicht verfügbar. Es wird hier jedoch zur Übersichtlichkeit dargestellt.

- Die Signalisierung wird von einem Gateway überbrücket.

- Medien werden von Skype for Business Media Relay innerhalb des lokalen Skype for Business Edge an Teams-Benutzer innerhalb des Kundennetzwerks mithilfe von Media Flow 5A weitervermittelt.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams mit Topologie des Telefonsystems für direktes Routing

Diese Topologie umfasst Teams mit Telefonsystem-Direct-Routing.

Mit Direct Routing können Sie einen Dienstanbieter des öffentlichen Telefonnetzwerks (Public Switched Telephone Network, PSTN) eines Drittanbieters verwenden, indem Sie ein unterstütztes lokales Hardwaregerät für den Session Border Controller (SBC) mit Microsoft 365 oder Office 365 koppeln und dann den Telefoniestamm mit diesem Gerät verbinden.

Um dieses Szenario zu unterstützen, muss der Kunde einen zertifizierten SBC für Direct Routing von einem der zertifizierten Microsoft-Partner bereitstellen. Der SBC muss wie vom Anbieter empfohlen konfiguriert werden und für direkten UDP-Datenverkehr von Microsoft 365 oder Office 365 routierbar sein. Die Medien können direkt von Teams und/oder dem Skype for Business-Client zum SBC (unter Umgehung des Teams-Gateways) oder über das Teams-Gateway fließen. Die Konnektivität mit dem SBC basiert, wenn der Trunk für die Umgehung des Teams-Gateways konfiguriert ist, auf ICE, in dem SBC ICE-Lite unterstützt, während der Medienendpunkt von Teams/Skype for Business ICE Full Form unterstützt.

[![Microsoft Teams Online-Anrufflüsse Abbildung 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Abbildung 17: Topologie von Teams mit Telefonsystem-Direct-Routing

Beachten Sie:

- Die Richtung der Pfeile im obigen Diagramm spiegelt die Initiierungsrichtung der Kommunikation wider, die sich auf die Konnektivität an den Unternehmensperimetern auswirkt. Bei UDP für Medien können die ersten Pakete in umgekehrter Richtung fließen, diese Pakete werden jedoch möglicherweise blockiert, bis Pakete in der anderen Richtung fließen.

- Teams wird nebeneinander mit Skype for Business Online bereitgestellt, daher werden Clients als "Teams/SFB-Benutzer" angezeigt.

Zusätzliche Flüsse (zusätzlich zur Onlinetopologie von Teams):

- **Flow 4'** – Stellt einen Fluss von Microsoft 365 oder Office 365 zum Kundennetzwerk dar, mit dem eine Verbindung zwischen dem Medienserver von Teams in der Cloud und dem lokalen SBC herzustellen ist.
- **Flow 5B** – Stellt einen Medienfluss zwischen dem Teams-Benutzer innerhalb des Kundennetzwerks mit dem Direct Routing SBC im Umgehungsmodus dar.
- **Flow 5C** – Stellt einen Medienfluss zwischen dem Direct Routing SBC zu einem anderen Direct Routing SBC in einem PSTN-Hairpin-Anrufumgehungsmodus dar.

**Interner Benutzer mit Direct Routing (Medien, die von Teams Transport Relay weitervermittelt werden)**

[![Microsoft Teams Online-Anrufflüsse Abbildung 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Abbildung 18: Interner Benutzer mit Direct Routing (Medien, die von Teams Transport Relay weitervermittelt werden)*

Beachten Sie:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Microsoft 365 oder Office 365 routierbar ist.

- Signalisierung und Medien vom SBC zu Microsoft 365 oder Office 365 und umgekehrt verwenden Flow 4 und/oder Flow 4'.

- Signalisierung und Medien vom Client im Kundennetzwerk an Microsoft 365 oder Office 365 verwenden Flow 4.

**Remotebenutzer mit Direct Routing (Medien werden über einen Medienserver (MP) geroutet)**

[![Microsoft Teams Online-Anrufflüsse Abbildung 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Abbildung 19: Remotebenutzer mit Direct Routing (Medien werden über einen Medienserver (MP) geroutet)*

Beachten Sie:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Microsoft 365 oder Office 365 routierbar ist.

- Signalisierung und Medien vom SBC zu Microsoft 365 oder Office 365 und umgekehrt verwenden Flow 4 und/oder Flow 4'.

- Signalisierung und Medien vom Client im Internet an Microsoft 365 oder Office 365 verwenden Fluss 3.

**Direktes Routing für interne Benutzer (Medienumgehung)**

[![Microsoft Teams Online-Anrufflüsse Abbildung 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Abbildung 20: Direktes Routing für interne Benutzer (Medienumgehung)*

Beachten Sie:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Microsoft 365 oder Office 365 routierbar ist.

- Bei Signalisierung von SBC zu Microsoft 365 oder Office 365 und umgekehrt verwenden Sie Flow 4 und/oder Flow 4'.

- Wenn Sie vom Client innerhalb des Kundennetzwerks an Microsoft 365 oder Office 365 signalisieren, verwenden Sie Flow 4.

- Medien vom Client im Kundennetzwerk bis zu SBC innerhalb des Kundennetzwerks verwenden Flow 5B.

**Remotebenutzer mit Direct Routing (Medienumgehung, die von Teams Transport Relay weitervermittelt wird)**

[![Microsoft Teams Online-Anrufflüsse Abbildung 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Abbildung 21: Remotebenutzer mit Direct Routing (Medienumgehung, die von Teams Transport Relay weitervermittelt wird)*

Beachten Sie:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Microsoft 365 oder Office 365 und dem Internet routierbar ist.

- Bei der Signalisierung von SBC an Microsoft 365 oder Office 365 und umgekehrt wird Flow 4 und/oder Flow 4' verwendet.

- Bei der Signalisierung vom Client im Internet an Microsoft 365 oder Office 365 wird Flow 3 verwendet.

- Medien vom Client im Internet an den SBC innerhalb des Kundennetzwerks verwenden die Flüsse 3 und 4, die von Teams Transport Relay übertragen werden.

**Direct Routing für Remotebenutzer (direkte Medienumgehung)**

[![Microsoft Teams Online-Anrufflüsse Abbildung 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Abbildung 22: Direktes Routing für Remotebenutzer (direkte Medienumgehung)*

Beachten Sie:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die aus Microsoft 365 oder Office 365 und dem Internet routierbar ist.

- Bei der Signalisierung von SBC an Microsoft 365 oder Office 365 und umgekehrt wird Flow 4 und/oder Flow 4' verwendet.

- Bei der Signalisierung vom Client im Internet an Microsoft 365 oder Office 365 wird Flow 3 verwendet.

- Medien vom Client im Internet bis zum SBC innerhalb des Kundennetzwerks verwenden Flow 2.

**Direktes Routing (Medienumgehung) – PSTN-Hairpinanruf (aufgrund von Anruf forward/transfer)**

[![Microsoft Teams Online–Anrufflüsse Abbildung 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Abbildung 23: Direktes Routing (Medienumgehung) – PstN-Haarnadelanruf (aufgrund von Anruf weiterleiten/Übertragung)*

Beachten Sie:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Microsoft 365 oder Office 365 routierbar ist.

- Bei der Signalisierung von SBC an Microsoft 365 oder Office 365 und umgekehrt wird Flow 4 und/oder Flow 4' verwendet.

- Der Client befindet sich nicht mehr in der Signal- und Medienschleife, nachdem der Anruf von PSTN in PSTN umgeklammert wurde.

- Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.

**Direktes Routing (Medien über Microsoft 365 oder Office 365) – PstN-Hairpinanruf für zwei Mandanten**

[![Microsoft Teams Online–Anrufflüsse Abbildung 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Abbildung 24: Direktes Routing (Medien über Microsoft 365 oder Office 365) – PSTN-Hairpinanruf über zwei Mandanten hinweg*

Beachten Sie:

- Der SBC muss über eine öffentliche IP-Adresse verfügen, die von Microsoft 365 oder Office 365 routierbar ist.

- Bei der Signalisierung von SBC an Microsoft 365 oder Office 365 und umgekehrt wird Flow 4 und/oder Flow 4' verwendet.

- Der Client befindet sich nicht mehr in der Signal- und Medienschleife, nachdem der Anruf von PSTN in PSTN umgeklammert wurde.

- Medien von SBC-Instanz A im Kundennetzwerk X-zu-SBC-Instanz B müssen über den Microsoft 365- oder Office 365 Media Server übertragen werden und können den Umgehungsmodus nicht verwenden.

## <a name="teams-with-express-route-optimization"></a>Teams mit Expressroutenoptimierung

[![Microsoft Teams Online–Anrufflüsse Abbildung 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Abbildung 25: Teams mit Expressroutenoptimierung*

Für den Fall, dass ExpressRoute berechtigt und bereitgestellt ist, können Teams-Flüsse von Fluss 4 auf Fluss 1 und von Fluss 4' zu Fluss 1' umgeroutet werden. Die #A0 ist jedoch stark von anderen Microsoft 365- oder Office 365-Flüssen über das Internet abhängig, die die Flüsse 4 und 4' verwenden. daher dürfen diese Flüsse nicht blockiert werden.

Beachten Sie, dass der Skype for Business-Hybriddatenverkehr an das Internet und nicht an Express Route übermittelt wird, um mit externen Benutzern zu kommunizieren und mit anderen Mandanten zusammen zu kommunizieren.

Um asymmetrische Ströme zu verhindern, muss das erneute Routing in beide Richtungen gehen. Mit anderen Worten: Eine Adresse innerhalb des Kundennetzwerks ist entweder über das Internet oder express Route auf der Grundlage der Optimierung, aber nicht über beides routingfähig.


**Kundennetzwerk an externen Benutzer (Medien, die von Teams Transport Relay weiterviert werden):**

[![Microsoft Teams Online–Anrufflüsse Abbildung 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Abbildung 26: Kundennetzwerk an externe Benutzer (Medien, die von Teams Transport Relay weitervermittelt werden)*

**Schritte auf hoher Ebene:**

1. Teams Benutzer innerhalb des Kundennetzwerks löst den NAMEN der URL-Domäne (DNS) mithilfe von flow2 auf.
1. Teams Benutzer innerhalb des Kundennetzwerks weisen einen Media Relay-Port für Teams Transport Relay mithilfe von Flow 1 zu.
1. Teams Benutzer innerhalb des Kundennetzwerks sendet "Einladung" mit ICE-Kandidaten mit Flow 1 an Microsoft 365 oder Office 365.
1. Microsoft 365 oder Office 365 sendet mithilfe von Flow 3 Benachrichtigungen an externe Teams-Benutzer.
1. Der externe Benutzer von Teams weist einen Media Relay-Port in Teams Transport Relay mithilfe von Fluss 3 zu.
1. Externe Teams-Benutzer sendet mithilfe von Flow 3 eine "Antwort" mit ICE-Kandidaten, die mithilfe von Flow 1 wieder an Teams-Benutzer A weitergeleitet wird.
1. Teams User A und Teams User B rufen ICE-Konnektivitätstests auf und wählen die Flüsse 1 und 3 aus, die von Teams Transport Relay weitervermittelt werden.
1. Teams Benutzer senden Telemetriedaten mithilfe der Flüsse 1 und 3 an Microsoft 365 oder Office 365.

> [!NOTE]
> Flow 4 muss aktiviert sein, um Abhängigkeiten der Teams-Anwendung von anderen Mikrodiensten zu unterstützen, die Fluss 4 vorverdingen.