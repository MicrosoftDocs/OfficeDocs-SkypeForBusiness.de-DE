---
title: 'Lync Server 2013: Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell'
TOCTitle: Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398832(v=OCS.15)
ms:contentKeyID: 49295388
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Eine Trennung der Rollen und Verantwortlichkeiten von Serveradministratoren und SQL Server-Administratoren kann zu Verzögerungen bei der Implementierung führen. Lync Server 2013 verwendet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) um diese Probleme zu minimieren. In einigen Fällen muss der SQL Server-Administrator die Installation von Datenbanken auf dem SQL Server-basierten Server verwalten, ohne dass die rollenbasierte Zugriffssteuerung verwendet werden kann. Mithilfe der Verwaltungsshell für Lync Server 2013 kann der SQL Server-Administrator Windows PowerShell-Cmdlets zum Konfigurieren der Datenbanken mit den richtigen Daten- und Protokolldateien ausführen. Ausführliche Informationen dazu finden Sie unter [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).


> [!IMPORTANT]
> Für das folgende Verfahren wird davon ausgegangen, dass mindestens Lync Server 2013 ( OCSCore.msi ), SQL Server Native Client ( sqlncli.msi ) Microsoft SQL Server&nbsp;2012 Management Objects, CLR-Typen für Microsoft SQL Server&nbsp;2012 und Microsoft SQL Server&nbsp;2012 ADOMD.NET installiert sind. Die Datei OCSCore.msi befindet sich auf dem Installationsmedium im Verzeichnis \Setup\AMD64\Setup . Die restlichen Komponenten befinden sich im Verzeichnis \Setup\amd64 . Zusätzlich wurde die Active Directory-Vorbereitung für Lync Server 2013 erfolgreich abgeschlossen.



Zur Installation der Datenbanken wird das Windows PowerShell-Cmdlet **Install-CsDatabase** verwendet. Das Cmdlet **Install-CsDatabase** verfügt über eine große Anzahl von Parametern, von denen an dieser Stelle nur wenige erläutert werden. Ausführliche Informationen zu den möglichen Parametern finden Sie in der Dokumentation zur Verwaltungsshell für Lync Server 2013.


> [!WARNING]
> Um Leistungs- und mögliche Timeoutprobleme zu verhindern, verwenden Sie stets die vollqualifizierten Domänennamen, wenn Sie auf SQL&nbsp;Server-basierte Server verweisen. Vermeiden Sie in Verweisen die ausschließliche Verwendung von Hostnamen. Beispiel: verwenden Sie sqlbe.contoso.net , vermeiden Sie jedoch die Verwendung von SQLBE01 .



Für die Installation von Datenbanken verwendet **Install-CsDatabase** drei primäre Methoden für die Platzierung der Datenbanken auf dem vorbereiteten SQL Server-basierten Server:

  - Führen Sie **Install-CsDatabase** ohne DatabasePaths oder UseDefaultSqlPath aus. Das Cmdlet verwendet einen integrierten Algorithmus zum Ermitteln der besten Platzierung für die Protokoll- und Datendateien. Dieser Algorithmus funktioniert nur bei eigenständigen SQL Server-Implementierungen.

  - Führen Sie **Install-CsDatabase** mit dem DatabasePaths -Parameter aus. Der integrierte Algorithmus zum Optimieren der Speicherorte für Protokoll- und Datendateien wird nicht verwendet, wenn der DatabasePaths -Parameter definiert ist. Bei Verwendung dieses Parameters können Sie die Verzeichnisse definieren, in denen Protokoll- und Datendateien bereitgestellt werden.

  - Führen Sie **Install-CsDatabase** mit UseDefaultSqlPaths aus. Bei Verwendung dieser Option wird der integrierte Algorithmus zum Optimieren der Speicherorte für Protokoll- und Datendateien nicht verwendet. Protokoll- und Datendateien werden in den Standardverzeichnissen bereitgestellt, die der SQL Server-Administrator festlegt. Diese Pfade werden typischerweise vorab zur automatischen Verwaltung von Protokoll- und Datendateien auf dem SQL Server-Computer festgelegt und sind nicht mit der Einrichtung von Lync Server 2013 verbunden.

  - Mit dem DatabasePathMap -Parameter können Sie auch explizit einen Speicherort für jede Datenbank und die zugehörige Protokolldatei angeben.

## So konfigurieren Sie den zentralen Verwaltungsspeicher von SQL Server mithilfe der Windows PowerShell-Cmdlets

1.  Melden Sie sich bei einem beliebigen Computer mit Administratoranmeldeinformationen an, um die Datenbanken auf dem SQL Server-basierten Server zu erstellen. Ausführliche Informationen dazu finden Sie unter [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Öffnen Sie die Verwaltungsshell für Lync Server 2013. Wenn Sie keine Anpassung der Ausführungsrichtlinie für Windows PowerShell vorgenommen haben, müssen Sie die Richtlinie jetzt anpassen, damit Windows PowerShell-Skripts ausgeführt werden können. Ausführliche Informationen finden Sie in "Überprüfen der Ausführungsrichtlinie" unter <http://go.microsoft.com/fwlink/?linkid=203093>.

3.  Verwenden Sie das Cmdlet **Install-CsDatabase**, um den zentralen Verwaltungsspeicher zu installieren.
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>

       &nbsp;
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
    

    > [!TIP]
    > Der optionale Parameter "Report" ist nützlich, wenn Sie den Installationsvorgang dokumentieren.



4.  **Install-CsDatabase –DatabasePaths** kann bis zu sechs Pfadparameter verwenden, von denen jeder die Pfade für die Laufwerke gemäß Definition in "Platzierung von SQL Server-Daten und Protokolldatei " festlegt. Durch die logischen Regeln der Datenbankkonfiguration in Lync Server 2013 werden Laufwerke analysiert und zu Buckets mit zwei, vier oder sechs Laufwerken gruppiert. In Abhängigkeit von der SQL Server-Konfiguration und der Anzahl der Buckets stellen Sie zwei, vier oder sechs Pfade bereit.
    
    Wenn Sie drei Laufwerke verwenden, erhält das Protokoll Vorrang, und die Datendateien werden danach verteilt. Es folgt ein Beispiel für einen SQL Server-basierten Server, der mit sechs Laufwerken konfiguriert ist:
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  Nach Abschluss der Datenbankinstallation können Sie die Verwaltungsshell für Lync Server 2013 schließen oder mit der Installation der für Lync Server 2013 konfigurierten Datenbanken fortfahren, die im Topologie-Generator definiert wurden.

## So konfigurieren Sie die für die SQL Server-Topologie konfigurierten Datenbanken mithilfe von Windows PowerShell-Cmdlets

1.  Um die im Topologie-Generator konfigurierten Datenbanken für Lync Server 2013 zu installieren, muss der Lync Server 2013-Administrator die Topologie veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation.

2.  Melden Sie sich an einem beliebigen Computer mit Administratoranmeldeinformationen an, um die Datenbanken auf dem SQL Server-basierten Server zu erstellen. Weitere Informationen hierzu finden unter [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    

    > [!IMPORTANT]
    > Damit die SQL Server-basierten Datenbanken konfiguriert werden können, stellen Sie sicher, dass das zum Ausführen der hier beschriebenen Schritte verwendete SQL Server-Administratorkonto auch Mitglied der Gruppe <STRONG>sysadmins</STRONG> (oder einer gleichwertigen Gruppe) auf dem Server mit SQL Server ist und die zentraler Verwaltungsserver-Rolle innehat. Dies ist besonders wichtig, um überprüfen zu können, in welchen zusätzlichen Lync Server 2013-Pools ggf. SQL Server-Datenbanken installiert oder konfiguriert werden müssen, z.&nbsp;B. wenn Sie einen zweiten Pool bereitstellen ( <STRONG>pool02</STRONG> ), aber <STRONG>pool01</STRONG> die zentraler Verwaltungsserver-Rolle innehat. Die <STRONG>sysadmin</STRONG> -Gruppe (oder eine gleichwertige Gruppe) von SQL Server benötigt Berechtigungen für beide SQL Server-basierten Datenbanken.



3.  Öffnen Sie gegebenenfalls die Verwaltungsshell für Lync Server 2013.

4.  Verwenden Sie das Cmdlet **Install-CsDatabase**, um die mit dem Topologie-Generator konfigurierten Datenbanken zu installieren.
    ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
    ```

    ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
    ```

    > [!TIP]
    > Der optionale Parameter "Report" ist nützlich, wenn Sie den Installationsvorgang dokumentieren.



5.  Schließen Sie die Verwaltungsshell für Lync Server 2013, wenn die Datenbankinstallation abgeschlossen ist.

## So konfigurieren Sie mithilfe der Windows PowerShell-Cmdlets die SQL Server-Topologie unter Verwendung des DatabasePathMap-Parameters

1.  Um Datenbanken für Lync Server 2013 zu installieren, muss der Lync Server-Administrator die Pfade erstellen und die Datenbank- und Protokolldateien gemäß einem vordefinierten Regelsatz bereitstellen.

2.  Melden Sie sich an einem beliebigen Computer mit Administratoranmeldeinformationen an, um die Datenbanken auf dem SQL Server-basierten Server zu erstellen. Weitere Informationen hierzu finden unter [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    

    > [!IMPORTANT]
    > Damit die SQL Server-basierten Datenbanken konfiguriert werden können, stellen Sie sicher, dass das zum Ausführen der hier beschriebenen Schritte verwendete SQL Server-Administratorkonto auch Mitglied der Gruppe <STRONG>sysadmins</STRONG> (oder einer gleichwertigen Gruppe) auf dem Server mit SQL Server ist und die zentraler Verwaltungsserver-Rolle innehat. Dies ist besonders wichtig, um überprüfen zu können, in welchen zusätzlichen Lync Server-Pools ggf. SQL Server-Datenbanken installiert oder konfiguriert werden müssen, z.&nbsp;B. wenn Sie einen zweiten Pool bereitstellen ( <STRONG>pool02</STRONG> ), aber <STRONG>pool01</STRONG> die zentraler Verwaltungsserver-Rolle innehat. Die <STRONG>sysadmin</STRONG> -Gruppe (oder eine gleichwertige Gruppe) von SQL Server benötigt Berechtigungen für beide SQL Server-basierten Datenbanken.



3.  Öffnen Sie gegebenenfalls die Lync Server-Verwaltungsshell.

4.  Verwenden Sie das **Install-CsDatabase**-Cmdlet mit dem DatabasePathMap -Parameter und einer PowerShell-Hashtabelle, um die mit dem Topologie-Generator konfigurierten Datenbanken zu installieren.

5.  Im Beispielcode können die für die Datenbanken definierten Pfade mit dem -DatabasePathsMap -Parameter und einer definierten Hashtabelle wie folgt im Einzelfall bestimmt werden (in diesem Beispiel wird C:\\CSData für alle Datenbankdateien (MDF) sowie C:\\CSLogFiles für alle Protokolldateien (LDF) verwendet. Der Ordner wird bei Bedarf von Install-CsDatabase erstellt):
    
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
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathsMap $pathmap

6.  Für die Datenbank- und Protokolldateien ist der Speicherort auf dem Zieldatenbankserver explizit angegeben. Deshalb können Sie für den eigentlichen Datenbank- und Protokollspeicherort jedes Diensttyps ganz bestimmte Speicherorte definieren. Im folgenden Beispiel werden Datenbanken für jeden Diensttyp auf separaten Datenträgern gespeichert, und die zugehörigen Protokolldateien werden auf einem anderen Datenträgern gespeichert. Beispiel:
    
      - Alle RTC-Datenbanken im Verzeichnis D:\\RTCDatabase
    
      - Alle RTC-Protokolldateien im Verzeichnis E:\\RTCLogs
    
      - Alle Anwendungsspeicher-Datenbanken im Verzeichnis F:\\CPSDatabases
    
      - Alle Anwendungsspeicherprotokolle im Verzeichnis G:\\CPSLogs
    
      - Alle Reaktionsgruppenspeicher-Datenbanken im Verzeichnis H:\\RGSDatabases
    
      - Alle Reaktionsgruppenspeicher-Protokolle im Verzeichnis I:\\RGSLogs
    
      - Alle Adressbuchspeicher-Datenbanken im Verzeichnis J:\\ABSDatabases
    
      - Alle Adressbuchspeicher-Protokolldateien im Verzeichnis K:\\ABSLogs
    
      - Alle Archivierungsspeicher-Datenbanken im Verzeichnis L:\\ArchivingDatabases
    
      - Alle Archivierungsspeicherprotokolle im Verzeichnis M:\\ArchivingLogs
    
      - Alle Überwachungsspeicher-Datenbanken im Verzeichnis N:\\MonitoringDatabases
    
      - Alle Überwachungsspeicher-Protokolldateien im Verzeichnis O:\\MonitoringLogfiles
    
    <!-- end list -->
    
    ``` 
    
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
    
    Mit dem -DatabasePathMap -Parameter können Sie eine beliebige logische Laufwerkbuchstabenzuordnung definieren, welche die optimale Lösung im Hinblick auf die Leistungs- und Platzierungsanforderungen für SQL Server bietet.

Wenn Sie Ihre Datenbankdatendateien und Protokolldateien mithilfe der **DatabasePathMap**-Methode konfigurieren, müssen Sie das übliche Verfahren geringfügig ändern, falls Sie den Topologie-Generator verwenden. Normalerweise würden Sie Ihre Topologieoptionen definieren, die Topologie veröffentlichen und die Datenbankoptionen bereitstellen.

Falls Sie **DatabasePathMap** verwendet haben, haben Sie bereits den dritten Schritt des Verfahrens mit dem Topologie-Generator abgeschlossen. Für den Fall, dass ein vollständig konfigurierter Datenbankserver vorhanden ist, bevor Sie den Topologie-Generator ausführen, würden Sie weiterhin alle Ihre Serverrollen und Optionen definieren, aber die Option zum Erstellen der Datenbanken deaktivieren.

