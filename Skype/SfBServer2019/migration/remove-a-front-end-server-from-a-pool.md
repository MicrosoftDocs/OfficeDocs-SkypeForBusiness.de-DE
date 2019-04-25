---
title: Entfernen eines Front-End-Servers aus einem Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Der Front-End-Server kann nicht als eigenständiger Computer vorhanden sein. Sie müssen als Front-End-Pool definiert werden, auch wenn Sie nur ein einzigen Computer im Pool vorhanden ist.
ms.openlocfilehash: f026570f0dff377ba7ca0c28975a685e236a9e13
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231430"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c65d6-104">Entfernen eines Front-End-Servers aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="c65d6-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="c65d6-105">Der Front-End-Server kann nicht als eigenständiger Computer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c65d6-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="c65d6-106">Sie müssen als Front-End-Pool definiert werden, auch wenn Sie nur ein einzigen Computer im Pool vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c65d6-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="c65d6-107">In diesem Thema führt Sie durch den Vorgang des Entfernens von einem einzelnen Front-End-Server von einem vorhandenen Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="c65d6-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="c65d6-108">Wenn der Front-End-Server der letzte Server im Pool ist oder wenn Sie den Pool vollständig entfernen möchten, finden Sie unter [Entfernen eines Front-End-Pool oder Standard Edition-Server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="c65d6-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="c65d6-109">Es besteht keine Notwendigkeit der einzelnen Front-End-Server zu entfernen, bevor Sie den Front-End-Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="c65d6-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="c65d6-110">Wenn Sie den Pool zu entfernen, entfernen Sie jedem Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="c65d6-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c65d6-111">So entfernen einen Front-End-Server aus einem pool</span><span class="sxs-lookup"><span data-stu-id="c65d6-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="c65d6-112">Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c65d6-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="c65d6-113">Navigieren Sie zu der Knoten legacy installieren.</span><span class="sxs-lookup"><span data-stu-id="c65d6-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="c65d6-114">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool mit dem Front-End-Server, den Sie entfernen rechten Maustaste auf den Front-End-Server, die Sie entfernen möchten, und klicken Sie dann auf **Löschen**möchten.</span><span class="sxs-lookup"><span data-stu-id="c65d6-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

