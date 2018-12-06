---
title: Wiederherstellen eines Dateispeichers
TOCTitle: Wiederherstellen eines Dateispeichers
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202180(v=OCS.15)
ms:contentKeyID: 52056382
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen eines Dateispeichers

 

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Die Dateispeicher der Standard Edition befinden Sie in der Regel auf dem Standard Edition-Server. Die Dateispeicher der Enterprise Edition hingegen befinden sich in der Regel auf einem Dateiserver oder einem Cluster. Im folgenden Verfahren wird beschrieben, wie ein Dateispeicher wiederhergestellt wird.

## So stellen Sie einen Dateispeicher wieder her

1.  Beim Ausfall eines Dateispeichers kopieren Sie den entsprechenden Dateispeicher aus **$Backup\\** in das Verzeichnis mit dem Dateispeicher auf dem Dateiserver oder Standard Edition-Server und geben den Ordner dann frei.
    

    > [!IMPORTANT]
    > Der Pfad und der Dateiname für den wiederhergestellten Dateispeicher sollten identisch sein mit dem gesicherten Dateispeicher, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.



2.  Falls notwendig, legen Sie die Zugriffssteuerungslisten (Access Control Lists, ACLs) für den Dateispeicher fest. Geben Sie an der Befehlszeile Folgendes ein:
    
        Enable-CsTopology
    

    > [!NOTE]
    > Dieser Schritt ist nur erforderlich, wenn Sie den Topologie-Generator nicht während des Wiederherstellungsvorgangs bereits ausgeführt haben.


