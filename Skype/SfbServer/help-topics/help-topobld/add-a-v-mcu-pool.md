---
title: Hinzufügen des A/V-MCU-Pools
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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Alle Enterprise Edition-Front-End-Server eines zentralen Standorts, die nicht über eine zusammengefasste A/V-Konferenzdienst verfügen, können dieselbe eigenständige A/V-Konferenzpool verwenden. Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und festlegen, ob nur ein einzelner A/V-Konferenzserver oder mehrere a/V-Konferenzserver mit Lastenausgleich vorhanden sein sollen.
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217476"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="f2354-104">Hinzufügen des A/V-MCU-Pools</span><span class="sxs-lookup"><span data-stu-id="f2354-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="f2354-105">Alle Enterprise Edition-Front-End-Server eines zentralen Standorts, die nicht über eine zusammengefasste A/V-Konferenzdienst verfügen, können dieselbe eigenständige A/V-Konferenzpool verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2354-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="f2354-106">Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und festlegen, ob nur ein einzelner A/V-Konferenzserver oder mehrere a/V-Konferenzserver mit Lastenausgleich vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="f2354-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f2354-107">Sie können einen Pool mit einem Server nicht in einen Pool mit mehreren Servern konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f2354-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="f2354-108">Wenn Sie später entscheiden, dass Ihre Organisation einen Pool mit mehreren Servern benötigt, müssen Sie den Pool mit einem Server löschen und dann den Pool mit mehreren Servern hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2354-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f2354-109">Wenn Sie eine A/V-Konferenzpool in der Zukunft implementieren möchten, wählen Sie **Pool mit mehreren Computern**aus.</span><span class="sxs-lookup"><span data-stu-id="f2354-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f2354-110">Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2354-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f2354-111">Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie den Topologie-Generator erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann das neue A/V-Konferenzpool Mitglied über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f2354-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f2354-112">A/V-Konferenzserver Pools sind insofern eindeutig, als Sie keine Lastenausgleichsmodule benötigen, um einen Pool zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2354-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="f2354-113">A/V-Konferenz Pools laden den Lastenausgleich intern und benötigen keine zusätzliche Hardware.</span><span class="sxs-lookup"><span data-stu-id="f2354-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

