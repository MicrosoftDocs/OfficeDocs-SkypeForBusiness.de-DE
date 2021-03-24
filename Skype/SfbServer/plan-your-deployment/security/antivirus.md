---
title: Antivirusscanausschlüsse für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Übersicht über die Interoperabilität von Antivirenscannern mit Skype for Business Server.
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104241"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Antivirusscanausschlüsse für Skype for Business Server

Übersicht über die Interoperabilität von Antivirenscannern mit Skype for Business Server.

Um sicherzustellen, dass der Antivirenscanner den Betrieb von Skype for Business Server nicht beeinträchtigt, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden Skype for Business Server-Server oder jede Serverrolle ausschließen, auf dem Sie einen Antivirenscanner ausführen. Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:

> [!NOTE]
> Die unten aufgeführten Ordner- und Dateispeicherorte sind die Standardspeicherorte für Skype for Business Server. Schließen Sie für alle Speicherorte, für die Sie nicht die Standardeinstellung verwendet haben, die für Ihre Organisation angegebenen Speicherorte anstelle der in diesem Thema angegebenen Standardspeicherorte aus.

> [!IMPORTANT]
> Bitte beachten Sie, dass einige Antivirenprogramme absolute, nicht relative Pfade für ihre Ausschlussliste benötigen.

- Skype for Business Server verarbeitet:

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
  
  - LyncBackupService.exe

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

- Windows Fabric Host Service verarbeitet:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- IIS-Prozesse:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End Prozesse:

    > [!NOTE]
    > Beachten Sie, dass diese Pfade spezifisch für SQL Server sind.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End Prozesse:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition Installation RTC Instance

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Verzeichnisse und Dateien:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Beachten Sie, dass diese Pfade für die Skype for Business Server-Version spezifisch sind.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Dateifreigabespeicher (angegeben im Topologie-Generator). Dateispeicher werden im Topologie-Generator angegeben.

  - SQL Server Daten und Protokolldateien, einschließlich der Daten für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher. Datenbank- und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie [unter SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation.

  - SQL Server und Protokolldateien, einschließlich der Daten für die Front-End-Datenbank, den Skype for Business-Speicher und den RtcDatabase-Speicher. Sie befinden sich normalerweise unter %localdrive%\CSData.