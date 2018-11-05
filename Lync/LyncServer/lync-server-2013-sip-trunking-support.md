---
title: 'Lync Server 2013: SIP-Trunking-Unterstützung'
TOCTitle: SIP-Trunking-Unterstützung
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399005(v=OCS.15)
ms:contentKeyID: 49295689
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# SIP-Trunking-Unterstützung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wenn Sie Enterprise-VoIP mit SIP-Trunking einsetzen möchten, müssen Sie einen Vermittlungsserver bereitstellen und dafür sorgen, dass andere Infrastrukturelemente und Komponenten die Supportanforderungen entsprechend Ihres Bereitstellungsmodells erfüllen. Ausführliche Informationen dazu, wie Sie feststellen können, ob Sie SIP-Trunking verwenden sollten, finden Sie unter [Übersicht über SIP-Trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in der Planungsdokumentation.

Über das Microsoft Unified Communications Open Interoperability Program für die Enterprise-Telefonieinfrastruktur können Sie qualifizierte PSTN-Gateways, IP-Nebenstellenanlagen und SIP-Trunking-Dienste finden, qualifizierte IP-Telefoniedienstanbieter eingeschlossen. Ausführliche Informationen hierzu finden Sie auf der Website des Microsoft Unified Communications Open Interoperability Program unter [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).

## Unterstützung eines Vermittlungsservers

Zur Implementierung des SIP-Trunkings müssen Sie die Verbindung über einen Vermittlungsserver routen, der als Proxy für Kommunikationssitzungen zwischen Lync Server 2013-Clients und dem Dienstanbieter fungiert. Der Vermittlungsserver entschlüsselt den Mediendatenverkehr von Clients und Servern und führt eine erneute Verschlüsselung durch, bevor die Daten an den Dienstanbieter gesendet werden. Die erneute Verschlüsselung ist erforderlich, da SIP-Trunks keine Unterstützung für einige Codecs wie z. B. die RTA- (Real Time Audio) oder ICE-Protokollaushandlung (Interactive Connectivity Establishment) für Firewallausnahmen bieten.

Jeder Vermittlungsserver kann über zwei Netzwerkkarten verfügen, die eine interne und externe Netzwerkschnittstelle bereitstellen. Die externe Schnittstelle wird allgemein als Gatewayschnittstelle bezeichnet, da sie traditionell zur Verbindung mit einem PSTN-Gateway oder einer IP-Nebenstellenanlage verwendet wird. Zur Implementierung eines SIP-Trunks verbinden Sie die externe Schnittstelle mit einem SBC (Session Border Controller) beim Dienstanbieter.

## Zentralisiertes und verteiltes SIP-Trunking im Vergleich

Beim *zentralisierten* SIP-Trunking wird der gesamte VoIP-Datenverkehr (Voice over Internet Protocol), einschließlich des Datenverkehrs von Zweigniederlassungen, über Ihr Rechenzentrum geroutet. Das zentralisierte Bereitstellungsmodell ist einfach, kosteneffizient und allgemein der bevorzugte Ansatz für die Implementierung von SIP-Trunks mit Lync Server 2013.

In Abhängigkeit von den Verwendungsmustern in Ihrem Unternehmen ist jedoch ein Routing aller Benutzer über den zentralisierten SIP-Trunk möglicherweise nicht erwünscht. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

  - Wie groß ist jeder Standort? Wie viele Benutzer sind vorhanden?

  - Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?

Das *verteilte* SIP-Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einer oder mehreren Zweigniederlassungen implementieren. Der VoIP-Datenverkehr wird anschließend von der Zweigniederlassung direkt an den zugehörigen Dienstanbieter geroutet, ohne über Ihr Rechenzentrum geleitet zu werden.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

  - Für die Zweigniederlassung muss Ausfallsicherheit gewährleistet werden (z. B. bei einem WAN-Ausfall). Wenn für die Zweigniederlassung Redundanz und Failover erforderlich sind, berechnet der Dienstanbieter höhere Gebühren, und die Konfiguration erfordert mehr Zeit. Diese Anforderung sollte für jede Zweigniederlassung geprüft werden. Für einige Zweigniederlassungen sind Redundanz und Failover möglicherweise erforderlich, während dies für andere Zweigniederlassungen nicht gilt.

  - Die Zweigniederlassung und das Rechenzentrum befinden sich in unterschiedlichen Ländern/Regionen. Aus Kompatibilitäts- und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region.

Die Entscheidung zur Bereitstellung des zentralisierten oder verteilten SIP-Trunkings erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht erforderlich ist. In einer vollständig zentralisierten Bereitstellung wird der gesamte Zweigniederlassungsdatenverkehr über WAN-Verbindungen geroutet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, möchten Sie möglicherweise das verteilte SIP-Trunking verwenden.


> [!NOTE]
> Ausführliche Informationen dazu, aus welchen Gründen und in welcher Weise Sie das SIP-Trunking verwenden könnten, finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">SIP-Trunking für Zweigstellenstandorte in Lync Server 2013</A> in der Planungsdokumentation.



## Unterstützte Verbindungstypen für das SIP-Trunking

Lync Server 2013 unterstützt die folgenden Verbindungstypen für das SIP-Trunking:

  - Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet, und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

  - Eine private Verbindung ohne anderen Datenverkehr ist im Allgemeinen die zuverlässigste und sicherste Form der Verbindung (beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung). Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

  - Das öffentliche Internet ist der günstigste Verbindungstyp, bietet jedoch auch die geringste Zuverlässigkeit und Anrufkapazität. Ihr Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP) kann diesen SIP-Trunkverbindungstyp sichern helfen, wenn er TLS (Transport Layer Security) und SRTP (Secure Real-Time Transport Protocol) für die Verschlüsselung von Signaldaten und Mediendatenverkehr unterstützt. Wenn Sie eine SIP-Trunkverbindung über das Internet nicht für die Verwendung von TLS und SRTP konfigurieren können, wird dringend empfohlen, einen VPN-Tunnel zu verwenden, um eine sicherere Verbindung zu gewährleisten. Erkundigen Sie sich bei Ihrem Dienstanbieter, ob er TLS mit SRTP unterstützt.

## Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

  - Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk im Allgemeinen den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

  - Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung oder eine T1-Leitung.

  - Für ein kleines Unternehmen oder eine kleine Zweigniederlassung mit niedrigem Anrufaufkommen kann ein SIP-Trunking über das Internet die beste Möglichkeit darstellen. Dieser Verbindungstyp wird jedoch für mittelständische oder größere Standorte nicht empfohlen.

## Codec-Unterstützung

Der Dienstanbieterproxy muss die folgenden Codecs unterstützen:

  - G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)

  - G.711 µ-Law (wird in Nordamerika verwendet)

