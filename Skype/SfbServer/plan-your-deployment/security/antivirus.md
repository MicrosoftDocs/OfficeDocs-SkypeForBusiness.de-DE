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
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Ausschlüsse für Antivirus-Scans für Skype for Business Server

Übersicht über die Interoperabilität des Antivirus-Scanners mit Skype for Business Server.

Dieser Artikel enthält Empfehlungen, die einem Administrator helfen können, die Ursache einer potenziellen Instabilität auf einem Computer zu ermitteln, auf dem eine unterstützte Version von Microsoft Windows ausgeführt wird, wenn diese mit Antivirensoftware in einer Active Directory-Domäne verwendet wird. Umgebung oder in einer verwalteten Unternehmensumgebung.

Wir empfehlen, diese Verfahren vorübergehend zur Auswertung eines Systems anzuwenden. Wenn sich die Leistung oder Stabilität Ihres Systems durch die Empfehlungen in diesem Artikel verbessert hat, wenden Sie sich an den Hersteller Ihrer Antivirensoftware, um Anweisungen oder eine aktualisierte Version der Antivirensoftware zu erhalten.

Dieser Artikel enthält Informationen, die zeigen, wie Sie die Sicherheitseinstellungen verringern oder wie Sie Sicherheitsfunktionen vorübergehend auf einem Computer deaktivieren können. Sie können diese Änderungen vornehmen, um die Art eines bestimmten Problems zu verstehen. Bevor Sie diese Änderungen vornehmen, empfehlen wir, dass Sie die Risiken bewerten, die mit der Implementierung dieser Problemumgehung in ihrer jeweiligen Umgebung verbunden sind. Wenn Sie diese Problemumgehung implementieren, führen Sie alle geeigneten zusätzlichen Schritte aus, um den Computer für die Dateien zu schützen, die von Ihrer Antivirensoftware nicht mehr gescannt werden.

Um sicherzustellen, dass der Virenscanner den Betrieb von Skype for Business Server nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden Skype for Business Server-Server oder jede Serverrolle ausschließen, auf der Sie einen Antivirus-Scanner ausführen. Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:

> [!NOTE]
> Die nachstehend aufgeführten Ordner-und Dateispeicherorte sind die Standardspeicherorte für Skype for Business Server. Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.

> [!IMPORTANT]
> Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.

- Skype for Business Server-Prozesse:

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
  
  - LyncBackupService. exe

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

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Beachten Sie, dass diese Pfade speziell für die Skype for Business Server-Version sind.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.

  - SQL Server-Daten und -Protokolldateien, u. a. für die Back-End-Datenbank, den Benutzer-, Archivierungs-, Überwachungs- und den Anwendungsspeicher. Datenbank- und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in der Bereitstellungsdokumentation.

  - SQL Server-Daten-und-Protokolldateien, einschließlich derer für die Front-End-Datenbank, den Skype for Business-Store und den RtcDatabase-Store. Sie befinden sich normalerweise unter%LocalDrive%\CSData.


