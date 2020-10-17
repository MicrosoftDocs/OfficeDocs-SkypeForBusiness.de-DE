---
title: 'Lync Server 2013: Planen des Location-Based Routings'
description: 'Lync Server 2013: Planen des Location-Based Routings.'
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
ms.openlocfilehash: 894a596e998fe07b97ad7911441eced670ba85b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553081"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="9a259-103">Planen von Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-103">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a259-104">_**Letztes Änderungsstand des Themas:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="9a259-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="9a259-105">Die Informationen in diesem Thema beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="9a259-105">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="9a259-106">Location-Based Routing ermöglicht es, das Routing von anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Parteien im Anruf einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="9a259-106">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="9a259-107">Location-Based Routing ist Teil der lync Server 2013 Enterprise-VoIP-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="9a259-107">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="9a259-108">Location-Based Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 ku1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9a259-108">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="9a259-109">Es erzwingt Anruf Autorisierungsregeln, ob Anrufe basierend auf dem geografischen Standort des lync-Anrufers an PBX-oder PSTN-Endpunkte weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="9a259-109">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a259-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9a259-110">In This Section</span></span>

  - [<span data-ttu-id="9a259-111">Übersicht über Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-111">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="9a259-112">Leitfaden für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-112">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="9a259-113">Szenarien für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-113">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="9a259-114">Technische Überlegungen für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-114">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="9a259-115">Client-und Server Unterstützung für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-115">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="9a259-116">Von Location-Based Routing in lync Server 2013 nicht unterstützte Funktionen</span><span class="sxs-lookup"><span data-stu-id="9a259-116">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="9a259-117">Bereitstellungsprozess für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-117">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="9a259-118">Standortbasiertes Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-118">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a259-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a259-119">See Also</span></span>


[<span data-ttu-id="9a259-120">Planung von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a259-120">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

