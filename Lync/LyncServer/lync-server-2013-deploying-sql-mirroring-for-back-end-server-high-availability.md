---
title: 'Lync Server 2013: Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern'
TOCTitle: Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204992(v=OCS.15)
ms:contentKeyID: 49294361
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Damit eine SQL-Spiegelung implementiert werden kann, müssen Ihre Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen eingebundenen Servern (auf dem primären, dem Spiegelserver und dem Zeugen) ausgeführt werden. Ausführliche Informationen finden Sie unter [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x407).

Im Allgemeinen sind folgende Voraussetzungen nötig, um eine SQL-Spiegelung zwischen zwei Back-End-Servern mit einem Zeugen auszuführen:

  - Die Version von SQL Server, die auf dem primären Server ausgeführt wird, muss die SQL-Spiegelung unterstützen.

  - Prinzipal, Spiegel und Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server verwenden.

  - Prinzipal und Spiegel müssen dieselbe Version von SQL Server verwenden. Der Zeuge darf eine andere Version verwenden.

Weitere Informationen im Hinblick auf bewährte SQL-Verfahren zu den einzelnen unterstützten SQL-Versionen für die Zeugenrolle finden Sie unter „Datenbank-Spiegelungszeuge“ in der MSDN-Bibliothek unter [http://go.microsoft.com/fwlink/?linkid=247345\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=247345%26clcid=0x407).

Sie verwenden den Topologie-Generator für die Bereitstellung der SQL-Spiegelung. Sie wählen eine Option im Topologie-Generator zum Spiegeln der Datenbanken aus, und der Topologie-Generator richtet die Spiegelung ein (ggf. einschließlich eines Zeugen), sobald Sie die Topologie veröffentlichen. Beachten Sie, dass der Zeuge zum selben Zeitpunkt eingerichtet oder entfernt werden muss, zu dem Sie den Spiegel einrichten oder entfernen. Es gibt keinen separaten Befehl für die explizite Bereitstellung oder Entfernung eines Zeugen.

Wenn Sie eine Serverspiegelung konfigurieren möchten, müssen Sie zuerst die SQL-Datenbankberechtigungen korrekt einrichten. Ausführliche Informationen finden Sie unter „Einrichten von Anmeldekonten für die Datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server)“ unter [http://go.microsoft.com/fwlink/?linkid=268454\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268454%26clcid=0x407).

Bei der SQL-Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, d. h., Sie müssen die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern, um zu verhindern, dass der Speicherplatz auf den Back-End-Servern nicht zur Neige geht. Die Häufigkeit der Transaktionsprotokollsicherungen ist abhängig von der Wachstumsrate des Protokolls. Letztere richtet sich wiederum nach den Datenbanktransaktionen, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, dass Sie das zu erwartende Wachstum des Transaktionsprotokolls für Ihre Lync-Bereitstellungsarbeitsauslastung ermitteln und eine entsprechende Planung vornehmen können. In den folgenden Artikeln finden Sie zusätzliche Informationen zur SQL-Sicherung und Protokollverwaltung:

  - Datenbankwiederherstellungsmodelle: „Wiederherstellungsmodelle (SQL Server)“ unter [http://go.microsoft.com/fwlink/?linkid=268446\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268446%26clcid=0x407)

  - Sicherungsübersicht: „Übersicht über Sicherungen \[SQL Server\]“ unter [http://go.microsoft.com/fwlink/?linkid=268449\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268449%26clcid=0x407)

  - Transaktionsprotokollsicherung: „Sichern eines Transaktionsprotokolls (SQL Server)“ unter [http://go.microsoft.com/fwlink/?linkid=268452\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268452%26clcid=0x407)

Bei der SQL-Spiegelung können Sie die Topologie für die Spiegelung entweder beim Erstellen der Pools oder erst nach dem Erstellen der Pools konfigurieren.


> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten oder Entfernen einer SQL-Spiegelung wird nur unterstützt, wenn Prinzipal-, Spiegel- und (bei Bedarf) Zeugeninstanz derselben Domäne angehören. Wenn Sie die SQL-Spiegelung für Server einrichten möchten, die sich in unterschiedlichen Domänen befinden, erhalten Sie weitere Informationen in der Dokumentation zu SQL Server.




> [!IMPORTANT]
> Bei jeder Änderung an einer Spiegelungsbeziehung einer Back-End-Datenbank müssen Sie die Front-End-Server im Pool neu starten.<BR>Bei einer Änderung in Bezug auf die Spiegelung (z. B. Änderung des Speicherorts eines Spiegels) müssen Sie mit dem Topologie-Generator die folgenden drei Schritte ausführen: 
> <OL>
> <LI>
> <P>Entfernen Sie die Spiegelung vom alten Spiegelserver.</P>
> <LI>
> <P>Fügen Sie dem neuen Spiegelserver die Spiegelung hinzu.</P>
> <LI>
> <P>Veröffentlichen Sie die Topologie.</P></LI></OL>




> [!NOTE]
> Sie müssen eine Dateifreigabe erstellen, an die die Spiegeldateien geschrieben werden, und der Dienst, unter dem SQL Server und SQL Agent ausgeführt werden, benötigt Lese-/Schreibzugriff. Wenn der SQL Server-Dienst unter dem Netzwerkdienstkontext ausgeführt wird, können Sie &lt;Domain&gt;\\&lt;SQLSERVERNAME&gt;$ des Prinzipal- und des Spiegel-SQL-Servers zu den Freigabeberechtigungen hinzufügen. Das $-Zeichen ist wichtig, um anzugeben, dass es sich um ein Computerkonto handelt.



## So konfigurieren Sie die SQL-Spiegelung bei der Erstellung eines Pools im Topologie-Generator

1.  Klicken Sie auf der Seite **SQL-Speicher definieren** auf **Neu** neben dem Feld **SQL-Speicher** .

2.  Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den primären Speicher ein, wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelverbindung** aus, geben Sie die SQL-Spiegelportnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK** .

3.  Wählen Sie anschließend auf der Seite **SQL-Speicher definieren** die Option **SQL-Speicherspiegelung aktivieren** aus.

4.  Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den SQL-Speicher an, der als Spiegelinstanz verwendet wird. Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelverbindung** aus, geben Sie die Portnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK** .

5.  Wenn Sie einen Zeugen für diesen Spiegel verwenden möchten, führen Sie folgende Schritte aus:
    
    1.  Wählen Sie **SQL-Spiegelungszeugen zur Aktivierung des automatischen Failovers verwenden** aus.
    
    2.  Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **SQL-Spiegelungszeugen zur Aktivierung des automatischen Failovers verwenden** aus, und geben Sie dann den SQL-Speicher an, der als Zeuge verwendet werden soll.
    
    3.  Geben Sie die Portnummer an (Standardwert 7022), und klicken Sie auf **OK** .

6.  Nachdem Sie Ihren Front-End-Pool und alle weiteren Rollen in der Topologie definiert haben, können Sie die Topologie mit dem Topologie-Generator veröffentlichen. Wenn für den Front-End-Pool, auf dem der zentralen Verwaltungsspeicher gehostet wird, die SQL-Spiegelung aktiviert ist, wird nach der Veröffentlichung der Topologie eine Option angezeigt, um die primäre und die Spiegel-SQL-Speicherdatenbanken zu erstellen.
    
    Klicken Sie auf **Einstellungen** , und geben Sie den Pfad ein, um diesen als Dateifreigabe für die Spiegelungssicherung zu verwenden.
    
    Klicken Sie auf **OK** und anschließend auf **Weiter** , um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegel- und die Zeugeninstanz (sofern angegeben) werden bereitgestellt.

Sie können die Eigenschaften eines bereits bestehenden Pools mit dem Topologie-Generator bearbeiten, um die SQL-Spiegelung zu aktivieren.

## So fügen Sie die SQL-Spiegelung einem bestehenden Front-End-Pool im Topologie-Generator hinzu

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten** .

2.  Wählen Sie **SQL-Speicherspiegelung aktivieren** aus, und klicken Sie dann auf **Neu** neben **Spiegelungs-SQL-Speicher** .

3.  Geben Sie den SQL-Speicher an, der als Spiegel verwendet werden soll.

4.  Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelverbindung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 5022), und klicken Sie anschließend auf **OK** .

5.  Wenn Sie eine Zeugeninstanz konfigurieren möchten, wählen Sie **SQL-Spiegelungszeugen zur Aktivierung des automatischen Failovers verwenden** aus, und klicken Sie dann auf **Neu** .

6.  Geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll.

7.  Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelverbindung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 7022), und klicken Sie anschließend auf **OK** .

8.  Klicken Sie auf **OK** .

9.  Veröffentlichen Sie die Topologie. Dabei werden Sie zur Installation der Datenbank aufgefordert.
    
    Während der Topologieveröffentlichung werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL-Server, die an der Spiegelung teilnehmen, benötigen Lese-/Schreibzugriff auf diese Dateifreigabe, damit der Spiegel eingerichtet werden kann.

Sie müssen nun erst die Datenbank installieren, bevor Sie mit dem nächsten Schritt fortfahren können.

Bei der Einrichtung einer SQL-Spiegelung sollten Sie die folgenden Aspekte berücksichtigen:

  - Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird dieser unter Verwendung des definierten Ports erneut verwendet; die von Ihnen in der Topologie angegebenen Ports werden ignoriert.

  - Alle bereits anderen Anwendungen auf demselben Server zugewiesenen Ports, einschließlich der Ports für andere SQL-Instanzen, sollten nicht für die jeweils installierten SQL-Instanzen verwendet werden. Das bedeutet, wenn Sie mehr als eine SQL-Instanz auf demselben Server installiert haben, dürfen diese Instanzen nicht denselben Port für die Spiegelung verwenden. Ausführliche Informationen finden Sie in den folgenden Artikeln:
    
      - „Angeben einer Servernetzwerkadresse (Datenbankspiegelung)“ in der MSDN-Bibliothek unter [http://go.microsoft.com/fwlink/?linkid=247346\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=247346%26clcid=0x407)
    
      - „Der Datenbankspiegelungs-Endpunkt (SQL Server)“ unter [http://go.microsoft.com/fwlink/?linkid=247347\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=247347%26clcid=0x407)

## Verwenden von Lync Server-Verwaltungsshell-Cmdlets zum Einrichten der SQL-Spiegelung

Die einfachste Möglichkeit zur Einrichtung der Spiegelung besteht in der Verwendung des Topologie-Generators. Alternativ können Sie jedoch auch Cmdlets verwenden.

1.  Öffnen Sie ein Lync Server-Verwaltungsshell-Fenster, und führen Sie das folgende Cmdlet aus:
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Beispiel:
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    Folgendes wird angezeigt:
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  Überprüfen Sie die folgenden Punkte:
    
      - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem primären SQL-Server „e04-ocs.los\_a.lsipt.local\\rtc“ aktiviert ist.
    
      - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem SQL-Spiegelserver „K16-ocs.los\_a.lsipt.local\\rtc“ aktiviert ist.
    
      - Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem SQL-Zeugenserver „AB14-lct.los\_a.lsipt.local\\rtc“ aktiviert ist.
    
      - Konten, unter denen SQL Server auf den primären bzw. Spiegel-SQL-Servern ausgeführt werden, verfügen über Lese-/Schreibberechtigungen für die Dateifreigabe „\\\\E04-OCS\\csdatabackup“ .
    
      - Stellen Sie sicher, dass der Windows-Verwaltungsinstrumentationsanbieter (Windows Management Instrumentation, WMI) auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für die SQL Server-Dienste zu ermitteln, die auf den Prinzipal- und Zeugenservern ausgeführt werden.
    
      - Stellen Sie sicher, dass das Konto, unter dem dieses Cmdlet ausgeführt wird, für alle Spiegelserver die Berechtigung zum Erstellen von Ordnern für die Daten- und Protokolldateien hat.
    
      - Beachten Sie, dass das Benutzerkonto, das von der SQL-Instanz für die Ausführung verwendet wird, über eine Lese- und Schreibberechtigung für die Dateifreigabe verfügt. Wenn sich die Dateifreigabe auf einem anderen Server befindet und von der SQL-Instanz ein lokales Systemkonto ausgeführt wird, müssen Sie dem Server, auf dem die SQL-Instanz gehostet wird, Dateifreigabeberechtigungen gewähren.

3.  Geben Sie „A“ ein, und drücken Sie dann die EINGABETASTE.
    
    Die Spiegelung wird konfiguriert.

**Install-CsMirrorDatabase** installiert den Spiegel und konfiguriert die Spiegelung für alle Datenbanken, die im primären SQL-Speicher verfügbar sind. Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie dazu die Option „-DatabaseType“ verwenden. Wenn Sie die Spiegelung für fast alle Datenbanken mit nur wenigen Ausnahmen konfigurieren möchten, empfiehlt sich die Option „-ExcludeDatabaseList“ in Verbindung mit einer kommagetrennten Liste der Datenbanknamen, die von der Spiegelung ausgenommen werden sollen.

Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden alle Datenbanken außer „rtcab“ und „rtcxds“ gespiegelt.

`-ExcludeDatabaseList rtcab,rtcxds`

Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden nur die Datenbanken „rtcab“ , rtcshared“ und „rtcxds“ gespiegelt.

`-DatabaseType User`

## Entfernen oder Ändern der SQL-Spiegelung

Wenn Sie die SQL-Spiegelung eines Pools im Topologie-Generator entfernen möchten, müssen Sie zuerst mithilfe eines Cmdlets den Spiegel in SQL Server entfernen. Anschließend können Sie mithilfe des Topologie-Generators den Spiegel aus der Topologie entfernen. Verwenden Sie das folgenden Cmdlet, um den Spiegel in SQL Server zu entfernen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu verwerfen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Durch die Option `-DropExistingDatabasesOnMirror` werden die betreffenden Datenbanken aus dem Spiegel gelöscht.

Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool und dann auf **Eigenschaften bearbeiten** .

2.  Deaktivieren Sie **SQL-Speicherspiegelung aktivieren** , und klicken Sie auf **OK** .

3.  Veröffentlichen Sie die Topologie.

## Entfernen eines Spiegelungszeugen

Verwenden Sie das folgende Verfahren, um den Zeugen aus einer Back-End-Server-Spiegelungskonfiguration zu entfernen.

1.  Klicken Sie in Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten** .

2.  Deaktivieren Sie **SQL Server-Spiegelungszeugen zur Aktivierung des automatischen Failovers verwenden** , und klicken Sie auf **OK** .

3.  Veröffentlichen Sie die Topologie.
    
    Nach Veröffentlichung der Topologie wird im Topologie-Generator eine Meldung mitfolgendem Inhalt angezeigt:
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Führen Sie diesen Schritt jedoch nicht aus, und geben Sie nicht `Uninstall-CsMirrorDatabase` ein, weil dadurch die gesamte Spiegelungskonfiguration entfernt werden würde.

4.  Wenn Sie lediglich den Zeugen aus der SQL Server-Konfiguration entfernen möchten, befolgen Sie die Anweisungen im Abschnitt „Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung (SQL Server)“ unter [http://go.microsoft.com/fwlink/?linkid=268456\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268456%26clcid=0x407).

