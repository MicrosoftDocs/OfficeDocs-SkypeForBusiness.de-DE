---
title: Virenscan Ausschlüsse für Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Übersicht über Antivirusscanner Interoperation mit Skype für Business Server.
ms.openlocfilehash: 1078b3c0a28573e84235cbd39a11a6aa84a58b47
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250024"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="fc97b-103">Virenscan Ausschlüsse für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="fc97b-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="fc97b-104">Übersicht über Antivirusscanner Interoperation mit Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc97b-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="fc97b-105">Dieser Artikel enthält Empfehlungen, die dazu beitragen können ein Administrator die Ursache des potenzielle instabil auf einem Computer, auf dem eine unterstützte Version von Microsoft Windows ausgeführt wird, wenn sie mithilfe von Antivirensoftware in einer Active Directory-Domäne verwendet wird Umgebung oder in einer verwalteten geschäftsumgebung.</span><span class="sxs-lookup"><span data-stu-id="fc97b-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="fc97b-106">Es wird empfohlen, dass Sie diese Verfahren zum Auswerten von einem System vorübergehend anwenden.</span><span class="sxs-lookup"><span data-stu-id="fc97b-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="fc97b-107">Wenn die Systemleistung oder Stabilität durch die Empfehlungen deutlich verbessert, die in diesem Artikel vorgenommen werden, Hersteller Ihrer Antivirensoftware Anweisungen oder eine aktualisierte Version der Software.</span><span class="sxs-lookup"><span data-stu-id="fc97b-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="fc97b-108">Dieser Artikel enthält Informationen, die zeigt, wie untere Sicherheitseinstellungen Hilfe oder Sicherheitsfeatures auf einem Computer vorübergehend zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fc97b-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="fc97b-109">Sie können diese Änderungen zu verstehen, die Art der eines bestimmten Problems vornehmen.</span><span class="sxs-lookup"><span data-stu-id="fc97b-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="fc97b-110">Bevor Sie diese Änderungen vornehmen, wird empfohlen, dass Sie bewerten die Risiken, die diese Lösung in Ihrer speziellen Umgebung implementieren zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="fc97b-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="fc97b-111">Wenn Sie diese Lösung implementieren, führen Sie entsprechenden Maßnahmen zum Schutz von dem Computer für die Dateien, die nicht mehr von Antivirensoftware gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="fc97b-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="fc97b-112">Um sicherzustellen, dass die Antivirusscanner nicht mit dem Betrieb des Skype für Business Server beeinträchtigt, müssen Sie bestimmte Prozesse und Verzeichnisse ausschließen, für jeden Skype für Business Server-Server oder Serverrolle auf dem Sie einen Antivirenscanner ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc97b-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="fc97b-113">Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="fc97b-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="fc97b-114">Unten aufgeführten sind Ordner und Datei die Standardspeicherorte für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc97b-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="fc97b-115">Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="fc97b-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc97b-116">Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.</span><span class="sxs-lookup"><span data-stu-id="fc97b-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="fc97b-117">Skype für Business Server-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="fc97b-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="fc97b-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-118">ABServer.exe</span></span>

  - <span data-ttu-id="fc97b-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="fc97b-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="fc97b-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-121">ChannelService.exe</span></span>

  - <span data-ttu-id="fc97b-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="fc97b-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="fc97b-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="fc97b-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-125">DataProxy.exe</span></span>

  - <span data-ttu-id="fc97b-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="fc97b-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="fc97b-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-128">IMMCUSvc.exe</span></span>

  - <span data-ttu-id="fc97b-129">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-129">LysSvc.exe</span></span>

  - <span data-ttu-id="fc97b-130">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-130">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="fc97b-131">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-131">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="fc97b-132">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-132">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="fc97b-133">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-133">MRASSvc.exe</span></span>

  - <span data-ttu-id="fc97b-134">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-134">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="fc97b-135">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-135">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="fc97b-136">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-136">ReplicationApp.exe</span></span>

  - <span data-ttu-id="fc97b-137">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-137">RtcHost.exe</span></span>

  - <span data-ttu-id="fc97b-138">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-138">RTCSrv.exe</span></span>

  - <span data-ttu-id="fc97b-139">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-139">XmppProxy.exe</span></span>

  - <span data-ttu-id="fc97b-140">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-140">XmppTGW.exe</span></span>

- <span data-ttu-id="fc97b-141">Windows Fabric-Hostdienst-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="fc97b-141">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="fc97b-142">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-142">Fabric.exe</span></span>

  - <span data-ttu-id="fc97b-143">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-143">FabricDCA.exe</span></span>

  - <span data-ttu-id="fc97b-144">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-144">FabricHost.exe</span></span>

- <span data-ttu-id="fc97b-145">IIS-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="fc97b-145">IIS processes:</span></span>

  - <span data-ttu-id="fc97b-146">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-146">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="fc97b-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="fc97b-148">SQL Server Back-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="fc97b-148">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc97b-149">Beachten Sie, dass diese Pfade nur für diese SQL Server-Version gelten.</span><span class="sxs-lookup"><span data-stu-id="fc97b-149">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="fc97b-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="fc97b-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="fc97b-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="fc97b-153">SQL Server Front-End-Prozesse:</span><span class="sxs-lookup"><span data-stu-id="fc97b-153">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="fc97b-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="fc97b-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="fc97b-156">Standard Edition-Installationsinstanz „rtc“</span><span class="sxs-lookup"><span data-stu-id="fc97b-156">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="fc97b-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fc97b-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="fc97b-158">Verzeichnisse und Dateien:</span><span class="sxs-lookup"><span data-stu-id="fc97b-158">Directories and files:</span></span>

  - <span data-ttu-id="fc97b-159">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="fc97b-159">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="fc97b-160">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="fc97b-160">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="fc97b-161">%SystemRoot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="fc97b-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc97b-162">Beachten Sie, dass diese Pfade für Business Server-Version für Skype spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="fc97b-162">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="fc97b-163">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fc97b-163">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="fc97b-164">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="fc97b-164">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="fc97b-165">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fc97b-165">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="fc97b-166">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fc97b-166">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="fc97b-167">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="fc97b-167">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="fc97b-p105">Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.</span><span class="sxs-lookup"><span data-stu-id="fc97b-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="fc97b-170">SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Back-End-Datenbank, Benutzerspeicher, Archivierungsspeicher, Speicher für Überwachung und Anwendungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="fc97b-170">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="fc97b-171">Datenbank-und Protokolldateien können im Topologie-Generator angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc97b-171">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="fc97b-172">Ausführliche Informationen zu den Dateien Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen finden Sie unter [SQL Server-Daten und Platzieren der Protokolldatei](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="fc97b-172">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="fc97b-173">SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Front-End-Datenbank, Skype für Business Store und RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="fc97b-173">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="fc97b-174">Sie sind normalerweise unter % localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="fc97b-174">They are normally under %localdrive%\CSData.</span></span>


