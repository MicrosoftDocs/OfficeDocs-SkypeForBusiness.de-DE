---
title: 'Lync Server 2013: Planen des standortbasierten Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a38a063b05d033a92defa86ff2cc77e2fdaa2b7a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3906e-102">Planen des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3906e-103">_**Letztes Änderungsstand des Themas:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="3906e-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="3906e-104">Die Informationen in diesem Thema beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="3906e-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="3906e-105">Das standortbasierte Routing ermöglicht das Einschränken des Routings von anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Parteien im Anruf.</span><span class="sxs-lookup"><span data-stu-id="3906e-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="3906e-106">Das standortbasierte Routing ist Teil der lync Server 2013 Enterprise-VoIP-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="3906e-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="3906e-107">Das standortbasierte Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 ku1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3906e-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="3906e-108">Es erzwingt Anruf Autorisierungsregeln, ob Anrufe basierend auf dem geografischen Standort des lync-Anrufers an PBX-oder PSTN-Endpunkte weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="3906e-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3906e-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3906e-109">In This Section</span></span>

  - [<span data-ttu-id="3906e-110">Übersicht über das standortbasierte Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="3906e-111">Leitfaden für standortbasiertes Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="3906e-112">Szenarien für das standortbasierte Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="3906e-113">Technische Überlegungen zum standortbasierten Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="3906e-114">Client-und Server Unterstützung für standortbasiertes Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="3906e-115">Von Standort basiertem Routing in lync Server 2013 nicht unterstützte Funktionen</span><span class="sxs-lookup"><span data-stu-id="3906e-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="3906e-116">Bereitstellungsprozess für standortbasiertes Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="3906e-117">Standortbasiertes Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3906e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3906e-118">See Also</span></span>


[<span data-ttu-id="3906e-119">Planung von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3906e-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

