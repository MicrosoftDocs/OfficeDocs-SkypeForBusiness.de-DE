---
title: Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet
TOCTitle: Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202172(v=OCS.15)
ms:contentKeyID: 52056319
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Eine Bereitstellung von Lync Server verfügt über einen einzigen zentralen Verwaltungsspeicher, von dem auf jeden Server eine Kopie repliziert wird, auf dem eine Lync Server-Serverrolle ausgeführt wird. In diesem Abschnitt wird beschrieben, wie ein Back-End-Server oder Standard Edition-Server wiederhergestellt wird, der den zentralen Verwaltungsspeicher hostet.

Um den Pool zu finden, in dem sich der zentraler Verwaltungsserver befindet, öffnen Sie Topologie-Generator, klicken Sie auf **Lync Server**, und sehen Sie im rechten Bereich unter **Zentraler Verwaltungsserver** nach.

Wenn sich der Back-End-Server, der den zentralen Verwaltungsspeicher hostet, in einer gespiegelten Einrichtung befindet und die Spiegeldatenbank noch funktioniert, wird empfohlen, eine Sicherung dieser Spiegeldatenbank zu erstellen und anschließend mithilfe dieser Sicherung eine vollständige Wiederherstellung der primären und der gespiegelten Datenbank durchzuführen. Führen Sie dazu das folgende Wiederherstellungsverfahren aus. Dies ist notwendig, da die Wiederherstellung eines Back-End-Servers das Ändern und Veröffentlichen der Topologie erfordert; dies ist nur bei einer funktionsfähigen primären Datenbank, die den CMS hostet, möglich. Beachten Sie ebenfalls, dass die Rollen der primären und der gespiegelten Datenbank nicht austauschbar sind, wenn die Topologie nicht veröffentlicht werden kann.


> [!NOTE]
> Wenn ein Back-End-Server oder Standard Edition-Server ausfällt, der den zentralen Verwaltungsspeicher nicht hostet, lesen Sie unter <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Back-End-Servers der Enterprise Edition</A> oder <A href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers</A> nach. Wenn sich ein Back-End-Server, der den zentralen Verwaltungsspeicher hostet, in einer gespiegelten Konfiguration befindet und nur der Spiegelserver ausfällt, lesen Sie unter <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegel</A> nach. Wenn ein anderer Server ausfällt, lesen Sie unter<A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers</A> nach.




> [!TIP]
> Es wird empfohlen, vor der Wiederherstellung ein Abbild des Systems zu erstellen. Sie können dieses Abbild dann als Rollbackpunkt verwenden, falls Probleme bei der Wiederherstellung auftreten. Es ist sinnvoll, das Abbild nach der Installation des Betriebssystems und von SQL&nbsp;Server zu erstellen und die Zertifikate wiederherzustellen oder erneut zu registrieren.



## So stellen Sie den zentralen Verwaltungsspeicher wieder her

1.  Voraussetzung ist ein bereinigter oder neuer Server, der denselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer aufweist. Installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her bzw. registrieren Sie sie erneut.
    

    > [!NOTE]
    > Folgen Sie dem Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt auszuführen.



2.  Melden Sie sich von einem Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" und der lokalen Administratorgruppe ist, bei dem Server an, den Sie wiederherstellen.

3.  Bei der Wiederherstellung von Standard Edition-Server stellen Sie den Dateispeicher wieder her, indem Sie den entsprechenden Dateispeicher aus $Backup in den Speicherort von Dateispeicher auf dem Server kopieren und anschließend den Ordner freigeben.
    

    > [!IMPORTANT]
    > Der Pfad und Dateiname des wiederhergestellten Dateispeicher müssen mit denen des gesicherten Dateispeicher identisch sein, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.



4.  Führen Sie einen der folgenden Schritte aus:
    
      - Bei der Installation eines Standard Edition-Server navigieren Sie zum Installationsordner oder -datenträger von Lync Server und starten dann mit "\\setup\\amd64\\Setup.exe" den Lync Server-Bereitstellungs-Assistenten. Im Bereitstellungs-Assistenten klicken Sie auf **Ersten Standard Edition-Server vorbereiten** und befolgen die Anweisungen des Assistenten, um zentralen Verwaltungsspeicher zu installieren.
    
      - Bei der Installation eines Enterprise-Back-End-Servers installieren Sie SQL Server 2012 oder SQL Server 2008 R2 und behalten dieselben Instanznamen bei wie vor dem Ausfall.
        

        > [!NOTE]
        > Abhängig von wiederherzustellenden Server und Ihrer Bereitstellung umfasst der Server u.&nbsp;U. mehrere verbundene oder separate Datenbanken. Führen Sie dasselbe Verfahren aus, um den SQL Server zu installieren, den Sie ursprünglich für die Bereitstellung des Servers verwendet haben, einschließlich der SQL Server-Berechtigungen und Anmeldungen.



5.  Auf einem Front-End-Server: Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

6.  Erstellen Sie den zentralen Verwaltungsspeicher neu. Geben Sie in die Befehlszeile Folgendes ein:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Beispiel:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Legen Sie den Active Directory-Domänendienste-Steuerungspunkt für den zentralen Verwaltungsspeicher fest. Geben Sie in die Befehlszeile Folgendes ein:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Beispiel:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    

    > [!NOTE]
    > Sollten Sie den Verbindungspunkt verlieren, können Sie dieses Cmdlet erneut ausführen.



8.  Importieren Sie die zentralen Verwaltungsspeicher-Daten aus $Backup. Geben Sie in die Befehlszeile Folgendes ein:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Beispiel:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Aktivieren Sie die eben vorgenommenen Änderungen. Geben Sie in die Befehlszeile Folgendes ein:
    
        Enable-CsTopology
    

    > [!NOTE]
    > Nach dem Aktivieren der Topologie wird das Topologiedokument in der Datenbank angezeigt.



10. Wenn Sie einen Back-End-Server der Enterprise Edition wiederherstellen, der auch den CMS hostet, oder wenn Sie einen Spiegelserver des CMS erneut erstellen müssen, führen Sie diesen Schritt aus. Setzen Sie den Vorgang andernfalls mit Schritt 11 fort.
    
    Gehen Sie folgendermaßen vor, um die eigenständigen Datenbanken zu veröffentlichen:
    
    1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.
    
    2.  Klicken Sie auf **Herunterladen der Topologie aus einer vorhandenen Bereitstellung** und anschließend auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie dann auf **Speichern**. Klicken Sie auf **Ja**, um Ihre Auswahl zu bestätigen.
    
    4.  Klicken Sie mit der rechten Maustaste auf den Knoten **Lync Server 2013**, und klicken Sie dann auf **Datenbank installieren**.
    
    5.  Befolgen Sie die Anweisungen des Assistenten zum **Installieren der Datenbank**. Möchten Sie eine andere Datenbank wiederherstellen als den zentralen Verwaltungsspeicher auf diesem Server, wählen Sie auf der Seite **Erstellen von Datenbanken** die neu zu erstellenden Datenbanken aus.
        

        > [!NOTE]
        > Auf der Seite <STRONG>Erstellen von Datenbanken</STRONG> werden nur eigenständige Datenbanken angezeigt. Verbundene Datenbanken werden durch Ausführen des Lync Server-Bereitstellungs-Assistenten erstellt.

    
    6.  Wenn Sie einen gespiegelten Back-End-Server wiederherstellen, führen Sie die Schritte des Assistenten weiter aus, bis die Aufforderung zum Erstellen einer Spiegeldatenbank erstellen angezeigt wird. Wählen Sie die zu installierende Datenbank aus, und stellen Sie den Prozess fertig.
    
    7.  Befolgen Sie die verbleibenden Anweisungen des Assistenten, und klicken Sie dann auf **Fertig stellen**.
    

    > [!TIP]
    > Anstatt den Topologie-Generator auszuführen, können Sie die einzelnen Datenbanken mithilfe des <STRONG>Install-CsDatabase</STRONG>-Cmdlets erstellen und die Spiegelung mithilfe des Cmdlets <STRONG>Install-CsMirrorDatabase</STRONG> konfigurieren. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> und <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.



11. Beim Wiederherstellen eines Standard Edition-Server navigieren Sie zum Installationsordner oder -datenträger von Lync Server und starten mit \\setup\\amd64\\Setup.exe den Lync Server-Bereitstellungs-Assistenten. Führen Sie mithilfe des Lync Server-Bereitstellungs-Assistenten folgende Aufgaben aus:
    
    1.  Führen Sie Schritt 1 **Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen Sie Schritt 2 **Lync Server-Komponenten einrichten oder entfernen** aus, um die Lync Server-Serverrollen zu installieren.
    
    3.  Führen Sie Schritt 3 **Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.
    
    4.  Führen Sie Schritt 4 **Dienste starten** aus, um Dienste auf dem Server zu starten.
    
    Ausführliche Informationen zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation zu der Serverrolle, die Sie wiederherstellen.

12. Gehen Sie folgendermaßen vor, um Benutzerdaten wiederherzustellen:
    
    1.  Kopieren Sie **ExportedUserData.zip** aus **$Backup\\** in ein lokales Verzeichnis.
    
    2.  Vor dem Wiederherstellen der Benutzerdaten müssen Sie Lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    3.  Geben Sie in die Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Geben Sie zum erneuten Starten der Lync-Dienste Folgendes ein:
        
            Start-CsWindowsService

13. Stellen Sie Standortinformationsdaten im zentralen Verwaltungsspeicher wieder her. Geben Sie in die Befehlszeile Folgendes ein:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Beispiel:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Wenn Sie in diesem Pool oder auf Standard Edition-ServerReaktionsgruppe bereitgestellt haben, stellen Sie die Reaktionsgruppe-Konfigurationsdaten wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen der Reaktionsgruppeneinstellungen](lync-server-2013-restoring-response-group-settings.md).

15. Beim Wiederherstellen eines Back-End-Servers, der Archivierungs- oder Überwachungsdatenbanken enthält, stellen Sie die Archivierungs- oder Überwachungsdaten wieder her, indem Sie ein SQL-Serververwaltungstool verwenden, z. B. SQL Server Management Studio. Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs- oder Archivierungsdaten](lync-server-2013-restoring-monitoring-or-archiving-data.md).

