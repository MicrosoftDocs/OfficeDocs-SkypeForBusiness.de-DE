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
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a>Virenschutzprogramm-Ausschlüsse für Skype for Business Server 2015
 
Übersicht über Antivirusscanner Interoperation mit Skype für Business Server 2015. 
  
Um sicherzustellen, dass die Antivirusscanner nicht mit dem Betrieb des Skype für Business Server 2015 beeinträchtigt, müssen Sie bestimmte Prozesse und Verzeichnisse ausschließen, für jeden Skype für Business Server 2015 Server oder Serverrolle auf dem Sie einen Antivirenscanner ausgeführt. Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:
  
> [!NOTE]
> Unten aufgeführten sind Ordner und Datei die Standardspeicherorte für Skype für Business Server 2015. Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben. 
  
> [!IMPORTANT]
> Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen. 
  
- Skype für Business Server 2015 Prozesse:
    
  - ABServer.exe
    
  - ASMCUSvc.exe
    
  - AVMCUSvc.exe
    
  - ChannelService.exe
    
  - ClsAgent.exe
    
  - ComplianceService.exe
    
  - DataMCUSvc.exe
    
  - DataProxy.exe
    
  - FileTransferAgent.exe
    
  - HealthAgent.exe
    
  - IMMCUSvc.exe
    
  - LysSvc.exe
    
  - MasterReplicatorAgent.exe
    
  - MediaRelaySvc.exe
    
  - MediationServerSvc.exe
    
  - MRASSvc.exe
    
  - OcsAppServerHost.exe
    
  - ReplicaReplicatorAgent.exe
    
  - ReplicationApp.exe
    
  - RtcHost.exe
    
  - RTCSrv.exe
    
  - XmppProxy.exe
    
  - XmppTGW.exe
    
- Windows Fabric-Hostdienst-Prozesse:
    
  - Fabric.exe
    
  - FabricDCA.exe
    
  - FabricHost.exe
    
- IIS-Prozesse:
    
  - %systemroot%\system32\inetsrv\w3wp.exe
    
  - %systemroot%\SysWOW64\inetsrv\w3wp.exe
    
- SQL Server Back-End-Prozesse:
    
    > [!NOTE]
    > Beachten Sie, dass diese Pfade nur für diese SQL Server-Version gelten. 
  
  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe
    
- SQL Server Front-End-Prozesse:
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - Standard Edition-Installationsinstanz „rtc“ 
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe
    
- Verzeichnisse und Dateien:
    
  - %systemroot%\System32\LogFiles
    
  - %systemroot%\SysWow64\LogFiles
    
  - %SystemRoot%\Microsoft.NET\assembly\GAC_MSIL
    
  - %programfiles%\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node
    
  - %programfiles%\Common Files\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.
    
  - SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Back-End-Datenbank, Benutzerspeicher, Archivierungsspeicher, Speicher für Überwachung und Anwendungsspeicher. Datenbank-und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Dateien Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen finden Sie unter [SQL Server-Daten und Platzieren der Protokolldatei](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.
    
  - SQL Server Daten- und Protokolldateien-Dateien, einschließlich derer, für die Front-End-Datenbank, Skype für Business Store und RtcDatabase Store. Sie sind normalerweise unter % localdrive%\CSData.
    

