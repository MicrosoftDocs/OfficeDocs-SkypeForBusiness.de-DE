---
title: Bereitstellen eines Anruf Qualitäts Dashboards für Skype for Business Server
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
description: 'Zusammenfassung: erfahren Sie mehr über den Bereitstellungsprozess für das Dashboard für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: ccfb19bf8069bf72d52d7399b012d81af72e4110
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816854"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="9cebf-104">Bereitstellen eines Anruf Qualitäts Dashboards für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9cebf-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="9cebf-105">**Zusammenfassung:** Informieren Sie sich über den Bereitstellungsprozess für das Dashboard für die Anrufqualität.</span><span class="sxs-lookup"><span data-stu-id="9cebf-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="9cebf-106">Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9cebf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="9cebf-107">Übersicht über die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9cebf-107">Deployment Overview</span></span>

<span data-ttu-id="9cebf-108">Das Dashboard für die Anrufqualität (CQD) besteht aus drei Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="9cebf-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="9cebf-109">**Archivdatenbank**, in der die QoE-Daten (Quality of Experience) repliziert und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="9cebf-110">**Cube**, in dem Daten aus der QoE-Archivdatenbank für optimierten und schnellen Zugriff aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="9cebf-111">**Portal**, in dem Benutzer problemlos QoE-Daten Abfragen und visualisieren können.</span><span class="sxs-lookup"><span data-stu-id="9cebf-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="9cebf-113">Der Setupvorgang für das QoE-Archiv umfasst das Erstellen der QoE-Archivdatenbank, das Bereitstelleneiner gespeicherten SQL Server-Prozedur, die die Daten aus der QoE-Quelldatenbank in die QoE-Archivdatenbank verschiebt, und das Einrichten des SQL Server-Agent-Auftrags zum Ausführen der gespeicherten Prozedur in regelmäßigen Abständen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="9cebf-114">Die Cube-Bereitstellung ruft Informationen des Benutzers ab, in dem sich das QoE-Archiv befindet, stellt den Cube bereit und richtet einen regulären SQL Server-Agentauftrag ein, der den Cube in regelmäßigen Abständen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9cebf-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="9cebf-115">Die Portal Installation erstellt eine Repository-Datenbank, in der die Zuordnung der CQD-Benutzer zu den Berichten/Abfragen jedes Benutzers gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="9cebf-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="9cebf-116">Anschließend wird eine IIS-Webanwendung eingerichtet, die das Dashboard ist, in dem Benutzer einen vordefinierten Satz von Berichten anzeigen sowie eigene Abfragen anpassen und erstellen können, um Daten aus dem Cube zu visualisieren.</span><span class="sxs-lookup"><span data-stu-id="9cebf-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="9cebf-117">Die Portal-Installation erstellt zwei zusätzliche Webanwendungen, die APIs für Benutzer verfügbar macht, um programmgesteuert auf das Repository und den Cube zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="9cebf-118">(Diese APIs werden auch intern vom Dashboard verwendet.)</span><span class="sxs-lookup"><span data-stu-id="9cebf-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="9cebf-119">**Phase**</span><span class="sxs-lookup"><span data-stu-id="9cebf-119">**Phase**</span></span>|<span data-ttu-id="9cebf-120">**Schritte**</span><span class="sxs-lookup"><span data-stu-id="9cebf-120">**Steps**</span></span>|<span data-ttu-id="9cebf-121">**Rollen und Gruppenmitgliedschaften**</span><span class="sxs-lookup"><span data-stu-id="9cebf-121">**Roles and group membership**</span></span>|<span data-ttu-id="9cebf-122">**Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="9cebf-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9cebf-123">Installieren Sie die erforderliche Hardware und Software.</span><span class="sxs-lookup"><span data-stu-id="9cebf-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="9cebf-124">Entscheiden Sie sich für die CQD-Konfiguration, und wählen Sie einen SQL Server aus, aus dem die Installation durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9cebf-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="9cebf-125">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="9cebf-126">Abschnitt "Voraussetzungen für die Installation" in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9cebf-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="9cebf-127">Installieren Sie CQD.</span><span class="sxs-lookup"><span data-stu-id="9cebf-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="9cebf-128">Führen Sie die MSI-Datei nach dem Bereitstellungs Dokument aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="9cebf-129">Zum Durchführen der Einrichtung muss das Installationskonto ein Domänenbenutzer sein, der Mitglied der lokalen Gruppe Administratoren ist und über Lesezugriff auf die QoE Metrics-Datenbank auf dem Überwachungs Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="9cebf-130">Abschnitte "Konten und Bereitstellungsschritte" in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9cebf-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="9cebf-131">Gewähren des Benutzerzugriffs</span><span class="sxs-lookup"><span data-stu-id="9cebf-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="9cebf-132">Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9cebf-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="9cebf-133">Weitere Informationen finden Sie unter [Grundlegendes zur IIS 7,0-URL-Autorisierung](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="9cebf-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="9cebf-134">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="9cebf-135">Verwalten des Benutzerzugriffs für den Portal Abschnitt in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="9cebf-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="9cebf-136">Optional: Geben Sie Informationen zur Subnet-Zuordnung an.</span><span class="sxs-lookup"><span data-stu-id="9cebf-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="9cebf-137">Füllen Sie Netzwerk-und Gebäude Zuordnungstabellen in der QoE-Archivdatenbank auf.</span><span class="sxs-lookup"><span data-stu-id="9cebf-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="9cebf-138">Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.</span><span class="sxs-lookup"><span data-stu-id="9cebf-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="9cebf-139">Abschnitt "Bereitstellen von Subnetz-Informationen" in der Benutzerdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9cebf-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="9cebf-140">Die Bereitstellung des Dashboards für die Anrufqualität umfasst das Einrichten der Infrastruktur und die Installation der Software.</span><span class="sxs-lookup"><span data-stu-id="9cebf-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="9cebf-141">Das folgende Verfahren beschreibt den Prozess.</span><span class="sxs-lookup"><span data-stu-id="9cebf-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="9cebf-142">Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="9cebf-142">Deployment Steps</span></span>

1. <span data-ttu-id="9cebf-143">Kopieren Sie die Datei "CallQualityDashboard. msi" auf den Computer, auf dem die Archivierungsdaten Bank Komponente von CQD installiert werden soll (Dies ist der Computer, auf dem SQL Server installiert ist).</span><span class="sxs-lookup"><span data-stu-id="9cebf-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="9cebf-144">Führen Sie die MSI-Abfrage aus (Windows wird zur Ausführung mit Administratorrechten aufgefordert).</span><span class="sxs-lookup"><span data-stu-id="9cebf-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="9cebf-145">Akzeptieren Sie den Endbenutzer-Lizenzvertrag.</span><span class="sxs-lookup"><span data-stu-id="9cebf-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="9cebf-146">Wählen Sie den Zielordner aus, in dem sich die Dateien für die Dashboard-Komponenten der Anrufqualität befinden, oder übernehmen Sie den Standardspeicherort.</span><span class="sxs-lookup"><span data-stu-id="9cebf-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="9cebf-147">Wählen Sie alle Features aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-147">Select all features.</span></span>
    
6. <span data-ttu-id="9cebf-148">Geben Sie auf der Seite QoE-Archivkonfiguration die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="9cebf-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="9cebf-149">**QoE-Metriken SQL Server:** Name der SQL Server-Instanz für die Position, an der sich die QoE-Metrik DB befindet (Dies ist die Datenquelle).</span><span class="sxs-lookup"><span data-stu-id="9cebf-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="9cebf-150">**QoE-Archiv-SQL Server-Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="9cebf-151">Archiv DB kann nur auf dem lokalen Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="9cebf-152">**QoE-Archiv-SQL Server-Instanz:** Ein lokaler SQL Server-Instanzname für die Stelle, an der die Archivdatenbank erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9cebf-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="9cebf-153">Wenn Sie eine Standard-SQL Server-Instanz verwenden möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="9cebf-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="9cebf-154">Wenn Sie eine benannte SQL Server-Instanz verwenden möchten, geben Sie den Namen der Instanz an (Beispiels\"Weise den Namen nach ").</span><span class="sxs-lookup"><span data-stu-id="9cebf-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="9cebf-155">**QoE-Archivdatenbank:** Diese Option ist standardmäßig auf "neue Datenbank erstellen" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="9cebf-156">Da die Archiv-DB-Aktualisierung nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Archivdatenbank dasselbe Schema wie der zu installierende Build aufweist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="9cebf-157">**Datenbank-Dateiverzeichnis:** Der Pfad, in dem die Datenbankdateien (MDF und LDF) für die Archivdatenbank gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="9cebf-158">Dies sollte sich auf einem Laufwerk (HDD2 in der empfohlenen Hardwarekonfiguration) befinden, das vom Betriebssystem getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="9cebf-159">Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, ein leeres Verzeichnis ohne Dateien verwendet werden sollte, um potenzielle Konflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="9cebf-160">**Verwenden mehrerer Partitionen:** Der Standardwert ist auf "mehrere Partitionen" eingestellt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert.</span><span class="sxs-lookup"><span data-stu-id="9cebf-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="9cebf-161">Wählen Sie für Standard Edition die Option "einzelne Partition" aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="9cebf-162">Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn einzelne Partitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9cebf-163">Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="9cebf-164">Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "ändern" in der Systemsteuerung erneut installiert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="9cebf-165">**Partitionsdatei Verzeichnis:** Der Pfad, in dem die Partitionen für die QoE-Archivdatenbank gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="9cebf-166">Dies sollte sich auf einem Laufwerk (HDD3 in der empfohlenen Hardwarekonfiguration) befinden, das vom Laufwerk des Betriebssystems und vom SQL-Datenbank-Protokolldateien getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="9cebf-167">Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, ein leeres Verzeichnis ohne Dateien verwendet werden sollte, um potenzielle Konflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="9cebf-168">**SQL-Agent-Auftrags Benutzer- &amp; Kennwort für Benutzer Name:** Name und Kennwort des Domänendienstkontos (maskiert), das verwendet wird, um den Schritt "QoE-Archivdaten" des SQL Server-Agent-Auftrags auszuführen (der die gespeicherte Prozedur ausführt, um Daten aus QoE-Metriken DB in Archiv DB abzurufen, damit dieses Konto über Lesezugriff auf QoE-Metriken DB verfügt, wie im Abschnitt "Konten" angegeben.</span><span class="sxs-lookup"><span data-stu-id="9cebf-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="9cebf-169">Dieses Konto muss auch über eine Anmeldung in der SQL Server-Instanz des QoE-Archivs verfügen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9cebf-170">Das Konto, unter dem die SQL Server-Instanz ausgeführt wird, beispielsweise NT-SERVICE\MSSQLSERVER, muss über Zugriff/Berechtigung für die oben angegebenen Verzeichnisse verfügen, damit die Installation erfolgreich durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9cebf-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="9cebf-171">Ausführliche Informationen finden Sie unter [Konfigurieren von Datei System Berechtigungen für den Zugriff auf Datenbankmodul](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9cebf-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="9cebf-172">Wenn Sie auf "weiter" klicken, führt das Installationsprogramm Voraussetzungen und meldet, ob Probleme aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="9cebf-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="9cebf-173">Wenn alle Voraussetzungen überprüft werden, wird das Installationsprogramm zur Seite Cube-Konfiguration weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="9cebf-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9cebf-174">Wenn im Installationsprogramm eine Warnmeldung angezeigt wird, dass der SQL Server-Agentdienst für die SQL Server-Instanz des QoE-Archivs derzeit nicht ausgeführt wird, kann die Installation fortgesetzt werden, aber nach der Installation stellen Sie sicher, dass der SQL-Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf Automatisch, damit der geplante Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9cebf-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="9cebf-175">Geben Sie auf der Seite Cube-Konfiguration die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="9cebf-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="9cebf-176">**QoE-Archiv-SQL Server-Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="9cebf-177">Cube kann nur auf dem Computer installiert werden, auf dem die QoE-Archivdatenbank vorhanden ist (Hinweis.</span><span class="sxs-lookup"><span data-stu-id="9cebf-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="9cebf-178">Cube selbst kann auf einem Remotecomputer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="9cebf-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="9cebf-179">Siehe unten)</span><span class="sxs-lookup"><span data-stu-id="9cebf-179">See below)</span></span>
    
   - <span data-ttu-id="9cebf-180">**QoE-Archiv-SQL Server-Instanz:** Name der SQL Server-Instanz für die Position der QoE-Archivdatenbank.</span><span class="sxs-lookup"><span data-stu-id="9cebf-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="9cebf-181">Wenn Sie eine standardmäßige SQL Server-Instanz angeben möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="9cebf-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="9cebf-182">Wenn Sie eine benannte SQL Server-Instanz angeben möchten, geben Sie den Namen der Instanz ein (z\". b. den Namen nach ").</span><span class="sxs-lookup"><span data-stu-id="9cebf-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="9cebf-183">Wenn die QoE-Archivierungs Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="9cebf-184">**Cube Analysis-Server:** SQL Server Analysis Service-Instanzname für die Stelle, an der der Cube erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9cebf-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="9cebf-185">Hierbei kann es sich um einen anderen Computer handeln, aber der Installationsbenutzer muss ein Mitglied der Serveradministratoren der Ziel-SQL Server-Analysis-Dienstinstanz sein.</span><span class="sxs-lookup"><span data-stu-id="9cebf-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="9cebf-186">Weitere Informationen zum Konfigurieren von Analysis Services Server-Administratorberechtigungen finden Sie unter [Erteilen von Server Administratorberechtigungen (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9cebf-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="9cebf-187">**Verwenden mehrerer Partitionen:** Der Standardwert ist auf "mehrere Partitionen" eingestellt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert.</span><span class="sxs-lookup"><span data-stu-id="9cebf-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="9cebf-188">Wählen Sie für Standard Edition die Option "einzelne Partition" aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="9cebf-189">Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn einzelne Partitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="9cebf-190">Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="9cebf-191">Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "ändern" in der Systemsteuerung erneut installiert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="9cebf-192">**Cube-Benutzer-Kennwort &amp; für Benutzer Name:** Name und Kennwort des Domänendienstkontos (maskiert), mit dem die Cube-Verarbeitung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9cebf-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="9cebf-193">Wenn die QoE-Archivierungs Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem Wert auf der Seite Archivkonfiguration für den SQL-Agentauftrag des Auftrags Benutzers ausgefüllt, es wird jedoch empfohlen, ein anderes Domänendienstkonto anzugeben, damit Setup dem das am wenigsten erforderliche Privileg.</span><span class="sxs-lookup"><span data-stu-id="9cebf-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="9cebf-194">Wenn Sie auf Weiter klicken, wird eine weitere Gültigkeitsprüfung durchgeführt, und es werden alle Probleme gemeldet.</span><span class="sxs-lookup"><span data-stu-id="9cebf-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="9cebf-195">Nach dem erfolgreichen Abschluss der Überprüfung wird das Installationsprogramm zur Seite Portal-Konfiguration wechseln.</span><span class="sxs-lookup"><span data-stu-id="9cebf-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="9cebf-196">Geben Sie auf der Seite Portal-Konfiguration die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="9cebf-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="9cebf-197">**QoE-Archiv SQL Server:** Name der SQL Server-Instanz für die Position der QoE-Archivdatenbank.</span><span class="sxs-lookup"><span data-stu-id="9cebf-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="9cebf-198">Beachten Sie, dass der Computername im Gegensatz zur Seite QoE-Archivkonfiguration und der Seite Cube-Konfiguration nicht festgelegt ist und bereitgestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="9cebf-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="9cebf-199">Wenn die QoE-Archivierungs Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="9cebf-200">**Cube Analysis-Server:** SQL Server Analysis Service-Instanzname für die Position des Cubes.</span><span class="sxs-lookup"><span data-stu-id="9cebf-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="9cebf-201">Wenn die Cube-Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite Cube-Konfiguration bereitgestellten Wert vorab gefüllt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="9cebf-202">**Repository SQL Server:** SQL Server-Instanzname, in dem die Repository-Datenbank erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9cebf-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="9cebf-203">Wenn der SQL Server-Instanzname für den Speicherort der QoE-Archivdatenbank zuvor in der Einrichtung (in anderen Komponenten) bereitgestellt wurde, wird dieses Feld mit dem SQL Server-Instanznamen der QoE-Archivdatenbank vorab ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="9cebf-204">Dies kann eine beliebige SQL Server-Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="9cebf-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="9cebf-205">**Repository-Datenbank:** Standardmäßig ist die Option auf "neue Datenbank erstellen" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="9cebf-206">Da die Repository-DB-Aktualisierung nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Repository-DB das gleiche Schema wie der zu installierende Build aufweist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="9cebf-207">**Benutzer Name &amp; -Kennwort des IIS-App-Pools:** Das Konto, unter dem der IIS-Anwendungspool ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9cebf-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="9cebf-208">Die Felder Benutzer Name und Kennwort werden abgeblendet, wenn integrierte Systemkonten ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="9cebf-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="9cebf-209">Diese Felder werden nur aktiviert, wenn im Dropdownfeld "andere" ausgewählt ist, damit der Benutzer die Informationen zum Domänendienstkonto eingeben kann.</span><span class="sxs-lookup"><span data-stu-id="9cebf-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="9cebf-210">Wenn Sie auf Weiter klicken, wird die abschließende Gültigkeitsprüfung durchgeführt, um sicherzustellen, dass die SQL Server-Instanzen über die bereitgestellten Anmeldeinformationen zugänglich sind und dass IIS auf dem Computer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="9cebf-211">Nach dem erfolgreichen Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9cebf-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="9cebf-212">Wenn das Installationsprogramm abgeschlossen ist, wird der SQL Server-Agent-Auftrag höchstwahrscheinlich ausgeführt, wobei das anfängliche Laden der QoE-Daten und die Cube-Verarbeitung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9cebf-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="9cebf-213">Je nach der Datenmenge in QoE steht dem Portal noch keine Daten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9cebf-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="9cebf-214">Wenn Sie den Status der Datenauslastung und der Cube-Verarbeitung überprüfen möchten `http://<machinename>/CQD/#/Health`, wechseln Sie zu.</span><span class="sxs-lookup"><span data-stu-id="9cebf-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="9cebf-215">Beachten Sie, dass die URL für die Überprüfung des Status der Download Cube-Verarbeitung Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="9cebf-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="9cebf-216">Wenn Sie "Gesundheit" eingeben, funktioniert die URL nicht.</span><span class="sxs-lookup"><span data-stu-id="9cebf-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="9cebf-217">Sie müssen "Gesundheit" am Ende der URL mit einem Großbuchstaben H eingeben.</span><span class="sxs-lookup"><span data-stu-id="9cebf-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="9cebf-218">Wenn der Debugmodus aktiviert ist, werden detaillierte Protokollmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="9cebf-219">Zum Aktivieren des Debugmodus wechseln Sie zu **%SystemDrive%\Programme\Gemeinsame Files\Skype for Business 2015 CQD\QoEDataService\web.config**, und aktualisieren Sie die folgende Zeile, damit der Wert auf **true**festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="9cebf-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="9cebf-220">Auf die Hauptseite des Portals `http://<machinename>/CQD`kann über zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="9cebf-221">Verwalten des Benutzerzugriffs für das Portal</span><span class="sxs-lookup"><span data-stu-id="9cebf-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="9cebf-222">Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7,0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9cebf-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="9cebf-223">Weitere Informationen zur IIS-Sicherheit finden Sie unter [Grundlegendes zur IIS 7,0-URL-Autorisierung](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="9cebf-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="9cebf-224">Jede Website oder Webanwendung erbt die für das gesamte IIS konfigurierte Standard-URL-Autorisierung, die in der Regel "alle Benutzer zulassen" lautet.</span><span class="sxs-lookup"><span data-stu-id="9cebf-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="9cebf-225">Wenn der Zugriff auf das Portal restriktiver sein muss, können Administratoren den Zugriff nur für bestimmte Benutzergruppen gewähren, indem Sie die "Autorisierungsregeln" bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9cebf-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Anrufqualität bereitstellen – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="9cebf-227">Das Symbol "Autorisierungsregeln" darf nicht mit der ".NET-Autorisierung" im Abschnitt ASP.net verwechselt werden, bei dem es sich um einen anderen Autorisierungsmechanismus handelt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="9cebf-228">Administratoren sollten zunächst die geerbte Regel "alle Benutzer zulassen" entfernen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="9cebf-229">Dadurch wird verhindert, dass nicht autorisierte Benutzer auf das Portal zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![CQD bereitstellen](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="9cebf-231">Als nächstes sollten Administratoren neue Zulassungsregeln hinzufügen und bestimmten Benutzern die Berechtigung für den Zugriff auf das Portal erteilen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="9cebf-232">Es wird empfohlen, eine lokale Gruppe mit dem Namen "CQDPortalUsers" zu erstellen, um die Benutzer zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9cebf-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Anrufqualitäts-Dashboard bereitstellen](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="9cebf-234">Die Konfigurationsdetails werden in der Web. config-Datei gespeichert, die sich im physikalischen Verzeichnis des Portals befindet.</span><span class="sxs-lookup"><span data-stu-id="9cebf-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```XML
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="9cebf-235">Im nächsten Schritt wird das Dashboard des CQD-Steuerpults konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9cebf-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="9cebf-236">Nachdem Benutzer von IIS authentifiziert wurden, müssen Sie über Dateiberechtigungen für das CQD-Verzeichnis verfügen, um auf den Inhalt des Webportals zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="9cebf-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="9cebf-237">Es ist möglich, die ACLs über die Registerkarte Sicherheit der CQD-Verzeichniseigenschaften zu ändern, um einzelne Benutzer oder Gruppen hinzuzufügen. die empfohlene Vorgehensweise besteht jedoch darin, die Dateiberechtigungen unangetastet zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="9cebf-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="9cebf-238">Ändern Sie stattdessen die IIS-Einstellung, um den IIS-Workerprozess für den Zugriff auf das CQD-Verzeichnis zu verwenden, unabhängig davon, welche Benutzer authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9cebf-239">Es ist wichtig, diese Einstellung nur für die CQD-Anwendung und nicht für die beiden API-Anwendungen zu ändern: QoEDataService und QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="9cebf-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="9cebf-240">Konfigurieren des Dateizugriffs für das CQD (Dashboard)</span><span class="sxs-lookup"><span data-stu-id="9cebf-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="9cebf-241">Öffnen Sie den Konfigurations-Editor für CQD.</span><span class="sxs-lookup"><span data-stu-id="9cebf-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="9cebf-243">Wählen Sie unter Abschnitt die Option **System. Webserver/serverRuntime**aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="9cebf-245">Ändern Sie authenticatedUserOverride in **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="9cebf-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="9cebf-247">Klicken Sie auf der rechten Seite der Seite auf über **nehmen** .</span><span class="sxs-lookup"><span data-stu-id="9cebf-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="9cebf-248">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="9cebf-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="9cebf-249">Das CQD zeigt nach der Bereitstellung keine Daten an.</span><span class="sxs-lookup"><span data-stu-id="9cebf-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="9cebf-250">Möglicherweise wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9cebf-250">You may receive the following error:</span></span>

<span data-ttu-id="9cebf-251">*Die Abfrage konnte nicht ausgeführt werden, während Sie auf dem Cube ausgeführt wurde. Verwenden Sie den Abfrage-Editor, um die Abfrage zu ändern und Probleme zu beheben. Stellen Sie außerdem sicher, dass der Cube barrierefrei ist.*</span><span class="sxs-lookup"><span data-stu-id="9cebf-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="9cebf-252">Dies bedeutet, dass der Cube in SQL Server Analysis Services verarbeitet werden muss, bevor er in CQD verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9cebf-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="9cebf-253">Führen Sie die folgenden Schritte aus, um dies zu beheben:</span><span class="sxs-lookup"><span data-stu-id="9cebf-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="9cebf-254">Öffnen Sie SQL Management Studio, und wählen Sie **Analysis Services**aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="9cebf-255">Erweitern Sie das **QoECube** -Objekt, wählen Sie **QoE-Metrik**aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Durchsuchen**aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="9cebf-256">Wenn dieser leere Browser zurückgibt, wurde der Cube noch nicht fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9cebf-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="9cebf-257">Klicken Sie mit der rechten Maustaste auf **QoE Metric** angain, und wählen Sie **Prozess**aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="9cebf-258">Wenn die Verarbeitung abgeschlossen ist, klicken Sie erneut mit der rechten Maustaste auf das Objekt, und wählen Sie **Durchsuchen** aus, um zu bestätigen, dass auf der Browser Seite nun Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="9cebf-259">Benutzer haben Probleme beim anmelden, weil das Installationsprogramm die richtigen Einstellungen in IIS nicht erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="9cebf-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="9cebf-260">In seltenen Fällen kann das Installationsprogramm die richtigen Einstellungen in IIS nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="9cebf-261">Eine manuelle Änderung ist erforderlich, damit Benutzer sich beim CQD anmelden können.</span><span class="sxs-lookup"><span data-stu-id="9cebf-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="9cebf-262">Wenn Benutzer Probleme beim Anmelden haben, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9cebf-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="9cebf-263">Öffnen Sie den IIS-Manager, und navigieren Sie zur Standardwebsite.</span><span class="sxs-lookup"><span data-stu-id="9cebf-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="9cebf-265">Klicken Sie auf "Authentifizierung".</span><span class="sxs-lookup"><span data-stu-id="9cebf-265">Click on "Authentication".</span></span> <span data-ttu-id="9cebf-266">Wenn die Optionen "anonyme Authentifizierung", "ASP.NET-Identitätswechsel", "Formularauthentifizierung" und "Windows-Authentifizierung" nicht den nachstehenden Einstellungen entsprechen, ändern Sie diese manuell so, dass Sie den unten angegebenen Einstellungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="9cebf-267">Alle anderen Authentifizierungsmechanismen sollten deaktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="9cebf-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="9cebf-269">Klicken Sie unter "Windows-Authentifizierung" auf der rechten Seite auf Erweiterte Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="9cebf-271">Setzen Sie "Erweiterter Schutz" auf "akzeptieren", und aktivieren Sie das Kontrollkästchen "Kernel Modus-Authentifizierung aktivieren".</span><span class="sxs-lookup"><span data-stu-id="9cebf-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="9cebf-273">Wiederholen Sie die obigen Schritte für jeden der Einträge "CQD", "QoEDataService" und "QoERepositoryService" unter "Standardwebsite".</span><span class="sxs-lookup"><span data-stu-id="9cebf-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="9cebf-274">Für http-und HTTPS-Portbindungen erstellt das Installationsprogramm Portbindungen auf den Standardportnummern (Port 80 für http und Port 443 für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="9cebf-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="9cebf-275">Wenn auf dem Computer eine andere Website vorhanden ist, die diese Bindungen verwendet, tritt ein Konflikt auf, und das IIS-Verhalten kann nicht vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="9cebf-276">Die beste Methode, um dieses Problem zu vermeiden, besteht darin, sicherzustellen, dass vor der Installation von CQD keine anderen Websites den Anschlüssen 80 und 443 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="9cebf-277">So aktivieren Sie SSL/TLS in IIS und erzwingen, dass Benutzer über sicheres HTTPS und nicht über HTTP verbunden werden:</span><span class="sxs-lookup"><span data-stu-id="9cebf-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="9cebf-278">Konfigurieren von Secure Sockets Layer in IIS finden Sie unter [Konfigurieren von Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="9cebf-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="9cebf-279">Wenn Sie fertig sind `http` , `https`ersetzen Sie durch.</span><span class="sxs-lookup"><span data-stu-id="9cebf-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="9cebf-280">Anweisungen zum Aktivieren von TLS in den SQL Server-Verbindungen finden Sie unter [Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe der Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="9cebf-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="9cebf-281">Fehler bei der Cube-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="9cebf-281">Cube Sync Fails</span></span>

<span data-ttu-id="9cebf-282">Datenbank QoEMetrics werden kann einige ungültige Datensätze enthalten, die auf Endbenutzer Uhren basieren.</span><span class="sxs-lookup"><span data-stu-id="9cebf-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="9cebf-283">Wenn die Zeitabweichung größer als 60 Jahre ist, schlägt der Cube-Import fehl.</span><span class="sxs-lookup"><span data-stu-id="9cebf-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="9cebf-284">Überprüfen Sie die min-und Max-anfangs-EndTime mit den nachstehenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="9cebf-285">Suchen und Löschen von Datensätzen in der Vergangenheit und in sehr ferner Zukunft können Sie ignoriert werden, und Sie werden die Synchronisierungsprozesse aufteilen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="9cebf-286">Wählen Sie min (Startzeit) in CqdPartitionedStreamView aus.</span><span class="sxs-lookup"><span data-stu-id="9cebf-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="9cebf-287">Wählen Sie Max (Startzeit) von CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="9cebf-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="9cebf-288">Wählen Sie min (EndTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="9cebf-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="9cebf-289">Wählen Sie Max (EndTime) aus CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="9cebf-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="9cebf-290">Aufgaben nach der Installation</span><span class="sxs-lookup"><span data-stu-id="9cebf-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="9cebf-291">Importieren von Gebäuden und Netzwerken</span><span class="sxs-lookup"><span data-stu-id="9cebf-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="9cebf-292">Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="9cebf-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="9cebf-293">Definieren von Gebäudetypen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="9cebf-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="9cebf-294">Definieren von Gebäude Besitztypen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="9cebf-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="9cebf-295">Definieren von Netzwerktypen (dringend empfohlen)</span><span class="sxs-lookup"><span data-stu-id="9cebf-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="9cebf-296">Importieren von Gebäuden (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="9cebf-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="9cebf-297">Importieren von Subnetzen (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="9cebf-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="9cebf-298">Definieren von Gebäudetypen</span><span class="sxs-lookup"><span data-stu-id="9cebf-298">Define Building Types</span></span>

<span data-ttu-id="9cebf-299">Gebäudetypen werden verwendet, um die verschiedenen Gebäude Definitionen oder-Typen in Ihrer Organisation zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9cebf-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9cebf-300">Dieser Schritt ist optional, wird aber empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="9cebf-301">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9cebf-301">Examples</span></span>
  
- <span data-ttu-id="9cebf-302">Hauptsitz</span><span class="sxs-lookup"><span data-stu-id="9cebf-302">Headquarters</span></span>
    
- <span data-ttu-id="9cebf-303">Remote Office</span><span class="sxs-lookup"><span data-stu-id="9cebf-303">Remote Office</span></span>
    
- <span data-ttu-id="9cebf-304">Joint-Venture-Standort</span><span class="sxs-lookup"><span data-stu-id="9cebf-304">Joint-venture location</span></span>
    
  <span data-ttu-id="9cebf-305">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="9cebf-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="9cebf-306">Die Parameter BuildingTypeId und BuildingTypeDesc sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9cebf-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="9cebf-307">Definieren von Gebäude Besitztypen</span><span class="sxs-lookup"><span data-stu-id="9cebf-307">Define Building Ownership Types</span></span>

<span data-ttu-id="9cebf-308">Besitzer Typen werden zur Unterscheidung von Besitz-vs-leasingobjekten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cebf-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cebf-309">Dieser Schritt ist optional, wird aber empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="9cebf-310">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9cebf-310">Examples</span></span>
  
- <span data-ttu-id="9cebf-311">Von Contoso geleaste nicht&amp;-Re F</span><span class="sxs-lookup"><span data-stu-id="9cebf-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="9cebf-312">Contoso vermietet re&amp;F</span><span class="sxs-lookup"><span data-stu-id="9cebf-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="9cebf-313">Contoso-Besitzer</span><span class="sxs-lookup"><span data-stu-id="9cebf-313">Contoso Owned</span></span>
    
- <span data-ttu-id="9cebf-314">Tochtergesellschaft geleast</span><span class="sxs-lookup"><span data-stu-id="9cebf-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="9cebf-315">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="9cebf-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="9cebf-316">Die Parameter OwnershipTypeId und OwnershipTypeDesc sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9cebf-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="9cebf-317">Definieren von Netzwerknamen</span><span class="sxs-lookup"><span data-stu-id="9cebf-317">Define Network Names</span></span>

<span data-ttu-id="9cebf-318">Netzwerktypen werden verwendet, um unterschiedliche Arten von Netzwerken innerhalb der Organisation zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9cebf-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="9cebf-319">Dadurch haben Sie die Möglichkeit, bestimmte Netzwerktypen zu filtern (oder zu filtern).</span><span class="sxs-lookup"><span data-stu-id="9cebf-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9cebf-320">Es wird dringend empfohlen, Netzwerknamen zu definieren, aber es ist optional.</span><span class="sxs-lookup"><span data-stu-id="9cebf-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="9cebf-321">Wenn Sie sich entscheiden, keine Netzwerknamen zu definieren, stellen Sie sicher, dass jeder CqdNetwork-Eintrag eine Building-0 (null) hat.</span><span class="sxs-lookup"><span data-stu-id="9cebf-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="9cebf-322">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9cebf-322">Examples</span></span>
  
- <span data-ttu-id="9cebf-323">VPN</span><span class="sxs-lookup"><span data-stu-id="9cebf-323">VPN</span></span>
    
- <span data-ttu-id="9cebf-324">Labor</span><span class="sxs-lookup"><span data-stu-id="9cebf-324">LAB</span></span>
    
  <span data-ttu-id="9cebf-325">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="9cebf-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="9cebf-326">Die Parameter NetworkNameID und networkName sind erforderlich, der NetworkType-Parameter ist optional, wird aber empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="9cebf-327">Importieren von Gebäuden</span><span class="sxs-lookup"><span data-stu-id="9cebf-327">Import Buildings</span></span>

<span data-ttu-id="9cebf-328">Durch das Importieren von Gebäuden erhalten Sie die Möglichkeit, gebäudespezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.).</span><span class="sxs-lookup"><span data-stu-id="9cebf-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9cebf-329">Dieser Schritt ist optional, wird aber empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="9cebf-330">Bevor Sie ein neues Gebäude importieren, sollten Sie bereits einen vordefinierten BuildingKey identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="9cebf-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="9cebf-331">Geben Sie dazu den SQL-Befehl "Select Max (BuildingKey) from CqdBuilding" ein, um den aktuellen Wert zu identifizieren und dem Ergebnis 1 hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="9cebf-332">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="9cebf-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="9cebf-333">Die Parameter BuildingKey, buildingname, BuildingShortName, OwnershipTypeId, BuildingTypeId sind erforderlich, die anderen Parameter sind optional.</span><span class="sxs-lookup"><span data-stu-id="9cebf-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="9cebf-334">Importieren von Subnetzen</span><span class="sxs-lookup"><span data-stu-id="9cebf-334">Import Subnets</span></span>

<span data-ttu-id="9cebf-335">Durch das Importieren von Gebäuden erhalten Sie die Möglichkeit, gebäudespezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.).</span><span class="sxs-lookup"><span data-stu-id="9cebf-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9cebf-336">Dieser Schritt ist optional, wird aber empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9cebf-336">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="9cebf-337">Importieren Sie Subnets, und ordnen Sie Sie den Gebäuden zu, die im letzten Schritt importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="9cebf-338">Wenn Sie sich entschließen, "networkName" zu füllen, stellen Sie sicher, dass jeder Eintrag in dieser Tabelle eine NetworkNameID von 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cebf-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="9cebf-339">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="9cebf-339">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="9cebf-340">Die Parameter Netzwerk und UpdatedDate sind erforderlich, die anderen Parameter sind optional.</span><span class="sxs-lookup"><span data-stu-id="9cebf-340">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="9cebf-341">Optional: BSSID</span><span class="sxs-lookup"><span data-stu-id="9cebf-341">Optional: BSSID</span></span>

<span data-ttu-id="9cebf-342">Durch das Auffüllen von BSSID-Informationen erhalten Sie zusätzliche WLAN-Datenstrom Korrelation per Controller oder Radio.</span><span class="sxs-lookup"><span data-stu-id="9cebf-342">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="9cebf-343">Dies gilt zusätzlich zum Filtern nach Gebäude oder Subnetz.</span><span class="sxs-lookup"><span data-stu-id="9cebf-343">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="9cebf-344">**SQL-Beispiel Syntax**</span><span class="sxs-lookup"><span data-stu-id="9cebf-344">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="9cebf-345">**Details zu CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="9cebf-345">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="9cebf-346">**Wie in CQD**</span><span class="sxs-lookup"><span data-stu-id="9cebf-346">**As shown in CQD**</span></span>|<span data-ttu-id="9cebf-347">**CQDBssid-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="9cebf-347">**CQDBssid Table**</span></span>|<span data-ttu-id="9cebf-348">**Beispieleingaben**</span><span class="sxs-lookup"><span data-stu-id="9cebf-348">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9cebf-349">AP NName</span><span class="sxs-lookup"><span data-stu-id="9cebf-349">Ap NName</span></span>  <br/> |<span data-ttu-id="9cebf-350">AP</span><span class="sxs-lookup"><span data-stu-id="9cebf-350">AP</span></span>  <br/> |<span data-ttu-id="9cebf-351">AP1</span><span class="sxs-lookup"><span data-stu-id="9cebf-351">AP1</span></span>  <br/> |
|<span data-ttu-id="9cebf-352">BBssid</span><span class="sxs-lookup"><span data-stu-id="9cebf-352">BBssid</span></span>  <br/> |<span data-ttu-id="9cebf-353">BSS</span><span class="sxs-lookup"><span data-stu-id="9cebf-353">BSS</span></span>  <br/> |<span data-ttu-id="9cebf-354">00-00-00-00-00-00 (Sie müssen die getrennte Fformat verwenden)</span><span class="sxs-lookup"><span data-stu-id="9cebf-354">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="9cebf-355">Controller</span><span class="sxs-lookup"><span data-stu-id="9cebf-355">Controller</span></span>  <br/> |<span data-ttu-id="9cebf-356">Gebäude</span><span class="sxs-lookup"><span data-stu-id="9cebf-356">Building</span></span>  <br/> |<span data-ttu-id="9cebf-357">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="9cebf-357">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="9cebf-358">Gerät</span><span class="sxs-lookup"><span data-stu-id="9cebf-358">Device</span></span>  <br/> |<span data-ttu-id="9cebf-359">ess</span><span class="sxs-lookup"><span data-stu-id="9cebf-359">ess</span></span>  <br/> |<span data-ttu-id="9cebf-360">Controller1</span><span class="sxs-lookup"><span data-stu-id="9cebf-360">Controller1</span></span>  <br/> |
|<span data-ttu-id="9cebf-361">Radio</span><span class="sxs-lookup"><span data-stu-id="9cebf-361">Radio</span></span>  <br/> |<span data-ttu-id="9cebf-362">phy</span><span class="sxs-lookup"><span data-stu-id="9cebf-362">phy</span></span>  <br/> |<span data-ttu-id="9cebf-363">BGN</span><span class="sxs-lookup"><span data-stu-id="9cebf-363">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="9cebf-364">Verarbeiten der importierten Daten</span><span class="sxs-lookup"><span data-stu-id="9cebf-364">Processing the imported data</span></span>

<span data-ttu-id="9cebf-365">Standardmäßig werden nach dem Importieren von Gebäude-/Netzwerkdaten nur Datensätze angewendet, die nach diesem Zeitpunkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-365">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="9cebf-366">Wenn Sie alle vorherigen Datensätze mit diesen neuen Daten kennzeichnen möchten, müssen Sie die gespeicherte Prozedur CqdUpdateBuilding ausführen, wie unten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9cebf-366">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="9cebf-367">Geben Sie Ihr das Datum des ersten Eintrags (identifizieren Sie die Verwendung des Befehls min (Startzeit) aus CqdPartitionedStreamView SQL auswählen), ein EndDate von morgen und dann NULL für die letzten beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="9cebf-367">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="9cebf-368">Sobald die Daten Datenstromdaten zugeordnet sind, muss der SSIS-Cube alle Datensätze erneut verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9cebf-368">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="9cebf-369">Dies gilt auch, wenn Massen BSSID/ISP-Daten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9cebf-369">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="9cebf-370">Stellen Sie sicher, dass "vollständiger Prozess" ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="9cebf-370">Ensure that "Process Full" is selected.</span></span>
  

