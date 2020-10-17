---
title: 'Lync Server 2013: unterstützte Server Migrationspfade und Szenarien für die Koexistenz'
description: 'Lync Server 2013: unterstützte Server Migrationspfade und Szenarien für die Koexistenz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d0a40ac6cc6570cf79b56dc896277c83909b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560231"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="8c4e2-103">Unterstützte Server Migrationspfade und Szenarien für die Koexistenz in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c4e2-103">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c4e2-104">_**Letztes Änderungsstand des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="8c4e2-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="8c4e2-105">Lync Server 2013 unterstützt die Migration aus einem der folgenden:</span><span class="sxs-lookup"><span data-stu-id="8c4e2-105">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="8c4e2-106">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8c4e2-106">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="8c4e2-107">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="8c4e2-107">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="8c4e2-108">Die Migration einer Umgebung, in der beide dieser vorherigen Versionen ausgeführt werden, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-108">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="8c4e2-109">Migration aus früheren Versionen, wie Microsoft Office Communications Server 2007 oder Live Communications Server 2005, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-109">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="8c4e2-110">Wenn Ihre frühere Bereitstellung Gruppen Chat umfasste, müssen Sie Sie separat migrieren.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-110">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="8c4e2-111">Migrationsmethoden</span><span class="sxs-lookup"><span data-stu-id="8c4e2-111">Migration Methods</span></span>

<span data-ttu-id="8c4e2-112">Die Migration aller lync Server Topologien und Server Rollen wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-112">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="8c4e2-113">Sie können von einer Topologie zu einer anderen Topologie migrieren, beispielsweise von Standard Edition-Server zu Enterprise Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-113">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="8c4e2-114">Lync Server 2013 unterstützt nur die folgende Migrationsmethode:</span><span class="sxs-lookup"><span data-stu-id="8c4e2-114">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="8c4e2-115">**Side-by-Side-Migration.**</span><span class="sxs-lookup"><span data-stu-id="8c4e2-115">**Side-by-side migration.**</span></span> <span data-ttu-id="8c4e2-116">Bei der parallelen Migration werden lync Server 2013 neben einer vorhandenen Microsoft lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung bereitgestellt, und anschließend werden die Vorgänge auf die neuen Server übertragen und Benutzer zu lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-116">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="8c4e2-117">Diese Methode erfordert zusätzliche Serverplattformen, einschließlich Hardware und Software, während der Migration, und Systemnamen und Poolnamen unterscheiden sich in der neuen Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-117">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="8c4e2-118">Wenn es erforderlich ist, ein Rollback auf die vorherige Version durchführen zu können, können Sie die Vorgänge wieder auf die vorherigen Server verschieben.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-118">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="8c4e2-119">Die Migration in Active Directory-Domänendienste Gesamtstrukturen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-119">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="8c4e2-p104">Die empfohlene Migration erfolgt phasenweise. Ausführliche Informationen zur Migration von einer vorherigen Version, einschließlich der geeigneten Phasen für die Komponentenbereitstellung, finden Sie in den folgenden Themen der Migration-Dokumentation:</span><span class="sxs-lookup"><span data-stu-id="8c4e2-p104">The recommended migration path is a phased approach. For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="8c4e2-122">Migration von Lync Server 2010 zu Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c4e2-122">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="8c4e2-123">Migration von Office Communications Server 2007 R2 zu lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c4e2-123">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="8c4e2-124">Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="8c4e2-124">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="8c4e2-125">Koexistenzszenarien</span><span class="sxs-lookup"><span data-stu-id="8c4e2-125">Coexistence Scenarios</span></span>

<span data-ttu-id="8c4e2-126">Lync Server 2013 können mit Komponenten einer lync Server 2010-Bereitstellung oder einer Office Communications Server 2007 R2-Bereitstellung koexistieren.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-126">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="8c4e2-127">Die gleichzeitige Bereitstellung von lync Server 2013 mit lync Server 2010 und Office Communications Server 2007 R2 (gleichzeitige Bereitstellung aller drei Versionen) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-127">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="8c4e2-128">Während einer phasenweisen Migration, bei der eine frühere lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung vorübergehend mit der neuen lync Server 2013-Bereitstellung koexistiert, ist die Unterstützung für das Routing in gemischten Versionen begrenzt.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-128">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="8c4e2-129">Ausführliche Informationen finden Sie in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-129">For details, see the Migration documentation.</span></span>

<span data-ttu-id="8c4e2-130">Sie müssen separate und unterschiedliche Computer mit Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für Ihre lync Server 2013-Datenbankinstanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-130">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="8c4e2-131">Sie können nicht dieselbe Instanz von SQL Server für eine lync Server 2013 Front-End-Pool verwenden, die Sie für eine lync Server 2010 oder Office Communications Server 2007 R2 Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-131">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="8c4e2-132">Wenn Sie lync Server 2013 im Topologie-Generator für eine Bereitstellung definieren und konfigurieren, die bereits lync Server 2010 oder Office Communications Server 2007 R2 bereitgestellt wurde, können Sie mit dem Topologie-Generator keine Instanz einer lync Server 2013 definieren, die bereits in der Topologie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-132">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="8c4e2-133">Im Topologie-Generator wird die folgende Meldung angezeigt, um Sie über dieses Problem zu informieren: "der SQL Server- \[ FQDN des Servers \] enthält bereits eine SQL-Instanz-Host Rolle" Benutzerspeicher ".</span><span class="sxs-lookup"><span data-stu-id="8c4e2-133">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c4e2-134">Wenn Sie Serverrollen bereitstellen möchten, die für Ihre lync Server 2013-Bereitstellung neu sind, sollten Sie zuerst die vorhandene Bereitstellung wie in der Migrationsdokumentation und in der Bereitstellungsdokumentation beschrieben aktualisieren und dann die neuen Serverrollen wie in der Planungsdokumentation und der Bereitstellungsdokumentation beschrieben bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-134">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="8c4e2-135">Wenn Sie eine frühere Version des Gruppenchats migrieren, migrieren Sie Sie zuletzt, nachdem Sie den Prozess für die Migration aller anderen Komponenten von lync Server 2010 oder Office Communications Server 2007 R2 abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-135">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="8c4e2-136">Informationen zu spezifischen Anforderungen an die Koexistenz und andere Details zur Koexistenz und Migration von lync Server 2010-oder Office Communications Server 2007 R2-und lync Server 2013-Komponenten finden Sie unter [Migration from lync Server 2010 to lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) und [Migration from Office Communications Server 2007 R2 to lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8c4e2-136">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="8c4e2-137">Ausführliche Informationen zur Unterstützung gemischter Versionen für Clients finden Sie unter [Supported Clients from previous Deployments in lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="8c4e2-137">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

