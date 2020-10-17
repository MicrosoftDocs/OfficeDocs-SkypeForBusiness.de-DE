---
title: 'Lync Server 2013: Speicherort des Benutzers'
description: 'Lync Server 2013: Speicherort des Benutzers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561211"
---
# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="a0a40-103">Speicherort des Benutzers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0a40-103">User's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0a40-104">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="a0a40-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="a0a40-105">Location-Based Routing nutzt dieselben netzwerkregionen, Standorte und Subnetze, die in lync Server verwendet werden, die von E9-1-1, CAC und medienumgehung definiert wurde, um Anruf Weiterleitungs Einschränkungen anzuwenden, um die PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="a0a40-105">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="a0a40-106">Der Standort eines Benutzers wird durch das IP-Subnetz der lync-Endpunkte des Benutzers festgelegt, von denen eine Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a0a40-106">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="a0a40-107">Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, der in vom Administrator definierten netzwerkregionen aggregiert wird.</span><span class="sxs-lookup"><span data-stu-id="a0a40-107">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="a0a40-108">Location-Based Routing wird basierend auf dem Netzwerkstandort des Benutzers erzwungen.</span><span class="sxs-lookup"><span data-stu-id="a0a40-108">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="a0a40-109">Location-Based Routingregeln werden auf einer pro Netzwerkstandort Basis angewendet, was bedeutet, dass ein bestimmter Satz von Regeln auf alle für Location-Based Routing aktivierten Endpunkte angewendet wird, die sich innerhalb desselben Netzwerkstandorts befinden.</span><span class="sxs-lookup"><span data-stu-id="a0a40-109">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="a0a40-110">Administratoren können Location-Based Routing auf Netzwerkstandorte anwenden, die dies erfordern.</span><span class="sxs-lookup"><span data-stu-id="a0a40-110">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="a0a40-111">VoIP-Routing Richtlinien können auf einer pro Netzwerkstandort Basis definiert werden, um ein bestimmtes PSTN-Gateway zu definieren, das von allen Benutzern am Netzwerkstandort zum Anrufen von PSTN-Telefonnummern verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0a40-111">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="a0a40-112">Solche VoIP-Routing Richtlinien haben Vorrang vor dem Routing, das durch die VoIP-Richtlinie des Benutzers definiert wird, wenn sich der Benutzer an einem Netzwerkstandort befindet, der für Location-Based Routing aktiviert ist, und er verhindert das Weiterleiten von Anrufen über andere PSTN-Gateways, die für Location-Based Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a0a40-112">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="a0a40-113">Wenn ein lync-Benutzer einen PSTN-Anruf tätigt, bestimmt die VoIP-Richtlinie des Benutzers, ob der Benutzer zum tätigen des Anrufs autorisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0a40-113">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="a0a40-114">Wenn die VoIP-Richtlinie des Benutzers es dem Benutzer ermöglicht, den Anruf zu tätigen, bestimmt Location-Based Routing, von welchem PSTN-Gateway der Anruf ausgehen soll.</span><span class="sxs-lookup"><span data-stu-id="a0a40-114">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="a0a40-115">Durch Location-Based Routing wird diese Bestimmung basierend auf dem Standort des Benutzers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a0a40-115">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="a0a40-116">Ein Benutzer Speicherort kann wie folgt kategorisiert werden:</span><span class="sxs-lookup"><span data-stu-id="a0a40-116">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="a0a40-117">Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der für Location-Based Routing aktiviert ist, und seine DID-Nummer (direkte Inward Dial) wird auf einem PSTN-Gateway am gleichen Netzwerkstandort (also Office) beendet.</span><span class="sxs-lookup"><span data-stu-id="a0a40-117">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="a0a40-118">Das Routing von ausgehenden Anrufen erfolgt über die VoIP-Routing Richtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="a0a40-118">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="a0a40-119">Eingehende PSTN-Anrufe an den Benutzer werden an Endpunkte geroutet, die sich am selben Netzwerkstandort wie das PSTN-Gateway befinden.</span><span class="sxs-lookup"><span data-stu-id="a0a40-119">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="a0a40-120">Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich vom Netzwerkstandort unterscheidet, auf dem sich das PSTN-Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="a0a40-120">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="a0a40-121">(d. h., der Benutzer hat in ein anderes Unternehmensbüro gereist).</span><span class="sxs-lookup"><span data-stu-id="a0a40-121">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="a0a40-122">Für das Routing von ausgehenden Anrufen wird die VoIP-Routing Richtlinie des Netzwerkstandorts verwendet, an dem sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="a0a40-122">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="a0a40-123">Eingehende PSTN-Anrufe an den Benutzer werden nicht an Endpunkte geroutet, die sich an unterschiedlichen Standorten befinden als das PSTN-Gateway, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="a0a40-123">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="a0a40-124">Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der der lync Server-Bereitstellung unbekannt ist, basiert das Routing von ausgehenden Anrufen auf der VoIP-Richtlinie, die dem Benutzer für PSTN-Gateways zugewiesen ist, die nicht an Location-Based Routing Einschränkungen gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="a0a40-124">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="a0a40-125">Eingehende PSTN-Anrufe werden nicht an Endpunkte geroutet, die sich an unbekannten Netzwerkstandorten befinden, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="a0a40-125">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a0a40-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0a40-126">See Also</span></span>


[<span data-ttu-id="a0a40-127">Leitfaden für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0a40-127">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

