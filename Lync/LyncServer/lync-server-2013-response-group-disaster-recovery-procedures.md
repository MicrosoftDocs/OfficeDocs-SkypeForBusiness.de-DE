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

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="38843-102">Verfahren für die Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38843-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38843-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="38843-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="38843-104">Während der Failover-Phase der Disaster Recovery befinden sich die Reaktionsgruppen in mehreren Pools: im primären Pool (der nicht verfügbar ist) und im Sicherungspool.</span><span class="sxs-lookup"><span data-stu-id="38843-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="38843-105">Die Antwortgruppen in beiden Pools haben denselben Namen und denselben Besitzer (den primären Pool), haben aber unterschiedliche übergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="38843-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="38843-106">In dieser Zeit funktionieren die Cmdlets der Reaktionsgruppe etwas anders.</span><span class="sxs-lookup"><span data-stu-id="38843-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="38843-107">Stellen Sie sicher, dass Sie die im folgenden Verfahren angegebenen Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="38843-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="38843-108">Ausführliche Informationen dazu, wie Cmdlets während der failoverphase funktionieren, finden Sie unter NextHop-Blog Artikel "lync Server 2013: Wiederherstellen von [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)Reaktionsgruppen während der Disaster Recovery" unter.</span><span class="sxs-lookup"><span data-stu-id="38843-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="38843-109">Dieser Blog Artikel bezieht sich auch auf die veröffentlichte Version von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38843-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="38843-110">Führen Sie die Schritte in der folgenden Vorgehensweise aus, um die Disaster Recovery für den lync Server Response Group-Dienst vorzubereiten und durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="38843-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="38843-111">So führen Sie eine Failover-und Failback-Reaktionsgruppe aus</span><span class="sxs-lookup"><span data-stu-id="38843-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="38843-112">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="38843-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="38843-113">Führen Sie regelmäßig Sicherungen durch.</span><span class="sxs-lookup"><span data-stu-id="38843-113">Routinely perform backups.</span></span> <span data-ttu-id="38843-114">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="38843-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="38843-116">Importieren Sie bei einem Ausfall nach einem Failover zum Sicherungspool die Antwortgruppen in den Sicherungspool.</span><span class="sxs-lookup"><span data-stu-id="38843-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="38843-117">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="38843-118">Wenn Sie die Einstellungen auf Anwendungsebene im Sicherungspool durch die Einstellungen des primären Pools ersetzen möchten, schließen Sie den Parameter – ReplaceExistingSettings ein.</span><span class="sxs-lookup"><span data-stu-id="38843-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="38843-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="38843-120">Wenn Sie die Einstellungen im Sicherungspool nicht ersetzen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen des primären Pools verloren.</span><span class="sxs-lookup"><span data-stu-id="38843-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="38843-121">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planen der Disaster Recovery einer Reaktionsgruppe in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38843-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="38843-122">Überprüfen Sie, ob der Import erfolgreich war, indem Sie die importierten Antwortgruppen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38843-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="38843-123">Die importierten Antwortgruppen sind weiterhin im Besitz des primären Pools.</span><span class="sxs-lookup"><span data-stu-id="38843-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="38843-124">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="38843-124">Do the following:</span></span>
    
      - <span data-ttu-id="38843-125">Zeigen Sie alle Workflows im Sicherungspool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle Workflows des primären Pools enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="38843-126">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="38843-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="38843-128">Zeigen Sie alle Warteschlangen im Sicherungspool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle primären Pool Warteschlangen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="38843-129">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="38843-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="38843-131">Zeigen Sie alle Agentengruppen im Sicherungspool an, die dem primären Pool gehören, und überprüfen Sie, ob alle Gruppen des primären Pool-Agents enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="38843-132">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="38843-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="38843-134">Zeigen Sie alle Geschäftszeiten im Backup-Pool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle Geschäftsstunden des primären Pools enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="38843-135">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="38843-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="38843-137">Zeigen Sie alle Feiertagssätze im Sicherungspool an, die im Besitz des primären Pools sind, und überprüfen Sie, ob alle Feiertagssätze des primären Pools enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="38843-138">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="38843-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="38843-140">Sie können aber auch alle Antwortgruppen im Sicherungspool anzeigen, einschließlich derer im Besitz des primären Pools und der Besitzer des Sicherungs Pools, indem Sie den Parameter – ShowAll anstelle des Parameters-Owner verwenden.</span><span class="sxs-lookup"><span data-stu-id="38843-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="38843-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38843-142">Sie müssen entweder den-ShowAll-Parameter oder den-owner-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="38843-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="38843-143">Wenn Sie keinen dieser Parameter verwenden, werden die Antwortgruppen, die Sie in den Sicherungspool importiert haben, nicht in den von den Cmdlets zurückgegebenen Ergebnissen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="38843-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="38843-144">Überprüfen Sie, ob der Import erfolgreich war, indem Sie eine importierte Antwortgruppe anrufen und überprüfen, ob der Anruf richtig gehandhabt wurde.</span><span class="sxs-lookup"><span data-stu-id="38843-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="38843-145">Anfordern von Agents, die Mitglieder von formellen Agentengruppen sind, um sich bei ihren Agentengruppen im Sicherungspool anzumeldet.</span><span class="sxs-lookup"><span data-stu-id="38843-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="38843-146">Verwalten und ändern Sie die importierten Antwortgruppen wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="38843-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38843-147">Während sich die Antwortgruppen im Sicherungspool befinden, müssen Sie Sie mithilfe der lync Server-Verwaltungsshell verwalten.</span><span class="sxs-lookup"><span data-stu-id="38843-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="38843-148">Sie können die lync Server-Systemsteuerung nicht zum Verwalten der Reaktionsgruppen verwenden, die Sie in den Sicherungspool importiert haben.</span><span class="sxs-lookup"><span data-stu-id="38843-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="38843-149">Nachdem der primäre Pool wiederhergestellt wurde und das Failback abgeschlossen ist, exportieren Sie die primären Pool Antwortgruppen, die in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="38843-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="38843-150">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="38843-151">Importieren Sie die Antwortgruppen zurück in den primären Pool.</span><span class="sxs-lookup"><span data-stu-id="38843-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="38843-152">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="38843-153">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38843-154">Wenn Sie während der Wiederherstellung einen Pool neu erstellen, ob mit dem gleichen oder einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN), müssen Sie den Parameter – OverwriteOwner verwenden.</span><span class="sxs-lookup"><span data-stu-id="38843-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="38843-155">Als Faustregel können Sie immer den – OverwriteOwner-Parameter verwenden, wenn Sie Antwortgruppen zurück in den primären Pool importieren.</span><span class="sxs-lookup"><span data-stu-id="38843-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="38843-156">Wenn Sie einen neuen Pool (mit demselben oder einem anderen FQDN) bereitgestellt haben, um den primären Pool zu ersetzen, und Sie die Einstellungen auf Anwendungsebene aus dem Sicherungspool für den neuen Pool verwenden möchten, schließen Sie den Parameter – ReplaceExistingSettings ein.</span><span class="sxs-lookup"><span data-stu-id="38843-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="38843-157">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="38843-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38843-159">Wenn Sie die Einstellungen auf Anwendungsebene und die Standard-Musikdatei für den neuen Pool nicht durch die Einstellungen aus dem Sicherungspool ersetzen möchten, verwendet der neue Pool die Standardeinstellungen auf Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="38843-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="38843-160">Überprüfen Sie, ob der Import zurück in den primären Pool erfolgreich war, indem Sie die Konfiguration der importierten Reaktionsgruppe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38843-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="38843-161">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="38843-161">Do the following:</span></span>
    
      - <span data-ttu-id="38843-162">Zeigen Sie alle Workflows im primären Pool an, und überprüfen Sie, ob alle importierten Workflows enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="38843-163">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="38843-164">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="38843-165">Zeigen Sie alle Warteschlangen im primären Pool an, und überprüfen Sie, ob alle importierten Warteschlangen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="38843-166">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="38843-167">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="38843-168">Zeigen Sie alle Agentengruppen im primären Pool an, und überprüfen Sie, ob alle importierten Agentengruppen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="38843-169">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="38843-170">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="38843-171">Zeigen Sie alle Geschäftszeiten im primären Pool an, und überprüfen Sie, ob alle importierten Geschäftszeiten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="38843-172">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="38843-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="38843-174">Zeigen Sie alle Feiertagssätze im primären Pool an, und überprüfen Sie, ob alle importierten Feiertagssätze enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="38843-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="38843-175">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="38843-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="38843-177">Überprüfen Sie, ob der Import erfolgreich war, indem Sie eine importierte Antwortgruppe anrufen und überprüfen, ob der Anruf richtig gehandhabt wurde.</span><span class="sxs-lookup"><span data-stu-id="38843-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="38843-178">Optional können Sie die Antwortgruppen entfernen, die im Besitz des primären Pools aus dem Sicherungspool sind.</span><span class="sxs-lookup"><span data-stu-id="38843-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="38843-179">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="38843-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="38843-180">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38843-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38843-181">In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt und dann aus dem Sicherungspool entfernt.</span><span class="sxs-lookup"><span data-stu-id="38843-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

