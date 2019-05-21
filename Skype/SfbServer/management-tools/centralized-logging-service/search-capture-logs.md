---
title: Suche nach vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellten Erfassungsprotokollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server 2015 die Protokolle für zentralisierte Protokollierungsdienste durchsuchen und lesen können.'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274373"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="f1ba1-103">Suche nach vom zentralisierten Protokollierungsdienst in Skype for Business Server 2015 erstellten Erfassungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="f1ba1-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f1ba1-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie in Skype for Business Server 2015 die Protokolle für zentralisierte Protokollierungsdienste durchsuchen und lesen können.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f1ba1-105">Die Suchfeatures im zentralisierten Protokollierungsdienst sind aus folgenden Gründen nützlich und leistungsfähig:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="f1ba1-106">Ihre Suchanfragen und die Ergebnisse werden basierend auf den festgelegten Kriterien auf einem Computer, in einem Pool, an einem Standort oder auf globaler Ebene ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="f1ba1-107">Ihre Suchanfragen können breit angelegt sein und anschließend auf genauere Kriterien wie Uhrzeit, Komponente oder Computer eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="f1ba1-108">Sie suchen nach denselben Protokollen und müssen keine Protokollierungssitzung erneut ausführen, wenn sich die Suchkriterien ändern.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="f1ba1-p102">Die Ergebnisse Ihrer Suche werden auf allen Computern und in allen Pools im Bereich erfasst und in einer einzelnen Ausgabedatei gesammelt, die alle Ergebnisse der Suchkriterien enthält (beschränkt auf ausgeführte Szenarien und auf die von den Szenarien erfassten Daten). Sie verwenden zum Lesen der Ausgabedatei und der Ablaufverfolgungsmeldungen in Ihrer Bereitstellung bekannte Tools wie **Snooper** oder **Notepad**.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="f1ba1-p103">Der CLS-Agent auf den einzelnen Computern erstellt die Protokolle auf Basis der Szenarien (zwei Szenarien pro Computer können jeweils zu einem bestimmten Zeitpunkt ausgeführt werden). Die Protokolle und ihre zugehörigen Index- und Cachedateien werden vom CLS-Agent verwaltet. Wenn Sie eine Suche definieren und ausführen, weist der Suchbefehl den CLS-Agent an, welche Informationen abgerufen werden sollen. Der CLS-Agent führt die Abfrage für die Protokolldateien, Cachedateien und Indexdateien aus und gibt die Ergebnisse der Suche an den CLS-Controller zurück. Der CLS-Controller empfängt die Suchergebnisse von allen Computern und Pools im Bereich der Suche. Der CLS-Controller aggregiert (kombiniert) anschließend die Protokolle und ordnet sie nach Zeitunterschied an (angefangen beim ältesten Eintrag bis hin zum neuesten Eintrag).</span><span class="sxs-lookup"><span data-stu-id="f1ba1-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="f1ba1-117">Nach jeder Suche wird das Cmdlet **Sync-CsClsLogging** ausgeführt, und es wird der von Suchvorgängen verwendete Cache geleert (nicht zu verwechseln mit den Cachedateien, die vom CLSAgent verwaltet werden).</span><span class="sxs-lookup"><span data-stu-id="f1ba1-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="f1ba1-118">Durch das Leeren des Caches können Sie sicherstellen, dass im CLSController für den nächsten Suchvorgang ein sauberer Protokoll-und Ablaufverfolgungsdatei-Aufnahmepuffer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="f1ba1-119">Um den größten Nutzen aus dem zentralisierten Protokollierungsdienst zu ziehen, benötigen Sie ein gutes Verständnis dafür, wie Sie die Suche so konfigurieren, dass nur nach Verfolgungs Nachrichten von den Computern und Pool Protokollen zurückgegeben werden, die für das von Ihnen recherchierte Problem relevant sind.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="f1ba1-120">Fragen</span><span class="sxs-lookup"><span data-stu-id="f1ba1-120">issues</span></span>
  
<span data-ttu-id="f1ba1-121">Wenn Sie die Suchfunktionen für den zentralisierten Protokollierungsdienst mithilfe der Skype for Business Server-Verwaltungsshell ausführen möchten, müssen Sie Mitglied der CsAdministrator-oder CsServerAdministrator-Sicherheitsgruppe (Role-Based Access Control, RBAC) oder einer benutzerdefinierten RBAC-Rolle sein. , die eine dieser beiden Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="f1ba1-122">Führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="f1ba1-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="f1ba1-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="f1ba1-124">Der Rest dieses Artikels befasst sich mit dem Definieren einer Suche zur Optimierung der Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="f1ba1-125">So führen Sie eine einfache Suche mit dem zentralen Protokollierungsdienst aus</span><span class="sxs-lookup"><span data-stu-id="f1ba1-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="f1ba1-126">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f1ba1-127">Stellen Sie sicher, dass das Szenario „AlwaysOn“ in Ihrer Bereitstellung auf globaler Ebene ausgeführt wird, und geben Sie dann Folgendes an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="f1ba1-128">Standardmäßig werden von „Search-CsClsLogging“ die Ergebnisse der Suche an die Konsole gesendet.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="f1ba1-129">Wenn Sie die Suchergebnisse in einer Datei speichern möchten, verwenden Sie-OutputFilePath _ \<Zeichenfolge vollqualifizierter\>Dateipfad_.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="f1ba1-130">Um den Parameter-OutputFilePath zu definieren, geben Sie einen Pfad und einen Dateinamen als Teil des Parameters in einem in Anführungszeichen eingeschlossenen Zeichenfolgenformat an (beispielsweise; C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="f1ba1-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="f1ba1-131">In diesen Beispiel müssen Sie sicherstellen, dass das Verzeichnis „C:\LogFiles“ vorhanden ist und Sie über Lese- und Schreibberechtigungen (NTFS-Berechtigungen) für Dateien in diesem Ordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="f1ba1-132">An die Ausgabe werden immer Daten angefügt, sie wird nicht überschrieben.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="f1ba1-133">Wenn Sie separate Dateien benötigen, geben Sie unterschiedliche Dateinamen für die einzelnen Suchvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="f1ba1-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="f1ba1-135">So führen Sie eine einfache Suche in einem Pool oder Computer mithilfe des zentralen Protokollierungsdiensts aus</span><span class="sxs-lookup"><span data-stu-id="f1ba1-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="f1ba1-136">Wenn Sie die Suche auf einen bestimmten Pool oder Computer einschränken möchten, verwenden Sie den-Computers-Parameter mit dem Computer, der durch einen vollqualifizierten Computernamen definiert ist, in Anführungszeichen eingeschlossen und wie folgt durch ein Komma getrennt:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="f1ba1-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="f1ba1-138">Geben Sie zum Suchen auf mehreren Computern mehrere Computernamen in Anführungszeichen und durch Komma getrennt ein:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="f1ba1-139">Wenn Sie einen gesamten Pool anstelle eines einzelnen Computers durchsuchen müssen, ändern Sie den Parameter-Computer in-Pools, entfernen Sie den Computernamen, und ersetzen Sie ihn durch den Pool oder die Pools in Anführungszeichen durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="f1ba1-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="f1ba1-141">Bei Verwendung der Suchbefehle können Pools in Ihrer Bereitstellung ein beliebiger Pool sein, beispielsweise Front-End-Pools, Edge-Pools, persistent Chat-Server Pools oder andere, die in Ihrer Bereitstellung als Pool definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="f1ba1-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="f1ba1-143">So führen Sie eine Suche mithilfe von Zeitparametern aus</span><span class="sxs-lookup"><span data-stu-id="f1ba1-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="f1ba1-144">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f1ba1-145">Standardmäßig liegt die Startzeit für die zeitspezifischen Parameter einer Suche 25 Minuten vor bis fünf Minuten nach der Zeit, zu der die Suche gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="f1ba1-146">Mit anderen Worten: Wenn die Suche um 16:00 Uhr gestartet wird, wird als Startzeit der Suche 15:35 Uhr bis 16:05 Uhr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="f1ba1-147">Wenn Sie 60 Minuten oder 3 Stunden vor der aktuellen Uhrzeit suchen müssen, verwenden Sie den-startTime-Parameter, und legen Sie die Datums-und Uhrzeitzeichenfolge fest, um die Uhrzeit anzugeben, zu der die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="f1ba1-148">Wenn Sie beispielsweise-StartTime und-EndTime verwenden, um einen Zeit-und Datumsbereich zu definieren, können Sie eine Suche zwischen 8 und 9 Uhr auf 11/20/2012 im Pool definieren.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="f1ba1-149">Sie können den Ausgabepfad angeben, sodass die Ergebnisse folgendermaßen in eine Datei namens „c:\logfile.txt“ geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="f1ba1-150">Die angegebene Uhrzeit- und Datumszeichenfolge kann „Datum Uhrzeit“ oder „Uhrzeit Datum“ lauten.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="f1ba1-151">"Der Befehl analysiert die Zeichenfolge und verwendet die entsprechenden Werte für Datum und Uhrzeit sowie ihre Gebietsschema-und Kultureinstellungen auf dem Computer, aus dem Sie das Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="f1ba1-152">Wenn Sie die Protokolle ab 11:00:00 am 11/20/2012 abrufen möchten, definieren Sie die Startzeit.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="f1ba1-153">Der standardmäßige Zeitbereich für die Suche beträgt 30 Minuten, es sei denn, Sie definieren einen bestimmten-EndTime.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="f1ba1-154">Die Suche gibt Protokolle der festgelegten Computer oder Pools aus dem Zeitraum von 11:00 Uhr bis 11:30 Uhr zurück.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="f1ba1-155">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="f1ba1-156">Wenn Sie eine Suche nach Protokollen innerhalb eines bestimmten Zeitraums durchführen möchten, definieren Sie a-StartTime und a-EndTime.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="f1ba1-157">Sie benötigen Protokolle für den Zeitraum zwischen 13 und 14:45 Uhr auf dem Computer „edge01.contoso.net“.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="f1ba1-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="f1ba1-159">So führen Sie mithilfe weiterer Kriterien und Abgleichungsoptionen eine erweiterte Suche aus</span><span class="sxs-lookup"><span data-stu-id="f1ba1-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="f1ba1-160">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f1ba1-161">Geben Sie zum Ausführen eines Befehls zum Erfassen von Ablaufverfolgungen für bestimmte Komponenten Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="f1ba1-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="f1ba1-163">Die Suche gibt alle Protokolleinträge zurück, die Ablaufverfolgungskomponenten für SIPStack, S4 und UserServices für alle Computer und Pools in Ihrer Bereitstellung in den letzten 30 Minuten enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="f1ba1-164">Wenn Sie die Suche auf die gleichen Komponenten nur auf Ihren Front-End-Pool mit dem Namen pool01.contoso.net beschränken möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="f1ba1-165">Die Standardsuchlogik für Befehle mit mehreren Parametern besteht darin, das logische „Oder“ mit den einzelnen definierten Parametern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="f1ba1-166">Sie können dieses Verhalten ändern, indem Sie den Parameter **-MatchAll** angeben.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="f1ba1-167">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="f1ba1-p114">Wenn Ihre Szenarien für eine ständige Ausführung festgelegt sind (wie AlwaysOn) oder wenn Sie ein langfristiges Szenario festgelegt haben, werden Protokolle möglicherweise vom lokalen Computer auf die Dateifreigabe verschoben. Sie legen die Dateifreigabe  mithilfe des Parameters „CacheFileNetworkFolder“ fest, um mithilfe von „New-CsClsConfiguration“ eine neue Konfiguration zu erstellen oder mithilfe von „Set-CsClsConfiguration“ eine vorhandene Konfiguration zu ändern. Wenn die Dateifreigabe in der Auflistung der zu durchsuchenden Protokolle nicht durchsucht werden soll, verwenden Sie den Parameter „SkipNetworkLogs“ folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="f1ba1-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="f1ba1-171">Lesen von Erfassungsprotokollen aus dem zentralisierten Protokollierungsdienst</span><span class="sxs-lookup"><span data-stu-id="f1ba1-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="f1ba1-172">Sie erkennen den wirklichen Vorteil des zentralen Protokollierungsdiensts, nachdem Sie die Suche ausgeführt haben, und Sie verfügen über eine Datei, mit der Sie ein gemeldetes Problem nachvollziehen können.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="f1ba1-173">Es gibt eine Reihe von Möglichkeiten, wie Sie die Datei lesen können.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="f1ba1-174">Die Ausgabedatei befindet sich in einem Standardtextformat, und Sie können Notepad. exe oder alle anderen Programme verwenden, die es Ihnen ermöglichen, eine Textdatei zu öffnen und zu lesen.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="f1ba1-175">Für größere Dateien und komplexere Probleme können Sie ein Tool wie Snooper. exe verwenden, das zum Lesen und Analysieren der Protokollierungsausgabe vom zentralen Protokollierungsdienst entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="f1ba1-176">Snooper ist im Lieferumfang der Debug-Tools enthalten, die als separater Download zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="f1ba1-177">Sie können die Debug-Tools hier herunter [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)laden:.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="f1ba1-178">Wenn Sie die Debug-Tools installieren, werden keine kurzen Schnitte und Menüelemente erstellt.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="f1ba1-179">Nachdem Sie die Debug-Tools installiert haben, öffnen Sie den Windows-Explorer, ein Befehlszeilenfenster oder die Skype for Business Server-Verwaltungsshell, und wechseln Sie zum Verzeichnis (Standardspeicherort) C:\Program Files\Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="f1ba1-180">Doppelklicken Sie auf Snooper. exe, oder geben Sie Snooper. exe ein, und drücken Sie dann die EINGABETASTE, wenn Sie die Befehlszeile oder die Skype for Business Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f1ba1-181">In diesem Thema sollen keine Problembehandlungstechniken beschrieben und behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="f1ba1-182">Die Problembehandlung und die damit verbundenen Prozesse sind ein komplexes Thema.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="f1ba1-183">Details zu den Grundlagen der Problembehandlung und zur Problembehandlung bei bestimmten Arbeitslasten finden Sie im Microsoft lync [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Server 2010 Resource Kit-Handbuch unter.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="f1ba1-184">Die Prozesse und Verfahren gelten weiterhin für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="f1ba1-185">So öffnen Sie eine Protokolldatei in Snooper</span><span class="sxs-lookup"><span data-stu-id="f1ba1-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="f1ba1-p117">Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="f1ba1-188">Nach der Installation der Debugtools („LyncDebugTools.msi“) wechseln Sie in Windows Explorer oder in der Befehlszeile zum Verzeichnis, in dem „Snooper.exe“ gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="f1ba1-189">Standardmäßig befinden sich die Debug-Tools unter C:\Program Files\Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="f1ba1-190">Führen Sie „Snooper.exe“ mittels Doppelklick aus.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="f1ba1-191">Nachdem Snooper geöffnet wurde, klicken Sie mit der rechten Maustaste auf **File** (Datei), klicken Sie auf **OpenFile** (Datei öffnen), suchen Sie nach Ihren Protokolldateien, wählen Sie eine Datei im Dialogfeld **Open** (Öffnen) aus und klicken Sie dann auf **Open** (Öffnen).</span><span class="sxs-lookup"><span data-stu-id="f1ba1-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="f1ba1-192">Die **Ablauf Verfolgungs** Meldungen der Protokolldatei werden auf der Registerkarte **Ablaufverfolgung** angezeigt. Klicken Sie auf die Registerkarte **Nachrichten** , um den Nachrichteninhalt der gesammelten Ablaufverfolgungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="f1ba1-193">So zeigen Sie ein Anrufflussdiagramm an</span><span class="sxs-lookup"><span data-stu-id="f1ba1-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="f1ba1-p119">Zum Öffnen von Protokolldateien mithilfe von Snooper benötigen Sie Lesezugriff für die Protokolldateien. Für den Zugriff auf die Protokolldateien mithilfe von Snooper müssen Sie ein Mitglied der rollenbasierten Zugriffssteuerungs-Sicherheitsgruppe „CsAdministrator“ oder „CsServerAdministrator“ oder einer benutzerdefinierten rollenbasierten Zugriffssteuerungsrolle sein, die eine dieser beiden Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="f1ba1-196">Öffnen Sie eine Protokolldatei und klicken Sie auf die Registerkarte **Messages** (Nachrichten), wählen Sie eine Unterhaltung in der Nachrichtenansicht aus oder wählen Sie eine Ablaufverfolgungskomponente auf der Registerkarte **Trace** (Ablaufverfolgung) aus.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="f1ba1-197">Klicken Sie auf **Call Flow** (Anruffluss).</span><span class="sxs-lookup"><span data-stu-id="f1ba1-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f1ba1-198">Wenn Sie auf eine Nachricht oder eine Ablaufverfolgung klicken, die nicht Teil eines Anrufflusses ist, wird das Diagramm nicht angezeigt, und unten in Snooper wird eine Statusmeldung angezeigt, die besagt, dass "diese Nachricht nicht für callfow geeignet ist".</span><span class="sxs-lookup"><span data-stu-id="f1ba1-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="f1ba1-199">Wählen Sie eine andere Nachricht oder Ablaufverfolgung aus, und der Anruffluss wird angezeigt, wenn die Nachricht oder Ablaufverfolgung Teil eines Anrufflusses ist.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="f1ba1-200">Navigieren Sie in den Nachrichten oder Ablaufverfolgungszeilen und überprüfen Sie, ob das Anrufflussdiagramm aktualisiert oder geändert und ein neues Diagramm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="f1ba1-201">Zeigen Sie auf Elemente, um Informationen zu Anrufnachrichten, Endpunkten und sonstigen Komponenten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f1ba1-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
