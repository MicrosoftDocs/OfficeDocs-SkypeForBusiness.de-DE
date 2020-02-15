---
title: Lync Server 2013 Kapazitätsplanung mithilfe der Benutzermodelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab2b7026ca49f8e12a5f8b67aa0780996feaebe1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="e1745-102">Kapazitätsplanung für lync Server 2013 mithilfe der Benutzermodelle</span><span class="sxs-lookup"><span data-stu-id="e1745-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1745-103">_**Letztes Änderungsstand des Themas:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="e1745-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="e1745-104">Dieser Abschnitt enthält Anleitungen dazu, wie viele Server Sie an einem Standort für die Anzahl der Benutzer an diesem Standort benötigen, entsprechend der in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)beschriebenen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e1745-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="e1745-105">Getestete Hardware Plattform</span><span class="sxs-lookup"><span data-stu-id="e1745-105">Tested Hardware Platform</span></span>

<span data-ttu-id="e1745-106">Alle Leistungsergebnisse und Bereitstellungsempfehlungen in diesem Abschnitt basieren auf Leistungstests auf Servern, die die in der folgenden Tabelle beschriebene Hardware ausführen.</span><span class="sxs-lookup"><span data-stu-id="e1745-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="e1745-107">Es wird empfohlen, dass Sie ähnliche Hardware verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1745-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="e1745-108">Wenn Sie weniger leistungsfähige Hardware verwenden, können Funktionsprobleme oder eine schlechte Leistung auftreten.</span><span class="sxs-lookup"><span data-stu-id="e1745-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="e1745-109">Beachten Sie, dass diese Hardwareempfehlungen höher als die der früheren Versionen von lync Server sind.</span><span class="sxs-lookup"><span data-stu-id="e1745-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="e1745-110">In Leistungstests verwendete Hardware</span><span class="sxs-lookup"><span data-stu-id="e1745-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1745-111">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="e1745-111">Hardware component</span></span></th>
<th><span data-ttu-id="e1745-112">Empfohlen</span><span class="sxs-lookup"><span data-stu-id="e1745-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1745-113">CPU</span><span class="sxs-lookup"><span data-stu-id="e1745-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="e1745-114">64-Bit Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher</span><span class="sxs-lookup"><span data-stu-id="e1745-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="e1745-115">Intel Itanium-Prozessoren werden für lync Server-Server Rollen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1745-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-116">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="e1745-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="e1745-117">32 Gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="e1745-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1745-118">Datenträger</span><span class="sxs-lookup"><span data-stu-id="e1745-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e1745-119">8 oder mehr 10.000-RPM-Festplatten mit mindestens 72 GB freiem Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="e1745-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="e1745-120">Zwei der Datenträger sollten RAID 1 verwenden, und sechs sollten RAID 10 verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1745-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="e1745-121">-Oder</span><span class="sxs-lookup"><span data-stu-id="e1745-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="e1745-122">Solid State Drives (SSDs), die ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 10.000-rpm bieten.</span><span class="sxs-lookup"><span data-stu-id="e1745-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-123">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="e1745-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e1745-124">1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist)</span><span class="sxs-lookup"><span data-stu-id="e1745-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="e1745-125">Zusammenfassung der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="e1745-125">Summary of Results</span></span>

<span data-ttu-id="e1745-126">Eine Übersicht über diese Empfehlungen finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e1745-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1745-127">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="e1745-127">Server role</span></span></th>
<th><span data-ttu-id="e1745-128">Maximale Anzahl von unterstützten Benutzern</span><span class="sxs-lookup"><span data-stu-id="e1745-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1745-129">Front-End-Pool mit zwölf Front-End-Servern und einem Back-End-Server oder einem gespiegelten Paar von Back-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="e1745-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="e1745-130">80.000 eindeutige Benutzer, die gleichzeitig angemeldet sind, plus 50% mehrere Points of Presence (mpop), die nicht-Mobile Instanzen darstellen, plus 40% der für die Mobilität aktivierten Benutzer für insgesamt 152.000 Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="e1745-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-131">A/V-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="e1745-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="e1745-132">Die A/V-Konferenzdienst, die von einem Front-End-Pool bereitgestellt werden, unterstützen die Konferenzen des Pools, vorausgesetzt eine maximale Konferenzgröße von 250 Benutzern und nur eine solche große Konferenz, die gleichzeitig gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e1745-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e1745-133">Darüber hinaus können Sie große Konferenzen zwischen 250 und 1000 Benutzern unterstützen, indem Sie einen separaten Front-End-Pool mit zwei Front-End-Servern bereitstellen, um die großen Konferenzen zu hosten.</span><span class="sxs-lookup"><span data-stu-id="e1745-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="e1745-134">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-supporting-large-meetings.md">unterstützen großer Besprechungen mit lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e1745-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1745-135">Ein Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e1745-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="e1745-136">12.000 gleichzeitige Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="e1745-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-137">Ein Director</span><span class="sxs-lookup"><span data-stu-id="e1745-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="e1745-138">12.000 gleichzeitige Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="e1745-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1745-139">Überwachen und Archivieren</span><span class="sxs-lookup"><span data-stu-id="e1745-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="e1745-140">In lync Server 2013 werden die Front-End-Dienste für die Überwachung und Archivierung nun auf jeder Front-End-Server statt auf separaten Server Rollen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1745-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="e1745-141">Für die Überwachung und Archivierung sind jeweils weiterhin eigene Datenbankspeicher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1745-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="e1745-142">Wenn Sie auch Exchange 2013 ausführen, können Sie Ihre Archivierungsdaten in Exchange und nicht in einer dedizierten SQL-Datenbank speichern.</span><span class="sxs-lookup"><span data-stu-id="e1745-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-143">Ein Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="e1745-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e1745-144">Vermittlungsserver zusammen mit Front-End-Server wird auf allen Front-End-Server in einem Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e1745-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="e1745-145">Informationen zur eigenständigen Vermittlungsserver finden Sie im Abschnitt "Vermittlungsserver" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="e1745-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1745-146">Ein Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="e1745-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="e1745-147">Wenn Sie Standard Edition-Server zum Hosten von Benutzern verwenden, wird dringend empfohlen, dass Sie immer zwei Server verwenden, gepaart mit den Empfehlungen <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">für die Planung der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e1745-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="e1745-148">Jeder Server im Paar kann bis zu 2.500 Benutzer hosten, und wenn ein Server ausfällt, kann der verbleibende Server 5.000-Benutzer in einem Failover-Szenario unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e1745-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="e1745-149">Wenn Ihre Bereitstellung eine erhebliche Menge an Audio-oder Videodatenverkehr umfasst, leidet die Serverleistung möglicherweise bei mehr als 2.500 Benutzern pro Server.</span><span class="sxs-lookup"><span data-stu-id="e1745-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="e1745-150">In diesem Fall sollten Sie in Betracht ziehen, weitere Standard Edition-Server hinzuzufügen oder zu lync Server Enterprise Edition zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="e1745-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="e1745-151">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="e1745-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1745-152">Gestreckte Pools werden für diese Serverrolle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1745-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e1745-153">In einem Front-End-Pool sollten Sie eine Front-End-Server für alle 6.660-Benutzer haben, die im Pool verwaltet werden, vorausgesetzt, dass das Hyper-Threading auf allen Servern im Pool aktiviert ist und dass die Server Hardware die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="e1745-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="e1745-154">Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000, vorausgesetzt, dass Hyper-Threading auf allen Servern im Pool aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e1745-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="e1745-155">Wenn Sie mehr als 80.000 Benutzer an einem Standort haben, können Sie mehr als einen Front-End-Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e1745-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="e1745-156">Wenn Sie die Anzahl von Benutzern in einem Front-End-Pool berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e1745-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="e1745-157">Wenn ein aktiver Server nicht mehr verfügbar ist, werden seine Verbindungen automatisch an die anderen Server innerhalb des Pools übertragen.</span><span class="sxs-lookup"><span data-stu-id="e1745-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="e1745-158">Wenn beispielsweise 30.000-Benutzer und fünf Front-End-Server vorhanden sind, müssen die Verbindungen von 6000-Benutzern auf die anderen vier Server übertragen werden, wenn ein Server nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e1745-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="e1745-159">Die verbleibenden vier Server verfügen jeweils über 7500 Benutzer, was eine höhere Anzahl als empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e1745-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="e1745-160">Wenn Sie stattdessen mit sechs Front-End-Servern für ihre 30.000-Benutzer begonnen und anschließend eine nicht verfügbar waren, werden insgesamt 5000-Benutzer auf die restlichen fünf Server verschoben.</span><span class="sxs-lookup"><span data-stu-id="e1745-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="e1745-161">Diese fünf Server werden alle Host 6000-Benutzer, die im empfohlenen Bereich ist.</span><span class="sxs-lookup"><span data-stu-id="e1745-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="e1745-162">Die maximale Anzahl von Benutzern in einem Front-End-Pool beträgt 80.000.</span><span class="sxs-lookup"><span data-stu-id="e1745-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="e1745-163">Die maximale Anzahl der Front-End-Server in einem Pool beträgt 12.</span><span class="sxs-lookup"><span data-stu-id="e1745-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="e1745-164">Für eine Front-End-Pool mit 80.000-Benutzern genügen zwölf Front-End-Server für die Leistung in typischen Bereitstellungen, die den [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e1745-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="e1745-165">Für Bereitstellungen zur Unterstützung des Notfall Wiederherstellungs Failovers wird davon ausgegangen, dass maximal 40.000 Benutzer in zwei gekoppelten Front-End-Pools gehostet werden können, in denen jeder Pool über genügend Front-End-Server verfügt, um die Benutzer in beiden Pools unterzubringen, wenn ein Pool fehlerhaft sein muss. auf den anderen.</span><span class="sxs-lookup"><span data-stu-id="e1745-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="e1745-166">Die Anzahl der Benutzer, die von einer bestimmten Front-End-Pool mit guter Leistung unterstützt werden, kann aus den folgenden Gründen von diesen Zahlen abweichen:</span><span class="sxs-lookup"><span data-stu-id="e1745-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="e1745-167">Die Hardware für Ihre Front-End-Server entspricht nicht den Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="e1745-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="e1745-168">Die Nutzung in Ihrer Organisation unterscheidet sich erheblich von den Benutzermodellen (z. B. deutlich mehr Konferenzdatenverkehr).</span><span class="sxs-lookup"><span data-stu-id="e1745-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e1745-169">In lync Server 2013 werden die Anwesenheits Datenbanken jetzt auf Front-End-Servern gehostet, im Gegensatz zu lync Server 2010, in denen Sie auf dem Back-End-Server gehostet wurden.</span><span class="sxs-lookup"><span data-stu-id="e1745-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="e1745-170">Dies bedeutet, dass die Datenträgerleistung und-Kapazität Ihrer Front-End-Server nicht von den Empfehlungen, die weiter oben in diesem Abschnitt und in <A href="lync-server-2013-server-hardware-platforms.md">Server Hardwareplattformen für lync Server 2013</A>aufgeführt sind, beeinträchtigt werden sollte, unabhängig von der Anzahl der Benutzer, die von ihren Front-End-Servern gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="e1745-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="e1745-171">In der folgenden Tabelle ist die durchschnittliche Bandbreite für Sofortnachrichten und Anwesenheitsinformationen anhand des Benutzermodells dargestellt, wie in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="e1745-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1745-172">Durchschnittliche Bandbreite pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="e1745-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="e1745-173">Bandbreitenanforderungen pro Front-End-Server mit 6.660 Benutzern</span><span class="sxs-lookup"><span data-stu-id="e1745-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1745-174">1,3 KBit/s</span><span class="sxs-lookup"><span data-stu-id="e1745-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="e1745-175">13 MBit/s</span><span class="sxs-lookup"><span data-stu-id="e1745-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e1745-176">Um die Medien Leistung der co-located A/V-Konferenz-und Vermittlungsserver Funktionalität auf Ihren Front-End-Servern zu verbessern, sollten Sie die Receive-Side Scaling (RSS) auf den Netzwerkadaptern auf Ihren Front-End-Servern aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1745-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="e1745-177">Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e1745-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="e1745-178">Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server 2008" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span><span class="sxs-lookup"><span data-stu-id="e1745-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="e1745-179">Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="e1745-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="e1745-180">Maximale Anzahl von Benutzern für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="e1745-180">Conferencing Maximums</span></span>

<span data-ttu-id="e1745-181">Bei einem Benutzermodell, bei dem 5 % der Benutzer in einem Pool gleichzeitig an einer Konferenz teilnehmen können, können in einem Pool mit 80.000 Benutzern gleichzeitig ca. 4.000 Benutzer an einer Konferenz teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="e1745-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="e1745-182">Bei diesen Konferenzen wird davon ausgegangen, dass eine Kombination aus Mediendatenverkehr (z.B. nur Sofortnachrichten, Sofortnachrichten mit Audio, Audio/Video-Konferenzen) verarbeitet werden muss und eine unterschiedliche Anzahl von Benutzern teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="e1745-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="e1745-183">Es gibt keine harte Grenze für die tatsächliche Anzahl von zulässigen Konferenzen, die tatsächliche Leistung ist durch die tatsächliche Nutzung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e1745-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="e1745-184">Wenn in Ihrer Organisation beispielsweise wesentlich mehr Konferenzen im gemischten Modus verwendet werden, als im Benutzermodell angenommen werden, müssen Sie u. U. mehr Front-End-Server oder A/V-Konferenzserver bereitstellen, als in diesem Dokument empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e1745-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="e1745-185">Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e1745-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="e1745-186">Die maximale unterstützte Konferenzgröße, die von einer regulären lync Server 2013 gehostet wird Front-End-Pool die auch Benutzer hostet, ist 250 Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="e1745-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="e1745-187">Während eine 250-User-Konferenz stattfindet, unterstützt der Pool weiterhin auch andere Konferenzen, sodass sich insgesamt 5% der Pool Benutzer in gleichzeitigen Konferenzen befinden.</span><span class="sxs-lookup"><span data-stu-id="e1745-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="e1745-188">In einem Pool mit zwölf Front-End-Servern und 80.000-Benutzern unterstützt lync Server beispielsweise 3.750 andere Benutzer, die an kleineren Konferenzen teilnehmen, während die 250-Benutzer Konferenz stattfindet.</span><span class="sxs-lookup"><span data-stu-id="e1745-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="e1745-189">Unabhängig von der Anzahl der Benutzer, die im Front-End-Pool oder Standard Edition-Server verwaltet werden, unterstützt lync Server mindestens 125 andere Benutzer, die an kleineren Konferenzen in demselben Pool oder Server teilnehmen, der eine Konferenz mit 250 Benutzern hostet.</span><span class="sxs-lookup"><span data-stu-id="e1745-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="e1745-190">Um Konferenzen mit Benutzern mit 250 und 1000 zu ermöglichen, können Sie einen separaten Front-End-Pool einrichten, um diese Konferenzen zu hosten.</span><span class="sxs-lookup"><span data-stu-id="e1745-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="e1745-191">In diesem Front-End-Pool werden keine Benutzer gehostet.</span><span class="sxs-lookup"><span data-stu-id="e1745-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="e1745-192">Ausführliche Informationen finden Sie unter [unterstützen großer Besprechungen mit lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="e1745-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="e1745-193">Wenn in Ihrer Organisation viel mehr Konferenzen im gemischten Modus stattfinden, die im Benutzermodell angenommen werden, müssen Sie möglicherweise mehr Front-End-Server bereitstellen als die Empfehlungen in diesem Dokument (bis zu einem Grenzwert von 12 Fes).</span><span class="sxs-lookup"><span data-stu-id="e1745-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="e1745-194">Ausführliche Informationen zu den Annahmen im Benutzermodell finden Sie unter [User Models in lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e1745-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="e1745-195">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e1745-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1745-196">Gestreckte Pools werden für diese Serverrolle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1745-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e1745-197">Sie sollten eine Edgeserver für alle 12.000-Remotebenutzer bereitstellen, die gleichzeitig auf eine Website zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e1745-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="e1745-198">Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Edgeservern empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e1745-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="e1745-199">Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="e1745-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e1745-200">Wenn Sie die Anzahl von Benutzern für die Edgeserver berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e1745-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1745-201">Zum Verbessern der Leistung des A/V-Konferenzedgediensts auf Ihren Edgeservern sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter Ihrer Edgeserver aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1745-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="e1745-202">Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e1745-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="e1745-203">Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server 2008" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span><span class="sxs-lookup"><span data-stu-id="e1745-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="e1745-204">Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="e1745-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="e1745-205">Director</span><span class="sxs-lookup"><span data-stu-id="e1745-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1745-206">Gestreckte Pools werden für diese Serverrolle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1745-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e1745-207">Wenn Sie die Director-Serverrolle bereitstellen, wird empfohlen, dass Sie einen Director für jeden 12.000-Remotebenutzer bereitstellen, der gleichzeitig auf eine Website zugreift.</span><span class="sxs-lookup"><span data-stu-id="e1745-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="e1745-208">Um hohe Verfügbarkeit zu bieten, wird die Bereitstellung von mindestens zwei Directors empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e1745-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="e1745-209">Bei diesen Empfehlungen wird davon ausgegangen, dass die Hardware für Ihre Edgeserver die Empfehlungen in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="e1745-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e1745-210">Wenn Sie die Anzahl von Benutzern für die Director-Server berechnen, berücksichtigen Sie auch die Benutzer in Survivable Branch Appliances und auf Survivable Branch Servern in Zweigstellen, die diesem Front-End-Pool an diesem Standort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e1745-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="e1745-211">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="e1745-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1745-212">Gestreckte Pools werden für diese Serverrolle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1745-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e1745-213">Wenn Sie Vermittlungsserver mit Front-End-Server collocate, wird Vermittlungsserver auf jeder Front-End-Server im Pool ausgeführt und sollte genügend Kapazität für die Benutzer im Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e1745-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="e1745-214">Wenn Sie einen eigenständigen Vermittlungsserver Pool bereitstellen, hängt die Anzahl der bereitzustellenden Vermittlungsserver von vielen Faktoren ab, einschließlich der für Vermittlungsserver verwendeten Hardware, der Anzahl der VoIP-Benutzer, der Anzahl der Gateway-Peers, die die einzelnen Vermittlungsserver Pools steuert den Datenverkehr über diese Gateways und den Prozentsatz der Anrufe mit Medien, die die Vermittlungsserver umgehen.</span><span class="sxs-lookup"><span data-stu-id="e1745-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="e1745-215">Die folgenden Tabellen bieten eine Richtlinie für die Anzahl gleichzeitiger Anrufe, die ein Vermittlungsserver verarbeiten kann, vorausgesetzt, dass die Hardware für die Vermittlungsserver die Anforderungen unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) erfüllt und Hyper-Threading aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e1745-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="e1745-216">Ausführliche Informationen zur Vermittlungsserver Skalierbarkeit finden Sie unter [Estimating Voice usage and Traffic for lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment Guidelines for Vermittlungsserver in lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="e1745-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="e1745-217">Alle folgenden Tabellen gehen davon aus, dass die Verwendung in [Benutzermodellen in lync Server 2013](lync-server-2013-user-models.md)zusammengefasst wird.</span><span class="sxs-lookup"><span data-stu-id="e1745-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="e1745-218">Eigenständige Vermittlungsserver Kapazität: 70% interne Benutzer, 30% externe Benutzer mit nicht-Bypass-Anrufkapazität (Medien Transkodierung durchgeführt von Vermittlungsserver)</span><span class="sxs-lookup"><span data-stu-id="e1745-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1745-219">Serverhardware</span><span class="sxs-lookup"><span data-stu-id="e1745-219">Server hardware</span></span></th>
<th><span data-ttu-id="e1745-220">Maximale Anzahl von Anrufen</span><span class="sxs-lookup"><span data-stu-id="e1745-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="e1745-221">Maximale Anzahl von T1-Leitungen</span><span class="sxs-lookup"><span data-stu-id="e1745-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="e1745-222">Maximale Anzahl von E1-Leitungen</span><span class="sxs-lookup"><span data-stu-id="e1745-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1745-223">Dualprozessor, Hex-Kern, 2,26 GHz-Hyper-Threaded-CPU <strong>mit deaktiviertem Hyper-Threading</strong>, mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.</span><span class="sxs-lookup"><span data-stu-id="e1745-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="e1745-224">1100</span><span class="sxs-lookup"><span data-stu-id="e1745-224">1100</span></span></p></td>
<td><p><span data-ttu-id="e1745-225">46</span><span class="sxs-lookup"><span data-stu-id="e1745-225">46</span></span></p></td>
<td><p><span data-ttu-id="e1745-226">35</span><span class="sxs-lookup"><span data-stu-id="e1745-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-227">Dualprozessor, Hex-Kern, 2,26 GHz Hyper-Threaded CPU, mit 32 GB Arbeitsspeicher und einer Netzwerkadapterkarte mit zwei Ports.</span><span class="sxs-lookup"><span data-stu-id="e1745-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="e1745-228">1500</span><span class="sxs-lookup"><span data-stu-id="e1745-228">1500</span></span></p></td>
<td><p><span data-ttu-id="e1745-229">63</span><span class="sxs-lookup"><span data-stu-id="e1745-229">63</span></span></p></td>
<td><p><span data-ttu-id="e1745-230">47</span><span class="sxs-lookup"><span data-stu-id="e1745-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e1745-231">Für die Leistungstests wurden Server mit 32 GB Arbeitsspeicher verwendet. Für einen eigenständigen Vermittlungsserver werden jedoch auch Server mit 16 GB Arbeitsspeicher unterstützt, was für die in dieser Tabelle dargestellte Leistung auch ausreicht.</span><span class="sxs-lookup"><span data-stu-id="e1745-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="e1745-232">Vermittlungsserver Kapazität (Vermittlungsserver zusammen mit Front-End-Server) 70% interne Benutzer, 30% externe Benutzer, nicht-Bypass-Anrufkapazität (Medienverarbeitung durch Vermittlungsserver durchgeführt)</span><span class="sxs-lookup"><span data-stu-id="e1745-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1745-233">Serverhardware</span><span class="sxs-lookup"><span data-stu-id="e1745-233">Server hardware</span></span></th>
<th><span data-ttu-id="e1745-234">Maximale Anzahl von Anrufen</span><span class="sxs-lookup"><span data-stu-id="e1745-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1745-235">Dual Prozessor, Hex-Kern, 2,26 GHz Hyper-Threaded CPU, mit 32 GB Arbeitsspeicher und 2 1GB Netzwerkadapterkarten.</span><span class="sxs-lookup"><span data-stu-id="e1745-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="e1745-236">150</span><span class="sxs-lookup"><span data-stu-id="e1745-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e1745-237">Diese Zahl ist viel kleiner als die Zahlen für die eigenständige Vermittlungsserver, da die Front-End-Server andere Features und Funktionen für die 6600-Benutzer, die auf Ihr verwaltet werden, sowie die für Sprachanrufe erforderliche Transcodierung verarbeiten muss.</span><span class="sxs-lookup"><span data-stu-id="e1745-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e1745-238">Um die Leistung des Vermittlungsserver zu verbessern, sollten Sie die Receive-Side Scaling (RSS) auf den Netzwerkadaptern auf Ihren Vermittlungsservern aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1745-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="e1745-239">Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e1745-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="e1745-240">Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server 2008" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span><span class="sxs-lookup"><span data-stu-id="e1745-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="e1745-241">Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.</span><span class="sxs-lookup"><span data-stu-id="e1745-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="e1745-242">Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="e1745-242">Back End Server</span></span>

<span data-ttu-id="e1745-243">In lync Server 2013 befinden sich die Anwesenheits Datenbanken auf den Front-End-Servern statt auf dem Back-End-Server.</span><span class="sxs-lookup"><span data-stu-id="e1745-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="e1745-244">Dies hat zu einer wesentlich einfacheren Anforderung für jeden Back-End-Server in lync Server 2013 geführt, der der Hardwareanforderung für die Front-End-Server entspricht.</span><span class="sxs-lookup"><span data-stu-id="e1745-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="e1745-245">Kontrastiert dies mit lync Server 2010, bei dem der Back-End-Server ein weitaus höherwertiger Server mit 25 Datenträgern sein muss.</span><span class="sxs-lookup"><span data-stu-id="e1745-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="e1745-246">Die Arbeitsauslastung von Back-End-Servern ist jedoch immer noch so, dass Sie die Hardwareempfehlungen, die weiter oben in diesem Abschnitt und in [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md)aufgeführt sind, nicht versäumen sollten.</span><span class="sxs-lookup"><span data-stu-id="e1745-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e1745-247">Um eine hohe Verfügbarkeit des Back-End-Servers bereitzustellen, empfehlen wir die Bereitstellung der Server Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="e1745-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="e1745-248">Weitere Informationen finden Sie unter [Back End Server High Availability in lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="e1745-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="e1745-249">Überwachen und Archivieren</span><span class="sxs-lookup"><span data-stu-id="e1745-249">Monitoring and Archiving</span></span>

<span data-ttu-id="e1745-250">Wenn Sie in lync Server 2013 die Überwachung oder Archivierung bereitstellen, wird die Front-End-Funktionalität dieser Dienste auf den Front-End-Servern statt auf separaten Server Rollen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1745-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="e1745-251">Für die Überwachung und Archivierung wird jeweils weiterhin ein eigener Datenbankspeicher verwendet, getrennt vom Back-End-Speicher.</span><span class="sxs-lookup"><span data-stu-id="e1745-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="e1745-252">Alternativ können Sie, wenn Sie Exchange 2013 bereitgestellt haben, Sofortnachrichten-Archivierungsdaten in Exchange anstatt in einem dedizierten SQL-Speicher speichern.</span><span class="sxs-lookup"><span data-stu-id="e1745-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="e1745-253">Die folgende Tabelle gibt an, wie viel Datenbankspeicher pro Benutzer pro Tag für die Überwachung und Archivierung von Daten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e1745-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="e1745-254"><strong>CDR (Überwachung)</strong></span><span class="sxs-lookup"><span data-stu-id="e1745-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="e1745-255"><strong>QoE (Überwachung)</strong></span><span class="sxs-lookup"><span data-stu-id="e1745-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="e1745-256"><strong>Archivierung</strong></span><span class="sxs-lookup"><span data-stu-id="e1745-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-257">Erforderlicher Festplattenspeicher pro Benutzer und Tag</span><span class="sxs-lookup"><span data-stu-id="e1745-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="e1745-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="e1745-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="e1745-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="e1745-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="e1745-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="e1745-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1745-261">Microsoft hat die Hardware in der folgenden Tabelle für den Datenbankserver für die Überwachung und Archivierung während der Leistungstests verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1745-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="e1745-262">Bei den Tests wurden die Daten zweier Front-End-Pools gesammelt, von denen jedes 80.000-Benutzer umfasste.</span><span class="sxs-lookup"><span data-stu-id="e1745-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="e1745-263">Hardware, die zum Überwachen und Archivieren von Leistungstests verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e1745-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1745-264">Hardwarekomponente</span><span class="sxs-lookup"><span data-stu-id="e1745-264">Hardware component</span></span></th>
<th><span data-ttu-id="e1745-265">Empfohlen</span><span class="sxs-lookup"><span data-stu-id="e1745-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1745-266">CPU</span><span class="sxs-lookup"><span data-stu-id="e1745-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="e1745-267">64-Bit Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher</span><span class="sxs-lookup"><span data-stu-id="e1745-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-268">Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="e1745-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="e1745-269">48 Gigabyte (GB)</span><span class="sxs-lookup"><span data-stu-id="e1745-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1745-270">Datenträger</span><span class="sxs-lookup"><span data-stu-id="e1745-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="e1745-271">25 10.000-RPM-Festplatten mit 300 GB auf jedem Datenträger mit der folgenden Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e1745-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1745-272"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="e1745-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="e1745-273"><strong>RAID-Konfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e1745-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e1745-274"><strong>Anzahl der Datenträger</strong></span><span class="sxs-lookup"><span data-stu-id="e1745-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-275">CDR-, QoE-und Archivierungsdatenbank-Datendateien auf einem einzelnen Laufwerk</span><span class="sxs-lookup"><span data-stu-id="e1745-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="e1745-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="e1745-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="e1745-277">16 </span><span class="sxs-lookup"><span data-stu-id="e1745-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1745-278">KDS-Datenbankprotokolldatei</span><span class="sxs-lookup"><span data-stu-id="e1745-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="e1745-279">1 </span><span class="sxs-lookup"><span data-stu-id="e1745-279">1</span></span></p></td>
<td><p><span data-ttu-id="e1745-280">2 </span><span class="sxs-lookup"><span data-stu-id="e1745-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-281">QoE-Datenbankprotokolldatei</span><span class="sxs-lookup"><span data-stu-id="e1745-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="e1745-282">1 </span><span class="sxs-lookup"><span data-stu-id="e1745-282">1</span></span></p></td>
<td><p><span data-ttu-id="e1745-283">2 </span><span class="sxs-lookup"><span data-stu-id="e1745-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1745-284">Archivierungsdatenbank Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="e1745-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="e1745-285">1 </span><span class="sxs-lookup"><span data-stu-id="e1745-285">1</span></span></p></td>
<td><p><span data-ttu-id="e1745-286">2 </span><span class="sxs-lookup"><span data-stu-id="e1745-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1745-287">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="e1745-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e1745-288">1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist)</span><span class="sxs-lookup"><span data-stu-id="e1745-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e1745-289">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e1745-289">In This Section</span></span>

  - [<span data-ttu-id="e1745-290">Schätzen der VoIP-Nutzung und des Datenverkehrs für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1745-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="e1745-291">Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1745-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

