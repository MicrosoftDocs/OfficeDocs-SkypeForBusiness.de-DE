---
title: Hinzufügen von Front-End-Webdiensten – 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.
ms.openlocfilehash: ad21132f26abd03355cb214811a67dfe0f42add2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="327e7-104">Hinzufügen von Front-End-Webdiensten – 2010</span><span class="sxs-lookup"><span data-stu-id="327e7-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="327e7-105">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="327e7-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="327e7-106">Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="327e7-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="327e7-107">Den internen Webdienste Pool vollqualifizierten Domänennamen (FQDN) für einen Standard Edition-Server kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="327e7-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="327e7-108">Wenn Sie Domain Name System (DNS) des Lastenausgleichs für einen Enterprise Edition-Front-End-Pool konfigurieren, können Sie einen anderen internen Basis-URL angeben (der FQDN des Pools unterscheidet und konnte sein, beispielsweise internen -\<Basis-URL\>).</span><span class="sxs-lookup"><span data-stu-id="327e7-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="327e7-109">Sie können einen externen Basis-URL, die sich unterscheidet angeben von Ihrer internen Basis-URL um Domänennamen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="327e7-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="327e7-110">Beispielsweise die interne Domäne ist contoso.net, aber der externen Domäne "contoso.com" lautet. Sie würden die externe base-URL mit den Domänennamen "contoso.com" definieren.</span><span class="sxs-lookup"><span data-stu-id="327e7-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="327e7-111">Dies ist wichtig für Reverseproxyserver für eine edgebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="327e7-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="327e7-112">Der externe URL-Domäne Basisnamen sollte die den Domänennamen des vollqualifizierten Domänennamens des Reverseproxys identisch sein.</span><span class="sxs-lookup"><span data-stu-id="327e7-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="327e7-113">Sofortnachrichten und Anwesenheit ist HTTP-Zugriff auf den Front-End-Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="327e7-113">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

