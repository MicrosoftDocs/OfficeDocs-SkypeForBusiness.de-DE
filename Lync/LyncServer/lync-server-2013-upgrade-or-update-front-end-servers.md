---
title: 'Lync Server 2013: Aktualisieren oder Aktualisieren von Front-End-Servern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99c91a4f5fcae9f8d78bf01b19a17795916fb660
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Upgrade or update Front End Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-06-28_

Die Front-End-Server in einem Enterprise Edition-Pool sind in *Upgrade-Domänen*unterteilt. Hierbei handelt es sich um Teilmengen der Front-End-Server im Pool. Upgrade-Domänen werden vom Topologie-Generator automatisch erstellt.

Wenn Sie Server aktualisieren, müssen Sie eine Upgrade-Domäne gleichzeitig ausführen. Führen Sie die einzelnen Server in einer Upgrade-Domäne herunter, aktualisieren Sie Sie, und starten Sie Sie dann neu, bevor Sie zu einer anderen Upgrade-Domäne wechseln. Achten Sie darauf, nachzuverfolgen, welche Upgrade-Domänen und-Server Sie bisher aktualisiert haben. Verwenden Sie das folgende Flussdiagramm Diagramm, wenn Sie jeden Server aktualisieren.

![42ed59a4-1c26-49f7-ADE4-a5a788457ab9] (images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "42ed59a4-1c26-49f7-ADE4-a5a788457ab9")

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>So führen Sie ein Upgrade für die Front-End-Server in einem Pool durch

1.  Führen Sie auf einem Front-End-Server im Pool das folgende Cmdlet aus:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Wenn der Wert von *PoolUpgradeState* **ausgelastet**ist, warten Sie 10 Minuten, und versuchen Sie dann erneut, **Get-CsPoolUpgradeReadinessState** . Wenn Sie **beschäftigt** mindestens drei Mal hintereinander sehen, nachdem Sie 10 Minuten zwischen jedem Versuch gewartet haben, oder wenn Sie ein Ergebnis von **InsufficientActiveFrontEnds** für PoolUpgradeState sehen **,** liegt ein Problem mit dem Pool vor. Wenn dieser Pool mit einem anderen Front-End-Pool in einer Disaster Recovery-Topologie gekoppelt ist, sollten Sie den Pool für den Sicherungspool nicht überschreiben und dann die Server in diesem Pool aktualisieren. Ausführliche Informationen finden Sie unter [Failover eines Pools in lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Wenn der Wert von *PoolUpgradeState* **bereit**ist, fahren Sie mit Schritt 2 fort.

2.  Das Cmdlet " **Get-CsPoolUpgradeReadinessState** " gibt auch Informationen zu jeder Upgrade-Domäne im Pool und zu den Front-End-Servern in jeder Upgrade-Domäne zurück. Wenn der **ReadyforUpgrade** -Wert für die Upgrade-Domäne mit dem Server oder den Servern, die Sie aktualisieren möchten, **wahr** ist, können Sie diese Server jetzt problemlos aktualisieren. Gehen Sie dazu folgendermaßen vor:
    
    1.  Beenden Sie neue Verbindungen mit den Front-End-Servern, die Sie aktualisieren möchten `Stop-CsWindowsService -Graceful -Verbose` , mithilfe des Cmdlets.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Server Upgrades während einer geplanten Server Downtime durchführen, können Sie dieses Cmdlet ohne den "-<STRONG>Graceful</STRONG>"-Parameter wie folgt ausführen: <STRONG>Stop-CsWindowsService</STRONG>. Dadurch werden die Dienste sofort beendet, ohne dass alle vorhandenen Dienstanforderungen ausgefüllt werden müssen.

        
        </div>
    
    2.  Aktualisieren Sie die Server, die dieser Upgrade-Domäne zugeordnet sind.
    
    3.  Starten Sie die Server neu, und stellen Sie sicher, dass Sie neue Verbindungen akzeptieren.

3.  Wiederholen Sie die Schritte 1 und 2 für jede andere Upgrade-Domäne im Pool, bis alle Front-End-Server aktualisiert wurden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

