---
title: 'Lync Server 2013: Poster: wichtige Integritätsindikatoren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="ad184-102">Wichtige Integritätsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad184-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad184-103">_**Letztes Änderungsdatum des Themas:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="ad184-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="ad184-104">Dieser Artikel ist ein Begleiter zu den [wichtigsten Integritätsindikatoren: die Grundlage für die Verwaltung eines fehlerfreien lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) -Plakats, das Sie aus dem Download Center herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="ad184-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="ad184-105">Poster, das die ![Problembehandlung mithilfe von KHI-Daten beschreibt] Poster, das die (images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Problembehandlung mithilfe von KHI-Daten beschreibt")</span><span class="sxs-lookup"><span data-stu-id="ad184-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="ad184-106">Sie können dieses Poster verwenden, um Informationen zu wichtigen Integritätsindikatoren (KHIs), Leistungsindikatoren mit Schwellenwerten für die Anzeige von Problemen mit der Benutzeroberfläche zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ad184-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="ad184-107">Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Methode für die Anrufqualität (Call Quality Method, CQM), die auf die Gewährleistung einer Audioqualität für lync-Benutzer ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ad184-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="ad184-108">Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com senden.</span><span class="sxs-lookup"><span data-stu-id="ad184-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="ad184-109">Das Poster erläutert die folgenden Bereiche:</span><span class="sxs-lookup"><span data-stu-id="ad184-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="ad184-110">Was sind die wichtigsten Statusindikatoren?</span><span class="sxs-lookup"><span data-stu-id="ad184-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="ad184-111">So erfassen Sie KHI-Daten</span><span class="sxs-lookup"><span data-stu-id="ad184-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="ad184-112">Korrektur Fluss für alle Server Rollen</span><span class="sxs-lookup"><span data-stu-id="ad184-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="ad184-113">Glossar</span><span class="sxs-lookup"><span data-stu-id="ad184-113">Glossary</span></span>

  - <span data-ttu-id="ad184-114">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="ad184-114">Front-end Servers</span></span>

  - <span data-ttu-id="ad184-115">Back-End-SQL-Server</span><span class="sxs-lookup"><span data-stu-id="ad184-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="ad184-116">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="ad184-116">Mediation Servers</span></span>

  - <span data-ttu-id="ad184-117">Edgeservers</span><span class="sxs-lookup"><span data-stu-id="ad184-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="ad184-118">Was sind die wichtigsten Statusindikatoren?</span><span class="sxs-lookup"><span data-stu-id="ad184-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="ad184-119">Zu den wichtigsten Integritätsindikatoren zählen Leistungsindikatoren mit Schwellenwerten, die darauf abzielen, Probleme mit der Benutzeroberfläche zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ad184-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="ad184-120">Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Methode für die Anrufqualität (Call Quality Method, CQM), die auf die Gewährleistung einer Audioqualität für lync-Benutzer ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ad184-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="ad184-121">KHIs werden zusätzlich zu den standardmäßigen lync-Überwachungslösungen (z. b. System Center Operations Manager, synthetische Transaktionen, Monitoring Server) und nicht anstelle dieser Lösungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad184-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="ad184-122">Sammeln Sie die KHI-Leistungsindikatoren, und füllen Sie die KHI-Kalkulationstabelle mit dem Netzwerk Leit Faden aus, um eine Scorecard zu erstellen, mit der Sie den Serverzustand einer lync-Bereitstellung ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="ad184-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="ad184-123">Sobald die Datei ausgefüllt ist, führt Sie Sie bei der Reparatur der Umgebung und gibt weiteren Einblick in andere Stakeholder.</span><span class="sxs-lookup"><span data-stu-id="ad184-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="ad184-124">Bewerten Sie KHIs monatlich, und fügen Sie Sie in die laufenden operativen Prozesse der Bereitstellung ein.</span><span class="sxs-lookup"><span data-stu-id="ad184-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="ad184-125">Laden Sie den [lync Server-Netzwerk Leit Faden](http://go.microsoft.com/fwlink/p/?linkid=390677) herunter, um die vollständige Liste der KHIs anzuzeigen und die zugehörigen Kalkulationstabellen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ad184-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="ad184-126">So erfassen Sie KHI-Daten</span><span class="sxs-lookup"><span data-stu-id="ad184-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="ad184-127">Führen Sie das KHI-Skript aus, das im lync Server-Netzwerk Leit Faden auf jedem lync-Server enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ad184-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="ad184-128">Dadurch wird ein Datenauflister innerhalb des Systemmonitors erstellt und der Name khi.</span><span class="sxs-lookup"><span data-stu-id="ad184-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="ad184-129">Standardmäßig werden Daten alle 15 Sekunden abgefragt.</span><span class="sxs-lookup"><span data-stu-id="ad184-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="ad184-130">Wechseln Sie vor dem Beginn des Geschäftstages des Unternehmens zu jedem lync-Server, und starten Sie den KHI-Datensammler.</span><span class="sxs-lookup"><span data-stu-id="ad184-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="ad184-131">Beenden Sie am Ende dieses Tages den KHI-Datenauflister, und kopieren Sie die Daten an eine zentrale Position.</span><span class="sxs-lookup"><span data-stu-id="ad184-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="ad184-132">Nachdem Sie die mit dem lync Server Networking Guide-Download enthaltene KHI-Kalkulationstabelle mit dem System Monitor gefüllt haben, vergleichen Sie die Ergebnisse mit den empfohlenen Zielen.</span><span class="sxs-lookup"><span data-stu-id="ad184-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="ad184-133">Korrektur Fluss für alle Server Rollen</span><span class="sxs-lookup"><span data-stu-id="ad184-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="ad184-134">Stellen Sie für jeden Server in ihrer lync-Implementierung zunächst sicher, dass die komponentenintegrität und Systemleistung des Servers auf oder über dem gewünschten Wert liegen.</span><span class="sxs-lookup"><span data-stu-id="ad184-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="ad184-135">Erst danach sollten Sie sich die Indikatoren in Bezug auf die Rolle des Servers in der gesamten lync-Implementierung anschauen.</span><span class="sxs-lookup"><span data-stu-id="ad184-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="ad184-136">Beginnen Sie mit dem Sammeln von KHI-Leistungsdaten für alle Server.</span><span class="sxs-lookup"><span data-stu-id="ad184-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="ad184-137">Für jede Systemrolle (Details, die weiter unten in diesem Dokument erläutert werden) ermitteln Sie, ob die grundlegenden Systemkomponenten die empfohlenen Ziele erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ad184-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="ad184-138">Wenn dies nicht der Fall ist, beheben Sie die Systemleistung, und sammeln Sie dann KHI-Daten erneut, und stellen Sie die Systemintegrität sicher, bevor Sie sich die Metriken ansehen, die für die Rolle des Servers in der lync-Implementierung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="ad184-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="ad184-139">Der Komponentenstatus für alle Rollen ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="ad184-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="ad184-140">CPU- \< Auslastung 80%</span><span class="sxs-lookup"><span data-stu-id="ad184-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="ad184-141">AVG. Disk schreibt \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="ad184-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="ad184-142">AVG. Disk lesen \< Sie 10 ms</span><span class="sxs-lookup"><span data-stu-id="ad184-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="ad184-143">Verfügbarer Arbeitsspeicher \>20% System gesamt MB</span><span class="sxs-lookup"><span data-stu-id="ad184-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="ad184-144">Netzwerk-Warte \< schlangenlänge 2</span><span class="sxs-lookup"><span data-stu-id="ad184-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="ad184-145">Verworfene Pakete (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="ad184-146">Glossar</span><span class="sxs-lookup"><span data-stu-id="ad184-146">Glossary</span></span>

<span data-ttu-id="ad184-147">Die folgenden Begriffe und Akronyme werden in diesem Poster verwendet:</span><span class="sxs-lookup"><span data-stu-id="ad184-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="ad184-148">Als MCU = Application Sharing Multi-Punkt-Steuereinheit</span><span class="sxs-lookup"><span data-stu-id="ad184-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="ad184-149">AV MCU = Audio/Video-MCU</span><span class="sxs-lookup"><span data-stu-id="ad184-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="ad184-150">IM MCU = Instant Messaging-MCU</span><span class="sxs-lookup"><span data-stu-id="ad184-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="ad184-151">UCWA = Unified Communications Web-API</span><span class="sxs-lookup"><span data-stu-id="ad184-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="ad184-152">AV Edge = durchlaufen von Audio/Video über Edge</span><span class="sxs-lookup"><span data-stu-id="ad184-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="ad184-153">AV auth = Audio/Video-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ad184-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="ad184-154">SIP Stack = enthält die zentrale SIP-Implementierung von lync</span><span class="sxs-lookup"><span data-stu-id="ad184-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="ad184-155">Data Proxy = wird für Edge-Konferenzen verwendet</span><span class="sxs-lookup"><span data-stu-id="ad184-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="ad184-156">LySS = lync-Speicherdienst</span><span class="sxs-lookup"><span data-stu-id="ad184-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="ad184-157">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="ad184-157">Front-end Servers</span></span>

<span data-ttu-id="ad184-158">Die folgenden empfohlenen KHI-Ziele sind für Front-End-Server zusätzlich zu den grundlegenden Komponentenstatus spezifisch:</span><span class="sxs-lookup"><span data-stu-id="ad184-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad184-159">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="ad184-159">Functional area</span></span></th>
<th><span data-ttu-id="ad184-160">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="ad184-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad184-161">AS/AV/im-MCU</span><span class="sxs-lookup"><span data-stu-id="ad184-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="ad184-162">MCU-Integritätsstatus &lt;2</span><span class="sxs-lookup"><span data-stu-id="ad184-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad184-163">Web-Komponenten</span><span class="sxs-lookup"><span data-stu-id="ad184-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="ad184-164">Erweiterung der Verteilerliste anzeigen Timeouts &lt;0</span><span class="sxs-lookup"><span data-stu-id="ad184-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="ad184-165">ABWQ-Fehler = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="ad184-166">LIS-Fehler = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="ad184-167">Authentifizierungs &lt; Fehler 1/Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ad184-168">ASP.net V4-Anforderungen abgelehnt = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad184-169">SIP-Stack</span><span class="sxs-lookup"><span data-stu-id="ad184-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="ad184-170">Verarbeitung &lt; von eingehenden Nachrichten 1 Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="ad184-171">Eingehende Antworten &lt; sanken 1/sec Eingeh &lt; Ende Anforderungen sanken 1/Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ad184-172">Warteschlangen Wartezeit &lt; 100 MS</span><span class="sxs-lookup"><span data-stu-id="ad184-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="ad184-173">Latenz Wartezeit &lt; 100 MS</span><span class="sxs-lookup"><span data-stu-id="ad184-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="ad184-174">Gedrosselte Anforderungen = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="ad184-175">Authentifizierungs &lt; Fehler 1/Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ad184-176">Timeout für eingehende &lt; Nachrichten 2</span><span class="sxs-lookup"><span data-stu-id="ad184-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="ad184-177">Eingehende Nachrichten: &lt; 1 Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="ad184-178">Durchflussgesteuerte &lt; Verbindungen 2</span><span class="sxs-lookup"><span data-stu-id="ad184-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="ad184-179">Verzögerung &lt; von AVG. Out-Warteschlange 2 Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad184-180">LySS</span><span class="sxs-lookup"><span data-stu-id="ad184-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="ad184-181">% des vom Speicherdienst DB &lt; 80 verwendeten Speicherplatzes</span><span class="sxs-lookup"><span data-stu-id="ad184-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="ad184-182">#Replikat Replikationsfehler = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="ad184-183">#von Datenverlust Ereignissen = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad184-184">SQL</span><span class="sxs-lookup"><span data-stu-id="ad184-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="ad184-185">Lebenserwartung &gt; der Seite 300 Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="ad184-186">Batch Anforderungen/Sek &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="ad184-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="ad184-187">Back-End-SQL-Server</span><span class="sxs-lookup"><span data-stu-id="ad184-187">Backend SQL Servers</span></span>

<span data-ttu-id="ad184-188">Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden Komponenten Integritäts Merkmalen für SQL-Server:</span><span class="sxs-lookup"><span data-stu-id="ad184-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad184-189">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="ad184-189">Functional area</span></span></th>
<th><span data-ttu-id="ad184-190">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="ad184-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad184-191">SQL</span><span class="sxs-lookup"><span data-stu-id="ad184-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="ad184-192">Lebenserwartung &gt; der Seite 300 Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="ad184-193">Batch Anforderungen/Sek &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="ad184-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="ad184-194">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="ad184-194">Mediation Servers</span></span>

<span data-ttu-id="ad184-195">Die folgenden empfohlenen KHI-Ziele gelten speziell für Vermittlungsserver sowie für die grundlegende komponentenintegrität:</span><span class="sxs-lookup"><span data-stu-id="ad184-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad184-196">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="ad184-196">Functional area</span></span></th>
<th><span data-ttu-id="ad184-197">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="ad184-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad184-198">Vermittlungs Server Dienst</span><span class="sxs-lookup"><span data-stu-id="ad184-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="ad184-199">Fehler beim Laden des Anrufs Index = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="ad184-200">Fehlgeschlagene Anrufe &lt;wegen Proxy 10</span><span class="sxs-lookup"><span data-stu-id="ad184-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="ad184-201">Fehlgeschlagene Anrufe &lt;wegen Gateway 10</span><span class="sxs-lookup"><span data-stu-id="ad184-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="ad184-202">Anrufe (in oder aus) abgelehnt = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="ad184-203">Medien Kandidaten fehlen = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="ad184-204">Fehler bei der Medien Verbindungsüberprüfung = 0</span><span class="sxs-lookup"><span data-stu-id="ad184-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="ad184-205">Edgeservers</span><span class="sxs-lookup"><span data-stu-id="ad184-205">Edge Servers</span></span>

<span data-ttu-id="ad184-206">Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden Komponentenstatus speziell für Edge-Server:</span><span class="sxs-lookup"><span data-stu-id="ad184-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad184-207">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="ad184-207">Functional area</span></span></th>
<th><span data-ttu-id="ad184-208">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="ad184-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad184-209">AV-auth</span><span class="sxs-lookup"><span data-stu-id="ad184-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="ad184-210">Ungültige Anforderungen &lt; 20/Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad184-211">AV-Edge</span><span class="sxs-lookup"><span data-stu-id="ad184-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="ad184-212">Auth. Fehler &lt;20/Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="ad184-213">Zuordnungsfehler &lt;20/Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="ad184-214">Pakete, &lt;die 300/Sek. gelöscht wurden</span><span class="sxs-lookup"><span data-stu-id="ad184-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad184-215">Daten Proxy</span><span class="sxs-lookup"><span data-stu-id="ad184-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="ad184-216">Gedrosselte Server &lt; Verbindungen 3</span><span class="sxs-lookup"><span data-stu-id="ad184-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="ad184-217">System Drosselung &lt;1</span><span class="sxs-lookup"><span data-stu-id="ad184-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad184-218">SIP-Stack</span><span class="sxs-lookup"><span data-stu-id="ad184-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="ad184-219">Verbindungen über Grenze sanken &lt; 1</span><span class="sxs-lookup"><span data-stu-id="ad184-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="ad184-220">Zeitüberschreitung bei &lt;Sends 10</span><span class="sxs-lookup"><span data-stu-id="ad184-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="ad184-221">Durchflussgesteuerte &lt;Verbindungen 100</span><span class="sxs-lookup"><span data-stu-id="ad184-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="ad184-222">Eingehende Anforderungen &lt; sanken auf 1/Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="ad184-223">AVG. Nachrichtenverarbeitung &lt; 3 Sek.</span><span class="sxs-lookup"><span data-stu-id="ad184-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad184-224">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad184-224">See Also</span></span>


[<span data-ttu-id="ad184-225">Lync Server-Netzwerkhandbuch</span><span class="sxs-lookup"><span data-stu-id="ad184-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="ad184-226">Wichtige Integritätsindikatoren: die Grundlage für die Verwaltung von fehlerfreien lync-Servern</span><span class="sxs-lookup"><span data-stu-id="ad184-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="ad184-227">Methodik der lync-Anrufqualität</span><span class="sxs-lookup"><span data-stu-id="ad184-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

