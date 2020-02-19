---
title: Lync Server 2013 von Sicherungs Registrierungsstellen Beziehungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07380cbea030f5c9219cef2654b4761f215988e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="01e8c-102">Sicherungs Registrierungs Beziehungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e8c-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01e8c-103">_**Letztes Änderungsstand des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="01e8c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="01e8c-104">Zusätzlich zur Bereitstellung von Notfallwiederherstellungsfunktionen dienen zwei gekoppelte Pools als Sicherungs Registrierungsstellen für einander.</span><span class="sxs-lookup"><span data-stu-id="01e8c-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="01e8c-105">In lync Server 2013 sind Sicherungs Registrierungs Beziehungen zwischen Front-End-Pools immer 1:1 und reziproke.</span><span class="sxs-lookup"><span data-stu-id="01e8c-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="01e8c-106">Das heißt, wenn P1 die Sicherung für P2 ist, muss P2 die Sicherung für P1 sein, und es kann auch keine Sicherung für andere Front-End-Pool sein.</span><span class="sxs-lookup"><span data-stu-id="01e8c-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="01e8c-107">Dies ist eine Änderung gegenüber lync Server 2010, in der Front-End-Pool Sicherungsbeziehungen viele zu eins sein könnten.</span><span class="sxs-lookup"><span data-stu-id="01e8c-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="01e8c-108">Auch wenn Sicherungsbeziehungen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool auch die Sicherungs Registrierungsstelle für eine beliebige Anzahl von Survivable Branch Appliances sein, genau wie in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="01e8c-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="01e8c-109">Beachten Sie, dass lync Server 2013 keine Unterstützung für die Notfallwiederherstellung für Benutzer in einem Survivable Branch Appliance erweitert.</span><span class="sxs-lookup"><span data-stu-id="01e8c-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="01e8c-110">Wenn ein Front-End-Pool, das als Sicherung für eine Survivable Branch Appliance dient, ausfällt, werden Benutzer, die sich beim Survivable Branch Appliance angemeldet haben, in den Ausfall Sicherheitsmodus verfallen, auch wenn Benutzer, die sich im Front-End-Pool befinden, auf die Sicherungs Front-End-Pool Failover.</span><span class="sxs-lookup"><span data-stu-id="01e8c-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

