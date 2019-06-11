---
title: 'Lync Server 2013: Konfigurieren und Überwachen des Sicherungsdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Konfigurieren und Überwachen des Sicherungsdiensts in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Sie können die folgenden Befehle der lync Server-Verwaltungsshell verwenden, um den Sicherungsdienst zu konfigurieren und zu überwachen.

<div>


> [!NOTE]  
> Die Gruppe RTCUniversalServerAdmins ist die einzige Gruppe, die über die standardmäßige Berechtigung zum Ausführen von <STRONG>Get-CsBackupServiceStatus</STRONG> verfügt. Wenn Sie dieses Cmdlet verwenden möchten, melden Sie sich als Mitglied dieser Gruppe an. Oder Sie können anderen Gruppen (beispielsweise CSAdministrator) mithilfe des Cmdlets " <STRONG>Satz-CsBackupServiceConfiguration</STRONG> " Zugriff auf diesen Befehl gewähren.



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>So zeigen Sie die Konfiguration des Sicherungsdiensts an

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceConfiguration

Der Standardwert für SyncInterval beträgt zwei Minuten.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>So stellen Sie das Synchronisierungsintervall für den Sicherungsdienst ein

Führen Sie das folgende Cmdlet aus:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Im folgenden Beispiel wird das Intervall auf drei Minuten festgelegt.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Obwohl Sie mit diesem Cmdlet das Standard Synchronisierungsintervall für den Sicherungsdienst ändern können, sollten Sie dies nicht tun, es sei denn, dies ist unbedingt erforderlich, da das Synchronisierungsintervall große Auswirkungen auf die Leistung des Sicherungsdiensts und auf das Recovery Point-Ziel (RPO) hat.



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>So rufen Sie den Sicherungsdienst Status für einen bestimmten Pool ab

Führen Sie das folgende Cmdlet aus:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> Der Synchronisierungsstatus des Sicherungsdiensts wird unidirektional von einem Pool (P1) zu seinem Sicherungspool (P2) definiert. Der Synchronisierungsstatus von P1 zu P2 kann von P2 zu P1 unterschiedlich sein. Bei P1 bis P2 befindet sich der Sicherungsdienst in einem "stabilen" Zustand, wenn alle Änderungen, die in P1 vorgenommen wurden, innerhalb des Synchronisierungsintervalls vollständig auf P2 repliziert werden. Es befindet sich im "endgültigen" Zustand, wenn keine weiteren Änderungen von P1 zu P2 synchronisiert werden. Beide Zustände deuten auf eine Momentaufnahme des Sicherungsdiensts zu dem Zeitpunkt hin, zu dem das Cmdlet ausgeführt wird. Das bedeutet nicht, dass der zurückgegebene Zustand unverändert bleibt. Insbesondere bleibt der Zustand "Final" weiterhin nur dann bestehen, wenn P1 nach der Ausführung des Cmdlets keine Änderungen generiert. Dies gilt im Fall eines Failovers von P1 auf P2, nachdem P1 als Teil der Ausführungslogik <STRONG>Invoke-CsPoolfailover</STRONG> in den schreibgeschützten Modus versetzt wurde.



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>So erhalten Sie Informationen zur Sicherungsbeziehung für einen bestimmten Pool

Führen Sie das folgende Cmdlet aus:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>So erzwingen Sie eine Synchronisierung des Sicherungsdiensts

Führen Sie das folgende Cmdlet aus:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

