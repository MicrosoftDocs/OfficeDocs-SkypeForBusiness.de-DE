---
title: 'Lync Server 2013: Wie kann ich SIP-Trunking implementieren?'
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
ms.openlocfilehash: ecd89ce28f1565e44c92ba543ccf992bb2a3c811
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504142"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Wie kann ich SIP-Trunking in lync Server 2013 implementieren?

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-18_

Um SIP-Trunking implementieren zu können, müssen Sie die Verbindung über eine Vermittlungsserver weiterleiten, die als Proxy für Kommunikationssitzungen zwischen lync Server 2013-Clients und dem Dienstanbieter fungiert und bei Bedarf transcodierte Medien.

Jedes Vermittlungsserver verfügt über eine interne Netzwerkschnittstelle und eine externe Netzwerkschnittstelle. Die interne Schnittstelle stellt eine Verbindung mit den Front-End-Servern her. Die externe Schnittstelle wird häufig als Gateway-Schnittstelle bezeichnet, da Sie traditionell verwendet wurde, um die Vermittlungsserver mit einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Nebenstellenanlage zu verbinden. Um einen SIP-Trunk zu implementieren, verbinden Sie die externe Schnittstelle des Vermittlungsserver mit der externen Edge-Komponente des ITSP.

<div>


> [!NOTE]  
> Die externe Edgekomponente des ITSP kann ein SBC (Session Border Controller), ein Router oder ein Gateway sein.



</div>

Ausführliche Informationen zu Vermittlungsservern finden Sie unter [Vermittlungsserver-Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Zentralisiertes und verteiltes SIP-Trunking im Vergleich

*Zentralisiert* Mit SIP-Trunking werden alle VoIP-Datenverkehr (Voice over Internet Protocol), einschließlich des Datenverkehrs an der Zweigstelle, über den zentralen Standort weitergeleitet. Das zentralisierte Bereitstellungsmodell ist einfach, kostengünstig und wird im Allgemeinen als Ansatz zur Implementierung von SIP-Trunks mit lync Server 2013 empfohlen.

*Verteilt* Bei SIP-Trunking handelt es sich um ein Bereitstellungsmodell, in dem Sie einen lokalen SIP-Trunk an einem oder mehreren Zweigstellenstandorten implementieren. VoIP-Datenverkehr wird dann direkt vom Zweigstellenstandort an einen Dienstanbieter weitergeleitet, ohne den zentralen Standort zu durchlaufen.

Ein verteiltes SIP-Trunking ist nur in den folgenden Fällen erforderlich:

  - Für den Zweigstellenstandort muss Ausfallsicherheit gewährleistet werden (beispielsweise bei einem WAN-Ausfall). Diese Anforderung sollte für jeden Zweigstellenstandort analysiert werden. einige ihrer Zweigstellen benötigen möglicherweise Redundanz und Failover, andere dagegen nicht.

  - Ausfallsicherheit ist zwischen zwei zentralen Standorten erforderlich. Sie müssen sicherstellen, dass ein SIP-Trunk an jedem zentralen Standort beendet wird. Wenn beispielsweise die zentralen Standorte Dublin und Tukwila und beide nur den SIP-Trunk eines Standorts verwenden und der trunk ausfällt, können die Benutzer der anderen Website keine PSTN-Anrufe tätigen.

  - Der Zweigstellenstandort und der zentrale Standort befinden sich in unterschiedlichen Ländern/Regionen. Aus Kompatibilitäts- und rechtlichen Gründen benötigen Sie mindestens einen SIP-Trunk pro Land/Region. Beispielsweise kann die Kommunikation in der Europäischen Union ein Land/eine Region nicht verlassen, ohne lokal an einem zentralen Ort zu kündigen.

Abhängig vom geografischen Standort der Standorte und von der voraussichtlichen Menge an Datenverkehr in Ihrem Unternehmen möchten Sie möglicherweise nicht alle Benutzer über den zentralen SIP-Trunk weiterleiten, oder Sie können einige Benutzer über einen SIP-Trunk an Ihrem Zweigstellenstandort weiterleiten. Beantworten Sie zur Analyse Ihrer Anforderungen die folgenden Fragen:

  - Wie groß ist jeder Standort (also wie viele Benutzer sind für Enterprise-VoIP aktiviert)?

  - Welche DID-Nummern (Direct Inward Dialing) erhalten an den einzelnen Standorten die meisten Telefonanrufe?

Die Entscheidung, ob ein zentralisiertes oder verteiltes SIP-Trunking bereitgestellt werden soll, erfordert eine Kosten-Nutzen-Analyse. In einigen Fällen kann es vorteilhaft sein, sich für das verteilte Bereitstellungsmodell zu entscheiden, auch wenn es nicht erforderlich ist. In einer vollständig zentralisierten Bereitstellung wird der gesamte Zweigstellendatenverkehr über WAN-Verbindungen geroutet. Statt für die erforderliche Bandbreite Gebühren für WAN-Verbindungen zu zahlen, möchten Sie möglicherweise das verteilte SIP-Trunking verwenden. Sie können beispielsweise eine Standard Edition-Server an einem Zweigstellenstandort mit Partnerverbund am zentralen Standort bereitstellen, oder Sie möchten ein Survivable Branch Appliance oder ein Survivable Branch Server mit einem kleinen Gateway bereitstellen.

<div>


> [!NOTE]  
> Ausführliche Informationen zum verteilten SIP-Trunking finden Sie unter <A href="lync-server-2013-branch-site-sip-trunking.md">Branch Site SIP Trunking in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Unterstützte Verbindungstypen für das SIP-Trunking

Lync Server unterstützt die folgenden Verbindungstypen für das SIP-Trunking:

  - Multiprotocol Label Switching (MPLS) ist ein privates Netzwerk, das Daten von einem Netzwerkknoten an einen anderen weiterleitet und übertragt. Die Bandbreite in einem MPLS-Netzwerk wird gemeinsam mit anderen Teilnehmern verwendet, und jedem Datenpaket wird eine Bezeichnung zugewiesen, um die Daten der einzelnen Teilnehmer voneinander zu unterscheiden. Für diesen Verbindungstyp ist kein VPN (virtuelles privates Netzwerk) erforderlich. Ein potenzieller Nachteil ist, dass übermäßiger IP-Datenverkehr zu Konflikten mit VoIP-Operationen führen kann, wenn dem VoIP-Datenverkehr keine Priorität eingeräumt wird.

  - Eine private Verbindung ohne anderen Datenverkehr – beispielsweise eine geleaste Glasfaserleitung oder T1-Leitung – stellt im Allgemeinen die zuverlässigste und sicherste Form der Verbindung dar. Dieser Verbindungstyp bietet die höchste Anrufkapazität, ist typischerweise jedoch auch die teuerste Variante. Ein VPN ist nicht erforderlich. Private Verbindungen sind geeignet für Organisationen mit hohem Anrufaufkommen oder strikten Sicherheits- und Verfügbarkeitsanforderungen.

  - Das Internet stellt den günstigsten Verbindungstyp dar, bietet jedoch auch die geringste Zuverlässigkeit. Internet Verbindung ist die einzige lync Server SIP-Trunking-Verbindungstyp, der VPN erfordert.

<div>

## <a name="selecting-a-connection-type"></a>Auswählen eines Verbindungstyps

Der für Ihr Unternehmen geeignete Verbindungstyp für das SIP-Trunking richtet sich nach Ihren Anforderungen und Ihrem Budget.

  - Für mittelständische oder größere Unternehmen bietet ein MPLS-Netzwerk üblicherweise den größten Nutzen. Dieser Netzwerktyp bietet die erforderliche Bandbreite zu einem günstigeren Preis als ein dediziertes privates Netzwerk.

  - Große Unternehmen benötigen möglicherweise eine private Glasfaserleitung, eine T1-, T3- oder eine noch leistungsstärkere Leitung (in der Europäischen Union E1, E3 oder besser).

  - Bei einem kleinen Unternehmen oder Zweigstellenstandort mit niedrigem Anrufvolumen ist die SIP-Trunkierung über das Internet möglicherweise die beste Wahl. Dieser Verbindungstyp wird jedoch für mittlere oder größere Standorte nicht empfohlen.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Erforderliche Bandbreite

Die für eine Implementierung erforderliche Bandbreite richtet sich nach der benötigten Anrufkapazität (die Anzahl von gleichzeitigen Anrufen, die unterstützt werden muss). Sie müssen die Bandbreitenverfügbarkeit berücksichtigen, um die gezahlte Spitzenbandbreite voll auszuschöpfen. Verwenden Sie die folgende Formel, um die erforderliche Spitzenbandbreite pro SIP-Trunk zu berechnen:

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

  - G.711 µ-Law (wird in Nordamerika verwendet)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Anbieter von Internettelefoniediensten

Die Implementierung der Dienstanbieterseite einer SIP-Trunkverbindung variiert abhängig vom Anbieter von Internettelefoniediensten. Informationen zur Bereitstellung erhalten Sie bei Ihrem Dienstanbieter. Eine Liste der zertifizierten SIP-Trunking-Dienstanbieter finden Sie unter [Microsoft Unified Communications Open Interoperability Program-Website](https://go.microsoft.com/fwlink/?linkid=287029).

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

