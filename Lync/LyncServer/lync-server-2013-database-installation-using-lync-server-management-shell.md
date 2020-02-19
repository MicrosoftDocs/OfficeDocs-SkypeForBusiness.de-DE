---
title: 'Lync Server 2013: Datenbankinstallation mit lync Server-Verwaltungsshell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0797ed44663f8a7b8baab7c3dbe5a3099ceac5fe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Datenbankinstallation mit lync Server-Verwaltungsshell in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-06-16_

Die Trennung von Rollen und Zuständigkeiten zwischen Serveradministratoren und SQL Server Administratoren kann zu Verzögerungen bei der Implementierung führen. Lync Server 2013 verwendet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), um diese Probleme zu verringern. In einigen Fällen muss der SQL Server Administrator die Installation von Datenbanken auf dem SQL Server basierten Server außerhalb von RBAC verwalten. Die lync Server 2013-Verwaltungsshell bietet dem SQL Server-Administrator die Möglichkeit, Windows PowerShell Cmdlets auszuführen, die für die Konfiguration der Datenbanken mit den richtigen Daten und Protokolldateien entwickelt wurden. Ausführliche Informationen finden Sie unter [Deployment Permissions for SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> Im folgenden Verfahren wird davon ausgegangen, dass mindestens die lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012-Verwaltungsobjekte, CLR-Typen für Microsoft SQL Server 2012 und Microsoft SQL Server 2012 ADOMD.NET installiert sind. Die OCSCore. msi befindet sich auf dem Installationsmedium im \Setup\AMD64\Setup-Verzeichnis. Die restlichen Komponenten befinden sich in \setup\amd64. Darüber hinaus wurde Active Directory Vorbereitung für lync Server 2013 erfolgreich abgeschlossen.



</div>

**Install-CsDatabase** ist das Windows PowerShell Cmdlet, mit dem Sie die Datenbanken installieren. Das Cmdlet **install-CsDatabase** verfügt über eine große Anzahl von Parametern, von denen nur einige hier erläutert werden. Ausführliche Informationen zu den möglichen Parametern finden Sie in der Dokumentation zur lync Server 2013 Management Shell.

<div class=" ">


> [!WARNING]  
> Verwenden Sie beim Verweisen auf SQL Server basierte Server immer vollqualifizierte Domänennamen (FQDNs), um die Leistung und mögliche Timeoutprobleme zu vermeiden. Vermeiden Sie die Verwendung von Host Namen bezogenen verweisen. Verwenden Sie beispielsweise sqlbe01.contoso.net, vermeiden Sie jedoch die Verwendung von sqlbe01.



</div>

Für die Installation von Datenbanken verwendet **install-CsDatabase** drei primäre Methoden zum Platzieren der Datenbanken auf dem vorbereiteten SQL Server basierten Server:

  - Führen Sie **install-CsDatabase** ohne DatabasePaths oder UseDefaultSqlPath aus. Das Cmdlet verwendet einen integrierten Algorithmus, um die beste Platzierung für die Protokoll-und Datendateien zu ermitteln. Der Algorithmus funktioniert nur für eigenständige SQL Server-Implementierungen.

  - Führen Sie **install-CsDatabase** mit dem Parameter DatabasePaths aus. Der integrierte Algorithmus zum Optimieren der Speicherorte von Protokoll-und Datendateien wird nicht verwendet, wenn der Parameter DatabasePaths definiert ist. Mithilfe dieses Parameters können Sie die Speicherorte definieren, an denen Protokoll-und Datendateien bereitgestellt werden.

  - Führen Sie **install-CsDatabase** mit UseDefaultSqlPaths aus. Bei dieser Option wird nicht der integrierte Algorithmus zum Optimieren der Speicherorte von Protokollen und Datendateien verwendet. Protokoll-und Datendatei werden gemäß den vom SQL Server Administrator festgelegten Standardeinstellungen bereitgestellt. Diese Pfade werden normalerweise zum Zweck der automatischen Verwaltung von Protokoll-und Datendateien auf der SQL Server im Voraus festgelegt und sind nicht mit dem Setup von lync Server 2013 verknüpft.

  - Der Parameter DatabasePathMap kann auch verwendet werden, um explizit einen Speicherort für jede Datenbank und die zugehörige Protokolldatei anzugeben.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren des SQL Server zentralen Verwaltungsspeichers

1.  Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server basierten Server an. Ausführliche Informationen finden Sie unter [Deployment Permissions for SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Öffnen Sie die lync Server 2013 Management-Shell. Wenn Sie die Ausführungsrichtlinie für Windows PowerShell nicht angepasst haben, müssen Sie die Richtlinie so anpassen, dass Windows PowerShell Skripts ausgeführt werden können. Ausführliche Informationen finden Sie unter "Überprüfen der Ausführungsrichtlinie" [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093)unter.

3.  Verwenden Sie das Cmdlet **install-CsDatabase** , um den zentralen Verwaltungsspeicher zu installieren.
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Der Parameter Report ist optional, aber nützlich, wenn Sie den Installationsvorgang dokumentieren.

    
    </div>

4.  **Install-CsDatabase – DatabasePaths** kann bis zu sechs Pfadparameter verwenden, wobei jeder die Pfade für die Laufwerke definiert, die in SQL Server Daten-und Protokolldatei Platzierung definiert sind. Durch die logischen Regeln der Datenbankkonfiguration in lync Server 2013 werden Laufwerke in Buckets mit zwei, vier oder sechs analysiert. Abhängig von der SQL Server Konfiguration und der Anzahl der Buckets werden zwei Pfade, vier Pfade oder sechs Pfade bereitgestellt.
    
    Wenn Sie drei Laufwerke haben, wird das Protokoll Priorität erhalten und die Datendateien werden nach verteilt. Ein Beispiel für einen SQL Server basierten Server, der mit sechs Laufwerken konfiguriert ist:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Wenn die Datenbankinstallation abgeschlossen ist, können Sie lync Server 2013 Verwaltungsshell schließen oder mit der Installation der lync Server 2013 konfigurierten Datenbanken fortfahren, die im Topologie-Generator definiert sind.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>So konfigurieren Sie die konfigurierten Datenbanken für die SQL Server Topologie mithilfe von Windows PowerShell-Cmdlets

1.  Zum Installieren des Topologie-Generators für lync Server 2013 konfigurierte Datenbanken muss der lync Server 2013 Administrator die Topologie veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation.

2.  Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server basierten Server an. Siehe das Thema, [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Um die SQL Server basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe "Sysadmins" (oder einer gleichwertigen) auf dem Server ist, auf dem SQL Server ausgeführt wird und das die zentrale Verwaltung hält. Server Rolle. Dies ist besonders wichtig, um nach zusätzlichen lync Server 2013 Pools zu suchen, die SQL Server Datenbankinstallation oder-Konfiguration erfordern. Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle jedoch von pool01 gehalten wird. Die SQL Server Gruppe "sysadmin" (oder gleichwertig) muss über Berechtigungen für beide SQL Server basierte Datenbanken verfügen.

    
    </div>

3.  Öffnen Sie lync Server 2013 Verwaltungsshell, falls Sie noch nicht geöffnet ist.

4.  Verwenden Sie das Cmdlet **install-CsDatabase** , um die konfigurierten Datenbanken des Topologie-Generators zu installieren.
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Der Parameter Report ist optional, aber nützlich, wenn Sie den Installationsvorgang dokumentieren.

    
    </div>

5.  Wenn die Datenbankinstallation abgeschlossen ist, schließen Sie lync Server 2013 Management Shell.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der SQL Server Topologie mithilfe des DatabasePathMap-Parameters

1.  Um Datenbanken für lync Server 2013 zu installieren, muss der lync Server-Administrator die Pfade erstellen und die Datenbankendateien und Protokolldateien entsprechend einem vordefinierten Satz von Regeln bereitstellen.

2.  Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server basierten Server an. Siehe das Thema, [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Um die SQL Server basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe "Sysadmins" (oder einer gleichwertigen) auf dem Server ist, auf dem SQL Server ausgeführt wird und das die zentrale Verwaltung hält. Server Rolle. Dies ist besonders wichtig, um nach zusätzlichen lync Server Pools zu suchen, die SQL Server Datenbankinstallation oder-Konfiguration erfordern. Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle jedoch von pool01 gehalten wird. Die SQL Server Gruppe "sysadmin" (oder gleichwertig) muss über Berechtigungen für beide SQL Server basierte Datenbanken verfügen.

    
    </div>

3.  Öffnen Sie lync Server-Verwaltungsshell, wenn es noch nicht geöffnet ist.

4.  Verwenden Sie das Cmdlet **install-CsDatabase** mit dem Parameter DatabasePathMap und einer PowerShell-Hashtabelle, um die konfigurierten Datenbanken des Topologie-Generators zu installieren.

5.  Im Beispielcode können die für die Datenbanken definierten Pfade auf granulare Weise mithilfe des Parameters – DatabasePathMap und einer definierten Hashtabelle wie folgt bestimmt werden (das Beispiel verwendet "c:\\CSData" für alle Datenbankdateien (MDF) und "c:\\CSLogFiles" für alle Protokolldateien (LDF). Der Ordner wird bei Bedarf von install-CsDatabase erstellt:
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  Da die Datenbank-und Protokolldateien explizit mit ihrem Speicherort auf dem Zieldatenbankserver benannt werden, können Sie bestimmte Speicherorte für die tatsächliche Datenbank und den Protokollspeicherort der einzelnen Diensttypen definieren. Im folgenden Beispiel werden Datenbanken für jeden bestimmten Diensttyp auf separaten Datenträgern und zugeordneten Protokolldateien auf einem anderen platziert. Zum Beispiel:
    
      - Alle RTC-Datenbanken in "\\D: RTCDatabase"
    
      - Alle RTC-Protokolldateien in "E\\: RTCLogs"
    
      - Alle Anwendungsspeicher Datenbanken in "F:\\CPSDatabases"
    
      - Alle Anwendungsspeicher Protokolle in "G:\\CPSLogs"
    
      - Alle Datenbanken der Reaktionsgruppen Speicherung in "\\H: RGSDatabases"
    
      - Alle Reaktionsgruppen Speicherprotokolle in "I:\\RGSLogs"
    
      - Alle Adressbuchspeicher-Datenbanken in "\\J: ABSDatabases"
    
      - Alle Protokolldateien des Adressbuch Speichers in "\\K: ABSLogs"
    
      - Alle Archivierungsspeicher Datenbanken in "L:\\ArchivingDatabases"
    
      - Alle Archivierungsspeicher Protokolle in "M:\\ArchivingLogs"
    
      - Alle Überwachungsspeicher Datenbanken in "N:\\MonitoringDatabases"
    
      - Alle Überwachungsspeicher-Protokolldateien in "O\\: MonitoringLogfiles"
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    Mithilfe des Parameters – DatabasePathMap können Sie eine beliebige Kombination aus logischem Laufwerkbuchstaben definieren, die die beste Lösung für Ihre SQL Server Leistungs-und Platzierungs Anforderungen bereitstellt.

Wenn Sie die Datenbankdateien und Protokolldateien mithilfe der **DatabasePathMap** -Methode konfigurieren, müssen Sie bei Verwendung des Topologie-Generators eine geringfügige Änderung an Ihrem normalen Prozess vornehmen. In der Regel definieren Sie die Auswahl der Topologie, veröffentlichen die Topologie und wählen, um die Datenbankauswahl bereitzustellen.

Wenn Sie **DatabasePathMap** verwendet haben, haben Sie bereits den dritten Teil des Topologie-Generator-Prozesses ausgeführt. Wenn Sie vor dem Ausführen des Topologie-Generators einen vollständig konfigurierten Datenbankserver haben, würden Sie trotzdem alle Ihre Serverrollen und Optionen definieren, aber deaktivieren Sie die Option zum Erstellen der Datenbanken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

