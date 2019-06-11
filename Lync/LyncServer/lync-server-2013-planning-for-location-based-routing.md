---
title: 'Lync Server 2013: Planung des standortbasierten Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3873e8710d6ab70212de7780ef5f34d1436df1d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="312e3-102">Planung des standortbasierten Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="312e3-103">_**Letztes Änderungsdatum des Themas:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="312e3-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="312e3-104">Die Informationen in diesem Thema beziehen sich auf kumulierte Updates für Lync Server 2013: February 2013.</span><span class="sxs-lookup"><span data-stu-id="312e3-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="312e3-105">Standortbasiertes Routing ermöglicht das Einschränken des Routings von anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Gesprächspartner.</span><span class="sxs-lookup"><span data-stu-id="312e3-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="312e3-106">Standortbasiertes Routing ist Teil der lync Server 2013 Enterprise Voice-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="312e3-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="312e3-107">Standortbasiertes Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 CU1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="312e3-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="312e3-108">Sie erzwingt Anruf Autorisierungsregeln, um festzulegen, ob Anrufe auf der Grundlage des geografischen Standorts des lync-Anrufers an PBX-oder PSTN-Endpunkte weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="312e3-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="312e3-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="312e3-109">In This Section</span></span>

  - [<span data-ttu-id="312e3-110">Übersicht über standortbasiertes Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="312e3-111">Anleitungen für das standortbasierte Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="312e3-112">Szenarien für das standortbasierte Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="312e3-113">Technische Überlegungen zum standortbasierten Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="312e3-114">Client- und Serverunterstützung für standortbasiertes Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="312e3-115">Vom standortbasierten Routing nicht unterstützte Funktionen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="312e3-116">Bereitstellungsvorgang beim standortbasierten Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="312e3-117">Standortbasiertes Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="312e3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="312e3-118">See Also</span></span>


[<span data-ttu-id="312e3-119">Planen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="312e3-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

