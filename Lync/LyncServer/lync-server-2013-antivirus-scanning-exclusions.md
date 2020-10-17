---
title: 'Lync Server 2013: Ausschlüsse für Antivirusscans'
description: 'Lync Server 2013: Ausschlüsse für Antivirusscans.'
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
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561911"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Antivirus-Scan Ausschlüsse für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-11-02_

Um sicherzustellen, dass der Antivirus-Scanner den Betrieb von lync Server 2013 nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden lync Server 2013 Server oder jede Serverrolle ausschließen, auf dem Sie einen Antivirenprogramm ausführen. Die folgenden Prozesse und Verzeichnisse sollten ausgeschlossen werden:

<div>


> [!NOTE]  
> Unten aufgeführte Ordner-und Dateispeicherorte sind die Standardspeicherorte für lync Server 2013. Schließen Sie für alle Standorte, für die Sie die Standardeinstellung nicht verwendet haben, die für Ihre Organisation angegebenen Speicherorte anstelle der in diesem Thema angegebenen Standardspeicherorte aus.



</div>

<div>


> [!IMPORTANT]  
> Beachten Sie, dass einige Antivirus-Programme möglicherweise absolute, keine relativen Pfade für Ihre Ausschlussliste benötigen.



</div>

  - Lync Server 2013 Prozesse:
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
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

  - Windows Fabric-Host Dienstprozesse:
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - IIS-Prozesse:
    
      - % systemroot% \\ system32 \\ inetsrv \\w3wp.exe
    
      - % systemroot% \\ syswow64 \\ inetsrv \\w3wp.exe

  - SQL Server Back-End Prozesse:
    
      - % Programme% \\ Microsoft SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe
    
      - % Programme% \\ Microsoft SQL Server \\ MSRS11. MSSQLSERVER \\ Reporting Services \\ Report \\ Container bin \\ReportingServicesService.exe
    
      - % Programme% \\ Microsoft SQL Server \\ MSAS11. OLAP-Schacht "MSSQLSERVER" \\ \\ \\MSMDSrv.exe

  - SQL Server Front-End Prozesse:
    
      - % Programme% \\ Microsoft SQL Server \\ MSSQL11. LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe
    
      - % Programme% \\ Microsoft SQL Server \\ MSSQL11. RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe

  - Verzeichnisse und Dateien:
    
      - % systemroot% \\ system32- \\ Protokolldateien
    
      - % systemroot-% \\ syswow64- \\ Protokolldateien
    
      - % systemroot% \\ Microsoft.net- \\ Assembly \\ GAC \_ MSIL
    
      - % Programme% \\ Microsoft lync Server 2013
    
      - % Programme% \\ Allgemeine Dateien \\ Microsoft lync Server 2013 \\ Watcher-Knoten
    
      - % Programme% \\ Allgemeine Dateien \\ Microsoft lync Server 2013
    
      - % System Drive% \\ RtcReplicaRoot
    
      - Dateifreigabe Speicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.
    
      - SQL Server von Daten-und Protokolldateien, einschließlich derer für die Back-End-Datenbank, den Benutzerspeicher, den Archivierungsspeicher, den Überwachungsspeicher und den Anwendungsspeicher. Datenbank-und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten und Protokolldateien für jede Datenbank, einschließlich der Standardnamen, finden Sie unter [SQL Server Data and Log File Placement for lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in der Bereitstellungsdokumentation.
    
      - SQL Server von Daten-und Protokolldateien, einschließlich der für die Front-End-Datenbank, lync Store und RtcDatabase Store. Sie befinden sich normalerweise unter% LokalesLaufwerk% \\ CSData.

</div>

<span> </span>

</div>

</div>

</div>

