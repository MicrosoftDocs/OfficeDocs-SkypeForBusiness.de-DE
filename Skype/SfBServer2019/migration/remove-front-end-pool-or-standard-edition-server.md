---
title: Entfernen eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dieses Thema führt Sie durch den Vorgang zum Entfernen eines Front-End-Pools oder eines Front-End-Servers der Standard Edition. Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jeden Front-End-Server, der zum Pool gehört, als Teil des Prozesses zum Entfernen des Pools. Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL Store-Definition aus dem Topology Builder entfernen.
ms.openlocfilehash: fd43682fca67b961ac93c01813ca6ea9e702b644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301132"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="94518-105">Entfernen eines Front-End-Pools oder Standard Edition-Servers</span><span class="sxs-lookup"><span data-stu-id="94518-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="94518-106">Dieser Artikel führt Sie durch den Vorgang zum Entfernen eines Front-End-Pools oder eines Standard Edition-Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="94518-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="94518-107">Wenn Sie einen Front-End-Pool entfernen, entfernen Sie jeden Front-End-Server, der zum Pool gehört, als Teil des Prozesses zum Entfernen des Pools.</span><span class="sxs-lookup"><span data-stu-id="94518-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="94518-108">Wenn Sie einen Standard Edition-Front-End-Server entfernen, müssen Sie die SQL Store-Definition aus dem Topology Builder entfernen.</span><span class="sxs-lookup"><span data-stu-id="94518-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="94518-109">So entfernen Sie einen Front-End-Server Pool</span><span class="sxs-lookup"><span data-stu-id="94518-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="94518-110">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="94518-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="94518-111">Navigieren Sie zum Legacy Knoten.</span><span class="sxs-lookup"><span data-stu-id="94518-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="94518-112">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool, klicken Sie mit der rechten Maustaste auf den zu entfernenden Frontend-Pool, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="94518-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="94518-113">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie den Legacy Bereitstellungs-Assistenten nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="94518-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="94518-114">So entfernen Sie einen Front-End-Server der Standard Edition</span><span class="sxs-lookup"><span data-stu-id="94518-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="94518-115">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="94518-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="94518-116">Navigieren Sie zum Knoten Legacy Installationen.</span><span class="sxs-lookup"><span data-stu-id="94518-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="94518-117">Erweitern Sie die **Standard Edition-Front-End-Server**, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="94518-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="94518-118">Erweitern Sie **SQL Stores**, klicken Sie mit der rechten Maustaste auf die SQL Server-Datenbank, die dem Front-End-Server der Standard Edition zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="94518-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="94518-119">Sie müssen die Definition der SQL Server-Datenbanken vom Standard Edition-Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="94518-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="94518-120">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Bereitstellungs-Assistenten nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="94518-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

