---
title: 'Lync Server 2013: Planen der hohen Verfügbarkeit und der Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="96e02-102">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e02-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96e02-103">_**Letztes Änderungsdatum des Themas:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="96e02-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="96e02-104">Wie in lync Server 2010 basiert das wichtigste Hochverfügbarkeits-Schema für die meisten Serverrollen in lync Server 2013 auf Server Redundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="96e02-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="96e02-105">Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen.</span><span class="sxs-lookup"><span data-stu-id="96e02-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="96e02-106">Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="96e02-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="96e02-107">Lync Server 2013 fügt neue Disaster Recovery-Maßnahmen für Front-End-Pools hinzu, indem geografische dispersement Ihrer Server in zwei Rechenzentren eingeführt werden, um den Service fortzusetzen, wenn ein ganzer Pool oder eine gesamte Website heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="96e02-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="96e02-108">Lync Server 2013 verbessert auch die höhere Verfügbarkeit von Back-End-Servern, indem die synchrone SQL-Spiegelung für Ihre Back-End-Datenbankenunter stützt wird.</span><span class="sxs-lookup"><span data-stu-id="96e02-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="96e02-109">In diesem Abschnitt werden diese wichtigen Funktionen für hohe Verfügbarkeit und Disaster Recovery erläutert, und es werden auch die Schritte beschrieben, die Sie für eine hohe Verfügbarkeit und Disaster Recovery für Ihre anderen Serverrollen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="96e02-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="96e02-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="96e02-110">In This Section</span></span>

  - [<span data-ttu-id="96e02-111">Notfallwiederherstellung eines Front-End-Pools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e02-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="96e02-112">Notfallwiederherstellung für Edgeserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e02-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="96e02-113">Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e02-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="96e02-114">Anrufverwaltungsfunktionen für die Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e02-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="96e02-115">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96e02-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="96e02-116">Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="96e02-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

