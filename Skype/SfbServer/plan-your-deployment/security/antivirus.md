---
title: Ausschlüsse für Antivirus-Scans für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Übersicht über die Interoperabilität des Antivirus-Scanners mit Skype for Business Server.
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296973"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="4615a-103">Ausschlüsse für Antivirus-Scans für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4615a-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="4615a-104">Übersicht über die Interoperabilität des Antivirus-Scanners mit Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4615a-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="4615a-105">Dieser Artikel enthält Empfehlungen, die einem Administrator helfen können, die Ursache einer potenziellen Instabilität auf einem Computer zu ermitteln, auf dem eine unterstützte Version von Microsoft Windows ausgeführt wird, wenn diese mit Antivirensoftware in einer Active Directory-Domäne verwendet wird. Umgebung oder in einer verwalteten Unternehmensumgebung.</span><span class="sxs-lookup"><span data-stu-id="4615a-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="4615a-106">Wir empfehlen, diese Verfahren vorübergehend zur Auswertung eines Systems anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4615a-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="4615a-107">Wenn sich die Leistung oder Stabilität Ihres Systems durch die Empfehlungen in diesem Artikel verbessert hat, wenden Sie sich an den Hersteller Ihrer Antivirensoftware, um Anweisungen oder eine aktualisierte Version der Antivirensoftware zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4615a-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="4615a-108">Dieser Artikel enthält Informationen, die zeigen, wie Sie die Sicherheitseinstellungen verringern oder wie Sie Sicherheitsfunktionen vorübergehend auf einem Computer deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="4615a-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="4615a-109">Sie können diese Änderungen vornehmen, um die Art eines bestimmten Problems zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="4615a-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="4615a-110">Bevor Sie diese Änderungen vornehmen, empfehlen wir, dass Sie die Risiken bewerten, die mit der Implementierung dieser Problemumgehung in ihrer jeweiligen Umgebung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="4615a-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="4615a-111">Wenn Sie diese Problemumgehung implementieren, führen Sie alle geeigneten zusätzlichen Schritte aus, um den Computer für die Dateien zu schützen, die von Ihrer Antivirensoftware nicht mehr gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="4615a-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="4615a-112">Um sicherzustellen, dass der Virenscanner den Betrieb von Skype for Business Server nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden Skype for Business Server-Server oder jede Serverrolle ausschließen, auf der Sie einen Antivirus-Scanner ausführen.</span><span class="sxs-lookup"><span data-stu-id="4615a-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="4615a-113">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="4615a-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="4615a-114">Die nachstehend aufgeführten Ordner-und Dateispeicherorte sind die Standardspeicherorte für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4615a-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="4615a-115">Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4615a-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4615a-116">Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.</span><span class="sxs-lookup"><span data-stu-id="4615a-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="4615a-117">Skype for Business Server-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="4615a-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="4615a-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-118">ABServer.exe</span></span>

  - <span data-ttu-id="4615a-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="4615a-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="4615a-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-121">ChannelService.exe</span></span>

  - <span data-ttu-id="4615a-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="4615a-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="4615a-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="4615a-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-125">DataProxy.exe</span></span>

  - <span data-ttu-id="4615a-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="4615a-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="4615a-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="4615a-129">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="4615a-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="4615a-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-130">LysSvc.exe</span></span>

  - <span data-ttu-id="4615a-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="4615a-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="4615a-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="4615a-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="4615a-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="4615a-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="4615a-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="4615a-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-138">RtcHost.exe</span></span>

  - <span data-ttu-id="4615a-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="4615a-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="4615a-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-141">XmppTGW.exe</span></span>

- <span data-ttu-id="4615a-142">Windows Fabric-Hostdienst-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="4615a-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="4615a-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-143">Fabric.exe</span></span>

  - <span data-ttu-id="4615a-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="4615a-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-145">FabricHost.exe</span></span>

- <span data-ttu-id="4615a-146">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="4615a-146">IIS processes:</span></span>

  - <span data-ttu-id="4615a-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="4615a-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="4615a-149">SQL Server Back-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="4615a-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="4615a-150">Beachten Sie, dass diese Pfade nur für diese SQL Server-Version gelten.</span><span class="sxs-lookup"><span data-stu-id="4615a-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="4615a-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="4615a-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="4615a-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="4615a-154">SQL Server Front-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="4615a-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="4615a-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="4615a-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="4615a-157">Standard Edition-Installationsinstanz „rtc“</span><span class="sxs-lookup"><span data-stu-id="4615a-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="4615a-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="4615a-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="4615a-159">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="4615a-159">Directories and files:</span></span>

  - <span data-ttu-id="4615a-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="4615a-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="4615a-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="4615a-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="4615a-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="4615a-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="4615a-163">Beachten Sie, dass diese Pfade speziell für die Skype for Business Server-Version sind.</span><span class="sxs-lookup"><span data-stu-id="4615a-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="4615a-164">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4615a-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="4615a-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="4615a-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="4615a-166">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4615a-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="4615a-167">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4615a-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="4615a-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="4615a-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="4615a-p105">Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="4615a-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="4615a-p106">SQL Server-Daten und -Protokolldateien, u. a. für die Back-End-Datenbank, den Benutzer-, Archivierungs-, Überwachungs- und den Anwendungsspeicher. Datenbank- und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4615a-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="4615a-174">SQL Server-Daten-und-Protokolldateien, einschließlich derer für die Front-End-Datenbank, den Skype for Business-Store und den RtcDatabase-Store.</span><span class="sxs-lookup"><span data-stu-id="4615a-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="4615a-175">Sie befinden sich normalerweise unter%LocalDrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="4615a-175">They are normally under %localdrive%\CSData.</span></span>


