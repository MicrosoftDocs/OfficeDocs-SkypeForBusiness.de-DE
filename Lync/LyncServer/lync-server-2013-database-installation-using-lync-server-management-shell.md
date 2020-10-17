---
title: 'Lync Server 2013: Datenbankinstallation mit lync Server-Verwaltungsshell'
description: 'Lync Server 2013: Datenbankinstallation mit lync Server-Verwaltungsshell.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558181"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="e659c-103">Datenbankinstallation mit lync Server-Verwaltungsshell in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e659c-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e659c-104">_**Letztes Änderungsstand des Themas:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="e659c-104">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="e659c-105">Die Trennung von Rollen und Zuständigkeiten zwischen Serveradministratoren und SQL Server Administratoren kann zu Verzögerungen bei der Implementierung führen.</span><span class="sxs-lookup"><span data-stu-id="e659c-105">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="e659c-106">Lync Server 2013 verwendet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), um diese Probleme zu verringern.</span><span class="sxs-lookup"><span data-stu-id="e659c-106">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="e659c-107">In einigen Fällen muss der SQL Server Administrator die Installation von Datenbanken auf dem SQL Server basierten Server außerhalb von RBAC verwalten.</span><span class="sxs-lookup"><span data-stu-id="e659c-107">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="e659c-108">Die lync Server 2013-Verwaltungsshell bietet dem SQL Server-Administrator die Möglichkeit, Windows PowerShell Cmdlets auszuführen, die für die Konfiguration der Datenbanken mit den richtigen Daten und Protokolldateien entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="e659c-108">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="e659c-109">Ausführliche Informationen finden Sie unter [Deployment Permissions for SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e659c-109">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e659c-110">Im folgenden Verfahren wird davon ausgegangen, dass mindestens die lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012-Verwaltungsobjekte, CLR-Typen für Microsoft SQL Server 2012 und Microsoft SQL Server 2012 ADOMD.NET installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e659c-110">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="e659c-111">Die OCSCore.msi befindet sich auf dem Installationsmedium im Verzeichnis \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="e659c-111">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="e659c-112">Die restlichen Komponenten befinden sich in \setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="e659c-112">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="e659c-113">Darüber hinaus wurde Active Directory Vorbereitung für lync Server 2013 erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e659c-113">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="e659c-114">**Install-CsDatabase** ist das Windows PowerShell Cmdlet, mit dem Sie die Datenbanken installieren.</span><span class="sxs-lookup"><span data-stu-id="e659c-114">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="e659c-115">Das Cmdlet **install-CsDatabase** verfügt über eine große Anzahl von Parametern, von denen nur einige hier erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="e659c-115">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="e659c-116">Ausführliche Informationen zu den möglichen Parametern finden Sie in der Dokumentation zur lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e659c-116">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="e659c-117">Verwenden Sie beim Verweisen auf SQL Server basierte Server immer vollqualifizierte Domänennamen (FQDNs), um die Leistung und mögliche Timeoutprobleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e659c-117">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="e659c-118">Vermeiden Sie die Verwendung von Host Namen bezogenen verweisen.</span><span class="sxs-lookup"><span data-stu-id="e659c-118">Avoid using host name-only references.</span></span> <span data-ttu-id="e659c-119">Verwenden Sie beispielsweise sqlbe01.contoso.net, vermeiden Sie jedoch die Verwendung von sqlbe01.</span><span class="sxs-lookup"><span data-stu-id="e659c-119">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="e659c-120">Für die Installation von Datenbanken verwendet **install-CsDatabase** drei primäre Methoden zum Platzieren der Datenbanken auf dem vorbereiteten SQL Server basierten Server:</span><span class="sxs-lookup"><span data-stu-id="e659c-120">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="e659c-121">Führen Sie **install-CsDatabase** ohne DatabasePaths oder UseDefaultSqlPath aus.</span><span class="sxs-lookup"><span data-stu-id="e659c-121">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="e659c-122">Das Cmdlet verwendet einen integrierten Algorithmus, um die beste Platzierung für die Protokoll-und Datendateien zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e659c-122">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="e659c-123">Der Algorithmus funktioniert nur für eigenständige SQL Server-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="e659c-123">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="e659c-124">Führen Sie **install-CsDatabase** mit dem Parameter DatabasePaths aus.</span><span class="sxs-lookup"><span data-stu-id="e659c-124">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="e659c-125">Der integrierte Algorithmus zum Optimieren der Speicherorte von Protokoll-und Datendateien wird nicht verwendet, wenn der Parameter DatabasePaths definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e659c-125">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="e659c-126">Mithilfe dieses Parameters können Sie die Speicherorte definieren, an denen Protokoll-und Datendateien bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e659c-126">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="e659c-127">Führen Sie **install-CsDatabase** mit UseDefaultSqlPaths aus.</span><span class="sxs-lookup"><span data-stu-id="e659c-127">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="e659c-128">Bei dieser Option wird nicht der integrierte Algorithmus zum Optimieren der Speicherorte von Protokollen und Datendateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="e659c-128">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="e659c-129">Protokoll-und Datendatei werden gemäß den vom SQL Server Administrator festgelegten Standardeinstellungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e659c-129">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="e659c-130">Diese Pfade werden normalerweise zum Zweck der automatischen Verwaltung von Protokoll-und Datendateien auf der SQL Server im Voraus festgelegt und sind nicht mit dem Setup von lync Server 2013 verknüpft.</span><span class="sxs-lookup"><span data-stu-id="e659c-130">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="e659c-131">Der Parameter DatabasePathMap kann auch verwendet werden, um explizit einen Speicherort für jede Datenbank und die zugehörige Protokolldatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e659c-131">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="e659c-132">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren des SQL Server zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="e659c-132">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="e659c-133">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="e659c-133">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="e659c-134">Ausführliche Informationen finden Sie unter [Deployment Permissions for SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e659c-134">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="e659c-135">Öffnen Sie die lync Server 2013 Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="e659c-135">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="e659c-136">Wenn Sie die Ausführungsrichtlinie für Windows PowerShell nicht angepasst haben, müssen Sie die Richtlinie so anpassen, dass Windows PowerShell Skripts ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e659c-136">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="e659c-137">Ausführliche Informationen finden Sie unter "Überprüfen der Ausführungsrichtlinie" unter [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .</span><span class="sxs-lookup"><span data-stu-id="e659c-137">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="e659c-138">Verwenden Sie das Cmdlet **install-CsDatabase** , um den zentralen Verwaltungsspeicher zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e659c-138">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e659c-139">Der Parameter Report ist optional, aber nützlich, wenn Sie den Installationsvorgang dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="e659c-139">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="e659c-140">**Install-CsDatabase – DatabasePaths** kann bis zu sechs Pfadparameter verwenden, wobei jeder die Pfade für die Laufwerke definiert, die in SQL Server Daten-und Protokolldatei Platzierung definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e659c-140">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="e659c-141">Durch die logischen Regeln der Datenbankkonfiguration in lync Server 2013 werden Laufwerke in Buckets mit zwei, vier oder sechs analysiert.</span><span class="sxs-lookup"><span data-stu-id="e659c-141">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="e659c-142">Abhängig von der SQL Server Konfiguration und der Anzahl der Buckets werden zwei Pfade, vier Pfade oder sechs Pfade bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e659c-142">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="e659c-143">Wenn Sie drei Laufwerke haben, wird das Protokoll Priorität erhalten und die Datendateien werden nach verteilt.</span><span class="sxs-lookup"><span data-stu-id="e659c-143">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="e659c-144">Ein Beispiel für einen SQL Server basierten Server, der mit sechs Laufwerken konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e659c-144">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="e659c-145">Wenn die Datenbankinstallation abgeschlossen ist, können Sie lync Server 2013 Verwaltungsshell schließen oder mit der Installation der lync Server 2013 konfigurierten Datenbanken fortfahren, die im Topologie-Generator definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e659c-145">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="e659c-146">So konfigurieren Sie die konfigurierten Datenbanken für die SQL Server Topologie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e659c-146">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="e659c-147">Zum Installieren des Topologie-Generators für lync Server 2013 konfigurierte Datenbanken muss der lync Server 2013 Administrator die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e659c-147">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="e659c-148">Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e659c-148">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="e659c-149">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="e659c-149">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="e659c-150">Siehe das Thema, [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e659c-150">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e659c-151">Um die SQL Server basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe "Sysadmins" (oder gleichwertig) auf dem Server ist, auf dem SQL Server ausgeführt wird und die zentrale Verwaltungsserverrolle innehat.</span><span class="sxs-lookup"><span data-stu-id="e659c-151">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="e659c-152">Dies ist besonders wichtig, um nach zusätzlichen lync Server 2013 Pools zu suchen, die SQL Server Datenbankinstallation oder-Konfiguration erfordern.</span><span class="sxs-lookup"><span data-stu-id="e659c-152">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="e659c-153">Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle jedoch von pool01 gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e659c-153">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="e659c-154">Die SQL Server Gruppe "sysadmin" (oder gleichwertig) muss über Berechtigungen für beide SQL Server basierte Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="e659c-154">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="e659c-155">Öffnen Sie lync Server 2013 Verwaltungsshell, falls Sie noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="e659c-155">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="e659c-156">Verwenden Sie das Cmdlet **install-CsDatabase** , um die konfigurierten Datenbanken des Topologie-Generators zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e659c-156">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="e659c-157">Der Parameter Report ist optional, aber nützlich, wenn Sie den Installationsvorgang dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="e659c-157">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="e659c-158">Wenn die Datenbankinstallation abgeschlossen ist, schließen Sie lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e659c-158">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="e659c-159">So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der SQL Server Topologie mithilfe des DatabasePathMap-Parameters</span><span class="sxs-lookup"><span data-stu-id="e659c-159">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="e659c-160">Um Datenbanken für lync Server 2013 zu installieren, muss der lync Server-Administrator die Pfade erstellen und die Datenbankendateien und Protokolldateien entsprechend einem vordefinierten Satz von Regeln bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e659c-160">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="e659c-161">Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server basierten Server an.</span><span class="sxs-lookup"><span data-stu-id="e659c-161">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="e659c-162">Siehe das Thema, [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e659c-162">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e659c-163">Um die SQL Server basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe "Sysadmins" (oder gleichwertig) auf dem Server ist, auf dem SQL Server ausgeführt wird und die zentrale Verwaltungsserverrolle innehat.</span><span class="sxs-lookup"><span data-stu-id="e659c-163">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="e659c-164">Dies ist besonders wichtig, um nach zusätzlichen lync Server Pools zu suchen, die SQL Server Datenbankinstallation oder-Konfiguration erfordern.</span><span class="sxs-lookup"><span data-stu-id="e659c-164">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="e659c-165">Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle jedoch von pool01 gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e659c-165">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="e659c-166">Die SQL Server Gruppe "sysadmin" (oder gleichwertig) muss über Berechtigungen für beide SQL Server basierte Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="e659c-166">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="e659c-167">Öffnen Sie lync Server-Verwaltungsshell, wenn es noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="e659c-167">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="e659c-168">Verwenden Sie das Cmdlet **install-CsDatabase** mit dem Parameter DatabasePathMap und einer PowerShell-Hashtabelle, um die konfigurierten Datenbanken des Topologie-Generators zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e659c-168">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="e659c-169">Im Beispielcode können die für die Datenbanken definierten Pfade auf granulare Weise mithilfe des Parameters – DatabasePathMap und einer definierten Hashtabelle wie folgt bestimmt werden (das Beispiel verwendet "c: \\ CSData" für alle Datenbankdateien (MDF) und "c: \\ CSLogFiles" für alle Protokolldateien (LDF).</span><span class="sxs-lookup"><span data-stu-id="e659c-169">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="e659c-170">Der Ordner wird bei Bedarf von install-CsDatabase erstellt:</span><span class="sxs-lookup"><span data-stu-id="e659c-170">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
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
    ```
6.  <span data-ttu-id="e659c-171">Da die Datenbank-und Protokolldateien explizit mit ihrem Speicherort auf dem Zieldatenbankserver benannt werden, können Sie bestimmte Speicherorte für die tatsächliche Datenbank und den Protokollspeicherort der einzelnen Diensttypen definieren.</span><span class="sxs-lookup"><span data-stu-id="e659c-171">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="e659c-172">Im folgenden Beispiel werden Datenbanken für jeden bestimmten Diensttyp auf separaten Datenträgern und zugeordneten Protokolldateien auf einem anderen platziert.</span><span class="sxs-lookup"><span data-stu-id="e659c-172">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="e659c-173">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e659c-173">For example:</span></span>
    
      - <span data-ttu-id="e659c-174">Alle RTC-Datenbanken in "D: \\ RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="e659c-174">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="e659c-175">Alle RTC-Protokolldateien in "E: \\ RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="e659c-175">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="e659c-176">Alle Anwendungsspeicher Datenbanken in "F: \\ CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="e659c-176">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="e659c-177">Alle Anwendungsspeicher Protokolle in "G: \\ CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="e659c-177">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="e659c-178">Alle Datenbanken der Reaktionsgruppen Speicherung in "H: \\ RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="e659c-178">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="e659c-179">Alle Reaktionsgruppen Speicherprotokolle in "I: \\ RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="e659c-179">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="e659c-180">Alle Adressbuchspeicher-Datenbanken in "J: \\ ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="e659c-180">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="e659c-181">Alle Protokolldateien des Adressbuch Speichers in "K: \\ ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="e659c-181">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="e659c-182">Alle Archivierungsspeicher Datenbanken in "L: \\ ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="e659c-182">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="e659c-183">Alle Archivierungsspeicher Protokolle in "M: \\ ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="e659c-183">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="e659c-184">Alle Überwachungsspeicher Datenbanken in "N: \\ MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="e659c-184">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="e659c-185">Alle Überwachungsspeicher-Protokolldateien in "O: \\ MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="e659c-185">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
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
    
    <span data-ttu-id="e659c-186">Mithilfe des Parameters – DatabasePathMap können Sie eine beliebige Kombination aus logischem Laufwerkbuchstaben definieren, die die beste Lösung für Ihre SQL Server Leistungs-und Platzierungs Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e659c-186">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="e659c-187">Wenn Sie die Datenbankdateien und Protokolldateien mithilfe der **DatabasePathMap** -Methode konfigurieren, müssen Sie bei Verwendung des Topologie-Generators eine geringfügige Änderung an Ihrem normalen Prozess vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e659c-187">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="e659c-188">In der Regel definieren Sie die Auswahl der Topologie, veröffentlichen die Topologie und wählen, um die Datenbankauswahl bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e659c-188">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="e659c-189">Wenn Sie **DatabasePathMap** verwendet haben, haben Sie bereits den dritten Teil des Topologie-Generator-Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e659c-189">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="e659c-190">Wenn Sie vor dem Ausführen des Topologie-Generators einen vollständig konfigurierten Datenbankserver haben, würden Sie trotzdem alle Ihre Serverrollen und Optionen definieren, aber deaktivieren Sie die Option zum Erstellen der Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="e659c-190">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

