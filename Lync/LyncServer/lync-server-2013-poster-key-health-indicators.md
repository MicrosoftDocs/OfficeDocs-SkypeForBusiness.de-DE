---
title: 'Lync Server 2013: Poster: wichtige Integritätsindikatoren'
description: 'Lync Server 2013: Poster: wichtige Integritätsindikatoren.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566341"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="3d392-103">Wichtige Integritätsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d392-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d392-104">_**Letztes Änderungsstand des Themas:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="3d392-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="3d392-105">Dieser Artikel ist ein Begleiter zu den [wichtigsten Integritätsindikatoren: die Grundlage für die Verwaltung eines gesunden Posters für lync Server](https://go.microsoft.com/fwlink/?linkid=391838) , das Sie aus dem Download Center herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="3d392-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="3d392-106">![Poster zur Beschreibung der Problembehandlung mithilfe von KHI-Daten](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster zur Beschreibung der Problembehandlung mithilfe von KHI-Daten")</span><span class="sxs-lookup"><span data-stu-id="3d392-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="3d392-107">Sie können dieses Poster verwenden, um Informationen zu wichtigen Integritätsindikatoren (KHIs), Leistungsindikatoren mit Schwellenwerten für die Offenlegung von Problemen mit der Benutzerfreundlichkeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d392-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="3d392-108">Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Call Quality Method (CQM), die sich auf die Sicherstellungeiner qualitativ hochwertigen Audioerfahrung für lync-Benutzer konzentriert.</span><span class="sxs-lookup"><span data-stu-id="3d392-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="3d392-109">Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com übermitteln.</span><span class="sxs-lookup"><span data-stu-id="3d392-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="3d392-110">Das Poster erläutert die folgenden Bereiche:</span><span class="sxs-lookup"><span data-stu-id="3d392-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="3d392-111">Was sind die wichtigsten Integritätsindikatoren?</span><span class="sxs-lookup"><span data-stu-id="3d392-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="3d392-112">So erfassen Sie KHI-Daten</span><span class="sxs-lookup"><span data-stu-id="3d392-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="3d392-113">Korrektur Fluss für alle Server Rollen</span><span class="sxs-lookup"><span data-stu-id="3d392-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="3d392-114">Glossar</span><span class="sxs-lookup"><span data-stu-id="3d392-114">Glossary</span></span>

  - <span data-ttu-id="3d392-115">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="3d392-115">Front-end Servers</span></span>

  - <span data-ttu-id="3d392-116">Back-End-SQL-Server</span><span class="sxs-lookup"><span data-stu-id="3d392-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="3d392-117">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="3d392-117">Mediation Servers</span></span>

  - <span data-ttu-id="3d392-118">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="3d392-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="3d392-119">Was sind die wichtigsten Integritätsindikatoren?</span><span class="sxs-lookup"><span data-stu-id="3d392-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="3d392-120">Wichtige Integritätsindikatoren sind Leistungsindikatoren mit Schwellenwerten für die Offenlegung von Problemen mit der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="3d392-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="3d392-121">Das Sammeln von KHI-Daten ist in der Regel der erste Schritt zur Implementierung der Call Quality Method (CQM), die sich auf die Sicherstellungeiner qualitativ hochwertigen Audioerfahrung für lync-Benutzer konzentriert.</span><span class="sxs-lookup"><span data-stu-id="3d392-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="3d392-122">KHIs werden zusätzlich zu den standardmäßigen lync-Überwachungslösungen (beispielsweise System Center Operations Manager, synthetische Transaktionen, Monitoring Server) und nicht anstelle dieser Lösungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d392-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="3d392-123">Sammeln Sie die KHI-Leistungsindikatoren, und füllen Sie die KHI-Kalkulationstabelle mit dem Netzwerk Leit Faden aus, um eine Scorecard zu erstellen, mit der Sie den Serverstatus einer lync-Bereitstellung bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="3d392-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="3d392-124">Sobald die Anwendung aufgefüllt wurde, werden Sie bei der Reparatur der Umgebung unterstützt und bietet zusätzliche Einblicke für andere Beteiligte.</span><span class="sxs-lookup"><span data-stu-id="3d392-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="3d392-125">Bewerten Sie KHIs monatlich, und integrieren Sie diese in die laufenden betrieblichen Prozesse der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="3d392-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="3d392-126">Laden Sie das [lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) herunter, um die vollständige Liste der KHIs zu sehen und die zugehörigen Arbeitsblätter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3d392-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="3d392-127">So erfassen Sie KHI-Daten</span><span class="sxs-lookup"><span data-stu-id="3d392-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="3d392-128">Führen Sie das KHI-Skript aus, das im lync Server-Netzwerk Leit Faden auf jeder lync Server enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3d392-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="3d392-129">Dadurch wird ein Datensammelpunkt in der Systemüberwachung erstellt und der Name khi.</span><span class="sxs-lookup"><span data-stu-id="3d392-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="3d392-130">Standardmäßig werden die Daten alle 15 Sekunden abgefragt.</span><span class="sxs-lookup"><span data-stu-id="3d392-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="3d392-131">Wechseln Sie vor dem Start des Geschäftstags Ihres Unternehmens zu jeder lync Server, und starten Sie den KHI-Datensammelpunkt.</span><span class="sxs-lookup"><span data-stu-id="3d392-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="3d392-132">Beenden Sie am Ende dieses Tages den KHI-Datensammelpunkt, und kopieren Sie die Daten an einen zentralen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="3d392-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="3d392-133">Nachdem Sie den System Monitor verwendet haben, um die im lync Server Network Guide-Download enthaltene KHI-Kalkulationstabelle auszufüllen, vergleichen Sie die Ergebnisse mit den empfohlenen Zielen.</span><span class="sxs-lookup"><span data-stu-id="3d392-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="3d392-134">Korrektur Fluss für alle Server Rollen</span><span class="sxs-lookup"><span data-stu-id="3d392-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="3d392-135">Überprüfen Sie für jeden Server in ihrer lync-Implementierung zunächst, ob sich die Integrität der Komponente und die Systemleistung des Servers auf oder über der gewünschten Ebene befinden.</span><span class="sxs-lookup"><span data-stu-id="3d392-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="3d392-136">Erst danach sollten Sie sich die Indikatoren ansehen, die sich auf die Rolle des Servers in der gesamten lync-Implementierung beziehen.</span><span class="sxs-lookup"><span data-stu-id="3d392-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="3d392-137">Beginnen Sie mit dem Sammeln von KHI-Leistungsdaten für alle Server.</span><span class="sxs-lookup"><span data-stu-id="3d392-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="3d392-138">Ermitteln Sie für jede Systemrolle (Details weiter unten in diesem Dokument erläutert), ob die grundlegenden Systemkomponenten die empfohlenen Ziele erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3d392-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="3d392-139">Wenn dies nicht der Fall ist, stellen Sie die Systemleistung wieder her, sammeln Sie dann KHI-Daten, und stellen Sie sicher, dass die Systemintegrität überprüft wird, bevor Sie die für die Serverrolle in der lync-Implementierung spezifischen Metriken betrachten.</span><span class="sxs-lookup"><span data-stu-id="3d392-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="3d392-140">Der Komponentenzustand für alle Rollen ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="3d392-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="3d392-141">CPU-Auslastung \< 80%</span><span class="sxs-lookup"><span data-stu-id="3d392-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="3d392-142">AVG. Disk Write \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="3d392-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="3d392-143">AVG. Disk Read \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="3d392-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="3d392-144">Verfügbarer Arbeitsspeicher \> 20% System gesamt MB</span><span class="sxs-lookup"><span data-stu-id="3d392-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="3d392-145">Netzwerkwarteschlange (Länge \< 2)</span><span class="sxs-lookup"><span data-stu-id="3d392-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="3d392-146">Verworfene Pakete (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="3d392-147">Glossar</span><span class="sxs-lookup"><span data-stu-id="3d392-147">Glossary</span></span>

<span data-ttu-id="3d392-148">Die folgenden Begriffe und Akronyme werden in diesem Poster verwendet:</span><span class="sxs-lookup"><span data-stu-id="3d392-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="3d392-149">AS MCU = Multi-Points-Steuereinheit für die Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="3d392-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="3d392-150">AV MCU = Audio/Video-MCU</span><span class="sxs-lookup"><span data-stu-id="3d392-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="3d392-151">Chat MCU = Instant Messaging MCU</span><span class="sxs-lookup"><span data-stu-id="3d392-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="3d392-152">UCWA = Unified Communications-WebAPI</span><span class="sxs-lookup"><span data-stu-id="3d392-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="3d392-153">AV Edge = Traversieren von Audio/Video über Edge</span><span class="sxs-lookup"><span data-stu-id="3d392-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="3d392-154">AV auth = Audio/Video-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3d392-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="3d392-155">SIP Stack = enthält die zentrale SIP-Implementierung von lync</span><span class="sxs-lookup"><span data-stu-id="3d392-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="3d392-156">Daten Proxy = wird für Edge-Konferenzen verwendet</span><span class="sxs-lookup"><span data-stu-id="3d392-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="3d392-157">LySS = lync-Speicherdienst</span><span class="sxs-lookup"><span data-stu-id="3d392-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="3d392-158">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="3d392-158">Front-end Servers</span></span>

<span data-ttu-id="3d392-159">Die folgenden empfohlenen KHI-Ziele sind für Front-End-Server zusätzlich zur grundlegenden komponentenintegrität spezifisch:</span><span class="sxs-lookup"><span data-stu-id="3d392-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d392-160">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="3d392-160">Functional area</span></span></th>
<th><span data-ttu-id="3d392-161">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="3d392-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d392-162">AS/AV/im MCU</span><span class="sxs-lookup"><span data-stu-id="3d392-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="3d392-163">MCU-Integritätsstatus &lt; 2</span><span class="sxs-lookup"><span data-stu-id="3d392-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d392-164">Web Components</span><span class="sxs-lookup"><span data-stu-id="3d392-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="3d392-165">Verteilerlistenerweiterung AD Timeouts &lt; 0</span><span class="sxs-lookup"><span data-stu-id="3d392-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="3d392-166">ABWQ-Fehler = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="3d392-167">LIS-Fehler = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="3d392-168">Authentifizierungsfehler &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="3d392-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3d392-169">ASP.net V4-Anforderungen abgelehnt = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d392-170">SIP-Stack</span><span class="sxs-lookup"><span data-stu-id="3d392-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="3d392-171">AVG. eingehende Nachrichtenverarbeitung &lt; 1 Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="3d392-172">Eingehende Antworten fallen gelassen &lt; 1/sec eingehende Anfragen wurden um &lt; 1/Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3d392-173">Warteschlangen Wartezeit &lt; 100 MS</span><span class="sxs-lookup"><span data-stu-id="3d392-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="3d392-174">Wartezeit in der Warte Prozedur &lt; 100 MS</span><span class="sxs-lookup"><span data-stu-id="3d392-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="3d392-175">Gedrosselte Anforderungen = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="3d392-176">Authentifizierungsfehler &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="3d392-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3d392-177">Timeout für eingehende Nachrichten &lt; 2</span><span class="sxs-lookup"><span data-stu-id="3d392-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="3d392-178">AVG. eingehende Nachricht halten &lt; 1 Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="3d392-179">Fluss gesteuerte Verbindungen &lt; 2</span><span class="sxs-lookup"><span data-stu-id="3d392-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="3d392-180">Verzögerung von AVG. Out-Warteschlange &lt; 2 Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d392-181">LySS</span><span class="sxs-lookup"><span data-stu-id="3d392-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="3d392-182">% des Speicherplatzes, der von der Speicherdienst-DB 80 verwendet wird &lt;</span><span class="sxs-lookup"><span data-stu-id="3d392-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="3d392-183"># von Replikat Replikationsfehlern = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="3d392-184"># von Datenverlust Ereignissen = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d392-185">SQL</span><span class="sxs-lookup"><span data-stu-id="3d392-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="3d392-186">Seiten Lebenserwartung &gt; 300 Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="3d392-187">Batch Anforderungen/Sek &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="3d392-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="3d392-188">Back-End-SQL-Server</span><span class="sxs-lookup"><span data-stu-id="3d392-188">Backend SQL Servers</span></span>

<span data-ttu-id="3d392-189">Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden komponentenintegrität für SQL-Server:</span><span class="sxs-lookup"><span data-stu-id="3d392-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d392-190">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="3d392-190">Functional area</span></span></th>
<th><span data-ttu-id="3d392-191">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="3d392-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d392-192">SQL</span><span class="sxs-lookup"><span data-stu-id="3d392-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="3d392-193">Seiten Lebenserwartung &gt; 300 Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="3d392-194">Batch Anforderungen/Sek &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="3d392-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="3d392-195">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="3d392-195">Mediation Servers</span></span>

<span data-ttu-id="3d392-196">Die folgenden empfohlenen KHI-Ziele gelten zusätzlich zu den grundlegenden komponentenintegrität für Vermittlungsserver:</span><span class="sxs-lookup"><span data-stu-id="3d392-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d392-197">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="3d392-197">Functional area</span></span></th>
<th><span data-ttu-id="3d392-198">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="3d392-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d392-199">Vermittlungsserver Dienst</span><span class="sxs-lookup"><span data-stu-id="3d392-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="3d392-200">Fehler beim Laden des Anrufs Index = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="3d392-201">Fehlgeschlagene Anrufe aufgrund von Proxy &lt; 10</span><span class="sxs-lookup"><span data-stu-id="3d392-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="3d392-202">Fehlgeschlagene Anrufe aufgrund von Gateway &lt; 10</span><span class="sxs-lookup"><span data-stu-id="3d392-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="3d392-203">Zurück geleitete Aufrufe (in oder out) = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="3d392-204">Fehlende Medien Kandidaten = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="3d392-205">Fehler bei der Medien Verbindungsüberprüfung = 0</span><span class="sxs-lookup"><span data-stu-id="3d392-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="3d392-206">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="3d392-206">Edge Servers</span></span>

<span data-ttu-id="3d392-207">Die folgenden empfohlenen KHI-Ziele gelten neben dem grundlegenden Zustand der Komponenten für Edgeserver spezifisch:</span><span class="sxs-lookup"><span data-stu-id="3d392-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d392-208">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="3d392-208">Functional area</span></span></th>
<th><span data-ttu-id="3d392-209">Ziel Metriken</span><span class="sxs-lookup"><span data-stu-id="3d392-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d392-210">AV-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3d392-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="3d392-211">Ungültige Anforderungen &lt; 20/Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d392-212">AV-Edge</span><span class="sxs-lookup"><span data-stu-id="3d392-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="3d392-213">Authentifizierungsfehler &lt; 20/Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="3d392-214">Zuordnungsfehler &lt; 20/Sek.</span><span class="sxs-lookup"><span data-stu-id="3d392-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="3d392-215">Gelöschte Pakete &lt; 300/s</span><span class="sxs-lookup"><span data-stu-id="3d392-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d392-216">Daten Proxy</span><span class="sxs-lookup"><span data-stu-id="3d392-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="3d392-217">Gedrosselte Server Verbindungen &lt; 3</span><span class="sxs-lookup"><span data-stu-id="3d392-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="3d392-218">Das System gibt die Drosselung 1 an. &lt;</span><span class="sxs-lookup"><span data-stu-id="3d392-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d392-219">SIP-Stack</span><span class="sxs-lookup"><span data-stu-id="3d392-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="3d392-220">Verbindungen über Grenzwert sank &lt; 1</span><span class="sxs-lookup"><span data-stu-id="3d392-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="3d392-221">Sende Zeitüberschreitung &lt; 10</span><span class="sxs-lookup"><span data-stu-id="3d392-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="3d392-222">Fluss gesteuerte Verbindungen &lt; 100</span><span class="sxs-lookup"><span data-stu-id="3d392-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="3d392-223">Eingehende Anforderungen sanken &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="3d392-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3d392-224">AVG. Message processing &lt; 3 sec</span><span class="sxs-lookup"><span data-stu-id="3d392-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d392-225">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d392-225">See Also</span></span>


[<span data-ttu-id="3d392-226">Leitfaden für lync Server Netzwerke</span><span class="sxs-lookup"><span data-stu-id="3d392-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="3d392-227">Wichtige Integritätsindikatoren: die Grundlage für die Verwaltung gesunder lync-Server</span><span class="sxs-lookup"><span data-stu-id="3d392-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="3d392-228">Methode für die lync-Anrufqualität</span><span class="sxs-lookup"><span data-stu-id="3d392-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

