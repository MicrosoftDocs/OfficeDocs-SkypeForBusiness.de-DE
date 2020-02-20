---
title: 'Lync Server 2013: Delegierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 360223733f003c30d63ef0145fa04c51503d510d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="eaeb8-102">Delegation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaeb8-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaeb8-103">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="eaeb8-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="eaeb8-104">Die Delegierungsfunktionen in lync sind von Standort basiertem Routing auf folgende Weise betroffen:</span><span class="sxs-lookup"><span data-stu-id="eaeb8-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="eaeb8-105">Wenn ein Stellvertreter, der für standortbasiertes Routing aktiviert ist, einen Anruf im Auftrag eines Managers tätigt, wird die VoIP-Richtlinie des Stellvertreters verwendet, um den Anruf zu autorisieren, und die Website VoIP-Routing Richtlinie des Stellvertreters wird zum Weiterleiten des Anrufs verwendet.</span><span class="sxs-lookup"><span data-stu-id="eaeb8-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="eaeb8-106">Für eingehende PSTN-Anrufe an einen Vorgesetzten gelten dieselben Regeln wie für die Anrufweiterleitung oder gleichzeitiges Klingeln, wie in den Themen Anrufweiterleitung und Weiterleitung und gleichzeitiges Klingeln beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eaeb8-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="eaeb8-107">Wenn ein Delegat einen PSTN-Endpunkt als gleichzeitiges Ring Ziel festlegt, wird für einen eingehenden Anruf an den Vorgesetzten die VoIP-Routing Richtlinie des Standorts, der dem eingehenden trunk zugeordnet ist, zum Weiterleiten des Anrufs an den PSTN-Endpunkt des Stellvertreters verwendet.</span><span class="sxs-lookup"><span data-stu-id="eaeb8-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="eaeb8-108">Für die Delegierung empfiehlt es sich, dass sich der Vorgesetzte und die zugehörigen Stellvertretungen normalerweise am selben Netzwerkstandort befinden.</span><span class="sxs-lookup"><span data-stu-id="eaeb8-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="eaeb8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaeb8-109">See Also</span></span>


[<span data-ttu-id="eaeb8-110">Szenarien für das standortbasierte Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaeb8-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

