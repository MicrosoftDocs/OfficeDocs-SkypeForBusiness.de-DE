---
title: 'Lync Server 2013: Verfahren für die Notfallwiederherstellung für Reaktionsgruppen'
TOCTitle: Verfahren für die Notfallwiederherstellung für Reaktionsgruppen
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205186(v=OCS.15)
ms:contentKeyID: 49295151
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verfahren für die Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Während der Failoverphase der Notfallwiederherstellung verbleiben die Reaktionsgruppen in mehreren Pools: Im primären Pool (der nicht verfügbar ist) und im Sicherungspool. Die Reaktionsgruppen weisen in beiden Pools den gleichen Namen und den gleichen Inhaber auf (den primären Pool), haben aber unterschiedliche übergeordnete Elemente. Während der Failoverphase zeigen die Reaktionsgruppe-Cmdlets ein leicht abweichendes Verhalten. Verwenden Sie Parameter, wie dies im folgenden Verfahren dargelegt wird. Genauere Informationen zur Funktionsweise von Cmdlets während der Failoverphase finden Sie im NextHop-Blogartikel "Lync Server 2013: Recovering Response Groups During Disaster Recovery" unter [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957). Dieser Blogartikel bezieht sich ebenfalls auf die die veröffentlichte Version von Lync Server 2013.

Verwenden Sie diese Schritte im folgenden Verfahren, um sich auf den Lync Server-Reaktionsgruppendienst vorzubereiten und eine Notfallwiederherstellung dafür vorzunehmen.

## Ausführen eines Failovers/Failbacks für Reaktionsgruppen

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie routinemäßige Sicherungen aus. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Importieren Sie während eines Ausfalls nach dem Failover zum Sicherungspool die Reaktionsgruppen zum Sicherungspool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Wenn Sie die Einstellungen auf Anwendungsebene im Sicherungspool durch die Einstellungen des primären Pools ersetzen möchten, fügen Sie den Parameter "-ReplaceExistingSettings" hinzu. Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    > [!CAUTION]  
	> Wenn Sie die Einstellungen im Sicherungspool nicht ersetzen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen des primären Pools verloren. Details sind <a href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planen der Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013</a> zu entnehmen.


4.  Stellen Sie sicher, dass der Import erfolgreich war, und zwar durch Anzeigen der importierten Reaktionsgruppen. Die importierten Reaktionsgruppen befinden sich weiterhin im Besitz des primären Pools. Führen Sie Folgendes aus:
    
      - Zeigen Sie alle Workflows im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Workflows des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Zeigen Sie alle Warteschlangen im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Warteschlangen des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Zeigen Sie alle Agentgruppen im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Agentgruppen des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Zeigen Sie alle Geschäftszeiten im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Geschäftszeiten des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Zeigen Sie alle Feiertagssätze im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Feiertagssätze des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Alternativ können Sie alle Reaktionsgruppen im Sicherungspool anzeigen, einschließlich der Gruppen, die sich im Besitz des primären bzw. des Sicherungspools befinden, indem Sie den Parameter "-ShowAll" anstelle von "-Owner" verwenden. Beispiel:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    

    > [!IMPORTANT]
    > Sie müssen entweder den Parameter "-ShowAll" oder "-Owner" verwenden. Wenn Sie keinen dieser Parameter verwenden, werden die von Ihnen in den Sicherungspool importierten Reaktionsgruppen nicht in den von den Cmdlets zurückgegebenen Ergebnissen angezeigt.



5.  Stellen Sie sicher, dass der Import erfolgreich war, indem Sie einen Anruf zu einer importierten Reaktionsgruppe platzieren und gewährleisten, dass der Anruf ordnungsgemäß verarbeitet wird.

6.  Fordern Sie Agents an, die Mitglieder der formalen Agentgruppe sind, um sich in ihren Agentgruppen im Sicherungspool anzumelden.

7.  Verwalten und Ändern Sie die importierten Reaktionsgruppen wie gewöhnlich.
    

    > [!IMPORTANT]
    > Wenn sich die Reaktionsgruppen im Sicherungspool befinden müssen Sie die Lync Server-Verwaltungsshell verwenden, um sie zu verwalten. Sie können Lync Server-Systemsteuerung nicht verwenden, um die Reaktionsgruppen zu verwalten, die Sie im Sicherungspool importiert haben.



8.  Exportieren Sie, nachdem der primäre Pool wiederhergestellt wurde und das Failback abgeschlossen ist, die Reaktionsgruppen des primären Pools, die in den Sicherungspool importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importieren Sie die Reaktionsgruppen zurück zum primären Pool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    

    > [!NOTE]
    > Wenn Sie einen Pool während der Wiederherstellung neu erstellen, und zwar entweder mit dem gleichen oder einem komplett anderen vollqualifizierten Domänennamen, müssen Sie den Parameter "-OverwriteOwner" verwenden. Daumenregel: Sie können den Parameter "-OverwriteOwner" immer verwenden, wenn Sie Reaktionsgruppen wieder in den primären Pool importieren.

    
    Wenn Sie einen neuen Pool bereitgestellt haben (mit demselben oder einem anderen vollqualifizierten Domänennamen), um den primären Pool zu ersetzen, und Sie die Anwendungsebeneneinstellungen des Sicherungspools für den neuen Pool verwenden möchten, fügen Sie den Parameter "-ReplaceExistingSettings" hinzu. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    

    > [!IMPORTANT]
    > Wenn Sie die Anwendungsebeneneinstellungen und die standardmäßige Wartemusik-Audiodatei für den neuen Pool nicht mit den Einstellungen des Sicherungspools ersetzen möchten, verwendet der neue Pool standardmäßige Anwendungsebeneneinstellungen.



10. Stellen Sie sicher, dass der Import zurück zum primären Tool erfolgreich war, indem Sie die importierte Reaktionsgruppenkonfiguration anzeigen. Führen Sie Folgendes aus:
    
      - Zeigen Sie alle Workflows im primären Pool an, und stellen Sie sicher, dass alle importierten Workflows enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Warteschlangen im primären Pool an, und stellen Sie sicher, dass alle Warteschlangen enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Agentgruppen im primären Pool an, und stellen Sie sicher, dass alle Agentgruppen enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Geschäftszeiten im primären Pool an, und stellen Sie sicher, dass alle Geschäftszeiten enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Feiertagssätze im primären Pool an, und stellen Sie sicher, dass alle Feiertagssätze enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Stellen Sie sicher, dass der Import erfolgreich war, indem Sie einen Anruf zu einer importierten Reaktionsgruppe platzieren und gewährleisten, dass der Anruf ordnungsgemäß verarbeitet wird.

12. Entfernen Sie optional die Reaktionsgruppen, die der primäre Pool besitzt, aus dem Sicherungspool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    

    > [!NOTE]
    > In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt und dann aus dem Sicherungspool entfernt.


