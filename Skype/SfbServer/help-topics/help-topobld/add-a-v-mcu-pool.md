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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Alle Enterprise Edition-Front-End-Server eines zentralen Standorts, die keinen a/v-Konferenzdienst haben, können denselben eigenständigen a/v-Konferenz Pool verwenden. Für jeden a/v-Konferenz Pool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und angeben, ob nur ein einzelner a/v-Konferenzserver oder mehrere Server mit Lastenausgleich für a/v-Konferenzen vorhanden sein sollen.
ms.openlocfilehash: cf34ca6b82f31b0232748d15f0b0cc6597511249
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685388"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="f1692-104">Hinzufügen des A/V-MCU-Pools</span><span class="sxs-lookup"><span data-stu-id="f1692-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="f1692-105">Alle Enterprise Edition-Front-End-Server eines zentralen Standorts, die keinen a/v-Konferenzdienst haben, können denselben eigenständigen a/v-Konferenz Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1692-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="f1692-106">Für jeden a/v-Konferenz Pool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und angeben, ob nur ein einzelner a/v-Konferenzserver oder mehrere Server mit Lastenausgleich für a/v-Konferenzen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="f1692-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f1692-107">Sie können einen Pool mit einem einzelnen Server nicht in einen Pool mit mehreren Servern konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f1692-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="f1692-108">Wenn Sie später entscheiden, dass Ihre Organisation einen Pool mit mehreren Servern benötigt, müssen Sie den Pool mit einem Server löschen und dann den Pool mit mehreren Servern hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f1692-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f1692-109">Wenn Sie beabsichtigen, in Zukunft einen A/V-Konferenz Pool zu implementieren, wählen Sie den **Pool für mehrere Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="f1692-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="f1692-110">Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1692-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="f1692-111">Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topologie-Generator erneut definieren, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann das neue A/V-Konferenz Poolmitglied über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten.</span><span class="sxs-lookup"><span data-stu-id="f1692-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="f1692-112">A/V-Konferenz Server Pools sind einzigartig, da Sie keine Lastenausgleichsfunktionen zum Erstellen eines Pools benötigen.</span><span class="sxs-lookup"><span data-stu-id="f1692-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="f1692-113">A/V-Konferenz Pools laden den Lastenausgleich intern und benötigen keine zusätzliche Hardware.</span><span class="sxs-lookup"><span data-stu-id="f1692-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

