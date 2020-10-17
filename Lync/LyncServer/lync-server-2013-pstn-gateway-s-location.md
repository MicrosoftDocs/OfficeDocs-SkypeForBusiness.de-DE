---
title: 'Lync Server 2013: Standort des PSTN-Gateways'
description: 'Lync Server 2013: Standort des PSTN-Gateways.'
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
ms.openlocfilehash: 4f793249908bd1f064f9038ddd90c7f5b01a61d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565601"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="e5d2a-103">Standort des PSTN-Gateways in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5d2a-103">PSTN gateway's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5d2a-104">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e5d2a-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e5d2a-105">Anrufe, die über PSTN-Gateways und Nebenstellenanlagen weitergeleitet werden, erfordern möglicherweise Location-Based Routing Einschränkungen je nach Standort dieser Systeme.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-105">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="e5d2a-106">Location-Based Routing kann an der Granularität pro trunk Basis aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-106">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="e5d2a-107">Mit Location-Based Routing wird der folgende Satz von Regeln eingeführt, wenn dieser für einen trunk aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="e5d2a-107">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="e5d2a-108">Wenn Location-Based Routing pro trunk aktiviert ist, werden die Regeln, die für diesen Trunk definiert sind, nur auf Anrufe angewendet, die über diesen Trunk weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-108">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="e5d2a-109">Um zu verhindern, dass PSTN-Maut Leitungen ausgehen, wenn Anrufe von einem Netzwerkstandort abweichen, die sich auf dem Netzwerkstandort befinden, an dem sich das PSTN-Gateway befindet, wird durch Location-Based Routing die Zuordnung eines Netzwerkstandorts zu einem bestimmten trunk eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-109">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="e5d2a-110">Dadurch wird der Netzwerkstandort definiert, auf dem Anrufe an einen bestimmten trunk weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-110">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="e5d2a-111">Trunks können auf zwei Arten für Location-Based Routing aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="e5d2a-111">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="e5d2a-112">Der trunk ist für ein PSTN-Gateway definiert, das Anrufe an das PSTN das.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-112">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="e5d2a-113">Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endpunkte geroutet, die sich innerhalb desselben Netzwerkstandorts befinden wie der Trunk.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-113">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="e5d2a-114">Der trunk ist für einen Vermittlungsserver Peer definiert, der keine Anrufe an das PSTN ausgeht und Dienste für Benutzer mit älteren Telefonen an statischen Standorten (also PBX-Telefone) anbietet.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-114">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="e5d2a-115">Für diese spezielle Konfiguration werden alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, als Ursprung vom selben Netzwerkstandort wie der trunk betrachtet.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-115">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="e5d2a-116">Anrufe von PBX-Benutzern haben dieselbe Location-Based Routing Erzwingung wie lync-Benutzer, die sich am selben Netzwerkstandort wie der trunk befinden.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-116">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="e5d2a-117">Wenn zwei Nebenstellenanlagen, die sich an separaten Netzwerkstandorten befinden, über lync Server verbunden sind, ermöglicht Location-Based Routing das Weiterleiten von einem PBX-Endpunkt an einem Netzwerkstandort an einen anderen PBX-Endpunkt am anderen Netzwerkstandort.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-117">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="e5d2a-118">Dieses Szenario wird nicht durch Location-Based Routing blockiert.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-118">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="e5d2a-119">Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein lync-Benutzer am gleichen Speicherort können Endpunkte, die mit einem Vermittlungsserver-Peer mit dieser Konfiguration verbunden sind, Anrufe von und von anderen Vermittlungsserver Peers tätigen oder empfangen, die Anrufe nicht an das PSTN weiterleiten (d. h. an eine andere Nebenstellenanlage), unabhängig vom Netzwerkstandort, dem der Vermittlungsserver Peer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-119">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="e5d2a-120">Alle eingehenden Anrufe, ausgehende Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen einem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die als lokal für solche Vermittlungsserver Peer definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e5d2a-120">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e5d2a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5d2a-121">See Also</span></span>


[<span data-ttu-id="e5d2a-122">Leitfaden für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5d2a-122">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

