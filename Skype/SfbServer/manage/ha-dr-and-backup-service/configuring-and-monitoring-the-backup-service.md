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
description: Sie können Skype for Business Server Verwaltungsshell-Befehle verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.
ms.openlocfilehash: ea4dd6bba87b06cb9c51320be9c040869c17204619656dfc4291054fcb6c214a
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849540"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Konfigurieren und Überwachen des Sicherungsdiensts in Skype for Business Server

Sie können die folgenden Befehle Skype for Business Server Verwaltungsshell verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen. Informationen zum Wiederherstellen von Konferenzinformationen, die im Dateispeicher eines Front-End-Pools gespeichert sind, finden Sie weiter unten unter ["Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts".](#restore-conference-contents-using-the-backup-service)

> [!NOTE]  
> Die Gruppe "RTCUniversalServerAdmins" ist die einzige Gruppe, die über Berechtigungen zum standardmäßigen Ausführen von **"Get-CsBackupServiceStatus"** verfügt. Um dieses Cmdlet zu verwenden, melden Sie sich als Mitglied dieser Gruppe an. Alternativ können Sie anderen Gruppen (z. B. CSAdministrator) mithilfe des Cmdlets **"Set-CsBackupServiceConfiguration"** Zugriff auf diesen Befehl gewähren.

## <a name="to-see-the-backup-service-configuration"></a>So zeigen Sie die Konfiguration des Sicherungsdiensts an

Führen Sie das folgende Cmdlet aus:<br/><br/>Get-CsBackupServiceConfiguration

Der Standardwert für SyncInterval beträgt zwei Minuten.

## <a name="to-set-the-backup-service-sync-interval"></a>So legen Sie das Synchronisierungsintervall des Sicherungsdiensts fest

Führen Sie das folgende Cmdlet aus:<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval-Intervall

Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Obwohl Sie dieses Cmdlet verwenden können, um das Standardsynchronisierungsintervall für den Sicherungsdienst zu ändern, sollten Sie dies nicht tun, es sei denn, es ist absolut erforderlich, da das Synchronisierungsintervall einen großen Einfluss auf die Leistung des Sicherungsdiensts und das Ziel des Wiederherstellungspunkts (Recovery Point Objective, RPO) hat.

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>So rufen Sie den Sicherungsdienststatus für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<pool-FQDN>

> [!NOTE]  
> Der Synchronisierungsstatus des Sicherungsdiensts wird unidirektional von einem Pool (P1) zu seinem Sicherungspool (P2) definiert. Der Synchronisierungsstatus von P1 zu P2 kann von P2 bis P1 abweichen. Für P1 bis P2 befindet sich der Sicherungsdienst in einem "stabilen" Zustand, wenn alle in P1 vorgenommenen Änderungen innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden. Er befindet sich im "endgültigen" Zustand, wenn keine weiteren Änderungen von P1 zu P2 synchronisiert werden müssen. Beide Zustände deuten auf eine Momentaufnahme des Sicherungsdiensts zum Zeitpunkt der Ausführung des Cmdlets hin. Es bedeutet nicht, dass der zurückgegebene Zustand wie danach bleibt. Insbesondere wird der Zustand "endgültig" nur dann beibehalten, wenn P1 nach ausführung des Cmdlets keine Änderungen generiert. Dies gilt für den Fall, dass P1 auf P2 umgestellt wird, nachdem P1 als Teil der **Invoke-CsPoolfailover-Ausführungslogik** in den schreibgeschützten Modus versetzt wurde.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>So rufen Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:<br/><br/>Get-CsPoolBackupRelationship -PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>So erzwingen Sie eine Synchronisierung des Sicherungsdiensts

Führen Sie das folgende Cmdlet aus:<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<poolFqdn> [-BackupModule {All| PresenceFocus| DataConf| CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts 

Wenn die im Dateispeicher eines Front-End-Pools gespeicherten Konferenzinformationen nicht mehr verfügbar sind, müssen Sie diese Informationen wiederherstellen, damit die im Pool verwalteten Benutzer ihre Konferenzdaten beibehalten. Wenn der Front-End-Pool, der Konferenzdaten verloren hat, mit einem anderen Front-End-Pool gekoppelt ist, können Sie den Sicherungsdienst verwenden, um die Daten wiederherzustellen.

Sie müssen diese Aufgabe auch ausführen, wenn ein ganzer Pool ausfällt und Sie einen Failover seiner Benutzer in einen Sicherungspool durchführen müssen. Wenn für diese Benutzer ein Failover zurück in den ursprünglichen Pool durchgeführt wird, müssen Sie dieses Verfahren nutzen, um ihre Konferenzinhalte ebenfalls zurück in ihren ursprünglichen Pool zu kopieren.

Es wird davon ausgegangen, dass Pool1 mit Pool2 kombiniert wird und die Konferenzdaten in Pool1 verlorengehen. Mit dem folgenden Cmdlet können Sie den Sicherungsdienst aufrufen, um den Inhalt wiederherzustellen:<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

Die Wiederherstellung der Konferenzinhalte kann je nach ihrer Größe einige Zeit dauern. Sie können den Status des Vorgangs mithilfe des folgenden Cmdlets prüfen:<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

Der Vorgang ist abgeschlossen, wenn das Cmdlet für das Datenkonferenzmodul einen Wert für ein stabiles System anzeigt.
