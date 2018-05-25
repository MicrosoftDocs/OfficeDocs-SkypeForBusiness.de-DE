---
title: Hinzufügen von Director-Pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Um den FQDN des Director-Pools zu definieren, wählen Sie einen Pool mit mehreren Computern, der aus zwei oder mehr Directors in einem Pool mit Lastenausgleich bestehen wird oder einen Pool mit einem Computer aus. Sie müssen auch den vollqualifizierten Domänennamen (FQDN) eingeben, der zum Verbinden mit den Director-Pool oder den einzelnen Director-FQDN verwendet werden. Für einen Pool von Computern Director würde dies den Eintrag Domain Name System (DNS) für die virtuelle IP-Adresse des ein Hardwaregerät zum Lastenausgleich oder den freigegebenen DNS-Eintrag für DNS-Lastenausgleich sein.
ms.openlocfilehash: d71219f6e9c51d69bee8d2457cc30c19f4fa6c89
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-director-pool"></a><span data-ttu-id="4439a-105">Hinzufügen von Director-Pool</span><span class="sxs-lookup"><span data-stu-id="4439a-105">Add Director Pool</span></span>
 
<span data-ttu-id="4439a-106">Wählen Sie mit **dem FQDN des Director-Pools definieren**entweder einen **Pool mit mehreren Computern** , die aus zwei oder mehr Directors in einem Pool mit Lastenausgleich bestehen wird oder einen **Pool mit einem Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="4439a-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="4439a-107">Sie müssen auch den vollqualifizierten Domänennamen (FQDN) eingeben, der zum Verbinden mit den Director-Pool oder den einzelnen Director-FQDN verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4439a-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="4439a-108">Für einen Pool von Computern Director würde dies den Eintrag Domain Name System (DNS) für die virtuelle IP-Adresse des ein Hardwaregerät zum Lastenausgleich oder den freigegebenen DNS-Eintrag für DNS-Lastenausgleich sein.</span><span class="sxs-lookup"><span data-stu-id="4439a-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="4439a-109">Wenn Sie einen Director-Pool in der Zukunft implementieren möchten, wählen Sie **Pool mit mehreren Computern**.</span><span class="sxs-lookup"><span data-stu-id="4439a-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="4439a-110">Obwohl ein Pool als zwei oder mehr Computer, die Lastenausgleich sind definiert ist, können Sie einen Pool mit einem Computer erstellt und erstellen einen Pool-FQDN für die einzelnen Computer.</span><span class="sxs-lookup"><span data-stu-id="4439a-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="4439a-111">Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie Topology Builder erneut aus, um das neue Mitglied Pool definieren, die neue Topologie veröffentlichen und setup wird das neue Mitglied der Director-Pool über die Skype für Business Server-Bereitstellungs-Assistenten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4439a-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="4439a-112">Sie müssen auch fügen Sie den neuen Pool Member für die entsprechenden Lastenausgleich für den Pool, für Domain Name System (DNS)-Netzwerklastenausgleich, oder für Hardware-Lastenausgleichsmodule.</span><span class="sxs-lookup"><span data-stu-id="4439a-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="4439a-113">In vielen Fällen müssen Sie beide Systeme direkten-Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="4439a-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="4439a-114">Stellen Sie sicher, dass Sie sowohl den neue Mitgliedsserver hinzugefügt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4439a-114">Be sure that you are adding the new member server to both.</span></span> 
  

