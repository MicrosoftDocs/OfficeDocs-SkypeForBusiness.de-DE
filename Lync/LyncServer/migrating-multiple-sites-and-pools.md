---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bee98cdc88a836be8b629d76b5bed57af402a3ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="8cf5f-102">Migrieren von mehreren Standorten und Pools</span><span class="sxs-lookup"><span data-stu-id="8cf5f-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cf5f-103">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="8cf5f-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="8cf5f-104">Lync Server 2013 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools.</span><span class="sxs-lookup"><span data-stu-id="8cf5f-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="8cf5f-105">Der Vorgang der Migration mehrerer Pools von lync Server 2010 zu lync Server 2013 erfordert folgende Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="8cf5f-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="8cf5f-106">Nachdem Sie einen lync Server 2013 Pilot-Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode für die Überprüfung der Funktionalität der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8cf5f-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="8cf5f-107">Nachdem Sie beispielsweise einen Benutzer in den Pilot Pool verschoben haben, überprüfen Sie, ob die konferenzrichtlinie des Benutzers in lync Server 2013 verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="8cf5f-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="8cf5f-108">Nachdem Sie eine Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="8cf5f-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="8cf5f-109">Nachdem Sie die Verbund Routen von lync Server 2010-Edgeserver zu den Pilot lync Server 2013-Edgeserver gewechselt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="8cf5f-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="8cf5f-110">Nachdem Sie alle Benutzer und nicht-Benutzer Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der lync Server 2010 Pool leer ist.</span><span class="sxs-lookup"><span data-stu-id="8cf5f-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="8cf5f-111">Nachdem Sie überprüft haben, dass der lync Server 2010 Pool leer ist, können Sie den Pool deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8cf5f-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="8cf5f-112">Ausführliche Informationen zum Deaktivieren des Legacy lync Server 2010 Pools und der Server finden Sie unter [Phase 8: decommission Legacy Pools](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="8cf5f-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

