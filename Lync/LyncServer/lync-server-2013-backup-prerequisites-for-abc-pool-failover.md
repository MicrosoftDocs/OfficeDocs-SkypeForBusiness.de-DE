---
title: 'Lync Server 2013: Backup-Voraussetzungen für ABC-Pool-Failover'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Backup-Voraussetzungen für ABC-Pool-Failover in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Um den größtmöglichen Nutzen aus der Verwendung des ABC-Pool-Failover-Verfahrens zu ziehen, müssen Sie bestimmte Sicherungen durchführen, bevor ein Notfall und ein Failover stattfinden:

  - Sie müssen die Konfigurationsdaten des Standort Informationsdiensts (Location Information Service, LIS) regelmäßig aus Pool A mithilfe des Cmdlets **Export-CsLISConfiguration** sichern.
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Sie müssen die Konfigurationsdaten der Reaktionsgruppe in Pool A regelmäßig mithilfe des Cmdlets **Export-CsRgsConfiguration** sichern.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    Im Allgemeinen empfehlen wir, dass Sie tägliche Sicherungen durchführen, aber wenn Sie über eine große Anzahl von Änderungen verfügen, möchten Sie möglicherweise häufigere Sicherungen planen. Die Menge der Informationen, die Sie bei einem Notfall verlieren können, hängt von der Häufigkeit Ihrer Sicherungen sowie von der Häufigkeit und dem Umfang der Änderungen ab.
    
    Die reaktionsgruppenanwendung kann nur einen Satz von Einstellungen auf Anwendungsebene pro Pool speichern. Auf diese Einstellungen kann über die Cmdlets " **Get-CsRgsConfiguration** " zugegriffen werden. Zu den Einstellungen gehören die standardmäßige Musik-in-situ-Konfiguration, die standardmäßige Musik-in-Halt-Audiodatei, die Kulanzzeit für den Agenten-Rückruf und die Kontextkonfiguration des Anrufs. Diese Einstellungen können mithilfe des **ReplaceExistingSettings** -Parameters von einem Pool zu einem anderen über das Cmdlet " **Import-CsRgsConfiguration** " übertragen werden, aber dieser Vorgang setzt alle Einstellungen auf Anwendungsebene im Ziel außer Kraft. Pool.
    
    <div>
    

    > [!TIP]  
    > Bewahren Sie an einem separaten Speicherort eine Sicherungskopie aller Original Audiodateien auf, die zum Konfigurieren der Antwortgruppen Anwendung verwendet wurden (also alle Aufzeichnungen oder Musik-in-halten-Dateien).

    
    </div>
    
    Wenn Sie benutzerdefinierte Musik-in-Warte-Dateien haben, die in einem Pool für den Anruf Park hochgeladen wurden, sollten Sie eine Kopie dieser Dateien an einem anderen Speicherort speichern. Diese Dateien werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > Die Anwendung Parken kann nur einen Satz von Einstellungen und eine angepasste Musik-auf-halten-Audiodatei pro Pool speichern. Auf diese Einstellungen kann über das Cmdlet " <STRONG>Get-CsCpsConfiguration</STRONG> " zugegriffen werden. Da der Disaster Recovery-Mechanismus für Call Park auf der Anwendung Parken des Backup-Pools basiert, werden die Einstellungen des primären Pools nicht gesichert, wenn ein Notfall eintritt. Wenn der primäre Pool verloren geht, können diese Einstellungen nicht wiederhergestellt werden, und wenn ein neuer Pool zum Ersetzen des primären Pools bereitgestellt wird, müssen die Einstellungen für den Anruf Park und alle angepassten Musik-in-halten-Audiodateien neu konfiguriert werden.

    
    </div>

  - Wenn Sie Ankündigungen als Teil des Sprachfeatures "nicht zugewiesene Rufnummern" konfigurieren, empfehlen wir, dass Sie an einem anderen Speicherort eine Kopie einer beliebigen Originalaudiodatei beibehalten, die während der Erstkonfiguration verwendet wurde. Wenn Sie dies nicht tun, können Sie eine Kopie der konfigurierten Audiodateien im Dateispeicher des Servers oder Pools abrufen, in den die Audiodateien importiert wurden. Diese Dateien werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden. Verwenden Sie Folgendes, um alle Audiodateien zu kopieren, die zum Konfigurieren des Sprachfeatures "nicht zugewiesene Rufnummern" aus dem Dateispeicher eines Servers oder Pools verwendet werden:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Wenn Sie über Überwachungs-und Archivierungsdatenbanken in einem Pool verfügen, sollten Sie die SQL Server-Verwaltungstools verwenden, um Sie zu sichern. Bei der ABC-Failover-Prozedur werden Überwachungs-und Archivierungsdatenbanken nicht beibehalten, wenn Sie in Pool A zusammengefasst werden, da diese Datenbanken nicht über den lync Server-Sicherungsdienst gesichert werden.

</div>

<span> </span>

</div>

</div>

</div>

