---
title: 'Lync Server 2013: Ausschlüsse für Antivirusscans'
description: 'Lync Server 2013: Ausschlüsse für Antivirusscans.'
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
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561911"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="eff8d-103">Antivirus-Scan Ausschlüsse für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eff8d-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eff8d-104">_**Letztes Änderungsstand des Themas:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="eff8d-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="eff8d-105">Um sicherzustellen, dass der Antivirus-Scanner den Betrieb von lync Server 2013 nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden lync Server 2013 Server oder jede Serverrolle ausschließen, auf dem Sie einen Antivirenprogramm ausführen.</span><span class="sxs-lookup"><span data-stu-id="eff8d-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="eff8d-106">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="eff8d-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eff8d-107">Unten aufgeführte Ordner-und Dateispeicherorte sind die Standardspeicherorte für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff8d-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="eff8d-108">Schließen Sie für alle Standorte, für die Sie die Standardeinstellung nicht verwendet haben, die für Ihre Organisation angegebenen Speicherorte anstelle der in diesem Thema angegebenen Standardspeicherorte aus.</span><span class="sxs-lookup"><span data-stu-id="eff8d-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eff8d-109">Beachten Sie, dass einige Antivirus-Programme möglicherweise absolute, keine relativen Pfade für Ihre Ausschlussliste benötigen.</span><span class="sxs-lookup"><span data-stu-id="eff8d-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="eff8d-110">Lync Server 2013 Prozesse:</span><span class="sxs-lookup"><span data-stu-id="eff8d-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="eff8d-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="eff8d-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="eff8d-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="eff8d-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="eff8d-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="eff8d-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="eff8d-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="eff8d-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="eff8d-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="eff8d-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="eff8d-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="eff8d-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="eff8d-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="eff8d-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="eff8d-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="eff8d-134">Windows Fabric-Host Dienstprozesse:</span><span class="sxs-lookup"><span data-stu-id="eff8d-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="eff8d-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="eff8d-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="eff8d-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-137">FabricHost.exe</span></span>

  - <span data-ttu-id="eff8d-138">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="eff8d-138">IIS processes:</span></span>
    
      - <span data-ttu-id="eff8d-139">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="eff8d-140">% systemroot% \\ syswow64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="eff8d-141">SQL Server Back-End Prozesse:</span><span class="sxs-lookup"><span data-stu-id="eff8d-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="eff8d-142">% Programme% \\ Microsoft SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="eff8d-143">% Programme% \\ Microsoft SQL Server \\ MSRS11. MSSQLSERVER \\ Reporting Services \\ Report \\ Container bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="eff8d-144">% Programme% \\ Microsoft SQL Server \\ MSAS11. OLAP-Schacht "MSSQLSERVER" \\ \\ \\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="eff8d-145">SQL Server Front-End Prozesse:</span><span class="sxs-lookup"><span data-stu-id="eff8d-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="eff8d-146">% Programme% \\ Microsoft SQL Server \\ MSSQL11. LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="eff8d-147">% Programme% \\ Microsoft SQL Server \\ MSSQL11. RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="eff8d-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="eff8d-148">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="eff8d-148">Directories and files:</span></span>
    
      - <span data-ttu-id="eff8d-149">% systemroot% \\ system32- \\ Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="eff8d-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="eff8d-150">% systemroot-% \\ syswow64- \\ Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="eff8d-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="eff8d-151">% systemroot% \\ Microsoft.net- \\ Assembly \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="eff8d-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="eff8d-152">% Programme% \\ Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eff8d-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="eff8d-153">% Programme% \\ Allgemeine Dateien \\ Microsoft lync Server 2013 \\ Watcher-Knoten</span><span class="sxs-lookup"><span data-stu-id="eff8d-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="eff8d-154">% Programme% \\ Allgemeine Dateien \\ Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eff8d-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="eff8d-155">% System Drive% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="eff8d-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="eff8d-156">Dateifreigabe Speicher (im Topologie-Generator angegeben).</span><span class="sxs-lookup"><span data-stu-id="eff8d-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="eff8d-157">Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="eff8d-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="eff8d-158">SQL Server von Daten-und Protokolldateien, einschließlich derer für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="eff8d-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="eff8d-159">Datenbank-und Protokolldateien können im Topologie-Generator angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eff8d-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="eff8d-160">Ausführliche Informationen zu den Daten und Protokolldateien für jede Datenbank, einschließlich der Standardnamen, finden Sie unter [SQL Server Data and Log File Placement for lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="eff8d-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="eff8d-161">SQL Server von Daten-und Protokolldateien, einschließlich der für die Front-End-Datenbank, lync Store und RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="eff8d-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="eff8d-162">Sie befinden sich normalerweise unter% LokalesLaufwerk% \\ CSData.</span><span class="sxs-lookup"><span data-stu-id="eff8d-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

