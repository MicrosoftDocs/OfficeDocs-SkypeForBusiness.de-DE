---
title: Hinzufügen des FQDN des Front-End-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools an, den Sie erstellen. Sie können den FQDN eines Pools nicht ändern, nachdem Sie die Topologie mit dem Front-End-Pool veröffentlicht haben. Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool löschen und dann einen neuen Pool mit dem neuen FQDN hinzufügen.
ms.openlocfilehash: 00bc6276062412abe55a518a45941fa9c4fbaff8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297751"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="db931-105">Hinzufügen des FQDN des Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="db931-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="db931-106">Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools an, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="db931-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="db931-107">Sie können den FQDN eines Pools nicht ändern, nachdem Sie die Topologie mit dem Front-End-Pool veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="db931-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="db931-108">Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool löschen und dann einen neuen Pool mit dem neuen FQDN hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="db931-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="db931-109">Wenn Sie beabsichtigen, in Zukunft einen Front-End-Pool zu implementieren, wählen Sie den **Pool für mehrere Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="db931-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="db931-110">Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="db931-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="db931-111">Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topology Builder erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Front-End-Pool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="db931-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="db931-112">Darüber hinaus müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichs Komponenten für den Pool, DNS-Lastenausgleich (Domain Name System) oder Hardwarelastenausgleichs hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="db931-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="db931-113">In vielen Fällen sind beide Lastenausgleichssysteme vorhanden.</span><span class="sxs-lookup"><span data-stu-id="db931-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="db931-114">Stellen Sie sicher, dass Sie beide den neuen Mitgliedsserver hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="db931-114">Be sure that you are adding the new member server to both.</span></span> 
  

