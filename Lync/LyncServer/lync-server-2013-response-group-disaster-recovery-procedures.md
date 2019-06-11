---
title: 'Lync Server 2013: Verfahren für die Notfallwiederherstellung für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Verfahren für die Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Während der Failover-Phase der Disaster Recovery befinden sich die Reaktionsgruppen in mehreren Pools: im primären Pool (der nicht verfügbar ist) und im Sicherungspool. Die Antwortgruppen in beiden Pools haben denselben Namen und denselben Besitzer (den primären Pool), haben aber unterschiedliche übergeordnete Elemente. In dieser Zeit funktionieren die Cmdlets der Reaktionsgruppe etwas anders. Stellen Sie sicher, dass Sie die im folgenden Verfahren angegebenen Parameter verwenden. Ausführliche Informationen dazu, wie Cmdlets während der failoverphase funktionieren, finden Sie unter NextHop-Blog Artikel "lync Server 2013: Wiederherstellen von [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)Reaktionsgruppen während der Disaster Recovery" unter. Dieser Blog Artikel bezieht sich auch auf die veröffentlichte Version von lync Server 2013.

Führen Sie die Schritte in der folgenden Vorgehensweise aus, um die Disaster Recovery für den lync Server Response Group-Dienst vorzubereiten und durchzuführen.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>So führen Sie eine Failover-und Failback-Reaktionsgruppe aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie regelmäßig Sicherungen durch. Geben Sie in der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Importieren Sie bei einem Ausfall nach einem Failover zum Sicherungspool die Antwortgruppen in den Sicherungspool. Geben Sie in der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Wenn Sie die Einstellungen auf Anwendungsebene im Sicherungspool durch die Einstellungen des primären Pools ersetzen möchten, schließen Sie den Parameter – ReplaceExistingSettings ein. Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie die Einstellungen im Sicherungspool nicht ersetzen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen des primären Pools verloren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planen der Disaster Recovery einer Reaktionsgruppe in lync Server 2013</A>.

    
    </div>

4.  Überprüfen Sie, ob der Import erfolgreich war, indem Sie die importierten Antwortgruppen anzeigen. Die importierten Antwortgruppen sind weiterhin im Besitz des primären Pools. Gehen Sie wie folgt vor:
    
      - Zeigen Sie alle Workflows im Sicherungspool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle Workflows des primären Pools enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Zeigen Sie alle Warteschlangen im Sicherungspool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle primären Pool Warteschlangen enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Zeigen Sie alle Agentengruppen im Sicherungspool an, die dem primären Pool gehören, und überprüfen Sie, ob alle Gruppen des primären Pool-Agents enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Zeigen Sie alle Geschäftszeiten im Backup-Pool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle Geschäftsstunden des primären Pools enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Zeigen Sie alle Feiertagssätze im Sicherungspool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle Feiertagssätze des primären Pools enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Beispiel:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Sie können aber auch alle Antwortgruppen im Sicherungspool anzeigen, einschließlich derer im Besitz des primären Pools und der Besitzer des Sicherungs Pools, indem Sie den Parameter – ShowAll anstelle des Parameters-Owner verwenden. Beispiel:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen entweder den-ShowAll-Parameter oder den-owner-Parameter verwenden. Wenn Sie keinen dieser Parameter verwenden, werden die Antwortgruppen, die Sie in den Sicherungspool importiert haben, nicht in den von den Cmdlets zurückgegebenen Ergebnissen aufgelistet.

    
    </div>

5.  Überprüfen Sie, ob der Import erfolgreich war, indem Sie eine importierte Antwortgruppe anrufen und überprüfen, ob der Anruf richtig gehandhabt wurde.

6.  Anfordern von Agents, die Mitglieder von formellen Agentengruppen sind, um sich bei ihren Agentengruppen im Sicherungspool anzumeldet.

7.  Verwalten und ändern Sie die importierten Antwortgruppen wie gewohnt.
    
    <div>
    

    > [!IMPORTANT]  
    > Während sich die Antwortgruppen im Sicherungspool befinden, müssen Sie Sie mithilfe der lync Server-Verwaltungsshell verwalten. Sie können die lync Server-Systemsteuerung nicht zum Verwalten der Reaktionsgruppen verwenden, die Sie in den Sicherungspool importiert haben.

    
    </div>

8.  Nachdem der primäre Pool wiederhergestellt wurde und das Failback abgeschlossen ist, exportieren Sie die primären Pool Antwortgruppen, die in den Sicherungspool importiert wurden. Geben Sie in der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importieren Sie die Antwortgruppen zurück in den primären Pool. Geben Sie in der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie während der Wiederherstellung einen Pool neu erstellen, ob mit dem gleichen oder einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN), müssen Sie den Parameter – OverwriteOwner verwenden. Als Faustregel können Sie immer den – OverwriteOwner-Parameter verwenden, wenn Sie Antwortgruppen zurück in den primären Pool importieren.

    
    </div>
    
    Wenn Sie einen neuen Pool (mit demselben oder einem anderen FQDN) bereitgestellt haben, um den primären Pool zu ersetzen, und Sie die Einstellungen auf Anwendungsebene aus dem Sicherungspool für den neuen Pool verwenden möchten, schließen Sie den Parameter – ReplaceExistingSettings ein. Geben Sie in der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie die Einstellungen auf Anwendungsebene und die Standard-Musikdatei für den neuen Pool nicht durch die Einstellungen aus dem Sicherungspool ersetzen möchten, verwendet der neue Pool die Standardeinstellungen auf Anwendungsebene.

    
    </div>

10. Überprüfen Sie, ob der Import zurück in den primären Pool erfolgreich war, indem Sie die Konfiguration der importierten Reaktionsgruppe anzeigen. Gehen Sie wie folgt vor:
    
      - Zeigen Sie alle Workflows im primären Pool an, und überprüfen Sie, ob alle importierten Workflows enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Warteschlangen im primären Pool an, und überprüfen Sie, ob alle importierten Warteschlangen enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Agentengruppen im primären Pool an, und überprüfen Sie, ob alle importierten Agentengruppen enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Geschäftszeiten im primären Pool an, und überprüfen Sie, ob alle importierten Geschäftszeiten enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Zeigen Sie alle Feiertagssätze im primären Pool an, und überprüfen Sie, ob alle importierten Feiertagssätze enthalten sind. Geben Sie in der Befehlszeile Folgendes ein:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Beispiel:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Überprüfen Sie, ob der Import erfolgreich war, indem Sie eine importierte Antwortgruppe anrufen und überprüfen, ob der Anruf richtig gehandhabt wurde.

12. Optional können Sie die Antwortgruppen entfernen, die im Besitz des primären Pools aus dem Sicherungspool sind. Geben Sie in der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt und dann aus dem Sicherungspool entfernt.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

