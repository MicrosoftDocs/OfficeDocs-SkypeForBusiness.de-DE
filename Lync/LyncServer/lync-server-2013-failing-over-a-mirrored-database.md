---
title: 'Lync Server 2013: Failover einer gespiegelten Datenbank'
description: 'Lync Server 2013: Fehler bei einer gespiegelten Datenbank.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7c401157c79762f674721ca717296c0fe502db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567691"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="86af5-103">Failover einer gespiegelten Datenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86af5-103">Failing over a mirrored database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86af5-104">_**Letztes Änderungsstand des Themas:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="86af5-104">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="86af5-105">Wenn Sie die Back-End-Datenbank so konfiguriert haben, dass die synchronisierte Spiegelung mit einem Zeugen verwendet wird, erfolgt das Failover automatisch.</span><span class="sxs-lookup"><span data-stu-id="86af5-105">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="86af5-106">Wenn Sie die synchronisierte Spiegelung ohne Zeugen konfiguriert haben, können Sie die folgenden Verfahren zum Failover und Failback der Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="86af5-106">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="86af5-107">Sie können diese Verfahren auch zum manuellen Failover und Failback Ihrer Datenbanken verwenden, selbst wenn Sie einen Zeugen konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="86af5-107">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="86af5-108">So führen Sie einen Failover für die Back-End-Datenbank aus</span><span class="sxs-lookup"><span data-stu-id="86af5-108">To fail over your back-end database</span></span>

1.  <span data-ttu-id="86af5-109">Stellen Sie vor dem Failover fest, welche Back-End-Datenbank der Prinzipal ist und welche die Spiegelung ist, indem Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="86af5-109">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="86af5-110">Wenn der zentrale Verwaltungsspeicher in diesem Pool gehostet wird, geben Sie das folgende Cmdlet ein, um zu bestimmen, welcher Prinzipal und welcher Spiegel für den zentralen Verwaltungsspeicher ist:</span><span class="sxs-lookup"><span data-stu-id="86af5-110">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="86af5-111">Ausführen des Failovers der Benutzerdatenbank:</span><span class="sxs-lookup"><span data-stu-id="86af5-111">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="86af5-112">Wenn der primäre Fehler aufgetreten ist und Sie einen Failover zur Spiegelung durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86af5-112">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="86af5-113">Wenn die Spiegelung fehlgeschlagen ist und Sie das primäre Failover durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86af5-113">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="86af5-114">Wenn der Pool den zentralen Verwaltungs Server hostet, führen Sie das Failover des zentralen Verwaltungsspeichers durch.</span><span class="sxs-lookup"><span data-stu-id="86af5-114">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="86af5-115">Wenn der primäre Fehler aufgetreten ist und Sie einen Failover zur Spiegelung durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86af5-115">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="86af5-116">Wenn die Spiegelung fehlgeschlagen ist und Sie das primäre Failover durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="86af5-116">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

