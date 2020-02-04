---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="68df2-102">Migrieren von mehreren Standorten und Pools</span><span class="sxs-lookup"><span data-stu-id="68df2-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68df2-103">_**Letztes Änderungsdatum des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="68df2-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="68df2-104">Lync Server 2013 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools.</span><span class="sxs-lookup"><span data-stu-id="68df2-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="68df2-105">Der Vorgang zum Migrieren mehrerer Pools von lync Server 2010 zu lync Server 2013 erfordert die folgenden Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="68df2-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="68df2-106">Nach der Bereitstellungeines lync Server 2013-pilotpools müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode zum Überprüfen der Funktionalität der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="68df2-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="68df2-107">Wenn Sie beispielsweise einen Benutzer in den Pilot Pool verschieben, überprüfen Sie, ob die konferenzrichtlinie des Benutzers nach lync Server 2013 verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="68df2-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="68df2-108">Nachdem Sie einen Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="68df2-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="68df2-109">Nachdem Sie die Verbund Routen von lync Server 2010-Edgeserver auf die Pilot-Edgeserver von lync Server 2013 umgestellt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="68df2-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="68df2-110">Nachdem Sie alle Benutzer und nicht-Benutzer-Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der lync Server 2010-Pool leer ist.</span><span class="sxs-lookup"><span data-stu-id="68df2-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="68df2-111">Nachdem Sie überprüft haben, dass der lync Server 2010-Pool leer ist, können Sie den Pool deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="68df2-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="68df2-112">Details zum Deaktivieren des Legacy-lync Server 2010-Pools und-Servers finden Sie unter [Phase 8: Legacy-Pools der decommission-Version](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="68df2-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

