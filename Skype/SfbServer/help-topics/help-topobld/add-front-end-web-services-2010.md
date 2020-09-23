---
title: Hinzufügen von Front-End-Webdiensten – 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217956"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="8e9b8-104">Hinzufügen von Front-End-Webdiensten – 2010</span><span class="sxs-lookup"><span data-stu-id="8e9b8-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="8e9b8-105">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="8e9b8-106">Wenn beispielsweise die vollständige URL für die Webdienste des Pools ist https://pool01.contoso.net , lautet die Basis-URL pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="8e9b8-107">Sie können den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des internen Webdienste Pools für eine Standard Edition-Server nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="8e9b8-108">Wenn Sie Domain Name System (DNS) Lastenausgleich für eine Enterprise Edition-Front-End-Pool konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom FQDN des Pools unterscheiden muss und beispielsweise Internal sein kann \<your base URL\> ).</span><span class="sxs-lookup"><span data-stu-id="8e9b8-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="8e9b8-109">Zur Unterscheidung von Domänennamen können Sie eine externe Basis-URL angegeben, die sich von Ihrer internen Basis-URL unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="8e9b8-110">Beispiel: der Name Ihrer internen Domäne lautet "contoso.net", der Name Ihrer externen Domäne lautet "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="8e9b8-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="8e9b8-111">Zur Definition der externen Basis-URL würden Sie den Domänennamen "contoso.com" verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="8e9b8-112">Dies ist bei einer Edgebereitstellung für Reverseproxyserver von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="8e9b8-113">Der Domänenname der externen Basis-URL muss dem Domänennamen des vollqualifizierten Domänennamens des Reverseproxys entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="8e9b8-114">Für Sofortnachrichten und Anwesenheitsinformationen ist ein HTTP-Zugriff auf den Front-End-Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e9b8-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

