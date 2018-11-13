---
title: Migrieren von mehreren Standorten und pools
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype für Business Server 2019 unterstützt mehrere Standorte und mit mehreren Pool-Bereitstellungen. Bei der Migration mehrerer Pools zu Skype für Business Server 2019 ist Folgendes erforderlich:'
ms.openlocfilehash: ecd7e795c7cde9265f26c9c7533fcfd6ec87d684
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293548"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="28d05-104">Migrieren von mehreren Standorten und pools</span><span class="sxs-lookup"><span data-stu-id="28d05-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="28d05-105">Skype für Business Server 2019 unterstützt mehrere Standorte und mit mehreren Pool-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="28d05-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="28d05-106">Bei der Migration mehrerer Pools zu Skype für Business Server 2019 ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="28d05-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="28d05-107">Nach der Bereitstellung einen Skype für Business Server 2019 pilotpool müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in der Skype für Business Server 2019-Pool und eine Methodik zum Überprüfen der Funktionalität der Benutzer verschoben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="28d05-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="28d05-108">Beispielsweise nach dem Verschieben eines Benutzers in den pilotpool, stellen Sie sicher, dass die Benutzerrichtlinie Konferenz in Skype für Business Server 2019 verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="28d05-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="28d05-109">Nach der Bereitstellung eines Edgeservers im pilotpool müssen Sie überprüfen, ob externe Benutzer mit der Skype für Business Server 2019-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="28d05-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="28d05-110">Persistent Chat, SQL-Spiegelung und XMPP-Funktionalität in Skype für Business Server 2019 veraltete und nicht mehr als Skype für Business Server 2019 Features verfügbar sind, aber kann in einer koexistenzumgebung fortgesetzt werden, wenn sie zuvor in bereitgestellt wurden eine Legacy-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="28d05-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="28d05-111">Wenn Sie weiterhin diese Features verwenden möchten, sollten Sie planen, um einer koexistenzumgebung fortzusetzen, wo bestimmte Benutzer in alten Pools verbleibt.</span><span class="sxs-lookup"><span data-stu-id="28d05-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="28d05-112">Nach dem Übergang der Sammelsuche Routen Edge-Servern die pilot Skype für Business Server 2019 Edge-Server, müssen Sie überprüfen, ob die Partnerbenutzer mit dem Skype für Business Server 2019-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="28d05-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="28d05-113">Nach dem Verschieben von allen Benutzern und Kontaktobjekten nicht vom Benutzer, müssen Sie überprüfen, ob der Pool der Vorgängerversion leer ist.</span><span class="sxs-lookup"><span data-stu-id="28d05-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="28d05-114">Nachdem Sie sichergestellt haben, dass der Pool der Vorgängerversion leer ist, können Sie den Pool deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="28d05-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="28d05-115">Informationen dazu, wie Sie die Vorversion legacy-Pools und-Servern aus der vorversionsumgebung finden Sie unter [Phase 8: Außerbetriebsetzen des vorversionspools](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="28d05-115">For details about how to deactivate the legacy legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

