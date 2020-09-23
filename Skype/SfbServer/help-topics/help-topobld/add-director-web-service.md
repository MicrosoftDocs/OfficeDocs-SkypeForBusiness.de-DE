---
title: Hinzufügen eines Director-Webdiensts
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219466"
---
# <a name="add-director-web-service"></a><span data-ttu-id="3c5cc-104">Hinzufügen eines Director-Webdiensts</span><span class="sxs-lookup"><span data-stu-id="3c5cc-104">Add Director Web Service</span></span>
 
<span data-ttu-id="3c5cc-105">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="3c5cc-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="3c5cc-106">Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="3c5cc-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="3c5cc-107">Wenn nur ein Director bereitgestellt wird, können Sie den vollqualifizierten Domänennamen (FQDN) des internen Webdienstepools nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="3c5cc-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="3c5cc-108">Wenn Sie einen Domain Name System (DNS) Lastenausgleich für Pool of Directors konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom FQDN des Pools unterscheiden muss und beispielsweise Internal sein kann \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="3c5cc-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="3c5cc-p104">Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet. Beispiel: der Name Ihrer internen Domäne lautet "contoso.net", der Name Ihrer externen Domäne lautet "contoso.com". Zur Definition der externen Basis-URL würden Sie den Domänennamen "contoso.com" verwenden. Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung. Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3c5cc-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

