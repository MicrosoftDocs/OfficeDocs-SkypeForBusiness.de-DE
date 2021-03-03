---
title: Konfigurieren und Überwachen des Sicherungsdiensts
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können skype for Business Server Management Shell Befehle verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817195"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Konfigurieren und Überwachen des Sicherungsdiensts in Skype for Business Server

Sie können die folgenden Skype for Business Server-Verwaltungsshell-Befehle verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen. Informationen zum Wiederherstellen von Konferenzinformationen, die im Dateispeicher eines Front-End-Pools gespeichert sind, finden Sie unter ["Wiederherstellen](#restore-conference-contents-using-the-backup-service)von Konferenzinhalten mithilfe des Sicherungsdiensts" weiter unten.

> [!NOTE]  
> Die Gruppe "RTCUniversalServerAdmins" ist die einzige Gruppe, die standardmäßig über Berechtigungen zum Ausführen von **"Get-CsBackupServiceStatus"** verfügt. Um dieses Cmdlet zu verwenden, melden Sie sich als Mitglied dieser Gruppe an. Sie können auch anderen Gruppen (z. B. CSAdministrator) mithilfe des Cmdlets **"Set-CsBackupServiceConfiguration"** Zugriff auf diesen Befehl gewähren.

## <a name="to-see-the-backup-service-configuration"></a>So sehen Sie die Sicherungsdienstkonfiguration

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceConfiguration

Der Standardwert für SyncInterval beträgt zwei Minuten.

## <a name="to-set-the-backup-service-sync-interval"></a>So legen Sie das Synchronisierungsintervall für den Sicherungsdienst fest

Führen Sie das folgende Cmdlet aus:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Obwohl Sie dieses Cmdlet verwenden können, um das Standardsynchronisierungsintervall für den Sicherungsdienst zu ändern, sollten Sie dies nur tun, wenn dies absolut erforderlich ist, da das Synchronisierungsintervall große Auswirkungen auf die Leistung des Sicherungsdiensts und das Ziel des Wiederherstellungspunkts (Recovery Point Objective, RPO) hat.

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>So erhalten Sie den Sicherungsdienststatus für einen bestimmten Pool

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> Der Sicherungsdienstsynchronisierungsstatus wird unidirektional von einem Pool (P1) zum Sicherungspool (P2) definiert. Der Synchronisierungsstatus von P1 zu P2 kann sich von P2 bis P1 unterscheiden. Für P1 bis P2 befindet sich der Sicherungsdienst in einem "stabilen" Zustand, wenn alle in P1 vorgenommenen Änderungen innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden. Er befindet sich im "endgültigen" Zustand, wenn es keine weiteren Änderungen gibt, die von P1 zu P2 synchronisiert werden sollen. Beide Zustände weisen auf eine Momentaufnahme des Sicherungsdiensts zum Zeitpunkt der Ausführung des Cmdlets hin. Es bedeutet nicht, dass der zurückgegebene Zustand wie danach bleibt. Insbesondere gilt der Status "final" nur, wenn P1 nach der Ausführung des Cmdlets keine Änderungen generiert. Dies gilt für den Fall, dass P1 auf P2 umgeschaltet wird, nachdem P1 als Teil der **Invoke-CsPoolfailover-Ausführungslogik** in den schreibgeschützten Modus versetzt wurde.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>So erhalten Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool

Führen Sie das folgende Cmdlet aus:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>So erzwingen Sie die Synchronisierung des Sicherungsdiensts

Führen Sie das folgende Cmdlet aus:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts 

Wenn die im Dateispeicher eines Front-End-Pools gespeicherten Konferenzinformationen nicht mehr verfügbar sind, müssen Sie diese Informationen wiederherstellen, damit benutzer, die im Pool gespeichert sind, ihre Konferenzdaten beibehalten. Wenn der Front-End-Pool, der Konferenzdaten verloren hat, mit einem anderen Front-End-Pool gekoppelt ist, können Sie die Daten mithilfe des Sicherungsdiensts wiederherstellen.

Sie müssen diese Aufgabe auch ausführen, wenn ein ganzer Pool ausfällt und Sie einen Failover seiner Benutzer in einen Sicherungspool durchführen müssen. Wenn für diese Benutzer ein Failover zurück in den ursprünglichen Pool durchgeführt wird, müssen Sie dieses Verfahren nutzen, um ihre Konferenzinhalte ebenfalls zurück in ihren ursprünglichen Pool zu kopieren.

Es wird davon ausgegangen, dass Pool1 mit Pool2 kombiniert wird und die Konferenzdaten in Pool1 verlorengehen. Mit dem folgenden Cmdlet können Sie den Sicherungsdienst aufrufen, um den Inhalt wiederherzustellen:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Die Wiederherstellung der Konferenzinhalte kann je nach ihrer Größe einige Zeit dauern. Sie können den Status des Vorgangs mithilfe des folgenden Cmdlets prüfen:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Der Vorgang ist abgeschlossen, wenn das Cmdlet für das Datenkonferenzmodul einen Wert für ein stabiles System anzeigt.
