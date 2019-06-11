---
title: 'Lync Server 2013: Standort eines PSTN-Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="27e65-102">Standort eines PSTN-Gateways in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27e65-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27e65-103">_**Letztes Änderungsdatum des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="27e65-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="27e65-104">Für Anrufe, die über PSTN-Gateways und PBX-Anlagen geroutet werden, können abhängig vom Standort solcher Systeme standortbasierte Routing Einschränkungen erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="27e65-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="27e65-105">Standortbasiertes Routing kann bei der Granularität pro trunk-Basis aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="27e65-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="27e65-106">Standortbasiertes Routing führt die folgenden Regelsätze ein, wenn Sie in einem Trunk aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="27e65-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="27e65-107">Wenn standortbasiertes Routing pro trunk aktiviert ist, werden die Regeln, die für diesen Stamm definiert sind, nur auf Anrufe angewendet, die durch diesen Trunk geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="27e65-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="27e65-108">Um zu verhindern, dass PSTN-Mautgebühren für Anrufe von einer Netzwerk Website abweichen, die sich auf der Netzwerk Website befinden, auf der sich das PSTN-Gateway befindet, führt das ortsbasierte Routing die Zuordnung einer Netzwerk Website zu einem bestimmten Stamm ein.</span><span class="sxs-lookup"><span data-stu-id="27e65-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="27e65-109">Dadurch wird die Netzwerk Website definiert, die das Weiterleiten von Anrufen an einen bestimmten trunk ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="27e65-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="27e65-110">Trunks kann auf zwei Arten für standortbasiertes Routing aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="27e65-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="27e65-p103">Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das Telefonfestnetz weiterleitet. Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endgeräte weitergeleitet, die sich am selben Netzwerkstandort befinden wie der Trunk.</span><span class="sxs-lookup"><span data-stu-id="27e65-p103">The trunk is defined for a PSTN gateway that egresses calls to the PSTN. Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="27e65-113">Der trunk ist für einen Vermittlungs Server-Peer definiert, der keine Anrufe an das PSTN abgibt und Dienste für Benutzer mit älteren Telefonen an statischen Speicherorten (also Telefonanlagen) abruft.</span><span class="sxs-lookup"><span data-stu-id="27e65-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="27e65-114">Für diese spezielle Konfiguration wird für alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, angenommen, dass sie vom selben Netzwerkstandort kommen wie der Trunk.</span><span class="sxs-lookup"><span data-stu-id="27e65-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="27e65-115">Anrufe von PBX-Benutzern haben dieselbe standortbasierte Routing Erzwingung wie lync-Benutzer, die sich am gleichen Netzwerkstandort wie der Stamm befinden.</span><span class="sxs-lookup"><span data-stu-id="27e65-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="27e65-116">Wenn zwei PBX-Anlagen, die sich auf separaten Netzwerkstandorten befinden, über lync Server verbunden sind, ermöglicht standortbasiertes Routing das Routing von einem PBX-Endpunkt in einer Netzwerk Website zu einem anderen PBX-Endpunkt auf der anderen Netzwerk Website.</span><span class="sxs-lookup"><span data-stu-id="27e65-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="27e65-117">Dieses Szenario wird nicht durch standortbasiertes Routing blockiert.</span><span class="sxs-lookup"><span data-stu-id="27e65-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="27e65-118">Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein lync-Benutzer am gleichen Speicherort können Endpunkte, die mit einem Vermittlungsserver-Peer mit dieser Konfiguration verbunden sind, Anrufe an und von anderen Vermittlungsserver-Peers tätigen oder empfangen, die keine Anrufe an das PSTN weiterleiten (i. e. ein Endpunkt, der mit einer anderen Telefonanlage verbunden ist) unabhängig von der Netzwerk Website, der der Vermittlungs Server-Peer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="27e65-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="27e65-119">Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen dem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die als lokal für diesen Vermittlungs Server-Peer definiert sind.</span><span class="sxs-lookup"><span data-stu-id="27e65-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="27e65-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27e65-120">See Also</span></span>


[<span data-ttu-id="27e65-121">Anleitungen für das standortbasierte Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27e65-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

