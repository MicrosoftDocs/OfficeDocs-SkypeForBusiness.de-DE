---
title: Migrationsphasen
description: Migrationsphasen.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72ef47cb9b6c9eba75c395eb9bd94c887ca5a433
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547051"
---
# <a name="migration-phases"></a><span data-ttu-id="72069-103">Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="72069-103">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72069-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="72069-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="72069-105">In lync Server 2013 definieren Sie Websites in Ihrem Netzwerk, die lync Server 2013 Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="72069-105">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="72069-106">Bei einer Website handelt es sich um eine Gruppe von Computern, die über ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik Netz verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="72069-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="72069-107">Ein *Front-End-Pool* ist eine Gruppe von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="72069-107">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="72069-108">Ein Pool bietet Skalierbarkeit und Failoverfunktionen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="72069-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="72069-109">Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72069-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="72069-110">Eine Standard Edition-Server, die für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72069-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="72069-111">Auf diese Weise können Sie lync Server 2013 Funktionalität zu geringeren Kosten Nutzen, jedoch keine echte Hochverfügbarkeitslösung anbieten.</span><span class="sxs-lookup"><span data-stu-id="72069-111">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="72069-112">In den folgenden Phasen wird der Prozess einer Pool Migration von lync Server 2010 auf lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72069-112">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="72069-113">Bei mehreren Standorten, die mehrere Pools enthalten, sollte jeder einzelne Pool diesen phasenweisen Ansatz durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="72069-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="72069-114">Phase 1: Planen der Migration von lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="72069-114">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="72069-115">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="72069-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="72069-116">Phase 3: Bereitstellen lync Server 2013 pilotpools</span><span class="sxs-lookup"><span data-stu-id="72069-116">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="72069-117">Phase 4: verlagern von Testbenutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="72069-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="72069-118">Phase 5: Hinzufügen von lync Server 2013 Edgeserver zu einem Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="72069-118">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="72069-119">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="72069-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="72069-120">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="72069-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="72069-121">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="72069-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

