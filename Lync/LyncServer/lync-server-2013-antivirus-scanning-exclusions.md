---
title: 'Lync Server 2013: Ausnahmen in Virenschutzprogrammen'
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
ms.openlocfilehash: 90847830d9f2586e0d111846f2867400c52fc940
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="3175e-102">Ausnahmen in Virenschutzprogrammen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3175e-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3175e-103">_**Letztes Änderungsdatum des Themas:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="3175e-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="3175e-104">Wenn Sie sicherstellen möchten, dass der Virenscanner den Betrieb von lync Server 2013 nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden lync Server 2013-Server oder die Serverrolle ausschließen, auf der Sie einen Antivirus-Scanner ausführen.</span><span class="sxs-lookup"><span data-stu-id="3175e-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="3175e-105">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="3175e-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3175e-106">Die nachstehend aufgeführten Ordner-und Dateispeicherorte sind die Standardspeicherorte für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3175e-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="3175e-107">Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="3175e-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3175e-108">Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.</span><span class="sxs-lookup"><span data-stu-id="3175e-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="3175e-109">Lync Server 2013-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="3175e-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="3175e-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="3175e-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="3175e-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="3175e-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="3175e-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="3175e-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="3175e-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="3175e-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="3175e-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="3175e-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="3175e-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="3175e-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="3175e-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="3175e-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="3175e-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="3175e-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="3175e-133">Windows Fabric-Hostdienst-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="3175e-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="3175e-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="3175e-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="3175e-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="3175e-136">FabricHost.exe</span></span>

  - <span data-ttu-id="3175e-137">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="3175e-137">IIS processes:</span></span>
    
      - <span data-ttu-id="3175e-138">% systemroot\\%\\System32\\inetsrv w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="3175e-139">% systemroot\\%\\syswow64\\inetsrv w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="3175e-140">SQL Server Back-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="3175e-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="3175e-141">% Programme%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="3175e-142">% Programme%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\Report\\Server\\bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="3175e-143">% Programme%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\bin\\MSMDSrv. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="3175e-144">SQL Server Front-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="3175e-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="3175e-145">% Programme%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="3175e-146">% Programme%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="3175e-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="3175e-147">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="3175e-147">Directories and files:</span></span>
    
      - <span data-ttu-id="3175e-148">% systemroot\\%\\System32-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="3175e-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="3175e-149">% systemroot\\% syswow64\\-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="3175e-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="3175e-150">% systemroot\\%\\Microsoft.net\\Assembly\_GAC MSIL</span><span class="sxs-lookup"><span data-stu-id="3175e-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="3175e-151">% Programme%\\Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3175e-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="3175e-152">% Programme%\\Common Files\\Microsoft lync Server 2013\\Watcher-Knoten</span><span class="sxs-lookup"><span data-stu-id="3175e-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="3175e-153">% Programme%\\allgemeine Dateien\\Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3175e-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="3175e-154">% SystemDrive\\% RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="3175e-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="3175e-155">Dateifreigabespeicher (im Topologie-Generator angegeben).</span><span class="sxs-lookup"><span data-stu-id="3175e-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="3175e-156">Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="3175e-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="3175e-157">SQL Server-Daten-und-Protokolldateien, einschließlich derer für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="3175e-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="3175e-158">In Topology Builder können Datenbank-und Protokolldateien angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3175e-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="3175e-159">Details zu den Daten-und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter [SQL Server-Daten-und Protokolldatei Platzierung für lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3175e-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3175e-160">SQL Server-Daten-und-Protokolldateien, einschließlich derer für die Front-End-Datenbank, den lync-Store und den RtcDatabase-Speicher.</span><span class="sxs-lookup"><span data-stu-id="3175e-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="3175e-161">Sie befinden sich normalerweise unter\\% LokalesLaufwerk% CSData.</span><span class="sxs-lookup"><span data-stu-id="3175e-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

