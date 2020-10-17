---
title: 'Lync Server 2013: Backup-Voraussetzungen für das Failover von ABC-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0607a0ddc2a1b2a8249135fa1256f2cb706a250a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527032"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Sicherungs Voraussetzungen für das Failover von ABC-Pools in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-26_

Um den größtmöglichen Nutzen aus dem Failover-Verfahren für das ABC-Pool zu ziehen, müssen Sie vor dem Ausfall und dem Failover bestimmte Sicherungen durchführen:

  - Sie müssen regelmäßig die LIS-Konfigurationsdaten (Location Information Service) aus Pool A mithilfe des **Export-CsLISConfiguration-** Cmdlets sichern.
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Sie müssen die Konfigurationsdaten der Reaktionsgruppe in Pool A mithilfe des Cmdlets **Export-CsRgsConfiguration** regelmäßig sichern.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    Im Allgemeinen wird empfohlen, tägliche Sicherungen durchzuführen, wenn jedoch ein hohes Umfang an Änderungen vorliegt, sollten Sie häufiger Sicherungen planen. Die Menge an Informationen, die Sie im Falle eines Notfalls verlieren können, hängt von der Häufigkeit Ihrer Sicherungen sowie von der Häufigkeit und dem Umfang der Änderungen ab.
    
    In der Reaktionsgruppenanwendung kann nur eine Gruppe von Einstellungen auf Anwendungsebene pro Pool gespeichert werden. Auf diese Einstellungen kann über die Cmdlets **Get-CsRgsConfiguration** zugegriffen werden. Die Einstellungen umfassen die standardmäßige Music-on-Hold-Konfiguration, die standardmäßige Music-on-Hold-Audiodatei, die Kulanzzeit für den Agent-Rückruf und die Konfiguration des Anruf Kontexts. Diese Einstellungen können über das **Import-CsRgsConfiguration-** Cmdlet mithilfe des **ReplaceExistingSettings** -Parameters von einem Pool an einen anderen übertragen werden, aber mit diesem Vorgang werden alle Einstellungen auf Anwendungsebene im Ziel Pool außer Kraft gesetzt.
    
    <div>
    

    > [!TIP]  
    > Bewahren Sie an einem separaten Speicherort eine Sicherungskopie aller Original-Audiodateien auf, die zum Konfigurieren des Reaktionsgruppenanwendung verwendet wurden (also alle Aufzeichnungen oder Musikdateien, die in einem Archiv gespeichert sind).

    
    </div>
    
    Wenn Sie über benutzerdefinierte Musikarchiv Dateien verfügen, die in einem Pool für das Parken von Anrufen hochgeladen wurden, sollten Sie eine Kopie davon an einem anderen Speicherort aufbewahren. Diese Dateien werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > Das Anwendung zum Parken von anrufen kann nur einen Einstellungssatz und eine benutzerdefinierte Audiodatei pro Pool speichern. Auf diese Einstellungen kann über das Cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> zugegriffen werden. Da der Notfall Wiederherstellungsmechanismus für das Parken von Anrufen auf dem Anwendung zum Parken von Anrufen des Sicherungs Pools beruht, werden die Einstellungen des primären Pools nicht gesichert oder erhalten, wenn ein Notfall auftritt. Wenn der primäre Pool verloren geht, können diese Einstellungen nicht wiederhergestellt werden, und wenn ein neuer Pool bereitgestellt wird, um den primären Pool zu ersetzen, müssen die Einstellungen für das Parken von Anrufen und alle angepassten Musikdateien, die in der Warteschleife gespeichert sind, neu konfiguriert werden.

    
    </div>

  - Wenn Sie Ankündigungen als Teil des Voice-Features für nicht zugewiesene Nummern konfigurieren, wird empfohlen, dass Sie an einem anderen Speicherort eine Kopie jeder Originalaudiodatei aufbewahren, die bei der Erstkonfiguration verwendet wurde. Wenn Sie dies nicht getan haben, können Sie eine Kopie der konfigurierten Audiodateien im Dateispeicher des Servers oder Pools abrufen, in den die Audiodateien importiert wurden. Diese Dateien werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden. Wenn Sie alle Audiodateien kopieren möchten, die zum Konfigurieren der VoIP-Funktion für nicht zugewiesene Nummern aus dem Dateispeicher eines Servers oder Pools verwendet werden, verwenden Sie Folgendes:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Wenn Sie Überwachungs-und Archivierungsdatenbanken in einem Pool haben, sollten Sie SQL Server-Verwaltungstools verwenden, um Sie zu sichern. Im ABC-Failover-Verfahren werden Überwachungs-und Archivierungsdatenbanken nicht beibehalten, wenn Sie in Pool A zusammengefasst werden, da diese Datenbanken nicht über lync Server Sicherungsdienst gesichert werden.

</div>

<span> </span>

</div>

</div>

</div>

