---
title: 'Lync Server 2013: Implementierung von SIP-Trunking'
TOCTitle: Implementierung von SIP-Trunking
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425743(v=OCS.15)
ms:contentKeyID: 49293475
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementierung von SIP-Trunking in Lync Server 2013?

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zur Implementierung des SIP-Trunkings müssen Sie die Verbindung über einen Vermittlungsserver routen, der als Proxy für Kommunikationssitzungen zwischen Lync Server 2013-Clients und dem Dienstanbieter fungiert und ggf. eine Medientranscodierung durchführt.

Jeder Vermittlungsserver verfügt über eine interne und eine externe Netzwerkschnittstelle. Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern her. Die externe Schnittstelle wird häufig als Gatewayschnittstelle bezeichnet, da sie traditionell zur Verbindungsherstellung zwischen dem Vermittlungsserver und einem PSTN-Gateway oder einer IP-Nebenstellenanlage dient. Zur Implementierung eines SIP-Trunks verbinden Sie die externe Schnittstelle des Vermittlungsservers mit der externen Edgekomponente des Anbieters von Internettelefoniediensten (Internet Telephony Service Provider, ITSP).


> [!NOTE]
> Die externe Edgekomponente des ITSP kann ein SBC (Session Border Controller), ein Router oder ein Gateway sein.



Ausführliche Informationen zu Vermittlungsserver finden Sie unter [Vermittlungsserverkomponente in Lync Server 2013](lync-server-2013-mediation-server-component.md).

## Zentralisiertes und verteiltes SIP-Trunking im Vergleich

Beim *zentralisierten* SIP-Trunking wird der gesamte VoIP-Datenverkehr (Voice over IP), einschließlich des Datenverkehrs von Zweigstellenstandorten, über Ihren zentraler Standort geroutet. Das zentralisierte Bereitstellungsmodell ist einfach, kosteneffizient und allgemein der empfohlene Ansatz für die Implementierung von SIP-Trunks mit Lync Server 2013.

Das *verteilte* SIP-Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einem oder mehreren Zweigstellenstandorten implementieren. Der VoIP-Datenverkehr wird anschließend von der Zweigstelle direkt und ohne Umweg über den zentraler Standort an einen Dienstanbieter geroutet.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

  - Für die Zweigstelle muss Ausfallsicherheit gewährleistet werden (z. B. bei einem WAN-Ausfall). Diese Anforderung muss für jede Zweigstelle untersucht werden: Für einige Zweigstellen sind Redundanz und Failover möglicherweise erforderlich, während dies für andere Zweigstellen nicht gilt.

  - Zwischen zwei zentraler Standorte ist Ausfallsicherheit erforderlich. Sie müssen sicherstellen, dass der SIP-Trunk an jedem zentraler Standort terminiert wird. Wenn Sie beispielsweise über die zentraler Standorte Dublin und Tukwila verfügen und beide nur den SIP-Trunk eines Standorts verwenden, können die Benutzer am jeweils anderen Standort bei Ausfall des Trunks keine PSTN-Anrufe tätigen.

  - Die Zweigstellen und zentraler Standorte befinden sich in unterschiedlichen Ländern/Regionen. Aus Kompatibilitäts- und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region. In der Europäischen Union beispielsweise dürfen Kommunikationsdaten ein Land bzw. eine Region nicht verlassen, ohne lokal an einem zentralen Punkt terminiert zu werden.

Je nach geografischer Lage der Standorte und abhängig davon, wie viel Datenverkehr innerhalb Ihres Unternehmens erwartet wird, möchten Sie vielleicht nicht alle Benutzer über den zentralen SIP-Trunk routen, oder das Routing einiger Benutzer soll über einen SIP-Trunk an der jeweiligen Zweigstelle erfolgen. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

  - Wie groß ist jeder Standort (d. h., wie viele Benutzer sind für Enterprise-VoIP aktiviert)?

  - Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?

Die Entscheidung zur Bereitstellung des zentralisierten oder verteilten SIP-Trunkings erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht notwendig ist. In einer vollständig zentralisierten Bereitstellung wird der gesamte Zweigstellendatenverkehr über WAN-Verbindungen geroutet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, möchten Sie möglicherweise das verteilte SIP-Trunking verwenden. Sie können beispielsweise einen Standard Edition-Server an der Zweigstelle bereitstellen und einen Partnerverbund mit dem zentralen Standort einrichten, oder Sie möchten vielleicht eine Survivable Branch-Anwendung oder einen Survivable Branch-Server mit einem kleinen Gateway bereitstellen.


> [!NOTE]
> Ausführliche Informationen zum verteilten SIP-Trunking finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">SIP-Trunking für Zweigstellenstandorte in Lync Server 2013</A>.



## Unterstützte Verbindungstypen für das SIP-Trunking

Lync Server unterstützt die folgenden Verbindungstypen für das SIP-Trunking:

  - Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet, und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

  - Eine private Verbindung ohne anderen Datenverkehr - beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung - stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

  - Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit. Die Internetverbindung ist der einzige Verbindungstyp für das Lync Server-SIP-Trunking, für den ein VPN benötigt wird.

## Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

  - Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

  - Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).

  - Für ein kleines Unternehmen oder eine Zweigstelle mit niedrigem Anrufaufkommen kann ein SIP-Trunking über das Internet die beste Option darstellen. Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.

## Erforderliche Bandbreite

Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (die Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:

Spitzenbandbreite für den SIP-Trunk = Max. gleichzeitige Anrufe x (64 KBit/s + Headergröße)


> [!NOTE]
> Die Headergröße beträgt maximal 20&nbsp;Byte.



## Codec-Unterstützung

Lync Server 2013 unterstützt ausschließlich die folgenden Codecs:

  - G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)

  - G.711 µ-Law (wird in Nordamerika verwendet)

## Anbieter von Internettelefoniediensten

Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten. Informationen zur Bereitstellung erhalten Sie von Ihrem Dienstanbieter. Eine Liste mit zertifizierten Dienstanbietern von SIP-Trunking finden Sie auf der [Website für das Microsoft Unified Communications Open Interoperability Program](http://go.microsoft.com/fwlink/?linkid=287029).

Ausführliche Informationen zu für Microsoft zertifizierten Anbietern von SIP-Trunking erhalten Sie bei Ihrem Microsoft-Ansprechpartner.


> [!IMPORTANT]
> Sie müssen einen für Microsoft zertifizierten Dienstanbieter nutzen, um sicherzustellen, dass Ihr Anbieter von Internettelefoniediensten sämtliche Funktionen unterstützt, die über den SIP-Trunk verarbeitet werden (z.&nbsp;B. das Einrichten und Verwalten von Sitzungen sowie die Unterstützung aller erweiterten VoIP-Dienste). Der technische Support von Microsoft kann nicht für Konfigurationen in Anspruch genommen werden, die nicht zertifizierte Anbieter verwenden. Wenn Sie gegenwärtig einen Internetdienstanbieter nutzen, der nicht für SIP-Trunking zertifiziert ist, können Sie diesen Anbieter weiterhin als ISP nutzen und sich für das SIP-Trunking für einen für Microsoft zertifizierten Anbieter entscheiden.


