---
title: 'Lync Server 2013: Planung von Enterprise-VoIP'
description: 'Lync Server 2013: Planung für Enterprise-VoIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dfa0d91fe8270e49524d648ef403cd69ede2407
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571851"
---
# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="ccc44-103">Planung von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-103">Planning for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc44-104">_**Letztes Änderungsstand des Themas:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="ccc44-104">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="ccc44-105">Der Bereitstellungsprozess für Enterprise-VoIP hängt von der vorhandenen Topologie, der Infrastruktur und der Enterprise-VoIP-Funktionalität ab, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="ccc44-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="ccc44-106">Die erforderlichen Verfahren hängen davon ab, welche Funktionen Sie auswählen, aber es gibt andere Planungsüberlegungen, die Sie auf einer hohen Ebene vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="ccc44-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="ccc44-107">Im Allgemeinen sollten Sie den Typ und die Anzahl der Websites, die Sie bereitstellen möchten, sowie deren geografische Standorte, das Anrufvolumen an jedem Standort, die Arten von Netzwerkverbindungen, die Standorte verbinden, festlegen, ob Redundanz und Failover für die VoIP-Funktionen für die einzelnen Standorte bereitgestellt werden sollen und ob vorhandene PBX-Anlagen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ccc44-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="ccc44-108">Es gibt bestimmte Überlegungen, beispielsweise hohe Verfügbarkeit, die Sie berücksichtigen sollten, wenn Sie lync Server Kommunikationssoftware als Ganzes planen.</span><span class="sxs-lookup"><span data-stu-id="ccc44-108">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="ccc44-109">Diese Überlegungen werden bei Bedarf in Themen in diesem Abschnitt behandelt.</span><span class="sxs-lookup"><span data-stu-id="ccc44-109">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="ccc44-110">Planungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="ccc44-110">Planning Considerations</span></span>

<span data-ttu-id="ccc44-111">Informationen zu Planungsentscheidungen, die sich auf die Bereitstellung einer bestimmten Enterprise-VoIP-Funktion oder eines Bereitstellungsszenarios oder einer Komponente beziehen, finden Sie in den Themen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ccc44-111">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="ccc44-112">Definieren der Anforderungen für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-112">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="ccc44-113">Schätzen der VoIP-Nutzung und des Datenverkehrs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-113">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="ccc44-114">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-114">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="ccc44-115">Erforderliche Komponenten für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-115">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="ccc44-116">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-116">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="ccc44-117">Planen der Integration von Exchange Unified Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-117">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="ccc44-118">Planung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-118">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="ccc44-119">Planung von Notrufdiensten (E9-1-1) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-119">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="ccc44-120">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-120">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="ccc44-121">Planen privater Telefonleitungen mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-121">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="ccc44-122">Planen von Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-122">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="ccc44-123">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-123">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="ccc44-124">Bereitstellungsrichtlinien für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-124">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="ccc44-125">Übersicht über den Bereitstellungsprozess für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-125">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="ccc44-126">Verschieben von Benutzern zu Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-126">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="ccc44-127">Tool für die lync-voranruf Diagnose in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc44-127">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

