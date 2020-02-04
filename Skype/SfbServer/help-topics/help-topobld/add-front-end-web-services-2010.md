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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685128"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="3f7f1-104">Hinzufügen von Front-End-Webdiensten – 2010</span><span class="sxs-lookup"><span data-stu-id="3f7f1-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="3f7f1-105">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="3f7f1-106">Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="3f7f1-107">Sie können den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für einen Standard Edition-Server nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="3f7f1-108">Wenn Sie den DNS-Lastenausgleich (Domain Name System) für einen Enterprise Edition-Front-End-Pool konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom FQDN des Pools unterscheiden muss und\<beispielsweise Internal\>-ihre Basis-URL sein kann).</span><span class="sxs-lookup"><span data-stu-id="3f7f1-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="3f7f1-109">Sie können eine externe Basis-URL angeben, die von ihrer internen Basis-URL abweicht, um die Domänenbenennung zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="3f7f1-110">Beispielsweise ist Ihre interne Domäne contoso.net, aber ihr externer Domänenname lautet contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="3f7f1-111">Sie würden die externe Basis-URL mit dem contoso.com-Domänennamen definieren.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="3f7f1-112">Dies ist wichtig für Reverse-Proxy Server für eine Edge-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="3f7f1-113">Der Domänenname der externen Basis-URL sollte mit dem Domänennamen des FQDN des Reverse-Proxy identisch sein.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="3f7f1-114">Für Sofortnachrichten und Anwesenheitsinformationen ist HTTP-Zugriff auf den Front-End-Pool erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3f7f1-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

