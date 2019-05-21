---
title: Hinzufügen des Director-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Um den FQDN des Director-Pools zu definieren, wählen Sie entweder einen Pool mit mehreren Computern aus, der aus zwei oder mehr Directors in einem Lastenausgleichspool oder einem einzelnen Computerpool bestehen soll. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der für die Verbindung mit dem Director-Pool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool von Director-Computern handelt es sich hierbei um den DNS-Eintrag (Domain Name System) für die virtuelle IP eines Hardwarelastenausgleichs oder den freigegebenen DNS-Eintrag für den DNS-Lastenausgleich.
ms.openlocfilehash: 163de8a6091e74238c4a4127ae39f7cd500cdb84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304786"
---
# <a name="add-director-pool"></a><span data-ttu-id="97380-105">Hinzufügen des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="97380-105">Add Director Pool</span></span>
 
<span data-ttu-id="97380-106">Um **den FQDN des Director-Pools zu definieren**, wählen Sie entweder einen **Pool mit mehreren Computern** aus, der aus zwei oder mehr Directors in einem Lastenausgleichspool oder einem **einzelnen Computerpool**bestehen soll.</span><span class="sxs-lookup"><span data-stu-id="97380-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="97380-107">Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der für die Verbindung mit dem Director-Pool oder dem FQDN des einzelnen Directors verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="97380-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="97380-108">Bei einem Pool von Director-Computern handelt es sich hierbei um den DNS-Eintrag (Domain Name System) für die virtuelle IP eines Hardwarelastenausgleichs oder den freigegebenen DNS-Eintrag für den DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="97380-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="97380-109">Wenn Sie beabsichtigen, einen Director-Pool in Zukunft zu implementieren, wählen Sie den **Pool für mehrere Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="97380-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="97380-110">Obwohl ein Pool als zwei oder mehr Computer definiert ist, die Lastenausgleich aufweisen, können Sie einen einzelnen Computerpool erstellen und einen Pool-FQDN für den einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="97380-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="97380-111">Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topology Builder erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Director-Pool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="97380-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="97380-112">Darüber hinaus müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichs Komponenten für den Pool, für den DNS-Lastenausgleich (Domain Name System) oder für Hardwarelastenausgleichs hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="97380-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="97380-113">In vielen Fällen sind beide Lastenausgleichssysteme vorhanden.</span><span class="sxs-lookup"><span data-stu-id="97380-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="97380-114">Stellen Sie sicher, dass Sie beide den neuen Mitgliedsserver hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="97380-114">Be sure that you are adding the new member server to both.</span></span> 
  

