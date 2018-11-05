---
title: Sicherungsvoraussetzungen für ein ABC Pool-Failover
TOCTitle: Sicherungsvoraussetzungen für ein ABC Pool-Failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945634(v=OCS.15)
ms:contentKeyID: 52056370
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sicherungsvoraussetzungen für ein ABC Pool-Failover

 

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Um alle Vorteile des ABC-Poolfailoververfahrens zu nutzen, müssen Sie vor dem Auftreten des Notfalls und des Failovers bestimmte Sicherungen durchführen:

  - Sie müssen die LIS (Location Information Service)-Konfigurationsdaten in Pool A regelmäßig mithilfe des Cmdlets **Export-CsLISConfiguration** sichern.
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Sie müssen die Reaktionsgruppen-Konfigurationsdaten in Pool A regelmäßig mithilfe des Cmdlets **Export-CsRgsConfiguration** sichern.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    Im Allgemeinen wird empfohlen, täglich eine Sicherung anzulegen. Wenn jedoch große Mengen von Daten innerhalb einer kurzen Zeit geändert werden, sollten Sie häufigere Sicherungen ansetzen. Die Menge an Informationen, die bei einem Notfall verloren gehen kann, hängt von der Häufigkeit Ihrer Sicherungen sowie von der Häufigkeit und Menge der Änderungen ab.
    
    Die Reaktionsgruppenanwendung kann nur einen Satz von Einstellungen auf Anwendungsebene pro Pool speichern. Der Zugriff auf diese Einstellungen erfolgt über die **Get-CsRgsConfiguration**-Cmdlets. Die Einstellungen umfassen die Standardkonfiguration für Wartemusik, die Standardaudiodatei für Wartemusik, die Kulanzfrist für Agentrückrufe und die Anrufkontextkonfiguration. Diese Einstellungen können aus einem Pool in einen anderen übertragen werden, indem das Cmdlet **Import-CsRgsConfiguration** mit dem Parameter **ReplaceExistingSettings** ausgeführt wird. Dieser Vorgang setzt jedoch nur alle Einstellungen auf Anwendungsebene im Zielpool außer Kraft.
    

    > [!TIP]
    > Bewahren Sie an einem separaten Standort eine Sicherungskopie aller ursprünglichen Audiodateien auf, die zum Konfigurieren der Reaktionsgruppenanwendung verwendet wurden (d.&nbsp;h alle Aufnahmen oder Wartemusikdateien).

    
    Wenn Sie über angepasste Wartemusikdateien verfügen, die für das Parken von Anrufen in einem Pool hochgeladen wurden, sollten Sie eine Kopie dieser Dateien an einem anderen Standort aufbewahren. Diese Dateien werden nicht im Rahmen des Lync Server 2013-Prozesses für die Notfallwiederherstellung gesichert und gehen folglich verloren, wenn die in den Pool hochgeladenen Dateien beschädigt oder gelöscht werden.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    

    > [!NOTE]
    > In der Anwendung zum Parken von Anrufen kann nur ein Satz von Einstellungen und eine angepasste Wartemusik-Audiodatei pro Pool gespeichert werden. Der Zugriff auf diese Einstellungen erfolgt über das Cmdlet <STRONG>Get-CsCpsConfiguration</STRONG>. Da der Notfallwiederherstellungsmechanismus für das Parken von Anrufen auf der Anwendung zum Parken von Anrufen des Sicherungspools basiert, werden die Einstellungen des primären Pools bei einem Notfall nicht gesichert oder beibehalten. Bei einem Verlust des primären Pools können diese Einstellungen nicht wiederhergestellt werden. Wenn ein neuer Pool als Ersatz für den primären Pool bereitgestellt wird, müssen die Einstellungen für das Parken von Anrufen und angepasste Wartemusik-Audiodateien erneut konfiguriert werden.



  - Wenn Sie Ankündigungen als Teil der VoIP-Funktion für nicht zugewiesene Nummern konfigurieren, wird empfohlen, eine Kopie der ursprünglichen Audiodatei, die bei der Erstkonfiguration verwendet wurde, an einem anderen Standort aufzubewahren. Andernfalls können Sie eine Kopie der konfigurierten Audiodateien aus dem Dateispeicher auf dem Server oder im Pool abrufen, in den die Audiodateien importiert wurden. Diese Dateien werden nicht im Rahmen des Lync Server 2013-Prozesses für die Notfallwiederherstellung gesichert und gehen folglich verloren, wenn die in den Pool hochgeladenen Dateien beschädigt oder gelöscht werden. Zum Kopieren aller Audiodateien, die zum Konfigurieren der VoIP-Funktion für nicht zugewiesene Nummern verwendet wurden, verwenden Sie Folgendes:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Wenn Sie über Überwachungs- und Archivierungsdatenbanken in einem Pool verfügen, sollten Sie für deren Sicherung SQL Server-Verwaltungstools verwenden. Beim ABC-Failoververfahren werden Überwachungs- und Archivierungsdatenbanken nicht beibehalten, wenn sie in Pool A verbunden sind, da diese Datenbanken nicht über den Lync Server-Sicherungsdienst gesichert werden.

