---
title: Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a37c554faf81795363522378160abf5081084f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-08_

Damit eine SQL-Spiegelung bereitgestellt werden kann, müssen Ihre Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern (primärer Server, Spiegel und Zeuge) ausgeführt werden. Ausführliche Informationen finden Sie [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)unter.

Im Allgemeinen müssen folgende Voraussetzungen erfüllt sein, um eine SQL-Spiegelung zwischen zwei Back-End-Servern mit einem Zeugen auszuführen:

  - Die Version von SQL Server, die auf dem primären Server ausgeführt wird, muss die SQL-Spiegelung unterstützen.

  - Prinzipal, Spiegel und Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server verwenden.

  - Prinzipal und Spiegel müssen dieselbe Version von SQL Server verwenden. Der Zeuge darf eine andere Version verwenden.

Informationen zu SQL-bewährten Methoden in Bezug auf die Unterstützung von SQL-Versionen für eine Zeugenrolle finden Sie unter "Daten Bank Spiegelungs [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)Zeuge" in der MSDN Library unter.

Sie verwenden den Topologie-Generator zum Bereitstellen der SQL-Spiegelung. Sie wählen eine Option im Topologie-Generator aus, um die Datenbanken zu spiegeln, und der Topologie-Generator richtet die Spiegelung (einschließlich der Einrichtung eines Zeugen bei Bedarf) ein, wenn Sie die Topologie veröffentlichen. Beachten Sie, dass Sie den Zeugen zum selben Zeitpunkt wie den Spiegel einrichten oder entfernen müssen. Es gibt keinen separaten Befehl, mit dem Sie nur einen Zeugen bereitstellen oder entfernen können.

Wenn Sie eine Serverspiegelung konfigurieren möchten, müssen Sie zuerst die SQL-Datenbankberechtigungen korrekt einrichten. Ausführliche Informationen finden Sie unter "Einrichten von Anmeldekonten für Datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454))" unter.

Bei der SQL-Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, d. h. Sie müssen die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern, um zu verhindern, dass der Speicherplatz auf den Back-End-Servern zur Neige geht. Die Häufigkeit der Transaktionsprotokollsicherungen ist abhängig von der Wachstumsrate des Protokolls. Letztere richtet sich wiederum nach den Datenbanktransaktionen, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, dass Sie das zu erwartende Wachstum des Transaktionsprotokolls für Ihre Lync-Bereitstellungsarbeitsauslastung ermitteln und eine entsprechende Planung vornehmen. In den folgenden Artikeln finden Sie zusätzliche Informationen zur SQL-Sicherung und Protokollverwaltung:

  - Daten Bank Wiederherstellungsmodelle: "Wiederherstellungsmodelle (SQL Server)" unter[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)

  - Übersicht über Backup: "Übersicht über Sicherungen (SQL Server)" unter[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)

  - Backup-Transaktionsprotokoll: "Sichern eines Transaktionsprotokolls (SQL Server)" unter[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)

Bei der SQL-Spiegelung können Sie die Topologie für die Spiegelung entweder beim Erstellen der Pools oder erst nach dem Erstellen der Pools konfigurieren.



> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die Server für primär-, Spiegel-und Zeugen (falls erwünscht) zur gleichen Domäne gehören. Wenn Sie die SQL-Spiegelung für Server einrichten möchten, die sich in unterschiedlichen Domänen befinden, erhalten Sie weitere Informationen in der Dokumentation zu SQL Server.





> [!IMPORTANT]
> Bei jeder Änderung an einer Spiegelungsbeziehung einer Back-End-Datenbank müssen Sie alle Front-End-Server im Pool neu starten. <BR>Wenn Sie eine Änderung der Spiegelung vornehmen möchten (beispielsweise die Position einer Spiegelung ändern), müssen Sie den Topologie-Generator verwenden, um diese drei Schritte auszuführen: 
> <OL>
> <LI>
> <P>Entfernen Sie die Spiegelung vom alten Spiegelserver.</P>
> <LI>
> <P>Fügen Sie dem neuen Spiegelserver die Spiegelung hinzu.</P>
> <LI>
> <P>Veröffentlichen Sie die Topologie.</P></LI></OL>




> [!NOTE]
> Sie müssen eine Dateifreigabe erstellen, in die die Spiegeldateien geschrieben werden, und der Dienst, unter dem SQL Server und SQL Agent ausgeführt werden, benötigt Lese-/Schreibzugriff. Wenn der SQL Server-Dienst unter dem Kontext des Netzwerkdiensts ausgeführt wird, können Sie &lt;den&gt; Freigabe &lt;Berechtigungen Domänen&#92;&gt;sqlservername $ sowohl der Prinzipal-als auch der Spiegelungs-SQL-Server hinzufügen. Das $-Zeichen ist wichtig, um anzugeben, dass es sich um ein Computerkonto handelt.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>So konfigurieren Sie die SQL-Spiegelung beim Erstellen eines Pools im Topologie-Generator

1.  Klicken Sie auf der Seite **SQL-Speicher definieren** neben dem Feld **SQL-Speicher** auf **Neu**. 

2.  Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den primären Speicher ein, wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die SQL-Spiegelportnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.

3.  Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **SQL-Speicherspiegelung aktivieren** aus. 

4.  Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den SQL-Speicher an, der als Spiegel verwendet werden soll. Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.

5.  Wenn Sie einen Zeugen für diesen Spiegel verwenden möchten, führen Sie folgende Schritte aus: 
    
    1.  Wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus. 
    
    2.  Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. 
    
    3.  Geben Sie die Portnummer an (Standardwert 7022), und klicken Sie auf **OK**. 

6.  Nachdem Sie die Definition des Front-End-Pools und aller anderen Rollen in Ihrer Topologie abgeschlossen haben, verwenden Sie den Topology Builder zum Veröffentlichen der Topologie. Wenn die Topologie veröffentlicht wird und der Front-End-Pool, in dem der zentrale Verwaltungsspeicher gehostet wird, die SQL-Spiegelung aktiviert hat, wird eine Option zum Erstellen von primären und Spiegel-SQL Store-Datenbanken angezeigt.
    
    Klicken Sie auf **Einstellungen**, und geben Sie den Pfad ein, den Sie als Dateifreigabe für die Spiegelungssicherung verwenden möchten.
    
    Klicken Sie auf **OK** und anschließend auf **Weiter**, um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegel- und die Zeugeninstanz (sofern angegeben) werden bereitgestellt.

Mithilfe des Topologie-Generators können Sie die Eigenschaften eines bereits vorhandenen Pools bearbeiten, um die SQL-Spiegelung zu ermöglichen.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>So fügen Sie eine SQL-Spiegelung zu einem vorhandenen Front-End-Pool im Topologie-Generator hinzu

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Wählen Sie **SQL-Speicherspiegelung aktivieren** aus, und klicken Sie dann neben **Spiegelungs-SQL-Speicher** auf **Neu**. 

3.  Geben Sie den SQL-Speicher an, der als Spiegel verwendet werden soll. 

4.  Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 5022), und klicken Sie anschließend auf **OK**.

5.  Wenn Sie einen Zeugen konfigurieren möchten, wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und klicken Sie dann auf **Neu**. 

6.  Geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. 

7.  Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 7022), und klicken Sie anschließend auf **OK**.

8.  Klicken Sie anschließend auf **OK**.

9.  Veröffentlichen Sie die Topologie. Dabei werden Sie zur Installation der Datenbank aufgefordert. 
    
    Während der Topologieveröffentlichung werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL-Server, die an der Spiegelung teilnehmen, benötigen Lese-/Schreibzugriff auf diese Dateifreigabe, damit der Spiegel eingerichtet werden kann.

Sie müssen nun erst die Datenbank installieren, bevor Sie mit dem nächsten Schritt fortfahren können.

Bei der Einrichtung einer SQL-Spiegelung sollten Sie die folgenden Aspekte berücksichtigen:

  - Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird dieser mit den definierten Ports erneut verwendet. Die von Ihnen in der Topologie angegebenen Ports werden ignoriert.

  - Alle bereits anderen Anwendungen auf demselben Server zugewiesenen Ports, einschließlich der Ports für andere SQL-Instanzen, sollten nicht für die jeweils installierten SQL-Instanzen verwendet werden. Das bedeutet, wenn mehrere SQL-Instanzen auf demselben Server installiert sind, dürfen diese Instanzen nicht denselben Port für die Spiegelung verwenden. Ausführliche Informationen finden Sie in den folgenden Artikeln:
    
      - "Geben Sie eine Server-Netzwerkadresse (Datenbankspiegelung)" in der MSDN Library unter[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "Der Endpunkt der Datenbankspiegelung (SQL Server)" unter[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Verwenden von Cmdlets der lync Server-Verwaltungsshell zum Einrichten der SQL-Spiegelung

Die einfachste Möglichkeit zum Einrichten der Spiegelung ist die Verwendung des Topologie-Generators, Sie können dies aber auch mithilfe von Cmdlets vornehmen.

1.  Öffnen Sie ein lync Server-Verwaltungsshell-Fenster, und führen Sie das folgende Cmdlet aus:
    
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
    
      - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im primären SQL Server E04-OCS\_. Los a. lsipt\\. local RTC aktiviert ist.
    
      - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Mirror SQL Server K16-OCS\_. Los a. lsipt\\. local RTC aktiviert ist.
    
      - Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Zeugen SQL Server AB14-LCT\_. Los a. lsipt\\. local RTC aktiviert ist.
    
      - Konten, auf denen die SQL-Server auf allen Primär-und Spiegelservern ausgeführt werden, verfügen über Lese \\ \\-/Schreibzugriff auf\\die Dateifreigabe E04-OCS-csdatabackup
    
      - Stellen Sie sicher, dass der Windows-Verwaltungsinstrumentationsanbieter (Windows Management Instrumentation, WMI) auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für die SQL Server-Dienste zu ermitteln, die auf allen primären, Spiegel- und Zeugenservern ausgeführt werden. 
    
      - Stellen Sie sicher, dass das Konto, unter dem dieses Cmdlet ausgeführt wird, für alle Spiegelserver über die Berechtigung zum Erstellen von Ordnern für die Daten- und Protokolldateien verfügt. 
    
      - Beachten Sie, dass das Benutzerkonto, unter dem die SQL-Instanz ausgeführt wird, über die Lese-/Schreibberechtigung für die Dateifreigabe verfügt. Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL-Instanz unter einem lokalen Systemkonto ausgeführt wird, müssen Sie dem Server, auf dem die SQL-Instanz gehostet wird, Dateifreigabeberechtigungen erteilen.

3.  Geben Sie „A“ ein, und drücken Sie dann die EINGABETASTE.
    
    Die Spiegelung wird konfiguriert.

**Install-CsMirrorDatabase** installiert die Spiegelung und konfiguriert die Spiegelung für alle Datenbanken, die im primären SQL Store vorhanden sind. Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie die Option – DatabaseType verwenden, oder wenn Sie die Spiegelung für alle Datenbanken mit Ausnahme einiger weniger konfigurieren möchten, können Sie die Option-ExcludeDatabaseList zusammen mit einer durch Trennzeichen getrennten Liste der Datenbank verwenden. auszuschließende Namen.

Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden alle Datenbanken außer „rtcab“ und „rtcxds“ gespiegelt.

`-ExcludeDatabaseList rtcab,rtcxds`

Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden nur die Datenbanken „rtcab“, „rtcshared“ und „rtcxds“ gespiegelt.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Entfernen oder Ändern der SQL-Spiegelung

Wenn Sie die SQL-Spiegelung eines Pools im Topologie-Generator entfernen möchten, müssen Sie zuerst mithilfe eines Cmdlets den Spiegel in SQL Server entfernen. Anschließend können Sie mithilfe des Topologie-Generators den Spiegel aus der Topologie entfernen. Verwenden Sie das folgende Cmdlet, um den Spiegel in SQL Server zu entfernen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu verwerfen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Die `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betroffenen Datenbanken aus der Spiegelung gelöscht werden.

Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Deaktivieren Sie **SQL-Speicherspiegelung aktivieren**, und klicken Sie dann auf **OK**.

3.  Veröffentlichen Sie die Topologie.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Entfernen eines Spiegelungszeugen

Verwenden Sie dieses Verfahren, wenn Sie den Zeugen aus einer Back-End-Server Spiegelungskonfiguration entfernen müssen.

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Deaktivieren Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, und klicken Sie auf **OK**.

3.  Veröffentlichen Sie die Topologie.
    
    Nach der Veröffentlichung der Topologie wird in der Topologie-Builder eine Meldung angezeigt, die Folgendes enthält:
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Führen Sie diesen Schritt jedoch nicht aus, und geben `Uninstall-CsMirrorDatabase` Sie nicht so ein, dass die gesamte Spiegelungskonfiguration deinstalliert wird.

4.  Wenn Sie nur den Zeugen aus der SQL Server-Konfiguration entfernen möchten, folgen Sie den Anweisungen unter "Entfernen des Zeugen aus einer Datenbankspiegelungssitzung ( [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)SQL Server)" unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

