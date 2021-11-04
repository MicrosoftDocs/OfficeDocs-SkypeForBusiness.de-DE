---
title: Antivirus-Scanausschlüsse für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Übersicht über die Interoperabilität von Antivirenscannern mit Skype for Business Server.
ms.openlocfilehash: 105abd3618c5e869681edc31321a07ab0bce9d57
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737651"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Antivirus-Scanausschlüsse für Skype for Business Server

Übersicht über die Interoperabilität von Antivirenscannern mit Skype for Business Server.

Um sicherzustellen, dass der Antivirenscanner den Betrieb von Skype for Business Server nicht beeinträchtigt, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden Skype for Business Server Server oder jede Serverrolle ausschließen, auf dem bzw. der Sie einen Antivirenscanner ausführen. Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:

> [!NOTE]
> Die unten aufgeführten Ordner- und Dateispeicherorte sind die Standardspeicherorte für Skype for Business Server. Schließen Sie für alle Speicherorte, für die Sie nicht die Standardeinstellung verwendet haben, die Speicherorte aus, die Sie für Ihre Organisation anstelle der in diesem Thema angegebenen Standardspeicherorte angegeben haben.

> [!IMPORTANT]
> Bitte beachten Sie, dass einige Antivirenprogramme absolute, nicht relative Pfade für ihre Ausschlussliste benötigen.

- Skype for Business Server Prozesse:

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

- Windows Fabric Hostdienstprozesse:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- IIS-Prozesse:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End Prozesse:

    > [!NOTE]
    > Beachten Sie, dass diese Pfade für SQL Server Version spezifisch sind.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End Prozesse:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition RTC-Instanz installieren

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Verzeichnisse und Dateien:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Beachten Sie, dass diese Pfade für Skype for Business Server Version spezifisch sind.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.

  - SQL Server Daten und Protokolldateien, einschließlich der Dateien für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher. Datenbank- und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter SQL Server Platzierung von [Daten und Protokolldateien](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in der Bereitstellungsdokumentation.

  - SQL Server Daten und Protokolldateien, einschließlich der Daten für die Front-End-Datenbank, Skype for Business speicher und des RtcDatabase-Speichers. Sie befinden sich normalerweise unter %localdrive%\CSData.