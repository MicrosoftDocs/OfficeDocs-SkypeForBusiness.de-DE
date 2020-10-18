---
title: 'Lync Server 2013: neue Features für die Notfallwiederherstellung und hohe Verfügbarkeit'
description: 'Lync Server 2013: neue Features für die Notfallwiederherstellung und hohe Verfügbarkeit.'
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
ms.openlocfilehash: 92816f61b66d9eed76c16286aaa6c7392dca7708
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578861"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="774d1-103">Neue Features für die Notfallwiederherstellung und hohe Verfügbarkeit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="774d1-103">New disaster recovery and high availability features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="774d1-104">_**Letztes Änderungsstand des Themas:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="774d1-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="774d1-105">Wie in lync Server 2010 basiert das Hauptsystem für hohe Verfügbarkeit (ha) für lync Server 2013 auf der Server Redundanz über das Pooling.</span><span class="sxs-lookup"><span data-stu-id="774d1-105">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="774d1-106">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="774d1-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="774d1-107">Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="774d1-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="774d1-108">Lync Server 2013 fügt neue Notfall Wiederherstellungsmaßnahmen hinzu, indem Sie das Koppeln von Front-End-Pools in zwei Rechenzentren ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="774d1-108">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="774d1-109">Wenn einer der gepaarten Pools ausfällt, kann ein Administrator ein Failover für die Benutzer aus diesem Pool mit dem anderen Pool im Paar durchführen, um eine Fortsetzung des Diensts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="774d1-109">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="774d1-110">Für diese Funktionalität sind keine teuren Netzwerk-oder Hardwarelösungen wie Speichernetzwerke oder freigegebene Datenträger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="774d1-110">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="774d1-111">Lync Server 2013 fügt auch eine hohe Verfügbarkeit von Back-End-Servern hinzu.</span><span class="sxs-lookup"><span data-stu-id="774d1-111">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="774d1-112">Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für eine Front-End-Pool bereitstellen und die synchrone SQL-Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausführen.</span><span class="sxs-lookup"><span data-stu-id="774d1-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="774d1-113">Sie können auswählen, ob ein Zeuge für die Spiegelung bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="774d1-113">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="774d1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="774d1-114">See Also</span></span>


[<span data-ttu-id="774d1-115">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="774d1-115">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

