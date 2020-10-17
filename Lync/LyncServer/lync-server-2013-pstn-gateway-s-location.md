---
title: 'Lync Server 2013: Standort des PSTN-Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29898244dc0e54da2586d0a58212148c493b96db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512442"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a>Standort des PSTN-Gateways in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Anrufe, die über PSTN-Gateways und Nebenstellenanlagen weitergeleitet werden, erfordern möglicherweise Location-Based Routing Einschränkungen je nach Standort dieser Systeme. Location-Based Routing kann an der Granularität pro trunk Basis aktiviert werden.

Mit Location-Based Routing wird der folgende Satz von Regeln eingeführt, wenn dieser für einen trunk aktiviert ist:

  - Wenn Location-Based Routing pro trunk aktiviert ist, werden die Regeln, die für diesen Trunk definiert sind, nur auf Anrufe angewendet, die über diesen Trunk weitergeleitet werden.

  - Um zu verhindern, dass PSTN-Maut Leitungen ausgehen, wenn Anrufe von einem Netzwerkstandort abweichen, die sich auf dem Netzwerkstandort befinden, an dem sich das PSTN-Gateway befindet, wird durch Location-Based Routing die Zuordnung eines Netzwerkstandorts zu einem bestimmten trunk eingeführt. Dadurch wird der Netzwerkstandort definiert, auf dem Anrufe an einen bestimmten trunk weitergeleitet werden können.

Trunks können auf zwei Arten für Location-Based Routing aktiviert werden:

  - Der trunk ist für ein PSTN-Gateway definiert, das Anrufe an das PSTN das. Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endpunkte geroutet, die sich innerhalb desselben Netzwerkstandorts befinden wie der Trunk.

  - Der trunk ist für einen Vermittlungsserver Peer definiert, der keine Anrufe an das PSTN ausgeht und Dienste für Benutzer mit älteren Telefonen an statischen Standorten (also PBX-Telefone) anbietet. Für diese spezielle Konfiguration werden alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, als Ursprung vom selben Netzwerkstandort wie der trunk betrachtet. Anrufe von PBX-Benutzern haben dieselbe Location-Based Routing Erzwingung wie lync-Benutzer, die sich am selben Netzwerkstandort wie der trunk befinden. Wenn zwei Nebenstellenanlagen, die sich an separaten Netzwerkstandorten befinden, über lync Server verbunden sind, ermöglicht Location-Based Routing das Weiterleiten von einem PBX-Endpunkt an einem Netzwerkstandort an einen anderen PBX-Endpunkt am anderen Netzwerkstandort. Dieses Szenario wird nicht durch Location-Based Routing blockiert. Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein lync-Benutzer am gleichen Speicherort können Endpunkte, die mit einem Vermittlungsserver-Peer mit dieser Konfiguration verbunden sind, Anrufe von und von anderen Vermittlungsserver Peers tätigen oder empfangen, die Anrufe nicht an das PSTN weiterleiten (d. h. an eine andere Nebenstellenanlage), unabhängig vom Netzwerkstandort, dem der Vermittlungsserver Peer zugeordnet ist. Alle eingehenden Anrufe, ausgehende Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen einem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die als lokal für solche Vermittlungsserver Peer definiert sind.

<div>

## <a name="see-also"></a>Siehe auch


[Leitfaden für Location-Based Routing in lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

