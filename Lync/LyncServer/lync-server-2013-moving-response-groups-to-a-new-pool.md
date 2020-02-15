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
ms.openlocfilehash: 41d739ae79998fe3dbf3acadba2b2f480a960a30
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="4a025-102">Verschieben von Reaktionsgruppen in einen neuen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a025-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a025-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4a025-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4a025-104">In lync Server 2013 wird die Unterstützung neuer Cmdlets für das Verschieben von Reaktionsgruppen von einem Pool in einen anderen Pool eingeführt, auch wenn der vollqualifizierte Domänenname (FQDN) unterschiedlich ist.</span><span class="sxs-lookup"><span data-stu-id="4a025-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="4a025-105">Führen Sie die Schritte im folgenden Verfahren aus, um Reaktionsgruppen von einem Front-End-Pool in eine andere Front-End-Pool mit einem anderen FQDN zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="4a025-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a025-106">In einer Umgebung mit Koexistenz können Sie Reaktionsgruppen nur zwischen lync Server 2013&nbsp;-Front-End-Pools verlagern.</span><span class="sxs-lookup"><span data-stu-id="4a025-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="4a025-107">So verschieben Sie Reaktionsgruppen in einen Pool mit einem unterschiedlichen FQDN</span><span class="sxs-lookup"><span data-stu-id="4a025-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="4a025-108">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="4a025-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4a025-p101">Exportieren Sie die Reaktionsgruppen im Quellpool. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p101">Export the response groups in the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="4a025-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4a025-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="4a025-p102">Geben Sie den –RemoveExportedConfiguration-Parameter an, um die Reaktionsgruppen während des Exports aus dem Quellpool zu entfernen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4a025-p102">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter. For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="4a025-p103">Importieren Sie die Reaktionsgruppen in den Zielpool, und weisen Sie den Zielpool als neuen Besitzer zu. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p103">Import the response groups to the destination pool and assign the destination pool as the new owner. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="4a025-116">Wenn Sie auch die Einstellungen auf Reaktionsgruppenanwendung Ebene aus dem Quell Pool in den Ziel Pool kopieren möchten, schließen Sie den Parameter – ReplaceExistingRgsSettings ein.</span><span class="sxs-lookup"><span data-stu-id="4a025-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="4a025-117">Pro Pool können Sie nur eine Gruppe von Einstellungen auf Anwendungsebene definieren.</span><span class="sxs-lookup"><span data-stu-id="4a025-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="4a025-118">Wenn Sie die Einstellungen auf Anwendungsebene aus dem Quell Pool in den Ziel Pool kopieren, ersetzen die Einstellungen aus dem Quell Pool die Einstellungen für den Ziel Pool.</span><span class="sxs-lookup"><span data-stu-id="4a025-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="4a025-119">Wenn Sie die Einstellungen auf Anwendungsebene nicht aus dem Quell Pool kopieren, gelten die vorhandenen Einstellungen aus dem Ziel Pool für die importierten Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="4a025-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="4a025-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4a025-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a025-121">Zu den Einstellungen auf Anwendungsebene gehören die Standardkonfiguration für die Musikeinspielung in der Warteschleife, die Standardaudiodatei für die Musikeinspielung in der Warteschleife, die Toleranzperiode für den Rückruf bei Halten des Agents sowie die Anrufkontextkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4a025-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="4a025-122">Zum Anzeigen dieser Konfigurationseinstellungen führen Sie das <STRONG>Get-CsRgsConfiguration</STRONG>-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="4a025-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="4a025-123">Ausführliche Informationen zu diesem Cmdlet finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="4a025-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="4a025-124">Überprüfen Sie wie folgt, ob der Import erfolgreich ausgeführt wurde, indem Sie die importierte Reaktionsgruppenkonfiguration anzeigen:</span><span class="sxs-lookup"><span data-stu-id="4a025-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="4a025-p106">Überprüfen Sie, ob alle Workflows importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p106">Verify that all the workflows were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="4a025-p107">Überprüfen Sie, ob alle Warteschlangen importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p107">Verify that all the queues were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="4a025-p108">Überprüfen Sie, ob alle Agentgruppen importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p108">Verify that all the agent groups were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="4a025-p109">Überprüfen Sie, ob alle Geschäftszeiten importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p109">Verify that all the hours of business were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="4a025-p110">Überprüfen Sie, ob alle Feiertagssätze importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p110">Verify that all the holiday sets were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="4a025-135">Überprüfen Sie, ob erfolgreich importiert wurde, indem Sie eine der Reaktionsgruppen anrufen und prüfen, ob der Anruf ordnungsgemäß abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="4a025-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="4a025-136">Fordern Sie Agents, die Mitglieder von formellen Agentgruppen sind, auf, sich bei ihren Agentgruppen im Zielpool anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a025-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="4a025-p111">Falls Sie zuvor die Reaktionsgruppen nicht aus dem Quellpool entfernt haben, entfernen Sie nun die Reaktionsgruppen aus dem Quellpool. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="4a025-p111">If you did not previously remove response groups from the source pool, remove the response groups from the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="4a025-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4a025-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

