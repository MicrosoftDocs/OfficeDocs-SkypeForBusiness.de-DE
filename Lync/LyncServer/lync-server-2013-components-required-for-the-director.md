---
title: 'Lync Server 2013: erforderliche Komponenten für den Director'
description: 'Lync Server 2013: erforderliche Komponenten für den Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f717b9ddb9557f212321cdab075713a4b85c2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549501"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="da5ac-103">Erforderliche Komponenten für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da5ac-103">Components required for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da5ac-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="da5ac-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="da5ac-105">Die einzige Komponente, die zum Erstellen und Konfigurieren eines Directors erforderlich ist, ist die Bereitstellung der Director-Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="da5ac-105">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="da5ac-106">Hierzu verwenden Sie den Topologie-Generator und definieren entweder einen Pool mit einem einzelnen Computer oder einen Pool mit mehreren Computern im Knoten Directorpool.</span><span class="sxs-lookup"><span data-stu-id="da5ac-106">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="da5ac-107">Nachdem Sie den Director oder Directorpool definiert haben, führen Sie den lync Server-Bereitstellungs-Assistenten auf dem Computer aus, der als Director verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="da5ac-107">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="da5ac-108">Im Fall eines Directorpool führen Sie den lync Server-Bereitstellungs-Assistenten auf jedem Server aus, der Mitglied des Pools sein soll.</span><span class="sxs-lookup"><span data-stu-id="da5ac-108">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="da5ac-109">Topologien</span><span class="sxs-lookup"><span data-stu-id="da5ac-109">Topologies</span></span>

<span data-ttu-id="da5ac-110">Sie können einen einzelnen Director-Server oder einen Directorpool implementieren.</span><span class="sxs-lookup"><span data-stu-id="da5ac-110">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="da5ac-111">Bei dem Director handelt es sich immer um einen separaten Server oder Pool, der nicht mit einer anderen Serverrolle in lync Server 2013 verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="da5ac-111">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da5ac-112">Wenn Sie Directors nicht bereitstellen, übernimmt der Front-End-Server oder Front-End-Pool die Director-Rolle.</span><span class="sxs-lookup"><span data-stu-id="da5ac-112">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="da5ac-113">Ein Director-Pool muss Lastenausgleich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="da5ac-113">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="da5ac-114">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="da5ac-114">You can do one of the following:</span></span>

  - <span data-ttu-id="da5ac-115">Erstellen Sie eine Topologie, die ein Hardwaregerät zum Lastenausgleich für Webdienste und einen DNS (Domain Name System)-Lastenausgleich für die anderen Datenverkehrstypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="da5ac-115">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="da5ac-116">Skalierte Directorpool-DNS-Lastenausgleich und Hardwarelastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da5ac-116">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="da5ac-117">Erstellen Sie eine Topologie, die ein Hardwaregerät zum Lastenausgleich für den Lastenausgleich verwendet, der für den Directorpool erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="da5ac-117">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="da5ac-118">Skaliertes Directorpool-Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da5ac-118">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

