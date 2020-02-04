---
title: Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Wenn Sie einen vertrauenswürdigen Anwendungspool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) definieren möchten, geben Sie Folgendes an:'
ms.openlocfilehash: 137d344c66fe73628002949b46cff85f451f2af0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702930"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="f58b8-103">Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools</span><span class="sxs-lookup"><span data-stu-id="f58b8-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="f58b8-104">Wenn Sie einen vertrauenswürdigen Anwendungspool vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) definieren möchten, geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="f58b8-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="f58b8-105">Ein FQDN des Servers oder Pools von Servern, auf dem die vertrauenswürdigen Anwendungen gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="f58b8-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="f58b8-106">Wählen Sie den Pool für **mehrere Computer** aus, wenn Sie einen Pool von Servern für die vertrauenswürdigen Anwendungen überlasten Ausgleich und hohe Verfügbarkeit bereitstellen, oder wählen Sie einen **einzelnen Computerpool** aus, wenn Sie keinen Lastenausgleich oder hohe Verfügbarkeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="f58b8-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f58b8-107">Ein einzelner Trusted Applications-Server kann später nicht in einen Pool von Servern konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="f58b8-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="f58b8-108">Wenn Sie der Meinung sind, dass Sie in Zukunft einen Pool benötigen, können Sie einen mehr Serverpool mit einem einzelnen Computer bereitstellen und bei Bedarf Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f58b8-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="f58b8-109">Details zu vertrauenswürdigen Anwendungspools finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f58b8-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

