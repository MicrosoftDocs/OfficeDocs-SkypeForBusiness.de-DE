---
title: 'Lync Server 2013: Für den Director erforderliche Komponenten'
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
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="719c7-102">Für den Director erforderliche Komponenten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="719c7-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="719c7-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="719c7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="719c7-104">Die einzige Komponente, die zum Erstellen und Konfigurieren eines Directors erforderlich ist, besteht darin, die Director-Serverrolle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="719c7-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="719c7-105">Dazu verwenden Sie den Topologie-Generator und definieren entweder einen einzelnen Computerpool oder einen Pool mit mehreren Computern im Director-Pool-Knoten.</span><span class="sxs-lookup"><span data-stu-id="719c7-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="719c7-106">Nachdem Sie den Director-oder Director-Pool definiert haben, führen Sie den lync Server-Bereitstellungs-Assistenten auf dem Computer aus, der als Director ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="719c7-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="719c7-107">Im Fall eines Director-Pools führen Sie den lync Server-Bereitstellungs-Assistenten auf jedem Server aus, der Mitglied des Pools sein soll.</span><span class="sxs-lookup"><span data-stu-id="719c7-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="719c7-108">Topologien verfügen</span><span class="sxs-lookup"><span data-stu-id="719c7-108">Topologies</span></span>

<span data-ttu-id="719c7-109">Sie können einen einzelnen Director-Server oder einen Director-Pool implementieren.</span><span class="sxs-lookup"><span data-stu-id="719c7-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="719c7-110">Der Director ist immer ein separater Server oder Pool, nicht mit einer anderen Serverrolle in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="719c7-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="719c7-111">Wenn Sie Directors nicht bereitstellen, übernimmt der Front-End-Server oder der Front-End-Pool die Director-Rolle.</span><span class="sxs-lookup"><span data-stu-id="719c7-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="719c7-112">Ein Pool von Directors muss Load Balanced sein.</span><span class="sxs-lookup"><span data-stu-id="719c7-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="719c7-113">Sie können eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="719c7-113">You can do one of the following:</span></span>

  - <span data-ttu-id="719c7-114">Erstellen Sie eine Topologie, die ein Hardwarelastenausgleich für Webdienste und DNS (Domain Name System)-Lastenausgleich für die anderen Datenverkehrstypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="719c7-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="719c7-115">Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="719c7-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="719c7-116">Erstellen Sie eine Topologie, die ein Hardware-Lastenausgleichsmodul für den für den Director-Pool erforderlichen Lastenausgleich verwendet.</span><span class="sxs-lookup"><span data-stu-id="719c7-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="719c7-117">Skalierter Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="719c7-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

