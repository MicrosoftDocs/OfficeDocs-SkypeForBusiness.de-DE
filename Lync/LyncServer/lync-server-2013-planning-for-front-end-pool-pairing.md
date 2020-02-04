---
title: 'Lync Server 2013: Planen der Bildung von Front-End-Poolpaaren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="a05fa-102">Planen der Bildung von Front-End-Poolpaaren in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a05fa-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a05fa-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a05fa-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a05fa-104">Stellen Sie für die besten Möglichkeiten zur Disaster Recovery in lync Server 2013 Paare von Front-End-Pools auf zwei geografisch verteilten Websites bereit.</span><span class="sxs-lookup"><span data-stu-id="a05fa-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="a05fa-105">Jede Website enthält einen Front-End-Pool, der mit einem entsprechenden Front-End-Pool in der anderen Website gekoppelt ist.</span><span class="sxs-lookup"><span data-stu-id="a05fa-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="a05fa-106">Beide Websites sind aktiv, und der lync Server-Sicherungsdienst bietet Echtzeitdaten Replikation, damit die Pools synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="a05fa-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="a05fa-107">Der Sicherungsdienst ist ein neues Feature in lync Server 2013, das zur Unterstützung der Disaster Recovery-Lösung entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="a05fa-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="a05fa-108">Sie wird in einem Front-End-Pool installiert, wenn Sie den Pool mit einem anderen Front-End-Pool koppeln.</span><span class="sxs-lookup"><span data-stu-id="a05fa-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="a05fa-109">Wenn der Pool auf einer Website fehlschlägt, können Sie die Benutzer aus diesem Pool in den Pool auf der anderen Website übertragen, wodurch Dienste für alle Benutzer in beiden Pools bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a05fa-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="a05fa-110">Bei der Kapazitätsplanung sollte jeder Pool so konzipiert sein, dass er die Arbeitslasten aller Benutzer in beiden Pools im Fall eines Notfalls behandelt.</span><span class="sxs-lookup"><span data-stu-id="a05fa-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a05fa-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a05fa-111">In This Section</span></span>

  - [<span data-ttu-id="a05fa-112">Unterstützte Pool-Kopplungs Optionen und bewährte Methoden für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a05fa-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="a05fa-113">Beziehungen von Sicherungsregistrierungsstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a05fa-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="a05fa-114">Wiederherstellungsdauer bei einem Failover und Failback eines Pools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a05fa-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="a05fa-115">Failover des zentralen Verwaltungsspeichers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a05fa-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="a05fa-116">Datensicherheit beim Bilden von Front-End-Poolpaaren in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a05fa-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

