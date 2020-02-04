---
title: 'Lync Server 2013: Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell'
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
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-06-16_

Die Trennung von Rollen und Zuständigkeiten zwischen Serveradministratoren und SQL Server-Administratoren kann zu Verzögerungen bei der Implementierung führen. Lync Server 2013 verwendet rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), um diese Probleme zu vermeiden. In einigen Fällen muss der SQL Server-Administrator die Installation von Datenbanken auf dem SQL Server-basierten Server außerhalb von RBAC verwalten. Die lync Server 2013-Verwaltungsshell bietet dem SQL Server-Administrator die Möglichkeit, Windows PowerShell-Cmdlets auszuführen, die zum Konfigurieren der Datenbanken mit den korrekten Daten und Protokolldateien entwickelt wurden. Ausführliche Informationen finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> Im folgenden Verfahren wird davon ausgegangen, dass mindestens die lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012-Verwaltungsobjekte, CLR-Typen für Microsoft SQL Server 2012 und Microsoft SQL Server 2012 ADOMD.NET installiert sind. Die OCSCore. msi-Datei befindet sich auf dem Installationsmedium im Verzeichnis \Setup\AMD64\Setup. Die restlichen Komponenten befinden sich in \setup\amd64. Darüber hinaus wurde die Active Directory-Vorbereitung für lync Server 2013 erfolgreich abgeschlossen.



</div>

" **Installieren-CsDatabase** " ist das Windows PowerShell-Cmdlet, mit dem Sie die Datenbanken installieren. Das Cmdlet " **install-CsDatabase** " verfügt über eine große Anzahl von Parametern, von denen nur einige hier besprochen werden. Details zu den möglichen Parametern finden Sie in der Dokumentation zur lync Server 2013-Verwaltungsshell.

<div class=" ">


> [!WARNING]  
> Um die Leistung und mögliche Timeoutprobleme zu vermeiden, sollten Sie immer vollqualifizierte Domänennamen (FQDNs) verwenden, wenn Sie auf SQL Server-basierte Server verweisen. Vermeiden Sie die Verwendung von Host Namen bezogenen verweisen. Verwenden Sie beispielsweise sqlbe01.contoso.net, aber vermeiden Sie die Verwendung von sqlbe01.



</div>

Für die Installation von Datenbanken verwendet **install-CsDatabase** drei primäre Methoden zum Platzieren der Datenbanken auf dem vorbereiteten SQL Server-basierten Server:

  - Führen Sie **install-CsDatabase** ohne DatabasePaths oder UseDefaultSqlPath aus. Das Cmdlet verwendet einen integrierten Algorithmus, um die beste Platzierung für das Protokoll und die Datendateien zu ermitteln. Der Algorithmus funktioniert nur für eigenständige SQL Server-Implementierungen.

  - Führen Sie **install-CsDatabase** mit dem DatabasePaths-Parameter aus. Der integrierte Algorithmus zum Optimieren von Protokoll-und Datendateispeicher Orten wird nicht verwendet, wenn der DatabasePaths-Parameter definiert ist. Mithilfe dieses Parameters können Sie die Speicherorte definieren, an denen Protokoll-und Datendateien bereitgestellt werden.

  - Führen Sie **install-CsDatabase** mit UseDefaultSqlPaths aus. Diese Option verwendet nicht den integrierten Algorithmus, um die Speicherorte für Protokolle und Datendateien zu optimieren. Protokoll-und Datendatei werden gemäß den vom SQL Server-Administrator gesetzten Standardeinstellungen bereitgestellt. Diese Pfade werden in der Regel für die automatische Verwaltung von Protokoll-und Datendateien auf dem SQL Server im Voraus eingestellt und sind nicht mit dem Setup von lync Server 2013 verbunden.

  - Der DatabasePathMap-Parameter kann auch verwendet werden, um einen Speicherort für jede Datenbank und die zugehörige Protokolldatei explizit anzugeben.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren des SQL Server Central-Verwaltungsspeichers

1.  Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an. Ausführliche Informationen finden Sie unter [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Öffnen Sie die lync Server 2013-Verwaltungsshell. Wenn Sie die Ausführungsrichtlinie für Windows PowerShell nicht angepasst haben, müssen Sie die Richtlinie so anpassen, dass Windows PowerShell-Skripts ausgeführt werden können. Ausführliche Informationen finden Sie unter "Überprüfen der Ausführungsrichtlinie" [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)unter.

3.  Verwenden Sie das Cmdlet " **install-CsDatabase** ", um den zentralen Verwaltungsspeicher zu installieren.
    
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
    > Der Berichtsparameter ist optional, aber hilfreich, wenn Sie den Installationsvorgang dokumentieren.

    
    </div>

4.  **Install-CsDatabase – DatabasePaths** kann bis zu sechs Pfadparameter verwenden, die jeweils die Pfade für die Laufwerke definieren, wie Sie in SQL Server-Daten und in der Protokolldatei Platzierung definiert sind. Nach den logischen Regeln der Datenbankkonfiguration in lync Server 2013 werden Laufwerke in Buckets von zwei, vier oder sechs analysiert. Je nach SQL Server-Konfiguration und Anzahl der Buckets werden zwei Pfade, vier Pfade oder sechs Pfade bereitgestellt.
    
    Wenn Sie über drei Laufwerke verfügen, erhält das Protokoll Priorität, und danach werden die Datendateien verteilt. Ein Beispiel für einen auf SQL Server basierenden Server, der mit sechs Laufwerken konfiguriert ist:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Nach Abschluss der Datenbankinstallation können Sie die lync Server 2013-Verwaltungsshell schließen oder mit der Installation der im Topologie-Generator definierten lync Server 2013-Datenbanken fortfahren.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der konfigurierten SQL Server-Topologie für Datenbanken

1.  Zum Installieren des Topologie-Generators, der für lync Server 2013 konfiguriert ist, muss der lync Server 2013-Administrator die Topologie veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md) in der Bereitstellungsdokumentation.

2.  Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an. Lesen Sie das Thema [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Um die SQL Server-basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server-Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe Sysadmins (oder Äquivalent) auf dem Server ist, auf dem SQL Server ausgeführt wird, und die zentrale Verwaltung verwaltet. Server Rolle. Dies ist besonders wichtig, um nach weiteren lync Server 2013-Pools zu suchen, die eine SQL Server-Datenbankinstallation oder-Konfiguration erfordern. Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle aber von pool01 gehalten wird. Die SQL Server-Gruppe sysadmin (oder eine entsprechende) muss über Berechtigungen für beide SQL Server-basierten Datenbanken verfügen.

    
    </div>

3.  Öffnen Sie die lync Server 2013-Verwaltungsshell, wenn Sie noch nicht geöffnet ist.

4.  Verwenden Sie das Cmdlet " **install-CsDatabase** ", um die konfigurierten Datenbanken des Topologie-Generators zu installieren.
    
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
    > Der Berichtsparameter ist optional, aber hilfreich, wenn Sie den Installationsvorgang dokumentieren.

    
    </div>

5.  Wenn die Datenbankinstallation abgeschlossen ist, schließen Sie die lync Server 2013-Verwaltungsshell.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>So verwenden Sie Windows PowerShell-Cmdlets zum Konfigurieren der SQL Server-Topologie mithilfe des DatabasePathMap-Parameters

1.  Zum Installieren von Datenbanken für lync Server 2013 muss der lync Server-Administrator die Pfade erstellen und die Datenbankendateien und Protokolldateien entsprechend einem vordefinierten Satz von Regeln bereitstellen.

2.  Melden Sie sich auf einem beliebigen Computer mit administrativen Anmeldeinformationen für die Erstellung der Datenbanken auf dem SQL Server-basierten Server an. Lesen Sie das Thema [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Um die SQL Server-basierten Datenbanken konfigurieren zu können, müssen Sie sicherstellen, dass das SQL Server-Administratorkonto, das zum Ausführen der hier beschriebenen Schritte verwendet wird, auch ein Mitglied der Gruppe Sysadmins (oder Äquivalent) auf dem Server ist, auf dem SQL Server ausgeführt wird, und die zentrale Verwaltung verwaltet. Server Rolle. Dies ist besonders wichtig, um nach weiteren lync Server-Pools zu suchen, die eine SQL Server-Datenbankinstallation oder-Konfiguration erfordern. Wenn Sie beispielsweise einen zweiten Pool (pool02) bereitstellen, die zentrale Verwaltungs Server Rolle aber von pool01 gehalten wird. Die SQL Server-Gruppe sysadmin (oder eine entsprechende) muss über Berechtigungen für beide SQL Server-basierten Datenbanken verfügen.

    
    </div>

3.  Öffnen Sie die lync Server-Verwaltungsshell, wenn Sie noch nicht geöffnet ist.

4.  Verwenden Sie das Cmdlet **install-CsDatabase** mit dem DatabasePathMap-Parameter und einer PowerShell-Hashtabelle, um die konfigurierten Datenbanken des Topologie-Generators zu installieren.

5.  Im Beispielcode können die für die Datenbanken definierten Pfade auf granulare Weise mithilfe des – DatabasePathMap-Parameters und einer definierten Hashtabelle wie folgt bestimmt werden (im Beispiel wird "c\\: CSData" für alle Datenbankdateien (MDF) und "c:\\CSLogFiles" für alle Protokolldateien (LDF) verwendet. Der Ordner wird nach Bedarf von install-CsDatabase erstellt):
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
6.  Da die Datenbank-und Protokolldateien explizit mit ihrem Speicherort auf dem Zieldatenbankserver benannt sind, können Sie bestimmte Speicherorte für die tatsächliche Datenbank und den Speicherort des jeweiligen Diensttyps definieren. Im folgenden Beispiel werden Datenbanken für jeden bestimmten Diensttyp auf separaten Datenträgern und zugehörigen Protokolldateien auf einer anderen Festplatte platziert. Beispiel:
    
      - Alle RTC-Datenbanken auf "\\D: RTCDatabase"
    
      - Alle RTC-Protokolldateien auf "E\\: RTCLogs"
    
      - Alle Anwendungsspeicher Datenbanken auf "F:\\CPSDatabases"
    
      - Alle Anwendungsspeicher Protokolle auf "G:\\CPSLogs"
    
      - Alle Antwortgruppen speichern Datenbanken auf "H\\: RGSDatabases"
    
      - Alle Reaktionsgruppen Speicherprotokolle auf "I:\\RGSLogs"
    
      - Alle Adressbuchspeicher Datenbanken auf "J:\\ABSDatabases"
    
      - Alle Adressbuchspeicher-Protokolldateien in "K\\: ABSLogs"
    
      - Alle Archivierungsspeicher Datenbanken auf "L:\\ArchivingDatabases"
    
      - Alle Archivierungsspeicher Protokolle auf "M:\\ArchivingLogs"
    
      - Alle Überwachungsspeicher Datenbanken auf "N:\\MonitoringDatabases"
    
      - Alle Überwachungsspeicher-Protokolldateien auf "O\\: MonitoringLogfiles"
    
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
    
    Mithilfe des-DatabasePathMap-Parameters können Sie eine beliebige Kombination aus logischem Laufwerksbuchstaben definieren, die die beste Lösung für Ihre Leistungs-und Platzierungs Anforderungen in SQL Server bietet.

Wenn Sie Ihre Datenbankdateien und Protokolldateien mithilfe der **DatabasePathMap** -Methode konfigurieren, müssen Sie bei Verwendung des Topologie-Generators eine geringfügige Änderung an Ihrem normalen Prozess vornehmen. In der Regel definieren Sie Ihre Topologie-Auswahl, veröffentlichen die Topologie und wählen, wie die Datenbankauswahl bereitgestellt wird.

Wenn Sie **DatabasePathMap** verwendet haben, haben Sie bereits den dritten Teil des Topologie-Builder-Prozesses erfüllt. Wenn Sie vor dem Ausführen des Topologie-Generators einen vollständig konfigurierten Datenbankserver besitzen, würden Sie weiterhin alle Serverrollen und-Optionen definieren, aber die Option zum Erstellen der Datenbanken deaktivieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

