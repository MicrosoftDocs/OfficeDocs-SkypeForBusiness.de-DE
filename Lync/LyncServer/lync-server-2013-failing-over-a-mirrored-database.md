---
title: 'Lync Server 2013: Ausführen eines Failovers für eine gespiegelte Datenbank'
TOCTitle: Ausführen eines Failovers für eine gespiegelte Datenbank
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204991(v=OCS.15)
ms:contentKeyID: 49294357
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen eines Failovers für eine gespiegelte Datenbank in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-03-14_

Wenn Sie Ihre Back-End-Datenbank so konfiguriert haben, dass eine synchronisierte Spiegelung mit einem Zeugen erfolgt, wird das Failover automatisch ausgeführt. Wenn Sie die synchronisierte Spiegelung ohne Zeugen konfiguriert haben, können Sie die nachfolgend beschriebenen Verfahren verwenden, um ein Failover und Failback für Ihre Datenbank auszuführen. Sie können diese Prozeduren auch für einen manuellen Failover- und Failback-Vorgang für Ihre Datenbank verwenden, selbst wenn Sie einen Zeugen konfiguriert haben.

## So führen Sie ein Failover für die Back-End-Datenbank aus

1.  Ermitteln Sie vor Ausführung des Failovers, welche Back-End-Datenbank die Hauptdatenbank und welche die gespiegelte Datenbank sein soll, indem Sie das folgenden Cmdlet ausführen:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Wenn der zentralen Verwaltungsspeicher in diesem Pool gehostet wird, geben Sie das folgende Cmdlet ein, um festzulegen, welche Datenbank die Hauptdatenbank und welche die gespiegelte Datenbank für den zentralen Verwaltungsspeicher sein soll:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Führen Sie das Failover für die Benutzerdatenbank aus:
    
      - Wenn die primäre Datenbank ausgefallen ist und Sie ein Failover auf die Spiegeldatenbank ausführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Wenn die Spiegeldatenbank ausgefallen ist und Sie ein Failover auf die primäre Datenbank ausführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Wenn ein zentraler Verwaltungsserver vom Pool gehostet wird, können Sie das Failover des zentralen Verwaltungsspeichers ausführen.
    
      - Wenn die primäre Datenbank ausgefallen ist und Sie ein Failover auf die Spiegeldatenbank ausführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Wenn die Spiegeldatenbank ausgefallen ist und Sie ein Failover auf die primäre Datenbank ausführen, geben Sie Folgendes ein:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

