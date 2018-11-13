---
title: Bereitstellen von Anrufqualität Dashboard für Skype für Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Zusammenfassung: Informationen Sie zu den Bereitstellungsprozess für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 31e1dc8d5508c7d3d31de0ec3af0b9c8c06a6c40
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294989"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a><span data-ttu-id="bed3f-104">Bereitstellen von Anrufqualität Dashboard für Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bed3f-104">Deploy Call Quality Dashboard for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bed3f-105">**Zusammenfassung:** Informationen Sie zu den Bereitstellungsprozess für die Qualitätsdashboard aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="bed3f-106">Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bed3f-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="bed3f-107">Übersicht über die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="bed3f-107">Deployment Overview</span></span>

<span data-ttu-id="bed3f-108">Anruf Quality Dashboard (CQD) besteht aus drei Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="bed3f-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="bed3f-109">**Archivdatenbank**, in dem die Daten Quality of Experience (QoE) repliziert und gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="bed3f-110">**Cubes**, auf dem die Daten aus der QoE-Archivdatenbank für optimierte und schnellen Zugriff aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="bed3f-111">**Portal**, wobei Benutzer können auf einfache Weise Abfragen und Visualisieren von QoE-Daten.</span><span class="sxs-lookup"><span data-stu-id="bed3f-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="bed3f-113">Der Setup-Prozess für QoE-Archiv umfasst die QoE-Archivdatenbank erstellen, Bereitstellen einer SQL Server gespeicherte Prozedur, die die Daten aus der Quelle QoE-Metriken Datenbank in QoE-Archivdatenbank verschoben werden und Einrichten von SQL Server Agent-Auftrags zum Ausführen der gespeicherten die Prozedur in einem regelmäßigen Intervall.</span><span class="sxs-lookup"><span data-stu-id="bed3f-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="bed3f-114">Cube-Bereitstellung Ruft Informationen aus der Benutzer auf, in dem das QoE-Archiv befindet sich in den Cube bereitgestellt und richtet einen regulären SQL Server-Agent-Auftrag, der den Cube in regelmäßigen Abständen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="bed3f-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="bed3f-115">Portal installieren erstellt eine Repositorydatenbank, die die Zuordnung der CQD Benutzer Berichten oder Abfragen des Benutzers gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="bed3f-116">Klicken Sie dann wird eingerichtet, die das Dashboard ist, in dem Benutzer können finden Sie eine vordefinierte Reihe von Berichten als auch anpassen und Erstellen ihrer eigenen Abfragen, um Daten aus dem Cube visualisieren, IIS Web-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bed3f-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="bed3f-117">Das Portal installieren erstellt zwei zusätzliche Webanwendungen, die für Benutzer zum programmgesteuerten Zugriff auf das Repository und den Cube APIs verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="bed3f-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="bed3f-118">(Diese APIs werden intern von sowie das Dashboard verwendet.)</span><span class="sxs-lookup"><span data-stu-id="bed3f-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="bed3f-119">**Phase**</span><span class="sxs-lookup"><span data-stu-id="bed3f-119">**Phase**</span></span>|<span data-ttu-id="bed3f-120">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="bed3f-120">**Steps**</span></span>|<span data-ttu-id="bed3f-121">**Rollen und Gruppenmitgliedschaften**</span><span class="sxs-lookup"><span data-stu-id="bed3f-121">**Roles and group membership**</span></span>|<span data-ttu-id="bed3f-122">**Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="bed3f-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bed3f-123">Erforderliche Hardware und Software zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bed3f-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="bed3f-124">Nach der Konfiguration CQD entscheiden Sie, und wählen Sie einen SQL Server aus dem die Installation ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="bed3f-125">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="bed3f-126">Abschnitt "Vor dem Installieren von Anforderungen", in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bed3f-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="bed3f-127">Installieren Sie CQD.</span><span class="sxs-lookup"><span data-stu-id="bed3f-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="bed3f-128">Führen Sie die MSI-Datei nach der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bed3f-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="bed3f-129">Zum Ausführen des Setups muss das Installieren von Konto werden ein Domänenbenutzer, der Mitglied der Gruppe der lokalen Administratoren ist und verfügen über Lesezugriff auf QoE-Metriken Datenbank auf dem Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="bed3f-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="bed3f-130">"Konten und Bereitstellungsschritte" Abschnitte in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bed3f-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="bed3f-131">Gewähren des Benutzerzugriffs.</span><span class="sxs-lookup"><span data-stu-id="bed3f-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="bed3f-132">Es wird empfohlen, für die Verwaltung der benutzerautorisierung-Portal, mithilfe der URL-Autorisierung in IIS 7.0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="bed3f-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="bed3f-133">Weitere Informationen finden Sie unter [Grundlegendes zu IIS 7.0-URL-Autorisierung](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="bed3f-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="bed3f-134">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="bed3f-135">Verwalten des Benutzerzugriffs für den Abschnitt Portal in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bed3f-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="bed3f-136">Optional: Geben Sie Zuordnungsinformationen Subnetz.</span><span class="sxs-lookup"><span data-stu-id="bed3f-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="bed3f-137">Füllen Sie auf Netzwerk- und Erstellen von Zuordnungstabellen in QoE-Archivdatenbank.</span><span class="sxs-lookup"><span data-stu-id="bed3f-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="bed3f-138">Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.</span><span class="sxs-lookup"><span data-stu-id="bed3f-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="bed3f-139">Abschnitt "Bereitstellung Subnetzinformationen", in der Dokumentation für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bed3f-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="bed3f-140">Bereitstellung von Anrufqualität Dashboard umfasst Einrichten der Infrastruktur und Installieren der Software.</span><span class="sxs-lookup"><span data-stu-id="bed3f-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="bed3f-141">Das folgende Verfahren beschreibt den Prozess.</span><span class="sxs-lookup"><span data-stu-id="bed3f-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="bed3f-142">Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="bed3f-142">Deployment Steps</span></span>

1. <span data-ttu-id="bed3f-143">Kopieren Sie die CallQualityDashboard.msi auf dem Computer, auf dem die Archiv Datenbankkomponente des CQD ist installiert werden soll (Dies ist der Computer, auf SQL Server installiert ist).</span><span class="sxs-lookup"><span data-stu-id="bed3f-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="bed3f-144">Führen Sie die MSI-Datei (Windows Sie werden aufgefordert, mit Administratorrechten ausgeführt werden, dazu).</span><span class="sxs-lookup"><span data-stu-id="bed3f-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="bed3f-145">Akzeptieren Sie den Endbenutzer-Lizenzvertrag.</span><span class="sxs-lookup"><span data-stu-id="bed3f-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="bed3f-146">Wählen Sie den Zielordner, in dem Dateien im Zusammenhang mit Anrufqualität Dashboardkomponenten befinden oder den Standardspeicherort akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="bed3f-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="bed3f-147">Wählen Sie alle Features aus.</span><span class="sxs-lookup"><span data-stu-id="bed3f-147">Select all features.</span></span>
    
6. <span data-ttu-id="bed3f-148">Geben Sie auf der Seite QoE-Archive-Konfiguration die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="bed3f-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="bed3f-149">**QoE-Metriken SQLServer:** SQL Server-Instanznamen, auf dem sich die QoE-Metriken DB befindet (Dies ist die Datenquelle).</span><span class="sxs-lookup"><span data-stu-id="bed3f-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="bed3f-150">**QoE-Archiv SQL Server-Name:** Dies ist nur-Lese-Feld und auf den vollqualifizierten Domänennamen des lokalen Computers behoben.</span><span class="sxs-lookup"><span data-stu-id="bed3f-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="bed3f-151">Archiv DB kann nur auf dem lokalen Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="bed3f-152">**QoE-Archiv SQL Server-Instanz:** Eine lokale SQL Server-Instanznamen für wobei ist das Archiv DB erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed3f-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="bed3f-153">Um eine Standardinstanz von SQL Server verwenden, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="bed3f-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="bed3f-154">Um eine benannte Instanz von SQL Server verwenden, geben Sie den Namen der Instanz (z. B. Name nach der "\").</span><span class="sxs-lookup"><span data-stu-id="bed3f-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="bed3f-155">**QoE-Archivdatenbank:** Diese Option ist standardmäßig auf "Neue Datenbank erstellen" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bed3f-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="bed3f-156">Da Archiv DB Upgrade nicht unterstützt wird, ist die einzige Situation, unter der die Option "Vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Archivdatenbank die Schema der Build installiert werden hat.</span><span class="sxs-lookup"><span data-stu-id="bed3f-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="bed3f-157">**Datenbank Dateiverzeichnis:** Der Pfad, in dem die Datenbankdateien (MDF- und LDF) für die Archivierung DB platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed3f-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="bed3f-158">Dies sollte auf einem Laufwerk (HDD2 in die empfohlene Hardwarekonfiguration) getrennt vom Betriebssystem sein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="bed3f-159">Beachten Sie, dass seit die Dateinamen in der Installation behoben werden, um alle Konflikte zu vermeiden empfohlen wird, dass ein leeres Verzeichnis ohne Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="bed3f-160">**Verwenden Sie mehrere Partitionen:** Die Standardeinstellung von "Mehrere Partition", die Business Intelligence-Edition oder Enterprise Edition von SQL Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bed3f-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="bed3f-161">Wählen Sie "Einzelpartition" Option aus, für die Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bed3f-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="bed3f-162">Beachten Sie, dass Cube Verarbeitung Leistung beeinträchtigt werden kann, wenn das Einzelpartition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bed3f-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="bed3f-163">Die Auswahl für Verwenden mehrerer Partitionen Option kann nicht geändert werden, wenn Setup abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="bed3f-164">Um es zu ändern, der Cube Feature benötigt, erste deinstalliert und anschließend erneut installiert, mit der Option "Ändern" in der Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="bed3f-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="bed3f-165">**Partitionieren Dateiverzeichnis:** Der Pfad, in dem die Partitionen für die QoE-Archivdatenbank platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed3f-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="bed3f-166">Dies sollte (HDD3 in die empfohlene Hardwarekonfiguration) getrennt vom OS Laufwerk und SQL-Datenbank Protokolllaufwerk Dateien auf einem Laufwerk sein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="bed3f-167">Beachten Sie, dass seit die Dateinamen in der Installation behoben werden, um alle Konflikte zu vermeiden empfohlen wird, dass ein leeres Verzeichnis ohne Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="bed3f-168">**SQL-Agent Job-Benutzer - Benutzernamen &amp; Kennwort:** Dienstkontoname Domäne und das Kennwort (maskiert), mit der der "QoE-Archivdaten" Schritt des Auftrags für SQL Server-Agent ausgeführt (die zum Abrufen von Daten aus der Datenbank der QoE-Metriken in Archiv DB, damit dieses Konto Lesezugriff auf den QoE-Metriken DB, benötigen die gespeicherte Prozedur ausgeführt wird  wie im Abschnitt Konten angegeben.</span><span class="sxs-lookup"><span data-stu-id="bed3f-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="bed3f-169">Dieses Konto muss außerdem ein Benutzername in der QoE-Archiv SQL Server-Instanz haben).</span><span class="sxs-lookup"><span data-stu-id="bed3f-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="bed3f-170">Das Konto, das SQL Server-Instanz unter, wie beispielsweise NT-SERVICE\MSSQLSERVER ausgeführt wird benötigen Zugriffsberechtigungen für die Verzeichnisse obigen für die Installation erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bed3f-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="bed3f-171">Weitere Informationen hierzu finden Sie unter [Konfigurieren Dateisystemberechtigungen für den Zugriff auf das Datenbankmodul](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bed3f-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="bed3f-172">Beim nächsten klicken, wird das Installationsprogramm Prüfungen und Untersuchung Bericht durchführen, wenn Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="bed3f-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="bed3f-173">Wenn alle vorausgesetzte Überprüfungen Durchgang gelangen das Installationsprogramm auf der Seite Cubekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="bed3f-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bed3f-174">Wenn das Installationsprogramm eine Warnmeldung angezeigt, die der SQL Server-Agent-Dienst für QoE-Archiv SQL Server-Instanz derzeit nicht ausgeführt wird wird, kann die Installation fortgesetzt werden, aber Post-Installation stellen Sie sicher, dass SQL-Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf Automatische, sodass die geplante Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bed3f-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="bed3f-175">Geben Sie auf der Seite Cubekonfiguration die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="bed3f-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="bed3f-176">**QoE-Archiv SQL Server-Name:** Dies ist nur-Lese-Feld und auf den vollqualifizierten Domänennamen des lokalen Computers behoben.</span><span class="sxs-lookup"><span data-stu-id="bed3f-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="bed3f-177">Cube kann nur auf dem Computer installiert werden, sind QoE-Archivdatenbank (Notiz.</span><span class="sxs-lookup"><span data-stu-id="bed3f-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="bed3f-178">Cube selbst kann auf einem Remotecomputer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="bed3f-179">Siehe unten)</span><span class="sxs-lookup"><span data-stu-id="bed3f-179">See below)</span></span>
    
   - <span data-ttu-id="bed3f-180">**QoE-Archiv SQL Server-Instanz:** Name der SQL Server-Instanz auf dem sich die QoE-Archiv-DB befindet.</span><span class="sxs-lookup"><span data-stu-id="bed3f-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="bed3f-181">Um eine Standardinstanz von SQL Server anzugeben, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="bed3f-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="bed3f-182">Um eine benannte Instanz von SQL Server anzugeben, geben Sie den Instanznamen (z. B. Name nach der "\").</span><span class="sxs-lookup"><span data-stu-id="bed3f-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="bed3f-183">Wenn QoE-Archiv-Komponente für die Installation ausgewählt wurde, wird dieses Feld bereits ausgefüllte mit dem Wert, der auf der Seite Konfiguration der QoE-Archiv bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="bed3f-184">**-Cubes in Analysis-Server:** SQL Server Analysis Services-Instanznamen für wobei ist der Cube erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed3f-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="bed3f-185">Dies kann einem anderen Computer aber der installierende Benutzer muss ein Mitglied der Zielinstanz von SQL Server Analysis Services-Server-Administratoren sein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="bed3f-186">Weitere Informationen zum Konfigurieren von Analysis Services-Server-Administrator Berechtigungen finden Sie unter [Server-Administrator-Berechtigungen erteilen (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="bed3f-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="bed3f-187">**Verwenden Sie mehrere Partitionen:** Die Standardeinstellung von "Mehrere Partition", die Business Intelligence-Edition oder Enterprise Edition von SQL Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bed3f-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="bed3f-188">Wählen Sie "Einzelpartition" Option aus, für die Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bed3f-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="bed3f-189">Beachten Sie, dass Cube Verarbeitung Leistung beeinträchtigt werden kann, wenn das Einzelpartition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bed3f-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="bed3f-190">Die Auswahl für Verwenden mehrerer Partitionen Option kann nicht geändert werden, wenn Setup abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="bed3f-191">Um es zu ändern, der Cube Feature benötigt, erste deinstalliert und anschließend erneut installiert, mit der Option "Ändern" in der Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="bed3f-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="bed3f-192">**Cube User - Benutzername &amp; Kennwort:** Dienstkontoname Domäne und das Kennwort (maskiert), die die Cubes Verarbeitung auslöst.</span><span class="sxs-lookup"><span data-stu-id="bed3f-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="bed3f-193">Wenn QoE-Archiv-Komponente für die Installation ausgewählt wurde, in diesem Feld mit dem Wert auf der Seite Konfiguration der Archivierung für den SQL-Agent-Auftrag Benutzer bereits ausgefüllte werden, aber es wird empfohlen, ein anderes Domänenkonto Service angeben, sodass Setup gewähren kann die mindestens erforderliche Berechtigung hinzu.</span><span class="sxs-lookup"><span data-stu-id="bed3f-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="bed3f-194">Wenn Sie auf Weiter klicken, wird eine weitere runde der Überprüfung durchgeführt, und alle Problem wird gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="bed3f-195">Nach dem erfolgreichen Abschluss der Validierung gelangen das Installationsprogramm auf der Seite Portal-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="bed3f-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="bed3f-196">Geben Sie auf der Seite Portal-Konfiguration die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="bed3f-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="bed3f-197">**QoE-Archiv SQLServer:** Name der SQL Server-Instanz auf dem sich die QoE-Archivdatenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="bed3f-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="bed3f-198">Beachten Sie, dass im Gegensatz zu der Seite QoE-Archiv-Konfiguration und der Seite Cubekonfiguration, den Namen des Computers nicht behoben und bereitgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="bed3f-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="bed3f-199">Wenn QoE-Archiv-Komponente für die Installation ausgewählt wurde, wird dieses Feld bereits ausgefüllte mit dem Wert, der auf der Seite Konfiguration der QoE-Archiv bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="bed3f-200">**-Cubes in Analysis-Server:** SQL Server Analysis Services-Instanznamen für, in der Cube gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="bed3f-201">Wenn der Cube-Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem Wert auf der Seite Cubekonfiguration bereits ausgefüllte sein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="bed3f-202">**Repository SQLServer:** Name der SQL Server-Instanz, in dem die Repositorydatenbank ist erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed3f-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="bed3f-203">Wenn der Name des SQL Server-Instanz für, in die QoE-Archivdatenbank gespeichert ist weiter oben in der Setup (in anderen Komponenten) bereitgestellt wurde, wird dieses Feld bereits ausgefüllte, mit dem Namen der QoE-Archiv DB SQL Server-Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="bed3f-204">Dies kann eine beliebige SQL Server-Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="bed3f-205">**Repositorydatenbank:** Die Option ist standardmäßig auf "Neue Datenbank erstellen" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bed3f-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="bed3f-206">Da Repository DB Upgrade nicht unterstützt wird, ist die einzige Situation, unter der die Option "Vorhandene Datenbank verwenden" verwendet werden kann, wenn der vorhandenen Repository DB die Schema der Build installiert werden hat.</span><span class="sxs-lookup"><span data-stu-id="bed3f-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="bed3f-207">**IIS-Anwendungspool-User - Benutzername &amp; Kennwort:** Das Konto, dem unter IIS-Anwendungspool ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bed3f-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="bed3f-208">Die Felder Benutzername und Kennwort werden abgeblendet, wenn integrierten Systemkonten ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="bed3f-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="bed3f-209">Diese Felder werden nur aktiviert werden, wenn "Andere" aus der Dropdownliste ausgewählt ist, damit der Benutzer die Domäne Service-Kontoinformationen eingeben kann.</span><span class="sxs-lookup"><span data-stu-id="bed3f-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="bed3f-210">Wenn Sie auf Weiter klicken, wird die endgültige Rundung der Überprüfung ausgeführt, um sicherzustellen, dass die SQL Server-Instanzen mithilfe der Anmeldeinformationen und, dass IIS auf dem Computer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="bed3f-211">Nach dem erfolgreichen Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="bed3f-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="bed3f-212">Wenn das Installationsprogramm abgeschlossen ist, wird sehr wahrscheinlich der Auftrag SQL Server-Agent ausgeführt wird, wie folgt das Laden des QoE-Daten und die Cubeverarbeitung sein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="bed3f-213">In Abhängigkeit vom Umfang des Datenteils QoE wird das Portal nicht Daten für die Anzeige von noch verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bed3f-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="bed3f-214">Um den Status der Cubeverarbeitung und Laden von Daten zu überprüfen, wechseln Sie zur `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="bed3f-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="bed3f-215">Beachten Sie, dass die URL für das Überprüfen des Status des Download Cube Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="bed3f-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="bed3f-216">Bei Eingabe von 'Health' die URL nicht funktionsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="bed3f-217">Geben Sie am Ende der URL mit dem Großbuchstaben h ' Health'</span><span class="sxs-lookup"><span data-stu-id="bed3f-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="bed3f-218">Ausführliches Protokollnachrichten werden angezeigt, wenn Debug-Modus aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="bed3f-219">Um Debug-Modus aktivieren möchten, besuchen Sie **%SystemDrive%\Programme\Microsoft Files\Skype für Business 2015 CQD\QoEDataService\web.config**, und aktualisieren Sie die folgende Zeile, sodass der Wert auf **True**festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="bed3f-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="bed3f-220">Die Hauptseite Portal ist auf den über `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="bed3f-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="bed3f-221">Verwalten des Benutzerzugriffs für das Portal</span><span class="sxs-lookup"><span data-stu-id="bed3f-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="bed3f-222">Es wird empfohlen, für die Verwaltung der benutzerautorisierung-Portal, mithilfe der URL-Autorisierung in IIS 7.0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="bed3f-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="bed3f-223">Weitere Informationen zur Sicherheit von IIS finden Sie unter [Grundlegendes zu IIS 7.0-URL-Autorisierung ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="bed3f-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="bed3f-224">Jede Web Site oder Web-Anwendung erben die Standard-URL-Autorisierung konfiguriert für die gesamte IIS, wobei es sich üblicherweise "Alle Benutzer zulassen".</span><span class="sxs-lookup"><span data-stu-id="bed3f-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="bed3f-225">Wenn Zugriff auf das Portal restriktiver sein muss, können dann Administratoren Zugriff auf nur die bestimmten Gruppe von Benutzern gewähren durch Bearbeiten der "Autorisierungsregeln".</span><span class="sxs-lookup"><span data-stu-id="bed3f-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Anrufqualität bereitstellen – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="bed3f-227">Das Symbol Autorisierungsregeln darf nicht mit ".NET Authorization" unter dem ASP.NET-Bereich, einen anderen Autorisierungsmechanismus verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="bed3f-228">Administratoren sollten die geerbte "alle Benutzer zulassen" Regel zuerst entfernen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="bed3f-229">Dadurch wird verhindert, dass keine nicht autorisierter Benutzer den Zugriff auf das Portal.</span><span class="sxs-lookup"><span data-stu-id="bed3f-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![CQD bereitstellen](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="bed3f-231">Administratoren sollten Sie als Nächstes Hinzufügen neuer Regeln auf zulassen und bestimmten Benutzern die Berechtigung, um auf das Portal zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="bed3f-232">Es wird empfohlen, eine lokale Gruppe namens "CQDPortalUsers" erstellt werden, um die Benutzer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="bed3f-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Anrufqualitäts-Dashboard bereitstellen](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="bed3f-234">Die Konfigurationsdetails werden in der Datei web.config befindet sich unter dem Portal physikalische Verzeichnis gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bed3f-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="bed3f-235">Im nächste Schritt wird das Dashboard, der die CQD konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bed3f-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="bed3f-236">Nachdem der Benutzer von IIS authentifiziert werden, müssen sie über die Datei im Verzeichnis CQD berechtigt, um Portal Web-Inhalt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="bed3f-237">Es ist möglich, ändern Sie die ACLs über die Sicherheitsregisterkarte CQD Directory-Eigenschaften, um einzelne Benutzer oder Gruppen hinzuzufügen. wird jedoch empfohlen, die Dateiberechtigungen unverändert lassen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="bed3f-238">Ändern Sie stattdessen die IIS-Einstellung, um die IIS-Arbeitsprozess verwenden, um das Verzeichnis CQD zugreifen, unabhängig davon, das welche Benutzer authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="bed3f-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="bed3f-239">Es ist wichtig, nur diese Einstellung für die Anwendung CQD und nicht für die zwei API-Anwendungen ändern: QoEDataService und QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="bed3f-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="bed3f-240">Konfigurieren von Zugriff auf die Datei für die CQD (Dashboard)</span><span class="sxs-lookup"><span data-stu-id="bed3f-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="bed3f-241">Öffnen Sie den Konfigurations-Editor CQD.</span><span class="sxs-lookup"><span data-stu-id="bed3f-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="bed3f-243">Klicken Sie im Abschnitt wählen Sie **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="bed3f-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="bed3f-245">Ändern Sie AuthenticatedUserOverride in **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="bed3f-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="bed3f-247">Klicken Sie auf **Übernehmen** auf der rechten Seite der Seite.</span><span class="sxs-lookup"><span data-stu-id="bed3f-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="bed3f-248">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="bed3f-248">Known Issues</span></span>

<span data-ttu-id="bed3f-249">In seltenen Fällen kann das Installationsprogramm die richtigen Einstellungen in IIS zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-249">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="bed3f-250">Manuelle Änderung ist erforderlich, um Benutzer zur Anmeldung bei der CQD zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-250">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="bed3f-251">Wenn Benutzer Probleme beim Anmelden haben, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="bed3f-251">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="bed3f-252">Öffnen Sie den IIS-Manager, und navigieren Sie auf Standardwebsite.</span><span class="sxs-lookup"><span data-stu-id="bed3f-252">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="bed3f-254">Klicken Sie auf "Authentifizierung".</span><span class="sxs-lookup"><span data-stu-id="bed3f-254">Click on "Authentication".</span></span> <span data-ttu-id="bed3f-255">Wenn die "Anonyme Authentifizierung", "ASP.NET Impersonation", "Formularauthentifizierung" und "Windows-Authentifizierung" die nachfolgend aufgeführten Einstellungen nicht übereinstimmen, auch manuell ändern Sie, um die folgenden Einstellungen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-255">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="bed3f-256">Alle anderen Authentifizierungsmechanismen sollte deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-256">All other authentication mechanisms should be disabled.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="bed3f-258">Klicken Sie für "Windows-Authentifizierung" auf der rechten Seite auf Erweiterte Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-258">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="bed3f-260">"Erweiterten Schutz" auf Accept festgelegt, und aktivieren Sie das Kontrollkästchen "Enable-Kernelmodusauthentifizierung".</span><span class="sxs-lookup"><span data-stu-id="bed3f-260">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="bed3f-262">Wiederholen Sie die obigen Schritte für jede die Einträge "CQD", "QoEDataService" und "QoERepositoryService" unter "Default Web Site" ein.</span><span class="sxs-lookup"><span data-stu-id="bed3f-262">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="bed3f-263">Für HTTP und HTTPS Port Bindungen erstellt der Installer auf die Standard-Portnummern (Port 80 für HTTP) und Port 443 für HTTPS Port Bindungen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-263">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="bed3f-264">Liegt eine andere Website auf dem Computer, der diese Bindungen verwendet, es ist ein Konflikt und das Verhalten von IIS kann nicht vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-264">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="bed3f-265">Die beste Möglichkeit zum Vermeiden dieses Problems ist, um sicherzustellen, dass keine anderen Websites vor der Installation von CQD Ports 80 und 443 zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bed3f-265">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="bed3f-266">So aktivieren SSL/TLS in IIS und erzwingen, dass Benutzer eine Verbindung herstellen über secure HTTPS anstelle von HTTP:</span><span class="sxs-lookup"><span data-stu-id="bed3f-266">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="bed3f-267">Konfigurieren von Secure Sockets Layer in IIS, finden Sie unter [Konfigurieren von Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="bed3f-267">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="bed3f-268">Ersetzen Sie abschließend `http` mit `https`.</span><span class="sxs-lookup"><span data-stu-id="bed3f-268">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="bed3f-269">Anweisungen zum Aktivieren von TLS in der SQL Server-Verbindungen finden Sie unter [Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe von Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="bed3f-269">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="bed3f-270">Fehler bei der Synchronisierung Cube</span><span class="sxs-lookup"><span data-stu-id="bed3f-270">Cube Sync Fails</span></span>

<span data-ttu-id="bed3f-271">QoEMetrics kann einige ungültige Datensätze basierend auf Endbenutzer Uhren enthalten.</span><span class="sxs-lookup"><span data-stu-id="bed3f-271">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="bed3f-272">Wenn die Zeit skew größer als 60 Jahre ist, schlägt der Import Cube fehl.</span><span class="sxs-lookup"><span data-stu-id="bed3f-272">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="bed3f-273">Überprüfen Sie die Funktionen Min und Max StartTime/EndTime nachstehend verwenden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-273">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="bed3f-274">Suchen und Löschen von Datensätzen in der Zukunft ganz vergangenen und sehr weit entfernt, können sie ignoriert, und sie werden die Sync-Prozesse unterteilen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-274">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="bed3f-275">Wählen Sie MIN(StartTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="bed3f-275">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="bed3f-276">Wählen Sie MAX(StartTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="bed3f-276">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="bed3f-277">Wählen Sie MIN(EndTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="bed3f-277">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="bed3f-278">Wählen Sie MAX(EndTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="bed3f-278">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="bed3f-279">Aufgaben nach der Installation</span><span class="sxs-lookup"><span data-stu-id="bed3f-279">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="bed3f-280">Importieren von Gebäude und Netzwerke</span><span class="sxs-lookup"><span data-stu-id="bed3f-280">Importing Buildings and Networks</span></span>

<span data-ttu-id="bed3f-281">Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="bed3f-281">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="bed3f-282">Definieren Sie zum Erstellen von Inhaltstypen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="bed3f-282">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="bed3f-283">Definieren Sie zum Erstellen von den Besitz Typen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="bed3f-283">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="bed3f-284">Definieren von Netzwerk-Typen (dringend empfohlen)</span><span class="sxs-lookup"><span data-stu-id="bed3f-284">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="bed3f-285">Importieren von Gebäude (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="bed3f-285">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="bed3f-286">Import-Subnetze (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="bed3f-286">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="bed3f-287">Erstellen von Typen definieren</span><span class="sxs-lookup"><span data-stu-id="bed3f-287">Define Building Types</span></span>

<span data-ttu-id="bed3f-288">Erstellen von Typen werden verwendet, um die verschiedenen Gebäuden Definitionen oder Typen innerhalb Ihrer Organisation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bed3f-288">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bed3f-289">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-289">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="bed3f-290">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bed3f-290">Examples</span></span>
  
- <span data-ttu-id="bed3f-291">Hauptsitz</span><span class="sxs-lookup"><span data-stu-id="bed3f-291">Headquarters</span></span>
    
- <span data-ttu-id="bed3f-292">Zweigstellen</span><span class="sxs-lookup"><span data-stu-id="bed3f-292">Remote Office</span></span>
    
- <span data-ttu-id="bed3f-293">Sofern Speicherort</span><span class="sxs-lookup"><span data-stu-id="bed3f-293">Joint-venture location</span></span>
    
  <span data-ttu-id="bed3f-294">**Beispiel-SQL-Syntax**</span><span class="sxs-lookup"><span data-stu-id="bed3f-294">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="bed3f-295">Der Parameter BuildingTypeId und BuildingTypeDesc sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bed3f-295">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="bed3f-296">Erstellen von Besitz Typen definieren</span><span class="sxs-lookup"><span data-stu-id="bed3f-296">Define Building Ownership Types</span></span>

<span data-ttu-id="bed3f-297">Gesamtbetriebskosten Typen dienen zum Besitzer Vs geleaste Ressourcen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="bed3f-297">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bed3f-298">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-298">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="bed3f-299">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bed3f-299">Examples</span></span>
  
- <span data-ttu-id="bed3f-300">Contoso geleaste nicht-RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="bed3f-300">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="bed3f-301">Contoso geleaste RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="bed3f-301">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="bed3f-302">Contoso gehören</span><span class="sxs-lookup"><span data-stu-id="bed3f-302">Contoso Owned</span></span>
    
- <span data-ttu-id="bed3f-303">Niederlassung geleaste</span><span class="sxs-lookup"><span data-stu-id="bed3f-303">Subsidiary Leased</span></span>
    
  <span data-ttu-id="bed3f-304">**Beispiel-SQL-Syntax**</span><span class="sxs-lookup"><span data-stu-id="bed3f-304">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

<span data-ttu-id="bed3f-305">Der Parameter OwnershipTypeId und OwnershipTypeDesc sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bed3f-305">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="bed3f-306">Definieren von Netzwerknamen</span><span class="sxs-lookup"><span data-stu-id="bed3f-306">Define Network Names</span></span>

<span data-ttu-id="bed3f-307">Netzwerktypen dienen zum Beschreiben der verschiedenen Types von Netzwerken innerhalb der Organisation.</span><span class="sxs-lookup"><span data-stu-id="bed3f-307">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="bed3f-308">Dies gibt Ihnen die Möglichkeit zu filtern (oder herauszufiltern) bestimmte Typen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-308">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bed3f-309">Es wird dringend empfohlen, Netzwerknamen definieren, aber es ist optional.</span><span class="sxs-lookup"><span data-stu-id="bed3f-309">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="bed3f-310">Wenn Sie nicht Netzwerknamen definieren möchten, sicherstellen Sie, dass der einzelnen CqdNetwork Eintrag einer BuildingId 0 verfügt.</span><span class="sxs-lookup"><span data-stu-id="bed3f-310">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="bed3f-311">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bed3f-311">Examples</span></span>
  
- <span data-ttu-id="bed3f-312">VPN</span><span class="sxs-lookup"><span data-stu-id="bed3f-312">VPN</span></span>
    
- <span data-ttu-id="bed3f-313">ÜBUNG</span><span class="sxs-lookup"><span data-stu-id="bed3f-313">LAB</span></span>
    
  <span data-ttu-id="bed3f-314">**Beispiel-SQL-Syntax**</span><span class="sxs-lookup"><span data-stu-id="bed3f-314">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="bed3f-315">Die Parameter NetworkNameID und Netzwerkname sind erforderlich, der NetworkType-Parameter ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-315">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="bed3f-316">Import Gebäude</span><span class="sxs-lookup"><span data-stu-id="bed3f-316">Import Buildings</span></span>

<span data-ttu-id="bed3f-317">Importieren von Gebäude können Sie bestimmte Insights (schlechter Anrufe pro erstellen WiFi/kabelgebundene usw.). erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="bed3f-317">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bed3f-318">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-318">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="bed3f-319">Vor dem Importieren sollte eine neue erstellen Sie bereits eine vordefinierte BuildingKey identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="bed3f-319">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="bed3f-320">Klicken Sie dazu Problem des "MAX(BuildingKey) aus CqdBuilding wählen Sie" SQL-Befehls zum Identifizieren des aktuellen Werts und das Ergebnis 1 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-320">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="bed3f-321">**Beispiel-SQL-Syntax**</span><span class="sxs-lookup"><span data-stu-id="bed3f-321">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="bed3f-322">Die BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId-Parameter sind erforderlich, die anderen Parameter sind optional.</span><span class="sxs-lookup"><span data-stu-id="bed3f-322">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="bed3f-323">Importieren von Subnetzen</span><span class="sxs-lookup"><span data-stu-id="bed3f-323">Import Subnets</span></span>

<span data-ttu-id="bed3f-324">Importieren von Gebäude können Sie bestimmte Insights (schlechter Anrufe pro erstellen WiFi/kabelgebundene usw.). erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="bed3f-324">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bed3f-325">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-325">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="bed3f-326">Importieren Sie Subnetze und ordnen sie Sie die Gebäude im letzten Schritt importiert.</span><span class="sxs-lookup"><span data-stu-id="bed3f-326">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="bed3f-327">Wenn Sie nicht Netzwerkname auffüllen, stellen Sie sicher, dass für jeden Eintrag in dieser Tabelle ein NetworkNameID 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="bed3f-327">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="bed3f-328">**Beispiel-SQL-Syntax**</span><span class="sxs-lookup"><span data-stu-id="bed3f-328">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="bed3f-329">Das Netzwerk und UpdatedDate-Parameter sind erforderlich, die anderen Parameter sind optional.</span><span class="sxs-lookup"><span data-stu-id="bed3f-329">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="bed3f-330">Optional: BSSID</span><span class="sxs-lookup"><span data-stu-id="bed3f-330">Optional: BSSID</span></span>

<span data-ttu-id="bed3f-331">Auffüllen BSSID Informationen erhalten Sie zusätzliche WiFi Stream Korrelation von Controller oder Radio.</span><span class="sxs-lookup"><span data-stu-id="bed3f-331">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="bed3f-332">Dies ist zusätzlich zum Filtern nach dem Erstellen oder Subnetz.</span><span class="sxs-lookup"><span data-stu-id="bed3f-332">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="bed3f-333">**Beispiel-SQL-Syntax**</span><span class="sxs-lookup"><span data-stu-id="bed3f-333">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="bed3f-334">**CqdBssidTable-Details**</span><span class="sxs-lookup"><span data-stu-id="bed3f-334">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="bed3f-335">**Siehe CQD**</span><span class="sxs-lookup"><span data-stu-id="bed3f-335">**As shown in CQD**</span></span>|<span data-ttu-id="bed3f-336">**CQDBssid-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="bed3f-336">**CQDBssid Table**</span></span>|<span data-ttu-id="bed3f-337">**Beispiel-Eingaben**</span><span class="sxs-lookup"><span data-stu-id="bed3f-337">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bed3f-338">AP NName</span><span class="sxs-lookup"><span data-stu-id="bed3f-338">Ap NName</span></span>  <br/> |<span data-ttu-id="bed3f-339">AP</span><span class="sxs-lookup"><span data-stu-id="bed3f-339">AP</span></span>  <br/> |<span data-ttu-id="bed3f-340">AP1</span><span class="sxs-lookup"><span data-stu-id="bed3f-340">AP1</span></span>  <br/> |
|<span data-ttu-id="bed3f-341">BBssid</span><span class="sxs-lookup"><span data-stu-id="bed3f-341">BBssid</span></span>  <br/> |<span data-ttu-id="bed3f-342">BSS</span><span class="sxs-lookup"><span data-stu-id="bed3f-342">BSS</span></span>  <br/> |<span data-ttu-id="bed3f-343">00-00-00-00-00-00 (Sie müssen den mit Trennzeichen versehenen Fformat verwenden)</span><span class="sxs-lookup"><span data-stu-id="bed3f-343">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="bed3f-344">Controller</span><span class="sxs-lookup"><span data-stu-id="bed3f-344">Controller</span></span>  <br/> |<span data-ttu-id="bed3f-345">Gebäude</span><span class="sxs-lookup"><span data-stu-id="bed3f-345">Building</span></span>  <br/> |<span data-ttu-id="bed3f-346">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="bed3f-346">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="bed3f-347">Gerät</span><span class="sxs-lookup"><span data-stu-id="bed3f-347">Device</span></span>  <br/> |<span data-ttu-id="bed3f-348">ess</span><span class="sxs-lookup"><span data-stu-id="bed3f-348">ess</span></span>  <br/> |<span data-ttu-id="bed3f-349">Controller1</span><span class="sxs-lookup"><span data-stu-id="bed3f-349">Controller1</span></span>  <br/> |
|<span data-ttu-id="bed3f-350">Radio</span><span class="sxs-lookup"><span data-stu-id="bed3f-350">Radio</span></span>  <br/> |<span data-ttu-id="bed3f-351">phy</span><span class="sxs-lookup"><span data-stu-id="bed3f-351">phy</span></span>  <br/> |<span data-ttu-id="bed3f-352">BGN</span><span class="sxs-lookup"><span data-stu-id="bed3f-352">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="bed3f-353">Verarbeitung der importierten Daten</span><span class="sxs-lookup"><span data-stu-id="bed3f-353">Processing the imported data</span></span>

<span data-ttu-id="bed3f-354">Standardmäßig nach dem Erstellen von-Netzwerk Daten importieren gilt es nur für Datensätze, die nach diesem Zeitpunkt Punkt generiert.</span><span class="sxs-lookup"><span data-stu-id="bed3f-354">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="bed3f-355">Um die vorherigen Datensätze mit diesen neuen Daten zu markieren, müssen Sie die gespeicherte CqdUpdateBuilding eine Ereignisprozedur ausgeführt werden wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bed3f-355">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="bed3f-356">Geben sie das Datum des ersten Datensatzes (identifizieren, die mit dem Befehl Select MIN(StartTime) aus CqdPartitionedStreamView SQL), ein Enddatum des morgen, und klicken Sie dann auf NULL für die letzten beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="bed3f-356">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="bed3f-357">Sobald die Daten Streamdaten zugeordnet ist, muss der Cube SSIS alle Datensätze erneut zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bed3f-357">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="bed3f-358">Dies gilt auch beim Bulk BSSID/Internetdienstanbieter Daten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bed3f-358">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="bed3f-359">Stellen Sie sicher, dass "Prozess Full" ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bed3f-359">Ensure that "Process Full" is selected.</span></span>
  

