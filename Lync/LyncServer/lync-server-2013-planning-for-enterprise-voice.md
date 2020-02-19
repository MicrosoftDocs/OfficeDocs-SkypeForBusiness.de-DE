---
title: 'Lync Server 2013: Planung von Enterprise-VoIP'
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
ms.openlocfilehash: 8bac9e4020ae29ec7ff6ec85a42ae0ee5d30d3af
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="37949-102">Planung von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37949-103">_**Letztes Änderungsstand des Themas:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="37949-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="37949-104">Der Bereitstellungsprozess für Enterprise-VoIP hängt von der vorhandenen Topologie, der Infrastruktur und der Enterprise-VoIP-Funktionalität ab, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="37949-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="37949-105">Die erforderlichen Verfahren hängen davon ab, welche Funktionen Sie auswählen, aber es gibt andere Planungsüberlegungen, die Sie auf einer hohen Ebene vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="37949-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="37949-106">Im Allgemeinen sollten Sie den Typ und die Anzahl der Websites, die Sie bereitstellen möchten, sowie deren geographische Standorte, das Anrufvolumen an jedem Standort, die Arten von Netzwerkverbindungen, die Standorte verbinden, unabhängig davon, ob Sie Redundanz und Failover für die VoIP-Funktionen für die einzelnen Website, und ob Sie vorhandene PBX-Geräte verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="37949-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="37949-107">Es gibt bestimmte Überlegungen, beispielsweise hohe Verfügbarkeit, die Sie berücksichtigen sollten, wenn Sie lync Server Kommunikationssoftware als Ganzes planen.</span><span class="sxs-lookup"><span data-stu-id="37949-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="37949-108">Diese Überlegungen werden bei Bedarf in Themen in diesem Abschnitt behandelt.</span><span class="sxs-lookup"><span data-stu-id="37949-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="37949-109">Planungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="37949-109">Planning Considerations</span></span>

<span data-ttu-id="37949-110">Informationen zu Planungsentscheidungen, die sich auf die Bereitstellung einer bestimmten Enterprise-VoIP-Funktion oder eines Bereitstellungsszenarios oder einer Komponente beziehen, finden Sie in den Themen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="37949-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="37949-111">Definieren der Anforderungen für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="37949-112">Schätzen der VoIP-Nutzung und des Datenverkehrs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="37949-113">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="37949-114">Erforderliche Komponenten für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="37949-115">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="37949-116">Planen der Integration von Exchange Unified Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="37949-117">Planung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="37949-118">Planung von Notrufdiensten (E9-1-1) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="37949-119">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="37949-120">Planen privater Telefonleitungen mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="37949-121">Planen des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="37949-122">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="37949-123">Bereitstellungsrichtlinien für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="37949-124">Übersicht über den Bereitstellungsprozess für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="37949-125">Verschieben von Benutzern zu Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="37949-126">Tool für die lync-voranruf Diagnose in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37949-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

