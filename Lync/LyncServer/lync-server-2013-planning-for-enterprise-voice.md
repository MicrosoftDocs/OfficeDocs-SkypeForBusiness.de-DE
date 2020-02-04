---
title: 'Lync Server 2013: Planung für Enterprise-VoIP'
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
ms.openlocfilehash: 83b0ec944ad857ffccb419cf9ed36fbca92306c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41753255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d817b-102">Planen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d817b-103">_**Letztes Änderungsdatum des Themas:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="d817b-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="d817b-104">Der Bereitstellungsprozess für Enterprise-VoIP hängt von Ihrer vorhandenen Topologie, Infrastruktur und der Enterprise-VoIP-Funktionalität ab, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="d817b-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="d817b-105">Die erforderlichen Verfahren hängen von den von Ihnen ausgewählten Funktionen ab, aber Sie müssen weitere allgemeine Planungsentscheidungen treffen.</span><span class="sxs-lookup"><span data-stu-id="d817b-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="d817b-106">In der Regel sollten Sie den Typ und die Anzahl der Websites, die Sie bereitstellen möchten, und deren geographische Speicherorte, das Anrufaufkommen an jedem Standort, die Typen von Netzwerk Links, die Websites verbinden, und zwar unabhängig davon, ob Sie Redundanz und Failover für die Sprachfunktionalität für jeden verwenden möchten. Website, und ob Sie vorhandene PBX-Anlagen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d817b-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="d817b-107">Es gibt bestimmte Überlegungen, wie beispielsweise die Höchstverfügbarkeit, die Sie berücksichtigen sollten, wenn Sie die lync Server-Kommunikationssoftware als Ganzes planen.</span><span class="sxs-lookup"><span data-stu-id="d817b-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="d817b-108">Diese Überlegungen werden nach Bedarf in den Themen in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="d817b-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="d817b-109">Planungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="d817b-109">Planning Considerations</span></span>

<span data-ttu-id="d817b-110">Informationen zu Planungsentscheidungen, die sich auf die Bereitstellung einer bestimmten Enterprise-VoIP-Funktion oder eines Bereitstellungsszenarios oder einer Komponente beziehen, finden Sie in den Themen in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="d817b-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="d817b-111">Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="d817b-112">Schätzen von VoIP-Nutzung und -Datenverkehr für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="d817b-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="d817b-114">Components required for Enterprise Voice in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="d817b-115">Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="d817b-116">Planen der Integration von Exchange Unified Messaging in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="d817b-117">Planen des Anrufsteuerungsdiensts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="d817b-118">Planen von Notrufdiensten (E9-1-1) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="d817b-119">Planung der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="d817b-120">Planen privater Telefonleitungen mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="d817b-121">Planung des standortbasierten Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="d817b-122">Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="d817b-123">Richtlinien für die Enterprise-VoIP-Bereitstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="d817b-124">Übersicht über den Bereitstellungsprozess für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="d817b-125">Verschieben von Benutzern zu Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="d817b-126">Lync-Tool für die voranruf Diagnose in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d817b-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

