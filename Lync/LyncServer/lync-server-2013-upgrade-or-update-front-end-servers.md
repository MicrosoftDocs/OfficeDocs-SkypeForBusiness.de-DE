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
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Aktualisieren oder Aktualisieren der Front-End-Server in lync Server 2013

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-06-28_

Die Front-End-Server in einem Enterprise Edition-Pool werden in *Upgradedomänen* aufgeteilt. Diese stellen Teilmengen von Front-End-Servern im Pool dar. Upgrade-Domänen werden automatisch vom Topologie-Generator erstellt.

Wenn Sie Server aktualisieren, müssen Sie jeweils eine Upgrade-Domäne durchführen. Bringen Sie jeden Server in eine Upgrade-Domäne herunter, aktualisieren Sie ihn, und starten Sie ihn neu, bevor Sie zu einer anderen Upgrade-Domäne übergehen. Achten Sie darauf, nachzuverfolgen, welche Upgrade-Domänen und-Server Sie bisher aktualisiert haben. Verwenden Sie das folgende Flussdiagramm Diagramm, wenn Sie jeden Server aktualisieren.

![Upgraden oder Updaten von Front-End-Servern](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>So wenden Sie ein Upgrade auf die Front-End-Server in einem Pool an

1.  Führen Sie auf einem Front-End-Server im Pool das folgende Cmdlet aus:
    
    **Get-cspoolupgradereadinessstate "**
    
    Wenn der Wert von *poolupgradestatebereit* **ausgelastet**ist, warten Sie 10 Minuten, und versuchen Sie es dann erneut mit **Get-cspoolupgradereadinessstate "** . Wenn Sie mindestens drei aufeinanderfolgende male **beschäftigt** sind, nachdem Sie 10 Minuten zwischen den einzelnen versuchen gewartet haben oder wenn ein Ergebnis von **InsufficientActiveFrontEnds** für poolupgradestatebereit angezeigt wird **,** liegt ein Problem mit dem Pool vor. Bildet dieser Pool ein Paar mit einem anderen Front-End-Pool in einer Notfallwiederherstellungstopologie, sollten Sie ein Failover für den Pool zum Sicherungspool ausführen und anschließend die Server in diesem Pool aktualisieren. Ausführliche Informationen finden Sie unter [failing over a Pool in lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Falls der Wert von *PoolUpgradeState***Bereit** lautet, fahren Sie mit Schritt 2 fort.

2.  Das Cmdlet **Get-cspoolupgradereadinessstate "** gibt außerdem Informationen zu jeder Upgrade-Domäne im Pool und zu den Front-End-Servern in jeder Upgrade-Domäne zurück. Wenn der **ReadyforUpgrade** -Wert für die Upgrade-Domäne **true** ist, die den Server enthält, den Sie aktualisieren möchten, können Sie diese Server problemlos jetzt aktualisieren. Gehen Sie hierzu wie folgt vor:
    
    1.  Beenden Sie neue Verbindungen mit den Front-End-Servern, die Sie aktualisieren möchten, mithilfe des `Stop-CsWindowsService -Graceful -Verbose` Cmdlets.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie diese Server Upgrades während einer geplanten Serverausfall Zeit durchführen, können Sie dieses Cmdlet wie folgt ohne den Parameter "-<STRONG>Graceful</STRONG>" ausführen: <STRONG>Stop-CsWindowsService</STRONG>. Dadurch werden Dienste sofort heruntergefahren, ohne darauf zu warten, dass alle vorhandenen Dienstanforderungen ausgefüllt werden.

        
        </div>
    
    2.  Aktualisieren Sie die damit verknüpften Server mit der Upgrade-Domäne.
    
    3.  Starten Sie die Server neu, und stellen Sie sicher, dass Sie neue Verbindungen akzeptieren.

3.  Wiederholen Sie die Schritte 1 und 2 für jede andere Upgrade-Domäne im Pool, bis alle Front-End-Server aktualisiert wurden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

