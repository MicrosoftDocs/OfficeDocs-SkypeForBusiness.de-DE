---
title: Konfigurieren und Überwachen des Sicherungsdiensts
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können die Befehle für die Skype for Business Server-Verwaltungsshell verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818216"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Konfigurieren und Überwachen des Sicherungsdiensts in Skype for Business Server

Sie können die folgenden Befehle der Skype for Business Server-Verwaltungsshell verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen. Informationen zum Wiederherstellen von Konferenz Informationen, die im Dateispeicher eines Front-End-Pools gespeichert sind, finden Sie weiter unten unter [Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts](#restore-conference-contents-using-the-backup-service).

> [!NOTE]  
> Die Gruppe RTCUniversalServerAdmins ist die einzige Gruppe, die über die standardmäßige Berechtigung zum Ausführen von **Get-CsBackupServiceStatus** verfügt. Wenn Sie dieses Cmdlet verwenden möchten, melden Sie sich als Mitglied dieser Gruppe an. Oder Sie können anderen Gruppen (beispielsweise CSAdministrator) mithilfe des Cmdlets " **Satz-CsBackupServiceConfiguration** " Zugriff auf diesen Befehl gewähren.

## <a name="to-see-the-backup-service-configuration"></a>So zeigen Sie die Konfiguration des Sicherungsdiensts an

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceConfiguration

Der Standardwert für SyncInterval beträgt zwei Minuten.

## <a name="to-set-the-backup-service-sync-interval"></a>So stellen Sie das Synchronisierungsintervall für den Sicherungsdienst ein

Führen Sie das folgende Cmdlet aus:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Obwohl Sie mit diesem Cmdlet das Standard Synchronisierungsintervall für den Sicherungsdienst ändern können, sollten Sie dies nicht tun, es sei denn, dies ist unbedingt erforderlich, da das Synchronisierungsintervall große Auswirkungen auf die Leistung des Sicherungsdiensts und auf das Recovery Point-Ziel (RPO) hat.

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>So rufen Sie den Sicherungsdienst Status für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> Der Synchronisierungsstatus des Sicherungsdiensts wird unidirektional von einem Pool (P1) zu seinem Sicherungspool (P2) definiert. Der Synchronisierungsstatus von P1 zu P2 kann von P2 zu P1 unterschiedlich sein. Bei P1 bis P2 befindet sich der Sicherungsdienst in einem "stabilen" Zustand, wenn alle Änderungen, die in P1 vorgenommen wurden, innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden. Es befindet sich im "endgültigen" Zustand, wenn keine weiteren Änderungen von P1 zu P2 synchronisiert werden. Beide Zustände deuten auf eine Momentaufnahme des Sicherungsdiensts zu dem Zeitpunkt hin, zu dem das Cmdlet ausgeführt wird. Das bedeutet nicht, dass der zurückgegebene Zustand unverändert bleibt. Insbesondere bleibt der Zustand "Final" weiterhin nur dann bestehen, wenn P1 nach der Ausführung des Cmdlets keine Änderungen generiert. Dies gilt im Fall eines Failovers von P1 auf P2, nachdem P1 als Teil der Ausführungslogik **Invoke-CsPoolfailover** in den schreibgeschützten Modus versetzt wurde.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>So erhalten Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool

Führen Sie das folgende Cmdlet aus:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>So erzwingen Sie eine Synchronisierung des Sicherungsdiensts

Führen Sie das folgende Cmdlet aus:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts 

Wenn die Konferenz Informationen, die im Dateispeicher eines Front-End-Pools gespeichert sind, nicht mehr zur Verfügung stehen, müssen Sie diese Informationen so wiederherstellen, dass Benutzer, die im Pool verwaltet werden, ihre Konferenzdaten beibehalten. Wenn der Front-End-Pool, in dem Konferenzdaten verloren gegangen sind, mit einem anderen Front-End-Pool gekoppelt ist, können Sie die Daten mithilfe des Sicherungsdiensts wiederherstellen.

Sie müssen diese Aufgabe auch ausführen, wenn ein gesamter Pool fehlgeschlagen ist und Sie die Benutzer nicht mit einem Sicherungspool durchführen müssen. Wenn diese Benutzer wieder in ihren ursprünglichen Pool zurückgekehrt sind, müssen Sie diese Vorgehensweise verwenden, um Ihre Konferenzinhalte wieder in ihren ursprünglichen Pool zu kopieren.

Gehen Sie davon aus, dass pool1 mit Pool2 gekoppelt ist und die Konferenzdaten in pool1 verloren gehen. Sie können das folgende Cmdlet verwenden, um den Sicherungsdienst aufzurufen, um den Inhalt wiederherzustellen:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Das Wiederherstellen der Konferenzinhalte kann je nach Größe einige Zeit in Anspruch nehmen. Sie können das folgende Cmdlet verwenden, um den Prozessstatus zu überprüfen:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Der Vorgang erfolgt, wenn dieses Cmdlet den Wert des Steady-State-Werts für das Datenkonferenz Modul zurückgibt.
