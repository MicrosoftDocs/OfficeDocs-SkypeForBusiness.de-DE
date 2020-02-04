---
title: 'Lync Server 2013: Ausnahmen in Virenschutzprogrammen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90847830d9f2586e0d111846f2867400c52fc940
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Ausnahmen in Virenschutzprogrammen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-11-02_

Wenn Sie sicherstellen möchten, dass der Virenscanner den Betrieb von lync Server 2013 nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden lync Server 2013-Server oder die Serverrolle ausschließen, auf der Sie einen Antivirus-Scanner ausführen. Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:

<div>


> [!NOTE]  
> Die nachstehend aufgeführten Ordner-und Dateispeicherorte sind die Standardspeicherorte für lync Server 2013. Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.



</div>

<div>


> [!IMPORTANT]  
> Beachten Sie, dass einige Virenschutzprogramme für ihre Ausschlussliste anstelle von relativen möglicherweise absolute Pfade benötigen.



</div>

  - Lync Server 2013-Prozesse:
    
      - ABServer.exe
    
      - AcpMcuSvc. exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
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
    
      - % systemroot\\%\\System32\\inetsrv w3wp. exe
    
      - % systemroot\\%\\syswow64\\inetsrv w3wp. exe

  - SQL Server Back-End-Prozesse:
    
      - % Programme%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe
    
      - % Programme%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\Report\\Server\\bin ReportingServicesService. exe
    
      - % Programme%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\bin\\MSMDSrv. exe

  - SQL Server Front-End-Prozesse:
    
      - % Programme%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe
    
      - % Programme%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe

  - Verzeichnisse und Dateien:
    
      - % systemroot\\%\\System32-Protokolldateien
    
      - % systemroot\\% syswow64\\-Protokolldateien
    
      - % systemroot\\%\\Microsoft.net\\Assembly\_GAC MSIL
    
      - % Programme%\\Microsoft lync Server 2013
    
      - % Programme%\\Common Files\\Microsoft lync Server 2013\\Watcher-Knoten
    
      - % Programme%\\allgemeine Dateien\\Microsoft lync Server 2013
    
      - % SystemDrive\\% RtcReplicaRoot
    
      - Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.
    
      - SQL Server-Daten-und-Protokolldateien, einschließlich derer für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher. In Topology Builder können Datenbank-und Protokolldateien angegeben werden. Details zu den Daten-und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter [SQL Server-Daten-und Protokolldatei Platzierung für lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in der Bereitstellungsdokumentation.
    
      - SQL Server-Daten-und-Protokolldateien, einschließlich derer für die Front-End-Datenbank, den lync-Store und den RtcDatabase-Speicher. Sie befinden sich normalerweise unter\\% LokalesLaufwerk% CSData.

</div>

<span> </span>

</div>

</div>

</div>

