---
title: 'Lync Server 2013: Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd9f07b979f89a28b6fa545f3a43009402f4ed1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="e73f2-102">Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e73f2-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e73f2-103">_**Letztes Änderungsdatum des Themas:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="e73f2-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="e73f2-104">Die Trennung von Rollen und Zuständigkeiten zwischen Serveradministratoren und SQL Server-Administratoren kann zu Verzögerungen bei der Implementierung führen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="e73f2-105">Lync Server 2013 verwendet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), um diese Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e73f2-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="e73f2-106">In einigen Fällen muss der SQL Server-Administrator die Installation von Datenbanken auf dem SQL Server-basierten Server außerhalb von RBAC verwalten.</span><span class="sxs-lookup"><span data-stu-id="e73f2-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="e73f2-107">Die lync Server 2013-Verwaltungsshell bietet dem SQL Server-Administrator die Möglichkeit, Windows PowerShell-Cmdlets auszuführen, die zum Konfigurieren der Datenbanken mit den korrekten Daten und Protokolldateien entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="e73f2-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="e73f2-108">Ausführliche Informationen finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e73f2-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e73f2-109">Im folgenden Verfahren wird davon ausgegangen, dass mindestens die lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012-Verwaltungsobjekte, CLR-Typen für Microsoft SQL Server 2012 und Microsoft SQL Server 2012 ADOMD.NET installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e73f2-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="e73f2-110">Die OCSCore. msi-Datei befindet sich auf dem Installationsmedium im Verzeichnis \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="e73f2-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="e73f2-111">Die restlichen Komponenten befinden sich in \setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="e73f2-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="e73f2-112">Darüber hinaus wurde die Active Directory-Vorbereitung für lync Server 2013 erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="e73f2-113">" **Installieren-CsDatabase** " ist das Windows PowerShell-Cmdlet, mit dem Sie die Datenbanken installieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="e73f2-114">Das Cmdlet " **install-CsDatabase** " verfügt über eine große Anzahl von Parametern, von denen nur einige hier besprochen werden.</span><span class="sxs-lookup"><span data-stu-id="e73f2-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="e73f2-115">Details zu den möglichen Parametern finden Sie in der Dokumentation zur lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e73f2-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="e73f2-116">Um die Leistung und mögliche Timeoutprobleme zu vermeiden, sollten Sie immer vollqualifizierte Domänennamen (FQDNs) verwenden, wenn Sie auf SQL Server-basierte Server verweisen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="e73f2-117">Vermeiden Sie die Verwendung von Host Namen bezogenen verweisen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-117">Avoid using host name-only references.</span></span> <span data-ttu-id="e73f2-118">Verwenden Sie beispielsweise sqlbe01.contoso.net, aber vermeiden Sie die Verwendung von sqlbe01.</span><span class="sxs-lookup"><span data-stu-id="e73f2-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="e73f2-119">Für die Installation von Datenbanken verwendet **install-CsDatabase** drei primäre Methoden zum Platzieren der Datenbanken auf dem vorbereiteten SQL Server-basierten Server:</span><span class="sxs-lookup"><span data-stu-id="e73f2-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="e73f2-120">Führen Sie **install-CsDatabase** ohne DatabasePaths oder UseDefaultSqlPath aus.</span><span class="sxs-lookup"><span data-stu-id="e73f2-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="e73f2-121">Das Cmdlet verwendet einen integrierten Algorithmus, um die beste Platzierung für das Protokoll und die Datendateien zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e73f2-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="e73f2-122">Der Algorithmus funktioniert nur für eigenständige SQL Server-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="e73f2-123">Führen Sie **install-CsDatabase** mit dem DatabasePaths-Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="e73f2-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="e73f2-124">Der integrierte Algorithmus zum Optimieren von Protokoll-und Datendateispeicher Orten wird nicht verwendet, wenn der DatabasePaths-Parameter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e73f2-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="e73f2-125">Mithilfe dieses Parameters können Sie die Speicherorte definieren, an denen Protokoll-und Datendateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e73f2-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="e73f2-126">Führen Sie **install-CsDatabase** mit UseDefaultSqlPaths aus.</span><span class="sxs-lookup"><span data-stu-id="e73f2-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="e73f2-127">Diese Option verwendet nicht den integrierten Algorithmus, um die Speicherorte für Protokolle und Datendateien zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="e73f2-128">Protokoll-und Datendatei werden gemäß den vom SQL Server-Administrator gesetzten Standardeinstellungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e73f2-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="e73f2-129">Diese Pfade werden in der Regel für die automatische Verwaltung von Protokoll-und Datendateien auf dem SQL Server im Voraus eingestellt und sind nicht mit dem Setup von lync Server 2013 verbunden.</span><span class="sxs-lookup"><span data-stu-id="e73f2-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="e73f2-130">Der DatabasePathMap-Parameter kann auch verwendet werden, um einen Speicherort für jede Datenbank und die zugehörige Protokolldatei explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e73f2-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="e73f2-131">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren des SQL Server Central-Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="e73f2-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="e73f2-132">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="e73f2-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="e73f2-133">Ausführliche Informationen finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e73f2-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="e73f2-134">Öffnen Sie die lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e73f2-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="e73f2-135">Wenn Sie die Ausführungsrichtlinie für Windows PowerShell nicht angepasst haben, müssen Sie die Richtlinie so anpassen, dass Windows PowerShell-Skripts ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e73f2-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="e73f2-136">Ausführliche Informationen finden Sie unter "Überprüfen der Ausführungsrichtlinie" [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)unter.</span><span class="sxs-lookup"><span data-stu-id="e73f2-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="e73f2-137">Verwenden Sie das Cmdlet " **install-CsDatabase** ", um den zentralen Verwaltungsspeicher zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e73f2-138">Der Berichtsparameter ist optional, aber hilfreich, wenn Sie den Installationsvorgang dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="e73f2-139">**Install-CsDatabase – DatabasePaths** kann bis zu sechs Pfadparameter verwenden, die jeweils die Pfade für die Laufwerke definieren, wie Sie in SQL Server-Daten und in der Protokolldatei Platzierung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e73f2-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="e73f2-140">Nach den logischen Regeln der Datenbankkonfiguration in lync Server 2013 werden Laufwerke in Buckets von zwei, vier oder sechs analysiert.</span><span class="sxs-lookup"><span data-stu-id="e73f2-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="e73f2-141">Je nach SQL Server-Konfiguration und Anzahl der Buckets werden zwei Pfade, vier Pfade oder sechs Pfade bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e73f2-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="e73f2-142">Wenn Sie über drei Laufwerke verfügen, erhält das Protokoll Priorität, und danach werden die Datendateien verteilt.</span><span class="sxs-lookup"><span data-stu-id="e73f2-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="e73f2-143">Ein Beispiel für einen auf SQL Server basierenden Server, der mit sechs Laufwerken konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e73f2-143">An example for a SQL Server-based server configured with six drives:</span></span>
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  <span data-ttu-id="e73f2-144">Nach Abschluss der Datenbankinstallation können Sie die lync Server 2013-Verwaltungsshell schließen oder mit der Installation der im Topologie-Generator definierten lync Server 2013-Datenbanken fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="e73f2-145">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der konfigurierten SQL Server-Topologie für Datenbanken</span><span class="sxs-lookup"><span data-stu-id="e73f2-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="e73f2-146">Zum Installieren des Topologie-Generators, der für lync Server 2013 konfiguriert ist, muss der lync Server 2013-Administrator die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="e73f2-147">Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e73f2-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="e73f2-148">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="e73f2-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="e73f2-149">Lesen Sie das Thema [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e73f2-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e73f2-150">Um die SQL Server-basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server-Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe Sysadmins (oder Äquivalent) auf dem Server ist, auf dem SQL Server ausgeführt wird, und die zentrale Verwaltung verwaltet. Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="e73f2-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="e73f2-151">Dies ist besonders wichtig, um nach weiteren lync Server 2013-Pools zu suchen, die eine SQL Server-Datenbankinstallation oder-Konfiguration erfordern.</span><span class="sxs-lookup"><span data-stu-id="e73f2-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="e73f2-152">Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle aber von pool01 gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e73f2-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="e73f2-153">Die SQL Server-Gruppe sysadmin (oder eine entsprechende) muss über Berechtigungen für beide SQL Server-basierten Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="e73f2-154">Öffnen Sie die lync Server 2013-Verwaltungsshell, wenn Sie noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="e73f2-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="e73f2-155">Verwenden Sie das Cmdlet " **install-CsDatabase** ", um die konfigurierten Datenbanken des Topologie-Generators zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e73f2-156">Der Berichtsparameter ist optional, aber hilfreich, wenn Sie den Installationsvorgang dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="e73f2-157">Wenn die Datenbankinstallation abgeschlossen ist, schließen Sie die lync Server 2013-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e73f2-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="e73f2-158">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der SQL Server-Topologie mithilfe des DatabasePathMap-Parameters</span><span class="sxs-lookup"><span data-stu-id="e73f2-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="e73f2-159">Zum Installieren von Datenbanken für lync Server 2013 muss der lync Server-Administrator die Pfade erstellen und die Datenbankendateien und Protokolldateien entsprechend einem vordefinierten Satz von Regeln bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="e73f2-160">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="e73f2-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="e73f2-161">Lesen Sie das Thema [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e73f2-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e73f2-162">Um die SQL Server-basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server-Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe Sysadmins (oder Äquivalent) auf dem Server ist, auf dem SQL Server ausgeführt wird, und die zentrale Verwaltung verwaltet. Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="e73f2-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="e73f2-163">Dies ist besonders wichtig, um nach weiteren lync Server-Pools zu suchen, die eine SQL Server-Datenbankinstallation oder-Konfiguration erfordern.</span><span class="sxs-lookup"><span data-stu-id="e73f2-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="e73f2-164">Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle aber von pool01 gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e73f2-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="e73f2-165">Die SQL Server-Gruppe sysadmin (oder eine entsprechende) muss über Berechtigungen für beide SQL Server-basierten Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="e73f2-166">Öffnen Sie die lync Server-Verwaltungsshell, wenn Sie noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="e73f2-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="e73f2-167">Verwenden Sie das Cmdlet **install-CsDatabase** mit dem DatabasePathMap-Parameter und einer PowerShell-Hashtabelle, um die konfigurierten Datenbanken des Topologie-Generators zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="e73f2-168">Im Beispielcode können die für die Datenbanken definierten Pfade auf granulare Weise mithilfe des – DatabasePathMap-Parameters und einer definierten Hashtabelle wie folgt bestimmt werden (im Beispiel wird "c\\: CSData" für alle Datenbankdateien (MDF) verwendet, und "\\ c: CSLogFiles "für alle Protokolldateien (LDF).</span><span class="sxs-lookup"><span data-stu-id="e73f2-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="e73f2-169">Der Ordner wird nach Bedarf von install-CsDatabase erstellt):</span><span class="sxs-lookup"><span data-stu-id="e73f2-169">Folder will be created as needed by Install-CsDatabase):</span></span>
    
        $pathmap = @{
        "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
        "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
        "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
        "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
        }
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap

6.  <span data-ttu-id="e73f2-170">Da die Datenbank-und Protokolldateien explizit mit ihrem Speicherort auf dem Zieldatenbankserver benannt sind, können Sie bestimmte Speicherorte für die tatsächliche Datenbank und den Speicherort des jeweiligen Diensttyps definieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="e73f2-171">Im folgenden Beispiel werden Datenbanken für jeden bestimmten Diensttyp auf separaten Datenträgern und zugehörigen Protokolldateien auf einer anderen Festplatte platziert.</span><span class="sxs-lookup"><span data-stu-id="e73f2-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="e73f2-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e73f2-172">For example:</span></span>
    
      - <span data-ttu-id="e73f2-173">Alle RTC-Datenbanken auf "\\D: RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="e73f2-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="e73f2-174">Alle RTC-Protokolldateien auf "E\\: RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="e73f2-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="e73f2-175">Alle Anwendungsspeicher Datenbanken auf "F:\\CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="e73f2-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="e73f2-176">Alle Anwendungsspeicher Protokolle auf "G:\\CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="e73f2-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="e73f2-177">Alle Antwortgruppen speichern Datenbanken auf "H\\: RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="e73f2-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="e73f2-178">Alle Reaktionsgruppen Speicherprotokolle auf "I:\\RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="e73f2-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="e73f2-179">Alle Adressbuchspeicher Datenbanken auf "J:\\ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="e73f2-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="e73f2-180">Alle Adressbuchspeicher-Protokolldateien in "K\\: ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="e73f2-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="e73f2-181">Alle Archivierungsspeicher Datenbanken auf "L:\\ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="e73f2-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="e73f2-182">Alle Archivierungsspeicher Protokolle auf "M:\\ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="e73f2-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="e73f2-183">Alle Überwachungsspeicher Datenbanken auf "N:\\MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="e73f2-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="e73f2-184">Alle Überwachungsspeicher-Protokolldateien auf "O\\: MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="e73f2-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ``` 
    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="e73f2-185">Mithilfe des-DatabasePathMap-Parameters können Sie eine beliebige Kombination aus logischem Laufwerksbuchstaben definieren, die die beste Lösung für Ihre Leistungs-und Platzierungs Anforderungen in SQL Server bietet.</span><span class="sxs-lookup"><span data-stu-id="e73f2-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="e73f2-186">Wenn Sie Ihre Datenbankdateien und Protokolldateien mithilfe der **DatabasePathMap** -Methode konfigurieren, müssen Sie bei Verwendung des Topologie-Generators eine geringfügige Änderung an Ihrem normalen Prozess vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e73f2-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="e73f2-187">In der Regel definieren Sie Ihre Topologie-Auswahl, veröffentlichen die Topologie und wählen, wie die Datenbankauswahl bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e73f2-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="e73f2-188">Wenn Sie **DatabasePathMap** verwendet haben, haben Sie bereits den dritten Teil des Topologie-Builder-Prozesses erfüllt.</span><span class="sxs-lookup"><span data-stu-id="e73f2-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="e73f2-189">Wenn Sie vor dem Ausführen des Topologie-Generators einen vollständig konfigurierten Datenbankserver besitzen, würden Sie weiterhin alle Serverrollen und-Optionen definieren, aber die Option zum Erstellen der Datenbanken deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e73f2-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

