---
title: Migrationsphasen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype für Business Server 2019 definieren Sie Websites in Ihrem Netzwerk, die Skype für Business Server 2019 Komponenten enthalten. Eine Website ist eine Gruppe von Computern, die über eine gute Verbindung über ein Netzwerk mit hoher Geschwindigkeit und geringer Latenz wie einem einzelnen lokalen Netzwerk (LAN) oder zwei Netzwerke über ein Glasfaserkabel Hochgeschwindigkeits-Fiber-Netzwerk verbunden sind.
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231623"
---
# <a name="migration-phases"></a><span data-ttu-id="b17e3-104">Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="b17e3-104">Migration phases</span></span>

<span data-ttu-id="b17e3-105">In Skype für Business Server 2019 definieren Sie Websites in Ihrem Netzwerk, die Skype für Business Server 2019 Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b17e3-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="b17e3-106">Eine Website ist eine Gruppe von Computern, die über eine gute Verbindung über ein Netzwerk mit hoher Geschwindigkeit und geringer Latenz wie einem einzelnen lokalen Netzwerk (LAN) oder zwei Netzwerke über ein Glasfaserkabel Hochgeschwindigkeits-Fiber-Netzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b17e3-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="b17e3-107">Ein Front-End-Pool ist eine Reihe von Front-End-Servern, die identischer Weise konfiguriert werden und arbeiten zusammen, zum Bereitstellen von Diensten für eine allgemeine Gruppe von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="b17e3-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="b17e3-108">Ein Pool bietet Skalierbarkeit und Failover-Funktionalität für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b17e3-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="b17e3-109">Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b17e3-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="b17e3-110">Ein Standard Edition-Server für kleine Unternehmen entwickelt auch einen Pool definiert und auf einem einzelnen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b17e3-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="b17e3-111">Dies ermöglicht es Ihnen, Skype für Business Server 2019-Funktionalität für eine geringere Kosten zur Verfügung, sondern bietet keine echte Hochverfügbarkeits-Lösung.</span><span class="sxs-lookup"><span data-stu-id="b17e3-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="b17e3-112">Die folgenden Phasen Beschreiben der Migration eines Pools zu Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b17e3-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="b17e3-113">Für mehrere Standorte mit mehreren Pools sollte jeder einzelne Pool dieser Phasen folgen.</span><span class="sxs-lookup"><span data-stu-id="b17e3-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="b17e3-114">Phase 1: Planen der Migration</span><span class="sxs-lookup"><span data-stu-id="b17e3-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="b17e3-115">Phase 2: Vorbereitung der Migration</span><span class="sxs-lookup"><span data-stu-id="b17e3-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="b17e3-116">Phase 3: Bereitstellen von Skype für Business Server 2019 pilot pool</span><span class="sxs-lookup"><span data-stu-id="b17e3-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="b17e3-117">Phase 4: Verschieben von Testbenutzern in den pilotpool</span><span class="sxs-lookup"><span data-stu-id="b17e3-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="b17e3-118">Phase 5: Hinzufügen von Skype für Business Server 2019 Edge-Server zum pilotpool</span><span class="sxs-lookup"><span data-stu-id="b17e3-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="b17e3-119">Phase 6: Migration von der Pilotbereitstellung zur Produktionsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="b17e3-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="b17e3-120">Phase 7: Aufgaben nach der Migration abschließen</span><span class="sxs-lookup"><span data-stu-id="b17e3-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="b17e3-121">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="b17e3-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

