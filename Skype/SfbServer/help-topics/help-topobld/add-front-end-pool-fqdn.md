---
title: Hinzufügen des FQDN des Front-End-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Geben Sie den vollqualifizierten Domänennamen des Front-End-Pools ein, den Sie erstellen. Sie können den vollqualifizierten Domänennamen eines Pools nach Veröffentlichung der Topologie mit dem Front-End-Pool nicht ändern. Wenn Sie den Pool umbenennen müssen, müssen Sie zunächst den Pool löschen und dann einen neuen Pool mit dem neuen vollqualifizierten Domänennamen hinzufügen.
ms.openlocfilehash: 99bf31760ce908952547ccfb3f150c136966e9f0
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218856"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="cc1a9-105">Hinzufügen des FQDN des Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="cc1a9-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="cc1a9-p102">Geben Sie den vollqualifizierten Domänennamen des Front-End-Pools ein, den Sie erstellen. Sie können den vollqualifizierten Domänennamen eines Pools nach Veröffentlichung der Topologie mit dem Front-End-Pool nicht ändern. Wenn Sie den Pool umbenennen müssen, müssen Sie zunächst den Pool löschen und dann einen neuen Pool mit dem neuen vollqualifizierten Domänennamen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc1a9-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="cc1a9-109">Wenn Sie die Verwendung eines Front-End-Pools für die Zukunft planen, wählen Sie **Pool mit mehreren Computern** aus.</span><span class="sxs-lookup"><span data-stu-id="cc1a9-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="cc1a9-110">Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc1a9-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="cc1a9-111">Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie den Topologie-Generator erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann das neue Front-End-Pool Mitglied über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="cc1a9-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="cc1a9-112">Zudem müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichsmodulen (DNS-Lastenausgleich (Domain Name System) oder Hardwaregerät zum Lastenausgleich) für den Pool hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc1a9-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="cc1a9-113">In vielen Fällen verfügen Sie über beide Lastenausgleichssysteme.</span><span class="sxs-lookup"><span data-stu-id="cc1a9-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="cc1a9-114">Stellen Sie sicher, dass Sie den neuen Mitgliedsserver beiden Systemen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc1a9-114">Be sure that you are adding the new member server to both.</span></span> 
  

