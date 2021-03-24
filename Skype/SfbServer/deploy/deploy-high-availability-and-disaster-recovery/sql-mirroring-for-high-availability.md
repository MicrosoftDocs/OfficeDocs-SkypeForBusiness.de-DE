---
title: Bereitstellen SQL Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Um die SQL bereitstellen zu können, müssen Die Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern ausgeführt werden: dem primären Server, dem Spiegel und dem Zeugen. Weitere Informationen finden Sie unter Kumulatives Updatepaket 9 für SQL Server 2008 Service Pack 1 .'
ms.openlocfilehash: 38c3e749b39cd510623232e9f29ace03a1c19f6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100721"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Bereitstellen SQL Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015


Um die SQL bereitstellen zu können, müssen Die Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern ausgeführt werden: dem primären Server, dem Spiegel und dem Zeugen. Weitere Informationen finden Sie unter [Kumulatives Updatepaket 9 für SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

Im Allgemeinen erfordert das Einrichten SQL Spiegelung zwischen den beiden Back-End-Servern mit einem Zeugen Folgendes:

- Die Version des primären Servers muss SQL Server die SQL unterstützen.

- Primär, Spiegel und Zeuge (sofern bereitgestellt) müssen die gleiche Version von SQL Server.

- Der primäre und der Spiegel müssen die gleiche Edition von SQL Server. Der Zeuge hat möglicherweise eine andere Edition.

Weitere SQL bewährte Methoden zur Unterstützung SQL für eine Zeugenrolle finden Sie unter [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).

Sie verwenden den Topologie-Generator, um SQL bereitstellen. Sie wählen eine Option im Topologie-Generator aus, um die Datenbanken zu spiegeln, und der Topologie-Generator richtet die Spiegelung ein (z. B. das Einrichten eines Zeugen, wenn Sie möchten), wenn Sie die Topologie veröffentlichen. Beachten Sie, dass Sie den Zeugen gleichzeitig einrichten oder entfernen, wenn Sie den Spiegel einrichten oder entfernen. Es gibt keinen separaten Befehl zum Bereitstellen oder Entfernen nur eines Zeugen.

Zum Konfigurieren der Serverspiegelung müssen Sie zuerst die SQL datenbankberechtigungen richtig einrichten. Weitere Informationen finden Sie [unter Einrichten von Anmeldekonten für datenbankspiegelung oder AlwaysOn Availability Groups (SQL Server).](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)

Bei SQL wird der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, was bedeutet, dass Sie die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern müssen, um zu vermeiden, dass auf den Back-End-Servern der Speicherplatz knapp wird. Die Häufigkeit der Transaktionsprotokollsicherungen hängt von der Protokollwachstumsrate ab, die wiederum von Datenbanktransaktionen abhängt, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, zu bestimmen, wie viel Transaktionsprotokollwachstum für Ihre Bereitstellungsauslastung erwartet wird, damit Sie die Planung entsprechend planen können. Die folgenden Artikel enthalten zusätzliche Informationen zur SQL- und Protokollverwaltung:

- [Datenbankwiederherstellungsmodelle](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [Übersicht über die Sicherung](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [Sicherungstransaktionsprotokoll](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

Mit SQL können Sie entweder die Topologie für die Spiegelung konfigurieren, wenn Sie die Pools erstellen, oder nachdem die Pools bereits erstellt wurden.

> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder der Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die primären, spiegel- und zeugenserver (falls gewünscht) zur gleichen Domäne gehören. Wenn Sie die Spiegelung SQL Servern in verschiedenen Domänen einrichten möchten, lesen Sie die SQL Server Dokumentation.

> [!IMPORTANT]
> Wenn Sie eine Änderung an einer Back-End-Datenbankspiegelungsbeziehung ändern, müssen Sie alle Front-End-Server im Pool neu starten. > Für eine Änderung der Spiegelung (z. B. das Ändern der Position eines Spiegels) müssen Sie den Topologie-Generator verwenden, um die folgenden drei Schritte ausführen zu können:

1. Entfernen der Spiegelung vom alten Spiegelserver.

2. Fügen Sie dem neuen Spiegelserver spiegelung hinzu.

3. Veröffentlichen Sie die Topologie.

> [!NOTE]
> Es muss eine Dateifreigabe erstellt werden, in die die Spiegeldateien geschrieben werden sollen, und der Dienst, SQL Server und SQL Agent ausgeführt werden, benötigt Lese-/Schreibzugriff. Wenn der SQL Server im Kontext von Netzwerkdienst ausgeführt wird, können Sie den Freigabeberechtigungen<SQLSERVERNAME $ des Prinzipalservers und des Spiegel \<Domain\> \\ \> SQL servers hinzufügen. $ist wichtig, um zu ermitteln, dass es sich um ein Computerkonto handelt.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>So konfigurieren SQL beim Erstellen eines Pools im Topologie-Generator

1. Klicken Sie auf der **Seite SQL store** definieren auf **Neu** neben dem **SQL Store.**

2. Geben Sie auf der Seite Neuen **SQL-Speicher** definieren den primären Speicher an, wählen Sie Diese **SQL-Instanz** befindet sich in spiegelungsbeziehung, geben Sie die SQL-Spiegelungsportnummer an (die Standardeinstellung ist 5022), und klicken Sie dann auf **OK**.

3. Wählen Sie auf der **Seite SQL Speichern definieren** die Option SQL **Store-Spiegelung aktivieren aus.**

4. Geben Sie auf der Seite SQL neuen Speicher **definieren** den SQL an, der als Spiegelung verwendet werden soll. Select **This SQL instance is in mirroring relation,** specify the port number (the default is 5022), and then click **OK**.

5. Wenn Sie einen Zeugen für diesen Spiegel wünschen, gehen Sie wie folgt vor:

    a. Wählen **Sie Verwenden SQL Spiegelungszeugen zum Aktivieren des automatischen Failovers aus.**

    b. Wählen Sie auf der Seite **SQL** Store definieren die Option SQL Spiegelungszeuge verwenden aus, um das automatische Failover zu **aktivieren,** und geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll.

    c. Geben Sie die Portnummer an (die Standardeinstellung ist 7022), und klicken Sie auf **OK**.

6. Nachdem Sie den Front-End-Pool und alle anderen Rollen in Ihrer Topologie definiert haben, verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen. Wenn die Topologie veröffentlicht wird und der Front-End-Pool, der den zentralen Verwaltungsspeicher hostet, SQL Spiegelung aktiviert ist, wird eine Option zum Erstellen von primären und Spiegelspeicherdatenbanken SQL angezeigt.

    Klicken **Sie auf** Einstellungen, und geben Sie den Pfad ein, der als Dateifreigabe für die Spiegelsicherung verwendet werden soll.

    Klicken **Sie auf OK** und dann auf **Weiter,** um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegelung und der Zeuge (sofern angegeben) werden bereitgestellt.

Sie können den Topologie-Generator verwenden, um die Eigenschaften eines bereits vorhandenen Pools zu bearbeiten, um SQL zu ermöglichen.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>So fügen SQL einem vorhandenen Front-End-Pool im Topologie-Generator hinzu

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann **auf Eigenschaften bearbeiten.**

2. Wählen **Sie SQL Storespiegelung aktivieren** aus, und klicken Sie dann auf **Neu** neben **Spiegelung SQL Store**.

3. Geben Sie den SQL an, den Sie als Spiegel verwenden möchten.

4. Select **This SQL instance is in mirroring relation,** specify the SQL mirroring port number the default port is 5022), and then click **OK**.

5. Wenn Sie einen Zeugen konfigurieren möchten, wählen Sie Verwenden SQL Spiegelungszeugen zum Aktivieren des automatischen **Failovers** aus, und klicken Sie auf **Neu**.

6. Geben Sie den SQL an, den Sie als Zeugen verwenden möchten.

7. Select **This SQL instance is in mirroring relation,** specify the SQL mirroring port number (the default port is 7022), and then click **OK**.

8. Klicken Sie auf **OK**.

9. Veröffentlichen Sie die Topologie. Wenn Sie dies tun, werden Sie aufgefordert, die Datenbank zu installieren.

    Während des Topologieveröffentlichungsprozesses werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL Server, die an der Spiegelung teilnehmen, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen, damit der Spiegel eingerichtet werden kann.

Anschließend müssen Sie die Datenbank installieren, bevor Sie mit dem nächsten Verfahren verfahren.

Beachten Sie folgendes beim Einrichten SQL Spiegelung:

- Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird er mit den dort definierten Ports wiederverwendet und ignoriert die in der Topologie angegebenen Ports.

- Jeder Port, der bereits für andere Anwendungen auf demselben Server reserviert ist, einschließlich der für andere SQL-Instanzen, sollte nicht für die installierten SQL verwendet werden. Dies bedeutet, dass, wenn mehrere SQL auf demselben Server installiert sind, nicht derselbe Port für die Spiegelung verwendet werden darf. Weitere Informationen finden Sie in den folgenden Artikeln:

  - [Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [Der Datenbankspiegelungsendpunkt (SQL Server)](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Verwenden von Skype for Business Server 2015-Verwaltungsshell-Cmdlets zum Einrichten SQL Spiegelung

Die einfachste Möglichkeit zum Einrichten der Spiegelung ist die Verwendung des Topologie-Generators, Sie können dies jedoch auch mithilfe von Cmdlets tun.

1. Öffnen Sie ein Skype for Business Server 2015-Verwaltungsshellfenster, und führen Sie das folgende Cmdlet aus:

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Zum Beispiel:

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Sie sehen Folgendes:

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

2. Überprüfen Sie Folgendes:

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im primären SQL Server e04-ocs.los_a.lsipt.local\rtc aktiviert ist.

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Spiegel SQL Server K16-ocs.los_a.lsipt.local\rtc aktiviert ist.

    - Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Zeugen SQL Server AB14-lct.los_a.lsipt.local\rtc aktiviert ist.

   - Konten, auf denen die SQL Server auf allen primären und Spiegelservern ausgeführt SQL haben Lese-/Schreibberechtigung für die Dateifreigabe \\ E04-OCS\csdatabackup

   - Stellen Sie sicher, dass der Windows Management Instrumentation (WMI)-Anbieter auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für SQL Server, die auf allen primären, Spiegel- und Zeugenservern ausgeführt werden, zu finden.

   - Stellen Sie sicher, dass das Konto, auf dem dieses Cmdlet ausgeführt wird, über die Berechtigung zum Erstellen der Ordner für die Daten und Protokolldateien für alle Spiegelserver verfügt.

   - Beachten Sie, dass das Benutzerkonto, das von SQL ausgeführt wird, über Lese-/Schreibberechtigungen für die Dateifreigabe verfügen muss. Wenn sich die Dateifreigabe auf einem anderen Server befindet und in der SQL-Instanz ein lokales Systemkonto ausgeführt wird, müssen Sie dem Server, der die SQL hostet, Dateifreigabeberechtigungen erteilen.

3. Geben Sie A ein, und drücken Sie die EINGABETASTE.

    Die Spiegelung wird konfiguriert.

    **Install-CsMirrorDatabase** installiert den Spiegel und konfiguriert die Spiegelung für alle Datenbanken, die sich im primären SQL befinden. Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie die Option -DatabaseType verwenden, oder wenn Sie die Spiegelung für alle Datenbanken mit Ausnahme weniger datenbanken konfigurieren möchten, können Sie die Option -ExcludeDatabaseList zusammen mit einer durch Kommas getrennten Liste von Datenbanknamen verwenden, die ausgeschlossen werden sollen.

    Wenn Sie beispielsweise die folgende Option zu **Install-CsMirrorDatabase** hinzufügen, werden alle Datenbanken mit Ausnahme von rtcab und rtcxds gespiegelt.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Wenn Sie beispielsweise **install-CsMirrorDatabase** die folgende Option hinzufügen, werden nur die Rtcab-, rtcshared- und rtcxds-Datenbanken gespiegelt.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Entfernen oder Ändern SQL Spiegelung

Um die SQL eines Pools im Topologie-Generator zu entfernen, müssen Sie zunächst ein Cmdlet verwenden, um den Spiegel in der SQL Server. Anschließend können Sie den Topologie-Generator verwenden, um den Spiegel aus der Topologie zu entfernen. Verwenden Sie das folgende Cmdlet, um die Spiegelung SQL Server entfernen:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu löschen:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

Die  `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betroffenen Datenbanken aus dem Spiegel gelöscht werden.

Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten.**

2. Deaktivieren Sie **aktivieren SQL Store Mirroring aktivieren,** und klicken Sie auf **OK**.

3. Veröffentlichen Sie die Topologie.

## <a name="removing-a-mirroring-witness"></a>Entfernen eines Spiegelzeugen

Verwenden Sie dieses Verfahren, wenn Sie den Zeugen aus einer Back-End-Serverspiegelungskonfiguration entfernen müssen.

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten.**

2. Deaktivieren Sie **die Option SQL Server Spiegelungszeuge verwenden, um das automatische Failover zu aktivieren,** und klicken Sie auf **OK**.

3. Veröffentlichen Sie die Topologie.

    Nach der Veröffentlichung der Topologie wird dem Topologie-Generator eine Meldung angezeigt, die Folgendes enthält:

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Führen Sie diesen Schritt jedoch nicht aus, und geben Sie nicht so ein, als würde die  `Uninstall-CsMirrorDatabase` gesamte Spiegelungskonfiguration deinstalliert.

4. Um nur den Zeugen aus der konfiguration SQL Server zu entfernen, befolgen Sie die Anweisungen unter Entfernen des Zeugen aus einer [Datenbankspiegelungssitzung (SQL Server).](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server)