---
title: Notfallwiederherstellungsverfahren für lync Server 2013 Reaktionsgruppen
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
ms.openlocfilehash: 2ecd074254243629bbb3a6dc732b11a93cfebbe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="1e431-102">Notfallwiederherstellungsverfahren für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e431-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e431-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1e431-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1e431-104">Während der Failoverphase der Notfallwiederherstellung verbleiben die Reaktionsgruppen in mehreren Pools: Im primären Pool (der nicht verfügbar ist) und im Sicherungspool.</span><span class="sxs-lookup"><span data-stu-id="1e431-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="1e431-105">Die Reaktionsgruppen weisen in beiden Pools den gleichen Namen und den gleichen Inhaber auf (den primären Pool), haben aber unterschiedliche übergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="1e431-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="1e431-106">Während dieser Zeit funktionieren die Cmdlets für Reaktionsgruppen ein wenig anders.</span><span class="sxs-lookup"><span data-stu-id="1e431-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="1e431-107">Verwenden Sie Parameter, wie dies im folgenden Verfahren dargelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1e431-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="1e431-108">Ausführliche Informationen zur Funktionsweise von Cmdlets während der failoverphase finden Sie unter NextHop Blog Artikel "lync Server 2013: Wiederherstellen von [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957)Reaktionsgruppen während der Notfallwiederherstellung" unter.</span><span class="sxs-lookup"><span data-stu-id="1e431-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="1e431-109">Dieser Blog Artikel gilt auch für die veröffentlichte Version von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e431-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="1e431-110">Führen Sie die Schritte im folgenden Verfahren aus, um eine Notfallwiederherstellung für lync Server Reaktionsgruppendienst vorzubereiten und durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="1e431-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="1e431-111">Ausführen eines Failovers/Failbacks für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="1e431-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="1e431-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1e431-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1e431-p102">Führen Sie routinemäßige Sicherungen aus. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="1e431-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="1e431-p103">Importieren Sie während eines Ausfalls nach dem Failover zum Sicherungspool die Reaktionsgruppen zum Sicherungspool. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="1e431-p104">Wenn Sie die Anwendungsebeneneinstellungen im Sicherungspool mit den Einstellungen des primären Pools ersetzen möchten, beziehen Sie den Parameter "–ReplaceExistingSettings" mit ein. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1e431-120">Wenn Sie die Einstellungen im Sicherungspool nicht ersetzen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen des primären Pools verloren.</span><span class="sxs-lookup"><span data-stu-id="1e431-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="1e431-121">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for Response Group Disaster Recovery in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1e431-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="1e431-p106">Stellen Sie sicher, dass der Import erfolgreich war, und zwar durch Anzeigen der importierten Reaktionsgruppen. Die importierten Reaktionsgruppen befinden sich weiterhin im Besitz des primären Pools. Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="1e431-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="1e431-p107">Zeigen Sie alle Workflows im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Workflows des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1e431-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="1e431-p108">Zeigen Sie alle Warteschlangen im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Warteschlangen des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1e431-130">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1e431-p109">Zeigen Sie alle Agentgruppen im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Agentgruppen des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1e431-133">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1e431-p110">Zeigen Sie alle Geschäftszeiten im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Geschäftszeiten des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1e431-136">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1e431-p111">Zeigen Sie alle Feiertagssätze im Sicherungspool an, die der primäre Pool besitzt, und stellen Sie sicher, dass alle Feiertagssätze des primären Pools enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1e431-139">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="1e431-p112">Alternativ können Sie alle Reaktionsgruppen im Sicherungspool anzeigen, einschließlich der Gruppen, die sich im Besitz des primären bzw. des Sicherungspools befinden, indem Sie den Parameter "–ShowAll" anstelle von "–Owner" verwenden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e431-p113">Sie müssen entweder den Parameter "–ShowAll" oder "–Owner" verwenden. Wenn Sie keinen dieser Parameter verwenden, werden die von Ihnen in den Sicherungspool importierten Reaktionsgruppen nicht in den von den Cmdlets zurückgegebenen Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e431-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="1e431-144">Stellen Sie sicher, dass der Import erfolgreich war, indem Sie einen Anruf zu einer importierten Reaktionsgruppe platzieren und gewährleisten, dass der Anruf ordnungsgemäß verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="1e431-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="1e431-145">Fordern Sie Agents an, die Mitglieder der formalen Agentgruppe sind, um sich in ihren Agentgruppen im Sicherungspool anzumelden.</span><span class="sxs-lookup"><span data-stu-id="1e431-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="1e431-146">Verwalten und Ändern Sie die importierten Reaktionsgruppen wie gewöhnlich.</span><span class="sxs-lookup"><span data-stu-id="1e431-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e431-147">Während sich die Reaktionsgruppen im Sicherungspool befinden, müssen Sie lync Server-Verwaltungsshell verwenden, um Sie zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1e431-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="1e431-148">Sie können nicht lync Server-Systemsteuerung verwenden, um die Reaktionsgruppen zu verwalten, die Sie in den Sicherungspool importiert haben.</span><span class="sxs-lookup"><span data-stu-id="1e431-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="1e431-p115">Exportieren Sie, nachdem der primäre Pool wiederhergestellt wurde und das Failback abgeschlossen ist, die Reaktionsgruppen des primären Pools, die in den Sicherungspool importiert wurden. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="1e431-p116">Importieren Sie die Reaktionsgruppen zurück zum primären Pool. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="1e431-153">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e431-p117">Wenn Sie einen Pool während der Wiederherstellung neu erstellen, und zwar entweder mit dem gleichen oder einem komplett anderen vollqualifizierten Domänennamen, müssen Sie weiterhin den Parameter "–OverwriteOwner" verwenden. Daumenregel: Sie können den Parameter "–OverwriteOwner" immer verwenden, wenn Sie Reaktionsgruppen zum primären Pool zurückimportieren.</span><span class="sxs-lookup"><span data-stu-id="1e431-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="1e431-p118">Wenn Sie einen neuen Pool bereitgestellt haben (mit demselben oder einem anderen vollqualifizierten Domänennamen), um den primären Pool zu ersetzen und Sie die Anwendungsebeneneinstellungen des Sicherungspools für den neuen Pool verwenden möchten, beziehen Sie den Parameter "–ReplaceExistingSettings" mit ein. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="1e431-158">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e431-159">Wenn Sie die Anwendungsebeneneinstellungen und die standardmäßige Wartemusik-Audiodatei für den neuen Pool nicht mit den Einstellungen des Sicherungspools ersetzen möchten, verwendet der neue Pool standardmäßige Anwendungsebeneneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1e431-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="1e431-p119">Stellen Sie sicher, dass der Import zurück zum primären Tool erfolgreich war, indem Sie die importierte Reaktionsgruppenkonfiguration anzeigen. Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="1e431-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="1e431-p120">Zeigen Sie alle Workflows im primären Pool an, und stellen Sie sicher, dass alle importierten Workflows enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1e431-164">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1e431-p121">Zeigen Sie alle Warteschlangen im primären Pool an, und stellen Sie sicher, dass alle Warteschlangen enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1e431-167">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1e431-p122">Zeigen Sie alle Agentgruppen im primären Pool an, und stellen Sie sicher, dass alle Agentgruppen enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1e431-170">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1e431-p123">Zeigen Sie alle Geschäftszeiten im primären Pool an, und stellen Sie sicher, dass alle Geschäftszeiten enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1e431-173">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1e431-p124">Zeigen Sie alle Feiertagssätze im primären Pool an, und stellen Sie sicher, dass alle Feiertagssätze enthalten sind. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1e431-176">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="1e431-177">Stellen Sie sicher, dass der Import erfolgreich war, indem Sie einen Anruf zu einer importierten Reaktionsgruppe platzieren und gewährleisten, dass der Anruf ordnungsgemäß verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="1e431-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="1e431-p125">Entfernen Sie optional die Reaktionsgruppen, die der primäre Pool besitzt, aus dem Sicherungspool. Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e431-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="1e431-180">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e431-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e431-181">In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt und dann aus dem Sicherungspool entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e431-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

