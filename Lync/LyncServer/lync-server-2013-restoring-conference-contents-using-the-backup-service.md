---
title: 'Lync Server 2013: Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts'
TOCTitle: Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49890716
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn die im Dateispeicher eines Front-End-Pools gespeicherten Informationen zu Konferenzen nicht mehr verfügbar sind, müssen Sie diese Informationen wiederherstellen, sodass die Konferenzdaten von Benutzern, die in diesem Pool verwaltet werden, erhalten bleiben. Wenn der Front-End-Pool, der Konferenzdaten verloren hat, mit einem anderen Front-End-Pool kombiniert wird, können Sie den Sicherungsdienst zur Wiederherstellung der Daten nutzen.

Sie müssen diese Aufgabe auch ausführen, wenn ein ganzer Pool ausfällt und Sie einen Failover seiner Benutzer in einen Sicherungspool durchführen müssen. Wenn für diese Benutzer ein Failover zurück in den ursprünglichen Pool durchgeführt wird, müssen Sie dieses Verfahren nutzen, um ihre Konferenzinhalte ebenfalls zurück in ihren ursprünglichen Pool zu kopieren.

Es wird davon ausgegangen, dass Pool1 mit Pool2 kombiniert wird und die Konferenzdaten in Pool1 verlorengehen. Mit folgendem Cmdlet können Sie den Sicherungsdienst starten, um die Inhalte wiederherzustellen:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Die Wiederherstellung der Konferenzinhalte kann je nach ihrer Größe einige Zeit dauern. Sie können den Status des Vorgangs mithilfe des folgenden Cmdlets prüfen:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Der Vorgang ist abgeschlossen, wenn das Cmdlet für das Datenkonferenzmodul einen Wert für ein stabiles System anzeigt.

