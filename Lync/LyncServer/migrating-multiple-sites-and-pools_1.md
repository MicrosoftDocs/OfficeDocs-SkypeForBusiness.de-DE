---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf8de79830dab0b85bd5346da24cf3c4222ed696
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="9ae77-102">Migrieren von mehreren Standorten und Pools</span><span class="sxs-lookup"><span data-stu-id="9ae77-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ae77-103">_**Letztes Änderungsstand des Themas:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="9ae77-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="9ae77-104">Lync Server 2013 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools.</span><span class="sxs-lookup"><span data-stu-id="9ae77-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="9ae77-105">Der Vorgang der Migration mehrerer Pools von Office Communications Server 2007 R2 zu lync Server 2013 erfordert folgende Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="9ae77-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="9ae77-106">Nachdem Sie einen lync Server 2013 Pilot-Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode für die Überprüfung der Funktionalität der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9ae77-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="9ae77-107">Nachdem Sie eine Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="9ae77-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="9ae77-108">Nachdem Sie die Verbund Routen von Office Communications Server 2007 R2-Edgeserver zu den Pilot lync Server 2013-Edgeserver gewechselt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="9ae77-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="9ae77-109">Nachdem Sie alle Benutzer und nicht-Benutzer Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Office Communications Server 2007 R2 Pool leer ist.</span><span class="sxs-lookup"><span data-stu-id="9ae77-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="9ae77-110">Nachdem Sie überprüft haben, dass der Office Communications Server 2007 R2 Pool leer ist, können Sie den Pool deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9ae77-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="9ae77-111">Ausführliche Informationen zum Deaktivieren des Legacy Office Communications Server 2007 R2 Pools und der Server finden Sie unter [Phase 10: decommission Legacy Site](phase-10-decommission-legacy-site.md).</span><span class="sxs-lookup"><span data-stu-id="9ae77-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

