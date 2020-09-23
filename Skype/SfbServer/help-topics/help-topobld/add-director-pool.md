---
title: Hinzufügen des Director-Pools
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
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Wählen Sie unter FQDN des Directorpools definieren entweder die Option Pool mit mehreren Computern, wobei der Pool mindestens zwei Directors in einem Pool mit Lastenausgleich umfasst, oder die Option Pool mit einem Computer aus. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der zum Herstellen einer Verbindung mit dem Directorpool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool aus Director-Computern ist dies der DNS-Eintrag (Domain Name System) für die virtuelle IP-Adresse eines Hardwaregeräts zum Lastenausgleich oder der gemeinsame DNS-Eintrag für den DNS-Lastenausgleich.
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219486"
---
# <a name="add-director-pool"></a><span data-ttu-id="37473-105">Hinzufügen des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="37473-105">Add Director Pool</span></span>
 
<span data-ttu-id="37473-106">Wählen Sie unter **FQDN des Directorpools definieren** entweder die Option **Pool mit mehreren Computern**, wobei der Pool mindestens zwei Directors in einem Pool mit Lastenausgleich umfasst, oder die Option **Pool mit einem Computer** aus.</span><span class="sxs-lookup"><span data-stu-id="37473-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="37473-107">Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der zum Herstellen einer Verbindung mit dem Directorpool oder dem FQDN des einzelnen Directors verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="37473-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="37473-108">Bei einem Pool aus Director-Computern ist dies der DNS-Eintrag (Domain Name System) für die virtuelle IP-Adresse eines Hardwaregeräts zum Lastenausgleich oder der gemeinsame DNS-Eintrag für den DNS-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="37473-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="37473-109">Wenn Sie für die Zukunft die Implementierung eines Director-Pools planen, wählen Sie **Pool mit mehreren Computern** aus.</span><span class="sxs-lookup"><span data-stu-id="37473-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="37473-110">Obwohl ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzelnen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="37473-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="37473-111">Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie den Topologie-Generator erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Directorpool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="37473-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="37473-112">Zudem müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichsmodulen hinzufügen (für den Pool, den DNS-Lastenausgleich (Domain Name System) oder das Hardwaregerät zum Lastenausgleich).</span><span class="sxs-lookup"><span data-stu-id="37473-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="37473-113">In vielen Fällen verfügen Sie über beide Lastenausgleichssysteme.</span><span class="sxs-lookup"><span data-stu-id="37473-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="37473-114">Stellen Sie sicher, dass Sie den neuen Mitgliedsserver beiden Systemen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="37473-114">Be sure that you are adding the new member server to both.</span></span> 
  

