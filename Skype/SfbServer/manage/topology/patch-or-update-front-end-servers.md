---
title: Patchen oder Aktualisieren von Front-End-Servern im Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Zusammenfassung: erfahren Sie, wie Upgrades oder Patches auf Front-End-Servern im Skype für Business Server angewendet.'
ms.openlocfilehash: cf209159391ef084d77b5adc639698ed766427ff
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371717"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="57a98-103">Patchen oder Aktualisieren von Front-End-Servern im Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="57a98-103">Patch or update Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="57a98-104">**Zusammenfassung:** Hier erfahren Sie, wie Upgrades oder Patches auf Front-End-Servern im Skype für Business Server angewendet.</span><span class="sxs-lookup"><span data-stu-id="57a98-104">**Summary:** learn how to apply upgrades or patches to Front End Servers in Skype for Business Server.</span></span>
  
<span data-ttu-id="57a98-105">Wenn Sie die Server in einem Front-End-Pool patchen, gehen Sie also einen Server zu einem Zeitpunkt vor.</span><span class="sxs-lookup"><span data-stu-id="57a98-105">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="57a98-106">So führen Sie ein Upgrade für die Front-End-Server in einem Pool durch</span><span class="sxs-lookup"><span data-stu-id="57a98-106">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="57a98-107">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="57a98-107">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="57a98-108">Wenn für dieses Cmdlet fehlende Replikate angezeigt werden, führen Sie vor dem Anwenden von Patches das folgende Cmdlet aus, um den Pool wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="57a98-108">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="57a98-109">Führen Sie auf dem ersten Server, auf den ein Patch angewendet werden soll, das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="57a98-109">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="57a98-110">Dieses Cmdlet verschiebt alle Dienste auf anderen Front-End-Servern im Pool, und wird von diesem Server offline geschaltet.</span><span class="sxs-lookup"><span data-stu-id="57a98-110">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="57a98-111">Wenden Sie das Upgrade oder Patch auf diesen Server an.</span><span class="sxs-lookup"><span data-stu-id="57a98-111">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="57a98-112">Führen Sie das folgende Cmdlet auf dem aktualisierten Server aus:</span><span class="sxs-lookup"><span data-stu-id="57a98-112">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="57a98-113">Der Server ist wieder im Dienst.</span><span class="sxs-lookup"><span data-stu-id="57a98-113">The server is returned to service.</span></span>
    
5. <span data-ttu-id="57a98-114">Wiederholen Sie die Schritte 2 bis 4 für jeden einzelnen Server, der ein Upgrade erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="57a98-114">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    

