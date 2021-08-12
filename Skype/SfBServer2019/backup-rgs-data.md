---
title: Sichern Reaktionsgruppendienst (RGS)-Daten in Skype for Business Server 2019
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
description: Erfahren Sie, wie Sie Reaktionsgruppendienst (RGS)-Daten in Skype for Business Server 2019 sichern.
ms.openlocfilehash: 8b0cbbb41c7bf2a61d21043141d2475a8c69a79696e8cf5cbde6709e2d196c52
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280470"
---
# <a name="back-up-response-group-service-rgs-data"></a>Sichern Reaktionsgruppendienst (RGS)-Daten

Mit dem kumulativen Update vom Skype for Business Server. Juli 2019 haben wir die Möglichkeit hinzugefügt, RGS-Daten als Teil der Standardsicherung einzuschließen.

## <a name="rgs-data-replication"></a>RGS-Datenreplikation

Führen Sie die folgenden Schritte aus, um die RGS-Datenreplikation zu testen:

1. Installieren Sie das kumulative Update vom Juli auf allen Front-Ends (FEs) Ihres gepaarten Pools.
1. Installieren Sie die RGS-Datenbank auf beiden Mitgliedern des gepaarten Pools:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Führen Sie das folgende Cmdlet für beide Pools aus, um vorhandene RGS-Daten in die Sicherungstabellen zu replizieren, damit die Daten von RGSBackupService aufgenommen werden können:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Aktivieren Sie RGSBackupService (dadurch wird RGSBackupService global aktiviert. Wenn dieser Parameter auf "true" festgelegt ist, beginnt RGSBackupService mit der Synchronisierung von RGS-Daten in gekoppelten Pools (beide Pools müssen CU1 sein). Warten Sie einige Minuten, um loszulegen. Zunächst wird der Status "RGS BackupService" nicht initialisiert.
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. So überprüfen Sie BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Um DataReplication über Pools hinweg zu überprüfen, verwenden Sie diese Cmdlets (diese Cmdlets zeigen nur Besitzerpooldaten an):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. So überprüfen Sie RGS-Daten des Besitzerpools und deren Sicherungsdaten:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Überprüfen Sie die Workflowfunktionalität, indem Sie einen Audioanruf an Workflow senden.
1. Failover ihres RGS-Besitzerpools.
1. Überprüfen Sie die Workflowfunktionalität, indem Sie einen Audioanruf an Workflow senden.
1. Failback des Pools.
1. Aktualisieren Sie RGS-Daten im Quellpool, und führen Sie ein weiteres Failover durch, um zu überprüfen, ob Änderungen im Sicherungspool widergespiegelt werden. RGS sollte sich genauso verhalten wie vor dem Failover.

> [!TIP]
> Es wird empfohlen, diese Schritte für einen Großteil der Daten durchzuführen und häufige Failover- und Failbacks durchzuführen. Alle neuen RGS, die nach diesem CU-Update erstellt wurden, sollten ebenfalls repliziert werden.

## <a name="rgs-cmdlets"></a>RGS-Cmdlets

- To check BackupServiceStatus (The export status should be in the Final or Steady state. Der Importstatus sollte den Status "Normal" aufweisen. RGSBackupservice sollte aktiviert sein.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.)
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.)
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- So synchronisieren Sie alle Moduldaten einschließlich RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- So deaktivieren Sie RGSBackupService (dadurch wird RGSBackupService global deaktiviert. Wenn dieser Parameter auf "true" festgelegt ist, wird RGSBackupService für alle gekoppelten Pools deaktiviert.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
