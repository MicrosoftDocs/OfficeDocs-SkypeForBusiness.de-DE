---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for Business Server 2019 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools. Der Vorgang zum Migrieren mehrerer Pools zu Skype for Business Server 2019 erfordert die folgenden Überlegungen:'
ms.openlocfilehash: e2577b6af1430be90e30fff3236d7ea3cf473cd5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237874"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="e9f4f-104">Migrieren von mehreren Standorten und Pools</span><span class="sxs-lookup"><span data-stu-id="e9f4f-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="e9f4f-105">Skype for Business Server 2019 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="e9f4f-106">Der Vorgang zum Migrieren mehrerer Pools zu Skype for Business Server 2019 erfordert die folgenden Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="e9f4f-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="e9f4f-107">Nachdem Sie einen Skype for Business Server 2019-Pilot Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den Skype for Business Server 2019-Pool verschoben werden, sowie eine Methodik zum Überprüfen der Funktionalität der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="e9f4f-108">Wenn Sie beispielsweise einen Benutzer in den Pilot Pool verschieben, stellen Sie sicher, dass die konferenzrichtlinie des Benutzers in Skype for Business Server 2019 verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="e9f4f-109">Nachdem Sie einen Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="e9f4f-110">Beständiger Chat, SQL-Spiegelung und XMPP-Funktionalität sind in Skype for Business Server 2019 veraltet und nicht mehr als Funktionen von Skype for Business Server 2019 verfügbar, können aber in einer Koexistenz-Umgebung fortgesetzt werden, wenn Sie zuvor in einer Legacyumgebung</span><span class="sxs-lookup"><span data-stu-id="e9f4f-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="e9f4f-111">Wenn Sie diese Features weiterhin verwenden möchten, sollten Sie mit einer Koexistenz-Umgebung fortfahren, in der bestimmte Benutzer in Legacy Pools verbleiben.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="e9f4f-112">Nachdem Sie die Edgeserver der Federated-Routes an die Pilot-Edgeserver von Skype for Business Server 2019 übertragen haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem Skype for Business Server 2019-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="e9f4f-113">Nachdem Sie alle Benutzer und nicht Benutzer-Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Legacy Pool leer ist.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="e9f4f-114">Nachdem Sie überprüft haben, dass der Legacy Pool leer ist, können Sie den Pool deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="e9f4f-115">Weitere Informationen zum Deaktivieren des Legacy Pools und der Legacy Server finden Sie unter [Phase 8: Legacy Pools](phase-8-decommission-legacy-pools.md)für decommission.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

