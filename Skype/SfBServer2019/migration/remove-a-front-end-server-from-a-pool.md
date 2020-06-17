---
title: Entfernen eines Front-End-Servers aus einem Pool
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
description: Das Front-End-Server kann nicht als eigenständiger Computer vorhanden sein. Er muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752317"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="d05ee-104">Entfernen eines Front-End-Servers aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="d05ee-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="d05ee-105">Das Front-End-Server kann nicht als eigenständiger Computer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d05ee-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="d05ee-106">Er muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.</span><span class="sxs-lookup"><span data-stu-id="d05ee-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="d05ee-107">In diesem Thema wird erläutert, wie Sie eine einzelne Front-End-Server aus einer vorhandenen Front-End-Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="d05ee-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="d05ee-108">Wenn der Front-End-Server der letzte Server im Pool ist oder wenn Sie den Pool vollständig entfernen, finden Sie weitere Informationen unter [Entfernen von Front-End-Pool oder Standard Edition-Server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="d05ee-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="d05ee-109">Es ist nicht erforderlich, die einzelnen Front-End-Server zu entfernen, bevor Sie die Front-End-Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="d05ee-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="d05ee-110">Wenn Sie den Pool entfernen, entfernen Sie die einzelnen Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="d05ee-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="d05ee-111">So entfernen Sie einen Front-End-Server aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="d05ee-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="d05ee-112">Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="d05ee-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="d05ee-113">Navigieren Sie zum Knoten Legacy Installation.</span><span class="sxs-lookup"><span data-stu-id="d05ee-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="d05ee-114">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie die Front-End-Pool mit der Front-End-Server, die Sie entfernen möchten, klicken Sie mit der rechten Maustaste auf das Front-End-Server, das Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d05ee-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

