---
title: Verwalten von Front-End-Servern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Front-End-Server in Skype for Business Server hinzufügen, entfernen, Patchen oder aktualisieren.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098413"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="7a533-103">Verwalten von Front-End-Servern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7a533-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="7a533-104">In diesem Artikel wird erläutert, wie Sie Front-End-Server hinzufügen oder entfernen und wie Sie Upgrades oder Patches auf Front-End-Server anwenden.</span><span class="sxs-lookup"><span data-stu-id="7a533-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="7a533-105">Skype for Business Server 2019 unterstützt keine Enterprise Edition-Front-End-Pools mit zwei Front-End-Servern und lässt nicht zu, dass die Topologie in diesem Szenario veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="7a533-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="7a533-106">Hinzufügen oder Entfernen von Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="7a533-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="7a533-107">Wenn Sie einem Pool einen Front-End-Server hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool anschließend neu starten.</span><span class="sxs-lookup"><span data-stu-id="7a533-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7a533-108">Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, führt dies dazu, dass alle Server im Pool gleichzeitig neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7a533-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="7a533-109">Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die Benutzer unterbrochen wird, die mit diesem Pool verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="7a533-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="7a533-110">Um eine Unterbrechung des Diensts für Benutzer zu verhindern, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten.</span><span class="sxs-lookup"><span data-stu-id="7a533-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="7a533-111">Sie können das folgende Verfahren verwenden, wenn Sie ein Front-End-Server hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="7a533-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a533-112">Wenn Sie dem Pool neue Server hinzufügen, aktualisieren Sie die neuen Pool Server so, dass Sie auf der gleichen kumulativen Update Ebene wie die vorhandenen Server im Pool sind.</span><span class="sxs-lookup"><span data-stu-id="7a533-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="7a533-113">So können Sie Front-End-Server hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="7a533-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="7a533-114">If you are removing any Front End Servers, first stop new connections to those servers.</span><span class="sxs-lookup"><span data-stu-id="7a533-114">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="7a533-115">To do so, you can use the following cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7a533-115">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="7a533-116">Öffnen Sie den Topologie-Generator, und fügen Sie die benötigten Server hinzu, oder entfernen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="7a533-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="7a533-117">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="7a533-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7a533-118">Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, führt dies dazu, dass alle Server im Pool gleichzeitig neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7a533-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="7a533-119">Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die Benutzer unterbrochen wird, die mit diesem Pool verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="7a533-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="7a533-120">Um eine Unterbrechung des Diensts für Benutzer zu verhindern, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten.</span><span class="sxs-lookup"><span data-stu-id="7a533-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="7a533-121">Wenn Sie einen Server zum Pool hinzufügen oder entfernen, müssen Sie den Assistenten für die Skype for Business Server-Bereitstellung auf jedem Computer ausführen, der hinzugefügt oder entfernt wurde, weitere Informationen finden Sie unter [install Skype for Business Server on Servers in The Topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="7a533-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="7a533-122">Wenn Sie die Anzahl der Server in Ihrem Front-End-Pool auf eine der folgenden Arten geändert haben, setzen Sie den Pool durch Eingeben des folgenden Cmdlets zurück: Reset-CsPoolRegistrarState-resettype FullReset-poolfqdn "</span><span class="sxs-lookup"><span data-stu-id="7a533-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="7a533-123">2 bis any</span><span class="sxs-lookup"><span data-stu-id="7a533-123">2 to any</span></span>
    
     - <span data-ttu-id="7a533-124">Beliebig bis 2</span><span class="sxs-lookup"><span data-stu-id="7a533-124">Any to 2</span></span>
    
     - <span data-ttu-id="7a533-125">3 bis any</span><span class="sxs-lookup"><span data-stu-id="7a533-125">3 to any</span></span>
    
     - <span data-ttu-id="7a533-126">Beliebig bis 3</span><span class="sxs-lookup"><span data-stu-id="7a533-126">Any to 3</span></span>
    
5. <span data-ttu-id="7a533-127">Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="7a533-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="7a533-128">Patchen oder Aktualisieren von Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="7a533-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="7a533-129">Wenn Sie die Server in einem Front-End-Pool Patchen, tun Sie dies jeweils auf einem Server.</span><span class="sxs-lookup"><span data-stu-id="7a533-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="7a533-130">So wenden Sie ein Upgrade auf die Front-End-Server in einem Pool an</span><span class="sxs-lookup"><span data-stu-id="7a533-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="7a533-131">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="7a533-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="7a533-132">Wenn in diesem Cmdlet fehlende Replikate angezeigt werden, führen Sie das folgende Cmdlet aus, um den Pool wiederherzustellen, bevor Sie Patches anwenden.</span><span class="sxs-lookup"><span data-stu-id="7a533-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="7a533-133">Führen Sie auf dem ersten Server, den Sie Patchen möchten, das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="7a533-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="7a533-134">Mit diesem Cmdlet werden alle Dienste auf andere Front-End-Server im Pool verschoben, und dieser Server wird offline geschaltet.</span><span class="sxs-lookup"><span data-stu-id="7a533-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="7a533-135">Wenden Sie das Upgrade oder Patch auf diesen Server an.</span><span class="sxs-lookup"><span data-stu-id="7a533-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="7a533-136">Führen Sie auf dem aktualisierten Server das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="7a533-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="7a533-137">Der Server wird an den Dienst zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7a533-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="7a533-138">Wiederholen Sie die Schritte 2-4 für jeden Server, der aktualisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="7a533-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
