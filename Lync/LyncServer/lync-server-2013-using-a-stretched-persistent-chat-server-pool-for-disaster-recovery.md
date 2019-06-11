---
title: Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cced4904619fdbda87fecb29f35f11b40270c0ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="92def-102">Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92def-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92def-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="92def-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="92def-104">Die Disaster Recovery-Lösung für den Server für beständigen Chat basiert auf einem ausgestreckten beständigen Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="92def-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="92def-105">Dies ähnelt der Stabilität von Metropolitan Site in lync Server 2010; Es gibt jedoch keine Voraussetzung für ein gedehntes virtuelles lokales Netzwerk (VLAN).</span><span class="sxs-lookup"><span data-stu-id="92def-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="92def-106">Indem Sie den Serverpool für beständigen Chat Strecken, konfigurieren Sie im Wesentlichen einen Pool in der Topologie logisch, aber Sie platzieren die Server physisch in einem Pool in zwei unterschiedlichen Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="92def-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="92def-107">Konfigurieren Sie die SQL Server-Spiegelung für die Datenbank auf die gleiche Weise, und stellen Sie die Datenbank und die Spiegelung im gleichen Rechenzentrum bereit.</span><span class="sxs-lookup"><span data-stu-id="92def-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="92def-108">Sie müssen eine Sicherungsdatenbank im sekundären Rechenzentrum konfigurieren (mit einem optionalen Mirror, um eine höhere Verfügbarkeit während der Disaster Recovery zu gewährleisten).</span><span class="sxs-lookup"><span data-stu-id="92def-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="92def-109">Hierbei handelt es sich um die Backup-Datenbank, die für ein Failover während der Disaster Recovery verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="92def-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="92def-110">Ausführliche Informationen zum Konfigurieren der SQL Server-Spiegelung für eine höhere Verfügbarkeit finden Sie unter [SQL Server-Spiegelung in lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="92def-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="92def-111">Details zum Failover der Datenbank für die Disaster Recovery finden Sie unter [Einrichten des SQL Server-Protokollversands in lync Server 2013 für die primäre Datenbank des](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) beständigen Chats und Einrichten des [SQL Server-Protokollversands zwischen der primären Spiegelung und dem Protokoll. Sekundäre Datenbank für den Versand in lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)</span><span class="sxs-lookup"><span data-stu-id="92def-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

