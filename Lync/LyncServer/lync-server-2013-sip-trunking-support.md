---
title: Lync Server 2013 Unterstützung für SIP-Trunking
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31159a2d14facbdfed2f74f3567081699a7bde9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Unterstützung für SIP-Trunking in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Wenn Sie Enterprise-VoIP mit SIP-Trunking verwenden möchten, müssen Sie eine Vermittlungsserver bereitstellen und sicherstellen, dass andere Infrastrukturen und Komponenten die für Ihr Bereitstellungsmodell geeigneten Supportanforderungen erfüllen. Ausführliche Informationen zum ermitteln, ob SIP-Trunking implementiert werden soll, finden Sie unter [Overview of SIP Trunking in lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in der Planungsdokumentation.

Sie können das Microsoft Unified Communications Open Interoperability-Programm für die Enterprise-Telefonie-Infrastruktur verwenden, um qualifizierte PSTN-Gateways (Public Switched Telephone Network), IP-Nebenstellenanlagen und SIP-Trunking-Dienste, einschließlich qualifizierter IP-Telefonie, zu finden. Dienstanbieter. Ausführliche Informationen finden Sie auf [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)der Website Microsoft Unified Communications Open Interoperability Program unter.

<div>

## <a name="mediation-server-support"></a>Unterstützung eines Vermittlungsservers

Zum Implementieren des SIP-trunkings müssen Sie die Verbindung über eine Vermittlungsserver weiterleiten, die als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert. Der Vermittlungsserver entschlüsselt den Mediendatenverkehr von Clients und Servern und führt eine erneute Verschlüsselung durch, bevor die Daten an den Dienstanbieter gesendet werden. Die erneute Codierung wird benötigt, da SIP-Trunks einige verwendete Codecs nicht unterstützen, beispielsweise Real Time Audio (RTA) oder Ice-Protokoll Aushandlung (Interactive Connectivity Establishment) für die Firewall-Durchquerung.

Jeder Vermittlungsserver kann über zwei Netzwerkkarten verfügen, die eine interne und externe Netzwerkschnittstelle bereitstellen. Die externe Schnittstelle wird häufig als Gateway-Schnittstelle bezeichnet, da Sie traditionell verwendet wurde, um eine Verbindung mit einem PSTN-Gateway oder einer IP-Nebenstellenanlage herzustellen. Zur Implementierung eines SIP-Trunks verbinden Sie die externe Schnittstelle mit einem SBC (Session Border Controller) beim Dienstanbieter.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Zentralisiertes und verteiltes SIP-Trunking im Vergleich

*Zentralisiert* Mit SIP-Trunking werden alle VoIP-Datenverkehr (Voice over Internet Protocol), einschließlich des Datenverkehrs in der Zweigstelle, über das Rechenzentrum weitergeleitet. Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und stellt im Allgemeinen den bevorzugten Ansatz für die Implementierung von SIP-Trunks mit lync Server 2013 dar.

In Abhängigkeit von den Verwendungsmustern in Ihrem Unternehmen ist jedoch ein Routing aller Benutzer über den zentralisierten SIP-Trunk möglicherweise nicht erwünscht. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

  - Wie groß ist jeder Standort? Wie viele Benutzer sind vorhanden?

  - Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?

Das *verteilte* SIP-Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einem oder mehreren Zweigstellenstandorten implementieren. Der VoIP-Datenverkehr wird anschließend vom Zweigstellenstandort direkt an den zugehörigen Dienstanbieter geroutet, ohne über Ihr Rechenzentrum geleitet zu werden.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

  - Für den Zweigstellenstandort muss Ausfallsicherheit gewährleistet werden (beispielsweise bei einem WAN-Ausfall). Wenn für die Zweigstelle Redundanz und Failover erforderlich sind, berechnet der Dienstanbieter höhere Gebühren, und die Konfiguration erfordert mehr Zeit. Diese Anforderung sollte für jeden Zweigstellenstandort geprüft werden. Einige ihrer Zweigstellen benötigen möglicherweise Redundanz und Failover, andere möglicherweise nicht.

  - Der Zweigstellenstandort und das Rechenzentrum befinden sich in unterschiedlichen Ländern/Regionen. Aus Kompatibilitäts- und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region.

Für die Entscheidung, ob zentralisiertes oder verteiltes SIP-Trunking bereitgestellt werden soll, ist eine Kosten-Nutzen-Analyse erforderlich. In einigen Fällen kann es vorteilhaft sein, sich für den verteilten Bereitstellungsmodus zu entscheiden, auch wenn dies nicht erforderlich ist. In einer vollständig zentralisierten Bereitstellung wird der gesamte Zweigstellendatenverkehr über WAN-Verbindungen geroutet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, möchten Sie möglicherweise das verteilte SIP-Trunking verwenden.

<div>


> [!NOTE]  
> Ausführliche Informationen dazu, warum und wie Sie verteilte SIP-Trunking verwenden können, finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">Branch Site SIP Trunking in lync Server 2013</A> in der Planungsdokumentation.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Unterstützte Verbindungstypen für das SIP-Trunking

Lync Server 2013 unterstützt die folgenden Verbindungstypen für das SIP-Trunking:

  - Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet, und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

  - Eine private Verbindung ohne anderen Datenverkehr ist im Allgemeinen die zuverlässigste und sicherste Form der Verbindung (beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung). Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

  - Das öffentliche Internet ist der günstigste Verbindungstyp, bietet jedoch auch die geringste Zuverlässigkeit und Anrufkapazität. Ihr Internet Telefonie-Dienstanbieter (ITSP) kann diesen SIP-Trunk-Verbindungstyp schützen, wenn er TLS (Transport Layer Security) und SRTP (Secure Real-Time Transport Protocol) unterstützt, um Signal-und Mediendatenverkehr zu verschlüsseln. Wenn Sie eine SIP-Trunkverbindung über das Internet nicht für die Verwendung von TLS und SRTP konfigurieren können, wird dringend empfohlen, einen VPN-Tunnel zu verwenden, um eine sicherere Verbindung zu gewährleisten. Erkundigen Sie sich bei Ihrem Dienstanbieter, ob er TLS mit SRTP unterstützt.

<div>

## <a name="selecting-a-connection-type"></a>Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

  - Für ein mittelständisches oder größeres Unternehmen bietet ein MPLS-Netzwerk im Allgemeinen den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

  - Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung oder eine T1-Leitung.

  - Bei einem kleinen Unternehmen oder Zweigstellenstandort mit niedrigem Anrufvolumen ist die SIP-Trunkierung über das Internet möglicherweise die beste Wahl. Dieser Verbindungstyp wird jedoch nicht für mittelgroße oder größere Websites empfohlen.

</div>

</div>

<div>

## <a name="codec-support"></a>Codec-Unterstützung

Der Dienstanbieterproxy muss die folgenden Codecs unterstützen:

  - G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)

  - G.711 µ-Law (wird in Nordamerika verwendet)

</div>

</div>

<span> </span>

</div>

</div>

</div>

