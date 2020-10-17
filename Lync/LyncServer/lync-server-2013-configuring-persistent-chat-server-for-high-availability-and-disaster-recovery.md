---
title: Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung
description: Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13935f2ec690deb7f896c13d185680ce1122a892
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544831"
---
# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="ef9ab-103">Konfigurieren des Servers für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9ab-103">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef9ab-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ef9ab-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ef9ab-105">Die lync Server 2013, die Server Dienste für beständigen Chat verwenden eine *gestreckte Pool* Konfiguration für die Notfallwiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="ef9ab-105">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="ef9ab-106">Ein gestreckter Pool ist ein Pool mit Computern, die zwischen zwei physischen Rechenzentren verteilt sind, aber sich innerhalb eines einzelnen logischen lync Server-Standorts befinden.</span><span class="sxs-lookup"><span data-stu-id="ef9ab-106">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef9ab-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ef9ab-107">In This Section</span></span>

  - [<span data-ttu-id="ef9ab-108">Erforderliche Ressourcen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9ab-108">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="ef9ab-109">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung mithilfe des Topologie-Generators in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9ab-109">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="ef9ab-110">Verwenden eines ausgedehnten Server Pools für beständigen Chat für die Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9ab-110">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="ef9ab-111">SQL Server Spiegelung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9ab-111">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="ef9ab-112">Einrichten SQL Server Protokollversands in lync Server 2013 für die primäre Datenbank des beständigen Chat Servers</span><span class="sxs-lookup"><span data-stu-id="ef9ab-112">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="ef9ab-113">Einrichten SQL Server Protokollversands zwischen der primären Spiegelung und der sekundären Datenbank des Protokollversands in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9ab-113">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

