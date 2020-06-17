---
title: Entfernen eines Front-End-Pools oder Standard Edition-Servers
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
description: In diesem Thema werden Sie durch den Vorgang zum Entfernen einer Front-End-Pool oder einer Standard Edition Front-End-Server geführt. Wenn Sie ein Front-End-Pool entfernen, entfernen Sie alle Front-End-Server, die zum Pool gehören, als Teil des Prozesses zur Pool Entfernung. Wenn Sie eine Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-speicherdefinition aus dem Topologie-Generator entfernen.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752277"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="d5779-105">Entfernen eines Front-End-Pools oder Standard Edition-Servers</span><span class="sxs-lookup"><span data-stu-id="d5779-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="d5779-106">Dieser Artikel führt Sie durch den Vorgang des Entfernens einer Front-End-Pool oder einer Standard Edition Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="d5779-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="d5779-107">Wenn Sie ein Front-End-Pool entfernen, entfernen Sie alle Front-End-Server, die zum Pool gehören, als Teil des Prozesses zur Pool Entfernung.</span><span class="sxs-lookup"><span data-stu-id="d5779-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="d5779-108">Wenn Sie eine Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-speicherdefinition aus dem Topologie-Generator entfernen.</span><span class="sxs-lookup"><span data-stu-id="d5779-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="d5779-109">So entfernen Sie einen Front-End-Server-Pool</span><span class="sxs-lookup"><span data-stu-id="d5779-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="d5779-110">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="d5779-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d5779-111">Navigieren Sie zum Knoten Legacy.</span><span class="sxs-lookup"><span data-stu-id="d5779-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="d5779-112">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie die Front-End-Pool, klicken Sie mit der rechten Maustaste auf das Front-End-Pool, das Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d5779-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="d5779-113">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die Legacy Bereitstellung bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="d5779-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="d5779-114">So entfernen Sie einen Standard Edition-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="d5779-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="d5779-115">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="d5779-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d5779-116">Navigieren Sie zum Knoten Legacy Installationen.</span><span class="sxs-lookup"><span data-stu-id="d5779-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="d5779-117">Erweitern Sie **Standard Edition-Front-End-Server**, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d5779-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="d5779-118">Erweitern Sie **SQL-Speicher**, klicken Sie mit der rechten Maustaste auf die SQL Server Datenbank, die der Standard Edition Front-End-Server zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d5779-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d5779-119">Sie müssen die Definition der verbundenen SQL Server Datenbanken aus der Standard Edition Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="d5779-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="d5779-120">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Bereitstellungs-Assistenten nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="d5779-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

