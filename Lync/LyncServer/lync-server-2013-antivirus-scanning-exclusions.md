---
title: 'Lync Server 2013: Ausnahmen in Virenschutzprogrammen'
TOCTitle: Ausnahmen in Virenschutzprogrammen für Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn440138(v=OCS.15)
ms:contentKeyID: 59373608
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausnahmen in Virenschutzprogrammen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-11-02_

Damit das Virenschutzprogramm die Ausführung von Lync Server 2013 nicht stört, müssen Sie bestimmte Prozesse und Verzeichnisse für jeden Server oder jede Serverrolle mit Lync Server 2013, auf dem bzw. der ein Virenschutzprogramm ausgeführt wird, ausschließen. Die folgenden Prozesse und Verzeichnisse sollten einbezogen werden:


> [!NOTE]
> Die Ordner- und Dateispeicherorte in der folgenden Liste sind die Standardspeicherorte für Lync Server 2013. Falls Sie andere Speicherorte als die Standardspeicherorte verwendet haben, schließen Sie statt der hier aufgeführten Standardspeicherorte die Speicherorte aus, die Sie für Ihre Organisation angegeben haben.



  - Lync Server 2013-Prozesse:
    
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

  - Windows Fabric-Hostdienst-Prozesse:
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - IIS-Prozesse:
    
      - %systemroot%\\system32\\inetsrv\\w3wp.exe
    
      - %systemroot%\\SysWOW64\\inetsrv\\w3wp.exe

  - SQL Server Back-End-Prozesse:
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe

  - SQL Server Front-End-Prozesse:
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSMQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSMQL\\Binn\\SQLServr.exe

  - Verzeichnisse und Dateien:
    
      - %systemroot%\\System32\\LogFiles
    
      - %systemroot%\\SysWow64\\LogFiles
    
      - %systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - %programfiles%\\Microsoft Lync Server 2013
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013
    
      - %SystemDrive%\\RtcReplicaRoot
    
      - Dateifreigabespeicher (im Topologie-Generator angegeben). Dateispeicher werden im Topologie-Generator angegeben.
    
      - SQL Server-Daten und -Protokolldateien, u. a. für die Back-End-Datenbank, den Benutzer-, Archivierungs-, Überwachungs- und den Anwendungsspeicher. Datenbank- und Protokolldateien können im Topologie-Generator angegeben werden. Ausführliche Informationen zu den Daten- und Protokolldateien für jede Datenbank, einschließlich Standardnamen, finden Sie unter [Platzierung von SQL Server-Daten und Protokolldatei für Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in der Bereitstellungsdokumentation.
    
      - SQL Server-Daten und -Protokolldateien, u. a. für die Front-End-Datenbank, den Lync-Speicher und den RTC-Datenbankspeicher. Diese befinden sich normalerweise unter "%localdrive%\\CSData".

