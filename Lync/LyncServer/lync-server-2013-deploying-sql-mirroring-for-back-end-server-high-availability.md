---
title: Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern
description: Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit des Back-End-Servers.
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
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566001"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-01-08_

Um die SQL-Spiegelung bereitstellen zu können, müssen die Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern ausgeführt werden: primär, Spiegel und Zeuge. Ausführliche Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) .

Im Allgemeinen erfordert das Einrichten der SQL-Spiegelung zwischen den beiden Back-End-Servern mit einem Zeugen Folgendes:

  - Die SQL Server Version des primären Servers muss die SQL-Spiegelung unterstützen.

  - Der primäre, der Spiegel und der Zeuge (falls bereitgestellt) müssen dieselbe Version von SQL Server haben.

  - Der primäre und der Spiegel müssen dieselbe Edition von SQL Server aufweisen. Der Zeugen kann eine andere Edition haben.

Informationen zu SQL-Best Practices in Bezug auf die Unterstützung von SQL-Versionen für eine Zeugenrolle finden Sie unter "Datenbank-Spiegelungs Zeuge" in der MSDN Library unter [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .

Verwenden Sie den Topologie-Generator, um die SQL-Spiegelung bereitzustellen. Sie wählen eine Option im Topologie-Generator aus, um die Datenbanken zu spiegeln, und der Topologie-Generator richtet die Spiegelung (einschließlich Einrichten eines Zeugen, falls gewünscht) ein, wenn Sie die Topologie veröffentlichen. Beachten Sie, dass Sie den Zeugen gleichzeitig einrichten oder entfernen, wenn Sie die Spiegelung einrichten oder entfernen. Es gibt keinen separaten Befehl zum Bereitstellen oder Entfernen eines Zeugen.

Zum Konfigurieren der Server Spiegelung müssen Sie zunächst die SQL-Datenbankberechtigungen ordnungsgemäß einrichten. Ausführliche Informationen finden Sie unter "Einrichten von Anmeldekonten für die Datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .

Bei der SQL-Spiegelung ist der Wiederherstellungsmodus der Datenbank immer auf **Full**festgelegt, was bedeutet, dass Sie die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern müssen, um zu vermeiden, dass der Speicherplatz auf den Back-End-Servern knapp wird. Die Häufigkeit der Transaktionsprotokollsicherungen hängt von der Protokoll Wachstumsrate ab, die wiederum von Datenbanktransaktionen abhängt, die von Benutzeraktivitäten auf dem Front-End-Pool verursacht werden. Es wird empfohlen, festzulegen, wie viel Transaktionsprotokoll Wachstum für Ihre lync-Bereitstellungs Arbeitsauslastung erwartet wird, damit Sie die Planung entsprechend durchführen können. Die folgenden Artikel bieten zusätzliche Informationen zur SQL-Sicherung und-Protokollverwaltung:

  - Daten Bank Wiederherstellungsmodelle: "Wiederherstellungsmodelle (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)

  - Übersicht über die Sicherung: "Übersicht über Sicherungen (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)

  - Sicherungs Transaktionsprotokoll: "Sichern eines Transaktionsprotokolls (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)

Bei der SQL-Spiegelung können Sie entweder die Topologie für die Spiegelung konfigurieren, wenn Sie die Pools erstellen oder nachdem die Pools bereits erstellt wurden.



> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die primären, Spiegel-und Zeugenserver (falls gewünscht) zu derselben Domäne gehören. Wenn Sie die SQL-Spiegelung zwischen Servern in unterschiedlichen Domänen einrichten möchten, lesen Sie Ihre SQL Server Dokumentation.





> [!IMPORTANT]
> Wenn Sie eine Änderung an einer Back-End-Daten Bank Spiegelungs Beziehung vornehmen, müssen Sie alle Front-End-Server im Pool neu starten.<BR>Für eine Änderung der Spiegelung (beispielsweise das Ändern des Speicherorts einer Spiegelung) müssen Sie den Topologie-Generator verwenden, um diese drei Schritte auszuführen: 
> <OL>
> <LI>
> <P>Entfernen Sie die Spiegelung vom alten Spiegelserver.</P>
> <LI>
> <P>Fügen Sie dem neuen Spiegelserver die Spiegelung hinzu.</P>
> <LI>
> <P>Veröffentlichen Sie die Topologie.</P></LI></OL>




> [!NOTE]
> Es muss eine Dateifreigabe erstellt werden, in die die Spiegeldateien geschrieben werden sollen, und der Dienst, auf dem SQL Server und SQL-Agent ausgeführt werden, benötigt Lese-/Schreibzugriff. Wenn der SQL Server Dienst unter dem Kontext von Netzwerkdienst läuft, können Sie &lt; Domänen &gt;&#92;&lt; SQLServerName &gt; $ sowohl der Prinzipal-als auch der Mirror SQL-Server den Freigabeberechtigungen hinzufügen. Der Wert $ ist wichtig, um festzustellen, dass es sich um ein Computerkonto handelt.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>So konfigurieren Sie die SQL-Spiegelung beim Erstellen eines Pools im Topologie-Generator

1.  Klicken Sie auf der Seite **SQL-Speicher definieren** neben dem Feld **SQL-Speicher** auf **neu** .

2.  Geben Sie auf der Seite **neuen SQL-Speicher definieren** den primären Speicher an, wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung aus**, geben Sie die SQL-Spiegelungs Portnummer an (Standardwert 5022), und klicken Sie dann auf **OK**.

3.  Wählen Sie zurück auf der Seite **SQL-Speicher definieren** die Option **SQL-Speicherspiegelung aktivieren**aus.

4.  Geben Sie auf der Seite **neuen SQL-Speicher definieren** den SQL-Speicher an, der als Spiegel verwendet werden soll. Wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung**aus, geben Sie die Portnummer an (Standardwert 5022), und klicken Sie dann auf **OK**.

5.  Wenn Sie einen Zeugen für diesen Spiegel verwenden möchten, gehen Sie wie folgt vor:
    
    1.  Wählen Sie **zum Aktivieren des automatischen Failovers die Option SQL-Spiegelungs Zeugen verwenden**aus.
    
    2.  Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **Automatisches Failover mithilfe des SQL-Spiegelungs Zeugen aktivieren**aus, und geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll.
    
    3.  Geben Sie die Portnummer an (der Standardwert lautet 7022), und klicken Sie auf **OK**.

6.  Nachdem Sie die Front-End-Pool und alle anderen Rollen in Ihrer Topologie definiert haben, verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen. Wenn die Topologie veröffentlicht wird und die Front-End-Pool, die den zentralen Verwaltungsspeicher hostet, die SQL-Spiegelung aktiviert hat, wird eine Option zum Erstellen von primären und Spiegel-SQL-Speicher Datenbanken angezeigt.
    
    Klicken Sie auf **Einstellungen**, und geben Sie den Pfad ein, der als Dateifreigabe für die Spiegelungs Sicherung verwendet werden soll.
    
    Klicken Sie auf **OK** und dann auf **weiter** , um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegelung und der Zeuge (sofern angegeben) werden bereitgestellt.

Sie können den Topologie-Generator zum Bearbeiten der Eigenschaften eines bereits vorhandenen Pools verwenden, um die SQL-Spiegelung zu aktivieren.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>So fügen Sie eine SQL-Spiegelung zu einer vorhandenen Front-End-Pool im Topologie-Generator hinzu

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.

2.  Wählen Sie **SQL-Speicherspiegelung aktivieren**aus, und klicken Sie dann neben **Spiegelungs-SQL-Speicher**auf **neu** .

3.  Geben Sie den SQL-Speicher an, der als Spiegel verwendet werden soll.

4.  Wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung**aus, geben Sie die SQL-Spiegelungs Portnummer an, die den Standardport 5022 ist), und klicken Sie dann auf **OK**.

5.  Wenn Sie einen Zeugen konfigurieren möchten, wählen Sie **zum Aktivieren des automatischen Failovers die Option SQL-Spiegelungs Zeugen verwenden**aus, und klicken Sie auf **neu**.

6.  Geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll.

7.  Wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung**aus, geben Sie die Portnummer für die SQL-Spiegelung an (der Standardport lautet 7022), und klicken Sie dann auf **OK**.

8.  Klicken Sie auf **OK**.

9.  Veröffentlichen Sie die Topologie. Wenn Sie dies tun, werden Sie aufgefordert, die Datenbank zu installieren.
    
    Während des Veröffentlichungsprozesses der Topologie werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL-Server, die an der Spiegelung teilnehmen, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen, damit die Spiegelung hergestellt werden kann.

Anschließend müssen Sie die Datenbank installieren, bevor Sie mit dem nächsten Verfahren fortfahren.

Beachten Sie beim Einrichten der SQL-Spiegelung Folgendes:

  - Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird er mithilfe der dort definierten Ports wieder verwendet und ignoriert diejenigen, die Sie in der Topologie angegeben haben.

  - Jeder Port, der bereits für andere Anwendungen auf demselben Server reserviert ist, einschließlich der für andere SQL-Instanzen, sollte nicht für die installierten SQL-Instanzen verwendet werden. Dies bedeutet, dass Sie bei mehr als einer SQL-Instanz auf demselben Server nicht denselben Port für die Spiegelung verwenden dürfen. Ausführliche Informationen finden Sie in den folgenden Artikeln:
    
      - "Angeben einer Server Netzwerkadresse (Datenbankspiegelung)" in der MSDN Library unter [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "Der Datenbankspiegelungsendpunkt (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Verwenden von lync Server-Verwaltungsshell-Cmdlets zum Einrichten der SQL-Spiegelung

Die einfachste Möglichkeit zum Einrichten der Spiegelung ist die Verwendung des Topologie-Generators, aber Sie können dies auch mithilfe von Cmdlets tun.

1.  Öffnen Sie ein lync Server-Verwaltungsshell Fenster, und führen Sie das folgende Cmdlet aus:
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Zum Beispiel:
    
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

2.  Überprüfen Sie Folgendes:
    
      - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im primären SQL Server "E04-OCS. Los \_ a. lsipt. local RTC aktiviert ist \\ .
    
      - Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Spiegel SQL Server "K16-OCS. Los \_ a. lsipt. local RTC aktiviert ist \\ .
    
      - Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Zeugen SQL Server "ab14-LCT. Los \_ a. lsipt. local RTC aktiviert ist \\ .
    
      - Konten, die die SQL-Server auf allen primären und Spiegel-SQL-Servern durchführen, verfügen über Lese-/Schreibzugriff auf die Dateifreigabe \\ \\ E04 – OCS- \\ csdatabackup
    
      - Stellen Sie sicher, dass der WMI-Anbieter (Windows Management Instrumentation) auf allen diesen Servern läuft. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für SQL Server Dienste zu finden, die auf allen primären, Spiegel-und Zeugen Servern aktiv sind.
    
      - Stellen Sie sicher, dass das Konto, mit dem dieses Cmdlet ausgeführt wird, über die Berechtigung zum Erstellen der Ordner für die Daten-und Protokolldateien für alle Spiegelserver verfügt.
    
      - Beachten Sie, dass das Benutzerkonto, das von der SQL-Instanz zur Ausführung verwendet wird, über Lese-/Schreibzugriff auf die Dateifreigabe verfügen muss. Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL-Instanz ein lokales Systemkonto ausführt, müssen Sie dem Server, auf dem die SQL-Instanz gehostet wird, Dateifreigabeberechtigungen erteilen.

3.  Geben Sie A ein, und drücken Sie die EINGABETASTE.
    
    Die Spiegelung wird konfiguriert.

**Install-CsMirrorDatabase** installiert die Spiegelung und konfiguriert die Spiegelung für alle Datenbanken, die auf dem primären SQL-Speicher vorhanden sind. Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie die Option – DatabaseType verwenden, oder wenn Sie die Spiegelung für alle Datenbanken mit Ausnahme einiger weniger konfigurieren möchten, können Sie die Option-ExcludeDatabaseList zusammen mit einer durch Trennzeichen getrennten Liste der auszuschließenden Datenbanknamen verwenden.

Wenn Sie beispielsweise die folgende Option zum Installieren von **-CsMirrorDatabase**hinzufügen, werden alle Datenbanken mit Ausnahme von RTCAb und "rtcxds" gespiegelt.

`-ExcludeDatabaseList rtcab,rtcxds`

Wenn Sie beispielsweise die folgende Option zum Installieren von **-CsMirrorDatabase**hinzufügen, werden nur die RTCAb-, rtcshared-und "rtcxds"-Datenbanken gespiegelt.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Entfernen oder Ändern der SQL-Spiegelung

Um die SQL-Spiegelung eines Pools im Topologie-Generator zu entfernen, müssen Sie zuerst ein Cmdlet verwenden, um die Spiegelung in SQL Server zu entfernen. Anschließend können Sie den Topologie-Generator verwenden, um den Spiegel aus der Topologie zu entfernen. Verwenden Sie das folgende Cmdlet, um die Spiegelung in SQL Server zu entfernen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu löschen:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Die `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betroffenen Datenbanken aus dem Spiegel gelöscht werden.

Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

2.  Deaktivieren Sie die **Option SQL-Speicherspiegelung aktivieren** , und klicken Sie auf **OK**.

3.  Veröffentlichen Sie die Topologie.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Entfernen eines Spiegelungs Zeugen

Verwenden Sie dieses Verfahren, wenn Sie den Zeugen aus einer Back-End-Server-Spiegelungskonfiguration entfernen müssen.

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.

2.  Deaktivieren Sie **die Option verwenden Sie SQL Server Spiegelungs Zeugen, um das automatische Failover zu aktivieren** , und klicken Sie auf **OK**.

3.  Veröffentlichen Sie die Topologie.
    
    Nach dem Veröffentlichen der Topologie wird im Topologie-Generator eine Meldung mit den folgenden Informationen angezeigt:
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Führen Sie diesen Schritt jedoch nicht aus, und geben Sie nicht `Uninstall-CsMirrorDatabase` so ein, dass die gesamte Spiegelungskonfiguration deinstalliert wird.

4.  Wenn Sie lediglich den Zeugen aus der SQL Server Konfiguration entfernen möchten, befolgen Sie die Anweisungen unter "Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

