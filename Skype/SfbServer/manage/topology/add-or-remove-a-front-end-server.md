---
title: Hinzufügen oder Entfernen eines Front-End-Servers in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Informationen Sie zum Hinzufügen oder Entfernen von Front-End-Servern in Skype für Business Server.'
ms.openlocfilehash: 80b0dab56d3adfb08856348b7ec749ef2e91079f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569006"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="54b2a-103">Hinzufügen oder Entfernen eines Front-End-Servers in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="54b2a-103">Add or remove a Front End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="54b2a-104">**Zusammenfassung:** Informationen Sie zum Hinzufügen oder Entfernen von Front-End-Servern in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="54b2a-104">**Summary:** Learn how to add or remove Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="54b2a-105">Wenn Sie einen Front-End-Server zu einem Pool hinzufügen oder eines Front-End-Servers aus einem Pool entfernen, müssen Sie dann den Pool neu starten.</span><span class="sxs-lookup"><span data-stu-id="54b2a-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="54b2a-p101">Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten.</span><span class="sxs-lookup"><span data-stu-id="54b2a-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="54b2a-109">Sie können das folgende Verfahren beim Hinzufügen oder Entfernen eines Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="54b2a-109">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="54b2a-110">Wenn Sie neue Server zum Pool hinzufügen, aktualisieren Sie Ihre neuen Poolserver, sodass diese im Hinblick auf das kumulative Update auf demselben Stand sind wie die bereits bestehenden Server in dem Pool.</span><span class="sxs-lookup"><span data-stu-id="54b2a-110">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="54b2a-111">Zum Hinzufügen oder Entfernen von Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="54b2a-111">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="54b2a-112">Wenn Sie alle Front-End-Server entfernen, beenden Sie zuerst neue Verbindungen mit diesen Servern.</span><span class="sxs-lookup"><span data-stu-id="54b2a-112">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="54b2a-113">Dazu können Sie das folgende Cmdlet verwenden:</span><span class="sxs-lookup"><span data-stu-id="54b2a-113">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="54b2a-114">Öffnen Sie den Topologie-Generator und fügen Sie hinzu oder entfernen Sie die benötigten Server.</span><span class="sxs-lookup"><span data-stu-id="54b2a-114">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="54b2a-115">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="54b2a-115">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="54b2a-p103">Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten.</span><span class="sxs-lookup"><span data-stu-id="54b2a-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
4. <span data-ttu-id="54b2a-119">Wenn Sie die Anzahl der Server im Front-End-Pool in einer der folgenden Methoden geändert haben, müssen Sie den Pool mit dann zurücksetzen, indem Sie das folgende Cmdlet eingeben: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="54b2a-119">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="54b2a-120">2 bis beliebig</span><span class="sxs-lookup"><span data-stu-id="54b2a-120">2 to any</span></span>
    
     - <span data-ttu-id="54b2a-121">Beliebig bis 2</span><span class="sxs-lookup"><span data-stu-id="54b2a-121">Any to 2</span></span>
    
     - <span data-ttu-id="54b2a-122">3 bis beliebig</span><span class="sxs-lookup"><span data-stu-id="54b2a-122">3 to any</span></span>
    
     - <span data-ttu-id="54b2a-123">Beliebig bis 3</span><span class="sxs-lookup"><span data-stu-id="54b2a-123">Any to 3</span></span>
    
5. <span data-ttu-id="54b2a-124">Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben</span><span class="sxs-lookup"><span data-stu-id="54b2a-124">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```