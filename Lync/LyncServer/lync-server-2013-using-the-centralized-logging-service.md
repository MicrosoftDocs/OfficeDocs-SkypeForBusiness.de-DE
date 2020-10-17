---
title: 'Lync Server 2013: Verwenden des zentralisierten Protokollierungsdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 276cc87d6ec943332fc30dc21c0906a03703382d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529952"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="f258a-102">Verwenden des zentralisierten Protokollierungsdiensts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f258a-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f258a-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f258a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f258a-104">Der zentralisierte Protokollierungsdienst ist ein neues Feature in lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f258a-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="f258a-105">Er stellt einen verbesserten Ersatz für die beiden Tools **OCSLogger** und **OCSTracer** dar, die in den vorherigen Versionen enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="f258a-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="f258a-106">Sie können den zentralisierten Protokollierungsdienst verwenden, um die folgenden Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f258a-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="f258a-107">Starten der Protokollierung für einen oder mehrere Computer und Pools über einen einzelnen Standort und Befehl.</span><span class="sxs-lookup"><span data-stu-id="f258a-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="f258a-108">Beenden der Protokollierung für einen oder mehrere Computer und Pools über einen einzelnen Standort und Befehl.</span><span class="sxs-lookup"><span data-stu-id="f258a-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="f258a-p102">Durchsuchen von Protokollen auf einen oder mehreren Computern und in einem oder mehreren Pools nach einem einzelnen Standort und Befehl. Sie können den Suchbefehl anpassen, um die gesamten zusammengefassten Protokolle, die auf allen Computern aufgezeichnet und gespeichert wurden, zurückzugeben, oder um ein reduziertes Suchergebnis zu erhalten, in dem nur bestimmte Daten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f258a-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="f258a-111">Konfigurieren Sie die Protokollierungssitzungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f258a-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="f258a-112">Definieren Sie ein **Szenario**, oder verwenden Sie ein Standardszenario.</span><span class="sxs-lookup"><span data-stu-id="f258a-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="f258a-113">Ein *Szenario* im zentralisierten Protokollierungsdienst besteht aus dem Bereich (Global oder Standort), einem Szenarionamen zur Identifizierung des Zwecks des Szenarios und einem oder mehreren Anbietern.</span><span class="sxs-lookup"><span data-stu-id="f258a-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="f258a-114">Auf einem Computer können gleichzeitig jeweils zwei Szenarien ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f258a-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="f258a-p104">Sie können einen vorhandenen *Anbieter* verwenden oder einen neuen Anbieter erstellen. Der *Anbieter* definiert, was bei der Protokollierungssitzung erfasst wird, welche Detailebene gilt, welche Komponenten nachverfolgt werden und welche Flags angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f258a-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="f258a-117">Wenn Sie mit der Verwendung von OCSLogger vertraut sind: Der Begriff <EM>Anbieter</EM> bezieht sich auf die Sammlung der <STRONG>Komponenten</STRONG> (z. B. S4, SIPStack), einen <STRONG>Protokollierungstyp</STRONG> (z. B. WPP, EventLog oder IIS logfile), eine <STRONG>Ablaufverfolgungsstufe</STRONG> (z. B. All, verbose, debug) sowie <STRONG>Flags</STRONG> (z. B. TF_COMPONENT, TF_DIAG).</span><span class="sxs-lookup"><span data-stu-id="f258a-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="f258a-118">Diese Elemente werden im Anbieter definiert (eine Windows PowerShell Variable) und an den Befehl für den zentralisierten Protokollierungsdienst übergeben.</span><span class="sxs-lookup"><span data-stu-id="f258a-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="f258a-119">Konfigurieren Sie die Computer und Pools, von denen Sie Protokolle erfassen möchten.</span><span class="sxs-lookup"><span data-stu-id="f258a-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="f258a-120">Definieren Sie den Bereich der Protokollierungssitzung unter Verwendung der Optionen **Standort** (Ausführung der Protokollierungsaufzeichnung erfolgt nur auf Computern an diesem Standort) bzw. **Global** (Ausführung der Protokollierungsaufzeichnung erfolgt auf allen Computern in der Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="f258a-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="f258a-121">Der zentralisierte Protokollierungsdienst ist äußerst leistungsfähig und kann nahezu alle Anforderungen für Problem Behandlungs Probleme erfüllen – groß oder klein.</span><span class="sxs-lookup"><span data-stu-id="f258a-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="f258a-122">Von der Ursachenanalyse bis hin zu Leistungsproblemen kann der zentralisierte Protokollierungsdienst ein wichtiges Tool für jeden Administrator sein.</span><span class="sxs-lookup"><span data-stu-id="f258a-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="f258a-123">Alle Beispiele werden mit dem lync Server-Verwaltungsshell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f258a-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="f258a-124">Es gibt eine Befehlszeilenkomponente für den zentralisierten Protokollierungsdienst namens **CLSController.exe**.</span><span class="sxs-lookup"><span data-stu-id="f258a-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="f258a-125">Die Hilfe zum Befehlszeilentool wird über das Tool selbst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f258a-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="f258a-126">Über die Befehlszeile kann jedoch nur eine beschränkte Anzahl an Funktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f258a-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="f258a-127">Durch die Verwendung von lync Server-Verwaltungsshell haben Sie Zugriff auf eine viel größere und viel mehr konfigurierbare Gruppe von Features.</span><span class="sxs-lookup"><span data-stu-id="f258a-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="f258a-128">Wenn Sie den zentralisierten Protokollierungsdienst verwenden, sollten Sie lync Server-Verwaltungsshell immer als die erste und wichtigste Methode berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f258a-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="f258a-129">In den Themen in diesem Abschnitt wird erklärt, wie der zentralisierte Protokollierungsdienst und Beispiele für die Verwendung der zahlreichen Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f258a-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f258a-130">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f258a-130">In This Section</span></span>

  - [<span data-ttu-id="f258a-131">Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f258a-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="f258a-132">Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f258a-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="f258a-133">Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f258a-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="f258a-134">Verwenden von Start für den zentralisierten Protokollierungsdienst zum Erfassen von Protokollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f258a-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="f258a-135">Verwenden von Stop für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f258a-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="f258a-136">Verwenden der Suche in den vom zentralisierten Protokollierungsdienst in lync Server 2013 erstellten Aufzeichnungs Protokollen</span><span class="sxs-lookup"><span data-stu-id="f258a-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="f258a-137">Lesen von Erfassungs Protokollen aus dem zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f258a-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

