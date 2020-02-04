---
title: Lync Server 2013-Kompatibilität mit der Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="40002-102">Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="40002-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40002-103">_**Letztes Änderungsdatum des Themas:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="40002-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="40002-104">Die für lync Server 2010 unterstützte Lösung für die Stabilität der Metropolitan-Website wird für lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="40002-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="40002-105">Diese Lösung umfasst einen einzigen Front-End-Pool über zwei Rechenzentren im gleichen Ballungsraum.</span><span class="sxs-lookup"><span data-stu-id="40002-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="40002-106">Die Resilienz-Lösung für Metropolitan Site wurde entwickelt, um den Verlust eines vollständigen Rechenzentrums zu beheben.</span><span class="sxs-lookup"><span data-stu-id="40002-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="40002-107">Wenn Sie Ihren Pool über zwei Rechenzentren spannen, stellen Sie normalerweise die Hälfte Ihrer Front-Ends in einem Rechenzentrum und die andere Hälfte in das zweite Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="40002-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="40002-108">Wenn Sie ein gesamtes Rechenzentrum verlieren, haben Sie die Hälfte der Front-End-Server verloren.</span><span class="sxs-lookup"><span data-stu-id="40002-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="40002-109">Dies kann zu Problemen mit dem neuen verteilten Systemmodell für Front-End-Pools in lync Server 2013 führen.</span><span class="sxs-lookup"><span data-stu-id="40002-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="40002-110">Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="40002-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

