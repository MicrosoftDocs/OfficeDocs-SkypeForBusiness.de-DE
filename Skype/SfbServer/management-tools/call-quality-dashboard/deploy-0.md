---
title: Bereitstellen des Anruf Qualitäts Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Zusammenfassung: Hier erfahren Sie mehr über den Bereitstellungsprozess für das Anruf Qualitäts Dashboard. Das Anruf Qualitäts Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 5879c4a99eec8471763e0fccc3a4886be660dbb6
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42840159"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="34762-104">Bereitstellen des Anruf Qualitäts Dashboards für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="34762-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="34762-105">**Zusammenfassung:** Erfahren Sie mehr über den Bereitstellungsprozess für das Anruf Qualitäts Dashboard.</span><span class="sxs-lookup"><span data-stu-id="34762-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="34762-106">Das Anruf Qualitäts Dashboard ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="34762-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="34762-107">Übersicht über die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="34762-107">Deployment Overview</span></span>

<span data-ttu-id="34762-108">Das Anruf Qualitäts Dashboard (CQD) besteht aus drei Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="34762-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="34762-109">**Archivdatenbank**, in der die QoE-Daten (Quality of Experience) repliziert und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="34762-110">**Cube**, in dem Daten aus QoE-Archivdatenbanken für einen optimierten und schnellen Zugriff aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="34762-111">**Portal**, in dem Benutzer QoE-Daten problemlos Abfragen und visualisieren können.</span><span class="sxs-lookup"><span data-stu-id="34762-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="34762-113">Der Setupvorgang für QoE-Archiven umfasst das Erstellen der QoE-Archivdatenbank, die Bereitstellung einer SQL Server gespeicherten Prozedur, die die Daten aus der Datenbank für QoE-Metriken in die QoE-Archivdatenbank verschiebt, und das Einrichten des SQL Server-Agent-Auftrags zum Ausführen der gespeicherten Prozedur in einem regulären Intervall.</span><span class="sxs-lookup"><span data-stu-id="34762-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="34762-114">Die Cube-Bereitstellung ruft Informationen vom Benutzer auf der Position des QoE-Archivs ab, stellt den Cube bereit und richtet einen regulären SQL Server-Agent-Auftrag ein, mit dem der Cube in einem regulären Intervall aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="34762-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="34762-115">Die Portal Installation erstellt eine Repository-Datenbank, in der die Zuordnung von CQD-Benutzern zu den Berichten/Abfragen jedes Benutzers gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="34762-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="34762-116">Anschließend wird eine IIS-Webanwendung eingerichtet, die das Dashboard ist, in dem Benutzer eine vordefinierte Gruppe von Berichten anzeigen sowie ihre eigenen Abfragen anpassen und erstellen können, um Daten aus dem Cube zu visualisieren.</span><span class="sxs-lookup"><span data-stu-id="34762-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="34762-117">Die Portal Installation erstellt zwei zusätzliche Webanwendungen, die APIs für Benutzer zur programmgesteuerten Zugriff auf das Repository und den Cube verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="34762-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="34762-118">(Diese APIs werden auch intern vom Dashboard verwendet.)</span><span class="sxs-lookup"><span data-stu-id="34762-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="34762-119">**Phase**</span><span class="sxs-lookup"><span data-stu-id="34762-119">**Phase**</span></span>|<span data-ttu-id="34762-120">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="34762-120">**Steps**</span></span>|<span data-ttu-id="34762-121">**Rollen und Gruppenmitgliedschaft**</span><span class="sxs-lookup"><span data-stu-id="34762-121">**Roles and group membership**</span></span>|<span data-ttu-id="34762-122">**Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="34762-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34762-123">Installieren Sie die erforderliche Hardware und Software.</span><span class="sxs-lookup"><span data-stu-id="34762-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="34762-124">Entscheiden Sie sich für die CQD-Konfiguration, und wählen Sie einen SQL Server aus, aus dem die Installation ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34762-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="34762-125">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="34762-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="34762-126">Abschnitt "Anforderungen vor der Installation" in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="34762-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="34762-127">Installieren Sie CQD.</span><span class="sxs-lookup"><span data-stu-id="34762-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="34762-128">Führen Sie die MSI-Datei nach dem Bereitstellungs Dokument aus.</span><span class="sxs-lookup"><span data-stu-id="34762-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="34762-129">Um das Setup durchführen zu können, muss das Installationskonto ein Domänenbenutzer sein, der Mitglied der lokalen Gruppe Administratoren ist und über Lesezugriff auf die Datenbank für QoE-Metriken auf der Monitoring Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="34762-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="34762-130">Abschnitte "Konten und Bereitstellungsschritte" in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="34762-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="34762-131">Erteilen Sie dem Benutzer Zugriff.</span><span class="sxs-lookup"><span data-stu-id="34762-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="34762-132">Für die Verwaltung der Benutzerautorisierung im Portal wird die Verwendung der URL-Autorisierung empfohlen, die in IIS 7,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="34762-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="34762-133">Weitere Informationen finden Sie unter [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="34762-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="34762-134">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="34762-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="34762-135">Verwalten des Benutzerzugriffs für den Portal Abschnitt in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="34762-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="34762-136">Optional: Geben Sie Informationen zur Subnetz-Zuordnung an.</span><span class="sxs-lookup"><span data-stu-id="34762-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="34762-137">Füllen Sie Netzwerk-und Gebäude Zuordnungstabellen in der QoE-Archivdatenbank auf.</span><span class="sxs-lookup"><span data-stu-id="34762-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="34762-138">Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.</span><span class="sxs-lookup"><span data-stu-id="34762-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="34762-139">Abschnitt "Bereitstellen von Subnetz-Informationen" in der Benutzerdokumentation.</span><span class="sxs-lookup"><span data-stu-id="34762-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="34762-140">Die Bereitstellung des Anruf Qualitäts Dashboards umfasst das Einrichten der Infrastruktur und die Installation der Software.</span><span class="sxs-lookup"><span data-stu-id="34762-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="34762-141">Im folgenden Verfahren wird der Prozess beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34762-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="34762-142">Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="34762-142">Deployment Steps</span></span>

1. <span data-ttu-id="34762-143">Kopieren Sie die Datei CallQualityDashboard. msi auf den Computer, auf dem die Archivdaten Bank Komponente von CQD installiert werden soll (Dies ist der Computer, auf dem SQL Server installiert ist).</span><span class="sxs-lookup"><span data-stu-id="34762-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="34762-144">Führen Sie die MSI-Verwaltungskonsole aus (Windows wird aufgefordert, die Ausführung mit Administratorrechten auszuführen).</span><span class="sxs-lookup"><span data-stu-id="34762-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="34762-145">Akzeptieren Sie den EULA.</span><span class="sxs-lookup"><span data-stu-id="34762-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="34762-146">Wählen Sie den Zielordner aus, in dem Dateien im Zusammenhang mit den Dashboard-Komponenten für die Anrufqualität gefunden werden, oder übernehmen Sie den Standardspeicherort.</span><span class="sxs-lookup"><span data-stu-id="34762-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="34762-147">Wählen Sie alle Features aus.</span><span class="sxs-lookup"><span data-stu-id="34762-147">Select all features.</span></span>
    
6. <span data-ttu-id="34762-148">Geben Sie auf der Seite QoE-Archivkonfiguration die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="34762-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="34762-149">**QoE-Metriken SQL Server:** SQL Server Instanzname, in dem sich die QoE-Metriken DB befindet (Dies ist die Datenquelle).</span><span class="sxs-lookup"><span data-stu-id="34762-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="34762-150">**QoE-Archiv SQL Server Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers fixiert ist.</span><span class="sxs-lookup"><span data-stu-id="34762-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="34762-151">Die Archivdatenbank kann nur auf dem lokalen Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="34762-152">**QoE-Archiv SQL Server Instanz:** Ein Name der lokalen SQL Server Instanz, in der die Archivdatenbank erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34762-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="34762-153">Wenn Sie eine Standard SQL Server Instanz verwenden möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="34762-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="34762-154">Um eine benannte SQL Server Instanz zu verwenden, geben Sie den Namen der Instanz an (beispielsweise den\"Namen nach dem ").</span><span class="sxs-lookup"><span data-stu-id="34762-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="34762-155">**QoE-Archivdatenbank:** Diese Option ist standardmäßig auf "neue Datenbank erstellen" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="34762-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="34762-156">Da das Archiv-DB-Upgrade nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Archivdatenbank das gleiche Schema wie das zu installierende Build aufweist.</span><span class="sxs-lookup"><span data-stu-id="34762-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="34762-157">**Datenbankdatei Verzeichnis:** Pfad zu dem Speicherort, an dem die Datenbankdateien (MDF und LDF) für die Archivdatenbank gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="34762-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="34762-158">Dies sollte sich auf einem Laufwerk (in der empfohlenen Hardwarekonfiguration) befinden, das sich vom Betriebssystem getrennt HDD2.</span><span class="sxs-lookup"><span data-stu-id="34762-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="34762-159">Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, um mögliche Konflikte zu vermeiden, empfohlen wird, ein leeres Verzeichnis ohne Dateien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="34762-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="34762-160">**Verwenden Sie mehrere Partitionen:** Der Standardwert ist auf "Multiple Partition" festgelegt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert.</span><span class="sxs-lookup"><span data-stu-id="34762-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="34762-161">Wählen Sie für Standard Edition die Option "einzelne Partition" aus.</span><span class="sxs-lookup"><span data-stu-id="34762-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="34762-162">Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn eine einzelne Partition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34762-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="34762-163">Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="34762-164">Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "Change" in der Systemsteuerung erneut installiert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="34762-165">**Partitionsdatei Verzeichnis:** Pfad zu dem Speicherort, an dem die Partitionen für die QoE-Archivdatenbank gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="34762-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="34762-166">Dies sollte sich auf einem Laufwerk (in der empfohlenen Hardwarekonfiguration) befinden, das sich von dem Laufwerk "OS Drive" (HDD3) und dem SQL-Datenbankprotokolldateien unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="34762-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="34762-167">Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, um mögliche Konflikte zu vermeiden, empfohlen wird, ein leeres Verzeichnis ohne Dateien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="34762-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="34762-168">**SQL-Agent-Auftrags Benutzer – &amp; Benutzernamen Kennwort:** Domänendienstkonto Name und Kennwort (maskiert), die verwendet werden, um den Schritt "QoE-Archivdaten" des SQL Server-Agent-Auftrags auszuführen (mit dem die gespeicherte Prozedur ausgeführt wird, um Daten aus QoE-Metriken DB in die Archivdatenbank zu übertragen, sodass dieses Konto über Lesezugriff auf QoE-Metriken verfügt, wie unter Konten Abschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="34762-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="34762-169">Dieses Konto muss außerdem über eine Anmeldung im QoE-Archiv SQL Server Instanz) verfügen.</span><span class="sxs-lookup"><span data-stu-id="34762-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="34762-170">Das Konto, unter dem die SQL Server Instanz ausgeführt wird, beispielsweise NT SERVICE\MSSQLSERVER, muss Zugriff/Berechtigung für die oben angegebenen Verzeichnisse haben, damit die Installation erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="34762-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="34762-171">Ausführliche Informationen finden Sie unter [configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34762-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="34762-172">Wenn Sie auf Weiter klicken, führt das Installationsprogramm vorab erforderliche Prüfungen durch und meldet, wenn Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="34762-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="34762-173">Wenn alle Voraussetzungen überprüft werden, wird das Installationsprogramm zur Seite mit der Cube-Konfiguration weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="34762-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="34762-174">Wenn das Installationsprogramm eine Warnmeldung anzeigt, dass der SQL Server Agent-Dienst für die QoE-Archiv SQL Server Instanz derzeit nicht ausgeführt wird, kann die Installation fortgesetzt werden, aber nach der Installation stellen Sie sicher, dass der SQL Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf Automatisch, sodass der geplante Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34762-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="34762-175">Geben Sie auf der Seite Cube-Konfiguration die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="34762-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="34762-176">**QoE-Archiv SQL Server Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers fixiert ist.</span><span class="sxs-lookup"><span data-stu-id="34762-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="34762-177">Cube kann nur auf dem Computer installiert werden, auf dem die QoE-Archivdatenbank vorhanden ist (Hinweis.</span><span class="sxs-lookup"><span data-stu-id="34762-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="34762-178">Cube selbst kann auf einem Remotecomputer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="34762-179">Siehe unten)</span><span class="sxs-lookup"><span data-stu-id="34762-179">See below)</span></span>
    
   - <span data-ttu-id="34762-180">**QoE-Archiv SQL Server Instanz:** SQL Server Name der Instanz, in der sich die QoE-Archiv-DB befindet.</span><span class="sxs-lookup"><span data-stu-id="34762-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="34762-181">Lassen Sie dieses Feld leer, um eine Standard SQL Server Instanz anzugeben.</span><span class="sxs-lookup"><span data-stu-id="34762-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="34762-182">Geben Sie zum Angeben einer benannten SQL Server Instanz den Namen der Instanz ein (beispielsweise den Namen nach\"dem ").</span><span class="sxs-lookup"><span data-stu-id="34762-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="34762-183">Wenn die QoE-Archiv Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="34762-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="34762-184">**Cube Analysis Server:** SQL Server Name der Analysis Services-Instanz, unter der der Cube erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34762-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="34762-185">Hierbei kann es sich um einen anderen Computer handeln, aber der Installationsbenutzer muss Mitglied der Server Administratoren der Ziel-SQL Server Analysis Service-Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="34762-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="34762-186">Weitere Informationen zum Konfigurieren von Analysis Services Server-Administratorberechtigungen finden Sie unter [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="34762-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="34762-187">**Verwenden Sie mehrere Partitionen:** Der Standardwert ist auf "Multiple Partition" festgelegt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert.</span><span class="sxs-lookup"><span data-stu-id="34762-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="34762-188">Wählen Sie für Standard Edition die Option "einzelne Partition" aus.</span><span class="sxs-lookup"><span data-stu-id="34762-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="34762-189">Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn eine einzelne Partition verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34762-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="34762-190">Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="34762-191">Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "Change" in der Systemsteuerung erneut installiert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="34762-192">**Cube-Benutzer – Benutzer &amp; Namen Kennwort:** Domänendienstkonto Name und Kennwort (maskiert), mit denen die Verarbeitung des Cubes ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="34762-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="34762-193">Wenn die QoE-Archiv Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite Archivierungskonfiguration für den SQL-Agent-Auftrags Benutzer bereitgestellten Wert vorab aufgefüllt, es wird jedoch empfohlen, ein anderes Domänendienstkonto anzugeben, damit das Setup die die am wenigsten erforderliche Berechtigung dafür.</span><span class="sxs-lookup"><span data-stu-id="34762-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="34762-194">Wenn Sie auf Weiter klicken, wird eine weitere Validierungs Runde ausgeführt, und jedes Problem wird gemeldet.</span><span class="sxs-lookup"><span data-stu-id="34762-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="34762-195">Nach erfolgreichem Abschluss der Überprüfung wird das Installationsprogramm zur Seite Portal Konfiguration wechseln.</span><span class="sxs-lookup"><span data-stu-id="34762-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="34762-196">Geben Sie auf der Seite Portal Konfiguration die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="34762-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="34762-197">**QoE-Archiv SQL Server:** SQL Server Name der Instanz, in der sich die QoE-Archivdatenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="34762-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="34762-198">Beachten Sie, dass der Computername im Gegensatz zur Konfigurationsseite von QoE-Archiven und der Seite Cube-Konfiguration nicht festgelegt und angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="34762-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="34762-199">Wenn die QoE-Archiv Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="34762-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="34762-200">**Cube Analysis Server:** SQL Server Name der Analysis Services-Instanz, für den der Cube gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="34762-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="34762-201">Wenn die Cube-Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite Cube-Konfiguration bereitgestellten Wert vorab aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="34762-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="34762-202">**Repository-SQL Server:** SQL Server Instanzname, in dem die Repository-Datenbank erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34762-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="34762-203">Wenn der Name der SQL Server Instanz, in der sich die QoE-Archivdatenbank befindet, zuvor in der Einrichtung (in anderen Komponenten) bereitgestellt wurde, wird dieses Feld vorab mit dem Namen der QoE-Archiv-DB-SQL Server Instanz aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="34762-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="34762-204">Hierbei kann es sich um eine beliebige SQL Server Instanz handeln.</span><span class="sxs-lookup"><span data-stu-id="34762-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="34762-205">**Repository-Datenbank:** Standardmäßig ist die Option auf "neue Datenbank erstellen" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="34762-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="34762-206">Da das Repository-DB-Upgrade nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Repository-DB das gleiche Schema wie das zu installierende Build aufweist.</span><span class="sxs-lookup"><span data-stu-id="34762-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="34762-207">**Benutzer Name &amp; Kennwort des IIS-App-Pools:** Das Konto, unter dem der IIS-Anwendungspool ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="34762-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="34762-208">Die Felder Benutzer Name und Kennwort werden abgeblendet, wenn integrierte Systemkonten ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="34762-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="34762-209">Diese Felder werden nur aktiviert, wenn im Dropdownfeld andere ausgewählt ist, damit der Benutzer die Informationen zum Domänendienstkonto eingeben kann.</span><span class="sxs-lookup"><span data-stu-id="34762-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="34762-210">Wenn Sie auf Weiter klicken, wird die abschließende Runde der Überprüfung durchgeführt, um sicherzustellen, dass auf die SQL Server Instanzen mithilfe der bereitgestellten Anmeldeinformationen zugegriffen werden kann und dass IIS auf dem Computer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="34762-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="34762-211">Nach erfolgreichem Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortfahren.</span><span class="sxs-lookup"><span data-stu-id="34762-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="34762-212">Wenn das Installationsprogramm fertig ist, wird wahrscheinlich der SQL Server-Agent-Auftrag ausgeführt, wobei die anfängliche Auslastung der QoE-Daten und die Verarbeitung des Cubes erfolgt.</span><span class="sxs-lookup"><span data-stu-id="34762-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="34762-213">Je nach Datenmenge in QoE stehen dem Portal keine Daten zur Verfügung, die noch angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="34762-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="34762-214">Wechseln Sie zum Überprüfen des Status der Daten-und Cube-Verarbeitung zu `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="34762-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="34762-215">Beachten Sie, dass bei der URL zum Überprüfen des Status der Download Cube-Verarbeitung die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="34762-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="34762-216">Wenn Sie "Integrität" eingeben, kann die URL nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34762-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="34762-217">Sie müssen "Integrität" am Ende der URL mit einem Haupt-H eingeben.</span><span class="sxs-lookup"><span data-stu-id="34762-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="34762-218">Wenn der Debugmodus aktiviert ist, werden ausführliche Protokollmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34762-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="34762-219">Wechseln Sie zum Aktivieren des Debugmodus zu **%SystemDrive%\Programme\Gemeinsame Files\Skype for Business 2015 CQD\QoEDataService\web.config**, und aktualisieren Sie die folgende Folge, sodass der Wert auf **true**festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="34762-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="34762-220">Die Hauptportal Seite ist über `http://<machinename>/CQD`verfügbar.</span><span class="sxs-lookup"><span data-stu-id="34762-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="34762-221">Verwalten des Benutzerzugriffs für das Portal</span><span class="sxs-lookup"><span data-stu-id="34762-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="34762-222">Für die Verwaltung der Benutzerautorisierung im Portal wird die Verwendung der URL-Autorisierung empfohlen, die in IIS 7,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="34762-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="34762-223">Weitere Informationen zur IIS-Sicherheit finden Sie unter [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="34762-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="34762-224">Jede Website oder Webanwendung erbt die standardmäßige URL-Autorisierung, die für den gesamten IIS konfiguriert ist, in der Regel "alle Benutzer zulassen".</span><span class="sxs-lookup"><span data-stu-id="34762-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="34762-225">Wenn der Zugriff auf das Portal restriktiver sein muss, können Administratoren nur Zugriff auf die bestimmte Benutzergruppe gewähren, indem Sie die "Autorisierungsregeln" bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="34762-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Bereitstellen der Anrufqualität – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="34762-227">Das Symbol für Autorisierungsregeln ist nicht mit der ".NET-Autorisierung" im Abschnitt ASP.net zu verwechseln, bei dem es sich um einen anderen Autorisierungsmechanismus handelt.</span><span class="sxs-lookup"><span data-stu-id="34762-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="34762-228">Administratoren sollten zunächst die geerbte Regel "alle Benutzer zulassen" entfernen.</span><span class="sxs-lookup"><span data-stu-id="34762-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="34762-229">Dadurch wird verhindert, dass nicht autorisierte Benutzer auf das Portal zugreifen.</span><span class="sxs-lookup"><span data-stu-id="34762-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Bereitstellen von CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="34762-231">Als nächstes sollten Administratoren neue Zulassungsregeln hinzufügen und bestimmten Benutzern die Berechtigung für den Zugriff auf das Portal erteilen.</span><span class="sxs-lookup"><span data-stu-id="34762-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="34762-232">Es wird empfohlen, eine lokale Gruppe mit dem Namen "CQDPortalUsers" zum Verwalten der Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="34762-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Bereitstellen des Anruf Qualitäts Dashboards](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="34762-234">Die Konfigurationsdetails werden in der Datei "Internet. config" gespeichert, die sich im physikalischen Verzeichnis des Portals befindet.</span><span class="sxs-lookup"><span data-stu-id="34762-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="34762-235">Der nächste Schritt besteht darin, das Dashboard des CQD zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="34762-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="34762-236">Nachdem Benutzer von IIS authentifiziert wurden, müssen Sie über Dateiberechtigungen für das CQD-Verzeichnis verfügen, um auf den Inhalt des Webportals zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="34762-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="34762-237">Es ist möglich, die ACLs über die Registerkarte Sicherheit der CQD-Verzeichniseigenschaften zu ändern, um einzelne Benutzer oder Gruppen hinzuzufügen. die empfohlene Vorgehensweise besteht jedoch darin, die Dateiberechtigungen unberührt zu lassen.</span><span class="sxs-lookup"><span data-stu-id="34762-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="34762-238">Ändern Sie stattdessen die IIS-Einstellung so, dass der IIS-Arbeitsprozess für den Zugriff auf das CQD-Verzeichnis verwendet wird, unabhängig davon, welcher Benutzer authentifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="34762-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="34762-239">Es ist wichtig, diese Einstellung nur für die CQD-Anwendung und nicht für die beiden API-Anwendungen zu ändern: im und QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="34762-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="34762-240">Konfigurieren des Dateizugriffs für das CQD (Dashboard)</span><span class="sxs-lookup"><span data-stu-id="34762-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="34762-241">Öffnen Sie den Konfigurations-Editor für CQD.</span><span class="sxs-lookup"><span data-stu-id="34762-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="34762-243">Wählen Sie unter Abschnitt **System. Webserver/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="34762-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="34762-245">Ändern Sie authenticatedUserOverride in **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="34762-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Bereitstellen des Anruf Qualitäts Dashboards – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="34762-247">Klicken Sie auf der rechten Seite auf **Apply** .</span><span class="sxs-lookup"><span data-stu-id="34762-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="34762-248">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="34762-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="34762-249">Das CQD zeigt nach der Bereitstellung keine Daten</span><span class="sxs-lookup"><span data-stu-id="34762-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="34762-250">Möglicherweise wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="34762-250">You may receive the following error:</span></span>

<span data-ttu-id="34762-251">*Die Abfrage konnte nicht ausgeführt werden, während Sie im Cube ausgeführt wird. Verwenden Sie den Abfrage-Editor, um die Abfrage zu ändern und Probleme zu beheben. Stellen Sie außerdem sicher, dass auf den Cube zugegriffen werden kann.*</span><span class="sxs-lookup"><span data-stu-id="34762-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="34762-252">Dies bedeutet, dass der Cube vor der Verwendung in CQD in SQL Server Analysis Services verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="34762-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="34762-253">Sie können dieses Problem beheben, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="34762-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="34762-254">Öffnen Sie SQL Management Studio, und wählen Sie **Analysis Services**aus.</span><span class="sxs-lookup"><span data-stu-id="34762-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="34762-255">Erweitern Sie das **QoECube** -Objekt, wählen Sie **QoE Metric**aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="34762-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="34762-256">Wenn dieser leere Browser zurückgibt, wurde der Cube noch nicht fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="34762-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="34762-257">Klicken Sie mit der rechten Maustaste auf **QoE Metric** angain, und wählen Sie **Prozess**.</span><span class="sxs-lookup"><span data-stu-id="34762-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="34762-258">Wenn die Verarbeitung abgeschlossen ist, klicken Sie mit der rechten Maustaste erneut auf das Objekt, und wählen Sie **Durchsuchen** aus, um zu bestätigen, dass auf der Browser Seite nun Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="34762-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="34762-259">Benutzer haben Probleme bei der Anmeldung, da das Installationsprogramm nicht die richtigen Einstellungen in IIS erstellt.</span><span class="sxs-lookup"><span data-stu-id="34762-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="34762-260">In seltenen Fällen kann das Installationsprogramm nicht die richtigen Einstellungen in IIS erstellen.</span><span class="sxs-lookup"><span data-stu-id="34762-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="34762-261">Manuelle Änderungen sind erforderlich, damit sich Benutzer bei der CQD anmelden können.</span><span class="sxs-lookup"><span data-stu-id="34762-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="34762-262">Wenn Benutzer Probleme beim Anmelden haben, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="34762-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="34762-263">Öffnen Sie den IIS-Manager, und navigieren Sie zur Standardwebsite.</span><span class="sxs-lookup"><span data-stu-id="34762-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="34762-265">Klicken Sie auf "Authentifizierung".</span><span class="sxs-lookup"><span data-stu-id="34762-265">Click on "Authentication".</span></span> <span data-ttu-id="34762-266">Wenn die "anonyme Authentifizierung", "ASP.NET-Identitätswechsel", "Formularauthentifizierung" und "Windows-Authentifizierung" nicht mit den unten gezeigten Einstellungen übereinstimmen, müssen Sie Sie manuell ändern, damit Sie den unten angegebenen Einstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="34762-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="34762-267">Alle anderen Authentifizierungsmechanismen sollten deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="34762-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="34762-269">Klicken Sie für "Windows-Authentifizierung" auf der rechten Seite auf Erweiterte Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="34762-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="34762-271">Legen Sie "Extended Protection" so fest, dass die Option "Kernel Modus-Authentifizierung aktivieren" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="34762-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="34762-273">Wiederholen Sie die obigen Schritte für jeden der Einträge "CQD", "im" und "QoERepositoryService" unter "Default Web Site".</span><span class="sxs-lookup"><span data-stu-id="34762-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="34762-274">Für http-und HTTPS-Portbindungen erstellt das Installationsprogramm Portbindungen für die Standardportnummern (Port 80 für http und Port 443 für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="34762-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="34762-275">Wenn auf dem Computer eine andere Website vorhanden ist, die diese Bindungen verwendet, tritt ein Konflikt auf, und das IIS-Verhalten kann nicht vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="34762-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="34762-276">Am besten vermeiden Sie dieses Problem, indem Sie sicherstellen, dass keine anderen Websites den Ports 80 und 443 vor der Installation von CQD zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="34762-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="34762-277">So aktivieren Sie SSL/TLS in IIS und erzwingen, dass Benutzer über sicheres HTTPS anstelle von http eine Verbindung herstellen:</span><span class="sxs-lookup"><span data-stu-id="34762-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="34762-278">Konfigurieren von Secure Sockets Layer in IIS finden Sie unter [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="34762-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="34762-279">Ersetzen `http` Sie einmal durch `https`.</span><span class="sxs-lookup"><span data-stu-id="34762-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="34762-280">Anweisungen zum Aktivieren von TLS in den SQL Server-Verbindungen finden Sie unter [Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe der Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="34762-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="34762-281">Cube-Synchronisierung schlägt fehl</span><span class="sxs-lookup"><span data-stu-id="34762-281">Cube Sync Fails</span></span>

<span data-ttu-id="34762-282">QoEMetrics kann einige ungültige Datensätze enthalten, die auf Endbenutzer Uhren basieren.</span><span class="sxs-lookup"><span data-stu-id="34762-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="34762-283">Wenn die Zeitabweichung größer als 60 Jahre ist, tritt beim Cube-Import ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="34762-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="34762-284">Überprüfen Sie die min-und Max-StartTime/EndTime mit den unten aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="34762-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="34762-285">Suchen nach und Löschen von Datensätzen in der fernen und sehr ferneren Zukunft können Sie ignoriert werden, und Sie werden die Synchronisierungsprozesse aufheben.</span><span class="sxs-lookup"><span data-stu-id="34762-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="34762-286">Wählen Sie min (StartTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="34762-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="34762-287">Wählen Sie Max (StartTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="34762-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="34762-288">Wählen Sie min (EndTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="34762-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="34762-289">Wählen Sie Max (EndTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="34762-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="34762-290">Aufgaben nach der Installation</span><span class="sxs-lookup"><span data-stu-id="34762-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="34762-291">Importieren von Gebäuden und Netzwerken</span><span class="sxs-lookup"><span data-stu-id="34762-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="34762-292">Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="34762-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="34762-293">Definieren von Gebäudetypen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="34762-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="34762-294">Definieren von Besitzer Typen für Gebäude (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="34762-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="34762-295">Definieren von Netzwerktypen (dringend empfohlen)</span><span class="sxs-lookup"><span data-stu-id="34762-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="34762-296">Importieren von Gebäuden (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="34762-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="34762-297">Subnetze importieren (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="34762-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="34762-298">Definieren von Gebäudetypen</span><span class="sxs-lookup"><span data-stu-id="34762-298">Define Building Types</span></span>

<span data-ttu-id="34762-299">Gebäudetypen werden verwendet, um die verschiedenen Gebäude Definitionen oder-Typen in Ihrer Organisation zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="34762-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34762-300">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="34762-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="34762-301">Beispiele</span><span class="sxs-lookup"><span data-stu-id="34762-301">Examples</span></span>
  
- <span data-ttu-id="34762-302">Zentrale</span><span class="sxs-lookup"><span data-stu-id="34762-302">Headquarters</span></span>
    
- <span data-ttu-id="34762-303">Remote Office</span><span class="sxs-lookup"><span data-stu-id="34762-303">Remote Office</span></span>
    
- <span data-ttu-id="34762-304">Joint-Venture-Standort</span><span class="sxs-lookup"><span data-stu-id="34762-304">Joint-venture location</span></span>
    
  <span data-ttu-id="34762-305">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="34762-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="34762-306">Die Parameter BuildingTypeId und BuildingTypeDesc sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34762-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="34762-307">Definieren von Besitzer Typen für Gebäude</span><span class="sxs-lookup"><span data-stu-id="34762-307">Define Building Ownership Types</span></span>

<span data-ttu-id="34762-308">Besitzer Typen werden verwendet, um Besitz-und Leasingobjekte zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="34762-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34762-309">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="34762-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="34762-310">Beispiele</span><span class="sxs-lookup"><span data-stu-id="34762-310">Examples</span></span>
  
- <span data-ttu-id="34762-311">Contoso-Leased Non-&amp;Re F</span><span class="sxs-lookup"><span data-stu-id="34762-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="34762-312">Contoso-Leased&amp;Re F</span><span class="sxs-lookup"><span data-stu-id="34762-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="34762-313">Contoso-Besitzer</span><span class="sxs-lookup"><span data-stu-id="34762-313">Contoso Owned</span></span>
    
- <span data-ttu-id="34762-314">Tochterunternehmen geleast</span><span class="sxs-lookup"><span data-stu-id="34762-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="34762-315">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="34762-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="34762-316">Die Parameter OwnershipTypeId und OwnershipTypeDesc sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34762-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="34762-317">Definieren von Netzwerknamen</span><span class="sxs-lookup"><span data-stu-id="34762-317">Define Network Names</span></span>

<span data-ttu-id="34762-318">Netzwerktypen werden verwendet, um verschiedene Typen von Netzwerken innerhalb der Organisation zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="34762-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="34762-319">Auf diese Weise können Sie bestimmte Netzwerktypen filtern oder filtern.</span><span class="sxs-lookup"><span data-stu-id="34762-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34762-320">Es wird dringend empfohlen, Netzwerknamen zu definieren, ist aber optional.</span><span class="sxs-lookup"><span data-stu-id="34762-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="34762-321">Wenn Sie keine Netzwerknamen definieren möchten, stellen Sie sicher, dass für jeden CqdNetwork-Eintrag eine Build-Nr von 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="34762-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="34762-322">Beispiele</span><span class="sxs-lookup"><span data-stu-id="34762-322">Examples</span></span>
  
- <span data-ttu-id="34762-323">VPN</span><span class="sxs-lookup"><span data-stu-id="34762-323">VPN</span></span>
    
- <span data-ttu-id="34762-324">Labor</span><span class="sxs-lookup"><span data-stu-id="34762-324">LAB</span></span>
    
  <span data-ttu-id="34762-325">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="34762-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="34762-326">Die Parameter NetworkNameID und networkName sind erforderlich, der Parameter NetworkType ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="34762-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="34762-327">Importieren von Gebäuden</span><span class="sxs-lookup"><span data-stu-id="34762-327">Import Buildings</span></span>

<span data-ttu-id="34762-328">Durch das Importieren von Gebäuden haben Sie die Möglichkeit, spezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.).</span><span class="sxs-lookup"><span data-stu-id="34762-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34762-329">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="34762-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="34762-330">Bevor Sie ein neues Gebäude importieren, sollten Sie bereits eine vordefinierte BuildingKey identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="34762-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="34762-331">Geben Sie dazu den SQL-Befehl "Max (BuildingKey) aus CqdBuilding" aus, um den aktuellen Wert zu identifizieren und dem Ergebnis 1 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="34762-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="34762-332">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="34762-332">**Sample SQL Syntax**</span></span>
  
```SQL
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

<span data-ttu-id="34762-333">Die Parameter BuildingKey, buildingname, BuildingShortName, OwnershipTypeId, BuildingTypeId sind erforderlich, die anderen Parameter sind optional.</span><span class="sxs-lookup"><span data-stu-id="34762-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="34762-334">Importieren von Subnetzen</span><span class="sxs-lookup"><span data-stu-id="34762-334">Import Subnets</span></span>

<span data-ttu-id="34762-335">Durch das Importieren von Gebäuden haben Sie die Möglichkeit, spezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.).</span><span class="sxs-lookup"><span data-stu-id="34762-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34762-336">Dieser Schritt ist optional, wird jedoch empfohlen.</span><span class="sxs-lookup"><span data-stu-id="34762-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="34762-337">Importieren Sie Subnetze, und ordnen Sie Sie den im letzten Schritt importierten Gebäuden zu.</span><span class="sxs-lookup"><span data-stu-id="34762-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="34762-338">Wenn Sie networkName nicht auffüllen möchten, stellen Sie sicher, dass für jeden Eintrag in dieser Tabelle ein NetworkNameID von 0 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34762-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="34762-339">Weitere Informationen zur SQL-Syntax und zu den Parametern für das Anruf qualitätsdashboard finden Sie unter [use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span><span class="sxs-lookup"><span data-stu-id="34762-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="34762-340">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="34762-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="34762-341">Die Parameter "Network" und "UpdatedDate" sind erforderlich, die anderen Parameter sind optional.</span><span class="sxs-lookup"><span data-stu-id="34762-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="34762-342">Optional: BSSID</span><span class="sxs-lookup"><span data-stu-id="34762-342">Optional: BSSID</span></span>

<span data-ttu-id="34762-343">Durch das Auffüllen von BSSID-Informationen erhalten Sie zusätzliche WLAN-Datenstrom Korrelation durch Controller oder Radio.</span><span class="sxs-lookup"><span data-stu-id="34762-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="34762-344">Dies ist zusätzlich zum Filtern nach Gebäude oder Subnetz.</span><span class="sxs-lookup"><span data-stu-id="34762-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="34762-345">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="34762-345">**Sample SQL Syntax**</span></span>
  
```SQL
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

<span data-ttu-id="34762-346">**CqdBssidTable-Details**</span><span class="sxs-lookup"><span data-stu-id="34762-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="34762-347">**Wie in CQD gezeigt**</span><span class="sxs-lookup"><span data-stu-id="34762-347">**As shown in CQD**</span></span>|<span data-ttu-id="34762-348">**CQDBssid-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="34762-348">**CQDBssid Table**</span></span>|<span data-ttu-id="34762-349">**Beispieleingaben**</span><span class="sxs-lookup"><span data-stu-id="34762-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34762-350">AP-NName</span><span class="sxs-lookup"><span data-stu-id="34762-350">Ap NName</span></span>  <br/> |<span data-ttu-id="34762-351">AP</span><span class="sxs-lookup"><span data-stu-id="34762-351">AP</span></span>  <br/> |<span data-ttu-id="34762-352">AP1</span><span class="sxs-lookup"><span data-stu-id="34762-352">AP1</span></span>  <br/> |
|<span data-ttu-id="34762-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="34762-353">BBssid</span></span>  <br/> |<span data-ttu-id="34762-354">BSS</span><span class="sxs-lookup"><span data-stu-id="34762-354">BSS</span></span>  <br/> |<span data-ttu-id="34762-355">00-00-00-00-00-00 (Sie müssen das getrennte Fformat verwenden)</span><span class="sxs-lookup"><span data-stu-id="34762-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="34762-356">Controller</span><span class="sxs-lookup"><span data-stu-id="34762-356">Controller</span></span>  <br/> |<span data-ttu-id="34762-357">Erstellen</span><span class="sxs-lookup"><span data-stu-id="34762-357">Building</span></span>  <br/> |<span data-ttu-id="34762-358">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="34762-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="34762-359">Gerät</span><span class="sxs-lookup"><span data-stu-id="34762-359">Device</span></span>  <br/> |<span data-ttu-id="34762-360">ESS</span><span class="sxs-lookup"><span data-stu-id="34762-360">ess</span></span>  <br/> |<span data-ttu-id="34762-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="34762-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="34762-362">Radio</span><span class="sxs-lookup"><span data-stu-id="34762-362">Radio</span></span>  <br/> |<span data-ttu-id="34762-363">PHY</span><span class="sxs-lookup"><span data-stu-id="34762-363">phy</span></span>  <br/> |<span data-ttu-id="34762-364">BGN</span><span class="sxs-lookup"><span data-stu-id="34762-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="34762-365">Verarbeiten der importierten Daten</span><span class="sxs-lookup"><span data-stu-id="34762-365">Processing the imported data</span></span>

<span data-ttu-id="34762-366">Standardmäßig wird nach dem Importieren von Gebäude-/Netzwerkdaten nur auf Datensätze angewendet, die nach diesem Zeitpunkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="34762-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="34762-367">Um alle vorherigen Datensätze mit diesen neuen Daten zu markieren, müssen Sie die gespeicherte Prozedur CqdUpdateBuilding wie unten gezeigt ausführen:</span><span class="sxs-lookup"><span data-stu-id="34762-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="34762-368">Geben Sie ihm das Datum Ihres ersten Datensatzes (identifizieren Sie anhand des SQL-Befehls Select min (StartTime) aus CqdPartitionedStreamView), ein EndDate von morgen, dann NULL für die letzten beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="34762-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="34762-369">Nachdem die Daten Datenstromdaten zugeordnet wurden, muss der SSIS-Cube alle Datensätze erneut verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="34762-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="34762-370">Dies gilt auch beim Massen Hinzufügen von BSSID/ISP-Daten.</span><span class="sxs-lookup"><span data-stu-id="34762-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="34762-371">Stellen Sie sicher, dass "vollständig verarbeiten" ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="34762-371">Ensure that "Process Full" is selected.</span></span>
  

