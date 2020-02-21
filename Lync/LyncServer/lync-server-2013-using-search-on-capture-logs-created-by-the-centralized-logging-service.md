---
title: Verwenden der Suche in vom zentralisierten Protokollierungsdienst erstellten Erfassungs Protokollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d306c17f2c399d38e406d466664a49e3e2df6ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="595d8-102">Verwenden der Suche in den vom zentralisierten Protokollierungsdienst in lync Server 2013 erstellten Aufzeichnungs Protokollen</span><span class="sxs-lookup"><span data-stu-id="595d8-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="595d8-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="595d8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="595d8-104">Die Suchfunktionen im zentralisierten Protokollierungsdienst sind aus den folgenden Gründen nützlich und leistungsfähig:</span><span class="sxs-lookup"><span data-stu-id="595d8-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="595d8-105">Ihre Suchanfragen und die Ergebnisse werden basierend auf den festgelegten Kriterien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="595d8-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="595d8-p101">Ihre Suchanfragen können breit angelegt sein und anschließend auf genauere Kriterien wie Uhrzeit, Komponente oder Computer eingeschränkt werden. Sie suchen mit denselben Protokollen und müssen nicht erneut eine Protokollierungssitzung ausführen, wenn sich die Suchkriterien ändern.</span><span class="sxs-lookup"><span data-stu-id="595d8-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="595d8-p102">Die Ergebnisse Ihrer Suche werden auf allen Computern und in allen Pools im Bereich erfasst und in einer einzelnen Ausgabedatei gesammelt und aggregiert, die alle Ergebnisse der Suchkriterien enthält (beschränkt auf ausgeführte Szenarien und auf die von den Szenarien erfassten Daten). Sie verwenden zum Lesen der Ausgabedatei und der Ablaufverfolgungsmeldungen in Ihrer Bereitstellung bekannte Tools wie **Snooper** oder **Editor**.</span><span class="sxs-lookup"><span data-stu-id="595d8-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="595d8-p103">Der CLS-Agent auf den einzelnen Computern erstellt die Protokolle auf Basis der Szenarien (zwei Szenarien pro Computer können jeweils zu einem bestimmten Zeitpunkt ausgeführt werden). Die Protokolle und ihre zugehörigen Index- und Cachedateien werden vom CLS-Agent verwaltet. Wenn Sie eine Suche definieren und ausführen, weist der Suchbefehl den CLS-Agent an, welche Informationen abgerufen werden sollen. Der CLS-Agent führt die Abfrage für die Protokolldateien, Cachedateien und Indexdateien aus und gibt die Ergebnisse der Suche an den CLS-Controller zurück. Der CLS-Controller empfängt die Suchergebnisse von allen Computern und Pools im Bereich der Suche. Der CLS-Controller aggregiert (kombiniert) anschließend die Protokolle und ordnet sie nach Zeitunterschied an (angefangen beim ältesten Eintrag bis hin zum neuesten Eintrag).</span><span class="sxs-lookup"><span data-stu-id="595d8-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="595d8-116">Nach jeder Suche wird das **Sync-CsClsLogging-** Cmdlet ausgeführt, und der von den Suchvorgängen verwendete Cache wird geleert (nicht mit den vom CLSAgent verwalteten Cachedateien verwechselt).</span><span class="sxs-lookup"><span data-stu-id="595d8-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="595d8-117">Durch das Leeren des Caches wird sichergestellt, dass am CLSController für den nächsten Suchvorgang ein bereinigter Protokoll-und Ablaufverfolgungsdatei-Puffer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="595d8-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="595d8-118">Um den größten Nutzen aus dem zentralisierten Protokollierungsdienst zu ziehen, benötigen Sie ein gutes Verständnis dafür, wie Sie die Suche so konfigurieren, dass nur Ablaufverfolgungsmeldungen vom Computer und Pool Protokolle zurückgegeben werden, die für das Problem relevant sind, das Sie durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="595d8-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="595d8-119">Probleme</span><span class="sxs-lookup"><span data-stu-id="595d8-119">issues</span></span>

<span data-ttu-id="595d8-120">Zum Ausführen der Suchfunktionen für den zentralisierten Protokollierungsdienst mithilfe der lync Server-Verwaltungsshell müssen Sie Mitglied der rollenbasierten Sicherheitsgruppen für die CsAdministrator oder CsServerAdministrator oder eine benutzerdefinierte RBAC-Rolle sein, die Folgendes enthält: eine dieser beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="595d8-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="595d8-121">Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="595d8-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="595d8-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="595d8-123">Der Rest dieses Artikels befasst sich mit dem Definieren einer Suche zur Optimierung der Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="595d8-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="595d8-124">So führen Sie eine einfache Suche mithilfe des zentralisierten Protokollierungsdiensts aus</span><span class="sxs-lookup"><span data-stu-id="595d8-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="595d8-125">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="595d8-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="595d8-126">Stellen Sie sicher, dass das AlwaysOn-Szenario in Ihrer Bereitstellung auf globaler Ebene ausgeführt wird, und geben Sie dann Folgendes an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="595d8-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="595d8-127">Standardmäßig werden von "Search-CsClsLogging" die Ergebnisse der Suche an die Konsole gesendet.</span><span class="sxs-lookup"><span data-stu-id="595d8-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="595d8-128">Wenn Sie die Suchergebnisse in einer Datei speichern möchten, verwenden Sie den voll &lt;qualifizierten Datei Pfad&gt;– OutputFilePath String.</span><span class="sxs-lookup"><span data-stu-id="595d8-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="595d8-129">Um den Parameter "–OutputFilePath" zu definieren, geben Sie einen Pfad und einen Dateinamen als Teil des Parameters in Form einer Zeichenfolge zwischen Anführungszeichen ein, z. B. "C:\LogFiles\SearchOutput.txt".</span><span class="sxs-lookup"><span data-stu-id="595d8-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="595d8-130">In diesen Beispiel müssen Sie sicherstellen, dass das Verzeichnis "C:\LogFiles" vorhanden ist und Sie über Lese- und Schreibberechtigungen  (NTFS-Berechtigungen) für Dateien in diesem Ordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="595d8-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="595d8-131">An die Ausgabe werden immer Daten angefügt, sie wird nicht überschrieben.</span><span class="sxs-lookup"><span data-stu-id="595d8-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="595d8-132">Wenn Sie separate Dateien benötigen, geben Sie unterschiedliche Dateinamen für die einzelnen Suchvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="595d8-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="595d8-133">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="595d8-134">So führen Sie eine einfache Suche in einem Pool oder Computer mithilfe des zentralisierten Protokollierungsdiensts aus</span><span class="sxs-lookup"><span data-stu-id="595d8-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="595d8-135">Um die Suche auf einen bestimmten Pool oder Computer einzuschränken, verwenden Sie den Parameter "–Computers" mit dem Computer, der durch einen vollqualifizierten Computernamen angegeben ist. Er wird folgendermaßen in Anführungszeichen gesetzt und durch Komma getrennt:</span><span class="sxs-lookup"><span data-stu-id="595d8-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="595d8-136">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="595d8-137">Geben Sie zum Suchen auf mehreren Computern mehrere Computernamen in Anführungszeichen und durch Komma getrennt ein:</span><span class="sxs-lookup"><span data-stu-id="595d8-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="595d8-138">Wenn Sie einen gesamten Pool anstelle eines einzelnen Computers durchsuchen müssen, ändern Sie den Parameter "–Computers" in "–Pools", entfernen Sie den Computernamen, und ersetzen Sie ihn mit den Pools (versehen mit Anführungszeichen und durch Komma getrennt).</span><span class="sxs-lookup"><span data-stu-id="595d8-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="595d8-139">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="595d8-140">Bei Verwendung der Suchbefehle kann es sich bei Pools um einen beliebigen Pool in der Bereitstellung handeln, beispielsweise um Front-End-Pools, Edge-Pools, Server Pools für beständigen Chat oder andere, die als Pool in der Bereitstellung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="595d8-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="595d8-141">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="595d8-142">So führen Sie eine Suche mithilfe der Zeitparameter aus</span><span class="sxs-lookup"><span data-stu-id="595d8-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="595d8-143">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="595d8-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="595d8-p108">Standardmäßig liegt die Startzeit für die zeitspezifischen Parameter einer Suche 30 Minuten vor der Zeit, zu der die Suche gestartet wird. Anders ausgedrückt: Wenn Sie die Suche um 16:00 Uhr starten, werden die Protokolle für die festgelegten Computer und Pools zwischen 15:30 und 16:00 Uhr durchsucht. Wenn 60 Minuten oder 3 Stunden vor der aktuellen Uhrzeit eine Suche ausgeführt werden soll, verwenden Sie den Parameter "–StartTime", und legen Sie die Zeichenfolge für Datum und Uhrzeit fest, um die Uhrzeit für den Beginn der Suche anzugeben.</span><span class="sxs-lookup"><span data-stu-id="595d8-p108">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search. In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM. If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="595d8-147">Beispiel: Wenn Sie mit "–StartTime" und "–EndTime" einen Uhrzeit- und Datumsbereich festlegen, können Sie eine Suche für den 20.11.2012 für den Zeitraum zwischen 8 und 9 Uhr für Ihren Pool definieren.</span><span class="sxs-lookup"><span data-stu-id="595d8-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="595d8-148">Sie können den Ausgabepfad so festlegen, dass die Ergebnisse wie folgt in eine Datei\\mit dem Namen "c: Logfile. txt" geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="595d8-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="595d8-149">Die von Ihnen angegebene Uhrzeit-und Datumszeichenfolge kann "Date Time" oder "time date" sein.</span><span class="sxs-lookup"><span data-stu-id="595d8-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="595d8-150">"Mit dem Befehl wird die Zeichenfolge analysiert und die entsprechenden Werte für Datum und Uhrzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="595d8-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="595d8-p111">Wenn Sie mit dem Abrufen von Protokollen am 20.11.2012 um 11:00 Uhr beginnen möchten, legen Sie "–StartTime" fest. Der Standardzeitraum für die Suche ist 30 Minuten, es sei denn, Sie legen einen bestimmten Wert für "–EndTime" fest. Die Suche gibt Protokolle der festgelegten Computer oder Pools aus dem Zeitraum zwischen 11:00 Uhr bis 11:30 Uhr zurück.</span><span class="sxs-lookup"><span data-stu-id="595d8-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="595d8-154">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="595d8-p112">Legen Sie zum Ausführen einer Suche nach Protokollen in einem bestimmten Zeitraum "–StartTime" und "–EndTime" fest. Sie benötigen Protokolle für den Zeitraum zwischen 13 und 14:45 Uhr auf dem Computer "edge01.contoso.net".</span><span class="sxs-lookup"><span data-stu-id="595d8-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="595d8-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="595d8-158">So führen Sie mithilfe weiterer Kriterien und Abgleichungsoptionen eine erweiterte Suche aus</span><span class="sxs-lookup"><span data-stu-id="595d8-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="595d8-159">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="595d8-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="595d8-160">Geben Sie zum Ausführen eines Befehls zum Erfassen von Ablaufverfolgungen für bestimmte Komponenten Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="595d8-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="595d8-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="595d8-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="595d8-162">Die Suche gibt alle Protokolleinträge zurück, die Ablaufverfolgungskomponenten für SIPStack, S4 und UserServices für alle Computer und Pools in Ihrer Bereitstellung in den letzten 30 Minuten enthalten.</span><span class="sxs-lookup"><span data-stu-id="595d8-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="595d8-163">Geben Sie Folgendes ein, um die Suche mit den gleichen Komponenten auf Ihren Front-End-Pool mit dem Namen pool01.contoso.net zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="595d8-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="595d8-p113">Die Standardsuchlogik für Befehle mit mehreren Parametern besteht darin, das logische "Oder" mit den einzelnen definierten Parametern zu verwenden. Sie können dieses Verhalten durch Angabe des Parameters **–MatchAll** ändern. Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="595d8-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="595d8-p114">Wenn Ihre Szenarien für die ständige Ausführung festgelegt sind (wie AlwaysOn) oder wenn Sie ein langwieriges Szenario festgelegt haben, werden Protokolle möglicherweise vom lokalen Computer auf die Dateifreigabe verschoben. Sie legen die Dateifreigabe  mithilfe des Parameters "CacheFileNetworkFolder" fest, um mithilfe von "New-CsClsConfiguration" eine neue Konfiguration zu erstellen oder mithilfe von "Set-CsClsConfiguration" eine vorhandene Konfiguration zu ändern. Soll die Suche die Dateifreigabe in der Auflistung der zu durchsuchenden Protokolle nicht durchsuchen, verwenden Sie den Parameter "SkipNetworkLogs" folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="595d8-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

