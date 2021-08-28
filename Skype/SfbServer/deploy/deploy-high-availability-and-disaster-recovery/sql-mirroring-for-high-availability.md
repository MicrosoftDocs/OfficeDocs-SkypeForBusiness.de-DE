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
ms.localizationpriority: medium
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Um SQL Spiegelung bereitstellen zu können, müssen Die Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern ausgeführt werden: dem primären Server, dem Spiegel und dem Zeugen. Ausführliche Informationen finden Sie unter kumulatives Updatepaket 9 für SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: 5432d7715a9fa6f73d7dcc663cf7a092369b746e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595989"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Bereitstellen SQL Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015


Um SQL Spiegelung bereitstellen zu können, müssen Die Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern ausgeführt werden: dem primären Server, dem Spiegel und dem Zeugen. Ausführliche Informationen finden Sie unter [kumulatives Updatepaket 9 für SQL Server 2008 Service Pack 1.](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)

Im Allgemeinen erfordert das Einrichten SQL Spiegelung zwischen den beiden Back-End-Servern mit einem Zeugen Folgendes:

- Die Version des primären Servers von SQL Server muss SQL Spiegelung unterstützen.

- Der Primäre, Spiegel und der Zeuge (sofern bereitgestellt) müssen die gleiche Version von SQL Server aufweisen.

- Die primäre und die Spiegelung müssen die gleiche Edition von SQL Server aufweisen. Der Zeuge hat möglicherweise eine andere Edition.

SQL bewährten Methoden in Bezug darauf, welche SQL Versionen für eine Zeugenrolle unterstützt werden, finden Sie unter ["Datenbankspiegelungszeugen".](/sql/database-engine/database-mirroring/database-mirroring-witness)

Sie verwenden den Topologie-Generator, um SQL Spiegelung bereitzustellen. Sie wählen im Topologie-Generator eine Option zum Spiegeln der Datenbanken aus, und der Topologie-Generator richtet die Spiegelung ein (einschließlich der Einrichtung eines Zeugen, falls gewünscht), wenn Sie die Topologie veröffentlichen. Beachten Sie, dass Sie den Zeugen gleichzeitig einrichten oder entfernen, während Sie den Spiegel einrichten oder entfernen. Es gibt keinen separaten Befehl, um nur einen Zeugen bereitzustellen oder zu entfernen.

Um die Serverspiegelung zu konfigurieren, müssen Sie zuerst SQL Datenbankberechtigungen ordnungsgemäß einrichten. Ausführliche Informationen finden Sie unter [Einrichten von Anmeldekonten für datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server).](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)

Bei SQL Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **"Vollständig"** festgelegt, was bedeutet, dass Sie die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern müssen, um zu vermeiden, dass der Speicherplatz auf den Back-End-Servern knapp wird. Die Häufigkeit von Transaktionsprotokollsicherungen hängt von der Protokoll-Wachstumsrate ab, die wiederum von Datenbanktransaktionen abhängt, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, dass Sie bestimmen, wie viel Transaktionsprotokoll-Wachstum für Ihre Bereitstellungsworkload erwartet wird, damit Sie die Planung entsprechend durchführen können. Die folgenden Artikel enthalten zusätzliche Informationen zur SQL Sicherung und Protokollverwaltung:

- [Datenbankwiederherstellungsmodelle](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [Übersicht über die Sicherung](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [Transaktionsprotokoll sichern](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

Mit SQL Spiegelung können Sie entweder die Topologie für die Spiegelung konfigurieren, wenn Sie die Pools erstellen, oder nachdem die Pools bereits erstellt wurden.

> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen SQL Spiegelung wird nur unterstützt, wenn die primären Server, Spiegelserver und Zeugenserver (falls gewünscht) zur gleichen Domäne gehören. Wenn Sie SQL Spiegelung zwischen Servern in verschiedenen Domänen einrichten möchten, lesen Sie die Dokumentation zu Ihrer SQL Server.

> [!IMPORTANT]
> Wenn Sie eine Änderung an einer Back-End-Datenbankspiegelungsbeziehung vornehmen, müssen Sie alle Front-End-Server im Pool neu starten. > Für eine Änderung der Spiegelung (z. B. ändern der Position eines Spiegels) müssen Sie den Topologie-Generator verwenden, um die folgenden drei Schritte auszuführen:

1. Entfernen Sie die Spiegelung vom alten Spiegelserver.

2. Fügen Sie dem neuen Spiegelserver Spiegelung hinzu.

3. Veröffentlichen Sie die Topologie.

> [!NOTE]
> Eine Dateifreigabe muss erstellt werden, damit die Spiegeldateien geschrieben werden können, und der Dienst, in dem SQL Server und SQL Agent ausgeführt wird, benötigt Lese-/Schreibzugriff. Wenn der SQL Server Dienst im Kontext des Netzwerkdiensts ausgeführt wird, können Sie \<Domain\> \\ den Freigabeberechtigungen<SQLSERVERNAME \> $ des Prinzipal- und Spiegelservers SQL hinzufügen. $ist wichtig, um zu erkennen, dass es sich um ein Computerkonto handelt.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>So konfigurieren Sie SQL Spiegelung beim Erstellen eines Pools im Topologie-Generator

1. Klicken **Sie** auf der Seite SQL Store definieren neben dem **SQL Speicherfeld** auf **Neu.**

2. Geben Sie auf der Seite **"Neuen SQL Store definieren"** den primären Speicher an, wählen Sie **Diese SQL Instanz befindet sich in der Spiegelungsbeziehung,** geben Sie die SQL Spiegelungsportnummer an (der Standardwert ist 5022), und klicken Sie dann auf **OK.**

3. Wählen Sie auf der Seite **"SQL Store definieren" die** Option **"SQL Store Spiegelung aktivieren"** aus.

4. Geben Sie auf der Seite **"Neuen SQL Store definieren"** den SQL Speicher an, der als Spiegelung verwendet werden soll. Wählen Sie **diese SQL Instanz sich in der Spiegelungsbeziehung befindet,** geben Sie die Portnummer an (der Standardwert ist 5022), und klicken Sie dann auf **OK.**

5. Wenn Sie einen Zeugen für diesen Spiegel wünschen, gehen Sie wie folgt vor:

    a. Wählen Sie **SQL Spiegelungszeugen verwenden aus, um das automatische Failover zu aktivieren.**

    b. Wählen Sie auf der Seite **"SQL Store definieren"** **SQL Spiegelungszeugen verwenden** aus, um das automatische Failover zu aktivieren, und geben Sie den SQL Speicher an, der als Zeuge verwendet werden soll.

    c. Geben Sie die Portnummer an (der Standardwert ist 7022), und klicken Sie auf **OK.**

6. Nachdem Sie den Front-End-Pool und alle anderen Rollen in Ihrer Topologie definiert haben, verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen. Wenn die Topologie veröffentlicht wird und der Front-End-Pool, in dem der zentrale Verwaltungsspeicher gehostet wird, SQL Spiegelung aktiviert ist, wird eine Option zum Erstellen von primären und spiegelungsfähigen SQL Speicherdatenbanken angezeigt.

    Klicken Sie auf **Einstellungen,** und geben Sie den Pfad ein, der als Dateifreigabe für die Spiegelungssicherung verwendet werden soll.

    Klicken Sie auf **"OK"** und dann auf **"Weiter",** um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegelung und der Zeuge (sofern angegeben) werden bereitgestellt.

Sie können den Topologie-Generator verwenden, um die Eigenschaften eines bereits vorhandenen Pools zu bearbeiten, um SQL Spiegelung zu aktivieren.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>So fügen Sie einem vorhandenen Front-End-Pool im Topologie-Generator SQL Spiegelung hinzu

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **"Eigenschaften bearbeiten".**

2. Wählen Sie **"SQL Store Spiegelung aktivieren"** aus, und klicken Sie dann neben **"Spiegelung" auf** **"Neu"** SQL Store .

3. Geben Sie den SQL Speicher an, den Sie als Spiegelung verwenden möchten.

4. Wählen Sie **diese SQL Instanz sich in der Spiegelungsbeziehung befindet,** geben Sie die SQL Spiegelung portnummer der Standardport 5022 ist), und klicken Sie dann auf **OK**.

5. Wenn Sie einen Zeugen konfigurieren möchten, wählen **Sie "Verwenden SQL Spiegelungszeugen" aus, um das automatische Failover zu aktivieren,** und klicken Sie auf **"Neu".**

6. Geben Sie den SQL Speicher an, den Sie als Zeugen verwenden möchten.

7. Wählen Sie **diese SQL Instanz sich in der Spiegelungsbeziehung befindet,** geben Sie die SQL Spiegelungsportnummer an (der Standardport ist 7022), und klicken Sie dann auf **OK.**

8. Klicken Sie auf **OK**.

9. Veröffentlichen Sie die Topologie. In diesem Fall werden Sie aufgefordert, die Datenbank zu installieren.

    Während des Topologieveröffentlichungsprozesses werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL Server, die an der Spiegelung teilnehmen, müssen Über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen, damit der Spiegel eingerichtet werden kann.

Sie müssen dann die Datenbank installieren, bevor Sie mit dem nächsten Verfahren fortfahren.

Beachten Sie beim Einrichten SQL Spiegelung Folgendes:

- Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird er mit den dort definierten Ports wiederverwendet und ignoriert die in der Topologie angegebenen Ports.

- Jeder port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. Dies bedeutet, dass, wenn Sie mehrere SQL Instanz auf demselben Server installiert haben, sie nicht denselben Port für die Spiegelung verwenden dürfen. Ausführliche Informationen finden Sie in den folgenden Artikeln:

  - [Angeben einer Servernetzwerkadresse (Datenbankspiegelung)](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [Der Datenbankspiegelungsendpunkt (SQL Server)](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Verwenden Skype for Business Server 2015-Verwaltungsshell-Cmdlets zum Einrichten SQL Spiegelung

Die einfachste Möglichkeit zum Einrichten der Spiegelung ist die Verwendung des Topologie-Generators, aber Sie können dies auch mithilfe von Cmdlets tun.

1. Öffnen Sie ein Skype for Business Server 2015-Verwaltungsshellfenster, und führen Sie das folgende Cmdlet aus:

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Zum Beispiel:

   ```powershell
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

2. Überprüfen Sie Folgendes:

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn Windows Firewall im primären SQL Server e04-ocs.los_a.lsipt.local\rtc aktiviert ist.

    - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn Windows Firewall im Spiegel SQL Server K16-ocs.los_a.lsipt.local\rtc aktiviert ist.

    - Auf Port 7022 kann über die Firewall zugegriffen werden, wenn Windows Firewall im Zeugen SQL Server AB14-lct.los_a.lsipt.local\rtc aktiviert ist.

   - Konten, die die SQL Server auf allen primären und Spiegelservern ausführen, SQL Server über Lese-/Schreibberechtigungen für die Dateifreigabe \\ "E04-OCS\csdatabackup" verfügen

   - Stellen Sie sicher, dass der WMI-Anbieter (Windows Management Instrumentation) auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für SQL Server Dienste zu suchen, die auf allen primären, Spiegel- und Zeugenservern ausgeführt werden.

   - Stellen Sie sicher, dass das Konto, das dieses Cmdlet ausführt, über die Berechtigung zum Erstellen der Ordner für die Daten und Protokolldateien für alle Spiegelserver verfügt.

   - Beachten Sie, dass das Benutzerkonto, mit dem die SQL Instanz ausgeführt wird, über Lese-/Schreibberechtigungen für die Dateifreigabe verfügen muss. Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL Instanz ein lokales Systemkonto ausführt, müssen Sie dem Server, der die SQL Instanz hostet, Dateifreigabeberechtigungen erteilen.

3. Geben Sie A ein, und drücken Sie die EINGABETASTE.

    Die Spiegelung wird konfiguriert.

    **Install-CsMirrorDatabase** installiert die Spiegelung und konfiguriert die Spiegelung für alle Datenbanken, die im primären SQL Speicher vorhanden sind. Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie die Option -DatabaseType verwenden, oder wenn Sie die Spiegelung für alle Datenbanken außer einigen wenigen datenbanken konfigurieren möchten, können Sie die Option -ExcludeDatabaseList zusammen mit einer durch Kommas getrennten Liste der auszuschließenden Datenbanknamen verwenden.

    Wenn Sie beispielsweise die folgende Option zu **Install-CsMirrorDatabase** hinzufügen, werden alle Datenbanken außer rtcab und rtcxds gespiegelt.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Wenn Sie beispielsweise die folgende Option zu **Install-CsMirrorDatabase** hinzufügen, werden nur die Rtcab-, rtcshared- und rtcxds-Datenbanken gespiegelt.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>Entfernen oder Ändern SQL Spiegelung

Um die SQL Spiegelung eines Pools im Topologie-Generator zu entfernen, müssen Sie zuerst ein Cmdlet verwenden, um die Spiegelung in SQL Server zu entfernen. Anschließend können Sie den Topologie-Generator verwenden, um den Spiegel aus der Topologie zu entfernen. Verwenden Sie das folgende Cmdlet, um die Spiegelung in SQL Server zu entfernen:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

Wenn Sie beispielsweise die Spiegelung entfernen und die Datenbanken für die Benutzerdatenbanken ablegen möchten, geben Sie Folgendes ein:

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

Die  `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betroffenen Datenbanken aus der Spiegelung gelöscht werden.

Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **"Eigenschaften bearbeiten".**

2. Deaktivieren **Sie die Option "SQL Store Spiegelung aktivieren",** und klicken Sie auf **"OK".**

3. Veröffentlichen Sie die Topologie.

## <a name="removing-a-mirroring-witness"></a>Entfernen eines Spiegelungszeugen

Verwenden Sie dieses Verfahren, wenn Sie den Zeugen aus einer Back-End-Serverspiegelungskonfiguration entfernen müssen.

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **"Eigenschaften bearbeiten".**

2. Deaktivieren Sie die Option **"Verwenden SQL Server Spiegelungszeugen", um das automatische Failover zu aktivieren,** und klicken Sie auf **"OK".**

3. Veröffentlichen Sie die Topologie.

    Nach der Veröffentlichung der Topologie wird dem Topologie-Generator eine Meldung angezeigt, die Folgendes enthält:

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Folgen Sie diesem Schritt jedoch nicht, und geben Sie nicht  `Uninstall-CsMirrorDatabase` ein, dass dadurch die gesamte Spiegelungskonfiguration deinstalliert würde.

4. Um nur den Zeugen aus der SQL Server Konfiguration zu entfernen, folgen Sie den Anweisungen unter [Entfernen des Zeugen aus einer Datenbankspiegelungssitzung (SQL Server).](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server)