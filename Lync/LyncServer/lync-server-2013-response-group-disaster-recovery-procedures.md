---
title: Notfallwiederherstellungsverfahren für lync Server 2013 Reaktionsgruppen
description: Lync Server 2013 Notfallwiederherstellungsverfahren für Reaktionsgruppen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9021fb75c8f937bfd298578a9241d6256d26d85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563891"
---
# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Notfallwiederherstellungsverfahren für Reaktionsgruppen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Während der Failoverphase der Notfallwiederherstellung verbleiben die Reaktionsgruppen in mehreren Pools: Im primären Pool (der nicht verfügbar ist) und im Sicherungspool. Die Reaktionsgruppen weisen in beiden Pools den gleichen Namen und den gleichen Inhaber auf (den primären Pool), haben aber unterschiedliche übergeordnete Elemente. Während dieser Zeit funktionieren die Cmdlets für Reaktionsgruppen ein wenig anders. Verwenden Sie Parameter, wie dies im folgenden Verfahren dargelegt wird. Ausführliche Informationen zur Funktionsweise von Cmdlets während der failoverphase finden Sie unter NextHop Blog Artikel "lync Server 2013: Wiederherstellen von Reaktionsgruppen während der Notfallwiederherstellung" unter [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957) . Dieser Blog Artikel gilt auch für die veröffentlichte Version von lync Server 2013.

Führen Sie die Schritte im folgenden Verfahren aus, um eine Notfallwiederherstellung für lync Server Reaktionsgruppendienst vorzubereiten und durchzuführen.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Ausführen eines Failovers/Failbacks für Reaktionsgruppen

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie routinemäßige Sicherungen aus. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Importieren Sie während eines Ausfalls nach dem Failover zum Sicherungspool die Reaktionsgruppen zum Sicherungspool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Wenn Sie die Anwendungsebeneneinstellungen im Sicherungspool mit den Einstellungen des primären Pools ersetzen möchten, beziehen Sie den Parameter "–ReplaceExistingSettings" mit ein. Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie die Einstellungen im Sicherungspool nicht ersetzen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen des primären Pools verloren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for Response Group Disaster Recovery in lync Server 2013</A>.

    
    </div>

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
    
    Alternativ können Sie alle Reaktionsgruppen im Sicherungspool anzeigen, einschließlich der Gruppen, die sich im Besitz des primären bzw. des Sicherungspools befinden, indem Sie den Parameter "–ShowAll" anstelle von "–Owner" verwenden. Beispiel:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen entweder den Parameter "–ShowAll" oder "–Owner" verwenden. Wenn Sie keinen dieser Parameter verwenden, werden die von Ihnen in den Sicherungspool importierten Reaktionsgruppen nicht in den von den Cmdlets zurückgegebenen Ergebnissen angezeigt.

    
    </div>

5.  Stellen Sie sicher, dass der Import erfolgreich war, indem Sie einen Anruf zu einer importierten Reaktionsgruppe platzieren und gewährleisten, dass der Anruf ordnungsgemäß verarbeitet wird.

6.  Fordern Sie Agents an, die Mitglieder der formalen Agentgruppe sind, um sich in ihren Agentgruppen im Sicherungspool anzumelden.

7.  Verwalten und Ändern Sie die importierten Reaktionsgruppen wie gewöhnlich.
    
    <div>
    

    > [!IMPORTANT]  
    > Während sich die Reaktionsgruppen im Sicherungspool befinden, müssen Sie lync Server-Verwaltungsshell verwenden, um Sie zu verwalten. Sie können nicht lync Server-Systemsteuerung verwenden, um die Reaktionsgruppen zu verwalten, die Sie in den Sicherungspool importiert haben.

    
    </div>

8.  Exportieren Sie, nachdem der primäre Pool wiederhergestellt wurde und das Failback abgeschlossen ist, die Reaktionsgruppen des primären Pools, die in den Sicherungspool importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importieren Sie die Reaktionsgruppen zurück zum primären Pool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen Pool während der Wiederherstellung neu erstellen, und zwar entweder mit dem gleichen oder einem komplett anderen vollqualifizierten Domänennamen, müssen Sie weiterhin den Parameter "–OverwriteOwner" verwenden. Daumenregel: Sie können den Parameter "–OverwriteOwner" immer verwenden, wenn Sie Reaktionsgruppen zum primären Pool zurückimportieren.

    
    </div>
    
    Wenn Sie einen neuen Pool bereitgestellt haben (mit demselben oder einem anderen vollqualifizierten Domänennamen), um den primären Pool zu ersetzen und Sie die Anwendungsebeneneinstellungen des Sicherungspools für den neuen Pool verwenden möchten, beziehen Sie den Parameter "–ReplaceExistingSettings" mit ein. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie die Anwendungsebeneneinstellungen und die standardmäßige Wartemusik-Audiodatei für den neuen Pool nicht mit den Einstellungen des Sicherungspools ersetzen möchten, verwendet der neue Pool standardmäßige Anwendungsebeneneinstellungen.

    
    </div>

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

