---
title: Migrationsphasen
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
ms.openlocfilehash: 19594eb5f0e7c2847dfbbf41795574c01b67d0be
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="1623e-102">Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="1623e-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1623e-103">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1623e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1623e-104">In lync Server 2013 definieren Sie Websites in Ihrem Netzwerk, die lync Server 2013 Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="1623e-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="1623e-105">Bei einer Website handelt es sich um eine Gruppe von Computern, die über ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik Netz verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1623e-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="1623e-106">Ein *Front-End-Pool* ist eine Gruppe von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1623e-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="1623e-107">Ein Pool bietet Skalierbarkeit und Failoverfunktionen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1623e-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="1623e-108">Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1623e-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="1623e-109">Eine Standard Edition-Server, die für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1623e-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="1623e-110">Auf diese Weise können Sie lync Server 2013 Funktionalität zu geringeren Kosten Nutzen, jedoch keine echte Hochverfügbarkeitslösung anbieten.</span><span class="sxs-lookup"><span data-stu-id="1623e-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="1623e-111">In den folgenden Phasen wird der Prozess einer Pool Migration von lync Server 2010 auf lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1623e-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="1623e-112">Bei mehreren Standorten, die mehrere Pools enthalten, sollte jeder einzelne Pool diesen phasenweisen Ansatz durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="1623e-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="1623e-113">Phase 1: Planen der Migration von lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1623e-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="1623e-114">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="1623e-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="1623e-115">Phase 3: Bereitstellen lync Server 2013 pilotpools</span><span class="sxs-lookup"><span data-stu-id="1623e-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="1623e-116">Phase 4: verlagern von Testbenutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="1623e-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="1623e-117">Phase 5: Hinzufügen von lync Server 2013 Edgeserver zu einem Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="1623e-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="1623e-118">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="1623e-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="1623e-119">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="1623e-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="1623e-120">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="1623e-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

