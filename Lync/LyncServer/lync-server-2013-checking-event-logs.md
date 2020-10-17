---
title: 'Lync Server 2013: Überprüfen von Ereignisprotokollen'
description: 'Lync Server 2013: Überprüfen der Ereignisprotokolle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6617bde846fd38ab3282fd023b16e0a921f48920
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570981"
---
# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="8de7c-103">Überprüfen von Ereignisprotokollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8de7c-103">Checking event logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8de7c-104">_**Letztes Änderungsstand des Themas:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="8de7c-104">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="8de7c-105">Sie können die [Windows-Ereignisanzeige](https://go.microsoft.com/fwlink/p/?linkid=314067) verwenden, um Ereignisprotokolle anzuzeigen und Informationen zu Dienstfehlern, Replikationsfehlern im AD DS und Warnungen zu Systemressourcen wie virtuellem Arbeitsspeicher und Speicherplatz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8de7c-105">You can use [Windows Event Viewer](https://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="8de7c-106">Die Ereignisanzeige ist in Windows Server 2008 und 2012 enthalten.</span><span class="sxs-lookup"><span data-stu-id="8de7c-106">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="8de7c-107">Wenn Sie im lync Server 2013 Protokollierungstool die Debugsitzung beenden, klicken Sie auf **Protokolldateien analysieren** , um die Protokolldateien mithilfe des Tools Snooper anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8de7c-107">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="8de7c-108">Die Ereignisanzeige verwaltet Protokolle zu Anwendungs-, Sicherheits-und Systemereignissen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="8de7c-108">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="8de7c-109">Sowohl lync Server 2013 als auch Windows melden Warnungen und Fehlerbedingungen für die Ereignisprotokolle.</span><span class="sxs-lookup"><span data-stu-id="8de7c-109">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="8de7c-110">Überprüfen Sie daher die Ereignisprotokolle täglich.</span><span class="sxs-lookup"><span data-stu-id="8de7c-110">Therefore, review event logs daily.</span></span>

<span data-ttu-id="8de7c-111">Verwenden Sie die Ereignisanzeige für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8de7c-111">Use Event Viewer to:</span></span>

  - <span data-ttu-id="8de7c-112">Anzeigen und Verwalten von Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="8de7c-112">View and manage event logs.</span></span>

  - <span data-ttu-id="8de7c-113">Erhalten Sie Informationen zu Hardware-, Software-und Systemproblemen, die behoben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8de7c-113">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="8de7c-114">Identifizieren Sie Trends, die zukünftige Aktionen erfordern.</span><span class="sxs-lookup"><span data-stu-id="8de7c-114">Identify trends that require future action.</span></span>

<span data-ttu-id="8de7c-115">Ein Server, auf dem lync Server auf einem Windows Server-Betriebssystem läuft, zeichnet Ereignisse in vier Protokolltypen auf:</span><span class="sxs-lookup"><span data-stu-id="8de7c-115">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="8de7c-116">**Anwendungsprotokolle**     Das Anwendungsprotokoll enthält Ereignisse, die von Anwendungen oder Programmen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="8de7c-116">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="8de7c-117">Entwickler legen fest, welche Ereignisse protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="8de7c-117">Developers determine which events to log.</span></span> <span data-ttu-id="8de7c-118">Ein Datenbankprogramm könnte z. B. einen Dateifehler im Anwendungsprotokoll aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="8de7c-118">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="8de7c-119">Die meisten lync Server 2013 bezogenen Ereignisse werden im Anwendungsprotokoll angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8de7c-119">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="8de7c-120">**Sicherheitsprotokolle**     Das Sicherheitsprotokoll zeichnet Ereignisse wie gültige und ungültige Anmeldeversuche zusätzlich zu Ereignissen im Zusammenhang mit der Ressourcenverwendung wie erstellen, öffnen oder Löschen von Dateien oder anderen Objekten auf.</span><span class="sxs-lookup"><span data-stu-id="8de7c-120">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="8de7c-121">Wenn Anmeldeüberwachung aktiviert ist, werden z. B. Anmeldeversuche am System im Sicherheitsprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8de7c-121">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="8de7c-122">**System Protokolle**     Das Systemprotokoll enthält Ereignisse, die von Windows-Systemkomponenten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="8de7c-122">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="8de7c-123">Der Ladefehler eines Treibers oder einer anderen Systemkomponente während des Startvorgangs wird z. B. im Systemprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8de7c-123">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="8de7c-124">Die von Systemkomponenten protokollierten Ereignistypen werden von Server im Vorfeld festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8de7c-124">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="8de7c-125">**Lync Server 2013**     Das Protokollierungstool zeichnet wichtige Ereignisse im Zusammenhang mit Authentifizierung, Verbindungen und Benutzeraktionen auf.</span><span class="sxs-lookup"><span data-stu-id="8de7c-125">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="8de7c-126">Nachdem Sie die Diagnoseprotokollierung aktiviert haben, können Sie die Protokolleinträge in der Ereignisanzeige anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8de7c-126">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8de7c-127">Es wird nicht empfohlen, die maximalen Protokollierungseinstellungen zu verwenden, es sei denn, Sie werden vom Microsoft-Kundendienst dazu aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8de7c-127">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="8de7c-128">Die maximale Protokollierung entwässert erhebliche Ressourcen und kann viele "falsch positive Ergebnisse" verursachen, also Fehler, die nur bei der maximalen Protokollierung protokolliert werden, aber wirklich erwartet werden und keine Anlass zur Besorgnis geben.</span><span class="sxs-lookup"><span data-stu-id="8de7c-128">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="8de7c-129">Außerdem wird empfohlen, die Diagnoseprotokollierung nicht dauerhaft zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8de7c-129">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="8de7c-130">Verwenden Sie sie nur zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="8de7c-130">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="8de7c-131">In den einzelnen Protokollen der Ereignisanzeige erfasst lync Server 2013 Informationen, Warnungen und Fehlerereignisse.</span><span class="sxs-lookup"><span data-stu-id="8de7c-131">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="8de7c-132">Überwachen Sie diese Protokolle eng, um die Transaktionstypen nachzuverfolgen, die auf den lync Server 2013 Servern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8de7c-132">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="8de7c-133">Sie sollten die Protokolle in regelmäßigen Abständen archivieren oder die automatische Rolloverfunktion verwenden, damit stets ausreichend Speicherplatz vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8de7c-133">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="8de7c-134">Da Protokolldateien eine begrenzte Menge an Speicherplatz belegen können, müssen Sie die Protokollgröße vergrößern (beispielsweise auf 50 MB) und diese auf Overwrite festlegen, damit der lync Server 2013 Server weiterhin neue Ereignisse schreiben kann.</span><span class="sxs-lookup"><span data-stu-id="8de7c-134">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="8de7c-135">Sie können die Ereignisprotokollverwaltung auch mithilfe der folgenden Tools und Technologien automatisieren:</span><span class="sxs-lookup"><span data-stu-id="8de7c-135">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="8de7c-136">System Center Operations Manager überwacht die Integrität und die Verwendung von lync Server 2013 Servern.</span><span class="sxs-lookup"><span data-stu-id="8de7c-136">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="8de7c-137">Lync Server 2013 Management Pack für Operations Manager erweitert Operations Manager durch die Bereitstellung spezieller Überwachung für Server, auf denen lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8de7c-137">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="8de7c-138">Das lync Server 2013 Management Pack für Operations Manager überwacht Standard-und Enterprise Edition von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8de7c-138">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="8de7c-139">In dieser Version ist auch das QoE-Management Pack (Quality of Experience) integriert, das zuvor ein separates Management Pack war.</span><span class="sxs-lookup"><span data-stu-id="8de7c-139">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="8de7c-140">Überwachte Typen sind Ereignisprotokolleinträge, Leistungsindikatoren und Stateful-Überwachung von QoE.</span><span class="sxs-lookup"><span data-stu-id="8de7c-140">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="8de7c-141">Diese Version des Management Packs überwacht nur lync Server 2013 und 2010 und kann nicht zum Überwachen von Office Communications Server 2007 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8de7c-141">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="8de7c-142">Das Management Pack bietet die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="8de7c-142">The management pack provides the following features:</span></span>

  - <span data-ttu-id="8de7c-143">Warnungen, die den Dienst beeinflussen, der Ereignisse angibt</span><span class="sxs-lookup"><span data-stu-id="8de7c-143">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="8de7c-144">Warnungen, die die Konfiguration und andere Probleme mit nicht-Dienst Auswirkungen betreffen</span><span class="sxs-lookup"><span data-stu-id="8de7c-144">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="8de7c-145">Statusüberwachung von lync Server Diensten</span><span class="sxs-lookup"><span data-stu-id="8de7c-145">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="8de7c-146">Produkt wissen: Ursache und Lösung identifizierter Probleme</span><span class="sxs-lookup"><span data-stu-id="8de7c-146">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="8de7c-147">Weitere Informationen zu lync Server 2013 Management Pack finden Sie unter [Monitoring lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8de7c-147">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="8de7c-148">**Ereignis Kamm**     Das Tool Event Comb sammelt bestimmte Ereignisse aus den Ereignisprotokollen mehrerer Computer an einem zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="8de7c-148">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="8de7c-149">Sie können nur die Ereignis-IDs oder Ereignisquellen melden, die es angibt.</span><span class="sxs-lookup"><span data-stu-id="8de7c-149">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="8de7c-150">Weitere Informationen zum Ereignis Kamm finden Sie auf der Website für [Kontosperrung und Verwaltungs Tools](https://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="8de7c-150">For more information about Event Comb, see the [Account Lockout and Management Tools](https://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="8de7c-151">**Ereignisauslöser**     In Windows Server 2012 können Sie "eine Aufgabe an dieses Ereignis anfügen" in der Windows-Ereignisanzeige, bei der ein Administrator entweder ein Programm ausführen, eine e-Mail-Nachricht senden oder eine Bildschirm Nachricht anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="8de7c-151">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="8de7c-152">Weitere Informationen zu diesem Feature finden Sie im Windows Server 2008 R2 Thema [Ausführen einer Aufgabe als Reaktion auf ein bestimmtes Ereignis](https://technet.microsoft.com/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="8de7c-152">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](https://technet.microsoft.com/library/cc748900.aspx).</span></span> <span data-ttu-id="8de7c-153">Sie können auch Befehlszeilentools wie "Eventtrigger.exe" zum Erstellen und Abfragen von Ereignisprotokollen und zum Zuordnen von Programmen zu bestimmten protokollierten Ereignissen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8de7c-153">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="8de7c-154">Mithilfe Eventtriggers.exe können Sie Ereignisauslöser erstellen, die Programme ausführen, wenn bestimmte Ereignisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="8de7c-154">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8de7c-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8de7c-155">See Also</span></span>


[<span data-ttu-id="8de7c-156">Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="8de7c-156">Windows Event Viewer</span></span>](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

