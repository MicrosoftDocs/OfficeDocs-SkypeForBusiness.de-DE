---
title: 'Lync Server 2013: Aktualisieren oder Aktualisieren der Front-End-Server'
description: 'Lync Server 2013: Aktualisieren oder Aktualisieren der Front-End-Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5340ca5549aeff51b275798572573b2c9f017644
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569921"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="ef1bd-103">Aktualisieren oder Aktualisieren der Front-End-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef1bd-103">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef1bd-104">_**Letztes Änderungsstand des Themas:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="ef1bd-104">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="ef1bd-105">Die Front-End-Server in einem Enterprise Edition-Pool werden in *Upgradedomänen* aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-105">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="ef1bd-106">Diese stellen Teilmengen von Front-End-Servern im Pool dar.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-106">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="ef1bd-107">Upgrade-Domänen werden automatisch vom Topologie-Generator erstellt.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-107">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="ef1bd-108">Wenn Sie Server aktualisieren, müssen Sie jeweils eine Upgrade-Domäne durchführen.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-108">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="ef1bd-109">Bringen Sie jeden Server in eine Upgrade-Domäne herunter, aktualisieren Sie ihn, und starten Sie ihn neu, bevor Sie zu einer anderen Upgrade-Domäne übergehen.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-109">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="ef1bd-110">Achten Sie darauf, nachzuverfolgen, welche Upgrade-Domänen und-Server Sie bisher aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-110">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="ef1bd-111">Verwenden Sie das folgende Flussdiagramm Diagramm, wenn Sie jeden Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-111">Use the following flowchart diagram when upgrading each server.</span></span>

![Upgraden oder Updaten von Front-End-Servern](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="ef1bd-113">So wenden Sie ein Upgrade auf die Front-End-Server in einem Pool an</span><span class="sxs-lookup"><span data-stu-id="ef1bd-113">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="ef1bd-114">Führen Sie auf einem Front-End-Server im Pool das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="ef1bd-114">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="ef1bd-115">**Get-cspoolupgradereadinessstate "**</span><span class="sxs-lookup"><span data-stu-id="ef1bd-115">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="ef1bd-116">Wenn der Wert von *poolupgradestatebereit* **ausgelastet**ist, warten Sie 10 Minuten, und versuchen Sie es dann erneut mit **Get-cspoolupgradereadinessstate "** .</span><span class="sxs-lookup"><span data-stu-id="ef1bd-116">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="ef1bd-117">Wenn Sie mindestens drei aufeinanderfolgende male **beschäftigt** sind, nachdem Sie 10 Minuten zwischen den einzelnen versuchen gewartet haben oder wenn ein Ergebnis von **InsufficientActiveFrontEnds** für poolupgradestatebereit angezeigt wird **,** liegt ein Problem mit dem Pool vor.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-117">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="ef1bd-118">Bildet dieser Pool ein Paar mit einem anderen Front-End-Pool in einer Notfallwiederherstellungstopologie, sollten Sie ein Failover für den Pool zum Sicherungspool ausführen und anschließend die Server in diesem Pool aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-118">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="ef1bd-119">Ausführliche Informationen finden Sie unter [failing over a Pool in lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ef1bd-119">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="ef1bd-120">Falls der Wert von *PoolUpgradeState\*\*\*Bereit*\* lautet, fahren Sie mit Schritt 2 fort.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-120">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="ef1bd-121">Das Cmdlet **Get-cspoolupgradereadinessstate "** gibt außerdem Informationen zu jeder Upgrade-Domäne im Pool und zu den Front-End-Servern in jeder Upgrade-Domäne zurück.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-121">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="ef1bd-122">Wenn der **ReadyforUpgrade** -Wert für die Upgrade-Domäne **true** ist, die den Server enthält, den Sie aktualisieren möchten, können Sie diese Server problemlos jetzt aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-122">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="ef1bd-123">Gehen Sie hierzu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ef1bd-123">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="ef1bd-124">Beenden Sie neue Verbindungen mit den Front-End-Servern, die Sie aktualisieren möchten, mithilfe des `Stop-CsWindowsService -Graceful -Verbose` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-124">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ef1bd-125">Wenn Sie diese Server Upgrades während einer geplanten Serverausfall Zeit durchführen, können Sie dieses Cmdlet wie folgt ohne den Parameter "-<STRONG>Graceful</STRONG>" ausführen: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-125">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="ef1bd-126">Dadurch werden Dienste sofort heruntergefahren, ohne darauf zu warten, dass alle vorhandenen Dienstanforderungen ausgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-126">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="ef1bd-127">Aktualisieren Sie die damit verknüpften Server mit der Upgrade-Domäne.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-127">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="ef1bd-128">Starten Sie die Server neu, und stellen Sie sicher, dass Sie neue Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-128">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="ef1bd-129">Wiederholen Sie die Schritte 1 und 2 für jede andere Upgrade-Domäne im Pool, bis alle Front-End-Server aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ef1bd-129">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

