---
title: 'Lync Server 2013: Übersicht über standortbasiertes Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="71d96-102">Übersicht über standortbasiertes Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d96-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71d96-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="71d96-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="71d96-p101">Das standortbasierte Routing stellt einen neuen Regelsatz zur Verfügung, mit dem das Routing nationaler und internationaler PSTN-Anrufe modifiziert werden kann, um eine Gebührenumgehung zu verhindern. Beim standortbasierten Routing lassen sich die Regeln flexibel auf bestimmte Regionen und Gateways und sogar auf bestimmte Benutzergruppen beschränken.</span><span class="sxs-lookup"><span data-stu-id="71d96-p101">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass. Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="71d96-106">Die folgenden Szenarien veranschaulichen die Haupttypen von Einschränkungen, die standortbasiertes Routing erzwingen kann:</span><span class="sxs-lookup"><span data-stu-id="71d96-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="71d96-107">Ausstiegs Anrufe – standortbasiertes Routing kann ausgehende Aufrufe von einem PSTN-Gateway erzwingen, das sich in derselben Region befindet, in der der Anrufer die PSTN-Maut Umgehung verhindert, die das Auslaufen von einem PSTN-Gateway in einer anderen Region wie die Rufnummernanzeige.</span><span class="sxs-lookup"><span data-stu-id="71d96-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="71d96-108">Ingress-Anrufe – standortbasiertes Routing kann verhindern, dass eingehende PSTN-Anrufe an lync-Endpunkte ablaufen, wenn sich das PSTN-Gateway, das den eingehenden Anruf leitet, nicht in der gleichen Region wie der angerufene lync-Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="71d96-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="71d96-109">Unbekannte Regionen – standortbasiertes Routing schränkt eingehende und ausgehende PSTN-Anrufe von und zu Benutzern ein, die sich an unbestimmten Speicherorten befinden (d. h. Remotebenutzer, die eine Verbindung mit dem Internet herstellen oder sich in unbekannten Regionen befinden).</span><span class="sxs-lookup"><span data-stu-id="71d96-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="71d96-110">Internationale Regionen – durch standortbasiertes Routing wird das Routing von ausgehenden Anrufen über internationale PSTN-Gateways erzwungen, wenn ein lokales Gateway zum Standort des Benutzers nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="71d96-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="71d96-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71d96-111">See Also</span></span>


[<span data-ttu-id="71d96-112">Planung des standortbasierten Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71d96-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

