---
title: Verschieben von Reaktionsgruppen in einen neuen Pool
TOCTitle: Verschieben von Reaktionsgruppen in einen neuen Pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205298(v=OCS.15)
ms:contentKeyID: 49295591
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben von Reaktionsgruppen in einen neuen Pool

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In Lync Server 2013 werden neue Cmdlets unterstützt, um Reaktionsgruppen zwischen Pools zu verschieben, selbst wenn der vollqualifizierte Domänenname (Fully Qualified Domain Dame, FQDN) nicht identisch ist.

Führen Sie die Schritte des folgenden Verfahrens aus, um Reaktionsgruppen von einem Front-End-Pool in einen Front-End-Pool mit einem unterschiedlichen FQDN zu verschieben.


> [!NOTE]
> In einer Koexistenzumgebung können Sie Reaktionsgruppen nur zwischen Lync Server 2013-Front-End-Pools verschieben.



## So verschieben Sie Reaktionsgruppen in einen Pool mit einem unterschiedlichen FQDN

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Exportieren Sie die Reaktionsgruppen im Quellpool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Geben Sie den –RemoveExportedConfiguration-Parameter an, um die Reaktionsgruppen während des Exports aus dem Quellpool zu entfernen. Beispiel:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importieren Sie die Reaktionsgruppen in den Zielpool, und weisen Sie den Zielpool als neuen Besitzer zu. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Wenn Sie auch die Einstellungen auf Anwendungsebene der Reaktionsgruppe aus dem Quellpool in den Zielpool kopieren möchten, geben Sie den –ReplaceExistingSettings-Parameter an. Pro Pool kann nur ein Satz von Einstellungen auf Anwendungsebene definiert werden. Falls Sie die Einstellungen auf Anwendungsebene aus dem Quellpool in den Zielpool kopieren, werden die Einstellungen für den Zielpool durch die Einstellungen aus dem Quellpool ersetzt. Falls Sie die Einstellungen auf Anwendungsebene nicht aus dem Quellpool kopieren, gelten die vorhandenen Einstellungen im Zielpool für die importierten Reaktionsgruppen.
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingSettings
    

    > [!NOTE]
    > Zu den Einstellungen auf Anwendungsebene gehören die Standardkonfiguration für die Musikeinspielung in der Warteschleife, die Standardaudiodatei für die Musikeinspielung in der Warteschleife, die Toleranzperiode für den Rückruf bei Halten des Agents sowie die Anrufkontextkonfiguration. Zum Anzeigen dieser Konfigurationseinstellungen führen Sie das <STRONG>Get-CsRgsConfiguration</STRONG>-Cmdlet aus. Ausführliche Informationen zu diesem Cmdlet finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.



4.  Überprüfen Sie wie folgt, ob der Import erfolgreich ausgeführt wurde, indem Sie die importierte Reaktionsgruppenkonfiguration anzeigen:
    
      - Überprüfen Sie, ob alle Workflows importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Überprüfen Sie, ob alle Warteschlangen importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Überprüfen Sie, ob alle Agentgruppen importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Überprüfen Sie, ob alle Geschäftszeiten importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Überprüfen Sie, ob alle Feiertagssätze importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Überprüfen Sie, ob erfolgreich importiert wurde, indem Sie eine der Reaktionsgruppen anrufen und prüfen, ob der Anruf ordnungsgemäß abgewickelt wird.

6.  Fordern Sie Agents, die Mitglieder von formellen Agentgruppen sind, auf, sich bei ihren Agentgruppen im Zielpool anzumelden.

7.  Falls Sie zuvor die Reaktionsgruppen nicht aus dem Quellpool entfernt haben, entfernen Sie nun die Reaktionsgruppen aus dem Quellpool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

