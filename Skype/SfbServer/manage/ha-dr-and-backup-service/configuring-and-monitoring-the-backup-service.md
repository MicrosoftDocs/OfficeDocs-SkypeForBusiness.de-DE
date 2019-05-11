---
title: Konfigurieren und Überwachen des Sicherungsdiensts
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können Skype für Business Server Management Shell-Befehle zum Konfigurieren und Überwachen des Sicherungsdienstes verwenden.
ms.openlocfilehash: aa6a1aca7e753877c15f64c3736a09ad9e2ca066
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903151"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Konfigurieren und Überwachen des Sicherungsdienstes in Skype für Business Server

Sie können die folgenden Skype für Business Server Management Shell-Befehle konfigurieren und Überwachen des Sicherungsdienstes verwenden. Um in den Dateispeicher eines Front-End-Pools gespeicherten Konferenzinformationen wiederherzustellen, finden Sie unter [Wiederherstellen von konferenzinhalten mithilfe des Sicherungsdienstes](#restore-conference-contents-using-the-backup-service), unten.

> [!NOTE]  
> Die Gruppe "RTCUniversalServerAdmins" ist die einzige Gruppe, die Berechtigungen zum Ausführen von **Get-CsBackupServiceStatus** standardmäßig verfügt. Wenn Sie dieses Cmdlet verwenden, melden Sie sich als Mitglied dieser Gruppe. Oder Sie können Zugriff auf mit diesem Befehl zu anderen Gruppen (z. B. "csadministrator") gewähren, mit dem Cmdlet **"Set-csbackupserviceconfiguration"** .

## <a name="to-see-the-backup-service-configuration"></a>Um die Konfiguration des Sicherungsdiensts finden Sie unter

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceConfiguration

Der Standard für SyncInterval sind zwei Minuten.

## <a name="to-set-the-backup-service-sync-interval"></a>So legen Sie das Synchronisierungsintervall Sicherungsdienst fest

Führen Sie das folgende Cmdlet aus:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Folgendes wird beispielsweise das Intervall von drei Minuten.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Obwohl Sie dieses Cmdlet zum Ändern des Standard-Synchronisierungsintervall für den Sicherungsdienst verwenden können, sollten Sie nicht, damit es sei denn, dies unbedingt erforderlich ist, als die Synchronisierung Intervall großen Einfluss auf die Leistung Sicherungsdienst und die Recovery Point Objectives (RPO) hat.

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Um den sicherungsdienststatus für einen bestimmten Pool zu erhalten

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> Der Synchronisierungsstatus des Sicherungsdienstes ist gleich dem Sicherungspool (P2) unidirectionally aus einem Pool (P1) definiert. Der Synchronisierungsstatus von P1 zu P2 kann andere als die von P2 zu P1 sein. Für P1 zu P2 ist Sicherungsdienst im Zustand "stetig", wenn alle Änderungen in P1 vollständig in das Synchronisierungsintervall über zu P2 repliziert werden. Es ist in "Endzustand" liegen keine weitere Änderungen, die von P1 zu P2 synchronisiert werden. Sowohl Zustand Geben Sie eine Momentaufnahme der des Sicherungsdienstes an, zu dem Zeitpunkt, die das Cmdlet ausgeführt wird. Es impliziert nicht, dass der zurückgegebene Status während bleibt unverändert anschließend. Insbesondere wird "Endzustand" weiterhin nur enthalten, wenn P1 keine Änderungen generiert, nachdem Sie das Cmdlet ausgeführt wird. Dies gilt im Fall von Failover P1 zu P2 nach P1 als Teil der Ausführungslogik **Invoke-CsPoolfailover** in den schreibgeschützten Modus befindet.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Zum Abrufen von Informationen zur sicherungsbeziehung für einen bestimmten pool

Führen Sie das folgende Cmdlet aus:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>So erzwingen Sie eine Synchronisierung

Führen Sie das folgende Cmdlet aus:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Wiederherstellen von konferenzinhalten mithilfe des Sicherungsdienstes 

In gespeicherte Konferenzinformationen in den Dateispeicher eines Front-End-Pools nicht mehr verfügbar ist, können Sie diese Informationen müssen wiederherstellen, sodass Benutzer im Pool verwaltet behalten ihre Konferenzdaten. Wenn Sie der Front-End-Pool, der Konferenzdaten verloren wurde mit einer anderen Front-End-Pool verbunden ist, können Sie den Sicherungsdienst zum Wiederherstellen der Daten verwenden.

Sie müssen auch für diese Aufgabe ausführen, wenn ein gesamtes Pools ausgefallen ist und Sie haben die Benutzer zu einem Sicherungspool Failover. Wenn diese Benutzer auf ihre ursprünglichen Pool wieder Failover ausgeführt werden, müssen Sie dieses Verfahren zum Kopieren von ihren konferenzinhalten wieder auf ihre ursprünglichen Pool auch verwenden.

Wird davon ausgegangen Sie, dass Pool1 Pool2 zugeordnet ist, und die Konferenzdaten in Pool1 verloren geht. Das folgende Cmdlet können zum Aufrufen des Sicherungsdienstes, um den Inhalt wiederherzustellen:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Wiederherstellen der Konferenz Inhalt kann je nach ihrer Größe einige Zeit dauern. Das folgende Cmdlet können Sie um den Prozessstatus zu überprüfen:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Der Vorgang ist abgeschlossen, wenn dieses Cmdlet gibt einen Wert für die Konferenz zu verwendenden Datenmoduls datenkonferenzmodul zurück.
