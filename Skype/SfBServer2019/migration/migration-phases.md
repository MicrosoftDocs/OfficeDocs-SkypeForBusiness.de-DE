---
title: Migrationsphasen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server 2019 definieren Sie Websites in Ihrem Netzwerk, die Skype for Business Server 2019-Komponenten enthalten. Bei einer Website handelt es sich um eine Gruppe von Computern, die durch ein Hochgeschwindigkeits-Netzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik-Netzwerk verbunden sind.
ms.openlocfilehash: b7d7fbddfe77c1303f0f6bde95827d94d7483f32
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813423"
---
# <a name="migration-phases"></a><span data-ttu-id="2d572-104">Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="2d572-104">Migration phases</span></span>

<span data-ttu-id="2d572-105">In Skype for Business Server 2019 definieren Sie Websites in Ihrem Netzwerk, die Skype for Business Server 2019-Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="2d572-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="2d572-106">Bei einer Website handelt es sich um eine Gruppe von Computern, die durch ein Hochgeschwindigkeits-Netzwerk mit niedriger Latenz gut verbunden sind, beispielsweise ein einzelnes lokales Netzwerk (LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Fiberoptik-Netzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="2d572-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="2d572-107">Bei einem Front-End-Pool handelt es sich um einen Satz von Front-End-Servern, die identisch konfiguriert sind und zusammenarbeiten, um Dienste für eine gemeinsame Gruppe von Benutzern bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d572-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="2d572-108">Ein Pool bietet ihren Benutzern Skalierbarkeit und Failover-Funktion.</span><span class="sxs-lookup"><span data-stu-id="2d572-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="2d572-109">Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d572-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="2d572-110">Ein Standard Edition-Server, der für kleine Organisationen entwickelt wurde, definiert auch einen Pool und wird auf einem einzelnen Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2d572-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="2d572-111">So können Sie die Funktionalität von Skype for Business Server 2019 zu geringeren Kosten Nutzen, jedoch keine echte Lösung mit hoher Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="2d572-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="2d572-112">In den folgenden Phasen wird der Prozess der Migration eines Pools zu Skype for Business Server 2019 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d572-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="2d572-113">Für mehrere Websites, die mehrere Pools enthalten, sollte jeder einzelne Pool diesem phasenweisen Ansatz folgen.</span><span class="sxs-lookup"><span data-stu-id="2d572-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="2d572-114">Phase 1: Planen der Migration</span><span class="sxs-lookup"><span data-stu-id="2d572-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="2d572-115">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="2d572-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="2d572-116">Phase 3: Bereitstellen des pilotpools für Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="2d572-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="2d572-117">Phase 4: Verschieben von Testbenutzern in den Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="2d572-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="2d572-118">Phase 5: Hinzufügen von Skype for Business Server 2019 Edge Server zum Pilot Pool</span><span class="sxs-lookup"><span data-stu-id="2d572-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="2d572-119">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="2d572-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="2d572-120">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="2d572-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="2d572-121">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="2d572-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

