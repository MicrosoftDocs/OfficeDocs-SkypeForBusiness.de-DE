---
title: 'Lync Server 2013: Übersicht über das Location-Based Routing'
description: 'Lync Server 2013: Übersicht über das Location-Based Routing.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562811"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="c0de1-103">Übersicht über Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0de1-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0de1-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c0de1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c0de1-105">Mit Location-Based Routing wird ein neuer Satz von Regeln eingeführt, durch den das Routing von nationalen und internationalen PSTN-anrufen geändert wird, um eine Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c0de1-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="c0de1-106">Location-Based Routing bietet die Möglichkeit, diese Regeln auf bestimmte Regionen, bestimmte Gateways oder nur auf bestimmte Benutzersätze zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="c0de1-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="c0de1-107">In den folgenden Szenarien werden die wichtigsten Arten von Einschränkungen veranschaulicht, die Location-Based Routing erzwingen kann:</span><span class="sxs-lookup"><span data-stu-id="c0de1-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="c0de1-108">Ausstiegs Aufrufe – Location-Based Routing kann ausgehende Anrufe von einem PSTN-Gateway erzwingen, das sich in derselben Region befindet, in der der Anrufer die PSTN-Maut Umgehung verhindert, wodurch Anrufe von einem PSTN-Gateway in einer anderen Region als der Anrufer verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="c0de1-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="c0de1-109">Ingress-Anrufe – Location-Based Routing kann verhindern, dass eingehende PSTN-Anrufe an lync-Endpunkte Ringen, wenn sich das PSTN-Gateway, das den eingehenden Anruf weiterleitet, nicht in derselben Region wie der angerufene lync-Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="c0de1-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="c0de1-110">Unbekannte Regionen – Location-Based Routing schränkt eingehende und ausgehende PSTN-Anrufe an und von Benutzern ein, die sich an unbestimmten Standorten befinden (d. h. Remotebenutzer, die über das Internet eine Verbindung herstellen oder sich in unbekannten Regionen befinden).</span><span class="sxs-lookup"><span data-stu-id="c0de1-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="c0de1-111">Internationale Regionen – durch Location-Based Routing wird das Routing von ausgehenden Anrufen über internationale PSTN-Gateways erzwungen, wenn ein lokales Gateway für den Standort des Benutzers nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0de1-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c0de1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0de1-112">See Also</span></span>


[<span data-ttu-id="c0de1-113">Planen von Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0de1-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

