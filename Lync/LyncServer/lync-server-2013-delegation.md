---
title: 'Lync Server 2013: Stellvertretung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="ba272-102">Stellvertretung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba272-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba272-103">_**Letztes Änderungsdatum des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="ba272-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="ba272-104">Die Delegierungsfunktionen in lync sind auf die folgende Weise vom standortbasierten Routing betroffen:</span><span class="sxs-lookup"><span data-stu-id="ba272-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="ba272-105">Wenn eine für standortbasierte Weiterleitung aktivierte Stellvertretung einen Anruf im Auftrag eines Managers anbietet, wird die VoIP-Richtlinie des Stellvertreters verwendet, um den Anruf zu genehmigen, und die VoIP-Routing Richtlinie des Stellvertreters wird zum Weiterleiten des Anrufs verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba272-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="ba272-106">Für eingehende Anrufe aus dem öffentlichen Telefonnetz für einen Vorgesetzten gelten die gleichen Regeln wie für Anrufweiterleitung oder paralleles Anrufen, wie in den Themen zur Anrufweiterleitung und -durchstellung bzw. zum parallelen Anrufen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba272-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="ba272-107">Wenn eine Stellvertretung einen Endpunkt im öffentlichen Telefonnetz als Ziel für paralleles Anrufen festlegt, wird bei einem für den Vorgesetzten eingehenden Anruf die VoIP-Routingrichtlinie des Standorts, der dem eingehenden Trunk zugeordnet ist, für das Routen des Anrufs an den Endpunkt der Stellvertretung im öffentlichen Telefonnetz verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba272-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="ba272-108">Für Stellvertretungen empfiehlt es sich, dass der Vorgesetzte und die ihm zugeordneten Stellvertretungen sich normalerweise am gleichen Netzwerkstandort befinden.</span><span class="sxs-lookup"><span data-stu-id="ba272-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ba272-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba272-109">See Also</span></span>


[<span data-ttu-id="ba272-110">Szenarien für das standortbasierte Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba272-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

