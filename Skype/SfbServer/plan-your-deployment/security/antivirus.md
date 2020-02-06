---
title: Ausschlüsse für Antivirus-Scans für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Übersicht über die Interoperabilität des Antivirus-Scanners mit Skype for Business Server.
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815693"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="6f7ab-103">Ausschlüsse für Antivirus-Scans für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6f7ab-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="6f7ab-104">Übersicht über die Interoperabilität des Antivirus-Scanners mit Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="6f7ab-105">Um sicherzustellen, dass der Virenscanner den Betrieb von Skype for Business Server nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden Skype for Business Server-Server oder jede Serverrolle ausschließen, auf der Sie einen Antivirus-Scanner ausführen.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="6f7ab-106">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="6f7ab-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="6f7ab-107">Die nachstehend aufgeführten Ordner-und Dateispeicherorte sind die Standardspeicherorte für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="6f7ab-108">Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f7ab-109">Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="6f7ab-110">Skype for Business Server-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="6f7ab-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="6f7ab-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-111">ABServer.exe</span></span>

  - <span data-ttu-id="6f7ab-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="6f7ab-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="6f7ab-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-114">ChannelService.exe</span></span>

  - <span data-ttu-id="6f7ab-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="6f7ab-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="6f7ab-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="6f7ab-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-118">DataProxy.exe</span></span>

  - <span data-ttu-id="6f7ab-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="6f7ab-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="6f7ab-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="6f7ab-122">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="6f7ab-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-123">LysSvc.exe</span></span>

  - <span data-ttu-id="6f7ab-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6f7ab-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="6f7ab-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="6f7ab-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="6f7ab-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="6f7ab-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6f7ab-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="6f7ab-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-131">RtcHost.exe</span></span>

  - <span data-ttu-id="6f7ab-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="6f7ab-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="6f7ab-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-134">XmppTGW.exe</span></span>

- <span data-ttu-id="6f7ab-135">Windows Fabric-Hostdienst-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="6f7ab-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="6f7ab-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-136">Fabric.exe</span></span>

  - <span data-ttu-id="6f7ab-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="6f7ab-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-138">FabricHost.exe</span></span>

- <span data-ttu-id="6f7ab-139">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="6f7ab-139">IIS processes:</span></span>

  - <span data-ttu-id="6f7ab-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="6f7ab-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="6f7ab-142">SQL Server Back-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="6f7ab-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f7ab-143">Beachten Sie, dass diese Pfade nur für diese SQL Server-Version gelten.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="6f7ab-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6f7ab-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="6f7ab-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="6f7ab-147">SQL Server Front-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="6f7ab-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="6f7ab-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6f7ab-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6f7ab-150">Standard Edition-Installationsinstanz „rtc“</span><span class="sxs-lookup"><span data-stu-id="6f7ab-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="6f7ab-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6f7ab-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="6f7ab-152">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="6f7ab-152">Directories and files:</span></span>

  - <span data-ttu-id="6f7ab-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6f7ab-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="6f7ab-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6f7ab-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="6f7ab-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="6f7ab-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f7ab-156">Beachten Sie, dass diese Pfade speziell für die Skype for Business Server-Version sind.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="6f7ab-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f7ab-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6f7ab-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="6f7ab-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="6f7ab-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f7ab-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6f7ab-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6f7ab-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="6f7ab-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="6f7ab-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="6f7ab-p103">Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="6f7ab-p104">SQL Server-Daten und -Protokolldateien, u. a. für die Back-End-Datenbank, den Benutzer-, Archivierungs-, Überwachungs- und den Anwendungsspeicher. Datenbank- und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="6f7ab-167">SQL Server-Daten-und-Protokolldateien, einschließlich derer für die Front-End-Datenbank, den Skype for Business-Store und den RtcDatabase-Store.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="6f7ab-168">Sie befinden sich normalerweise unter%LocalDrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="6f7ab-168">They are normally under %localdrive%\CSData.</span></span>


