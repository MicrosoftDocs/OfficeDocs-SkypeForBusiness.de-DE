---
title: Virenschutzprogramm-Ausschlüsse für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Übersicht über Antivirusscanner Interoperation mit Skype für Business Server 2015.
ms.openlocfilehash: 054ed03146964de7ec0621138186e3c41843c236
ms.sourcegitcommit: 1cb8ab7d1e3debb84f051be404403e4a116ee741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="2cc41-103">Virenschutzprogramm-Ausschlüsse für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2cc41-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2cc41-104">Übersicht über Antivirusscanner Interoperation mit Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2cc41-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span>

<span data-ttu-id="2cc41-105">Dieser Artikel enthält Empfehlungen, die dazu beitragen können ein Administrator die Ursache des potenzielle instabil auf einem Computer, auf dem eine unterstützte Version von Microsoft Windows ausgeführt wird, wenn sie mithilfe von Antivirensoftware in einer Active Directory-Domäne verwendet wird Umgebung oder in einer verwalteten geschäftsumgebung.</span><span class="sxs-lookup"><span data-stu-id="2cc41-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="2cc41-106">Es wird empfohlen, dass Sie diese Verfahren zum Auswerten von einem System vorübergehend anwenden.</span><span class="sxs-lookup"><span data-stu-id="2cc41-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="2cc41-107">Wenn die Systemleistung oder Stabilität durch die Empfehlungen deutlich verbessert, die in diesem Artikel vorgenommen werden, Hersteller Ihrer Antivirensoftware Anweisungen oder eine aktualisierte Version der Software.</span><span class="sxs-lookup"><span data-stu-id="2cc41-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="2cc41-108">Dieser Artikel enthält Informationen, die zeigt, wie untere Sicherheitseinstellungen Hilfe oder Sicherheitsfeatures auf einem Computer vorübergehend zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2cc41-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="2cc41-109">Sie können diese Änderungen zu verstehen, die Art der eines bestimmten Problems vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2cc41-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="2cc41-110">Bevor Sie diese Änderungen vornehmen, wird empfohlen, dass Sie bewerten die Risiken, die diese Lösung in Ihrer speziellen Umgebung implementieren zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2cc41-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="2cc41-111">Wenn Sie diese Lösung implementieren, führen Sie entsprechenden Maßnahmen zum Schutz von dem Computer für die Dateien, die nicht mehr von Antivirensoftware gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="2cc41-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>
  
<span data-ttu-id="2cc41-112">Um sicherzustellen, dass die Antivirusscanner nicht mit dem Betrieb des Skype für Business Server 2015 beeinträchtigt, müssen Sie bestimmte Prozesse und Verzeichnisse ausschließen, für jeden Skype für Business Server 2015 Server oder Serverrolle auf dem Sie einen Antivirenscanner ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2cc41-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="2cc41-113">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="2cc41-113">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="2cc41-114">Unten aufgeführten sind Ordner und Datei die Standardspeicherorte für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2cc41-114">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="2cc41-115">Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="2cc41-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2cc41-116">Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.</span><span class="sxs-lookup"><span data-stu-id="2cc41-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="2cc41-117">Skype für Business Server 2015 Prozesse:</span><span class="sxs-lookup"><span data-stu-id="2cc41-117">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="2cc41-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-118">ABServer.exe</span></span>
    
  - <span data-ttu-id="2cc41-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-119">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-120">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-121">ChannelService.exe</span></span>
    
  - <span data-ttu-id="2cc41-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-122">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="2cc41-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-123">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="2cc41-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-124">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-125">DataProxy.exe</span></span>
    
  - <span data-ttu-id="2cc41-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-126">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="2cc41-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-127">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="2cc41-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-128">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-129">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-129">LysSvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-130">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-130">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="2cc41-131">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-131">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-132">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-132">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-133">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-133">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="2cc41-134">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-134">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="2cc41-135">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-135">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="2cc41-136">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-136">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="2cc41-137">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-137">RtcHost.exe</span></span>
    
  - <span data-ttu-id="2cc41-138">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-138">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="2cc41-139">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-139">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="2cc41-140">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-140">XmppTGW.exe</span></span>
    
- <span data-ttu-id="2cc41-141">Windows Fabric-Hostdienst-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="2cc41-141">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="2cc41-142">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-142">Fabric.exe</span></span>
    
  - <span data-ttu-id="2cc41-143">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-143">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="2cc41-144">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-144">FabricHost.exe</span></span>
    
- <span data-ttu-id="2cc41-145">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="2cc41-145">IIS processes:</span></span>
    
  - <span data-ttu-id="2cc41-146">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-146">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="2cc41-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="2cc41-148">SQL Server Back-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="2cc41-148">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2cc41-149">Beachten Sie, dass diese Pfade nur für diese SQL Server-Version gelten.</span><span class="sxs-lookup"><span data-stu-id="2cc41-149">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="2cc41-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="2cc41-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="2cc41-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="2cc41-153">SQL Server Front-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="2cc41-153">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="2cc41-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="2cc41-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="2cc41-156">Standard Edition-Installationsinstanz „rtc“</span><span class="sxs-lookup"><span data-stu-id="2cc41-156">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="2cc41-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2cc41-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="2cc41-158">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="2cc41-158">Directories and files:</span></span>
    
  - <span data-ttu-id="2cc41-159">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="2cc41-159">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="2cc41-160">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="2cc41-160">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="2cc41-161">%SystemRoot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="2cc41-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="2cc41-162">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2cc41-162">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="2cc41-163">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="2cc41-163">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="2cc41-164">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2cc41-164">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="2cc41-165">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2cc41-165">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="2cc41-166">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="2cc41-166">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="2cc41-p105">Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="2cc41-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="2cc41-169">SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Back-End-Datenbank, Benutzerspeicher, Archivierungsspeicher, Speicher für Überwachung und Anwendungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="2cc41-169">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="2cc41-170">Datenbank-und Protokolldateien können im Topologie-Generator angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2cc41-170">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="2cc41-171">Ausführliche Informationen zu den Dateien Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen finden Sie unter [SQL Server-Daten und Platzieren der Protokolldatei](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2cc41-171">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="2cc41-172">SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Front-End-Datenbank, Skype für Business Store und RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="2cc41-172">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="2cc41-173">Sie sind normalerweise unter % localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="2cc41-173">They are normally under %localdrive%\CSData.</span></span>
    

