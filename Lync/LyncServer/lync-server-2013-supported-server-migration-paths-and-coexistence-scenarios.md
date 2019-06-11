---
title: 'Lync Server 2013: Unterstützte Servermigrationspfade und Koexistenzszenarien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33b2ce878fef53f444e3834e8b1cd40286c24b0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="539e6-102">Unterstützte Servermigrationspfade und Koexistenzszenarien in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="539e6-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="539e6-103">_**Letztes Änderungsdatum des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="539e6-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="539e6-104">Lync Server 2013 unterstützt die Migration von einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="539e6-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="539e6-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="539e6-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="539e6-106">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="539e6-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="539e6-107">Die Migration aus einer Umgebung, auf der diese beiden vorherigen Versionen ausgeführt werden, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="539e6-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="539e6-108">Die Migration aus früheren Versionen, wie etwa Microsoft Office Communications Server 2007 oder Live Communications Server 2005, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="539e6-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="539e6-109">Wenn Ihre vorherige Bereitstellung Gruppen-Chats enthielt, müssen Sie Sie separat migrieren.</span><span class="sxs-lookup"><span data-stu-id="539e6-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="539e6-110">Migrationsmethoden</span><span class="sxs-lookup"><span data-stu-id="539e6-110">Migration Methods</span></span>

<span data-ttu-id="539e6-111">Die Migration aller lync Server-Topologien und Serverrollen wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="539e6-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="539e6-112">Sie können von einer Topologie zu einer anderen Topologie migrieren, einschließlich vom Standard Edition-Server zu Enterprise Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="539e6-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="539e6-113">Lync Server 2013 unterstützt nur die folgende Migrationsmethode:</span><span class="sxs-lookup"><span data-stu-id="539e6-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="539e6-114">**Parallele Migration.**</span><span class="sxs-lookup"><span data-stu-id="539e6-114">**Side-by-side migration.**</span></span> <span data-ttu-id="539e6-115">Bei der parallelen Migration wird lync Server 2013 zusammen mit einer vorhandenen Microsoft lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung bereitgestellt, und Sie können dann Vorgänge auf die neuen Server übertragen und Benutzer zu lync Server 2013 verschieben.</span><span class="sxs-lookup"><span data-stu-id="539e6-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="539e6-116">Diese Methode erfordert zusätzliche Serverplattformen, einschließlich Hardware und Software, während der Migration, und Systemnamen und Poolnamen unterscheiden sich in der neuen Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="539e6-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="539e6-117">Wenn ein Rollback zur vorherigen Version erforderlich ist, können Sie die Vorgänge zurück auf die vorherigen Server verschieben.</span><span class="sxs-lookup"><span data-stu-id="539e6-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="539e6-118">Die Migration in den Active Directory-Domänendienst Gesamtstrukturen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="539e6-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="539e6-119">Der empfohlene Migrationspfad ist ein Phasenbasierter Ansatz.</span><span class="sxs-lookup"><span data-stu-id="539e6-119">The recommended migration path is a phased approach.</span></span> <span data-ttu-id="539e6-120">Details zur Migration von einer früheren Version, einschließlich der entsprechenden Phasen der Komponentenbereitstellung, finden Sie in den folgenden Themen in der Migrationsdokumentation:</span><span class="sxs-lookup"><span data-stu-id="539e6-120">For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="539e6-121">Migration von Lync Server 2010 zu Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="539e6-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="539e6-122">Migration von Office Communications Server 2007 R2 zu Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="539e6-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="539e6-123">Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="539e6-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="539e6-124">Koexistenz-Szenarien</span><span class="sxs-lookup"><span data-stu-id="539e6-124">Coexistence Scenarios</span></span>

<span data-ttu-id="539e6-125">Lync Server 2013 kann mit Komponenten einer lync Server 2010-Bereitstellung oder einer Office Communications Server 2007 R2-Bereitstellung koexistieren.</span><span class="sxs-lookup"><span data-stu-id="539e6-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="539e6-126">Die gleichzeitige Bereitstellung von lync Server 2013 mit lync Server 2010 und Office Communications Server 2007 R2 (gleichzeitige Bereitstellung aller drei Versionen) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="539e6-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="539e6-127">Während einer phasenweisen Migration, bei der eine vorherige lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung temporär mit der neuen lync Server 2013-Bereitstellung koexistiert, ist die Unterstützung für das Routing für gemischte Versionen begrenzt.</span><span class="sxs-lookup"><span data-stu-id="539e6-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="539e6-128">Ausführliche Informationen finden Sie in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="539e6-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="539e6-129">Sie müssen getrennte und unterschiedliche Computer mit Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für Ihre lync Server 2013-Datenbankinstanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="539e6-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="539e6-130">Sie können nicht dieselbe Instanz von SQL Server für einen lync Server 2013-Front-End-Pool verwenden, den Sie für einen lync Server 2010-oder Office Communications Server 2007 R2-Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="539e6-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="539e6-131">Wenn Sie lync Server 2013 im Topologie-Generator für eine Bereitstellung definieren und konfigurieren, die bereits lync Server 2010 oder Office Communications Server 2007 R2 bereitgestellt hat, können Sie mit dem Topology Builder keine Instanz eines lync Server 2013 definieren, die bereits in Verwendung ist die Topologie.</span><span class="sxs-lookup"><span data-stu-id="539e6-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="539e6-132">Der Topologie-Generator zeigt die folgende Meldung an, um Sie über dieses Problem zu informieren: \["der SQL Server\] -FQDN des Servers enthält bereits eine SQL-Instanz-Hostfunktion ' Benutzerspeicher '."</span><span class="sxs-lookup"><span data-stu-id="539e6-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="539e6-133">Wenn Sie Serverrollen bereitstellen möchten, die für Ihre lync Server 2013-Bereitstellung neu sind, sollten Sie zunächst die vorhandene Bereitstellung wie in der Migrationsdokumentation und der Bereitstellungsdokumentation beschrieben aktualisieren und dann die neuen Serverrollen wie in beschrieben bereitstellen. die Dokumentation zur Planungsdokumentation und zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="539e6-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="539e6-134">Wenn Sie eine frühere Version des Gruppen-Chats migrieren, migrieren Sie Sie zuletzt nach Abschluss des Prozesses für die Migration aller anderen Komponenten von lync Server 2010 oder Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="539e6-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="539e6-135">Spezifische Anforderungen an die Koexistenz und weitere Details zur Koexistenz und Migration von lync Server 2010 oder Office Communications Server 2007 R2 und lync Server 2013-Komponenten finden Sie unter [Migration von lync Server 2010 zu lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) und [ Migration von Office Communications Server 2007 R2 zu lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in der Migrationsdokumentation</span><span class="sxs-lookup"><span data-stu-id="539e6-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="539e6-136">Details zur Unterstützung von gemischten Versionen für Clients finden Sie unter [Unterstützte Clients aus vorherigen Bereitstellungen in lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="539e6-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

