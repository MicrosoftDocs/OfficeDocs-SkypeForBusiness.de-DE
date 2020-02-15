---
title: 'Lync Server 2013: Übersicht über das standortbasierte Routing'
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
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="ec7a9-102">Übersicht über das standortbasierte Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec7a9-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec7a9-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ec7a9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ec7a9-104">Mit dem standortbasierten Routing wird ein neuer Satz von Regeln eingeführt, durch den das Routing von nationalen und internationalen PSTN-anrufen geändert wird, um eine Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ec7a9-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="ec7a9-105">Durch das standortbasierte Routing können diese Regeln flexibel auf bestimmte Regionen, bestimmte Gateways oder nur auf bestimmte Benutzersätze beschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="ec7a9-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="ec7a9-106">Die folgenden Szenarien illustrieren die Haupttypen von Einschränkungen, die standortbasiertes Routing erzwingen kann:</span><span class="sxs-lookup"><span data-stu-id="ec7a9-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="ec7a9-107">Ausstiegs Aufrufe – standortbasiertes Routing kann ausgehende Anrufe von einem PSTN-Gateway erzwingen, das sich in derselben Region befindet, in der der Anrufer die PSTN-Maut Umgehung verhindert, was verhindert, dass Anrufe von einem PSTN-Gateway in einer anderen Region als Anrufer.</span><span class="sxs-lookup"><span data-stu-id="ec7a9-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="ec7a9-108">Ingress-Anrufe – standortbasiertes Routing kann verhindern, dass eingehende PSTN-Anrufe an lync-Endpunkte Ringen, wenn sich das PSTN-Gateway, das den eingehenden Anruf weiterleitet, nicht in derselben Region wie der angerufene lync-Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="ec7a9-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="ec7a9-109">Unbekannte Regionen – standortbasiertes Routing schränkt eingehende und ausgehende PSTN-Anrufe an und von Benutzern ein, die sich an unbestimmten Standorten befinden (d. h. Remotebenutzer, die eine Verbindung über das Internet herstellen oder sich in unbekannten Regionen befinden).</span><span class="sxs-lookup"><span data-stu-id="ec7a9-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="ec7a9-110">Internationale Regionen – durch das standortbasierte Routing wird das Weiterleiten von ausgehenden Anrufen über internationale PSTN-Gateways erzwungen, wenn ein lokales Gateway für den Standort des Benutzers nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec7a9-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ec7a9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec7a9-111">See Also</span></span>


[<span data-ttu-id="ec7a9-112">Planen des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec7a9-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

