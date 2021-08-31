---
title: SIP-Trunking in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Informationen zum SIP-Trunking in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: d10f14a8c3f65309c52351a0721aa042faad47b6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728234"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>SIP-Trunking in Skype for Business Server

Informationen zum SIP-Trunking in Skype for Business Server Enterprise-VoIP

SIP (Session Initiation Protocol) wird zum Initiieren und Verwalten von VoIP-Kommunikationssitzungen (Voice over IP) für grundlegende Telefondienste und zusätzliche Echtzeitkommunikationsdienste wie Instant Messaging, Konferenzfunktionen, Anwesenheitserkennung und Multimediafunktionen verwendet. Dieser Abschnitt umfasst Planungsinformationen für die Implementierung von SIP-Trunks, eine Art von SIP-Verbindung, die über die Grenzen Ihres lokalen Netzwerks hinausgeht.

## <a name="what-is-sip-trunking"></a>Was ist SIP-Trunking?

Bei einem SIP-Trunk handelt es sich um eine IP-Verbindung für die SIP-Kommunikation zwischen Ihrer Organisation und einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP), die über Ihre Firewall hinausgeht. In der Regel wird ein SIP-Trunk verwendet, um den zentralen Standort Ihrer Organisation mit einem ITSP zu verbinden. In einigen Fällen können Sie das SIP-Trunking auch zum Verbinden einer Zweigstelle mit einem ITSP nutzen.

Die Bereitstellung von SIP-Trunking kann ein großer Schritt zur Vereinfachung der Telekommunikation Ihrer Organisation und zur Vorbereitung auf aktuelle Verbesserungen der Echtzeitkommunikation sein. Einer der Hauptvorteile von SIP-Trunking besteht darin, dass Sie die Verbindungen Ihrer Organisation mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) an einem zentralen Standort konsolidieren können, im Gegensatz zum Vorgänger, dem TDM-Trunking (Time Division Multiplexing), das in der Regel einen separaten Trunk von jedem Zweigstellenstandort erfordert.

### <a name="cost-savings"></a>Kosteneinsparung

Die mit dem SIP-Trunking verbundene Kosteneinsparung kann erheblich sein:

- Die Kosten für Ferngespräche sind bei Verwendung eines SIP-Trunks in der Regel deutlich niedriger.

- Sie können die Verwaltungskosten senken und die Komplexität der Bereitstellung verringern.

- Gebühren für Basisanschlüsse (Basic Rate Interface, BRI) und Primärmultiplexanschlüsse (Primary Rate Interface, PRI) entfallen, wenn Sie eine deutlich günstigere Direktverbindung zwischen SIP-Trunk und Ihrem Anbieter von Internettelefoniediensten (ISTP) konfigurieren. Beim TDM-Trunking rechnen Dienstanbieter Anrufe pro Minute ab. Die Kosten für das SIP-Trunking können auf der Bandbreitennutzung basieren, die Sie in kleineren, wirtschaftlicheren Einheiten erwerben können. (Die tatsächlichen Kosten richten sich nach dem Servicemodell des jeweiligen Anbieters von Internettelefoniediensten (ITSP).)

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP-Trunking im Vergleich zum Hosting eines PSTN-Gateways oder einer IP-Nebenstellenanlage

Da SIP-Trunks eine direkte Verbindung mit dem Dienstanbieter herstellen, entfallen Ihre PSTN-Gateways und die damit verbundenen Verwaltungskosten sowie die Komplexität dieser Lösung. Die Verwendung von SIP-Trunks kann durch einen geringeren Wartungs- und Verwaltungsaufwand zu einer erheblichen Kosteneinsparung beitragen.

### <a name="expanded-voip-services"></a>Erweiterte VoIP-Dienste

VoIP-Funktionen sind häufig die wichtigste Motivation für die Bereitstellung von SIP-Trunking, die VoIP-Unterstützung stellt jedoch nur den ersten Schritt dar. Mit SIP-Trunking können Sie VoIP-Funktionen erweitern und Skype for Business Server aktivieren, um eine umfangreichere Gruppe von Diensten bereitzustellen. Beispiel:

- Die erweiterte Anwesenheitserkennung für Geräte, die nicht Skype for Business Server ausgeführt werden, kann eine bessere Integration in Mobiltelefone ermöglichen, sodass Sie sehen können, wann sich ein Benutzer in einem Mobiltelefon befindet.

- E9-1-1-Notrufe ermöglichen es den Behörden, 911 Anrufe entgegenzunehmen, den Standort des Anrufers anhand seiner Telefonnummer zu ermitteln.

> [!NOTE]
> Erkundigen Sie sich bei Ihrem ITSP, welche Dienste unterstützt werden und für Ihre Organisation aktiviert werden können.

### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP-Trunks im Vergleich zu direkten SIP-Verbindungen

Der Begriff Trunk wurde aus der leitungsvermittelten Technologie abgeleitet. Er bezieht sich auf eine dedizierte physische Leitung zur Verbindung von Telefonvermittlungsanlagen. Wie ihr Vorgänger, TDM-Trunks (Time Division Multiplexing), sind SIP-Trunks Verbindungen zwischen zwei separaten SIP-Netzwerken – dem Skype for Business Server Unternehmen und dem ITSP. Im Gegensatz zu leitungsvermittelten Trunks handelt es sich bei SIP-Trunks um virtuelle Verbindungen, die über jeden der unterstützten Typen von SIP-Trunkingverbindungen hergestellt werden können.

Bei direkten SIP-Verbindungen hingegen handelt es sich um SIP-Verbindungen, die nicht über die Grenzen des lokalen Netzwerks hinausgehen (das heißt, es wird eine Verbindung mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) oder einer Nebenstellenanlage (Private Branch Exchange, PBX) innerhalb des internen Netzwerks hergestellt). Ausführliche Informationen dazu, wie Sie direkte SIP-Verbindungen mit Skype for Business Server verwenden können, finden Sie [unter "Direkte SIP-Verbindungen" in Skype for Business Server.](direct-sip.md)

## <a name="how-do-i-implement-sip-trunking"></a>Wie implementiere ich SIP-Trunking?

Um SIP-Trunking zu implementieren, müssen Sie die Verbindung über einen Vermittlungsserver weiterleiten, der als Proxy für Kommunikationssitzungen zwischen Skype for Business Server Clients und dem Dienstanbieter fungiert und bei Bedarf Medien transkodiert.

Jeder Vermittlungsserver verfügt über eine interne Netzwerkschnittstelle und eine externe Netzwerkschnittstelle. Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern her. Die externe Schnittstelle wird häufig als Gatewayschnittstelle bezeichnet, da sie traditionell zum Verbinden des Vermittlungsservers mit einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Nebenstellenanlage verwendet wurde. Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle des Vermittlungsservers mit der externen Edgekomponente des ITSP. Die externe Edgekomponente des ITSP kann ein SBC (Session Border Controller), ein Router oder ein Gateway sein.

Ausführliche Informationen zu Vermittlungsservern finden Sie [unter "Vermittlungsserverkomponente" in Skype for Business Server.](mediation-server.md)

### <a name="centralized-vs-distributed-sip-trunking"></a>Zentralisiertes und verteiltes SIP-Trunking im Vergleich

Zentrales SIP-Trunking leitet den gesamten VoIP-Datenverkehr, einschließlich Zweigstellendatenverkehr, über Ihren zentralen Standort weiter. Das zentrale Bereitstellungsmodell ist einfach und kostengünstig und ist im Allgemeinen der empfohlene Ansatz für die Implementierung von SIP-Trunks mit Skype for Business Server.

Verteiltes SIP-Trunking ist ein Bereitstellungsmodell, in dem Sie lokale SIP-Trunks an einem oder mehreren Zweigstellenstandorten implementieren. VoIP-Datenverkehr wird dann von der Zweigstelle direkt an einen Dienstanbieter weitergeleitet, ohne den zentralen Standort zu durchlaufen.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

- Für den Zweigstellenstandort muss Ausfallsicherheit gewährleistet werden (beispielsweise bei einem WAN-Ausfall). Diese Anforderung sollte für jede Zweigstelle analysiert werden. Einige Ihrer Verzweigungen erfordern möglicherweise Redundanz und Failover, andere dagegen nicht.

- Resilienz ist zwischen zwei zentralen Standorten erforderlich. Sie müssen sicherstellen, dass ein SIP-Trunk an jedem zentralen Standort beendet wird. Wenn Sie z. B. über zentrale Standorte von Dublin und Xamlwila verfügen und beide nur den SIP-Trunk eines Standorts verwenden, können die Benutzer des anderen Standorts keine PSTN-Anrufe tätigen, wenn der Trunk ausfällt.

- Die Zweigstelle und der zentrale Standort befinden sich in verschiedenen Ländern/Regionen. Aus Kompatibilitäts- und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region. Beispielsweise kann die Kommunikation in der Europäischen Union ein Land/eine Region nicht verlassen, ohne lokal an einem zentralen Punkt zu enden.

Abhängig vom geografischen Standort der Standorte und dem erwarteten Datenverkehr in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralen SIP-Trunk weiterleiten, oder Sie können sich dafür entscheiden, einige Benutzer über einen SIP-Trunk an ihrem Zweigstellenstandort weiterzuleiten. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

- Wie groß ist jede Website (d. a. wie viele Benutzer sind für Enterprise-VoIP aktiviert)?

- Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?

Die Entscheidung, ob zentrales oder verteiltes SIP-Trunking bereitgestellt werden soll, erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht erforderlich ist. In einer vollständig zentralisierten Bereitstellung wird der gesamte Zweigstellendatenverkehr über WAN-Verbindungen geroutet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, möchten Sie möglicherweise das verteilte SIP-Trunking verwenden. Sie können z. B. einen Standard Edition-Server an einem Zweigstellenstandort mit Partnerverbund am zentralen Standort bereitstellen oder eine Survivable Branch Appliance oder einen Survivable Branch Server mit einem kleinen Gateway bereitstellen.

> [!NOTE]
> Ausführliche Informationen zum verteilten SIP-Trunking finden Sie unter [Branch Site SIP trunking in Skype for Business Server](branch-site.md).

### <a name="supported-sip-trunking-connection-types"></a>Unterstützte Verbindungstypen für das SIP-Trunking

Skype for Business Server unterstützt die folgenden Verbindungstypen für SIP-Trunking:

- Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird für andere Abonnenten freigegeben, und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten eines Abonnenten von den Daten eines anderen Teilnehmers zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

- Eine private Verbindung ohne anderen Datenverkehr – beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung – stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

- Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit. Die Internetverbindung ist der einzige Skype for Business Server SIP-Trunking-Verbindungstyp, der VPN erfordert.

#### <a name="selecting-a-connection-type"></a>Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

- Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

- Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).

- Für kleine Unternehmen oder Zweigstellen mit geringem Anrufaufkommen kann SIP-Trunking über das Internet die beste Wahl sein. Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.

### <a name="bandwidth-requirements"></a>Erforderliche Bandbreite

Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (die Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:

Spitzenbandbreite für den SIP-Trunk = Max. gleichzeitige Anrufe x (64 KBit/s + Headergröße)

> [!NOTE]
> Die Headergröße beträgt maximal 20 Byte.

### <a name="codec-support"></a>Codec-Unterstützung

Skype for Business Server unterstützt nur die folgenden Codecs:

- G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)

- G.711 µ-Law (wird in Nordamerika verwendet)

### <a name="internet-telephony-service-provider"></a>Anbieter von Internettelefoniediensten

Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten. Informationen zur Bereitstellung erhalten Sie bei Ihrem Dienstanbieter. Eine Liste der zertifizierten SIP-Trunkingdienstanbieter finden Sie auf der Website des [Microsoft Unified Communications Open Interoperability Program.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)

Ausführliche Informationen zu für Microsoft zertifizierten Anbietern von SIP-Trunking erhalten Sie bei Ihrem Microsoft-Ansprechpartner.

> [!IMPORTANT]
> Sie müssen einen für Microsoft zertifizierten Dienstanbieter nutzen, um sicherzustellen, dass Ihr Anbieter von Internettelefoniediensten sämtliche Funktionen unterstützt, die über den SIP-Trunk verarbeitet werden (z. B. das Einrichten und Verwalten von Sitzungen sowie die Unterstützung aller erweiterten VoIP-Dienste). Der technische Support von Microsoft kann nicht für Konfigurationen in Anspruch genommen werden, die nicht zertifizierte Anbieter verwenden. Wenn Sie gegenwärtig einen Internetdienstanbieter nutzen, der nicht für SIP-Trunking zertifiziert ist, können Sie diesen Anbieter weiterhin als ISP nutzen und sich für das SIP-Trunking für einen für Microsoft zertifizierten Anbieter entscheiden.

### <a name="topologies-and-components-for-sip-trunking"></a>Topologien und Komponenten für SIP-Trunking

Die folgende Abbildung zeigt die SIP-Trunkingtopologie in Skype for Business Server.

**SIP-Trunkingtopologie**

![SIP-Trunkingtopologie.](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Wie im Diagramm dargestellt, wird ein VIRTUELLEs privates IP-Netzwerk (VPN) für die Verbindung zwischen dem Unternehmensnetzwerk und dem PSTN-Dienstanbieter (Public Switched Telephone Network) verwendet. Der Zweck dieses privaten Netzwerks besteht darin, IP-Konnektivität bereitzustellen, die Sicherheit zu verbessern und (optional) QoS-Garantien (Quality of Service) zu erhalten. Aufgrund der Art eines VPN müssen Sie Transport Layer Security (TLS) nicht für SIP-Signaldatenverkehr oder SRTP (Secure Real-Time Transport Protocol) für den Mediendatenverkehr verwenden. Verbindungen zwischen dem Unternehmen und dem Dienstanbieter bestehen daher aus einfachen TCP-Verbindungen für SIP und rtp (plain real-time transport protocol) (über UDP) für Medientunnel, die über ein IP-VPN getunnelt werden. Stellen Sie sicher, dass alle Firewalls zwischen den VPN-Routern über offene Ports verfügen, damit die VPN-Router kommunizieren können, und dass die IP-Adressen an den externen Rändern der VPN-Router öffentlich routingbar sind.

> [!IMPORTANT]
> Wenden Sie sich an Ihren Dienstanbieter, um festzustellen, ob er Unterstützung für hohe Verfügbarkeit bietet, einschließlich Failover. Wenn ja, müssen Sie die Verfahren für die Einrichtung festlegen. Müssen Sie beispielsweise nur eine IP-Adresse und einen SIP-Trunk auf jedem Vermittlungsserver konfigurieren, oder müssen Sie mehrere SIP-Trunks auf jedem Vermittlungsserver konfigurieren? > Wenn Sie mehrere zentrale Standorte haben, fragen Sie auch, ob der Dienstanbieter in der Lage ist, Verbindungen zu und von einem anderen zentralen Standort zu aktivieren.

> [!NOTE]
> Für SIP-Trunking wird dringend empfohlen, eigenständige Vermittlungsserver bereitzustellen. Ausführliche Informationen finden Sie unter [Bereitstellen von Vermittlungsservern und Definieren von Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers) in der Bereitstellungsdokumentation.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Sichern des Vermittlungsservers für SIP-Trunking

Aus Sicherheitsgründen sollten Sie für jede Verbindung zwischen den beiden VPN-Routern ein virtuelles LAN (VLAN) einrichten. Der tatsächliche Prozess zum Einrichten eines VLAN variiert von Routerhersteller zu Router. Weitere Informationen erhalten Sie von Ihrem Routeranbieter.

Es wird empfohlen, folgende Richtlinien zu befolgen:

- Richten Sie ein virtuelles LAN (VLAN) zwischen dem Vermittlungsserver und dem VPN-Router im Umkreisnetzwerk (auch als DMZ, demilitarisierte Zone und überprüftes Subnetz bezeichnet) ein.

- Übertragungs- oder Multicastpakete dürfen nicht vom Router an das VLAN übertragen werden.

- Blockieren Sie alle Routingregeln, die Datenverkehr vom Router an eine beliebige Stelle weiterleiten, außer an den Vermittlungsserver.

Wenn Sie einen VPN-Server verwenden, empfehlen wir, dass Sie die folgenden Richtlinien befolgen:

- Richten Sie ein VLAN zwischen dem VPN-Server und dem Vermittlungsserver ein.

- Übertragungs- oder Multicastpakete dürfen nicht vom VPN-Server an das VLAN übertragen werden.

- Blockieren Sie alle Routingregelen, die VPN-Serverdatenverkehr an eine beliebige Stelle außer dem Vermittlungsserver weiterleiten.

- Verschlüsseln von Daten auf dem VPN mithilfe der generischen Routing-Kapselung (GENERIC Routing Encapsulation, GRE).

## <a name="see-also"></a>Siehe auch

[SIP-Trunking am Zweigstellenstandort in Skype for Business Server](branch-site.md)