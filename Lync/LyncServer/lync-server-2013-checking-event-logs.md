---
title: 'Lync Server 2013: Überprüfen von Ereignisprotokollen'
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
ms.openlocfilehash: 862d419d9db5d8465b3507c40fde32acd01bb659
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="fb8c4-102">Überprüfen von Ereignisprotokollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb8c4-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb8c4-103">_**Letztes Änderungsdatum des Themas:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="fb8c4-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="fb8c4-104">Sie können die [Windows-Ereignisanzeige](http://go.microsoft.com/fwlink/p/?linkid=314067) verwenden, um Ereignisprotokolle anzuzeigen und Informationen zu Dienstfehlern, Replikationsfehlern in AD DS sowie Warnungen zu Systemressourcen wie virtuellem Arbeitsspeicher und Speicherplatz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="fb8c4-105">Die Ereignisanzeige ist im Lieferumfang von Windows Server 2008 und 2012 enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="fb8c4-106">Klicken Sie im lync Server 2013-Protokollierungstool beim Beenden der Debugsitzung auf **Protokolldateien analysieren** , um die Protokolldateien mithilfe des Snooper-Tools anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="fb8c4-107">Die Ereignisanzeige verwaltet Protokolle zu Anwendungs-, Sicherheits-und Systemereignissen auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="fb8c4-108">Sowohl lync Server 2013 als auch Windows melden Warnungen und Fehlerbedingungen für die Ereignisprotokolle.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="fb8c4-109">Überprüfen Sie daher die Ereignisprotokolle täglich.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="fb8c4-110">Verwenden Sie die Ereignisanzeige für folgende Zwecke:</span><span class="sxs-lookup"><span data-stu-id="fb8c4-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="fb8c4-111">Anzeigen und Verwalten von Ereignisprotokollen</span><span class="sxs-lookup"><span data-stu-id="fb8c4-111">View and manage event logs.</span></span>

  - <span data-ttu-id="fb8c4-112">Abrufen von Informationen zu Hardware-, Software-und Systemproblemen, die aufgelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="fb8c4-113">Erkennen von Trends, die eine zukünftige Aktion erfordern</span><span class="sxs-lookup"><span data-stu-id="fb8c4-113">Identify trends that require future action.</span></span>

<span data-ttu-id="fb8c4-114">Ein Server, auf dem lync Server unter einem Windows Server-Betriebssystem ausgeführt wird, zeichnet Ereignisse in vier Typen von Protokollen auf:</span><span class="sxs-lookup"><span data-stu-id="fb8c4-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="fb8c4-115">**Anwendungsprotokolle**   das Anwendungsprotokoll enthält Ereignisse, die von Anwendungen oder Programmen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="fb8c4-116">Entwickler legen fest, welche Ereignisse protokolliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-116">Developers determine which events to log.</span></span> <span data-ttu-id="fb8c4-117">Beispielsweise kann ein Datenbankprogramm einen Datei Fehler im Anwendungsprotokoll aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="fb8c4-118">Die meisten Ereignisse im Zusammenhang mit lync Server 2013 werden im Anwendungsprotokoll angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="fb8c4-119">**Sicherheitsprotokolle**   das Sicherheitsprotokoll zeichnet Ereignisse wie gültige und ungültige Anmeldeversuche zusätzlich zu Ereignissen auf, die sich auf die Ressourcennutzung beziehen, wie das Erstellen, öffnen oder Löschen von Dateien oder anderen Objekten.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="fb8c4-120">Wenn beispielsweise die Anmeldeüberwachung aktiviert ist, werden Versuche zur Anmeldung am System im Sicherheitsprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="fb8c4-121">**Systemprotokolle**   das Systemprotokoll enthält Ereignisse, die von Windows-Systemkomponenten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="fb8c4-122">Beispielsweise wird der Fehler eines Treibers oder einer anderen Systemkomponente zum Laden während des Starts im Systemprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="fb8c4-123">Die von Systemkomponenten protokollierten Ereignistypen sind vom Server vorgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="fb8c4-124">**Lync Server 2013**   das Protokollierungstool zeichnet wichtige Ereignisse auf, die sich auf Authentifizierung, Verbindungen und Benutzeraktionen beziehen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="fb8c4-125">Nachdem Sie die Diagnoseprotokollierung aktiviert haben, können Sie die Protokolleinträge in der Ereignisanzeige anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb8c4-126">Es wird nicht empfohlen, die maximalen Protokollierungseinstellungen zu verwenden, es sei denn, Sie werden von den Microsoft-Kundendienst angewiesen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="fb8c4-127">Die maximale Protokollierung führt zu erheblichen Ressourcen und kann viele "falsch positive" geben, das heißt, Fehler, die nur bei maximaler Protokollierung protokolliert werden, aber wirklich erwartet werden und keine Besorgnis erregend sind.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="fb8c4-128">Wir empfehlen außerdem, die Diagnoseprotokollierung nicht dauerhaft zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="fb8c4-129">Verwenden Sie es nur bei der Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="fb8c4-130">In jedem Ereignisanzeigeprotokoll zeichnet lync Server 2013 Informations-, Warnungs-und Fehlerereignisse auf.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="fb8c4-131">Überwachen Sie diese Protokolle genau, um die Typen von Transaktionen zu verfolgen, die auf den lync Server 2013-Servern durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="fb8c4-132">Sie sollten die Protokolle in regelmäßigen Abständen archivieren oder das automatische Rollover verwenden, um nicht genügend Speicherplatz zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="fb8c4-133">Da Protokolldateien eine begrenzte Menge an Speicherplatz belegen können, erhöhen Sie die Protokollgröße (beispielsweise auf 50 MB), und legen Sie Sie auf Overwrite fest, damit der lync Server 2013-Server weiterhin neue Ereignisse schreiben kann.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="fb8c4-134">Sie können die Ereignisprotokollverwaltung auch mithilfe der folgenden Tools und Technologien automatisieren:</span><span class="sxs-lookup"><span data-stu-id="fb8c4-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="fb8c4-135">System Center Operations Manager überwacht den Zustand und die Verwendung von lync Server 2013-Servern.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="fb8c4-136">Das lync Server 2013 Management Pack für Operations Manager erweitert Operations Manager durch die Bereitstellung spezieller Überwachung für Server, auf denen lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="fb8c4-137">Das lync Server 2013-Management Pack für Operations Manager überwacht die Standard-und Enterprise-Edition von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="fb8c4-138">Diese Version enthält auch das QoE-Management Pack (Quality of Experience), das zuvor ein separates Management Pack war.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="fb8c4-139">Überwachte Typen sind Ereignisprotokolleinträge, Leistungsindikatoren und statusbehaftete Überwachung von QoE.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="fb8c4-140">Diese Version des Management Packs überwacht nur lync Server 2013 und 2010 und kann nicht zum Überwachen von Office Communications Server 2007 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="fb8c4-141">Das Management Pack bietet die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="fb8c4-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="fb8c4-142">Benachrichtigungen, die darauf hindeuten, dass der Dienst Auswirkungen auf Ereignisse hat</span><span class="sxs-lookup"><span data-stu-id="fb8c4-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="fb8c4-143">Warnungen, die die Konfiguration angeben, und andere Probleme, die sich nicht auf Dienste auswirken</span><span class="sxs-lookup"><span data-stu-id="fb8c4-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="fb8c4-144">Statusüberwachung der lync Server-Dienste</span><span class="sxs-lookup"><span data-stu-id="fb8c4-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="fb8c4-145">Produkt wissen: Ursache und Lösung identifizierter Probleme</span><span class="sxs-lookup"><span data-stu-id="fb8c4-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="fb8c4-146">Weitere Informationen zum lync Server 2013 Management Pack finden Sie unter über [Wachen von lync Server 2013 mit System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fb8c4-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="fb8c4-147">**Ereignis Kamm**   mit dem Event Comb-Tool werden bestimmte Ereignisse aus den Ereignisprotokollen von mehreren Computern an einem zentralen Speicherort erfasst.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="fb8c4-148">Damit können Sie nur die Ereignis-IDs oder Ereignisquellen melden, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="fb8c4-149">Weitere Informationen zum Event Comb finden Sie auf der Website [Kontosperrung und Verwaltungs Tools](http://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="fb8c4-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="fb8c4-150">**Ereignisauslöser**   in Windows Server 2012 Sie können "eine Aufgabe an dieses Ereignis anfügen" in der Windows-Ereignisanzeige, in der ein Administrator entweder ein Programm ausführen, eine e-Mail-Nachricht senden oder eine auf dem Bildschirm angezeigte Nachricht anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="fb8c4-151">Weitere Informationen zu diesem Feature finden Sie unter Windows Server 2008 R2-Thema [Ausführen einer Aufgabe als Antwort auf ein bestimmtes Ereignis](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb8c4-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="fb8c4-152">Sie können auch Befehlszeilentools wie "EventTrigger. exe" verwenden, um Ereignisprotokolle zu erstellen und zu Abfragen und Programme mit bestimmten protokollierten Ereignissen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="fb8c4-153">Mit Eventtriggers. exe können Sie Ereignisauslöser erstellen, die Programme ausführen, wenn bestimmte Ereignisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="fb8c4-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fb8c4-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb8c4-154">See Also</span></span>


[<span data-ttu-id="fb8c4-155">Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="fb8c4-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

