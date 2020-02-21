---
title: Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04614e970064f765e24b86b6e875d1fb284b3fbc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="1c625-102">Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c625-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c625-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1c625-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1c625-104">Zum Erfassen von Ablaufverfolgungsprotokollen mit dem zentralisierten Protokollierungsdienst geben Sie einen Befehl ein, um mit der Protokollierung für einen oder mehrere Computer und Pools zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="1c625-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="1c625-105">Sie können auch Parameter ausgeben, die definieren, welche Computer oder Pools, welche Szenarien ausgeführt werden sollen (beispielsweise AlwaysOn, ein anderes vordefiniertes Szenario oder ein Szenario, das Sie erstellt haben), welche lync Server Komponenten (beispielsweise S4, SipStack) zur Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="1c625-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="1c625-106">Um die richtigen Informationen zu erfassen, müssen Sie sicherstellen, dass Sie das richtige Szenario verwenden, um Informationen zu sammeln, die für das Problem relevant sind.</span><span class="sxs-lookup"><span data-stu-id="1c625-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="1c625-107">Im zentralisierten Protokollierungsdienst ist ein Szenario das Konzept der Aktivierung der Protokollierung basierend auf einer Auflistung von Server Komponenten, Protokollierungsebenen und Flags, die wesentlich effizienter und nützlicher ist, als diese Elemente auf einer pro-Server-Basis zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1c625-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="1c625-108">Sie definieren und geben ein Szenario an, das ausgeführt werden soll, und das Szenario wird konsistent auf allen Servern und Pools im Bereich der Infrastruktur ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c625-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="1c625-p103">Das Standardszenario heißt **AlwaysOn**. AlwaysOn soll dazu dienen, das Szenario ständig auszuführen, wie der Name des Szenarios bereits impliziert. Das Szenario AlwaysOn erfasst Informationen auf der Ebene "Info" (zum Protokolliergrad "Info" zählen zusätzlich zu den Infomeldungen Meldungen der Ebenen "Schwerwiegend", "Fehler" und "Warnung") für viele der häufigsten Serverkomponenten. Von AlwaysOn werden Informationen vor und nach einem Problem sowie während eines Problems erfasst. Daher unterscheidet es sich gravierend vom typischen Verhalten früherer Protokollierungstools wie OCSLogger. OCSLogger wurde ausgeführt, nachdem das Problem bereits aufgetreten war. Dadurch wurde die Problembehandlung erschwert, da die erfassten Daten nicht proaktiv, sondern rückwirkend waren. Falls AlwaysOn nicht die gewünschten Informationen zum Ermitteln der fehlerhaften Komponente und keine Vorgehensweise zur Behebung enthält (was aufgrund des Umfangs der Anbieter in AlwaysOn unwahrscheinlich ist), erhalten Sie immerhin angemessene Informationen, mit denen die erforderlichen Schritte (z. B. Erstellen eines neuen Szenarios, Erfassen weiterer Informationen, Ausführen einer anderen Suche zum Sammeln genauerer Einzelheiten usw.) ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="1c625-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="1c625-116">Der zentralisierte Protokollierungsdienst bietet zwei Möglichkeiten zum Ausgeben von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="1c625-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="1c625-117">Eine Reihe von Themen wurde direkt auf die Verwendung von Windows PowerShell über die lync Server-Verwaltungsshell ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="1c625-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="1c625-118">Die Möglichkeit, eine Reihe komplexer Konfigurationen und Befehle zu verwenden, begünstigt Windows PowerShell für die Verwendung von zentralisiertem Protokollierungsdienst.</span><span class="sxs-lookup"><span data-stu-id="1c625-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="1c625-119">Da Windows PowerShell über das lync Server-Verwaltungsshell für alle Funktionen in lync Server fast allgegenwärtig ist, werden nur die Windows PowerShell-Befehle besprochen.</span><span class="sxs-lookup"><span data-stu-id="1c625-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1c625-120">Wenn Sie sich für die Verwendung des begrenzten Befehlssatzes entscheiden, der über die Befehlszeile verfügbar ist, können Sie Hilfe zu CLSController <CODE>ClsController.exe</CODE>. exe erhalten, indem Sie die EINGABETASTE eingeben.</span><span class="sxs-lookup"><span data-stu-id="1c625-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="1c625-121">Standardmäßig wird <STRONG>ClsController. exe</STRONG> im Verzeichnis C:\Program Files\Microsoft lync Server 2013 \ ClsAgent installiert.</span><span class="sxs-lookup"><span data-stu-id="1c625-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="1c625-122">So führen Sie Start-CsClsLogging mit Windows PowerShell mit grundlegenden Befehlen aus</span><span class="sxs-lookup"><span data-stu-id="1c625-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="1c625-123">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1c625-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1c625-124">Starten Sie ein Protokollierungsszenario mit dem zentralisierten Protokollierungsdienst, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="1c625-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="1c625-125">Geben Sie beispielsweise zum Starten des Szenarios **AlwaysOn** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1c625-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1c625-126">Für das AlwaysOn-Szenario ist keine Standarddauer festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1c625-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="1c625-127">Das Szenario wird so lange ausgeführt, bis Sie es mit dem Cmdlet <STRONG>Stop-CsClsLogging</STRONG> explizit beenden.</span><span class="sxs-lookup"><span data-stu-id="1c625-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="1c625-128">Ausführliche Informationen finden Sie unter <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="1c625-128">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="1c625-129">Für alle anderen Szenarios gilt eine Standarddauer von 4 Stunden.</span><span class="sxs-lookup"><span data-stu-id="1c625-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="1c625-130">Drücken Sie zum Ausführen des Befehls die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="1c625-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1c625-131">Es kann einen kurzen Moment dauern (30 bis 60 Sekunden), bis der Befehl ausgeführt und der Status von den Computern in Ihrer Bereitstellung abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1c625-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="1c625-132">![Start-CsClsLogging wird gestartet.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Start-CsClsLogging wird gestartet.")</span><span class="sxs-lookup"><span data-stu-id="1c625-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="1c625-133">Um ein weiteres Szenario zu starten, verwenden Sie das Cmdlet **Start-CsClsLogging** mit dem Namen des zusätzlichen Szenarios (z. B. des Szenarios **Authentifizierung**) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1c625-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="1c625-134">Sie können jederzeit insgesamt zwei Szenarien auf einem beliebigen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="1c625-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="1c625-135">Hat der Befehl einen globalen Gültigkeitsbereich, werden die Szenarien auf allen Computern in Ihrer Bereitstellung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c625-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="1c625-136">Wenn Sie ein drittes Szenario starten möchten, müssen Sie die Protokollierung für den Computer, Pool, Standort oder globalen Gültigkeitsbereich beenden, für den das neue Szenario ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c625-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="1c625-137">Haben Sie einen globalen Gültigkeitsbereich gestartet, können Sie die Protokollierung für mindestens ein Szenario für mindestens einen Computer oder Pool beenden.</span><span class="sxs-lookup"><span data-stu-id="1c625-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="1c625-138">Ausführliche Informationen zum Verwalten der ausgeführten Szenarien finden Sie unter <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">using Stop for the zentralisiert Logging Service in lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="1c625-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="1c625-139">So führen Sie Start-CsClsLogging mit Windows PowerShell mit erweiterten Befehlen aus</span><span class="sxs-lookup"><span data-stu-id="1c625-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="1c625-140">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1c625-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1c625-141">Zur Verwaltung der Protokollierungsbefehle stehen zusätzliche Parameter zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1c625-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="1c625-142">Mit –Duration können Sie die Dauer der Ausführung des Szenarios festlegen.</span><span class="sxs-lookup"><span data-stu-id="1c625-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="1c625-143">Darüber hinaus können Sie –Computers, eine Liste der durch Komma getrennten Computer-FQDNs (Fully Qualified Domain Names, vollqualifizierte Domänennamen), oder –Pools, eine durch Komma getrennte Liste der FQDNs aller Pools, für die die Protokollierung ausgeführt werden soll, definieren.</span><span class="sxs-lookup"><span data-stu-id="1c625-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="1c625-144">Sie starten eine Protokollierungssitzung für das *UserReplicator* -Szenario im Pool "pool01.contoso.net".</span><span class="sxs-lookup"><span data-stu-id="1c625-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="1c625-145">Außerdem legen Sie für die Dauer der Protokollierungssitzung 8 Stunden fest.</span><span class="sxs-lookup"><span data-stu-id="1c625-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="1c625-146">Geben Sie hierzu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1c625-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="1c625-147">Bei erfolgreicher Ausführung dieses Szenarios wird in etwa folgendes Ergebnis zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="1c625-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="1c625-148">![Start-CsClsLogging wird gestartet.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Start-CsClsLogging wird gestartet.")</span><span class="sxs-lookup"><span data-stu-id="1c625-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="1c625-149">Beachten Sie, dass in diesem Beispiel die Szenarien "AlwaysOn" und "UserReplicator" ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1c625-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c625-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c625-150">See Also</span></span>


[<span data-ttu-id="1c625-151">Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c625-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

