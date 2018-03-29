---
title: SIP-Trunking in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Erfahren Sie mehr über SIP-Trunking in Skype für Business Server Enterprise-VoIP
ms.openlocfilehash: 434e013e2ee7d0d6736b39546ba7921aa15cdee3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="sip-trunking-in-skype-for-business-server-2015"></a>SIP-Trunking in Skype for Business Server 2015
 
Erfahren Sie mehr über SIP-Trunking in Skype für Business Server Enterprise-VoIP
  
SIP (Session Initiation Protocol) wird zum Initiieren und Verwalten von VoIP-Kommunikationssitzungen (Voice over IP) für grundlegende Telefondienste und zusätzliche Echtzeitkommunikationsdienste wie Chats, Konferenzfunktionen, Anwesenheitserkennung und Multimediafunktionen verwendet. Dieser Abschnitt enthält Informationen zur Planung für die Implementierung von SIP-Trunks, eine Art von SIP-Verbindung, die über die Grenze der Ihr lokales Netzwerk erweitert.
  
## <a name="what-is-sip-trunking"></a>Was ist SIP-Trunking?

Bei einem SIP-Trunk handelt es sich um eine IP-Verbindung für die SIP-Kommunikation zwischen Ihrer Organisation und einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP), die über Ihre Firewall hinausgeht. In der Regel wird ein SIP-Trunk eines ITSP Ihrer Organisation zentralen Standort herstellen. In einigen Fällen können Sie das SIP-Trunking auch zum Verbinden einer Zweigstelle mit einem ITSP nutzen.
  
Bereitstellen von SIP-Trunking kann ein großer Schritt in Richtung Ihrer Organisation Telekommunikation vereinfachen und zur Vorbereitung auf dem neuesten Stand Verbesserungen an Echtzeitkommunikation sein. Die wichtigsten Vorteile des SIP-Trunking ist, dass Sie Ihre Organisation Verbindungen mit dem öffentlichen Telefonfestnetz (PSTN) an einen zentralen Standort, im Gegensatz zum Vorgänger Time Division multiplexing (TDM) Trunking, konsolidieren können die in der Regel erfordert einen separaten Trunk aus jeder Zweigstellenstandort.
  
### <a name="cost-savings"></a>Kosteneinsparung

Die mit dem SIP-Trunking verbundene Kosteneinsparung kann erheblich sein:
  
- Die Kosten für Ferngespräche sind bei Verwendung eines SIP-Trunks in der Regel deutlich niedriger.
    
- Sie können die Verwaltungskosten senken und die Komplexität der Bereitstellung verringern.
    
- Gebühren für Basisanschlüsse (Basic Rate Interface, BRI) und Primärmultiplexanschlüsse (Primary Rate Interface, PRI) entfallen, wenn Sie eine deutlich günstigere Direktverbindung zwischen einem SIP-Trunk und Ihrem Anbieter von Internettelefoniediensten (ITSP) konfigurieren. Beim TDM-Trunking rechnen Dienstanbieter Anrufe pro Minute ab. Die Kosten für das SIP-Trunking können auf der Bandbreitennutzung basieren, die Sie in kleineren, wirtschaftlicheren Einheiten erwerben können. (Die tatsächlichen Kosten richten sich nach dem Servicemodell des jeweiligen Anbieters von Internettelefoniediensten (ITSP).)
    
#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP-Trunking im Vergleich zum Hosting eines PSTN-Gateways oder einer IP-Nebenstellenanlage

Da SIP-Trunks eine direkte Verbindung mit dem Dienstanbieter herstellen, entfallen Ihre PSTN-Gateways und die damit verbundenen Verwaltungskosten sowie die Komplexität dieser Lösung. Die Verwendung von SIP-Trunks kann durch einen geringeren Wartungs- und Verwaltungsaufwand zu einer erheblichen Kosteneinsparung beitragen. 
  
### <a name="expanded-voip-services"></a>Erweiterte VoIP-Dienste

VoIP-Funktionen sind häufig die wichtigste Motivation für die Bereitstellung von SIP-Trunking, die VoIP-Unterstützung stellt jedoch nur den ersten Schritt dar. Mit SIP-Trunking können Sie VoIP-Funktionen erweitern und Skype für Business Server übermitteln eine umfangreichere Dienste zu aktivieren. Beispiel:
  
- Die erweiterte anwesenheitserkennung für Geräte, die nicht Skype für Business Server ausgeführt wird, kann eine bessere Integration für Mobiltelefone, sodass Sie sehen, wenn ein Benutzer ein Gespräch über ein Mobiltelefon bereitstellen.
    
- E9-1-1-notrufdienste ermöglichen es die Behörden, die zum Ermitteln des Standorts von seinem Telefonnummer des Anrufers 911-Anrufe entgegennehmen.
    
> [!NOTE]
> Erkundigen Sie sich bei Ihrem ITSP, welche Dienste unterstützt werden und für Ihre Organisation aktiviert werden können. 
  
### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP-Trunks und direkte SIP-Verbindungen im Vergleich

Der Begriff Trunk wird von leitungsvermittelte Technologie abgeleitet. Er bezieht sich auf eine dedizierte physische Leitung zur Verbindung von Telefonvermittlungsanlagen. Wie ihre Vorgänger, Time-Division multiplexing (TDM)-Trunks SIP-Trunks Verbindungen zwischen zwei unterschiedliche SIP-Netzwerke sind – die Skype für Enterprise Business Server und dem ITSP. Im Gegensatz zu leitungsvermittelten Trunks handelt es sich bei SIP-Trunks um virtuelle Verbindungen, die über jeden der unterstützten Typen von SIP-Trunkingverbindungen hergestellt werden können.
  
Bei direkten SIP-Verbindungen hingegen handelt es sich um SIP-Verbindungen, die nicht über die Grenzen des lokalen Netzwerks hinausgehen (das heißt, es wird eine Verbindung mit einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz) oder einer Nebenstellenanlage (Private Branch Exchange, PBX) innerhalb des internen Netzwerks hergestellt). Informationen dazu, wie Sie die direkte SIP-Verbindungen mit Skype für Business Server verwenden können finden Sie unter [Direct SIP Connections in Skype für Business Server 2015](direct-sip.md). 
  
## <a name="how-do-i-implement-sip-trunking"></a>Implementierung von SIP-Trunking

Um SIP-Trunking zu implementieren, müssen Sie die Verbindung über einen Vermittlungsserver weiterleiten die fungiert als Proxy für kommunikationssitzungen zwischen Skype für Business Server-Clients und dem Dienstanbieter und transcodiert Medien, bei Bedarf.
  
Jeder Vermittlungsserver verfügt über eine interne Netzwerkschnittstelle und externe Netzwerkschnittstelle. Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern. Die externe Schnittstelle ist häufig die Gatewayschnittstelle bezeichnet, da es bisher verwendet wurde, um ein Gateway public switched Telephone Network, (PSTN) oder eine IP-Nebenstellenanlage des Vermittlungsservers herstellen. Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle des Vermittlungsservers und die externe edgekomponente des ITSP. Die externe Edgekomponente des ITSP könnte ein Session Border Controller (SBC), ein Router oder ein Gateway sein.
  
Ausführliche Informationen zu Vermittlungsservern finden Sie unter [Mediation Server Component in Skype für Business Server 2015](mediation-server.md). 
  
### <a name="centralized-vs-distributed-sip-trunking"></a>Zentralisiertes und verteiltes SIP-Trunking im Vergleich

Zentralisierte SIP-Trunking leitet alle VoIP-Datenverkehr, einschließlich Branch-Site-Datenverkehr durch Ihre zentralen Standort. Das zentrale Bereitstellungsmodell ist einfache und kostengünstige und ist im Allgemeinen empfiehlt es sich für die Implementierung von SIP-Trunks mit Skype für Business Server.
  
Verteiltes SIP-Trunking ist ein Bereitstellungsmodell, in dem Sie lokale SIP-Trunks an einen oder mehrere Zweigniederlassungen implementieren. VoIP-Datenverkehr wird aus den Zweigstellenstandort klicken Sie dann direkt mit einem Dienstanbieter weitergeleitet, ohne den Umweg über den zentralen Standort verwendet wird.
  
Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich: 
  
- Die Zweigniederlassung erfordert survivable Telefon Connectivity (z. B., wenn das WAN ausfällt). Dies sollte für jeden Zweigstellenstandort analysiert werden; Einige Ihrer Zweigstellen erfordern Redundanz und Failover, während andere Benutzer nicht können.
    
- Resiliency ist zwischen zwei zentralen Standorten erforderlich. Sie müssen sicherstellen, dass bei jeder zentrale Standort ein SIP-Trunk endet. Beispielsweise ist nicht möglich, wenn Sie Dublin und Tukwila zentrale Standorten und beide nur eine Site SIP-Trunk, verwendet Wenn der Trunk ausfällt, die andere Website Benutzer PSTN-Anrufe tätigen.
    
- Der Zweigstelle und dem zentralen Standort befinden sich in verschiedenen Ländern/Regionen. Kompatibilität und rechtlichen Gründen benötigen Sie mindestens eine SIP-Trunk pro Land/Region. Beispielsweise kann nicht in der Europäischen Union Communications eine Land/Region ohne verlassen lokal an einem zentralen Punkt beendet.
    
Je nach der geografischen Standort von Websites und wie viel Datenverkehr Sie innerhalb Ihres Unternehmens erwarten Sie möglicherweise nicht alle Benutzer über die Zentraladministration SIP-Trunk weiterleiten möchten, oder Sie entscheiden können, so, dass einige Benutzer über einen SIP-Trunk an ihre Zweigstellenstandort weitergeleitet. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:
  
- Wie groß ist jeder Standort (d. h., wie viele Benutzer für Enterprise Voice aktiviert sind)? 
    
- Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe? 
    
Die Entscheidung zur Bereitstellung des zentralisierten oder verteilten SIP-Trunkings erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht notwendig ist. Bei einer Bereitstellung vollständig zentralisierte wird alle Branch Site Datenverkehr über WAN-Verbindungen weitergeleitet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, können Sie das verteilte SIP-Trunking verwenden. Angenommen, Sie Standard Edition-Server an einem Zweigstellenstandort mit verbunden am zentralen Standort bereitstellen möchten, oder Sie eine Survivable Branch Appliance oder einen Survivable Branch Server mit einem kleinen Gateway bereitstellen möchten.
  
> [!NOTE]
> Ausführliche Informationen zum verteilten SIP-Trunking finden Sie unter [Branch Site SIP-Trunking in Skype für Business Server 2015](branch-site.md). 
  
### <a name="supported-sip-trunking-connection-types"></a>Unterstützte Verbindungstypen für das SIP-Trunking

Skype für Business Server unterstützt die folgenden Verbindungstypen für das SIP-Trunking:
  
- Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk an andere Abonnenten freigegeben und jedes Datenpaket erhält eine Beschriftung ein Abonnent Daten von einer anderen Person zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.
    
- Eine private Verbindung ohne anderen Datenverkehr – beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung – stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.
    
- Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit. Verbindung mit dem Internet ist die einzige Skype für Business Server-SIP-Trunking Verbindungstyp, die VPN benötigt.
    
#### <a name="selecting-a-connection-type"></a>Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.
  
- Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.
    
- Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).
    
- Für eine kleine Unternehmen oder Zweigstellenstandort mit geringer Anrufvolumen möglicherweise SIP-Trunking über das Internet die beste Wahl. Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.
    
### <a name="bandwidth-requirements"></a>Erforderliche Bandbreite

Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (der Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:
  
Spitzenbandbreite für den SIP-Trunk = Max. gleichzeitige Anrufe x (64 KBit/s + Headergröße)
  
> [!NOTE]
> Die Headergröße beträgt maximal 20 Byte. 
  
### <a name="codec-support"></a>Codec-Unterstützung

Skype für Business Server unterstützt nur die folgenden Codecs:
  
- G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)
    
- G.711 µ-Law (wird in Nordamerika eingesetzt)
    
### <a name="internet-telephony-service-provider"></a>Anbieter von Internettelefoniediensten

Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten. Informationen zur Bereitstellung erhalten Sie von Ihrem Dienstanbieter. Eine Liste mit zertifizierten SIP-Trunking-Dienstanbieter finden Sie unter [Microsoft Unified Communications Open Interoperability Program-Website](https://go.microsoft.com/fwlink/p/?LinkId=287029).
  
Ausführliche Informationen zu für Microsoft zertifizierten Anbietern von SIP-Trunking erhalten Sie bei Ihrem Microsoft-Ansprechpartner.
  
> [!IMPORTANT]
> Sie müssen einen für Microsoft zertifizierten Dienstanbieter nutzen, um sicherzustellen, dass Ihr Anbieter von Internettelefoniediensten sämtliche Funktionen unterstützt, die über den SIP-Trunk verarbeitet werden (z. B. das Einrichten und Verwalten von Sitzungen sowie die Unterstützung aller erweiterten VoIP-Dienste). Der technische Support von Microsoft kann nicht für Konfigurationen in Anspruch genommen werden, die nicht zertifizierte Anbieter verwenden. Wenn Sie gegenwärtig einen Internetdienstanbieter nutzen, der nicht für SIP-Trunking zertifiziert ist, können Sie diesen Anbieter weiterhin als ISP nutzen und sich für das SIP-Trunking für einen für Microsoft zertifizierten Anbieter entscheiden. 
  
### <a name="topologies-and-components-for-sip-trunking"></a>Topologien und Komponenten für das SIP-Trunking

Die folgende Abbildung zeigt die Topologie für das SIP-Trunking in Skype für Business Server.
  
**SIP-Trunking-Topologie**

![Topologie für das SIP-Trunking](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)
  
Wie in der Abbildung gezeigt wird das virtuelle private IP-Netzwerk (IP-VPN) für die Verbindungen zwischen dem Unternehmensnetzwerk und dem PSTN (Public Switched Telephone Network, Telefonfestnetz)-Dienstanbieter verwendet. Mit diesem privaten Netzwerk sollen IP-Verbindungen, erweiterte Sicherheit und (optional) Garantien für die Dienstqualität (Quality of Service, QoS) geboten werden. Aufgrund der Merkmale eines VPNs ist es nicht erforderlich, Transport Layer Security (TLS) für den SIP-Signaldatenverkehr oder Secure Real-Time Transport Protocol (SRTP) für den Mediendatenverkehr zu verwenden. Die Verbindungen zwischen dem Unternehmen und dem Dienstanbieter bestehen deshalb aus einfachen TCP-Verbindungen für SIP-Datenverkehr und einfachen Real-Time Transport Protocol (RTP)-Verbindungen (über UDP) für Mediendatenverkehr, der durch ein IP-VPN getunnelt werden kann. Stellen Sie sicher, dass alle Firewalls zwischen den VPN-Routern offene Ports aufweisen, damit die VPN-Router kommunizieren können. Zudem müssen die IP-Adressen der externen Edgeschnittstellen der VPN-Router öffentlich routingfähig sein.
  
> [!IMPORTANT]
> Kontaktieren Sie Ihren Dienstanbieter, um zu ermitteln, ob er Unterstützung für hohe Verfügbarkeit (einschließlich Failover) bietet. Wenn ja, müssen Sie die erforderlichen Vorgehensweisen zum Einrichten von hoher Verfügbarkeit ermitteln. Beispielsweise müssen Sie nur eine IP-Adresse und eine SIP-Trunk auf jedem Vermittlungsserver konfigurieren, oder möchten Sie mehrere SIP-Trunks auf jedem Vermittlungsserver konfigurieren? > Wenn Sie mehrere zentrale Standorte verfügen, Fragen Sie auch, ob der Dienstanbieter die Verbindungen zu und von einem anderen zentralen Standort aktivieren kann. 
  
> [!NOTE]
> SIP-Trunking wird dringend empfohlen, dass Sie den eigenständigen Vermittlungsserver bereitstellen. Weitere Informationen hierzu finden Sie unter [Bereitstellen von Vermittlungsservern und Definieren von Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) in der Bereitstellungsdokumentation.
  
### <a name="securing-the-mediation-server-for-sip-trunking"></a>Schützen des Vermittlungsservers für das SIP-Trunking

Aus Sicherheitsgründen sollten Sie ein virtuelles LAN (VLAN) für jede Verbindung zwischen den zwei VPN-Routern einrichten. Die tatsächliche Vorgehensweise zum Einrichten eines VLANs variiert abhängig vom Routerhersteller. Ausführliche Informationen erhalten Sie von Ihrem Routeranbieter.
  
Sie sollten die folgenden Richtlinie befolgen:
  
- Legen Sie ein virtuelles LAN (VLAN) zwischen dem Vermittlungsserver und dem VPN-Router im Umkreisnetzwerk (auch als DMZ, demilitarisierte Zone und überwachtes Subnetz bezeichnet).
    
- Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom Router in das VLAN zu.
    
- Blockieren Sie alle Routingregeln, die Datenverkehr vom Router an ein anderes weiterleiten, aber der Vermittlungsserver.
    
Bei Verwendung eines VPN-Servers sollten Sie die folgenden Richtlinien befolgen:
  
- Richten Sie ein VLAN zwischen dem VPN-Server und dem Vermittlungsserver.
    
- Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom VPN-Server in das VLAN zu.
    
- Blockieren Sie alle Routingregeln, mit dem VPN-Server-Datenverkehr an ein anderes weitergeleitet, aber der Vermittlungsserver.
    
- Verschlüsseln Sie Daten im VPN mithilfe von GRE (Generic Routing Encapsulation).
    
## <a name="see-also"></a>Siehe auch

#### 

[Branch Site SIP-Trunking in Skype für Business Server 2015](branch-site.md)

