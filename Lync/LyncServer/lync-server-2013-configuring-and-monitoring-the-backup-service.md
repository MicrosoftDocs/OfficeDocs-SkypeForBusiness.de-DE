---
title: 'Lync Server 2013: Konfigurieren und Überwachen des Sicherungsdiensts'
description: 'Lync Server 2013: Konfigurieren und Überwachen des Sicherungsdiensts.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35302aeb430e8591babd88969d4c5c158c1ac0bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574641"
---
# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Konfigurieren und Überwachen des Sicherungsdiensts in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Sie können die folgenden lync Server-Verwaltungsshell Befehle verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.

<div>


> [!NOTE]  
> Die RTCUniversalServerAdmins-Gruppe ist die einzige Gruppe mit Berechtigungen zum standardmäßigen Ausführen von <STRONG>Get-CsBackupServiceStatus</STRONG> . Um dieses Cmdlet zu verwenden, melden Sie sich als Mitglied dieser Gruppe an. Sie können auch anderen Gruppen (beispielsweise CSAdministrator) Zugriff auf diesen Befehl gewähren, indem Sie das Cmdlet " <STRONG>csbackupserviceconfiguration"</STRONG> "verwenden.



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>So zeigen Sie die Sicherungsdienst Konfiguration an

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceConfiguration

Der Standardwert für SyncInterval ist zwei Minuten.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>So legen Sie das Synchronisierungsintervall für den Sicherungsdienst fest

Führen Sie das folgende Cmdlet aus:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Obwohl Sie dieses Cmdlet zum Ändern des standardmäßigen Synchronisierungsintervalls für den Sicherungsdienst verwenden können, sollten Sie dies nur tun, wenn dies unbedingt erforderlich ist, da das Synchronisierungsintervall große Auswirkungen auf die Leistung des Sicherungsdiensts und das Ziel des Wiederherstellungspunkts (RPO) hat.



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>So rufen Sie den Sicherungsdienst Status für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> Der Synchronisierungsstatus des Sicherungsdiensts wird von einem Pool (P1) auf den Sicherungspool (P2) unidirektional festgelegt. Der Synchronisierungsstatus von P1 bis P2 kann unterschiedlich sein als der von P2 bis P1. Bei P1 bis P2 befindet sich der Sicherungsdienst in einem "stationären" Zustand, wenn alle in P1 vorgenommenen Änderungen innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden. Es befindet sich im "endgültigen" Zustand, wenn keine Änderungen mehr von P1 zu P2 synchronisiert werden sollen. Beide Zustände deuten auf eine Momentaufnahme des Sicherungsdiensts zu dem Zeitpunkt hin, an dem das Cmdlet ausgeführt wird. Dies bedeutet nicht, dass der zurückgegebene Status wie im Anschluss bleibt. Insbesondere wird der Status "endgültig" nur dann beibehalten, wenn P1 nach dem Ausführen des Cmdlets keine Änderungen mehr generiert. Dies gilt für den Fall, dass P1 über bis P2 verfällt, nachdem P1 als Teil der <STRONG>Invoke-CsPoolfailover-</STRONG> Ausführungslogik in den schreibgeschützten Modus versetzt wurde.



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>So rufen Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>So erzwingen Sie die Synchronisierung eines Sicherungsdiensts

Führen Sie das folgende Cmdlet aus:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

