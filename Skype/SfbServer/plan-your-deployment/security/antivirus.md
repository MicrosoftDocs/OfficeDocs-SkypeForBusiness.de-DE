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
description: Übersicht über die Interoperabilität von Antivirusscannern mit Skype for Business Server.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832265"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Antivirusscanausschlüsse für Skype for Business Server

Übersicht über die Interoperabilität von Antivirusscannern mit Skype for Business Server.

Um sicherzustellen, dass der Antivirenscanner den Betrieb von Skype for Business Server nicht beeinträchtigt, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden Skype for Business Server-Server oder jede Serverrolle ausschließen, auf dem Sie einen Antivirenscanner ausführen. Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:

> [!NOTE]
> Die unten aufgeführten Ordner- und Dateispeicherorte sind die Standardspeicherorte für Skype for Business Server. Schließen Sie für alle Speicherorte, für die Sie nicht die Standardeinstellung verwendet haben, die Für Ihre Organisation angegebenen Speicherorte anstelle der in diesem Thema angegebenen Standardspeicherorte aus.

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

- SQL Server Back-End prozesse:

    > [!NOTE]
    > Beachten Sie, dass diese Pfade spezifisch für SQL Server sind.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End prozesse:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition Installation RTC Instance

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Verzeichnisse und Dateien:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Beachten Sie, dass diese Pfade spezifisch für die Skype for Business Server-Version sind.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Dateifreigabespeicher (angegeben im Topologie-Generator). Dateispeicher werden im Topologie-Generator angegeben.

  - SQL Server daten- und protokolldateien, einschließlich derjenigen für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher. Datenbank- und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter [SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) Platzierung von Daten und Protokolldateien in der Bereitstellungsdokumentation.

  - SQL Server daten- und protokolldateien, einschließlich derjenigen für die Front-End-Datenbank, den Skype for Business-Speicher und den RtcDatabase-Speicher. Sie befinden sich normalerweise unter %localdrive%\CSData.


