---
title: Entfernen eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Thema führt Sie durch den Vorgang des Entfernens von einem Front-End-Pool oder Standard Edition-Front-End-Servers. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jedem Front-End-Server, die als Teil des Löschvorgangs Pool auf den Pool gehört. Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-Speicher-Definition Topologie-Generator entfernen.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231546"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="0c8c5-105">Entfernen eines Front-End-Pools oder Standard Edition-Servers</span><span class="sxs-lookup"><span data-stu-id="0c8c5-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="0c8c5-106">Dieser Artikel führt Sie durch den Vorgang des Entfernens von einem Front-End-Pool oder Standard Edition-Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="0c8c5-107">Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jedem Front-End-Server, die als Teil des Löschvorgangs Pool auf den Pool gehört.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="0c8c5-108">Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-Speicher-Definition Topologie-Generator entfernen.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="0c8c5-109">So entfernen einen Front-End-Server-pool</span><span class="sxs-lookup"><span data-stu-id="0c8c5-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="0c8c5-110">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0c8c5-111">Navigieren Sie zum Knoten Vorversion.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="0c8c5-112">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool, mit der rechten Maustaste in des Front-End-Pools, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="0c8c5-113">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann bei Bedarf legacy Bereitstellungs-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="0c8c5-114">Entfernen eines Standard Edition-Front-End-Servers</span><span class="sxs-lookup"><span data-stu-id="0c8c5-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="0c8c5-115">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0c8c5-116">Navigieren Sie zum Knoten Vorversion installiert.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="0c8c5-117">Erweitern Sie **Standard Edition-Front-End-Server**rechten Maustaste auf den Front-End-Server, die Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="0c8c5-118">Erweitern Sie **SQL-Speicher**, mit der rechten Maustaste in der SQL Server-Datenbank, die mit dem Standard Edition-Front-End-Server verbunden ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0c8c5-119">Sie müssen die Definition der verbundenen SQL Server-Datenbanken aus dem Standard Edition-Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="0c8c5-120">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus und führen Sie dann je nach Bedarf den Bereitstellungs-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="0c8c5-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

