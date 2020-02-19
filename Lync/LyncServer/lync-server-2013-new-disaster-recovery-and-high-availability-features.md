---
title: 'Lync Server 2013: neue Features für die Notfallwiederherstellung und hohe Verfügbarkeit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 366b58f05e8567659dc630042494f1ede25cf338
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="d3a2a-102">Neue Features für die Notfallwiederherstellung und hohe Verfügbarkeit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3a2a-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3a2a-103">_**Letztes Änderungsstand des Themas:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="d3a2a-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="d3a2a-104">Wie in lync Server 2010 basiert das Hauptsystem für hohe Verfügbarkeit (ha) für lync Server 2013 auf der Server Redundanz über das Pooling.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="d3a2a-105">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="d3a2a-106">Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="d3a2a-107">Lync Server 2013 fügt neue Notfall Wiederherstellungsmaßnahmen hinzu, indem Sie das Koppeln von Front-End-Pools in zwei Rechenzentren ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="d3a2a-108">Wenn einer der gepaarten Pools ausfällt, kann ein Administrator ein Failover für die Benutzer aus diesem Pool mit dem anderen Pool im Paar durchführen, um eine Fortsetzung des Diensts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="d3a2a-109">Für diese Funktionalität sind keine teuren Netzwerk-oder Hardwarelösungen wie Speichernetzwerke oder freigegebene Datenträger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="d3a2a-110">Lync Server 2013 fügt auch eine hohe Verfügbarkeit von Back-End-Servern hinzu.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="d3a2a-111">Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für eine Front-End-Pool bereitstellen und die synchrone SQL-Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausführen.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="d3a2a-112">Sie können auswählen, ob ein Zeuge für die Spiegelung bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d3a2a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3a2a-113">See Also</span></span>


[<span data-ttu-id="d3a2a-114">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3a2a-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

