---
title: 'Lync Server 2013: Ausführen eines Failovers für eine gespiegelte Datenbank'
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
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="5593c-102">Ausführen eines Failovers für eine gespiegelte Datenbank in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5593c-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5593c-103">_**Letztes Änderungsdatum des Themas:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="5593c-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="5593c-104">Wenn Sie Ihre Back-End-Datenbank so konfiguriert haben, dass die synchronisierte Spiegelung mit einem Zeugen verwendet wird, ist das Failover automatisch.</span><span class="sxs-lookup"><span data-stu-id="5593c-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="5593c-105">Wenn Sie die synchronisierte Spiegelung ohne Zeugen konfiguriert haben, können Sie die folgenden Verfahren zum Failover und Failback der Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="5593c-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="5593c-106">Sie können diese Verfahren auch zum manuellen Failover und Failback Ihrer Datenbanken verwenden, selbst wenn Sie einen Zeugen konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="5593c-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="5593c-107">So führen Sie einen Failover für Ihre Back-End-Datenbank aus</span><span class="sxs-lookup"><span data-stu-id="5593c-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="5593c-108">Bevor Sie einen Failover durchführen, können Sie ermitteln, welche Back-End-Datenbank der Prinzipal ist und welche die Spiegelung ist, indem Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="5593c-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="5593c-109">Wenn der zentrale Verwaltungsspeicher in diesem Pool gehostet wird, geben Sie das folgende Cmdlet ein, um zu ermitteln, welches der Prinzipal ist und welches die Spiegelung für den zentralen Verwaltungsspeicher ist:</span><span class="sxs-lookup"><span data-stu-id="5593c-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="5593c-110">Durchführen des Failovers der Benutzerdatenbank:</span><span class="sxs-lookup"><span data-stu-id="5593c-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="5593c-111">Wenn der primäre Fehler aufgetreten ist und Sie einen Failover zur Spiegelung durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5593c-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="5593c-112">Wenn der Spiegel Fehler aufgetreten ist und Sie das primäre Failover durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5593c-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="5593c-113">Wenn der Pool den zentralen Verwaltungs Server hostet, führen Sie das Failover des zentralen Verwaltungsspeichers durch.</span><span class="sxs-lookup"><span data-stu-id="5593c-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="5593c-114">Wenn der primäre Fehler aufgetreten ist und Sie einen Failover zur Spiegelung durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5593c-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="5593c-115">Wenn der Spiegel Fehler aufgetreten ist und Sie das primäre Failover durchführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="5593c-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

