---
title: Lync Server 2013 Kompatibilität mit lync Server 2010 Ausfallsicherheit von großstädtischen Standorten
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
ms.openlocfilehash: a7f1c637c49784dd5acb81c26d8ab36400730278
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="f6f42-102">Ausfallsicherheit für lync Server 2010 Metropole-Standort</span><span class="sxs-lookup"><span data-stu-id="f6f42-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6f42-103">_**Letztes Änderungsstand des Themas:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="f6f42-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="f6f42-104">Die für lync Server 2010 unterstützte Lösung für die Ausfallsicherheit von Metropolitan Site wird für lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6f42-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="f6f42-105">Diese Lösung beinhaltete einen einzelnen Front-End-Pool, der zwei Rechenzentren im selben innerstädtischen Gebiet umfasst.</span><span class="sxs-lookup"><span data-stu-id="f6f42-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="f6f42-106">Die ausfallsicherheitslösung für den Standort Metropolitan Site wurde entwickelt, um den Verlust eines vollständigen Datencenters wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6f42-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="f6f42-107">Wenn Sie Ihren Pool über zwei Rechenzentren hinweg überspannen, setzen Sie normalerweise die Hälfte Ihrer Front-Ends in ein Datencenter und die andere Hälfte in das zweite Datencenter.</span><span class="sxs-lookup"><span data-stu-id="f6f42-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="f6f42-108">Wenn Sie ein gesamtes Rechenzentrum verlieren, haben Sie die Hälfte Ihrer Front-End-Server verloren.</span><span class="sxs-lookup"><span data-stu-id="f6f42-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="f6f42-109">Dies kann Probleme mit dem neuen Modell für verteilte Systeme für Front-End-Pools in lync Server 2013 verursachen.</span><span class="sxs-lookup"><span data-stu-id="f6f42-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="f6f42-110">Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="f6f42-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

