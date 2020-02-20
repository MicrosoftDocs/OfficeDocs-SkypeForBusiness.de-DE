---
title: 'Lync Server 2013: Ausschlüsse für Antivirusscans'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3a67d7777017c004b0cfcc59a46cd27baf5c209
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="f8ff4-102">Antivirus-Scan Ausschlüsse für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8ff4-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8ff4-103">_**Letztes Änderungsstand des Themas:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="f8ff4-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="f8ff4-104">Um sicherzustellen, dass der Antivirus-Scanner den Betrieb von lync Server 2013 nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden lync Server 2013 Server oder jede Serverrolle ausschließen, auf dem Sie einen Antivirenprogramm ausführen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="f8ff4-105">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8ff4-106">Unten aufgeführte Ordner-und Dateispeicherorte sind die Standardspeicherorte für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="f8ff4-107">Schließen Sie für alle Standorte, für die Sie die Standardeinstellung nicht verwendet haben, die für Ihre Organisation angegebenen Speicherorte anstelle der in diesem Thema angegebenen Standardspeicherorte aus.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8ff4-108">Beachten Sie, dass einige Antivirus-Programme möglicherweise absolute, keine relativen Pfade für Ihre Ausschlussliste benötigen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="f8ff4-109">Lync Server 2013 Prozesse:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="f8ff4-110">ABServer. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="f8ff4-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-112">ASMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-113">AVMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-114">Channelservice. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="f8ff4-115">ClsAgent. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="f8ff4-116">ComplianceService. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="f8ff4-117">DataMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-118">Dataproxy. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="f8ff4-119">FileTransferAgent. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="f8ff4-120">IMMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-121">LysSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-122">MasterReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f8ff4-123">MediaRelaySvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-124">MediationServerSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-125">MRASSvc. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="f8ff4-126">OcsAppServerHost. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="f8ff4-127">ReplicaReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f8ff4-128">ReplicationApp. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="f8ff4-129">RtcHost. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="f8ff4-130">RtcSrv. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="f8ff4-131">XmppProxy. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="f8ff4-132">XmppTGW. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="f8ff4-133">Windows Fabric-Host Dienstprozesse:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="f8ff4-134">Fabric. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="f8ff4-135">FabricDCA. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="f8ff4-136">FabricHost. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-136">FabricHost.exe</span></span>

  - <span data-ttu-id="f8ff4-137">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-137">IIS processes:</span></span>
    
      - <span data-ttu-id="f8ff4-138">% systemroot\\%\\System32\\inetsrv w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="f8ff4-139">% systemroot\\%\\syswow64\\inetsrv w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="f8ff4-140">SQL Server Back-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="f8ff4-141">% Programme%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f8ff4-142">% Programme%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\Report\\Container\\bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="f8ff4-143">% Programme%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\bin\\MSMDSrv. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="f8ff4-144">SQL Server Front-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="f8ff4-145">% Programme%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f8ff4-146">% Programme%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="f8ff4-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="f8ff4-147">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-147">Directories and files:</span></span>
    
      - <span data-ttu-id="f8ff4-148">% systemroot\\%\\System32-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="f8ff4-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="f8ff4-149">% systemroot\\-%\\syswow64-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="f8ff4-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="f8ff4-150">% systemroot\\%\\Microsoft.net\\-\_Assembly GAC MSIL</span><span class="sxs-lookup"><span data-stu-id="f8ff4-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="f8ff4-151">% Programme%\\Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8ff4-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f8ff4-152">% Programme%\\allgemeine Dateien\\Microsoft lync Server 2013\\Watcher-Knoten</span><span class="sxs-lookup"><span data-stu-id="f8ff4-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="f8ff4-153">% Programme%\\allgemeine Dateien\\Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8ff4-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f8ff4-154">% System Drive\\% RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="f8ff4-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="f8ff4-155">Dateifreigabe Speicher (im Topologie-Generator angegeben).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="f8ff4-156">Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="f8ff4-157">SQL Server von Daten-und Protokolldateien, einschließlich derer für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="f8ff4-158">Datenbank-und Protokolldateien können im Topologie-Generator angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="f8ff4-159">Ausführliche Informationen zu den Daten und Protokolldateien für jede Datenbank, einschließlich der Standardnamen, finden Sie unter [SQL Server Data and Log File Placement for lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f8ff4-160">SQL Server von Daten-und Protokolldateien, einschließlich der für die Front-End-Datenbank, lync Store und RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="f8ff4-161">Sie befinden sich normalerweise unter\\% LokalesLaufwerk% CSData.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

