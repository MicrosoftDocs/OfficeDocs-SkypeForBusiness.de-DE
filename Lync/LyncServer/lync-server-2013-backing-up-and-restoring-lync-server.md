---
title: 'Lync Server 2013: Sichern und Wiederherstellen lync Server'
description: 'Lync Server 2013: Sichern und Wiederherstellen von lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1a7024b2264fb895d1562a6da0775f9397644b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543781"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="a062a-103">Sichern und Wiederherstellen lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a062a-103">Backing up and restoring Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a062a-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a062a-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a062a-105">In diesem Abschnitt finden Sie die bewährten Methoden zum Sichern Ihrer lync Server 2013 Daten sowie zum Wiederherstellen bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="a062a-105">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="a062a-106">Diese bewährten Methoden gelten für die folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="a062a-106">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="a062a-107">Ein ganzer lync Server Pool eines beliebigen Typs (Front-End-Server, Edgeserver, Vermittlungsserver, beständiger Chat Server oder Director) oder ein einzelner Server in einem dieser Pools.</span><span class="sxs-lookup"><span data-stu-id="a062a-107">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="a062a-108">Der zentrale Verwaltungs Server</span><span class="sxs-lookup"><span data-stu-id="a062a-108">The Central Management Server</span></span>

  - <span data-ttu-id="a062a-109">Ein Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="a062a-109">A Standard Edition server</span></span>

  - <span data-ttu-id="a062a-110">Ein Enterprise Edition-Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="a062a-110">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="a062a-111">Ein Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="a062a-111">A File Store</span></span>

  - <span data-ttu-id="a062a-112">Eine Datenbank für Archivierungsdatenbank, Überwachungsdatenbank oder beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="a062a-112">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="a062a-113">Dieser Abschnitt enthält keine Informationen zum Wiederherstellen einer gesamten Website oder zum Entwickeln einer Standby-Website.</span><span class="sxs-lookup"><span data-stu-id="a062a-113">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="a062a-114">Ausführliche Informationen zum Entwickeln einer Notfallwiederherstellungslösung mit gepaarten Front-End-Pools finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a062a-114">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="a062a-115">Dies ist die empfohlene Methode für die Planung der Notfallwiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="a062a-115">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="a062a-116">Wenn Sie gekoppelte Front-End-Pools bereitgestellt haben und einer dieser Pools fehlschlägt und nicht mehr wiederhergestellt werden kann, können Sie diesen Pool mit einem neuen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aus dem gekoppelten Pool wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="a062a-116">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="a062a-117">Ausführliche Informationen zu den Schritten zum Durchführen dieser Wiederherstellung finden Sie unter [failing over a Pool in lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="a062a-117">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="a062a-118">Wenn Sie später einen fehlerhaften und nicht behebbaren Pool erneut erstellen möchten, der Teil eines Front-End-Paars war, können Sie die Schritte unter [Durchführen eines ABC-Front-End-Pool-Failovers in lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="a062a-118">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="a062a-119">Bei der hier beschriebenen Methodik werden besondere Überlegungen während der Planungsphase mit berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a062a-119">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="a062a-120">Ausführliche Informationen finden Sie unter [Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="a062a-120">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a062a-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a062a-121">In This Section</span></span>

  - [<span data-ttu-id="a062a-122">Vorbereiten der lync Server 2013 Sicherung und-Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="a062a-122">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="a062a-123">Sichern von Daten und Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a062a-123">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="a062a-124">Wiederherstellen von Daten und Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a062a-124">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="a062a-125">Arbeitsblätter zur Sicherung und Wiederherstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a062a-125">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

