---
title: 'Lync Server 2013: Verwenden von "beenden" für den zentralisierten Protokollierungsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 621d7c02530fea62b1601c1db755292c8f819a6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="a9f79-102">Verwenden von "beenden" für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f79-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9f79-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a9f79-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a9f79-p101">Eine aktuell ausgeführte Protokollierungssitzung können Sie mit dem Cmdlet „Stop-CsClsLogging“ anhalten. Eine Protokollierungssitzung muss in Allgemeinen nur in wenigen Situationen angehalten werden. Beispielsweise können Sie Protokolle durchsuchen und Konfigurationen ändern, ohne die Protokollierung zuvor anzuhalten. Wenn Sie zwei Szenarien ausführen, z. B. „AlwaysOn“ und „UserReplicator“, und Informationen zur Authentifizierung sammeln müssen, müssen Sie eines der anderen Szenarien anhalten (auf globaler Ebene oder auf Standort-, Pool- oder Computerebene), bevor Sie die Ausführung des Authentifizierungsszenarios starten können. Ausführliche Informationen finden Sie unter [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="a9f79-p101">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet. Generally, there aren’t many situations in which you would need to stop a logging session. For example, you can search logs and change configurations without first needing to stop logging. If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario. For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9f79-109">Wenn Sie feststellen möchten, welche Szenarien Sie für eine bestimmte Bereitstellung, einen Pool oder einen Computer ausführen können, müssen Sie daran denken, dass Sie auf die Ausführung von zwei Szenarien <STRONG>pro Computer</STRONG>beschränken.</span><span class="sxs-lookup"><span data-stu-id="a9f79-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="a9f79-110">Wenn Sie in einem Pool Aktivitäten protokollieren, sollten Sie den Pool als einzelne Entität behandeln.</span><span class="sxs-lookup"><span data-stu-id="a9f79-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="a9f79-111">In den meisten Fällen ist das Ausführen verschiedener Szenarien auf jedem Computer in einem Pool nicht sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="a9f79-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="a9f79-112">Sinnvoll ist es dagegen, sich mit dem Problem zu befassen, zu dem Sie Daten sammeln, und zu ermitteln, welches Szenario auf einem bestimmten Computer in der gesamten Bereitstellung am hilfreichsten ist.</span><span class="sxs-lookup"><span data-stu-id="a9f79-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="a9f79-113">Wenn Sie beispielsweise das UserReplicator-Szenario in Frage stellen, gibt es bei der Ausführung von UserReplicator auf einem Edgeserver oder Edge-Pool nur sehr wenig Wert.</span><span class="sxs-lookup"><span data-stu-id="a9f79-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="a9f79-p103">Nachdem Sie das Problem und den Umfang der Auswirkungen analysiert haben, sollten Sie sorgfältig auswählen, welche Szenarien auf welchen Computern und in welchen Pools ausgeführt werden sollen. Während das „AlwaysOn“ für einen weiten Bereich von Anwendungen mit weitem Bereich sinnvoll ist, da dabei Informationen zu einer Vielzahl von Anbietern gesammelt werden, haben bestimmte Szenarien nur Anwendungswert auf bestimmten Computern bzw. in bestimmten Pools. Seien Sie außerdem vorsichtig beim willkürlichen Starten einer Protokollierungssitzung, ohne den Wert eines bestimmten Szenarios zu kennen. Wenn Sie das falsche Szenario verwenden – oder ein für die Aufgabe zwar geeignetes Szenario verwenden, jedoch auf der falschen Ebene (global, Standort, Pool oder Computer) –, erhalten Sie fragwürdige und wenig nützliche Daten, so als ob Sie das Szenario überhaupt nicht ausgeführt hätten.</span><span class="sxs-lookup"><span data-stu-id="a9f79-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="a9f79-118">Um die Funktionen für den zentralisierten Protokollierungsdienst mithilfe der lync Server-Verwaltungsshell zu steuern, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein, die eine dieser beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="a9f79-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="a9f79-119">Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="a9f79-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="a9f79-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a9f79-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="a9f79-121">So beenden Sie eine derzeit ausgeführte zentralisierte Protokollierungsdienst Sitzung</span><span class="sxs-lookup"><span data-stu-id="a9f79-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="a9f79-122">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a9f79-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a9f79-123">Fragen Sie den zentralisierten Protokollierungsdienst ab, um herauszufinden, welche Szenarien zurzeit ausgeführt werden, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="a9f79-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="a9f79-124">![Windows PowerShell-Konsole nach dem Aufruf von Show-CSCL](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell-Konsole nach dem Aufruf von Show-CSCL")</span><span class="sxs-lookup"><span data-stu-id="a9f79-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="a9f79-p105">Das Ergebnis von „Show-CsClsLogging“ ist eine Zusammenfassung der ausgeführten Szenarien und der Ebenen, auf denen Sie ausgeführt werden. Ausführliche Informationen finden Sie unter [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="a9f79-p105">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in. For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="a9f79-127">Geben Sie zum Anhalten einer aktuell ausgeführten Protokollierungssitzung mit einem bestimmten Szenario Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a9f79-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="a9f79-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a9f79-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="a9f79-129">Mit diesem Befehl wird die Protokollierung mit dem Szenario „UserReplicator“ in „pool01.contoso.net“ angehalten.</span><span class="sxs-lookup"><span data-stu-id="a9f79-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9f79-p106">Protokolle, die während dieser Protokollierungssitzung mit dem Szenario „UserReplicator“ erstellt wurden, werden nicht gelöscht. Die Protokollierung steht Ihnen noch zur Verfügung, um Suchen mit dem Befehl „Search-CsClsLogging“ auszuführen. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="a9f79-p106">Logs created during this logging session using the UserReplicator scenario are not deleted. The logging is still available for you to execute searches against using the Search-CsClsLogging command. For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="a9f79-p107">Das Cmdlet „Stop-CsClsLogging“ fungiert als Begleitbefehl zu „Start-CsClsLogging“, beendet die Protokollierungssitzung entsprechend der Definition im aktuellen Szenario und behält die von der Protokollierungssitzung erstellten Protokolle bei. Sie können jederzeit zwei Szenarien auf einem bestimmten Computer ausführen. Das Anhalten eines Szenarios, um mithilfe eines anderen Szenarios Informationen zu sammeln, ist eine gängige Aufgabe, die Sie meistens auch bei großer Arbeitsauslastung während der Fehlerbehebung anwenden können.</span><span class="sxs-lookup"><span data-stu-id="a9f79-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9f79-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9f79-136">See Also</span></span>


[<span data-ttu-id="a9f79-137">Verwenden von "Start" für den zentralisierten Protokollierungsdienst zum Aufzeichnen von Protokollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f79-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="a9f79-138">Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9f79-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="a9f79-139">Anzeigen-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="a9f79-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="a9f79-140">Anfang-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="a9f79-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="a9f79-141">Stopp-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="a9f79-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

