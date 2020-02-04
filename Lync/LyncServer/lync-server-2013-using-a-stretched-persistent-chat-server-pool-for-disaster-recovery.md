---
title: Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d5091623e381191d23ae0c8a62835577a1f66a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="af18e-102">Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af18e-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af18e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="af18e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="af18e-104">Die Disaster Recovery-Lösung für den Server für beständigen Chat basiert auf einem ausgestreckten beständigen Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="af18e-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="af18e-105">Dies ähnelt der Stabilität von Metropolitan Site in lync Server 2010; Es gibt jedoch keine Voraussetzung für ein gedehntes virtuelles lokales Netzwerk (VLAN).</span><span class="sxs-lookup"><span data-stu-id="af18e-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="af18e-106">Indem Sie den Serverpool für beständigen Chat Strecken, konfigurieren Sie im Wesentlichen einen Pool in der Topologie logisch, aber Sie platzieren die Server physisch in einem Pool in zwei unterschiedlichen Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="af18e-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="af18e-107">Konfigurieren Sie die SQL Server-Spiegelung für die Datenbank auf die gleiche Weise, und stellen Sie die Datenbank und die Spiegelung im gleichen Rechenzentrum bereit.</span><span class="sxs-lookup"><span data-stu-id="af18e-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="af18e-108">Sie müssen eine Sicherungsdatenbank im sekundären Rechenzentrum konfigurieren (mit einem optionalen Mirror, um eine höhere Verfügbarkeit während der Disaster Recovery zu gewährleisten).</span><span class="sxs-lookup"><span data-stu-id="af18e-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="af18e-109">Hierbei handelt es sich um die Backup-Datenbank, die für ein Failover während der Disaster Recovery verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="af18e-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="af18e-110">Ausführliche Informationen zum Konfigurieren der SQL Server-Spiegelung für eine höhere Verfügbarkeit finden Sie unter [SQL Server-Spiegelung in lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="af18e-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="af18e-111">Details zum Failover der Datenbank für die Disaster Recovery finden Sie unter [Einrichten des SQL Server-Protokollversands in lync Server 2013 für die primäre Datenbank des beständigen Chats](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) und Einrichten des [SQL Server-Protokollversands zwischen der primären Spiegelung und der sekundären Protokollversanddatenbank in lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span><span class="sxs-lookup"><span data-stu-id="af18e-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

