---
title: 'Lync Server 2013: Implementierung von SIP-Trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de621d7508b69dd3adc3babf487406825f3a93f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Implementierung von SIP-Trunking in Lync Server 2013?

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-18_

Wenn Sie SIP-Trunking implementieren möchten, müssen Sie die Verbindung über einen Vermittlungs Server weiterleiten, der als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert und die Medien bei Bedarf transcodieren kann.

Jeder Vermittlungs Server verfügt über eine interne Netzwerkschnittstelle und eine externe Netzwerkschnittstelle. Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern her. Die externe Schnittstelle wird gemeinhin als Gateway-Schnittstelle bezeichnet, da Sie traditionell verwendet wurde, um den Vermittlungs Server mit einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Telefonanlage zu verbinden. Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle des Vermittlungsservers mit der Komponente External Edge des ITSP.

<div>


> [!NOTE]  
> Die externe Edgekomponente des ITSP könnte ein Session Border Controller (SBC), ein Router oder ein Gateway sein.



</div>

Details zu Vermittlungsservern finden Sie unter [Mediation Server Component in lync Server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Zentralisiertes und verteiltes SIP-Trunking im Vergleich

*Zentralisiert* SIP-Trunking leitet den gesamten VoIP-Datenverkehr (einschließlich Zweigstellen-Websitedatenverkehr) über Ihren zentralen Standort weiter. Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und im Allgemeinen der empfohlene Ansatz für die Implementierung von SIP-Stämmen mit lync Server 2013.

*Verteilte* SIP Trunking ist ein Bereitstellungsmodell, bei dem Sie einen lokalen SIP-Trunk an einer oder mehreren Zweigstellen implementieren. VoIP-Datenverkehr wird dann direkt von der Verzweigungs Website an einen Dienstanbieter weitergeleitet, ohne die zentrale Website zu durchlaufen.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

  - Die Verzweigungs Website erfordert eine überlebensfähige Telefonverbindung (beispielsweise, wenn das WAN ausfällt). Diese Anforderung sollte für jede Verzweigungs Website analysiert werden. einige ihrer Zweigstellen erfordern möglicherweise Redundanz und Failover, während andere möglicherweise nicht.

  - Zwischen zwei zentralen Standorten ist eine Ausfallsicherheit erforderlich. Sie müssen sicherstellen, dass ein SIP-Trunk an jedem zentralen Standort beendet wird. Wenn Sie beispielsweise über Dublin-und Tukwila-zentrale Websites verfügen und beide nur den SIP-Stamm einer Website verwenden, können die Benutzer der anderen Website keine PSTN-Anrufe tätigen, wenn der trunk herunterfällt.

  - Die Verzweigungs Website und der zentrale Standort befinden sich in verschiedenen Ländern/Regionen. Aus Kompatibilitäts-und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region. In der Europäischen Union kann die Kommunikation beispielsweise ein Land/eine Region nicht bestanden, ohne lokal an einem zentralen Punkt zu beenden.

Je nach geographischem Standort der Websites und dem voraussichtlichen Datenverkehr in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralen SIP-Stamm weiterleiten, oder Sie können einige Benutzer über einen SIP-Stamm an ihrer Zweigstelle weiterleiten. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

  - Wie groß ist jede Website (also, wie viele Benutzer sind für Enterprise-VoIP aktiviert)?

  - Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?

Die Entscheidung zur Bereitstellung des zentralisierten oder verteilten SIP-Trunkings erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht notwendig ist. Bei einer vollständig zentralisierten Bereitstellung wird der gesamte Datenverkehr der Zweigstelle über WAN-Verbindungen weitergeleitet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, können Sie das verteilte SIP-Trunking verwenden. So können Sie beispielsweise einen Standard Edition-Server an einer Zweigstelle mit Föderations Standort an der zentralen Website bereitstellen, oder Sie möchten eine Survivable Branch-Appliance oder einen Überlebenden Branch-Server mit einem kleinen Gateway bereitstellen.

<div>


> [!NOTE]  
> Details zum verteilten SIP-Trunking finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">SIP-Trunking in der Zweigstelle in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Unterstützte Verbindungstypen für das SIP-Trunking

Lync Server unterstützt die folgenden Verbindungstypen für SIP-Trunking:

  - Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

  - Eine private Verbindung ohne anderen Datenverkehr – beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung – stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

  - Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit. Internet Verbindung ist die einzige SIP-Trunking-Verbindungsart für lync Server, für die VPN erforderlich ist.

<div>

## <a name="selecting-a-connection-type"></a>Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

  - Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

  - Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).

  - Für ein kleines Unternehmen oder eine Zweigstelle mit geringem Anrufaufkommen kann die SIP-Trunkierung über das Internet die beste Wahl sein. Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Erforderliche Bandbreite

Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (der Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:

Spitzenbandbreite für den SIP-Trunk = Max. gleichzeitige Anrufe x (64 KBit/s + Headergröße)

<div>


> [!NOTE]  
> Die Headergröße beträgt maximal 20 Byte.



</div>

</div>

<div>

## <a name="codec-support"></a>Codec-Unterstützung

Lync Server 2013 unterstützt nur die folgenden Codecs:

  - G.711 A-Law (wird hauptsächlich außerhalb von Nordamerika eingesetzt)

  - G.711 µ-Law (wird in Nordamerika eingesetzt)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Anbieter von Internettelefoniediensten

Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten. Informationen zur Bereitstellung erhalten Sie von Ihrem Dienstanbieter. Eine Liste der zertifizierten SIP-Trunking-Dienstanbieter finden Sie auf der [Microsoft Unified Communications Open Interoperability Program-Website](http://go.microsoft.com/fwlink/?linkid=287029).

Ausführliche Informationen zu für Microsoft zertifizierten Anbietern von SIP-Trunking erhalten Sie bei Ihrem Microsoft-Ansprechpartner.

<div>


> [!IMPORTANT]  
> Sie müssen einen für Microsoft zertifizierten Dienstanbieter nutzen, um sicherzustellen, dass Ihr Anbieter von Internettelefoniediensten sämtliche Funktionen unterstützt, die über den SIP-Trunk verarbeitet werden (z. B. das Einrichten und Verwalten von Sitzungen sowie die Unterstützung aller erweiterten VoIP-Dienste). Der technische Support von Microsoft kann nicht für Konfigurationen in Anspruch genommen werden, die nicht zertifizierte Anbieter verwenden. Wenn Sie gegenwärtig einen Internetdienstanbieter nutzen, der nicht für SIP-Trunking zertifiziert ist, können Sie diesen Anbieter weiterhin als ISP nutzen und sich für das SIP-Trunking für einen für Microsoft zertifizierten Anbieter entscheiden.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

