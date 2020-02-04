---
title: 'Lync Server 2013: SIP-Trunking-Unterstützung'
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
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>SIP-Trunking-Unterstützung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Wenn Sie Enterprise-VoIP mit SIP-Trunking verwenden möchten, müssen Sie einen Vermittlungs Server bereitstellen und sicherstellen, dass andere Infrastrukturen und Komponenten die für Ihr Bereitstellungsmodell geeigneten Supportanforderungen erfüllen. Details zum ermitteln, ob SIP-Trunking implementiert werden soll, finden Sie unter [Übersicht über SIP-Trunking in lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in der Planungsdokumentation.

Sie können das offene Interoperabilitäts Programm Microsoft Unified Communications für die Enterprise-Telefonie-Infrastruktur verwenden, um qualifizierte PSTN-Gateways (Public Switched Telephone Network), IP-PBX-Anlagen und SIP-Trunking-Dienste, einschließlich qualifizierter IP-Telefonie, zu finden. Dienstanbieter. Ausführliche Informationen finden Sie auf [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)der Microsoft Unified Communications Open Interoperability Program-Website unter.

<div>

## <a name="mediation-server-support"></a>Vermittlungs Server Unterstützung

Um SIP-Trunking zu implementieren, müssen Sie die Verbindung über einen Vermittlungs Server weiterleiten, der als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert. Der Vermittlungs Server dekodiert den Mediendatenverkehr von Clients und Servern und codiert ihn erneut, bevor er an den Dienstanbieter gesendet wird. Die erneute Codierung ist erforderlich, da SIP-Trunks einige verwendete Codecs nicht unterstützen, wie etwa Echtzeit-Audio (RTA) oder Interaktions Einrichtung (ICE) Protocol Negotiation für die Firewall-Durchquerung.

Jeder Vermittlungs Server kann über zwei Netzwerkadapter verfügen, die eine interne und eine externe Netzwerkschnittstelle bereitstellen. Die externe Schnittstelle wird gemeinhin als Gateway-Schnittstelle bezeichnet, da Sie üblicherweise für die Verbindung mit einem PSTN-Gateway oder einer IP-PBX-Anlage verwendet wurde. Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle mit einem Session Border Controller (SBC) bei einem Dienstanbieter.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Zentralisiertes und verteiltes SIP-Trunking im Vergleich

*Zentralisiert* SIP-Trunking leitet den gesamten VoIP-Datenverkehr (einschließlich Zweigstellen-Websitedatenverkehr) über Ihr Rechenzentrum weiter. Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und im Allgemeinen der bevorzugte Ansatz für die Implementierung von SIP-Stämmen mit lync Server 2013.

Je nach Verwendungsmustern in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralisierten SIP-Stamm weiterleiten. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

  - Wie groß ist jede Website? Wie viele Benutzer?

  - Welche direkten Durchwahlnummern (DID) an jedem Standort erhalten die meisten Telefonanrufe?

*Verteilte* SIP Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einer oder mehreren Zweigstellen implementieren. VoIP-Datenverkehr wird dann direkt von der Verzweigungs Website an Ihren Dienstanbieter weitergeleitet, ohne Ihr Rechenzentrum zu durchlaufen.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

  - Die Verzweigungs Website erfordert eine überlebensfähige Telefonverbindung (beispielsweise, wenn das WAN ausfällt). Wenn für die Verzweigung Redundanz und Failover erforderlich sind, berechnet der Dienstanbieter mehr, und die Konfiguration wird länger dauern. Dies sollte für jede Verzweigungs Website analysiert werden. Einige ihrer Zweigstellen erfordern möglicherweise Redundanz und Failover, während andere möglicherweise nicht.

  - Die Verzweigungs Website und das Rechenzentrum befinden sich in verschiedenen Ländern/Regionen. Aus Kompatibilitäts-und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region.

Die Entscheidung, ob eine zentralisierte oder verteilte SIP-Trunkierung bereitgestellt werden soll, erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, den verteilten Bereitstellungsmodus zu wählen, auch wenn dies nicht erforderlich ist. Bei einer vollständig zentralisierten Bereitstellung wird der gesamte Datenverkehr der Zweigstelle über WAN-Verbindungen weitergeleitet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, können Sie das verteilte SIP-Trunking verwenden.

<div>


> [!NOTE]  
> Ausführliche Informationen dazu, warum und wie Sie das verteilte SIP-Trunking verwenden können, finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">SIP-Trunking in der Zweigstelle in lync Server 2013</A> in der Planungsdokumentation.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Unterstützte Verbindungstypen für das SIP-Trunking

Lync Server 2013 unterstützt die folgenden Verbindungstypen für SIP-Trunking:

  - Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

  - Eine private Verbindung ohne anderen Datenverkehr ist in der Regel der zuverlässigste und sicherste Verbindungstyp (beispielsweise eine geleaste Glasfaser-oder T1-Verbindung). Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist aber in der Regel am teuersten. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

  - Das öffentliche Internet ist der kostengünstigste Verbindungstyp, aber auch der am wenigsten zuverlässige, und der mit der niedrigsten Anruf Tragfähigkeit. Ihr Internet-Telefoniedienstanbieter (ITSP) kann diesen SIP Trunk-Verbindungstyp schützen, wenn er TLS (Transport Layer Security) und SRTP (Secure Real-Time Transport Protocol) unterstützt, um Signalisierungs-und Mediendatenverkehr zu verschlüsseln. Wenn Sie keine SIP Trunk-Verbindung über das Internet für die Verwendung von TLS und SRTP konfigurieren können, wird dringend empfohlen, einen VPN-Tunnel zu verwenden, um eine sicherere Verbindung bereitzustellen. Wenden Sie sich an Ihren ITSP, um zu ermitteln, ob er TLS mit SRTP unterstützt.

<div>

## <a name="selecting-a-connection-type"></a>Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

  - Für ein mittelständisches oder größeres Unternehmen bietet ein MPLS-Netzwerk im Allgemeinen den größten Wert. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

  - Große Unternehmen benötigen möglicherweise eine private Fiber-Optic-oder T1-Verbindung.

  - Für ein kleines Unternehmen oder eine Zweigstelle mit geringem Anrufaufkommen kann die SIP-Trunkierung über das Internet die beste Wahl sein. Dieser Verbindungstyp wird jedoch für mittelgroße oder größere Websites nicht empfohlen.

</div>

</div>

<div>

## <a name="codec-support"></a>Codec-Unterstützung

Der Dienstanbieter Proxy muss die folgenden Codecs unterstützen:

  - G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)

  - G.711 µ-Law (wird in Nordamerika eingesetzt)

</div>

</div>

<span> </span>

</div>

</div>

</div>

