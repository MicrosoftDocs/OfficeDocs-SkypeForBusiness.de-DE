---
title: Hinzufügen des A/V-MCU-Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Alle Enterprise Edition-Front-End-Server von einem zentralen Standort, die nicht über einen verbundenen verfügen A / V-Konferenzdienst können das gleiche eigenständige A / V-konferenzpool. Für jede A / V-konferenzpool, geben Sie einen vollqualifizierten Domänennamen (FQDN) für den Pool und gibt an, ob es nur einen einzelnen A hat / V-Konferenzserver oder mehrere, Lastenausgleich und A / V-Konferenzserver.
ms.openlocfilehash: c120504b56d159b40be7d7401f43ef39757f5253
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883623"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="a9c6c-104">Hinzufügen des A/V-MCU-Pools</span><span class="sxs-lookup"><span data-stu-id="a9c6c-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="a9c6c-105">Alle Enterprise Edition-Front-End-Server von einem zentralen Standort, die nicht über einen verbundenen verfügen A / V-Konferenzdienst können das gleiche eigenständige A / V-konferenzpool.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="a9c6c-106">Für jede A / V-konferenzpool, geben Sie einen vollqualifizierten Domänennamen (FQDN) für den Pool und gibt an, ob es nur einen einzelnen A hat / V-Konferenzserver oder mehrere, Lastenausgleich und A / V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a9c6c-107">Sie können keinen einzelnen Server Pool in einen Pool von mehreren Servern konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="a9c6c-108">Wenn Sie später entscheiden, dass Ihre Organisation einen Pool von mehreren Servern benötigt, müssen Sie den Pool einem einzelnen Server zu löschen, und fügen Sie MultiServer-Pool.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="a9c6c-109">Wenn Sie planen, implementieren einen A / V-konferenzpool wählen Sie **Pool mit mehreren Computern**in der Zukunft aus.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="a9c6c-110">Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="a9c6c-111">Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie den Topologie-Generator erneut aus, um das neue Mitglied Pool definieren, die neue Topologie veröffentlichen und richten Sie dann den neuen A / V-konferenzpool Member über die Skype für Business Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="a9c6c-112">A / V-Konferenzserver-Pools, dass sie nicht zum Erstellen eines Pools Lastenausgleich laden müssen eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="a9c6c-113">A / V-konferenzpools Lastenausgleich intern und zusätzlichen Hardware ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a9c6c-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

