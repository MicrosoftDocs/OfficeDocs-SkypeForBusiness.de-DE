---
title: 'Lync Server 2013: Planen der hohen Verfügbarkeit und Notfallwiederherstellung'
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
ms.openlocfilehash: 38a41585da7cb247dc955b3f4e18ee4812ef5a2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="45bdf-102">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45bdf-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45bdf-103">_**Letztes Änderungsstand des Themas:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="45bdf-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="45bdf-104">Wie in lync Server 2010 basiert das Hauptsystem für hohe Verfügbarkeit für die meisten Serverrollen in lync Server 2013 auf der Serverredundanz über das Pooling.</span><span class="sxs-lookup"><span data-stu-id="45bdf-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="45bdf-105">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen dieselbe Rolle ausgeführt wird, die Arbeitslast dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="45bdf-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="45bdf-106">Dies gilt für Front-End-Server, Edgeserver, Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="45bdf-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="45bdf-107">Lync Server 2013 fügt neue Notfall Wiederherstellungsmaßnahmen für Front-End-Pools hinzu, indem die geografische Verteilung Ihrer Server in zwei Rechenzentren eingeführt wird, um den Dienst fortzusetzen, wenn ein ganzer Pool oder eine gesamte Website ausfällt.</span><span class="sxs-lookup"><span data-stu-id="45bdf-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="45bdf-108">Lync Server 2013 verbessert auch die hohe Verfügbarkeit von Back-End-Servern, indem die synchrone SQL-Spiegelung für Ihre Back-End-Datenbankenunter stützt wird.</span><span class="sxs-lookup"><span data-stu-id="45bdf-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="45bdf-109">In diesem Abschnitt werden diese wichtigen Features für hohe Verfügbarkeit und Notfallwiederherstellung erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für Ihre anderen Serverrollen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="45bdf-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="45bdf-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="45bdf-110">In This Section</span></span>

  - [<span data-ttu-id="45bdf-111">Front-End-Pool Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45bdf-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="45bdf-112">Edgeserver Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45bdf-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="45bdf-113">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45bdf-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="45bdf-114">Anrufverwaltungsfunktionen für die Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45bdf-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="45bdf-115">Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45bdf-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="45bdf-116">Ausfallsicherheit für lync Server 2010 Metropole-Standort</span><span class="sxs-lookup"><span data-stu-id="45bdf-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

