---
title: 'Lync Server 2013: Neue Funktionen für Notfallwiederherstellung und hohe Verfügbarkeit'
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
ms.openlocfilehash: aabac29c5e866c4bfeff8ad79d392578d52ba650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="8c3fb-102">Neue Funktionen für Notfallwiederherstellung und hohe Verfügbarkeit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c3fb-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c3fb-103">_**Letztes Änderungsdatum des Themas:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="8c3fb-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="8c3fb-104">Wie in lync Server 2010 basiert das Hauptsystem für hohe Verfügbarkeit (ha) für lync Server 2013 auf Server Redundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="8c3fb-105">Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="8c3fb-106">Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="8c3fb-107">Lync Server 2013 fügt neue Wiederherstellungsmaßnahmen für Notfälle hinzu, indem es Ihnen ermöglicht, Front-End-Pools in zwei Rechenzentren zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="8c3fb-108">Wenn eines der gekoppelten Pools ausfällt, kann ein Administrator die Benutzer aus diesem Pool mit dem anderen Pool des Paars Failover, um die Fortsetzung des Diensts zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="8c3fb-109">Für diese Funktionalität sind keine kostspieligen Netzwerk-oder Hardwarelösungen wie Speichernetzwerke oder freigegebene Datenträger erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="8c3fb-110">Lync Server 2013 fügt auch eine höhere Verfügbarkeit für den Back-End-Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="8c3fb-111">Hierbei handelt es sich um eine optionale Topologie, in der Sie zwei Back-End-Server für einen Front-End-Pool bereitstellen und die synchrone SQL-Spiegelung für alle lync-Datenbankeneinrichten, die auf den Back-End-Servern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="8c3fb-112">Sie können auswählen, ob Sie einen Zeugen für den Spiegel bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8c3fb-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8c3fb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c3fb-113">See Also</span></span>


[<span data-ttu-id="8c3fb-114">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c3fb-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

