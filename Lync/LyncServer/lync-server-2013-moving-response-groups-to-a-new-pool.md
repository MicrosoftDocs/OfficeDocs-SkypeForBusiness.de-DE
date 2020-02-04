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
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Verschieben von Reaktionsgruppen in einen neuen Pool in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Lync Server 2013 führt eine neue Cmdlet-Unterstützung für das Verschieben von Reaktionsgruppen aus einem Pool in einen anderen Pool ein, selbst wenn der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) anders ist.

Führen Sie die Schritte in der folgenden Vorgehensweise aus, um Reaktionsgruppen aus einem Front-End-Pool in einen anderen Front-End-Pool mit einem anderen FQDN zu verschieben.

<div>


> [!NOTE]  
> In einer Koexistenz-Umgebung können Sie Reaktionsgruppen nur zwischen lync Server 2013&nbsp;-Front-End-Pools verschieben.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>So verschieben Sie Antwortgruppen in einen Pool mit einem anderen FQDN

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Exportieren Sie die Antwortgruppen im Quell Pool. Geben Sie in der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Wenn Sie die Antwortgruppen aus dem Quell Pool während des Exports entfernen möchten, schließen Sie den Parameter – RemoveExportedConfiguration ein. Beispiel:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importieren Sie die Antwortgruppen in den Ziel Pool, und weisen Sie den Ziel Pool als neuen Besitzer zu. Geben Sie in der Befehlszeile Folgendes ein:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Wenn Sie auch die Einstellungen für die Reaktionsgruppe auf Anwendungsebene aus dem Quell Pool in den Ziel Pool kopieren möchten, schließen Sie den Parameter – ReplaceExistingRgsSettings ein. Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren. Wenn Sie die Einstellungen auf Anwendungsebene aus dem Quell Pool in den Ziel Pool kopieren, ersetzen die Einstellungen des Quell Pools die Einstellungen für den Ziel Pool. Wenn Sie die Einstellungen auf Anwendungsebene nicht aus dem Quell Pool kopieren, gelten die vorhandenen Einstellungen aus dem Ziel Pool für die importierten Antwortgruppen.
    
    Beispiel:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Zu den Einstellungen auf Anwendungsebene gehören die standardmäßige Musik-in-situ-Konfiguration, die standardmäßige Musik-in-halten-Audiodatei, die Kulanzzeit für den Agenten-Rückruf und die Kontextkonfiguration des Anrufs. Führen Sie das Cmdlet " <STRONG>Get-CsRgsConfiguration</STRONG> " aus, um diese Konfigurationseinstellungen anzuzeigen. Details zu diesem Cmdlet finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.

    
    </div>

4.  Überprüfen Sie, ob der Import erfolgreich war, indem Sie die Konfiguration der importierten Reaktionsgruppe wie folgt anzeigen:
    
      - Überprüfen Sie, ob alle Workflows importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Überprüfen Sie, ob alle Warteschlangen importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Überprüfen Sie, ob alle Agentengruppen importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Überprüfen Sie, ob alle Geschäftszeiten importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Überprüfen Sie, ob alle Feiertagssätze importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Überprüfen Sie, ob der Import erfolgreich war, indem Sie eine der Antwortgruppen anrufen und überprüfen, ob der Anruf richtig gehandhabt wurde.

6.  Anfordern von Agents, die Mitglieder von formellen Agentengruppen sind, um sich bei ihren Agentengruppen im Ziel Pool anzumeldet.

7.  Wenn Sie die Antwortgruppen zuvor nicht aus dem Quell Pool entfernt haben, entfernen Sie die Antwortgruppen aus dem Quell Pool. Geben Sie in der Befehlszeile Folgendes ein:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Beispiel:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

