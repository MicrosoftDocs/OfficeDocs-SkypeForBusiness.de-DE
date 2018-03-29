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
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="df7f1-103">Virenschutzprogramm-Ausschlüsse für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="df7f1-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="df7f1-104">Übersicht über Antivirusscanner Interoperation mit Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="df7f1-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="df7f1-105">Um sicherzustellen, dass die Antivirusscanner nicht mit dem Betrieb des Skype für Business Server 2015 beeinträchtigt, müssen Sie bestimmte Prozesse und Verzeichnisse ausschließen, für jeden Skype für Business Server 2015 Server oder Serverrolle auf dem Sie einen Antivirenscanner ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="df7f1-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="df7f1-106">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="df7f1-106">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="df7f1-107">Unten aufgeführten sind Ordner und Datei die Standardspeicherorte für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="df7f1-107">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="df7f1-108">Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="df7f1-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="df7f1-109">Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.</span><span class="sxs-lookup"><span data-stu-id="df7f1-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="df7f1-110">Skype für Business Server 2015 Prozesse:</span><span class="sxs-lookup"><span data-stu-id="df7f1-110">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="df7f1-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-111">ABServer.exe</span></span>
    
  - <span data-ttu-id="df7f1-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-112">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-113">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-114">ChannelService.exe</span></span>
    
  - <span data-ttu-id="df7f1-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-115">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="df7f1-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-116">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="df7f1-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-117">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-118">DataProxy.exe</span></span>
    
  - <span data-ttu-id="df7f1-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-119">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="df7f1-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-120">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="df7f1-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-121">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-122">LysSvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-123">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="df7f1-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-124">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-125">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-126">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="df7f1-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-127">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="df7f1-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-128">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="df7f1-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-129">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="df7f1-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-130">RtcHost.exe</span></span>
    
  - <span data-ttu-id="df7f1-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-131">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="df7f1-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-132">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="df7f1-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-133">XmppTGW.exe</span></span>
    
- <span data-ttu-id="df7f1-134">Windows Fabric-Hostdienst-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="df7f1-134">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="df7f1-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-135">Fabric.exe</span></span>
    
  - <span data-ttu-id="df7f1-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-136">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="df7f1-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-137">FabricHost.exe</span></span>
    
- <span data-ttu-id="df7f1-138">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="df7f1-138">IIS processes:</span></span>
    
  - <span data-ttu-id="df7f1-139">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-139">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="df7f1-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="df7f1-141">SQL Server Back-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="df7f1-141">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df7f1-142">Beachten Sie, dass diese Pfade nur für diese SQL Server-Version gelten.</span><span class="sxs-lookup"><span data-stu-id="df7f1-142">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="df7f1-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="df7f1-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="df7f1-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="df7f1-146">SQL Server Front-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="df7f1-146">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="df7f1-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="df7f1-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="df7f1-149">Standard Edition-Installationsinstanz „rtc“</span><span class="sxs-lookup"><span data-stu-id="df7f1-149">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="df7f1-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="df7f1-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="df7f1-151">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="df7f1-151">Directories and files:</span></span>
    
  - <span data-ttu-id="df7f1-152">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="df7f1-152">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="df7f1-153">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="df7f1-153">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="df7f1-154">%SystemRoot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="df7f1-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="df7f1-155">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="df7f1-155">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="df7f1-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="df7f1-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="df7f1-157">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="df7f1-157">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="df7f1-158">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="df7f1-158">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="df7f1-159">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="df7f1-159">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="df7f1-p103">Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="df7f1-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="df7f1-162">SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Back-End-Datenbank, Benutzerspeicher, Archivierungsspeicher, Speicher für Überwachung und Anwendungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="df7f1-162">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="df7f1-163">Datenbank-und Protokolldateien können im Topologie-Generator angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="df7f1-163">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="df7f1-164">Ausführliche Informationen zu den Dateien Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen finden Sie unter [SQL Server-Daten und Platzieren der Protokolldatei](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="df7f1-164">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="df7f1-165">SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Front-End-Datenbank, Skype für Business Store und RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="df7f1-165">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="df7f1-166">Sie sind normalerweise unter % localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="df7f1-166">They are normally under %localdrive%\CSData.</span></span>
    

