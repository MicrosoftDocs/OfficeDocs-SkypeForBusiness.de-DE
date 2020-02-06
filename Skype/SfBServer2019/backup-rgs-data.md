---
title: Sichern von Daten des Reaktionsgruppendiensts (RGS) in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Hier erfahren Sie, wie Sie in Skype for Business Server 2019 Daten zum Response Group Service (RGS) sichern.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824069"
---
# <a name="back-up-response-group-service-rgs-data"></a>Sichern von Daten des Reaktionsgruppendiensts (RGS)

Mit dem kumulativen Update für Skype for Business Server 2019 Juli haben wir die Möglichkeit aufgenommen, RGS-Daten als Teil der Standardsicherung einzubeziehen.

## <a name="rgs-data-replication"></a>RGS-Datenreplikation

Führen Sie die folgenden Schritte aus, um die Funktionalität der RGS-Datenreplikation zu testen:

1. Installieren Sie das kumulative Update vom Juli auf allen Front-Ends (FES) Ihres gekoppelten Pools.
1. Installieren Sie die RGS-Datenbank auf beiden Mitgliedern des gekoppelten Pools:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Führen Sie das folgende Cmdlet in beiden Pools aus, um vorhandene RGS-Daten in die Sicherungstabellen zu replizieren, damit die Daten von RGSBackupService abgerufen werden können:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Aktivieren Sie RGSBackupService (Dadurch wird RGSBackupService global aktiviert. Wenn dieser Parameter auf "true" festgelegt ist, startet RGSBackupService die Synchronisierung von RGS-Daten in gekoppelten Pools (beide Pools müssen CU1 sein). Warten Sie ein paar Minuten, um den Vorgang zu starten. Zunächst wird der RGS-Backupservice-Status NotInitialized.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. So überprüfen Sie BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Verwenden Sie diese Cmdlets, um die Datenreplikation über Pools hinweg zu überprüfen (diese Cmdlets zeigen nur Besitzer Pool Daten an):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. So überprüfen Sie die RGS-Daten des Besitzer Pools und dessen Sicherungsdaten:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Überprüfen Sie die Workflow Funktionalität, indem Sie einen Audioanruf an den Workflow durchführen.
1. Failover Ihres RGS-Besitzer Pools.
1. Überprüfen Sie die Workflow Funktionalität, indem Sie einen Audioanruf an den Workflow durchführen.
1. Failback des Pools.
1. Aktualisieren Sie RGS-Daten im Quell Pool, und führen Sie ein weiteres Failover durch, um zu überprüfen, ob Änderungen im Sicherungspool wiedergegeben werden. RGS sollte sich auf die gleiche Weise Verhalten, wie es sich vor dem Failover befand.

> [!TIP]
> Es wird empfohlen, dass Sie diese Schritte für einen Großteil der Daten ausführen und häufige Failover-und Failback-Vorgänge durchführen. Alle neuen RGS, die nach diesem Cu-Update erstellt wurden, sollten ebenfalls repliziert werden.

## <a name="rgs-cmdlets"></a>RGS-Cmdlets

- Zum Überprüfen von BackupServiceStatus (der Exportstatus sollte im endgültigen oder stationären Zustand sein. Der Importstatus sollte im normalen Zustand sein. RGSBackupservice sollte aktiviert sein.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Zum vollständigen Synchronisieren von RGS-Daten im Sicherungspool (Hiermit werden die vollständigen RGS-Daten im Sicherungspool synchronisiert.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Zum vollständigen Synchronisieren des RGS-Dateispeichers im Sicherungspool (Hiermit werden die vollständigen RGS-Daten im Sicherungspool synchronisiert.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- So synchronisieren Sie RGS-Deltadaten im Sicherungspool (Hiermit werden Delta-Daten nur für RGS in einem Sicherungspool synchronisiert.):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- So synchronisieren Sie alle Modul Daten einschließlich RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- So deaktivieren Sie RGSBackupService (Dadurch wird RGSBackupService global deaktiviert. Wenn dieser Parameter auf "true" festgelegt ist, wird RGSBackupService für alle gekoppelten Pools deaktiviert.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
