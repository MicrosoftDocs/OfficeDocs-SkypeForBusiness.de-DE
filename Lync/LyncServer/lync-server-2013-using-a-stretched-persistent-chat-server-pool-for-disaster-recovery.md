---
title: Verwenden eines ausgedehnten Server Pools für beständigen Chat für die Notfallwiederherstellung
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
ms.openlocfilehash: 1c09231abfae7bbcc32083d7db72d8a4be79ecff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535922"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="1b1f5-102">Verwenden eines ausgedehnten Server Pools für beständigen Chat für die Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b1f5-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b1f5-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="1b1f5-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1b1f5-104">Die Notfallwiederherstellungslösung für den Server für beständigen Chat basiert auf einem ausgedehnten Serverpool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="1b1f5-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="1b1f5-105">Dies ähnelt der Ausfallsicherheit für die Metropolitan Site in lync Server 2010; Es gibt jedoch keine Voraussetzung für ein ausgedehntes virtuelles lokales Netzwerk (VLAN).</span><span class="sxs-lookup"><span data-stu-id="1b1f5-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="1b1f5-106">Wenn Sie den Serverpool für beständigen Chat Strecken, konfigurieren Sie im Wesentlichen einen Pool in der Topologie logisch, aber Sie platzieren die Server physisch im Pool in zwei verschiedenen Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="1b1f5-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="1b1f5-107">Konfigurieren Sie SQL Server Spiegelung für die Datenbank auf die gleiche Weise, und stellen Sie die Datenbank und die Spiegelung im gleichen Rechenzentrum bereit.</span><span class="sxs-lookup"><span data-stu-id="1b1f5-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="1b1f5-108">Sie müssen im sekundären Rechenzentrum eine Sicherungsdatenbank konfigurieren (mit einem optionalen Spiegel, um eine hohe Verfügbarkeit im Fall einer Notfallwiederherstellung zu gewährleisten).</span><span class="sxs-lookup"><span data-stu-id="1b1f5-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="1b1f5-109">Dies ist die Sicherungsdatenbank, die bei der Notfallwiederherstellung für das Failover verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1b1f5-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="1b1f5-110">Ausführliche Informationen zum Konfigurieren SQL Server Spiegelung für hohe Verfügbarkeit finden Sie unter [SQL Server Spiegelung in lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f5-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="1b1f5-111">Ausführliche Informationen zum Failover der Datenbank für die Notfallwiederherstellung finden Sie unter [Einrichten SQL Server Protokollversands in lync Server 2013 für die primäre Datenbank für beständigen Chat](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) und einrichten [SQL Server Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Protokoll versanddatenbank in lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span><span class="sxs-lookup"><span data-stu-id="1b1f5-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

