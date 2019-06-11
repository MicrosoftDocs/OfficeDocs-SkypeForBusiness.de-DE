---
title: Migrationsphasen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="3a889-102">Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="3a889-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a889-103">_**Letztes Änderungsdatum des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="3a889-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="3a889-104">In lync Server 2013 definieren Sie Websites in Ihrem Netzwerk, die lync Server 2013-Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="3a889-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="3a889-105">Bei einer Website handelt es sich um eine Gruppe von Computern, die durch ein Hochgeschwindigkeits-Netzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik-Netzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="3a889-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="3a889-106">Bei einem *Front-End-Pool* handelt es sich um einen Satz von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3a889-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="3a889-107">Ein Pool bietet ihren Benutzern Skalierbarkeit und Failover-Funktion.</span><span class="sxs-lookup"><span data-stu-id="3a889-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="3a889-108">Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3a889-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="3a889-109">Ein Standard Edition-Server, der für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a889-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="3a889-110">Dies ermöglicht Ihnen, lync Server 2013-Funktionen zu einem niedrigeren Preis zu nutzen, bietet jedoch keine echte Lösung mit hoher Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="3a889-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="3a889-111">In den folgenden Phasen wird der Prozess einer Pool Migration von lync Server 2010 zu lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a889-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="3a889-112">Für mehrere Websites, die mehrere Pools enthalten, sollte jeder einzelne Pool diesem phasenweisen Ansatz folgen.</span><span class="sxs-lookup"><span data-stu-id="3a889-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="3a889-113">Phase 1: Planen der Migration von lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3a889-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="3a889-114">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="3a889-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="3a889-115">Phase 3: Bereitstellen des lync Server 2013-pilotpools</span><span class="sxs-lookup"><span data-stu-id="3a889-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="3a889-116">Phase 4: Verschieben von Testbenutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="3a889-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="3a889-117">Phase 5: Hinzufügen von lync Server 2013 Edge-Server zu Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="3a889-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="3a889-118">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="3a889-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="3a889-119">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="3a889-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="3a889-120">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="3a889-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

