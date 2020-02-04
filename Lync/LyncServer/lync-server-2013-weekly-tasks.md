---
title: 'Lync Server 2013: Wöchentliche Aufgaben'
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
ms.openlocfilehash: b973d5d69e6e4609a1dff3029b0ad0b05ec3a936
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="db90f-102">Wöchentliche Aufgaben in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db90f-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db90f-103">_**Letztes Änderungsdatum des Themas:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="db90f-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="db90f-104">Wöchentliche Aufgaben sind im Allgemeinen mit dem sammeln und Analysieren von Protokollen und Berichten verbunden.</span><span class="sxs-lookup"><span data-stu-id="db90f-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="db90f-105">Archivieren von Ereignisprotokollen</span><span class="sxs-lookup"><span data-stu-id="db90f-105">Archive event logs</span></span>

<span data-ttu-id="db90f-106">Wenn Ereignisprotokolle nicht so konfiguriert sind, dass Ereignisse nach Bedarf überschrieben werden, müssen Sie regelmäßig archiviert und gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="db90f-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="db90f-107">Diese Aktion ist besonders wichtig für Sicherheitsprotokolle, die möglicherweise bei der Untersuchung von Sicherheitsverstößen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="db90f-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="db90f-108">In Ihrer Organisation müssen Richtlinien und Verfahren für die Protokoll Archivierung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="db90f-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="db90f-109">Erstellen von Berichten</span><span class="sxs-lookup"><span data-stu-id="db90f-109">Create reports</span></span>

<span data-ttu-id="db90f-110">Erstellen Sie Statusberichte, die Ihnen bei der Kapazitätsplanung, SLA-Bewertungen und Leistungsanalyse helfen.</span><span class="sxs-lookup"><span data-stu-id="db90f-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="db90f-111">Verwenden Sie tägliche Daten aus dem Ereignisprotokoll und dem System Monitor, um Berichte auf Datenträger, Arbeitsspeicher und CPU-Auslastung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db90f-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="db90f-112">Verwenden Sie System Center Operations Manager, um Verfügbarkeits-und Verfügbarkeitsberichte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db90f-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="db90f-113">In Ihrer Organisation müssen Richtlinien und Verfahren für Statusberichte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="db90f-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="db90f-114">Vorfallberichte</span><span class="sxs-lookup"><span data-stu-id="db90f-114">Incident reports</span></span>

<span data-ttu-id="db90f-115">Führen Sie eine wöchentliche Überprüfung der vorfallberichte Ihrer Organisation durch, die sich auf lync Server beziehen.</span><span class="sxs-lookup"><span data-stu-id="db90f-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="db90f-116">Diese Überprüfung sollte Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="db90f-116">This audit should include the following:</span></span>

  - <span data-ttu-id="db90f-117">Die am häufigsten generierten, behobenen und ausstehenden Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="db90f-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="db90f-118">Lösungen für ungelöste Vorfälle.</span><span class="sxs-lookup"><span data-stu-id="db90f-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="db90f-119">Aktualisieren von Berichten, um neue Trouble-Tickets einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="db90f-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="db90f-120">Aktualisieren eines Dokument-Repositorys zur Fehlerbehebung und zur Obduktion über Ausfälle</span><span class="sxs-lookup"><span data-stu-id="db90f-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="db90f-121">Da das Vorfall Überwachungssystem Ihrer Organisation eine Wahl ist, die von lync Server unabhängig ist, sind bestimmte Anweisungen oder Zeiger nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="db90f-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="db90f-122">Konsultieren Sie die Dokumentation für das System, das Ihre Organisation ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="db90f-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="db90f-123">Überprüfen von IIS-Protokollen und-Leistung</span><span class="sxs-lookup"><span data-stu-id="db90f-123">Check IIS logs and performance</span></span>

<span data-ttu-id="db90f-124">Führen Sie eine wöchentliche Überprüfung der Internet Informationsdienste (IIS)-Protokolle und-Leistung durch.</span><span class="sxs-lookup"><span data-stu-id="db90f-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="db90f-125">Weitere Informationen zum Überwachen von IIS-Protokollen und-Leistung finden Sie unter [Übersicht über die Ereignisprotokollierung in Windows Server 2003 (IIS)](http://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="db90f-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="db90f-126">Die Überprüfung sollte Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="db90f-126">The review should include the following:</span></span>

  - <span data-ttu-id="db90f-127">Webdienst-Cache-Leistungsindikatoren zum Überwachen des WWW-Dienst Caches.</span><span class="sxs-lookup"><span data-stu-id="db90f-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="db90f-128">ASP-Leistungsindikatoren (Active Server Pages) zum Überwachen von Anwendungen, die als ASP ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="db90f-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="db90f-129">Generieren von Datenbankberichten</span><span class="sxs-lookup"><span data-stu-id="db90f-129">Generate database reports</span></span>

<span data-ttu-id="db90f-130">**So generieren Sie Berichte für die SQL-Datenbank**</span><span class="sxs-lookup"><span data-stu-id="db90f-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="db90f-131">Öffnen Sie lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db90f-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="db90f-132">Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="db90f-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="db90f-133">Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="db90f-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="db90f-134">Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="db90f-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="db90f-135">Wenn Sie den Namen der Datenbank anzeigen möchten, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.</span><span class="sxs-lookup"><span data-stu-id="db90f-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="db90f-136">Wenn Sie die aktuellen Benutzer Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="db90f-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="db90f-137">Wenn Sie aktuelle Daten pro Benutzer für einen einzelnen Benutzer des Pools abrufen möchten, erweitern Sie **Benutzer Berichte**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="db90f-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="db90f-138">Wenn Sie aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="db90f-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="db90f-139">Überprüfen auf Sicherheits-und lync Server-Updates</span><span class="sxs-lookup"><span data-stu-id="db90f-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="db90f-140">Identifizieren Sie alle neuen Service Packs, Hotfixes oder Updates.</span><span class="sxs-lookup"><span data-stu-id="db90f-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="db90f-141">Testen Sie diese gegebenenfalls in einem Testlabor, und verwenden Sie die Änderungskontrollverfahren, um die Bereitstellung auf den Produktionsservern zu arrangieren.</span><span class="sxs-lookup"><span data-stu-id="db90f-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="db90f-142">Außerdem sind Updates für lync Server-Komponenten jetzt als Teil von Windows Update verfügbar.</span><span class="sxs-lookup"><span data-stu-id="db90f-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="db90f-143">Alle lync Server-Komponenten Updates müssen gleichzeitig auf allen Servern mit lync Server aktualisiert werden, für die die Updates gelten.</span><span class="sxs-lookup"><span data-stu-id="db90f-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="db90f-144">Ausführen des lync Server 2013 Best Practice Analyzer</span><span class="sxs-lookup"><span data-stu-id="db90f-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="db90f-145">Das lync Server 2013 Best Practices Analyzer-Tool ist ein Diagnosetool, das Konfigurationsinformationen sammelt und bestimmt, ob die Konfiguration gemäß den bewährten Methoden von Microsoft festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="db90f-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="db90f-146">Die Dokumentation für dieses Tool finden Sie unter [lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="db90f-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="db90f-147">Das Tool vergleicht die Konfigurationsdaten Ihrer Bereitstellung mit einer Reihe vordefinierter Regeln für lync Server und meldet potenzielle Probleme.</span><span class="sxs-lookup"><span data-stu-id="db90f-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="db90f-148">Für jedes gemeldete Problem bietet das Tool die aktuelle Konfiguration in der lync Server-Umgebung und die empfohlene Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="db90f-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="db90f-149">Mit dem richtigen Netzwerkzugriff kann das Tool Ihre AD DS und Server untersuchen, auf denen lync Server 2013 ausgeführt wird, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="db90f-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="db90f-150">Proaktive Durchführung von Integritätsprüfungen und überprüfen, ob die Konfiguration gemäß den empfohlenen bewährten Methoden festzulegen ist</span><span class="sxs-lookup"><span data-stu-id="db90f-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="db90f-151">Erstellen einer Liste von Problemen, beispielsweise suboptimal-Konfigurationseinstellungen oder nicht unterstützte oder nicht empfohlene Optionen</span><span class="sxs-lookup"><span data-stu-id="db90f-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="db90f-152">Beurteilen des allgemeinen Zustands eines Systems</span><span class="sxs-lookup"><span data-stu-id="db90f-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="db90f-153">Hilfe zur Problembehandlung bei bestimmten Problemen</span><span class="sxs-lookup"><span data-stu-id="db90f-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="db90f-154">Aufforderung zum Herunterladen von Updates, wenn diese verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="db90f-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="db90f-155">Bereitstellen von Online-und lokalen Dokumentation zu gemeldeten Problemen und einbeziehen von Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="db90f-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="db90f-156">Generieren von Konfigurationsinformationen, die zur späteren Überprüfung erfasst werden können</span><span class="sxs-lookup"><span data-stu-id="db90f-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="db90f-157">Stellen Sie sicher, dass RTCBPA. msi auf allen lync Server 2013-Servern installiert ist, und erstellen Sie einen wöchentlichen Status Prüfbericht.</span><span class="sxs-lookup"><span data-stu-id="db90f-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="db90f-158">Notieren Sie sich die Ergebnisse, und korrigieren Sie, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="db90f-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="db90f-159">Überprüfen der SLA-Leistungskennzahlen</span><span class="sxs-lookup"><span data-stu-id="db90f-159">Review SLA performance figures</span></span>

<span data-ttu-id="db90f-160">Überprüfen Sie die wichtigsten Leistungsdaten für die vorherige Woche.</span><span class="sxs-lookup"><span data-stu-id="db90f-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="db90f-161">Überprüfen Sie die Leistung mit den Anforderungen der SLA.</span><span class="sxs-lookup"><span data-stu-id="db90f-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="db90f-162">Erkennen von Trends und Elementen, die ihre Ziele nicht erreicht haben</span><span class="sxs-lookup"><span data-stu-id="db90f-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="db90f-163">Überprüfen von System Center Operations Manager-Management Pack und Berichte zur Qualität der Erfahrung</span><span class="sxs-lookup"><span data-stu-id="db90f-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="db90f-164">Beziehen und überprüfen Sie das lync Server 2013-Management Pack und die Qualität der Erfahrungsberichte.</span><span class="sxs-lookup"><span data-stu-id="db90f-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="db90f-165">Generieren und Anzeigen von Datenbankberichten für Enterprise-Pools</span><span class="sxs-lookup"><span data-stu-id="db90f-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="db90f-166">**So generieren Sie Pool Berichte**</span><span class="sxs-lookup"><span data-stu-id="db90f-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="db90f-167">Öffnen Sie lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db90f-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="db90f-168">Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="db90f-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="db90f-169">Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="db90f-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="db90f-170">Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="db90f-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="db90f-171">Wenn Sie den Namen der Datenbank anzeigen möchten, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.</span><span class="sxs-lookup"><span data-stu-id="db90f-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="db90f-172">Wenn Sie die aktuellen Benutzer Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="db90f-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="db90f-173">Wenn Sie aktuelle Daten pro Benutzer für einen einzelnen Benutzer des Pools abrufen möchten, erweitern Sie **Benutzer Berichte**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="db90f-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="db90f-174">Wenn Sie aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="db90f-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="db90f-175">Für jeden Enterprise-Pool können Administratoren die Registerkarte **Datenbank** verwenden, um den Datenbanknamen anzuzeigen und Berichte aus der Datenbank abzurufen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="db90f-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="db90f-176">Datenbankberichte und Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="db90f-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db90f-177">Abschnittsüberschrift</span><span class="sxs-lookup"><span data-stu-id="db90f-177">Section</span></span></th>
<th><span data-ttu-id="db90f-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db90f-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db90f-179">Benutzer Zusammenfassungsberichte</span><span class="sxs-lookup"><span data-stu-id="db90f-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="db90f-180">Dbanalyze/v/Report: diag [/SQLServer: Wert]</span><span class="sxs-lookup"><span data-stu-id="db90f-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="db90f-181">In diesem Abschnitt werden aggregierte Informationen zu Benutzern in einem Pool angezeigt, beispielsweise die Anzahl der aktivierten Benutzer, die durchschnittliche Anzahl der Kontakte pro Benutzer und die Anzahl der Benutzer für bestimmte Features.</span><span class="sxs-lookup"><span data-stu-id="db90f-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="db90f-182">Wenn Sie diese Berichte verwenden, können die folgenden Informationen hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="db90f-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="db90f-183">Ein aktivierter Benutzer ist ein Benutzer, der mit dem Snap-in Active Directory-Benutzer und-Computer für lync Server 2013 aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="db90f-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="db90f-184">Ein aktiver Benutzer ist ein Benutzer, der sich angemeldet oder registriert hat.</span><span class="sxs-lookup"><span data-stu-id="db90f-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="db90f-185">Die Zusammenfassungsberichte bieten auch eine Reihe von statistischen Informationen zu Kontakten.</span><span class="sxs-lookup"><span data-stu-id="db90f-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="db90f-186">Diese Statistiken gelten nur für die Bevölkerung von Benutzern, die sich mindestens einmal angemeldet haben und die mindestens einen Kontakt haben.</span><span class="sxs-lookup"><span data-stu-id="db90f-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="db90f-187">Daher wird normalerweise keine minimale Anzahl von Kontakten von 0 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db90f-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="db90f-188">Wenn ein Benutzer über keine Kontakte verfügt (aber aktiv ist, in dem sich der Benutzer registriert hat), wird möglicherweise für einige Statistik &lt;Felder&gt; leer angezeigt:</span><span class="sxs-lookup"><span data-stu-id="db90f-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db90f-189">Berichte pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="db90f-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="db90f-190">Dbanalyze/v/Report: Datenträger [/SQLServer: Wert]</span><span class="sxs-lookup"><span data-stu-id="db90f-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="db90f-191">Im Gegensatz zu den Zusammenfassungsberichten, die über eine Benutzerpopulation berechnet werden, handelt es sich um Berichte über einen bestimmten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="db90f-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db90f-192">Konferenz Zusammenfassungsberichte</span><span class="sxs-lookup"><span data-stu-id="db90f-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="db90f-193">Dbanalyze/v/Report: conf [/SQLServer: Wert]</span><span class="sxs-lookup"><span data-stu-id="db90f-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="db90f-194">In diesem Abschnitt werden aggregierte Informationen zu Konferenz Zusammenfassungs Statistiken für den Pool angezeigt, beispielsweise die Anzahl aktiver Konferenzen und die Gesamtzahl der Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="db90f-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="db90f-195">Ausführen von Bandbreiten Auslastungsanalyse</span><span class="sxs-lookup"><span data-stu-id="db90f-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="db90f-196">Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten des Bandbreitenverbrauchs durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="db90f-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="db90f-197">Diese Berichte können verwendet werden, um das aktuelle Muster der Bandbreitennutzung zu verstehen und bei der Planung der Bandbreitenkapazität zu helfen.</span><span class="sxs-lookup"><span data-stu-id="db90f-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="db90f-198">Das Tool durchläuft außerdem die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="db90f-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="db90f-199">Das Tool bietet folgende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="db90f-199">This tool does the following:</span></span>

  - <span data-ttu-id="db90f-200">Generiert bestimmte Berichte für die audionutzung über das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="db90f-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="db90f-201">Hilfe bei einer effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="db90f-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="db90f-202">Der Bandbreiten Auslastungs Analysator kann grafische Plots von Bandbreiten Kapazitäts-und Nutzungsberichten generieren.</span><span class="sxs-lookup"><span data-stu-id="db90f-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="db90f-203">Sie sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="db90f-203">They are as follows:</span></span>

  - <span data-ttu-id="db90f-204">Alle WAN-Verbindungen im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="db90f-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="db90f-205">Gefiltert nach ausgewählten WAN-Links, die ausgewählt wurden</span><span class="sxs-lookup"><span data-stu-id="db90f-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="db90f-206">Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben</span><span class="sxs-lookup"><span data-stu-id="db90f-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="db90f-207">Gefiltert nach WAN-Links, die die bereitgestellte Bandbreite unter Verwenden</span><span class="sxs-lookup"><span data-stu-id="db90f-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="db90f-208">Filtern nach WAN-Links, die kritische Ebenen erreichen (eine Bandbreitennutzung, die größer als 90 Prozent der Bandbreitenkapazität der WAN-Verbindung ist)</span><span class="sxs-lookup"><span data-stu-id="db90f-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="db90f-209">Nach WAN-Verknüpfungstyp gefiltert – Netzwerk-Standort-Links, interregionale Links und Links innerhalb einer Website</span><span class="sxs-lookup"><span data-stu-id="db90f-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="db90f-210">Gefiltert nach Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="db90f-210">Filtered by network region</span></span>

<span data-ttu-id="db90f-211">Die Dokumentation zu diesem Tool finden Sie in der [Dokumentation zur lync Server 2013 Resource Kit-Tools](http://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="db90f-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db90f-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db90f-212">See Also</span></span>


[<span data-ttu-id="db90f-213">Checkliste für wöchentliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="db90f-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

