---
title: 'Lync Server 2013: Verwenden von Stop für den zentralisierten Protokollierungsdienst'
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
ms.openlocfilehash: 2f764bbc93ae327e30fa6ac9daf3128963856460
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="464c2-102">Verwenden von Stop für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="464c2-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="464c2-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="464c2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="464c2-104">Eine derzeit ausgeführte Protokollierungssitzung können Sie mit dem Cmdlet "Stop-CsClsLogging" anhalten.</span><span class="sxs-lookup"><span data-stu-id="464c2-104">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="464c2-105">Eine Protokollierungssitzung muss in Allgemeinen nur in wenigen Situationen angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="464c2-105">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="464c2-106">Beispielsweise können Sie Protokolle durchsuchen und Konfigurationen ändern, ohne die Protokollierung zuvor anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="464c2-106">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="464c2-107">Wenn Sie zwei Szenarien ausführen, z. B. "AlwaysOn" und "UserReplicator" und Informationen zur Authentifizierung sammeln müssen, so müssen Sie eines der anderen Szenarien anhalten (auf globaler Ebene oder auf Standort-, Pool- oder Computerebene), bevor Sie die Ausführung des Authentifizierungsszenarios starten können.</span><span class="sxs-lookup"><span data-stu-id="464c2-107">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="464c2-108">Ausführliche Informationen finden Sie unter [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="464c2-108">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="464c2-109">Beim Festlegen der Szenarien, die in einer bestimmten Bereitstellung, einem Pool oder auf einem Computer ausgeführt werden können, denken Sie unbedingt daran, dass <STRONG>pro Computer</STRONG> nur zwei Szenarien ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="464c2-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="464c2-110">Wenn Sie in einem Pool Aktivitäten protokollieren, sollten Sie den Pool als einzelne Entität behandeln.</span><span class="sxs-lookup"><span data-stu-id="464c2-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="464c2-111">In den meisten Fällen wäre das Ausführen verschiedener Szenarien auf jedem Computer in einem Pool nicht sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="464c2-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="464c2-112">Sinnvoll ist es dagegen, sich mit dem Problem zu befassen, zu dem Sie Daten sammeln und zu ermitteln, welches Szenario auf einem bestimmten Computer in der gesamten Bereitstellung am sinnvollsten ist.</span><span class="sxs-lookup"><span data-stu-id="464c2-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="464c2-113">Wenn Sie beispielsweise das UserReplicator-Szenario in Frage stellen, gäbe es bei der Ausführung von UserReplicator auf einem Edgeserver oder Edgepool nur sehr wenig Wert.</span><span class="sxs-lookup"><span data-stu-id="464c2-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="464c2-p103">Nachdem Sie das Problem und den Umfang der Auswirkungen analysiert haben, sollten Sie sorgfältig auswählen, welche Szenarien auf welchen Computern und in welchen Pools ausgeführt werden sollen. Während das AlwaysOn-Szenario für eine Anwendung mit weitem Bereich sinnvoll ist, da dabei Informationen zu einer Vielfalt von Anbietern gesammelt werden, haben bestimmte Szenarien nur Anwendungswert auf bestimmten Computern bzw. in bestimmten Pools. Seien Sie außerdem vorsichtig beim willkürlichen Starten einer Protokollierungssitzung, ohne den Wert eines bestimmten Szenarios zu kennen. Wenn Sie das falsche Szenario verwenden – oder ein für die Aufgabe zwar geeignetes Szenario verwenden, jedoch auf der falschen Ebene (global, Standort, Pool oder Computer) anwenden – erhalten Sie fragwürdige und wenig nützliche Daten, so als ob Sie das Szenario überhaupt nicht ausgeführt hätten.</span><span class="sxs-lookup"><span data-stu-id="464c2-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="464c2-118">Zum Steuern der Funktionen für den zentralisierten Protokollierungsdienst mit dem lync Server-Verwaltungsshell müssen Sie Mitglied der rollenbasierten Sicherheitsgruppen für die CsAdministrator oder CsServerAdministrator oder eine benutzerdefinierte RBAC-Rolle sein, die Folgendes enthält: eine dieser beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="464c2-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="464c2-119">Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="464c2-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="464c2-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="464c2-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="464c2-121">So beenden Sie eine derzeit ausgeführten Sitzung für den zentralisierten Protokollierungsdienst</span><span class="sxs-lookup"><span data-stu-id="464c2-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="464c2-122">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="464c2-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="464c2-123">Fragen Sie den zentralisierten Protokollierungsdienst, um herauszufinden, welche Szenarien derzeit durchführen, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="464c2-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="464c2-124">![Windows PowerShell Konsole nach dem Aufruf von Show-CSCL](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell Konsole nach dem Aufruf von Show-CSCL")</span><span class="sxs-lookup"><span data-stu-id="464c2-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="464c2-125">Das Ergebnis von "Show-CsClsLogging" ist eine Zusammenfassung der ausgeführten Szenarien und der Ebenen, auf denen Sie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="464c2-125">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="464c2-126">Ausführliche Informationen finden Sie unter [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="464c2-126">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="464c2-127">Zum Anhalten einer derzeit ausgeführten Protokollierungssitzung mit einem bestimmten Szenario, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="464c2-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="464c2-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="464c2-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="464c2-129">Mit diesem Befehl wird die Protokollierung mit dem UserReplicatior-Szenario in "pool01.contoso.net" angehalten.</span><span class="sxs-lookup"><span data-stu-id="464c2-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="464c2-130">Protokolle, die während dieser Protokollierungssitzung mit dem UserReplicator-Szenario erstellt wurden, werden nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="464c2-130">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="464c2-131">Die Protokollierung steht Ihnen noch zur Verfügung, um Suchen mit dem Befehl "Search-CsClsLogging" auszuführen.</span><span class="sxs-lookup"><span data-stu-id="464c2-131">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="464c2-132">Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="464c2-132">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="464c2-p107">Das Cmdlet "Stop-CsClsLogging" fungiert als Begleitbefehl zu "Start-CsClsLogging", beendet definiert nach Szenarien die Protokollierungssitzung und behält die von der Protokollierungssitzung erstellten Protokolle bei. Sie können jederzeit zwei Szenarien auf einem bestimmten Computer ausführen. Das Anhalten eines Szenarios, um mithilfe eines anderen Szenarios Informationen zu sammeln ist eine gängige Aufgabe, die Sie während der Fehlerbehebung bei der Arbeitsauslastung meist anwenden können.</span><span class="sxs-lookup"><span data-stu-id="464c2-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="464c2-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="464c2-136">See Also</span></span>


[<span data-ttu-id="464c2-137">Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="464c2-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="464c2-138">Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="464c2-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="464c2-139">Show-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="464c2-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="464c2-140">Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="464c2-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="464c2-141">Stop-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="464c2-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

