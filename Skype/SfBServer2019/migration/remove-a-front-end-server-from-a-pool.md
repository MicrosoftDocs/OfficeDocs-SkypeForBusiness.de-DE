---
title: Entfernen eines Front-End-Servers aus einem Pool
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
description: Der Front-End-Server kann nicht als eigenständiger Computer vorhanden sein. Es muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813033"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="1298a-104">Entfernen eines Front-End-Servers aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="1298a-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="1298a-105">Der Front-End-Server kann nicht als eigenständiger Computer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1298a-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="1298a-106">Es muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.</span><span class="sxs-lookup"><span data-stu-id="1298a-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="1298a-107">Dieses Thema führt Sie durch den Vorgang zum Entfernen eines einzelnen Front-End-Servers aus einem vorhandenen Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="1298a-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="1298a-108">Wenn der Front-End-Server der letzte Server im Pool ist oder wenn Sie den Pool vollständig entfernen, lesen Sie [Entfernen des Front-End-Pools oder des Standard Edition-Servers](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="1298a-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="1298a-109">Es ist nicht erforderlich, die einzelnen Front-End-Server zu entfernen, bevor Sie den Front-End-Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="1298a-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="1298a-110">Wenn Sie den Pool entfernen, entfernen Sie jeden Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1298a-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="1298a-111">So entfernen Sie einen Front-End-Server aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="1298a-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="1298a-112">Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="1298a-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="1298a-113">Navigieren Sie zum Legacy Installations Knoten.</span><span class="sxs-lookup"><span data-stu-id="1298a-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="1298a-114">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool mit dem zu entfernenden Front-End-Server, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="1298a-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

