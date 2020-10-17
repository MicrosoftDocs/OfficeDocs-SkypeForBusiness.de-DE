---
title: 'Lync Server 2013: Planen der Front-End-Pool Kopplung'
description: 'Lync Server 2013: Planen der Front-End-Pool Kopplung.'
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
ms.openlocfilehash: ac235cf682e286132836e13b34b457adf2bfc233
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562791"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="71f94-103">Planen der Front-End-Pool Kopplung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f94-103">Planning for Front End pool pairing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71f94-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="71f94-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="71f94-105">Für die besten Möglichkeiten zur Notfallwiederherstellung in lync Server 2013 stellen Sie Paare von Front-End-Pools auf zwei geografisch verteilten Standorten bereit.</span><span class="sxs-lookup"><span data-stu-id="71f94-105">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="71f94-106">Jede Website enthält eine Front-End-Pool, die mit einem entsprechenden Front-End-Pool am anderen Standort gekoppelt ist.</span><span class="sxs-lookup"><span data-stu-id="71f94-106">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="71f94-107">Beide Standorte sind aktiv, und der lync Server Sicherungsdienst bietet eine Echtzeitdaten Replikation, damit die Pools synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="71f94-107">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="71f94-108">Der Sicherungsdienst ist ein neues Feature in lync Server 2013, das zur Unterstützung der Notfallwiederherstellungslösung entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="71f94-108">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="71f94-109">Sie wird auf einem Front-End-Pool installiert, wenn Sie den Pool mit einem anderen Front-End-Pool koppeln.</span><span class="sxs-lookup"><span data-stu-id="71f94-109">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="71f94-110">Wenn für den Pool an einem Standort ein Fehler auftritt, können Sie die Benutzer aus diesem Pool mit dem Pool im anderen Standort verfallen, der dann für alle Benutzer in beiden Pools Dienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="71f94-110">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="71f94-111">Für Kapazitäts Planungszwecke sollte jeder Pool so konzipiert sein, dass er die Arbeitslasten aller Benutzer in beiden Pools im Falle eines Notfalls behandelt.</span><span class="sxs-lookup"><span data-stu-id="71f94-111">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="71f94-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="71f94-112">In This Section</span></span>

  - [<span data-ttu-id="71f94-113">Unterstützte Optionen für das Pool koppeln und bewährte Methoden für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f94-113">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="71f94-114">Sicherungs Registrierungs Beziehungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f94-114">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="71f94-115">Wiederherstellungszeit für Pool-Failover und Pool-Failback in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f94-115">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="71f94-116">Failover des zentralen Verwaltungsspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f94-116">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="71f94-117">Front-End-Pool koppeln von Datensicherheit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f94-117">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

