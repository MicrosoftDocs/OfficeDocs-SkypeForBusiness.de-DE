---
title: 'Lync Server 2013: Beziehungen von Sicherungsregistrierungsstellen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a642c8d8872b2c0d1372a209c9c05dac704ee20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="953a6-102">Beziehungen von Sicherungsregistrierungsstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="953a6-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="953a6-103">_**Letztes Änderungsdatum des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="953a6-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="953a6-104">Neben der Notfallwiederherstellung dienen die verbundenen Pools als Sicherungsregistrierungsstellen füreinander.</span><span class="sxs-lookup"><span data-stu-id="953a6-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="953a6-105">In lync Server 2013 sind Sicherungs Registrierungsstellen Beziehungen zwischen Front-End-Pools immer 1:1 und wechselseitig.</span><span class="sxs-lookup"><span data-stu-id="953a6-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="953a6-106">Dies bedeutet Folgendes: Wenn P1 die Sicherung für P2 ist, muss P2 die Sicherung für P1 sein, und es kann auch keine Sicherung für einen anderen Front-End-Pool sein.</span><span class="sxs-lookup"><span data-stu-id="953a6-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="953a6-107">Hierbei handelt es sich um eine Änderung von lync Server 2010, bei der Backup-Beziehungen im Front-End-Pool viel zu eins sein können.</span><span class="sxs-lookup"><span data-stu-id="953a6-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="953a6-108">Auch wenn die Sicherungsbeziehungen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool weiterhin als Sicherungs Registrierungsstelle für eine beliebige Anzahl von Überlebenden Branch-Appliances, wie in lync Server 2010, eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="953a6-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="953a6-109">Beachten Sie, dass lync Server 2013 die Disaster Recovery-Unterstützung nicht für Benutzer ausdehnt, die auf einer Survivable Branch-Appliance verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="953a6-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="953a6-110">Wenn ein Front-End-Pool, der als Sicherung für eine Survivable Branch-Appliance dient, herunterfällt, fallen Benutzer, die bei der Survivable Branch-Appliance angemeldet sind, in den Stabilitäts Modus, auch wenn Benutzer im Front-End-Pool über einen Failover zum Backup-Front-End-Pool verstoßen haben.</span><span class="sxs-lookup"><span data-stu-id="953a6-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

