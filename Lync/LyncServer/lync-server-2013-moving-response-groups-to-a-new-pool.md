---
title: 'Lync Server 2013: Verschieben von Reaktionsgruppen in einen neuen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562d519e278096acf589482124eeb9cdf7ebf189
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Verschieben von Reaktionsgruppen in einen neuen Pool in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

In lync Server 2013 wird die Unterstützung neuer Cmdlets für das Verschieben von Reaktionsgruppen von einem Pool in einen anderen Pool eingeführt, auch wenn der vollqualifizierte Domänenname (FQDN) unterschiedlich ist.

Führen Sie die Schritte im folgenden Verfahren aus, um Reaktionsgruppen von einem Front-End-Pool in eine andere Front-End-Pool mit einem anderen FQDN zu verlagern.

<div>


> [!NOTE]  
> In einer Umgebung mit Koexistenz können Sie Reaktionsgruppen nur zwischen lync Server 2013&nbsp;-Front-End-Pools verlagern.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>So verschieben Sie Reaktionsgruppen in einen Pool mit einem unterschiedlichen FQDN

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Exportieren Sie die Reaktionsgruppen im Quellpool. Geben Sie an der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Geben Sie den –RemoveExportedConfiguration-Parameter an, um die Reaktionsgruppen während des Exports aus dem Quellpool zu entfernen. Beispiel:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importieren Sie die Reaktionsgruppen in den Zielpool, und weisen Sie den Zielpool als neuen Besitzer zu. Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Wenn Sie auch die Einstellungen auf Reaktionsgruppenanwendung Ebene aus dem Quell Pool in den Ziel Pool kopieren möchten, schließen Sie den Parameter – ReplaceExistingRgsSettings ein. Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren. Wenn Sie die Einstellungen auf Anwendungsebene aus dem Quell Pool in den Ziel Pool kopieren, ersetzen die Einstellungen aus dem Quell Pool die Einstellungen für den Ziel Pool. Wenn Sie die Einstellungen auf Anwendungsebene nicht aus dem Quell Pool kopieren, gelten die vorhandenen Einstellungen aus dem Ziel Pool für die importierten Reaktionsgruppen.
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Zu den Einstellungen auf Anwendungsebene gehören die Standardkonfiguration für die Musikeinspielung in der Warteschleife, die Standardaudiodatei für die Musikeinspielung in der Warteschleife, die Toleranzperiode für den Rückruf bei Halten des Agents sowie die Anrufkontextkonfiguration. Zum Anzeigen dieser Konfigurationseinstellungen führen Sie das <STRONG>Get-CsRgsConfiguration</STRONG>-Cmdlet aus. Ausführliche Informationen zu diesem Cmdlet finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.

    
    </div>

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

</div>

</div>

<span> </span>

</div>

</div>

</div>

