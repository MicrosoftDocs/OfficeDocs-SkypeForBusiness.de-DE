---
title: 'Lync Server 2013: wöchentliche Aufgaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d3f87b37b8c0fe29c4dee76467a9e07931551a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="abffa-102">Wöchentliche Aufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abffa-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abffa-103">_**Letztes Änderungsstand des Themas:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="abffa-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="abffa-104">Wöchentliche Aufgaben beziehen sich im Allgemeinen auf das Sammeln und Analysieren von Protokollen und Berichten.</span><span class="sxs-lookup"><span data-stu-id="abffa-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="abffa-105">Archiv Ereignisprotokolle</span><span class="sxs-lookup"><span data-stu-id="abffa-105">Archive event logs</span></span>

<span data-ttu-id="abffa-106">Wenn Ereignisprotokolle nicht so konfiguriert sind, dass Ereignisse nach Bedarf überschrieben werden, müssen Sie regelmäßig archiviert und gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="abffa-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="abffa-107">Diese Aktion ist besonders wichtig für Sicherheitsprotokolle, die bei der Untersuchung versuchter Sicherheitsverletzungen möglicherweise erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="abffa-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="abffa-108">In Ihrer Organisation müssen Richtlinien und Verfahren für die Protokoll Archivierung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="abffa-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="abffa-109">Erstellen von Berichten</span><span class="sxs-lookup"><span data-stu-id="abffa-109">Create reports</span></span>

<span data-ttu-id="abffa-110">Erstellen von Statusberichten zur Unterstützung bei der Kapazitätsplanung, SLA-Überprüfungen und Leistungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="abffa-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="abffa-111">Verwenden Sie tägliche Daten aus dem Ereignisprotokoll und dem System Monitor, um Berichte zu Datenträgern, Arbeitsspeicher und CPU-Auslastung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="abffa-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="abffa-112">Verwenden Sie System Center Operations Manager zum Generieren von Verfügbarkeits-und Verfügbarkeitsberichten.</span><span class="sxs-lookup"><span data-stu-id="abffa-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="abffa-113">In Ihrer Organisation müssen Richtlinien und Verfahren für Statusberichte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="abffa-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="abffa-114">Schadensberichte</span><span class="sxs-lookup"><span data-stu-id="abffa-114">Incident reports</span></span>

<span data-ttu-id="abffa-115">Führen Sie eine wöchentliche Überprüfung der vorfallberichte Ihrer Organisation durch, die sich auf lync Server beziehen.</span><span class="sxs-lookup"><span data-stu-id="abffa-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="abffa-116">Diese Überwachung sollte Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="abffa-116">This audit should include the following:</span></span>

  - <span data-ttu-id="abffa-117">Die am häufigsten generierten, aufgelösten und ausstehenden Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="abffa-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="abffa-118">Lösungen für ungelöste Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="abffa-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="abffa-119">Aktualisieren von Berichten, um neue Trouble Tickets einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="abffa-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="abffa-120">Aktualisieren eines Dokument-Repositorys für die Problem Behandlungs Anleitungen und Post mortem über Ausfälle.</span><span class="sxs-lookup"><span data-stu-id="abffa-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="abffa-121">Da das Vorfall Verfolgungssystem Ihrer Organisation unabhängig von lync Server ausgewählt werden kann, sind bestimmte Anweisungen oder Zeiger nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="abffa-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="abffa-122">Lesen Sie in der Dokumentation zu dem System, das Ihre Organisation ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="abffa-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="abffa-123">Überprüfen der IIS-Protokolle und-Leistung</span><span class="sxs-lookup"><span data-stu-id="abffa-123">Check IIS logs and performance</span></span>

<span data-ttu-id="abffa-124">Führen Sie eine wöchentliche Überprüfung der Internet Information Services (IIS) Protokolle und der Leistung durch.</span><span class="sxs-lookup"><span data-stu-id="abffa-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="abffa-125">Weitere Informationen zum Überwachen von IIS-Protokollen und-Leistung finden Sie unter [Windows Server 2003 Internet Information Services (IIS) Ereignisprotokollierung (Übersicht](http://go.microsoft.com/fwlink/?linkid=36077)).</span><span class="sxs-lookup"><span data-stu-id="abffa-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="abffa-126">Die Überprüfung sollte Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="abffa-126">The review should include the following:</span></span>

  - <span data-ttu-id="abffa-127">Webdienst-Cache Indikatoren zum Überwachen des WWW-Dienst Caches.</span><span class="sxs-lookup"><span data-stu-id="abffa-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="abffa-128">ASP-Indikatoren (Active Server Pages) zum Überwachen von Anwendungen, die als ASP ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="abffa-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="abffa-129">Generieren von Datenbankberichten</span><span class="sxs-lookup"><span data-stu-id="abffa-129">Generate database reports</span></span>

<span data-ttu-id="abffa-130">**So generieren Sie Berichte für die SQL-Datenbank**</span><span class="sxs-lookup"><span data-stu-id="abffa-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="abffa-131">Öffnen Sie lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abffa-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="abffa-132">Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="abffa-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="abffa-133">Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="abffa-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="abffa-134">Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="abffa-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="abffa-135">Um den Namen der Datenbank anzuzeigen, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.</span><span class="sxs-lookup"><span data-stu-id="abffa-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="abffa-136">Um aktuelle Benutzer Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **wechseln**, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="abffa-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="abffa-137">Zum Abrufen aktueller benutzerbezogener Daten für einen einzelnen Benutzer des Pools erweitern Sie **Berichte pro Benutzer**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="abffa-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="abffa-138">Um aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="abffa-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="abffa-139">Überprüfen der Sicherheit und lync Server Updates</span><span class="sxs-lookup"><span data-stu-id="abffa-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="abffa-140">Identifizieren Sie neue Service Packs, Hotfixes oder Updates.</span><span class="sxs-lookup"><span data-stu-id="abffa-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="abffa-141">Testen Sie diese gegebenenfalls in einem Test Labor, und ordnen Sie die Bereitstellung auf den Produktionsservern mithilfe der Änderungskontrollverfahren an.</span><span class="sxs-lookup"><span data-stu-id="abffa-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="abffa-142">Außerdem sind lync Server Komponenten Aktualisierungen jetzt im Rahmen von Windows Update verfügbar.</span><span class="sxs-lookup"><span data-stu-id="abffa-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="abffa-143">Alle lync Server-Komponenten Updates müssen gleichzeitig auf allen Servern mit lync Server aktualisiert werden, für die die Updates gelten.</span><span class="sxs-lookup"><span data-stu-id="abffa-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="abffa-144">Ausführen des lync Server 2013 Best Practice Analyzer</span><span class="sxs-lookup"><span data-stu-id="abffa-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="abffa-145">Das lync Server 2013 Best Practices Analyzer ist ein Diagnosetool, das Konfigurationsinformationen sammelt und ermittelt, ob die Konfiguration gemäß den bewährten Methoden von Microsoft festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="abffa-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="abffa-146">Dokumentation zu diesem Tool finden Sie unter [lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="abffa-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="abffa-147">Das Tool vergleicht die Konfigurationsdaten Ihrer Bereitstellung mit einer Reihe vordefinierter Regeln für lync Server und meldet potenzielle Probleme.</span><span class="sxs-lookup"><span data-stu-id="abffa-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="abffa-148">Für jedes gemeldete Problem stellt das Tool die aktuelle Konfiguration in der lync Server Umgebung und die empfohlene Konfiguration bereit.</span><span class="sxs-lookup"><span data-stu-id="abffa-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="abffa-149">Mit dem richtigen Netzwerkzugriff kann das Tool Ihre AD DS und Server untersuchen, auf denen lync Server 2013 ausführen, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="abffa-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="abffa-150">Proaktives durchführen von Integritätsprüfungen, überprüfen, ob die Konfiguration gemäß den empfohlenen bewährten Methoden festgelegt wurde</span><span class="sxs-lookup"><span data-stu-id="abffa-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="abffa-151">Erstellen einer Liste von Problemen, beispielsweise suboptimale Konfigurationseinstellungen oder nicht unterstützte oder nicht empfohlene Optionen</span><span class="sxs-lookup"><span data-stu-id="abffa-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="abffa-152">Beurteilen der allgemeinen Integrität eines Systems</span><span class="sxs-lookup"><span data-stu-id="abffa-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="abffa-153">Hilfe bei der Behandlung bestimmter Probleme</span><span class="sxs-lookup"><span data-stu-id="abffa-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="abffa-154">Aufforderung zum Herunterladen von Updates, sofern diese verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="abffa-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="abffa-155">Bereitstellen von Online-und lokalen Dokumentationen zu gemeldeten Problemen und einschließen von Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="abffa-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="abffa-156">Generieren von Konfigurationsinformationen, die für eine spätere Überprüfung erfasst werden können</span><span class="sxs-lookup"><span data-stu-id="abffa-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="abffa-157">Stellen Sie sicher, dass die RTCBPA. msi auf allen lync Server 2013 Servern installiert ist, und generieren Sie einen wöchentlichen Integritäts Prüfungsbericht.</span><span class="sxs-lookup"><span data-stu-id="abffa-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="abffa-158">Notieren Sie sich die Ergebnisse und korrigieren Sie, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abffa-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="abffa-159">Überprüfen der SLA-Leistungszahlen</span><span class="sxs-lookup"><span data-stu-id="abffa-159">Review SLA performance figures</span></span>

<span data-ttu-id="abffa-160">Überprüfen Sie die wichtigsten Leistungsdaten für die vorherige Woche.</span><span class="sxs-lookup"><span data-stu-id="abffa-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="abffa-161">Überprüfen der Leistung anhand der Anforderungen der SLA.</span><span class="sxs-lookup"><span data-stu-id="abffa-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="abffa-162">Identifizieren von Trends und Elementen, die ihre Ziele nicht erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="abffa-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="abffa-163">Überprüfen von System Center Operations Manager Management Pack und Quality of Experience-Berichten</span><span class="sxs-lookup"><span data-stu-id="abffa-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="abffa-164">Abrufen und überprüfen lync Server 2013 Management Packs und Quality of Experience-Berichte.</span><span class="sxs-lookup"><span data-stu-id="abffa-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="abffa-165">Generieren und Anzeigen von Datenbankberichten für Enterprise-Pools</span><span class="sxs-lookup"><span data-stu-id="abffa-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="abffa-166">**So generieren Sie Pool Berichte**</span><span class="sxs-lookup"><span data-stu-id="abffa-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="abffa-167">Öffnen Sie lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abffa-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="abffa-168">Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="abffa-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="abffa-169">Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="abffa-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="abffa-170">Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="abffa-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="abffa-171">Um den Namen der Datenbank anzuzeigen, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.</span><span class="sxs-lookup"><span data-stu-id="abffa-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="abffa-172">Um aktuelle Benutzer Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **wechseln**, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="abffa-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="abffa-173">Zum Abrufen aktueller benutzerbezogener Daten für einen einzelnen Benutzer des Pools erweitern Sie **Berichte pro Benutzer**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="abffa-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="abffa-174">Um aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="abffa-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="abffa-175">Für jeden Enterprise-Pool können Administratoren die Registerkarte **Datenbank** verwenden, um den Datenbanknamen anzuzeigen und Berichte aus der Datenbank abzurufen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="abffa-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="abffa-176">Datenbankberichte und-Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="abffa-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abffa-177">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="abffa-177">Section</span></span></th>
<th><span data-ttu-id="abffa-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abffa-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abffa-179">Benutzer Zusammenfassungsberichte</span><span class="sxs-lookup"><span data-stu-id="abffa-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="abffa-180">Dbanalyze/v/Report: diag [/SQLServer: Wert]</span><span class="sxs-lookup"><span data-stu-id="abffa-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="abffa-181">In diesem Abschnitt werden aggregierte Informationen zu Benutzern in einem Pool angezeigt, beispielsweise die Anzahl der aktivierten Benutzer, die durchschnittliche Anzahl der Kontakte pro Benutzer und die Anzahl der Benutzer für bestimmte Features.</span><span class="sxs-lookup"><span data-stu-id="abffa-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="abffa-182">Wenn Sie diese Berichte verwenden, sind die folgenden Informationen möglicherweise hilfreich:</span><span class="sxs-lookup"><span data-stu-id="abffa-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="abffa-183">Ein aktivierter Benutzer ist ein Benutzer, der mithilfe des Snap-Ins Active Directory Benutzer und Computer für lync Server 2013 aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="abffa-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="abffa-184">Ein aktiver Benutzer ist ein Benutzer, der sich angemeldet oder registriert hat.</span><span class="sxs-lookup"><span data-stu-id="abffa-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="abffa-185">Die zusammenfassenden Berichte bieten auch eine Reihe von statistischen Informationen über Kontakte.</span><span class="sxs-lookup"><span data-stu-id="abffa-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="abffa-186">Diese Statistiken sind nur für die Auffüllung von Benutzern gültig, die sich mindestens einmal angemeldet haben und die mindestens einen Kontakt haben.</span><span class="sxs-lookup"><span data-stu-id="abffa-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="abffa-187">Folglich wird normalerweise keine Mindestanzahl von Kontakten von 0 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="abffa-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="abffa-188">Wenn ein Benutzer über keine Kontakte verfügt (aber aktiv ist, in dem der Benutzer registriert ist), wird aufgrund dieses Verhaltens möglicherweise Folgendes &lt;angezeigt&gt; : Empty für einige Statistikfelder.</span><span class="sxs-lookup"><span data-stu-id="abffa-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abffa-189">Berichte pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="abffa-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="abffa-190">Dbanalyze/v/Report: Datenträger [/SQLServer: Wert]</span><span class="sxs-lookup"><span data-stu-id="abffa-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="abffa-191">Im Gegensatz zu den Zusammenfassungsberichten, die für eine Benutzer Auffüllung berechnet werden, handelt es sich um Berichte über einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="abffa-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abffa-192">Konferenz Zusammenfassungsberichte</span><span class="sxs-lookup"><span data-stu-id="abffa-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="abffa-193">Dbanalyze/v/Report: conf [/SQLServer: Wert]</span><span class="sxs-lookup"><span data-stu-id="abffa-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="abffa-194">In diesem Abschnitt werden aggregierte Informationen zu Konferenz Zusammenfassungs Statistiken für den Pool angezeigt, beispielsweise die Anzahl der aktiven Konferenzen und die Gesamtzahl der Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="abffa-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="abffa-195">Ausführung des Bandbreiten Auslastungsanalyse Programms</span><span class="sxs-lookup"><span data-stu-id="abffa-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="abffa-196">Bandwidth Auslastung Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="abffa-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="abffa-197">Diese Berichte können verwendet werden, um das aktuelle Muster der Bandbreitennutzung zu verstehen und die Planung der Bandbreitenkapazität zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="abffa-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="abffa-198">Außerdem wird die Bandbreitenkapazität durchlaufen, die verschiedenen Links zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="abffa-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="abffa-199">Dieses Tool führt folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="abffa-199">This tool does the following:</span></span>

  - <span data-ttu-id="abffa-200">Generiert spezifische Berichte für die audionutzung über das Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="abffa-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="abffa-201">Hilft bei der effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Links zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="abffa-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="abffa-202">Bandbreiten Auslastungsanalyse kann grafische Plots von Bandbreitenkapazität und Nutzungsberichten generieren.</span><span class="sxs-lookup"><span data-stu-id="abffa-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="abffa-203">Sie sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="abffa-203">They are as follows:</span></span>

  - <span data-ttu-id="abffa-204">Alle WAN-Verbindungen im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="abffa-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="abffa-205">Gefiltert nach ausgewählten WAN-Verbindungen, die ausgewählt wurden</span><span class="sxs-lookup"><span data-stu-id="abffa-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="abffa-206">Gefiltert nach WAN-Verbindungen, die die Link Kapazität überschritten haben</span><span class="sxs-lookup"><span data-stu-id="abffa-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="abffa-207">Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite unter Verwenden</span><span class="sxs-lookup"><span data-stu-id="abffa-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="abffa-208">Filtern nach WAN-Verbindungen, die kritische Ebenen erreicht haben (Bandbreitenauslastung von mehr als 90% der Bandbreitenkapazität der WAN-Verbindung)</span><span class="sxs-lookup"><span data-stu-id="abffa-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="abffa-209">Gefiltert nach WAN-Linktyp – Netzwerkstandort Verknüpfungen, interregionale Links und Links innerhalb eines Standorts</span><span class="sxs-lookup"><span data-stu-id="abffa-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="abffa-210">Gefiltert nach netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="abffa-210">Filtered by network region</span></span>

<span data-ttu-id="abffa-211">Dokumentation zu diesem Tool finden Sie in der [Dokumentation zum lync Server 2013 Resource Kit-Tools](http://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="abffa-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="abffa-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abffa-212">See Also</span></span>


[<span data-ttu-id="abffa-213">Prüfliste für wöchentliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="abffa-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

