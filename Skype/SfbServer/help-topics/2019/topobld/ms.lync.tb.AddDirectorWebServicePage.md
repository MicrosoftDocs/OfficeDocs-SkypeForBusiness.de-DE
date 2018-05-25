---
title: Hinzufügen von Director-Webdiensts
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.
ms.openlocfilehash: c65d7d9276aaa394d1810136a97dcc8c075d3607
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="add-director-web-service"></a><span data-ttu-id="86d55-104">Hinzufügen von Director-Webdiensts</span><span class="sxs-lookup"><span data-stu-id="86d55-104">Add Director Web Service</span></span>
 
<span data-ttu-id="86d55-105">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="86d55-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="86d55-106">Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="86d55-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="86d55-107">Den internen Webdienste Pool vollqualifizierten Domänennamen (FQDN) kann nicht überschrieben werden, wenn nur einen einzelnen Director bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="86d55-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="86d55-108">Wenn Sie eine Domain Name System (DNS) Lastenausgleich für den Pool von Directors konfigurieren, können Sie einen anderen internen Basis-URL angeben (der FQDN des Pools unterscheidet und konnte sein, beispielsweise internen -\<Basis-URL\>).</span><span class="sxs-lookup"><span data-stu-id="86d55-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="86d55-109">Sie können einen externen Basis-URL, die sich unterscheidet angeben von Ihrer internen Basis-URL um Domänennamen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="86d55-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="86d55-110">Beispielsweise die interne Domäne ist contoso.net, aber der externen Domäne "contoso.com" lautet. Sie würden die externe base-URL mit den Domänennamen "contoso.com" definieren.</span><span class="sxs-lookup"><span data-stu-id="86d55-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="86d55-111">Dies ist wichtig für Reverseproxyserver für eine edgebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="86d55-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="86d55-112">Der externe URL-Domäne Basisnamen sollte die den Domänennamen des vollqualifizierten Domänennamens des Reverseproxys identisch sein.</span><span class="sxs-lookup"><span data-stu-id="86d55-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

