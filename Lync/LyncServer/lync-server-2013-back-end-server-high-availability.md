---
title: 'Lync Server 2013: hohe Verfügbarkeit des Back-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335f7680a98eb53414a8b438975d79327b515946
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="4dc9d-102">Hohe Verfügbarkeit von Back-End-Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dc9d-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc9d-103">_**Letztes Änderungsstand des Themas:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="4dc9d-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="4dc9d-104">Um eine hohe Verfügbarkeit für die Back-End-Server sicherzustellen, können Sie entweder synchrone SQL-Spiegelung oder SQL-Clustering verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="4dc9d-105">Die Verwendung einer dieser Lösungen ist optional, wird jedoch empfohlen, um die Geschäftskontinuität in Ihrer Organisation aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="4dc9d-106">Die asynchrone SQL-Spiegelung wird für die hohe Verfügbarkeit von Back-End-Servern in lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="4dc9d-107">In diesem Dokument steht, sofern nicht anders angegeben, SQL-Spiegelung für die synchrone SQL-Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="4dc9d-108">Sie können die SQL-Spiegelung ganz einfach mit dem Topologie-Generator einrichten.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="4dc9d-109">Für SQL-Failoverclustering müssen Sie SQL Server für das Setup verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="4dc9d-110">Wenn Sie entweder SQL-Spiegelung oder SQL-Clustering in einem Pool verwenden, der mit einem anderen Front-End-Pool für die Notfallwiederherstellung gekoppelt ist, sollten Sie dieselbe Back-End-Lösung für hohe Verfügbarkeit in beiden Pools verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="4dc9d-111">Sie sollten keinen Pool mit SQL-Spiegelung mit einem Pool mit SQL-Clustering koppeln.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="4dc9d-112">Wenn Sie die SQL-Spiegelung bereitstellen, werden alle lync Server-Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, wenn dieser sich in diesem Pool befindet, sowie der Reaktionsgruppenanwendung Datenbank und der Anwendung zum Parken von Anrufen Datenbank, wenn diese Anwendungen werden im Pool betrieben.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="4dc9d-p104">Bei der SQL-Spiegelung müssen Sie keinen gemeinsam genutzten Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="4dc9d-p105">Sie können die SQL-Spiegelung mit oder ohne einen Spiegelungszeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="4dc9d-p106">Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="4dc9d-122">Weitere Informationen zur Unterstützung von SQL-Clusterunterstützung finden Sie unter [Datenbanksoftware-Unterstützung in lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="4dc9d-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="4dc9d-123">Ausführliche Informationen zum Bereitstellen von SQL-Clustering finden Sie unter [configure SQL Server Clustering for lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="4dc9d-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="4dc9d-124">Wiederherstellungszeit für automatisches Back-End-Server Failover mit SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="4dc9d-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="4dc9d-125">Für das automatische Back-End-Failover mit SQL-Spiegelung beträgt das Entwicklungsziel für die Wiederherstellungszeit (RTO) 5 Minuten.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="4dc9d-126">Aufgrund der synchronen SQL-Spiegelung wird nicht von einem Datenverlust bei Ausfällen von Back-End-Servern ausgegangen, außen in seltenen Fällen, wenn sowohl der Front-End-Server als auch der Back-End-Server beim Verschieben von Daten zwischen diesen Servern gleichzeitig ausfällt.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="4dc9d-127">Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="4dc9d-128">Benutzerfreundlichkeit während des Back-End-Server Fehlers mit SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="4dc9d-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="4dc9d-129">Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="4dc9d-130">Wenn Sie die SQL-Spiegelung verwenden und einen Zeugen konfiguriert haben und der Prinzipal ausfällt, erfolgt das Failover des Back-End-Servers automatisch und schnell.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="4dc9d-131">Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="4dc9d-132">Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="4dc9d-133">Während dieser Zeit sind möglicherweise aktive Benutzer betroffen.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-133">During that time, active users may be affected.</span></span> <span data-ttu-id="4dc9d-134">Sie werden Ihre Sitzungen wie gewohnt für etwa 30 Minuten fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="4dc9d-135">Wenn das primäre Gerät noch nicht wiederhergestellt wurde oder ein Administrator nicht auf die Sicherung gescheitert ist, werden die Benutzer in den Ausfall Sicherheitsmodus umgeschaltet, was bedeutet, dass Sie keine Aufgaben ausführen können, die eine beständige Änderung am lync Server erfordern (beispielsweise das Hinzufügen eines Kontakts).</span><span class="sxs-lookup"><span data-stu-id="4dc9d-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="4dc9d-p111">Wenn Sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen, oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

