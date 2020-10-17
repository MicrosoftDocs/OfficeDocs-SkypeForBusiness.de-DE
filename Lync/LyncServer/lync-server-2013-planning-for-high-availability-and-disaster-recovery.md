---
title: 'Lync Server 2013: Planen der hohen Verfügbarkeit und Notfallwiederherstellung'
description: 'Lync Server 2013: Planung für hohe Verfügbarkeit und Notfallwiederherstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb5f430201c48738421c4fbe72151ca58173898
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571841"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="7f3d1-103">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f3d1-103">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f3d1-104">_**Letztes Änderungsstand des Themas:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="7f3d1-104">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="7f3d1-105">Wie in lync Server 2010 basiert das Hauptsystem für hohe Verfügbarkeit für die meisten Serverrollen in lync Server 2013 auf der Serverredundanz über das Pooling.</span><span class="sxs-lookup"><span data-stu-id="7f3d1-105">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="7f3d1-106">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="7f3d1-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="7f3d1-107">Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="7f3d1-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="7f3d1-108">Lync Server 2013 fügt neue Notfall Wiederherstellungsmaßnahmen für Front-End-Pools hinzu, indem die geografische Verteilung Ihrer Server in zwei Rechenzentren eingeführt wird, um den Dienst fortzusetzen, wenn ein ganzer Pool oder eine gesamte Website ausfällt.</span><span class="sxs-lookup"><span data-stu-id="7f3d1-108">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="7f3d1-109">Lync Server 2013 verbessert auch die hohe Verfügbarkeit von Back-End-Servern, indem die synchrone SQL-Spiegelung für Ihre Back-End-Datenbankenunter stützt wird.</span><span class="sxs-lookup"><span data-stu-id="7f3d1-109">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="7f3d1-110">In diesem Abschnitt werden diese wichtigen Features für hohe Verfügbarkeit und Notfallwiederherstellung erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für Ihre anderen Serverrollen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="7f3d1-110">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f3d1-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7f3d1-111">In This Section</span></span>

  - [<span data-ttu-id="7f3d1-112">Front-End-Pool Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f3d1-112">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="7f3d1-113">Edgeserver Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f3d1-113">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="7f3d1-114">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f3d1-114">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="7f3d1-115">Anrufverwaltungsfunktionen für die Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f3d1-115">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="7f3d1-116">Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f3d1-116">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="7f3d1-117">Ausfallsicherheit für lync Server 2010 Metropole-Standort</span><span class="sxs-lookup"><span data-stu-id="7f3d1-117">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

