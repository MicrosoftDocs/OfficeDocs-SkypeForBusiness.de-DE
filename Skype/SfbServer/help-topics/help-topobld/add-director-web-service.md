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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: Die Basis-URL ist die Webdienstidentität der URL ohne https://. Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.
ms.openlocfilehash: e62adfb080886397de51ff4c51c5fac19878eeff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685318"
---
# <a name="add-director-web-service"></a><span data-ttu-id="8cfde-104">Hinzufügen eines Director-Webdiensts</span><span class="sxs-lookup"><span data-stu-id="8cfde-104">Add Director Web Service</span></span>
 
<span data-ttu-id="8cfde-105">Die Basis-URL ist die Webdienstidentität der URL ohne https://.</span><span class="sxs-lookup"><span data-stu-id="8cfde-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="8cfde-106">Wenn beispielsweise die vollständige URL für die Webdienste des Pools lautet https://pool01.contoso.net, lautet die Basis-URL pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="8cfde-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="8cfde-107">Wenn Sie nur einen einzigen Director bereitstellen, können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des internen Webdienste-Pools nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="8cfde-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="8cfde-108">Wenn Sie einen DNS-Lastenausgleich (Domain Name System) für den Pool von Directors konfigurieren, können Sie eine andere interne Basis-URL angeben (die sich vom FQDN des Pools unterscheiden muss und beispielsweise Internal-\<ihre Basis-\>URL sein kann).</span><span class="sxs-lookup"><span data-stu-id="8cfde-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="8cfde-109">Sie können eine externe Basis-URL angeben, die von ihrer internen Basis-URL abweicht, um die Domänenbenennung zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="8cfde-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="8cfde-110">Beispielsweise ist Ihre interne Domäne contoso.net, aber ihr externer Domänenname lautet contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8cfde-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="8cfde-111">Sie würden die externe Basis-URL mit dem contoso.com-Domänennamen definieren.</span><span class="sxs-lookup"><span data-stu-id="8cfde-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="8cfde-112">Dies ist wichtig für Reverse-Proxy Server für eine Edge-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="8cfde-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="8cfde-113">Der Domänenname der externen Basis-URL sollte mit dem Domänennamen des FQDN des Reverse-Proxy identisch sein.</span><span class="sxs-lookup"><span data-stu-id="8cfde-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

