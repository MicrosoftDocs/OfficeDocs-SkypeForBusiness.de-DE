---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7412d0ffb1a5d24c2f30b76b987a16903253bfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="00a22-102">Migrieren von mehreren Standorten und Pools</span><span class="sxs-lookup"><span data-stu-id="00a22-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00a22-103">_**Letztes Änderungsdatum des Themas:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="00a22-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="00a22-104">Lync Server 2013 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools.</span><span class="sxs-lookup"><span data-stu-id="00a22-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="00a22-105">Der Vorgang zum Migrieren mehrerer Pools von Office Communications Server 2007 R2 zu lync Server 2013 erfordert die folgenden Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="00a22-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="00a22-106">Nach der Bereitstellungeines lync Server 2013-pilotpools müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode zum Überprüfen der Funktionalität der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="00a22-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="00a22-107">Nachdem Sie einen Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="00a22-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="00a22-108">Nachdem Sie die Verbund Routen von Office Communications Server 2007 R2-Edgeserver auf die Pilot-Edgeserver von lync Server 2013 umgestellt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="00a22-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="00a22-109">Nachdem Sie alle Benutzer und nicht-Benutzer-Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Office Communications Server 2007 R2-Pool leer ist.</span><span class="sxs-lookup"><span data-stu-id="00a22-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="00a22-110">Nachdem Sie überprüft haben, dass der 2007 R2-Pool von Office Communications Server leer ist, können Sie den Pool deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="00a22-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="00a22-111">Details zum Deaktivieren des Legacy-Pools und der Server für Office Communications Server 2007 R2 finden Sie unter [Phase 10: Legacy Website](phase-10-decommission-legacy-site.md)der decommission.</span><span class="sxs-lookup"><span data-stu-id="00a22-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

