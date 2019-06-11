---
title: 'Lync Server 2013: Sichern und Wiederherstellen von lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0cf9f9baabd095e54373c31acd4f4522974a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="dd888-102">Sichern und Wiederherstellen von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd888-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd888-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dd888-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dd888-104">In diesem Abschnitt finden Sie die bewährten Methoden zum Sichern Ihrer lync Server 2013-Daten sowie zum Wiederherstellen bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="dd888-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="dd888-105">Diese bewährten Methoden gelten für die folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="dd888-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="dd888-106">Ein gesamter lync Server-Pool eines beliebigen Typs (Front-End-Server, Edgeserver, Vermittlungsserver, beständiger Chat Server oder Director) oder ein einzelner Server in einem dieser Pools.</span><span class="sxs-lookup"><span data-stu-id="dd888-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="dd888-107">Der zentrale Verwaltungs Server</span><span class="sxs-lookup"><span data-stu-id="dd888-107">The Central Management Server</span></span>

  - <span data-ttu-id="dd888-108">Ein Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="dd888-108">A Standard Edition server</span></span>

  - <span data-ttu-id="dd888-109">Ein Enterprise Edition-Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="dd888-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="dd888-110">Ein Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="dd888-110">A File Store</span></span>

  - <span data-ttu-id="dd888-111">Eine Archivierungsdatenbank, eine Überwachungsdatenbank oder eine persistente Chat Datenbank</span><span class="sxs-lookup"><span data-stu-id="dd888-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="dd888-112">Dieser Abschnitt enthält keine Informationen zum Wiederherstellen einer gesamten Website oder zur Entwicklung einer Standby-Website.</span><span class="sxs-lookup"><span data-stu-id="dd888-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="dd888-113">Details zur Entwicklung einer Disaster Recovery-Lösung mit gekoppelten Front-End-Pools finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="dd888-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="dd888-114">Dies ist die empfohlene Methode für die Planung der Notfallwiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="dd888-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="dd888-115">Wenn Sie gekoppelte Front-End-Pools bereitgestellt haben, können Sie diesen Pool mit einem neuen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) aus dem gekoppelten Pool wiederherstellen, wenn eines dieser Pools ausfällt und nicht wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd888-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="dd888-116">Ausführliche Informationen zu den Schritten zum Durchführen dieser Wiederherstellung finden Sie unter [Failover eines Pools in lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="dd888-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="dd888-117">Wenn Sie später einen fehlerhaften und nicht behebbaren Pool erstellen möchten, der Teil eines Front-End-Paars war, können Sie die Schritte unter [Durchführen eines Failovers des ABC-Front-End-Pools in lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd888-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="dd888-118">Die in diesem Dokument beschriebene Methodik umfasst besondere Aspekte in der Planungsphase.</span><span class="sxs-lookup"><span data-stu-id="dd888-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="dd888-119">Ausführliche Informationen finden Sie unter [Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="dd888-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd888-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dd888-120">In This Section</span></span>

  - [<span data-ttu-id="dd888-121">Vorbereiten der Sicherung und Wiederherstellung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd888-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="dd888-122">Sichern von Daten und Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd888-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="dd888-123">Wiederherstellen von Daten und Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd888-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="dd888-124">Arbeitsblätter zum Sichern und Wiederherstellen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd888-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

