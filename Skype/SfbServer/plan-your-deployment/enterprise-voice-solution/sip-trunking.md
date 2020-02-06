---
title: SIP-Trunking in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Weitere Informationen zu SIP-Trunking in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 229774ef976a08031da7892dec0088d78b954b24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802415"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>SIP-Trunking in Skype for Business Server

Weitere Informationen zu SIP-Trunking in Skype for Business Server Enterprise-VoIP

SIP (Session Initiation Protocol) wird zum Initiieren und Verwalten von VoIP-Kommunikationssitzungen (Voice over IP) für grundlegende Telefondienste und zusätzliche Echtzeitkommunikationsdienste wie Chats, Konferenzfunktionen, Anwesenheitserkennung und Multimediafunktionen verwendet. Dieser Abschnitt umfasst Planungsinformationen für die Implementierung von SIP-Trunks, einer Art von SIP-Verbindung, die über die Grenzen Ihres lokalen Netzwerks hinausgeht.

## <a name="what-is-sip-trunking"></a>Was ist SIP-Trunking?

Bei einem SIP-Trunk handelt es sich um eine IP-Verbindung für die SIP-Kommunikation zwischen Ihrer Organisation und einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP), die über Ihre Firewall hinausgeht. In der Regel wird ein SIP-Trunk verwendet, um die zentrale Website Ihrer Organisation mit einem ITSP zu verbinden. In einigen Fällen können Sie das SIP-Trunking auch zum Verbinden einer Zweigstelle mit einem ITSP nutzen.

Das Bereitstellen von SIP-Trunking kann einen großen Schritt zur Vereinfachung der Telekommunikation in Ihrer Organisation und zur Vorbereitung auf aktuelle Verbesserungen bei der Echtzeitkommunikation sein. Einer der Hauptvorteile von SIP-Trunking besteht darin, dass Sie die Verbindungen Ihrer Organisation mit dem öffentlichen Telefonnetz (PSTN) an einem zentralen Standort konsolidieren können, im Gegensatz zu dem Vorgänger-Trunking (Time Division Multiplexing), das in der Regel erfordert einen separaten trunk von jeder Verzweigungs Website.

### <a name="cost-savings"></a>Kosteneinsparung

Die mit dem SIP-Trunking verbundene Kosteneinsparung kann erheblich sein:

- Die Kosten für Ferngespräche sind bei Verwendung eines SIP-Trunks in der Regel deutlich niedriger.

- Sie können die Verwaltungskosten senken und die Komplexität der Bereitstellung verringern.

- Gebühren für Basisanschlüsse (Basic Rate Interface, BRI) und Primärmultiplexanschlüsse (Primary Rate Interface, PRI) entfallen, wenn Sie eine deutlich günstigere Direktverbindung zwischen einem SIP-Trunk und Ihrem Anbieter von Internettelefoniediensten (ITSP) konfigurieren. Beim TDM-Trunking rechnen Dienstanbieter Anrufe pro Minute ab. Die Kosten für das SIP-Trunking können auf der Bandbreitennutzung basieren, die Sie in kleineren, wirtschaftlicheren Einheiten erwerben können. (Die tatsächlichen Kosten richten sich nach dem Servicemodell des jeweiligen Anbieters von Internettelefoniediensten (ITSP).)

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP-Trunking im Vergleich zum Hosting eines PSTN-Gateways oder einer IP-Nebenstellenanlage

Da SIP-Trunks eine direkte Verbindung mit dem Dienstanbieter herstellen, entfallen Ihre PSTN-Gateways und die damit verbundenen Verwaltungskosten sowie die Komplexität dieser Lösung. Die Verwendung von SIP-Trunks kann durch einen geringeren Wartungs- und Verwaltungsaufwand zu einer erheblichen Kosteneinsparung beitragen.

### <a name="expanded-voip-services"></a>Erweiterte VoIP-Dienste

VoIP-Funktionen sind häufig die wichtigste Motivation für die Bereitstellung von SIP-Trunking, die VoIP-Unterstützung stellt jedoch nur den ersten Schritt dar. Mit SIP-Trunking können Sie die VoIP-Funktionen erweitern und Skype for Business Server in die Lage versetzen, umfassendere Dienste bereitzustellen. Beispiel:

- Die verbesserte Anwesenheitserkennung für Geräte, die nicht mit Skype for Business Server ausgestattet sind, kann eine bessere Integration mit Mobiltelefonen ermöglichen, sodass Sie sehen können, wann ein Nutzer einen handyanruf hat.

- Mit E9-1-1-Notrufen können die Behörden, die 911-Anrufe annehmen, den Standort des Anrufers anhand seiner Telefonnummer ermitteln.

> [!NOTE]
> Erkundigen Sie sich bei Ihrem ITSP, welche Dienste unterstützt werden und für Ihre Organisation aktiviert werden können.

### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP-Trunks und direkte SIP-Verbindungen im Vergleich

Der Begriff Trunk wurde aus der leitungsvermittelten Technologie abgeleitet. Er bezieht sich auf eine dedizierte physische Leitung zur Verbindung von Telefonvermittlungsanlagen. Wie ihre Vorgänger-, Time Division Multiplexing-(TDM-) Trunks sind SIP-Stämme Verbindungen zwischen zwei getrennten SIP-Netzwerken – dem Skype for Business Server Enterprise-und dem ITSP. Im Gegensatz zu leitungsvermittelten Trunks handelt es sich bei SIP-Trunks um virtuelle Verbindungen, die über jeden der unterstützten Typen von SIP-Trunkingverbindungen hergestellt werden können.

Bei direkten SIP-Verbindungen hingegen handelt es sich um SIP-Verbindungen, die nicht über die Grenzen des lokalen Netzwerks hinausgehen (das heißt, es wird eine Verbindung mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) oder einer Nebenstellenanlage (Private Branch Exchange, PBX) innerhalb des internen Netzwerks hergestellt). Details dazu, wie Sie direkte SIP-Verbindungen mit Skype for Business Server verwenden können, finden Sie unter [direkte SIP-Verbindungen in Skype for Business Server](direct-sip.md).

## <a name="how-do-i-implement-sip-trunking"></a>Implementierung von SIP-Trunking

Um SIP-Trunking zu implementieren, müssen Sie die Verbindung über einen Vermittlungs Server weiterleiten, der als Proxy für Kommunikationssitzungen zwischen Skype for Business Server-Clients und dem Dienstanbieter fungiert und die Medien bei Bedarf transcodieren kann.

Jeder Vermittlungs Server verfügt über eine interne Netzwerkschnittstelle und eine externe Netzwerkschnittstelle. Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern her. Die externe Schnittstelle wird gemeinhin als Gateway-Schnittstelle bezeichnet, da Sie traditionell verwendet wurde, um den Vermittlungs Server mit einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Telefonanlage zu verbinden. Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle des Vermittlungsservers mit der Komponente External Edge des ITSP. Die externe Edgekomponente des ITSP könnte ein Session Border Controller (SBC), ein Router oder ein Gateway sein.

Details zu Vermittlungsservern finden Sie unter [Mediation Server-Komponente in Skype for Business Server](mediation-server.md).

### <a name="centralized-vs-distributed-sip-trunking"></a>Zentralisiertes und verteiltes SIP-Trunking im Vergleich

Zentrales SIP-Trunking leitet den gesamten VoIP-Datenverkehr, einschließlich des verzweigten Website Verkehrs, über Ihren zentralen Standort weiter. Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und im Allgemeinen der empfohlene Ansatz für die Implementierung von SIP-Stämmen mit Skype for Business Server.

Distributed SIP Trunking ist ein Bereitstellungsmodell, bei dem Sie lokale SIP-Stämme an einer oder mehreren Zweigstellen implementieren. VoIP-Datenverkehr wird dann direkt von der Verzweigungs Website an einen Dienstanbieter weitergeleitet, ohne die zentrale Website zu durchlaufen.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

- Die Verzweigungs Website erfordert eine überlebensfähige Telefonverbindung (beispielsweise, wenn das WAN ausfällt). Diese Anforderung sollte für jede Verzweigungs Website analysiert werden. einige ihrer Zweigstellen erfordern möglicherweise Redundanz und Failover, während andere möglicherweise nicht.

- Zwischen zwei zentralen Standorten ist eine Ausfallsicherheit erforderlich. Sie müssen sicherstellen, dass ein SIP-Trunk an jedem zentralen Standort beendet wird. Wenn Sie beispielsweise über Dublin-und Tukwila-zentrale Websites verfügen und beide nur den SIP-Stamm einer Website verwenden, können die Benutzer der anderen Website keine PSTN-Anrufe tätigen, wenn der trunk herunterfällt.

- Die Verzweigungs Website und der zentrale Standort befinden sich in verschiedenen Ländern/Regionen. Aus Kompatibilitäts-und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region. In der Europäischen Union kann die Kommunikation beispielsweise ein Land/eine Region nicht bestanden, ohne lokal an einem zentralen Punkt zu beenden.

Je nach geographischem Standort der Websites und dem voraussichtlichen Datenverkehr in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralen SIP-Stamm weiterleiten, oder Sie können einige Benutzer über einen SIP-Stamm an ihrer Zweigstelle weiterleiten. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

- Wie groß ist jede Website (also, wie viele Benutzer sind für Enterprise-VoIP aktiviert)?

- Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?

Die Entscheidung zur Bereitstellung des zentralisierten oder verteilten SIP-Trunkings erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht notwendig ist. Bei einer vollständig zentralisierten Bereitstellung wird der gesamte Datenverkehr der Zweigstelle über WAN-Verbindungen weitergeleitet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, können Sie das verteilte SIP-Trunking verwenden. So können Sie beispielsweise einen Standard Edition-Server an einer Zweigstelle mit Föderations Standort an der zentralen Website bereitstellen, oder Sie möchten eine Survivable Branch-Appliance oder einen Überlebenden Branch-Server mit einem kleinen Gateway bereitstellen.

> [!NOTE]
> Details zum verteilten SIP-Trunking finden Sie unter [SIP-Trunking in der Zweigstelle in Skype for Business Server](branch-site.md).

### <a name="supported-sip-trunking-connection-types"></a>Unterstützte Verbindungstypen für das SIP-Trunking

Skype for Business Server unterstützt die folgenden Verbindungstypen für SIP-Trunking:

- Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird für andere Teilnehmer freigegeben, und jedem Datenpaket wird eine Beschriftung zugewiesen, um die Daten eines Abonnenten von einem anderen zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

- Eine private Verbindung ohne anderen Datenverkehr – beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung – stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

- Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit. Internet Verbindung ist die einzige SIP-Trunking-Verbindungsart für Skype for Business Server, für die VPN erforderlich ist.

#### <a name="selecting-a-connection-type"></a>Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

- Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

- Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).

- Für ein kleines Unternehmen oder eine Zweigstelle mit geringem Anrufaufkommen kann die SIP-Trunkierung über das Internet die beste Wahl sein. Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.

### <a name="bandwidth-requirements"></a>Erforderliche Bandbreite

Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (der Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:

Spitzenbandbreite für den SIP-Trunk = Max. gleichzeitige Anrufe x (64 KBit/s + Headergröße)

> [!NOTE]
> Die Headergröße beträgt maximal 20 Byte.

### <a name="codec-support"></a>Codec-Unterstützung

Skype for Business Server unterstützt nur die folgenden Codecs:

- G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)

- G.711 µ-Law (wird in Nordamerika eingesetzt)

### <a name="internet-telephony-service-provider"></a>Anbieter von Internettelefoniediensten

Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten. Informationen zur Bereitstellung erhalten Sie von Ihrem Dienstanbieter. Eine Liste der zertifizierten SIP-Trunking-Dienstanbieter finden Sie auf der [Microsoft Unified Communications Open Interoperability Program-Website](https://go.microsoft.com/fwlink/p/?LinkId=287029).

Ausführliche Informationen zu für Microsoft zertifizierten Anbietern von SIP-Trunking erhalten Sie bei Ihrem Microsoft-Ansprechpartner.

> [!IMPORTANT]
> Sie müssen einen für Microsoft zertifizierten Dienstanbieter nutzen, um sicherzustellen, dass Ihr Anbieter von Internettelefoniediensten sämtliche Funktionen unterstützt, die über den SIP-Trunk verarbeitet werden (z. B. das Einrichten und Verwalten von Sitzungen sowie die Unterstützung aller erweiterten VoIP-Dienste). Der technische Support von Microsoft kann nicht für Konfigurationen in Anspruch genommen werden, die nicht zertifizierte Anbieter verwenden. Wenn Sie gegenwärtig einen Internetdienstanbieter nutzen, der nicht für SIP-Trunking zertifiziert ist, können Sie diesen Anbieter weiterhin als ISP nutzen und sich für das SIP-Trunking für einen für Microsoft zertifizierten Anbieter entscheiden.

### <a name="topologies-and-components-for-sip-trunking"></a>Topologien und Komponenten für das SIP-Trunking

Die folgende Abbildung zeigt die SIP-Trunking-Topologie in Skype for Business Server.

**SIP-Trunking-Topologie**

![Topologie für das SIP-Trunking](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Wie in der Abbildung gezeigt wird das virtuelle private IP-Netzwerk (IP-VPN) für die Verbindungen zwischen dem Unternehmensnetzwerk und dem PSTN (Public Switched Telephone Network, Telefonfestnetz)-Dienstanbieter verwendet. Mit diesem privaten Netzwerk sollen IP-Verbindungen, erweiterte Sicherheit und (optional) Garantien für die Dienstqualität (Quality of Service, QoS) geboten werden. Aufgrund der Merkmale eines VPNs ist es nicht erforderlich, Transport Layer Security (TLS) für den SIP-Signaldatenverkehr oder Secure Real-Time Transport Protocol (SRTP) für den Mediendatenverkehr zu verwenden. Die Verbindungen zwischen dem Unternehmen und dem Dienstanbieter bestehen deshalb aus einfachen TCP-Verbindungen für SIP-Datenverkehr und einfachen Real-Time Transport Protocol (RTP)-Verbindungen (über UDP) für Mediendatenverkehr, der durch ein IP-VPN getunnelt werden kann. Stellen Sie sicher, dass alle Firewalls zwischen den VPN-Routern offene Ports aufweisen, damit die VPN-Router kommunizieren können. Zudem müssen die IP-Adressen der externen Edgeschnittstellen der VPN-Router öffentlich routingfähig sein.

> [!IMPORTANT]
> Kontaktieren Sie Ihren Dienstanbieter, um zu ermitteln, ob er Unterstützung für hohe Verfügbarkeit (einschließlich Failover) bietet. Wenn ja, müssen Sie die erforderlichen Vorgehensweisen zum Einrichten von hoher Verfügbarkeit ermitteln. Müssen Sie beispielsweise nur eine IP-Adresse und einen SIP-Trunk auf jedem Vermittlungsserver konfigurieren, oder müssen mehrere SIP-Stämme auf jedem Vermittlungsserver konfiguriert werden? > Wenn Sie über mehrere zentrale Websites verfügen, Fragen Sie auch, ob der Dienstanbieter Verbindungen zu und von einem anderen zentralen Standort aus aktivieren kann.

> [!NOTE]
> Für SIP-Trunking empfehlen wir dringend, eigenständige Vermittlungsserver bereitzustellen. Ausführliche Informationen finden Sie in der Bereitstellungsdokumentation unter [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Schützen des Vermittlungsservers für das SIP-Trunking

Aus Sicherheitsgründen sollten Sie ein virtuelles LAN (VLAN) für jede Verbindung zwischen den zwei VPN-Routern einrichten. Die tatsächliche Vorgehensweise zum Einrichten eines VLANs variiert abhängig vom Routerhersteller. Ausführliche Informationen erhalten Sie von Ihrem Routeranbieter.

Sie sollten die folgenden Richtlinie befolgen:

- Einrichten eines virtuellen LANs (VLAN) zwischen dem Vermittlungs Server und dem VPN-Router im Umkreisnetzwerk (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz).

- Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom Router in das VLAN zu.

- Blockieren Sie Routingregeln, die den Datenverkehr vom Router an eine beliebige Stelle, aber auf den Vermittlungs Server weiterleiten.

Bei Verwendung eines VPN-Servers sollten Sie die folgenden Richtlinien befolgen:

- Einrichten eines VLAN zwischen dem VPN-Server und dem Vermittlungsserver

- Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom VPN-Server in das VLAN zu.

- Blockieren Sie jede Routingregel, die den VPN-Server Datenverkehr an eine beliebige Stelle, aber den Vermittlungsserver weiterleitet.

- Verschlüsseln Sie Daten im VPN mithilfe von GRE (Generic Routing Encapsulation).

## <a name="see-also"></a>Siehe auch

[SIP-Trunking in der Zweigstelle in Skype for Business Server](branch-site.md)

