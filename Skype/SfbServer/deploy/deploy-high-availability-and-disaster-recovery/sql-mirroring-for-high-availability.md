---
title: Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: Damit eine SQL-Spiegelung bereitgestellt werden kann, müssen Ihre Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern (primärer Server, Spiegel und Zeuge) ausgeführt werden. Weitere Informationen hierzu finden Sie unter kumulative Paket 9 für SQL Server 2008 Service Pack 1 aktualisiert.
ms.openlocfilehash: ae34271fc85b16e411daa39d4b087508186d6ff6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894605"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Bereitstellen von SQL-Spiegelung für hohe Verfügbarkeit in Skype Back-End-Server für Business Server 2015


Damit eine SQL-Spiegelung bereitgestellt werden kann, müssen Ihre Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern (primärer Server, Spiegel und Zeuge) ausgeführt werden. Weitere Informationen hierzu finden Sie unter [kumulative Paket 9 für SQL Server 2008 Service Pack 1 zu aktualisieren ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

Im Allgemeinen müssen folgende Voraussetzungen erfüllt sein, um eine SQL-Spiegelung zwischen zwei Back-End-Servern mit einem Zeugen auszuführen:

- Der primäre Server-Version von SQL Server muss SQL-Spiegelung unterstützen.

- Prinzipal, Spiegel und Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server verwenden.

- Prinzipal und Spiegel müssen dieselbe Version von SQL Server verwenden. Der Zeuge darf eine andere Version verwenden.

Best Practices für SQL im Hinblick auf die für eine Rolle Zeugen welche SQL-Versionen unterstützt werden finden Sie unter [Datenbank-Spiegelungszeuge](https://go.microsoft.com/fwlink/p/?LinkId=247345).

Sie verwenden die Topologie-Generator zum Bereitstellen von SQL-Spiegelung. Wählen Sie eine Option im Topologie-Generator zu spiegelnden Datenbanken und Topologie-Generator richtet die Spiegelung (einschließlich der Einrichtung von ein Zeuge wie gewünscht) Wenn Sie die Topologie veröffentlichen. Beachten Sie, dass Sie den Zeugen zum selben Zeitpunkt wie den Spiegel einrichten oder entfernen müssen. Es gibt keinen separaten Befehl, mit dem Sie nur einen Zeugen bereitstellen oder entfernen können.

Wenn Sie eine Serverspiegelung konfigurieren möchten, müssen Sie zuerst die SQL-Datenbankberechtigungen korrekt einrichten. Weitere Informationen hierzu finden Sie unter [Von Anmeldung Konten für Database Mirroring oder AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).

Bei der SQL-Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, d. h., Sie müssen die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern. Damit verhindern Sie, dass der Speicherplatz auf den Datenträgern der Back-End-Server zur Neige geht. Die Häufigkeit der Transaktionsprotokollsicherungen ist abhängig von der Wachstumsrate des Protokolls. Letztere richtet sich wiederum nach den Datenbanktransaktionen, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, das zu erwartende Wachstum des Transaktionsprotokolls für Ihre Bereitstellungsarbeitsauslastung zu ermitteln und entsprechend zu planen. In den folgenden Artikeln finden Sie zusätzliche Informationen zur SQL-Sicherung und Protokollverwaltung:

- [Wiederherstellungsmodelle für Datenbanken](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [Sicherung (Übersicht)](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [Transaktionsprotokoll sichern](https://go.microsoft.com/fwlink/p/?LinkId=268452)

Bei der SQL-Spiegelung können Sie die Topologie für die Spiegelung entweder beim Erstellen der Pools oder erst nach dem Erstellen der Pools konfigurieren.

> [!IMPORTANT]
> Über Topologie-Generator oder Cmdlets zum Einrichten und Entfernen von SQL-Spiegelung werden nur, wenn die primäre, Spiegel und Zeuge (sofern gewünscht) Server derselben Domäne angehören. Wenn Sie die SQL-Spiegelung für Server einrichten möchten, die sich in unterschiedlichen Domänen befinden, erhalten Sie weitere Informationen in der Dokumentation zu SQL Server.

> [!IMPORTANT]
> Bei jeder Änderung an einer Spiegelungsbeziehung einer Back-End-Datenbank müssen Sie alle Front-End-Server im Pool neu starten.  > für eine Änderung der Spiegelung, (z. B. "ändern den Speicherort der Spiegelung), Sie müssen Topologie-Generator zum Verwenden dieser drei Schritte ausführen:

1. Entfernen Sie die Spiegelung vom alten Spiegelserver.

2. Fügen Sie dem neuen Spiegelserver die Spiegelung hinzu.

3. Veröffentlichen Sie die Topologie.

> [!NOTE]
> Sie müssen eine Dateifreigabe erstellen, in die die Spiegeldateien geschrieben werden, und der Dienst, unter dem SQL Server und SQL Agent ausgeführt werden, benötigt Lese-/Schreibzugriff. Wenn der SQL Server-Dienst im Kontext des Netzwerkdienst ausgeführt wird, können Sie hinzufügen \<Domäne\>\\<SQLSERVERNAME\>$ von Haupt- und SQL-Spiegelserver an die Freigabeberechtigungen. Das $-Zeichen ist wichtig, um anzugeben, dass es sich um ein Computerkonto handelt.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>So konfigurieren Sie SQL-Spiegelung bei der Erstellung eines Pools im Topologie-Generator

1. Klicken Sie auf der Seite **SQL-Speicher definieren** neben dem Feld **SQL-Speicher** auf **Neu**. 

2. Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den primären Speicher ein, wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die SQL-Spiegelportnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.

3. Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **SQL-Speicherspiegelung aktivieren** aus. 

4. Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den SQL-Speicher an, der als Spiegel verwendet werden soll. Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.

5. Wenn Sie einen Zeugen für diesen Spiegel verwenden möchten, führen Sie folgende Schritte aus: 

    a. Wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus. 

    b. Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. 

    c. Geben Sie die Portnummer an (Standardwert 7022), und klicken Sie auf **OK**. 

6. Sobald Sie fertig sind definieren des Front-End-Pools und alle anderen Rollen in Ihrer Topologie Topologie-Generator verwenden, um die Topologie zu veröffentlichen. Wenn die Topologie, veröffentlicht wird Wenn der Front-End-Pool, auf dem zentralen Verwaltungsspeicher gehostet hat, SQL-Spiegelung aktiviert, sehen Sie eine Option zum Erstellen von Primär- und SQL-Datenbanken im Verzeichnis zu spiegeln.

    Klicken Sie auf **Einstellungen**, und geben Sie den Pfad ein, den Sie als Dateifreigabe für die Spiegelungssicherung verwenden möchten.

    Klicken Sie auf **OK** und anschließend auf **Weiter**, um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegel- und die Zeugeninstanz (sofern angegeben) werden bereitgestellt.

Topologie-Generator können zum Bearbeiten der Eigenschaften eines bereits bestehenden Pools zu SQL-Spiegelung zu aktivieren.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Hinzufügen des SQL-Spiegelung einem bestehenden Front-End-Pool im Topologie-Generator

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2. Wählen Sie **SQL-Speicherspiegelung aktivieren** aus, und klicken Sie dann neben **Spiegelungs-SQL-Speicher** auf **Neu**. 

3. Geben Sie den SQL-Speicher an, der als Spiegel verwendet werden soll. 

4. Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 5022), und klicken Sie anschließend auf **OK**.

5. Wenn Sie einen Zeugen konfigurieren möchten, wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und klicken Sie dann auf **Neu**. 

6. Geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. 

7. Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 7022), und klicken Sie anschließend auf **OK**.

8. Klicken Sie anschließend auf **OK**.

9. Veröffentlichen Sie die Topologie. Dabei werden Sie zur Installation der Datenbank aufgefordert. 

    Während der Topologieveröffentlichung werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL-Server, die an der Spiegelung teilnehmen, benötigen Lese-/Schreibzugriff auf diese Dateifreigabe, damit der Spiegel eingerichtet werden kann.

Sie müssen nun erst die Datenbank installieren, bevor Sie mit dem nächsten Schritt fortfahren können.

Bei der Einrichtung einer SQL-Spiegelung sollten Sie die folgenden Aspekte berücksichtigen:

- Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird dieser mit den definierten Ports erneut verwendet. Die von Ihnen in der Topologie angegebenen Ports werden ignoriert.

- Alle bereits anderen Anwendungen auf demselben Server zugewiesenen Ports, einschließlich der Ports für andere SQL-Instanzen, sollten nicht für die jeweils installierten SQL-Instanzen verwendet werden. Das bedeutet, wenn mehrere SQL-Instanzen auf demselben Server installiert sind, dürfen diese Instanzen nicht denselben Port für die Spiegelung verwenden. Ausführliche Informationen finden Sie in den folgenden Artikeln:

  - [Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [Die Datenbank Spiegelung Endpunkt (SQLServer)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Verwenden von Skype für Business Server 2015-Verwaltungsshell-Cmdlets zum Set Up SQL-Spiegelung

Die einfachste Möglichkeit zum Einrichten der Spiegelung wird mithilfe des Topologie-Generator, aber Sie können auch hierfür Cmdlets verwenden.

1. Öffnen Sie eine Skype für Business Server 2015-Verwaltungsshell-Fenster, und führen Sie das folgende Cmdlet aus:

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Beispiel:

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Folgendes wird angezeigt:

   <pre>
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
   </pre>

2. Überprüfen Sie die folgenden Punkte:

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem primären SQL-Server „e04-ocs.los_a.lsipt.local\rtc“ aktiviert ist. 

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem SQL-Spiegelserver „K16-ocs.los_a.lsipt.local\rtc“ aktiviert ist. 

    - Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem SQL-Zeugenserver „AB14-lct.los_a.lsipt.local\rtc“ aktiviert ist. 

   - Ausführen des SQL Server auf allen primären und SQL-Spiegelserver Konten haben Lese-/Schreibberechtigung für die Dateifreigabe \\E04 OCS\csdatabackup

   - Stellen Sie sicher, dass der Windows-Verwaltungsinstrumentationsanbieter (Windows Management Instrumentation, WMI) auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für die SQL Server-Dienste zu ermitteln, die auf allen primären, Spiegel- und Zeugenservern ausgeführt werden. 

   - Stellen Sie sicher, dass das Konto, unter dem dieses Cmdlet ausgeführt wird, für alle Spiegelserver über die Berechtigung zum Erstellen von Ordnern für die Daten- und Protokolldateien verfügt. 

   - Beachten Sie, dass das Benutzerkonto, unter dem die SQL-Instanz ausgeführt wird, über die Lese-/Schreibberechtigung für die Dateifreigabe verfügt. Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL-Instanz unter einem lokalen Systemkonto ausgeführt wird, müssen Sie dem Server, auf dem die SQL-Instanz gehostet wird, Dateifreigabeberechtigungen erteilen.

3. Geben Sie „A“ ein, und drücken Sie dann die EINGABETASTE.

    Die Spiegelung wird konfiguriert.

    **Install-csmirrordatabase anfügen** Spiegel installiert und konfiguriert die Spiegelung für alle Datenbanken, die auf dem primären SQL-Speicher vorhanden sind. Wenn Sie nur bestimmte Datenbanken für die Spiegelung konfigurieren möchten, können Sie die Option "databasetype"-, oder wenn Sie für alle Datenbanken mit Ausnahme von ein paar Spiegelung konfigurieren möchten, können Sie die Option - ExcludeDatabaseList zusammen mit einer durch Trennzeichen getrennte Liste der Datenbank verwenden Namen, ausgeschlossen werden sollen.

    Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden alle Datenbanken außer „rtcab“ und „rtcxds“ gespiegelt.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden nur die Datenbanken „rtcab“, „rtcshared“ und „rtcxds“ gespiegelt.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Entfernen oder Ändern der SQL-Spiegelung

Wenn Sie die SQL-Spiegelung eines Pools im Topologie-Generator entfernen möchten, müssen Sie zuerst mithilfe eines Cmdlets den Spiegel in SQL Server entfernen. Anschließend können Sie mithilfe des Topologie-Generators den Spiegel aus der Topologie entfernen. Verwenden Sie das folgende Cmdlet, um den Spiegel in SQL Server zu entfernen:

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu verwerfen:

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

Die `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betreffenden Datenbanken aus dem Spiegel gelöscht werden soll.

Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2. Deaktivieren Sie **SQL-Speicherspiegelung aktivieren**, und klicken Sie dann auf **OK**.

3. Veröffentlichen Sie die Topologie.

## <a name="removing-a-mirroring-witness"></a>Entfernen eines Spiegelungszeugen

Verwenden Sie dieses Verfahren, wenn Sie benötigen, um den Zeugen aus einem Back End-Server Spiegelungskonfiguration zu entfernen.

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2. Deaktivieren Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, und klicken Sie auf **OK**.

3. Veröffentlichen Sie die Topologie.

    Nach der Veröffentlichung der Topologie, Topologie-Generator sehen Sie eine Nachricht, die Folgendes enthält,

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Führen Sie diesen Schritt nicht jedoch, und geben Sie keine `Uninstall-CsMirrorDatabase` wie, die die gesamte Spiegelungskonfiguration würde.

4. Wenn Sie lediglich den Zeugen aus der SQL Server-Konfiguration entfernen möchten, befolgen Sie die Anweisungen [Entfernen des Zeugen aus einer Datenbankspiegelung Sitzung (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).


