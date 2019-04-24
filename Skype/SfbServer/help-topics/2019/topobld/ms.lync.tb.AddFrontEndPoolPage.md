---
title: Hinzufügen des FQDN des Front-End-Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Geben Sie den vollqualifizierten Domänennamen (FQDN) des Front-End-Pools, die Sie erstellen. Sie können den FQDN eines Pools nach dem Veröffentlichen der Topologie mit den Front-End-Pool nicht ändern. Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool zu löschen und fügen Sie einen neuen Pool mit dem neuen vollqualifizierten Domänennamen.
ms.openlocfilehash: 28e831df0cdf86620eefc1a22ced199507026c46
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202061"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="06cf1-105">Hinzufügen des FQDN des Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="06cf1-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="06cf1-106">Geben Sie den vollqualifizierten Domänennamen (FQDN) des Front-End-Pools, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="06cf1-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="06cf1-107">Sie können den FQDN eines Pools nach dem Veröffentlichen der Topologie mit den Front-End-Pool nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="06cf1-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="06cf1-108">Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool zu löschen und fügen Sie einen neuen Pool mit dem neuen vollqualifizierten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="06cf1-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="06cf1-109">Wenn Sie einen Front-End-Pool in der Zukunft implementieren möchten, wählen Sie **Pool mit mehreren Computern**.</span><span class="sxs-lookup"><span data-stu-id="06cf1-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="06cf1-110">Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="06cf1-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="06cf1-111">Wenn Sie später weitere Computer zum Pool hinzufügen möchten, führen Sie die Topologie-Generator erneut aus, um das neue Mitglied Pool definieren, die neue Topologie veröffentlichen und dann das neue Mitglied der Front-End-Pool über die Skype für Business Server-Bereitstellungsassistenten einrichten.</span><span class="sxs-lookup"><span data-stu-id="06cf1-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="06cf1-112">Sie müssen auch den neuen Pool Member für die entsprechenden Lastenausgleich für den Pool, Domain Name System (DNS) zum Lastenausgleich oder Hardwaregerät zum Lastenausgleich hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="06cf1-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="06cf1-113">In vielen Fällen müssen Sie beide Systeme direkten-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="06cf1-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="06cf1-114">Stellen Sie sicher, dass Sie sowohl den neue Mitgliedsserver hinzugefügt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="06cf1-114">Be sure that you are adding the new member server to both.</span></span> 
  

