---
title: Unterstützung von lync Server 2013 Datenbanksoftware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f7290a6d4e80c522d29c886b49723cca51d19e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516502"
---
# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="3814f-102">Unterstützung der Datenbanksoftware in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3814f-102">Database software support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3814f-103">_**Letztes Änderungsstand des Themas:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="3814f-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="3814f-104">Lync Server 2013 unterstützt die folgenden Datenbankverwaltungssysteme:</span><span class="sxs-lookup"><span data-stu-id="3814f-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="3814f-105">**Back-End-Datenbank eines Front-End-Pools, Archivierungsdatenbank, Überwachungsdatenbank, Datenbank für beständigen Chat und Konformitätsdatenbank für beständigen Chat**</span><span class="sxs-lookup"><span data-stu-id="3814f-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="3814f-p101">Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="3814f-p102">Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-p102">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="3814f-p103">Microsoft SQL Server 2012 Enterprise (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="3814f-p104">Microsoft SQL Server 2012 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="3814f-114">**Standard Edition-Server Datenbank und Front-End-Server Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="3814f-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="3814f-115">Microsoft SQL Server 2012 Express (64-Bit-Edition).</span><span class="sxs-lookup"><span data-stu-id="3814f-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="3814f-116">Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="3814f-117">Wir unterstützen das Patchen und Upgrade von Microsoft SQL Server auf Front-End-Servern und Standard Edition-Servern.</span><span class="sxs-lookup"><span data-stu-id="3814f-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="3814f-118">Wenn Sie allerdings ein Upgrade oder Patch auf Front-End-Servern vornehmen, müssen Sie die Quorum Anforderungen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3814f-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="3814f-119">Weitere Informationen finden Sie unter [aktualisieren oder Aktualisieren von Front-End-Servern in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) und [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="3814f-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3814f-120">Microsoft SQL Server 2012 Express (64-Bit Edition) wird automatisch von lync Server 2013 auf jedem Standard Edition-Server und jedem Front-End-Server Server installiert.</span><span class="sxs-lookup"><span data-stu-id="3814f-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="3814f-121">Die 32-Bit-Version von SQL Server wird von lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3814f-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="3814f-122">Sie müssen die 64-Bit-Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="3814f-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="3814f-123">SQL Server-webEdition und SQL Server Workgroup Edition werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3814f-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="3814f-124">Sie können Sie nicht mit lync Server 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="3814f-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="3814f-125">Lync Server 2013 unterstützt die systemeigene Datenbankspiegelung.</span><span class="sxs-lookup"><span data-stu-id="3814f-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="3814f-126">Um die Monitoring Server-Rolle verwenden zu können, sollten Sie SQL Server Reporting Services installieren.</span><span class="sxs-lookup"><span data-stu-id="3814f-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3814f-127">In einem Front-End-Pool kann es sich bei der Back-End-Datenbank um einen einzelnen SQL Server Computer handeln.</span><span class="sxs-lookup"><span data-stu-id="3814f-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3814f-128">Wenn Sie lync Server Datenbanken mit anderen Datenbanken collocate, wird dringend empfohlen, alle Faktoren zu bewerten, die sich auf die Verfügbarkeit und Leistung auswirken können, sowie sicherzustellen, dass der verbleibende Knoten bei einem Ausfall des Knotens die Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3814f-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="3814f-129">Zum Überprüfen der Failoverfunktionen wird empfohlen, alle Failover-Szenarien zu testen.</span><span class="sxs-lookup"><span data-stu-id="3814f-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="3814f-130">Verwenden von SQL-Spiegelung und SQL-Clustering</span><span class="sxs-lookup"><span data-stu-id="3814f-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="3814f-131">Lync Server 2013 unterstützt die Verwendung von SQL-Spiegelung oder SQL-Clustering für jede lync Server Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3814f-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="3814f-132">Sie können die SQL-Spiegelung ganz einfach mit dem Topologie-Generator-Tool in lync Server 2013 einrichten.</span><span class="sxs-lookup"><span data-stu-id="3814f-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="3814f-133">Für SQL-Failoverclustering müssen Sie SQL Server für das Setup verwenden.</span><span class="sxs-lookup"><span data-stu-id="3814f-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="3814f-134">Lync Server 2013 unterstützt sowohl SQL-Spiegelungs-als auch SQL-Clustering-Topologien für alle Bereitstellungen, einschließlich Greenfield-Bereitstellungen und Organisationen, die von früheren Versionen von lync Server aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="3814f-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="3814f-135">Die Unterstützung für SQL-Clustering ist für eine aktive/passive Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3814f-135">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="3814f-136">Aus Leistungsgründen sollte der passive Knoten nicht von einer anderen SQL-Instanz gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3814f-136">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="3814f-137">Die folgende Unterstützung ist enthalten:</span><span class="sxs-lookup"><span data-stu-id="3814f-137">The following support is included:</span></span>

  - <span data-ttu-id="3814f-138">Failover-Clusterunterstützung mit zwei Knoten für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3814f-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="3814f-139">Microsoft SQL Server 2012 Standard (64-Bit-Version).</span><span class="sxs-lookup"><span data-stu-id="3814f-139">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="3814f-140">Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-140">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="3814f-141">Microsoft SQL Server 2008 R2 Standard (64-Bit-Version).</span><span class="sxs-lookup"><span data-stu-id="3814f-141">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="3814f-142">Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-142">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="3814f-143">Failover-Clusterunterstützung für bis zu sechzehn Knoten für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3814f-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="3814f-144">Microsoft SQL Server 2012 Enterprise (64-Bit-Version).</span><span class="sxs-lookup"><span data-stu-id="3814f-144">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="3814f-145">Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-145">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="3814f-146">Microsoft SQL Server 2008 R2 Enterprise-Datenbanksoftware (64-Bit-Version).</span><span class="sxs-lookup"><span data-stu-id="3814f-146">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="3814f-147">Darüber hinaus wird das neueste Service Pack empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3814f-147">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="3814f-148">Weitere Informationen zur SQL-Spiegelung finden Sie unter [Back End Server High Availability in lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="3814f-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="3814f-149">Ausführliche Informationen zum Bereitstellen von SQL-Clustering finden Sie unter [configure SQL Server Clustering for lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="3814f-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="3814f-150">Weitere Informationen und bewährte Methoden für die Failover-Clusterunterstützung in SQL Server 2012 finden Sie unter <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="3814f-150">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="3814f-151">Informationen zur Failover-Clusterunterstützung in SQL Server 2008 finden Sie unter <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="3814f-151">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

