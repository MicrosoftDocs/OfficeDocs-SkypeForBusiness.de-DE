---
title: Upgraden oder Updaten von Front-End-Servern in Lync Server 2013
TOCTitle: Upgraden oder Updaten von Front-End-Servern in Lync Server 2013
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204736(v=OCS.15)
ms:contentKeyID: 49293404
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Upgraden oder Updaten von Front-End-Servern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-06-28_

Die Front-End-Server in einem Enterprise Edition-Pool werden in *Upgradedomänen* aufgeteilt. Diese stellen Teilmengen von Front-End-Servern im Pool dar. Upgradedomänen werden automatisch vom Topologie-Generator erstellt.

Wenn Sie Server upgraden, müssen Sie dies für jede Upgradedomäne einzeln ausführen. Fahren Sie jeden Server in einer Upgradedomäne herunter, führen Sie das Upgrade für ihn durch, und starten Sie ihn neu, bevor Sie zu einer anderen Upgradedomäne wechseln. Merken Sie sich unbedingt, für welche Upgradedomänen und Server Sie bereits Upgrades durchgeführt haben. Verwenden Sie für ein Upgraden jedes Servers das folgende Flussdiagramm.

![Flussdiagramm zu Updateserver](images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "Flussdiagramm zu Updateserver")

## So führen Sie ein Upgrade für die Front-End-Server in einem Pool durch

1.  Führen Sie auf einem Front-End-Server im Pool das folgende Cmdlet aus:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Wenn der Wert von *PoolUpgradeState***Busy** lautet, warten Sie 10 Minuten, und führen Sie dann **Get-CsPoolUpgradeReadiness** erneut aus. Wenn **Busy** mindestens drei Mal hintereinander angezeigt wird (und Sie zwischen den einzelnen Versuchen 10 Minuten verstreichen lassen) oder das Ergebnis **InsufficientActiveFrontEnds** für **PoolUpgradeState** angezeigt wird, liegt ein Problem mit dem Pool vor. Bildet dieser Pool ein Paar mit einem anderen Front-End-Pool in einer Notfallwiederherstellungstopologie, sollten Sie ein Failover für den Pool zum Sicherungspool ausführen und anschließend die Server in diesem Pool aktualisieren. Ausführliche Informationen finden Sie unter [Ausführen eines Failovers für einen Pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Falls der Wert von *PoolUpgradeState***Bereit** lautet, fahren Sie mit Schritt 2 fort.

2.  Das Cmdlet **Get-CsPoolUpgradeReadinessState** gibt darüber hinaus Informationen zu den einzelnen Upgradedomänen im Pool sowie zu den Front-End-Servern in den einzelnen Upgradedomänen zurück. Hat **ReadyforUpgrade** den Wert **True** für die Upgradedomäne, die den oder die zu aktualisierenden Server enthält, können Sie nun für diese Server problemlos ein Upgrade durchführen. Gehen Sie hierzu wie folgt vor:
    
    1.  Stoppen Sie neue Verbindungen mit den Front-End-Servern, die Sie upgraden möchten, über das Cmdlet `Stop-CsWindowsService -Graceful -Verbose`.
        

        > [!NOTE]
        > Wenn Sie diese Serverupgrades während einer geplanten Serverstillstandszeit ausführen, können Sie das Cmdlet ohne den Parameter -<STRONG>Graceful</STRONG> ausführen: <STRONG>Stop-CsWindowsService</STRONG>. Hiermit werden die Dienste sofort heruntergefahren, ohne dass gewartet wird, bis alle vorhandenen Dienstanforderungen abgearbeitet wurden.

    
    2.  Führen Sie Upgrades für die Server durch, die dieser Upgradedomäne zugewiesen sind.
    
    3.  Starten Sie die Server neu, und stellen Sie sicher, dass sie neue Verbindungen zulassen.

3.  Wiederholen Sie die Schritte 1 und 2 für jede Upgradedomäne im Pool, bis für alle Front-End-Server ein Upgrade durchgeführt wurde.

