---
title: Verwalten von Front-End-Servern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Front-End-Server in Skype for Business Server hinzufügen, entfernen, Patchen oder aktualisieren.'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275157"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="ede82-103">Verwalten von Front-End-Servern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede82-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="ede82-104">In diesem Artikel wird erläutert, wie Sie Front-End-Server hinzufügen oder entfernen und wie Sie Upgrades oder Patches auf Front-End-Server anwenden.</span><span class="sxs-lookup"><span data-stu-id="ede82-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="ede82-105">Hinzufügen oder Entfernen von Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="ede82-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="ede82-106">Wenn Sie einen Front-End-Server zu einem Pool hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool erneut starten.</span><span class="sxs-lookup"><span data-stu-id="ede82-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ede82-p101">Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten.</span><span class="sxs-lookup"><span data-stu-id="ede82-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="ede82-110">Sie können das folgende Verfahren verwenden, wenn Sie einen Front-End-Server hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="ede82-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ede82-111">Wenn Sie neue Server zum Pool hinzufügen, aktualisieren Sie Ihre neuen Poolserver, sodass diese im Hinblick auf das kumulative Update auf demselben Stand sind wie die bereits bestehenden Server in dem Pool.</span><span class="sxs-lookup"><span data-stu-id="ede82-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="ede82-112">So können Sie Front-End-Server hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="ede82-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="ede82-113">Wenn Sie alle Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern.</span><span class="sxs-lookup"><span data-stu-id="ede82-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="ede82-114">Dazu können Sie das folgende Cmdlet verwenden:</span><span class="sxs-lookup"><span data-stu-id="ede82-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="ede82-115">Öffnen Sie den Topologie-Generator, und fügen Sie die erforderlichen Server hinzu, oder entfernen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="ede82-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="ede82-116">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="ede82-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ede82-p103">Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten.</span><span class="sxs-lookup"><span data-stu-id="ede82-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="ede82-120">Wenn Sie dem Pool einen Server hinzufügen oder daraus entfernen, müssen Sie auch den Skype for Business Server-Bereitstellungs-Assistenten auf jedem Computer ausführen, der hinzugefügt oder entfernt wurde, und weitere Informationen finden Sie unter [Installieren von Skype for Business Server auf Servern in der Topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .</span><span class="sxs-lookup"><span data-stu-id="ede82-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="ede82-121">Wenn Sie die Anzahl der Server im Front-End-Pool auf eine der folgenden Arten geändert haben, setzen Sie den Pool zurück, indem Sie folgendes Cmdlet eingeben: Reset-CsPoolRegistrarState-resettype FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="ede82-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="ede82-122">2 bis beliebig</span><span class="sxs-lookup"><span data-stu-id="ede82-122">2 to any</span></span>
    
     - <span data-ttu-id="ede82-123">Beliebig bis 2</span><span class="sxs-lookup"><span data-stu-id="ede82-123">Any to 2</span></span>
    
     - <span data-ttu-id="ede82-124">3 bis beliebig</span><span class="sxs-lookup"><span data-stu-id="ede82-124">3 to any</span></span>
    
     - <span data-ttu-id="ede82-125">Beliebig bis 3</span><span class="sxs-lookup"><span data-stu-id="ede82-125">Any to 3</span></span>
    
5. <span data-ttu-id="ede82-126">Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben</span><span class="sxs-lookup"><span data-stu-id="ede82-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="ede82-127">Patchen oder Aktualisieren der Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="ede82-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="ede82-128">Wenn Sie die Server in einem Front-End-Pool Patchen, tun Sie dies jeweils auf einem Server.</span><span class="sxs-lookup"><span data-stu-id="ede82-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="ede82-129">So führen Sie ein Upgrade für die Front-End-Server in einem Pool durch</span><span class="sxs-lookup"><span data-stu-id="ede82-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="ede82-130">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="ede82-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="ede82-131">Wenn für dieses Cmdlet fehlende Replikate angezeigt werden, führen Sie vor dem Anwenden von Patches das folgende Cmdlet aus, um den Pool wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ede82-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="ede82-132">Führen Sie auf dem ersten Server, auf den ein Patch angewendet werden soll, das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ede82-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="ede82-133">Mit diesem Cmdlet werden alle Dienste auf andere Front-End-Server im Pool verschoben, und der Server wird offline geschaltet.</span><span class="sxs-lookup"><span data-stu-id="ede82-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="ede82-134">Wenden Sie das Upgrade oder Patch auf diesen Server an.</span><span class="sxs-lookup"><span data-stu-id="ede82-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="ede82-135">Führen Sie das folgende Cmdlet auf dem aktualisierten Server aus:</span><span class="sxs-lookup"><span data-stu-id="ede82-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="ede82-136">Der Server ist wieder im Dienst.</span><span class="sxs-lookup"><span data-stu-id="ede82-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="ede82-137">Wiederholen Sie die Schritte 2 bis 4 für jeden einzelnen Server, der ein Upgrade erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="ede82-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
