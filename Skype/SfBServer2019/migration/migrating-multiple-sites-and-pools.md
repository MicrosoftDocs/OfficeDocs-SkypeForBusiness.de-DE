---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server 2019 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools. Der Vorgang der Migration mehrerer Pools zu Skype for Business Server 2019 erfordert folgende Überlegungen:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752657"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="58156-104">Migrieren von mehreren Standorten und Pools</span><span class="sxs-lookup"><span data-stu-id="58156-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="58156-105">Skype for Business Server 2019 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools.</span><span class="sxs-lookup"><span data-stu-id="58156-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="58156-106">Der Vorgang der Migration mehrerer Pools zu Skype for Business Server 2019 erfordert folgende Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="58156-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="58156-107">Nachdem Sie einen Skype for Business Server 2019-Pilot Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den Skype for Business Server 2019-Pool verschoben werden, und eine Methode zur Überprüfung der Funktionalität der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="58156-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="58156-108">Nachdem Sie beispielsweise einen Benutzer in den Pilot Pool verschoben haben, stellen Sie sicher, dass die konferenzrichtlinie des Benutzers zu Skype for Business Server 2019 verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="58156-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="58156-109">Nachdem Sie eine Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="58156-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="58156-110">Beständiger Chat, SQL-Spiegelung und XMPP-Funktionalität sind in Skype for Business Server 2019 veraltet und nicht mehr als Skype for Business Server 2019-Features verfügbar, aber Sie können in einer Umgebung mit Koexistenz fortgesetzt werden, wenn Sie zuvor in einer Legacyumgebung bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="58156-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="58156-111">Wenn Sie diese Funktionen weiterhin verwenden möchten, sollten Sie mit einer Koexistenz-Umgebung fortfahren, in der bestimmte Benutzer in älteren Pools verbleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="58156-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="58156-112">Nach dem Übergang der Edgeserver der Verbund Routen zu den Pilot Skype for Business Server 2019-Edgeserver müssen Sie überprüfen, ob Verbundbenutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="58156-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="58156-113">Nachdem Sie alle Benutzer und nicht-Benutzer Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Legacy Pool leer ist.</span><span class="sxs-lookup"><span data-stu-id="58156-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="58156-114">Nachdem Sie überprüft haben, dass der Legacy Pool leer ist, können Sie den Pool deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="58156-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="58156-115">Ausführliche Informationen zum Deaktivieren des Legacy Pools und der Server finden Sie unter [Phase 8: decommission Legacy Pools](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="58156-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

