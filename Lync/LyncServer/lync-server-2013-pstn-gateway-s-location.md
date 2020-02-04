---
title: 'Lync Server 2013: Standort eines PSTN-Gateways'
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
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Standort eines PSTN-Gateways in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Für Anrufe, die über PSTN-Gateways und PBX-Anlagen geroutet werden, können abhängig vom Standort solcher Systeme standortbasierte Routing Einschränkungen erforderlich sein. Standortbasiertes Routing kann bei der Granularität pro trunk-Basis aktiviert werden.

Standortbasiertes Routing führt die folgenden Regelsätze ein, wenn Sie in einem Trunk aktiviert sind:

  - Wenn standortbasiertes Routing pro trunk aktiviert ist, werden die Regeln, die für diesen Stamm definiert sind, nur auf Anrufe angewendet, die durch diesen Trunk geleitet werden.

  - Um zu verhindern, dass PSTN-Mautgebühren für Anrufe von einer Netzwerk Website abweichen, die sich auf der Netzwerk Website befinden, auf der sich das PSTN-Gateway befindet, führt das ortsbasierte Routing die Zuordnung einer Netzwerk Website zu einem bestimmten Stamm ein. Dadurch wird die Netzwerk Website definiert, die das Weiterleiten von Anrufen an einen bestimmten trunk ermöglicht.

Trunks kann auf zwei Arten für standortbasiertes Routing aktiviert werden:

  - Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das Telefonfestnetz weiterleitet. Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endgeräte weitergeleitet, die sich am selben Netzwerkstandort befinden wie der Trunk.

  - Der trunk ist für einen Vermittlungs Server-Peer definiert, der keine Anrufe an das PSTN abgibt und Dienste für Benutzer mit älteren Telefonen an statischen Speicherorten (also Telefonanlagen) abruft. Für diese spezielle Konfiguration wird für alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, angenommen, dass sie vom selben Netzwerkstandort kommen wie der Trunk. Anrufe von PBX-Benutzern haben dieselbe standortbasierte Routing Erzwingung wie lync-Benutzer, die sich am gleichen Netzwerkstandort wie der Stamm befinden. Wenn zwei PBX-Anlagen, die sich auf separaten Netzwerkstandorten befinden, über lync Server verbunden sind, ermöglicht standortbasiertes Routing das Routing von einem PBX-Endpunkt in einer Netzwerk Website zu einem anderen PBX-Endpunkt auf der anderen Netzwerk Website. Dieses Szenario wird nicht durch standortbasiertes Routing blockiert. Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein lync-Benutzer am gleichen Speicherort können Endpunkte, die mit einem Vermittlungsserver-Peer mit dieser Konfiguration verbunden sind, Anrufe an und von anderen Vermittlungsserver-Peers tätigen oder empfangen, die keine Anrufe an das PSTN weiterleiten (i. e. ein Endpunkt, der mit einer anderen Telefonanlage verbunden ist) unabhängig von der Netzwerk Website, der der Vermittlungs Server-Peer zugeordnet ist. Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen dem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die als lokal für diesen Vermittlungs Server-Peer definiert sind.

<div>

## <a name="see-also"></a>Siehe auch


[Anleitungen für das standortbasierte Routing in Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

