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
description: 'Damit Sie die SQL bereitstellen können, müssen Auf den Servern mindestens SQL Server 2008 R2 ausgeführt werden. Diese Version muss auf allen beteiligten Servern ausgeführt werden: dem primären Server, dem Spiegelserver und dem Zeugenserver. Weitere Informationen finden Sie im kumulativen Updatepaket 9 für SQL Server 2008 Service Pack 1 .'
ms.openlocfilehash: 8a546f65d8ad5c701eea20fb2c9c3bf0e026ff1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830555"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Bereitstellen SQL Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015


Damit Sie die SQL bereitstellen können, müssen Auf den Servern mindestens SQL Server 2008 R2 ausgeführt werden. Diese Version muss auf allen beteiligten Servern ausgeführt werden: dem primären Server, dem Spiegelserver und dem Zeugenserver. Weitere Informationen finden Sie im [kumulativen Updatepaket 9 für SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

Im Allgemeinen erfordert das Einrichten SQL Spiegelung zwischen den beiden Back-End-Servern mit einem Spiegelungszeugen Folgendes:

- Die Version des primären Servers muss SQL Server die SQL unterstützen.

- Der primäre Spiegel und der Spiegelungszeuge (sofern bereitgestellt) müssen die gleiche Version des SQL Server.

- Die primäre und die Spiegelung müssen dieselbe Edition von SQL Server. Der Zeuge hat möglicherweise eine andere Edition.

Bewährte SQL, welche SQL für eine Zeugenrolle unterstützt werden, finden Sie unter ["Datenbankspiegelungszeuge".](https://go.microsoft.com/fwlink/p/?LinkId=247345)

Sie verwenden den Topologie-Generator, um die SQL bereitstellen. Sie wählen eine Option im Topologie-Generator aus, um die Datenbanken zu spiegeln, und der Topologie-Generator richtet die Spiegelung ein (einschließlich des Einrichtens eines Spiegelungszeugen, falls sie möchten), wenn Sie die Topologie veröffentlichen. Beachten Sie, dass Sie den Zeugen gleichzeitig einrichten oder entfernen, wenn Sie den Spiegel einrichten oder entfernen. Es gibt keinen separaten Befehl, um nur einen Zeugen bereitstellen oder entfernen zu können.

Zum Konfigurieren der Serverspiegelung müssen Sie zuerst die SQL Datenbankberechtigungen ordnungsgemäß einrichten. Weitere Informationen finden Sie unter [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server).](https://go.microsoft.com/fwlink/p/?LinkId=268454)

Bei SQL spiegelung ist der Datenbankwiederherstellungsmodus immer auf **"Full"** festgelegt, d. h., Sie müssen die Größe von Transaktionsprotokollen genau überwachen und Transaktionsprotokolle regelmäßig sichern, um zu vermeiden, dass auf den Back-End-Servern nicht mehr genügend Speicherplatz zur Verfügung steht. Die Häufigkeit von Transaktionsprotokollsicherungen hängt von der Protokollzuwachsrate ab, die wiederum von Datenbanktransaktionen abhängt, die durch Benutzeraktivitäten im Front-End-Pool anfallen. Es wird empfohlen, zu bestimmen, wie viel Transaktionsprotokollwachstum für Ihre Bereitstellungsarbeitsauslastung zu erwarten ist, damit Sie die Planung entsprechend planen können. Die folgenden Artikel enthalten zusätzliche Informationen zur SQL und Protokollverwaltung:

- [Datenbankwiederherstellungsmodelle](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [Übersicht über die Sicherung](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [Sicherungstransaktionsprotokoll](https://go.microsoft.com/fwlink/p/?LinkId=268452)

Mit SQL können Sie entweder die Topologie für die Spiegelung konfigurieren, wenn Sie die Pools erstellen, oder nachdem die Pools bereits erstellt wurden.

> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die primären, Spiegel- und Zeugenserver (falls gewünscht) zur gleichen Domäne gehören. Wenn Sie eine Spiegelung SQL Servern in verschiedenen Domänen einrichten möchten, lesen Sie ihre SQL Server Dokumentation.

> [!IMPORTANT]
> Wenn Sie eine Änderung an einer Back-End-Datenbankspiegelungsbeziehung ändern, müssen Sie alle Front-End-Server im Pool neu starten. > Für eine Änderung der Spiegelung (z. B. ändern der Position eines Spiegels) müssen Sie den Topologie-Generator verwenden, um die folgenden drei Schritte durchzuführen:

1. Entfernen Sie die Spiegelung vom alten Spiegelserver.

2. Fügen Sie dem neuen Spiegelserver Spiegelung hinzu.

3. Veröffentlichen Sie die Topologie.

> [!NOTE]
> Es muss eine Dateifreigabe erstellt werden, in die die Spiegeldateien geschrieben werden sollen, und der Dienst, unter dem SQL Server und SQL Agent ausgeführt werden, benötigt Lese-/Schreibzugriff. Wenn der SQL Server im Kontext des Netzwerkdiensts ausgeführt wird, können Sie den Freigabeberechtigungen<SQLSERVERNAME $ des Prinzipalservers und des \<Domain\> \\ Spiegelservers SQL \> hinzufügen. $ist wichtig, um zu identifizieren, dass es sich um ein Computerkonto handelt.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>So konfigurieren SQL beim Erstellen eines Pools im Topologie-Generator

1. Klicken Sie **auf der Seite SQL Store definieren** auf **"Neu"** neben dem **SQL Store-Feld.**

2. Geben Sie auf der Seite neuen **SQL Speicher** definieren den primären Speicher an, wählen Sie **"Diese SQL-Instanz** befindet sich in einer Spiegelungsbeziehung", geben Sie die Portnummer der SQL-Spiegelung an (der Standardwert ist 5022), und klicken Sie dann auf **OK**.

3. Wählen Sie auf der **Seite zum Definieren SQL Speichers** die Option **"SQL A0 aktivieren" aus.**

4. Geben Sie auf der **Seite SQL neuen Speicher definieren** den SQL an, der als Spiegel verwendet werden soll. Select **This SQL instance is in mirroring relation,** specify the port number (the default is 5022), and then click **OK**.

5. Wenn Sie einen Spiegelzeugen wünschen, gehen Sie wie folgt vor:

    a. Wählen **Sie "SQL Spiegelungszeugen verwenden" aus, um das automatische Failover zu aktivieren.**

    b. Wählen Sie auf der Seite **"SQL** Store definieren" die Option "SQL Spiegelungszeugen verwenden" aus, um das automatische Failover zu **aktivieren,** und geben Sie den SQL an, der als Zeuge verwendet werden soll.

    c. Geben Sie die Portnummer an (der Standardwert ist 7022), und klicken Sie auf **OK**.

6. Nachdem Sie den Front-End-Pool und alle anderen Rollen in ihrer Topologie definiert haben, verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen. Wenn bei der Veröffentlichung der Topologie die Spiegelung für den Front-End-Pool, der den zentralen Verwaltungsspeicher hostet, SQL aktiviert ist, wird eine Option zum Erstellen von primären und Spiegelspeicherdatenbanken SQL angezeigt.

    Klicken **Sie auf**"Einstellungen", und geben Sie den Pfad ein, der als Dateifreigabe für die Spiegelungssicherung verwendet werden soll.

    Klicken **Sie auf "OK"** und dann auf **"Weiter",** um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegelung und der Spiegelungszeuge (sofern angegeben) werden bereitgestellt.

Sie können den Topologie-Generator verwenden, um die Eigenschaften eines bereits vorhandenen Pools zu bearbeiten, um die SQL zu ermöglichen.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>So fügen SQL A0 einem vorhandenen Front-End-Pool im Topologie-Generator hinzu

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann **auf "Eigenschaften bearbeiten".**

2. Wählen **Sie SQL "Spiegelung aktivieren"**  aus, und klicken Sie dann auf "Neu" neben SQL **Store**.

3. Geben Sie SQL Speicher an, den Sie als Spiegel verwenden möchten.

4. Select **This SQL instance is in mirroring relation,** specify the SQL mirroring port number the default port is 5022), and then click **OK**.

5. Wenn Sie einen Spiegelungszeugen konfigurieren möchten, wählen Sie **"SQL** Spiegelungszeugen verwenden" aus, um das automatische Failover zu aktivieren, und klicken Sie auf **"Neu".**

6. Geben Sie SQL Speicher an, den Sie als Zeugen verwenden möchten.

7. Select **This SQL instance is in mirroring relation,** specify the SQL mirroring port number (the default port is 7022), and then click **OK**.

8. Klicken Sie auf **OK**.

9. Veröffentlichen Sie die Topologie. Wenn Sie dies tun, werden Sie aufgefordert, die Datenbank zu installieren.

    Während des Veröffentlichungsprozesses der Topologie werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL Server, die an der Spiegelung teilnehmen, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen, damit der Spiegel eingerichtet werden kann.

Anschließend müssen Sie die Datenbank installieren, bevor Sie mit dem nächsten Verfahren verfahren.

Beachten Sie beim Einrichten der SQL Folgendes:

- Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird er mithilfe der dort definierten Ports wiederverwendet und ignoriert die in der Topologie angegebenen Ports.

- Jeder Port, der bereits anderen Anwendungen auf demselben Server zugewiesen ist, einschließlich der für andere SQL-Instanzen, sollte nicht für die installierten SQL verwendet werden. Dies bedeutet, dass sie nicht denselben Port für die Spiegelung verwenden dürfen, SQL mehrere Instanzen auf demselben Server installiert sind. Weitere Informationen finden Sie in den folgenden Artikeln:

  - [Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [Der Datenbankspiegelungsendpunkt (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Verwenden von Skype for Business Server 2015-Verwaltungsshell-Cmdlets zum Einrichten SQL Spiegelung

Die einfachste Möglichkeit zum Einrichten der Spiegelung ist die Verwendung des Topologie-Generators, aber Sie können dies auch mithilfe von Cmdlets tun.

1. Öffnen Sie ein Skype for Business Server 2015-Verwaltungsshellfenster, und führen Sie das folgende Cmdlet aus:

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Beispiel:

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Es wird Folgendes zu sehen sein:

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

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows Firewall im primären SQL Server e04-ocs.los_a.lsipt.local\rtc aktiviert ist.

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Spiegelserver SQL Server K16-ocs.los_a.lsipt.local\rtc aktiviert ist.

    - Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows Firewall im Zeugendienst SQL Server AB14-lct.los_a.lsipt.local\rtc aktiviert ist.

   - Konten, die die SQL Server auf allen primären und Spiegelservern SQL haben Lese-/Schreibberechtigungen für die Dateifreigabe \\ "E04-OCS\csdatabackup"

   - Stellen Sie sicher, dass der Anbieter für die Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI) auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für SQL Server Dienste zu finden, die auf allen primären Servern, Spiegelservern und Zeugenservern ausgeführt werden.

   - Stellen Sie sicher, dass das Konto, unter dem dieses Cmdlet ausgeführt wird, über die Berechtigung zum Erstellen der Ordner für die Daten und Protokolldateien für alle Spiegelserver verfügt.

   - Beachten Sie, dass das Benutzerkonto, das von SQL ausgeführt wird, über Lese-/Schreibberechtigungen für die Dateifreigabe verfügen muss. Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL-Instanz ein lokales Systemkonto ausgeführt, müssen Sie dem Server, auf dem die dateifreigabeninstanz hostet, Dateifreigabeberechtigungen SQL erteilen.

3. Geben Sie A ein, und drücken Sie die EINGABETASTE.

    Die Spiegelung wird konfiguriert.

    **"Install-CsMirrorDatabase"** installiert die Spiegelung und konfiguriert die Spiegelung für alle Datenbanken, die sich im primären SQL befinden. Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie die Option -DatabaseType verwenden, oder wenn Sie die Spiegelung für alle Datenbanken außer einigen wenigen konfigurieren möchten, können Sie die Option -ExcludeDatabaseList zusammen mit einer durch Kommas getrennten Liste der auszuschließenden Datenbanknamen verwenden.

    Wenn Sie beispielsweise **"Install-CsMirrorDatabase"** die folgende Option hinzufügen, werden alle Datenbanken mit Ausnahme von "rtcab" und "rtcxds" gespiegelt.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Wenn Sie beispielsweise **"Install-CsMirrorDatabase"** die folgende Option hinzufügen, werden nur die Datenbanken "rtcab", "rtcshared" und "rtcxds" gespiegelt.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Entfernen oder Ändern SQL Spiegelung

Um die SQL eines Pools im Topologie-Generator zu entfernen, müssen Sie zuerst ein Cmdlet verwenden, um den Spiegel in der SQL Server. Anschließend können Sie den Spiegel mithilfe des Topologie-Generators aus der Topologie entfernen. Verwenden Sie das folgende Cmdlet, SQL Server, um den Spiegel in einem anderen Cmdlet zu entfernen:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu löschen:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

Die  `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betroffenen Datenbanken aus dem Spiegel gelöscht werden.

Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **"Eigenschaften bearbeiten".**

2. Deaktivieren Sie **die Option SQL Speicherspiegelung aktivieren,** und klicken Sie auf **"OK".**

3. Veröffentlichen Sie die Topologie.

## <a name="removing-a-mirroring-witness"></a>Entfernen eines Spiegelungszeugen

Verwenden Sie dieses Verfahren, wenn Sie den Spiegelungszeugen aus einer Back-End-Serverspiegelungskonfiguration entfernen müssen.

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann **auf "Eigenschaften bearbeiten".**

2. Deaktivieren Sie **die Option SQL Server Spiegelungszeugen verwenden, um das automatische Failover zu aktivieren, und** klicken Sie auf **"OK".**

3. Veröffentlichen Sie die Topologie.

    Nach der Veröffentlichung der Topologie wird im Topologie-Generator eine Meldung angezeigt, die Folgendes enthält:

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Führen Sie diesen Schritt jedoch nicht aus, und geben Sie nicht so ein, als würde die  `Uninstall-CsMirrorDatabase` gesamte Spiegelungskonfiguration deinstalliert.

4. Um nur den Zeugen aus der SQL Server zu entfernen, folgen Sie den Anweisungen in "Entfernen des Spiegelungszeugen aus einer [Datenbankspiegelungssitzung" (SQL Server).](https://go.microsoft.com/fwlink/p/?LinkId=268456)


