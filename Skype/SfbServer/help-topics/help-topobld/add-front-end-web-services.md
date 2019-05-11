---
title: Hinzufügen von Front-End-Webdiensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.
ms.openlocfilehash: fc67ed792ab121bc4a9aaa0c72bcf764a2dadf1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897685"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="56dd8-104">Hinzufügen von Front-End-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="56dd8-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="56dd8-105">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="56dd8-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="56dd8-106">Wenn die vollständige URL für die Webdienste des Pools ist beispielsweise https://pool01.contoso.net, die base-URL ist pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="56dd8-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="56dd8-107">Den internen Webdienste Pool vollqualifizierten Domänennamen (FQDN) für einen Standard Edition-Server kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="56dd8-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="56dd8-108">Wenn Sie Domain Name System (DNS) des Lastenausgleichs für einen Enterprise Edition-Front-End-Pool konfigurieren, können Sie angeben, dass einen anderen internen Basis-URL der FQDN des Pools unterscheidet sein muss (beispielsweise internen -\<Basis-URL\>).</span><span class="sxs-lookup"><span data-stu-id="56dd8-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="56dd8-109">Sie können einen externen Basis-URL, die sich unterscheidet angeben von Ihrer internen Basis-URL um Domänennamen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="56dd8-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="56dd8-110">Beispielsweise die interne Domäne ist contoso.net, aber der externen Domäne "contoso.com" lautet.</span><span class="sxs-lookup"><span data-stu-id="56dd8-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="56dd8-111">Definieren Sie die externe base-URL, die mit dem Domänennamen "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="56dd8-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="56dd8-112">Dies ist wichtig für Reverseproxyserver für eine edgebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="56dd8-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="56dd8-113">Der externe URL-Domäne Basisnamen sollte die den Domänennamen des vollqualifizierten Domänennamens des Reverseproxys identisch sein.</span><span class="sxs-lookup"><span data-stu-id="56dd8-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="56dd8-114">Sofortnachrichten und Anwesenheit ist HTTP-Zugriff auf den Front-End-Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56dd8-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

