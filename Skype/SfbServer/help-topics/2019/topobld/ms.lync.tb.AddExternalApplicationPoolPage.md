---
title: Fügen Sie vertrauenswürdiger Anwendungspool FQDN hinzu
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Um eine vertrauenswürdige Pool vollqualifizierten Domänennamens (FQDN) zu definieren, geben Sie Folgendes ein:'
ms.openlocfilehash: af21ab09797a5b81f2071a37a2668d556f0a4012
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="b702d-103">Fügen Sie vertrauenswürdiger Anwendungspool FQDN hinzu</span><span class="sxs-lookup"><span data-stu-id="b702d-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="b702d-104">Um eine vertrauenswürdige Pool vollqualifizierten Domänennamens (FQDN) zu definieren, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b702d-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="b702d-105">Der FQDN des Servers oder Pools von Servern, auf denen vertrauenswürdigen Anwendungen gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="b702d-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="b702d-106">Wählen Sie **Pool mit mehreren Computern** , wenn Sie einen Pool von Servern für die vertrauenswürdigen Anwendungen Lastenausgleich und hohe Verfügbarkeit bereitstellen, oder wählen **Pool mit einem Computer** aus, wenn Sie keine Lastenausgleich oder hohe Verfügbarkeit zu laden müssen.</span><span class="sxs-lookup"><span data-stu-id="b702d-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b702d-107">Einen einzelnen vertrauenswürdigen Anwendungsserver kann nicht in einem Pool von Servern später konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b702d-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="b702d-108">Wenn Sie, dass Sie einen Pool in der Zukunft benötigen können annehmen, können Sie einen Serverpool mit mehreren mit einem einzelnen Computer jetzt bereitstellen und Hinzufügen von Servern bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="b702d-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="b702d-109">Ausführliche Informationen zu vertrauenswürdigen Anwendungspools finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b702d-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

