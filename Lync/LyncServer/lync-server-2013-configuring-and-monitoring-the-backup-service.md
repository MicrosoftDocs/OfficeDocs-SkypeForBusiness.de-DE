---
title: 'Lync Server 2013: Konfigurieren und Überwachen des Sicherungsdiensts'
TOCTitle: Konfigurieren und Überwachen des Sicherungsdiensts
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205252(v=OCS.15)
ms:contentKeyID: 49295352
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren und Überwachen des Sicherungsdiensts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit den folgenden Befehlen der Lync Server-Verwaltungsshell können Sie den Sicherungsdienst konfigurieren und überwachen.


> [!NOTE]
> Die Gruppe RTCUniversalServerAdmins ist standardmäßig die einzige Gruppe mit der Berechtigung zum Ausführen von <STRONG>Get-CsBackupServiceStatus</STRONG>. Wenn Sie dieses Cmdlet verwenden möchten, melden Sie sich sich als Mitglied dieser Gruppe an. Sie können aber auch mit dem <STRONG>Set-CsBackupServiceConfiguration</STRONG>-Cmdlet anderen Benutzergruppen (z.&nbsp;B. CSAdministrator ) den Zugriff auf diesen Befehl gewähren.



## So zeigen Sie die Konfiguration des Sicherungsdiensts an

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceConfiguration

Der Standard für SyncInterval sind zwei Minuten.

## So legen Sie das Synchronisierungsintervall für den Sicherungsdienst fest

Führen Sie das folgende Cmdlet aus:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Beispielsweise wird mit dem folgenden Befehl ein Synchronisierungsintervall von drei Minuten festgelegt.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]
> Mit diesem Cmdlet können Sie auch das standardmäßige Synchronisierungsintervall für den Sicherungsdienst ändern. Sie sollten das Synchronisierungsintervall aber nur ändern, wenn es unbedingt erforderlich ist, da das Synchronisierungsintervall erhebliche Auswirkungen auf die Leistung des Sicherungsdiensts und den Zielwert für den Wiederherstellungspunkt (Recovery Point Objective, RPO) hat.



## So rufen Sie den Sicherungsdienststatus für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>


> [!NOTE]
> Der Synchronisierungsstatus des Sicherungsdiensts wird unidirektional zwischen einem Pool (P1) und dem zugehörigen Sicherungspool (P2) definiert. Der Synchronisierungsstatus zwischen P1 und P2 kann vom Synchronisierungsstatus zwischen P2 und P1 abweisen. Zwischen P1 und P2 weist der Sicherungsdienst den Status "Bereit" auf, wenn alle in P1 vorgenommenen Änderungen innerhalb des Synchronisierungsintervalls vollständig nach P2 repliziert werden. Er weist den Status "Endgültig" auf, wenn zwischen P1 und P2 keine zu synchronisierenden Änderungen mehr vorhanden sind. Beide Status stellen eine Momentaufnahme des Sicherungsdiensts zum Zeitpunkt der Ausführung des Cmdlets dar. Dies bedeutet nicht, dass der zurückgegebene Status so bleibt. Insbesondere der Status "Endgültig" bleibt nur erhalten, wenn P1 keine Änderungen generiert, nachdem das Cmdlet ausgeführt wurde. Dies gilt für das Failover von P1 zu P2, nachdem P1 im Rahmen der <STRONG>Invoke-CsPoolfailover</STRONG>-Ausführungslogik in den schreibgeschützten Modus versetzt wird.



## So rufen Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## So erzwingen Sie eine Synchronisierung des Sicherungsdiensts

Führen Sie das folgende Cmdlet aus:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

