---
title: 'Lync Server 2013: Aktualisieren oder Aktualisieren von Front-End-Servern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1680da68299881fe94244969d44fce1900532b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="4ca43-102">Upgrade or update Front End Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ca43-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ca43-103">_**Letztes Änderungsdatum des Themas:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="4ca43-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="4ca43-104">Die Front-End-Server in einem Enterprise Edition-Pool sind in *Upgrade-Domänen*unterteilt.</span><span class="sxs-lookup"><span data-stu-id="4ca43-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="4ca43-105">Hierbei handelt es sich um Teilmengen der Front-End-Server im Pool.</span><span class="sxs-lookup"><span data-stu-id="4ca43-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="4ca43-106">Upgrade-Domänen werden vom Topologie-Generator automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="4ca43-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="4ca43-107">Wenn Sie Server aktualisieren, müssen Sie eine Upgrade-Domäne gleichzeitig ausführen.</span><span class="sxs-lookup"><span data-stu-id="4ca43-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="4ca43-108">Führen Sie die einzelnen Server in einer Upgrade-Domäne herunter, aktualisieren Sie Sie, und starten Sie Sie dann neu, bevor Sie zu einer anderen Upgrade-Domäne wechseln.</span><span class="sxs-lookup"><span data-stu-id="4ca43-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="4ca43-109">Achten Sie darauf, nachzuverfolgen, welche Upgrade-Domänen und-Server Sie bisher aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="4ca43-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="4ca43-110">Verwenden Sie das folgende Flussdiagramm Diagramm, wenn Sie jeden Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ca43-110">Use the following flowchart diagram when upgrading each server.</span></span>

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Aktualisieren oder Aktualisieren von Front-End-Servern":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="4ca43-112">So führen Sie ein Upgrade für die Front-End-Server in einem Pool durch</span><span class="sxs-lookup"><span data-stu-id="4ca43-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="4ca43-113">Führen Sie auf einem Front-End-Server im Pool das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="4ca43-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="4ca43-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="4ca43-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="4ca43-115">Wenn der Wert von *PoolUpgradeState* **ausgelastet**ist, warten Sie 10 Minuten, und versuchen Sie dann erneut, **Get-CsPoolUpgradeReadinessState** .</span><span class="sxs-lookup"><span data-stu-id="4ca43-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="4ca43-116">Wenn Sie **beschäftigt** mindestens drei Mal hintereinander sehen, nachdem Sie 10 Minuten zwischen jedem Versuch gewartet haben, oder wenn Sie ein Ergebnis von **InsufficientActiveFrontEnds** für PoolUpgradeState sehen **,** liegt ein Problem mit dem Pool vor.</span><span class="sxs-lookup"><span data-stu-id="4ca43-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="4ca43-117">Wenn dieser Pool mit einem anderen Front-End-Pool in einer Disaster Recovery-Topologie gekoppelt ist, sollten Sie den Pool für den Sicherungspool nicht überschreiben und dann die Server in diesem Pool aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ca43-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="4ca43-118">Ausführliche Informationen finden Sie unter [Failover eines Pools in lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="4ca43-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="4ca43-119">Wenn der Wert von *PoolUpgradeState* **bereit**ist, fahren Sie mit Schritt 2 fort.</span><span class="sxs-lookup"><span data-stu-id="4ca43-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="4ca43-120">Das Cmdlet " **Get-CsPoolUpgradeReadinessState** " gibt auch Informationen zu jeder Upgrade-Domäne im Pool und zu den Front-End-Servern in jeder Upgrade-Domäne zurück.</span><span class="sxs-lookup"><span data-stu-id="4ca43-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="4ca43-121">Wenn der **ReadyforUpgrade** -Wert für die Upgrade-Domäne mit dem Server oder den Servern, die Sie aktualisieren möchten, **wahr** ist, können Sie diese Server jetzt problemlos aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ca43-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="4ca43-122">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="4ca43-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="4ca43-123">Beenden Sie neue Verbindungen mit den Front-End-Servern, die Sie aktualisieren möchten `Stop-CsWindowsService -Graceful -Verbose` , mithilfe des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4ca43-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4ca43-124">Wenn Sie diese Server Upgrades während einer geplanten Server Downtime durchführen, können Sie dieses Cmdlet ohne den "-<STRONG>Graceful</STRONG>"-Parameter wie folgt ausführen: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4ca43-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="4ca43-125">Dadurch werden die Dienste sofort beendet, ohne dass alle vorhandenen Dienstanforderungen ausgefüllt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4ca43-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="4ca43-126">Aktualisieren Sie die Server, die dieser Upgrade-Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4ca43-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="4ca43-127">Starten Sie die Server neu, und stellen Sie sicher, dass Sie neue Verbindungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="4ca43-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="4ca43-128">Wiederholen Sie die Schritte 1 und 2 für jede andere Upgrade-Domäne im Pool, bis alle Front-End-Server aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4ca43-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

