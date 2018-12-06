---
title: 'Lync Server 2013: ABC-Failover-Verfahren im Front-End-Pool'
TOCTitle: ABC-Failover-Verfahren im Front-End-Pool
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945635(v=OCS.15)
ms:contentKeyID: 52056373
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ABC-Failover-Verfahren im Front-End-Pool in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-05-22_

Verwenden Sie diese Schritte zum Durchführen eines ABC-Failoververfahrens. Dieses Verfahren umfasst eine allgemeine Beschreibung jedes Schritts, gefolgt von den jeweils auszuführenden Befehlen und Cmdlets.

Zum Ausführen der Cmdlet öffnen Sie eine Lync Server-Verwaltungsshell mit der Option "Als Administrator ausführen".

## So führen Sie ein ABC-Failover aus

1.  Prüfen Sie, ob Pool A der Host für den zentralen Verwaltungsserver (Central Management Server, CMS) ist.
    
      - Führen Sie das folgende Cmdlet aus:
        
            Get-CsService -CentralManagement
        
        Wenn das Feld "Identität" der aktiven CMS-Punkte auf den vollqualifizierten Domänennamen (FQDN) von Pool A verweist, führen Sie die Schritte 2 und 3 dieses Verfahrens aus, um zuerst ein Failover des zentralen Verwaltungsservers durchzuführen. Setzen Sie den Vorgang andernfalls mit Schritt 4 fort.

2.  Führen Sie ein Failover des CMS nach Pool B im Notfallwiederherstellungsmodus aus, indem Sie folgendes Cmdlet ausführen:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Anschließend wird empfohlen, den CMS von Pool B in einen anderen vorhandenen gekoppelten Pool zu verschieben, um zusätzliche Ausfallsicherheit zu erzielen. Ausführliche Informationen finden Sie unter [Move-CsManagementServer](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsManagementServer)..

3.  Wenn Pool A den CMS enthält, importieren Sie die LIS-Konfiguration von Pool A in die LIS-Datenbank (Lis.mdf) von Pool B. Dies funktioniert nur, wenn Sie LIS-Daten regelmäßig gesichert haben. Führen Sie zum Importieren der LIS-Konfiguration folgende Cmdlets aus:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importieren Sie gesicherte Workflows des Lync Server-Reaktionsgruppendiensts von Pool A in Pool B.
    

    > [!NOTE]
    > Derzeit erfordert das Cmdlet <STRONG>Import-CsRgsConfiguration</STRONG>, dass sich die Warteschlangen- und Workflownamen in Pool&nbsp;A von den Warteschlangen- und Workflownamen in Pool&nbsp;B unterscheiden. Unterscheiden sich die Namen nicht, tritt beim Ausführen des Cmdlets <STRONG>Import-CsRgsConfiguration</STRONG> ein Fehler auf, und die Warteschlangen und Workflows müssen in Pool&nbsp;B. umbenannt werden, bevor mit dem Cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> fortgefahren werden kann.

    
    Zum Importieren der Reaktionsgruppenkonfiguration von Pool A in Pool B stehen Ihnen zwei Optionen zur Verfügung. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool B mit den Einstellungen auf Anwendungsebene in Pool A überschreiben möchten.
    
      - Wenn Sie die Einstellungen von Pool B überschreiben möchten, führen Sie das Cmdlet **Import-CsRgsConfiguration** mit der Option **ReplaceExistingSettings** aus:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Wenn Sie die Einstellungen von Pool B nicht überschreiben möchten, führen Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** aus:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    

    > [!WARNING]
    > Wenn Sie die Einstellungen auf Anwendungsebene des Sicherungspools (Pool&nbsp;B) nicht mit den Einstellungen des primären Pools (Pool&nbsp;A) überschreiben möchten, gehen bei einem Verlust von Pool&nbsp;A auch die Einstellungen auf Anwendungsebene von Pool&nbsp;A verloren, da die Reaktionsgruppenanwendung nur einen Satz von Einstellungen auf Anwendungsebene pro Pool speichern kann. Wenn Pool&nbsp;C als Ersatz für Pool&nbsp;A bereitgestellt wird, müssen die Einstellungen auf Anwendungsebene neu konfiguriert werden, einschließlich der standardmäßigen Wartemusik-Audiodatei.



5.  Überprüfen Sie ob die Reaktionsgruppenkonfiguration erfolgreich importiert wurde, indem Sie die folgenden Cmdlets ausführen, um die importierten Reaktionsgruppen anzuzeigen. Beachten Sie, dass sich die importierten Reaktionsgruppen noch im Besitz von Pool A befinden.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Verschieben Sie für nicht zugewiesene Nummern die Bereiche mit dem ausgewählten Ankündigungsdiensts "Ankündigung" von Pool A nach Pool B. Gehen Sie hierzu folgendermaßen vor:
    
      - Erstellen Sie in Pool B alle Ankündigungen neu, die in Pool A bereitgestellt waren. Wenn bei der Bereitstellung der Ankündigungen in Pool A Audiodateien verwendet wurden, sind diese Dateien zum erneuten Erstellen der Ankündigungen in Pool B erforderlich. Verwenden Sie zum erneuten Erstellen der Ankündigungen in Pool B die Cmdlets **New-CsAnnouncement** mit Pool B als übergeordneten Dienst.
    
      - Konfigurieren Sie alle Bereiche für nicht zugewiesene Nummern, die für eine Ankündigung in Pool A bereitgestellt sind, für die neu bereitgestellten Ankündigungen in Pool B. Führen Sie das folgende Cmdlet für jeden Bereich für nicht zugewiesene Nummern aus, der für eine Ankündigung in Pool A bereitgestellt ist.
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    

    > [!NOTE]
    > Dieser Schritt ist für Bereiche nicht zugewiesener Nummern, bei denen "Exchange UM" als Ankündigungsdienst ausgewählt ist, nicht erforderlich.



7.  Führen Sie ein Failover von Pool A zu Pool B im Notfallwiederherstellungsmodus aus, indem Sie folgendes Cmdlet ausführen:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Erstellen Sie Pool C, starten Sie jedoch keine Dienste auf Pool C.
    
    Dieser Schritt kann gleichzeitig mit den Schritten 5 und 6 ausgeführt werden.

9.  Erzwingen Sie das Verschieben von in Pool A gehosteten Benutzern nach Pool C, indem Sie folgendes Cmdlet ausführen:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    Zu diesem Zeitpunkt wird für Benutzer, die in Pool A gehostet sind, ein Dienstausfall spürbar. Dieser Ausfall dauert bis Schritt 16 an, in dem in Pool C Dienste gestartet werden.

10. Erzwingen Sie das Verschieben des Konferenzverzeichnisses von Pool A nach Pool C, indem Sie folgendes Cmdlet ausführen:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Erzwingen Sie das Verschieben des Kontaktobjekts für die automatische Konferenztelefonzentrale (Conference Auto Attendant, CAA) von Pool A nach Pool C, indem Sie folgendes Cmdlet ausführen:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Kopiere Sie Konferenzinhalt von Pool B nach Pool C.

13. Exportieren Sie Benutzerdaten aus Pool B und importieren sie in Pool C, indem Sie folgende Cmdlets ausführen:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Stellen Sie gesicherte Daten der Anwendung zum Parken von Anrufen aus Pool A in Pool C wieder her, und weisen Sie die Orbitbereiche für das Parken von Anrufen von Pool A an Pool C zu.
    
      - Sie können einen Orbitbereich für das Parken von Anrufen von Pool A entweder über die Lync Server-Systemsteuerung oder die Lync Server-Verwaltungsshell erneut an Pool C zuweisen. Führen Sie in der Lync Server-Verwaltungsshell das folgende Cmdlet für jeden Orbitbereich für das Parken von Anrufen, der Pool A zugewiesen ist (der Identity-Parameter verweist auf die Orbitbereiche für das Parken von Anrufen, die zu Pool A gehören):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Wenn für das Parken von Anrufen in Pool A angepasste Wartemusik konfiguriert war, stellen Sie die angepassten Wartemusikdatei in Pool C wieder her.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Beispiel:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Konfigurieren Sie schließlich die Einstellungen für das Parken von Anrufen in Pool C mithilfe des Cmdlets **Set-CsCpsConfiguration** neu. In der Anwendung zum Parken von Anrufen kann nur ein Satz von Einstellungen und eine angepasste Wartemusik-Audiodatei pro Pool gespeichert werden, und diese Einstellungen werden bei einem Notfall nicht gesichert oder beibehalten.

15. Wenn der nächste Hoppool für Beständiger Chat auf Pool A verweist, nehmen Sie Topologieänderungen vor und veröffentlichen diese, damit der nächste Hopserver auf Pool C verweist.
    
      - Ändern Sie im Topologie-Generator den Pool für Beständiger Chat so, dass er auf Pool C als nächsten Hop verweist. Klicken Sie dazu mit der rechten Maustaste auf den Pool für Beständiger Chat, klicken Sie auf die Registerkarte **Allgemein** , und geben Sie dann in **Nächster Hoppool** den Namen von Pool C ein.
    
      - Starten Sie Dienste auf Pool C, indem Sie folgendes Cmdlet ausführen:
        
            Start-csWindowsService
    
    Zu diesem Zeitpunkt endet der Dienstausfall für Benutzer, die ursprünglich in Pool A gehostet waren.

16. Exportieren Sie Workflows des Lync Server-Reaktionsgruppendiensts aus Pool B im Besitz von Pool A für den Import in Pool C, indem Sie folgendes Cmdlet ausführen:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importieren Sie Workflows des Lync Server-Reaktionsgruppendiensts aus Pool B in Pool C.
    
    Zum Importieren der Reaktionsgruppenkonfiguration aus Pool B in Pool C stehen Ihnen zwei Optionen zur Verfügung. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool C mit den Einstellungen auf Anwendungsebene in Pool B überschreiben möchten.
    
      - Wenn Sie die Einstellungen von Pool C überschreiben möchten, führen Sie das Cmdlet **Import-CsRgsConfiguration** mit der Option **ReplaceExistingSettings** aus:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Wenn Sie die Einstellungen von Pool C nicht überschreiben möchten, führen Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** aus:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    

    > [!WARNING]
    > Wenn Sie die Einstellungen auf Anwendungsebene von Pool&nbsp;C nicht mit den Einstellungen des Sicherungspools (Pool&nbsp;B) überschreiben möchten, gehen die Einstellungen auf Anwendungsebene von Pool&nbsp;B verloren, da die Reaktionsgruppenanwendung nur einen Satz von Einstellungen auf Anwendungsebene pro Pool speichern kann.



18. Überprüfen Sie ob die Reaktionsgruppenkonfiguration erfolgreich importiert wurde, indem Sie die folgenden Cmdlets ausführen, um die in Pool C importierten Reaktionsgruppen anzuzeigen.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Wenn die importierte Konfiguration in Pool C überprüft wurde, entfernen Sie die Reaktionsgruppen im Besitz des primären Pools aus Pool B. Dadurch wird die Ausfallzeit der Reaktionsgruppen möglichst gering gehalten.
    
    In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt und dann die Datei aus Pool B entfernt.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Verschieben Sie die Bereiche nicht zugewiesener Nummern, die von Pool A nach Pool B verschoben wurden, nach Pool C.
    
      - Erstellen Sie in Pool C alle Ankündigungen erneut, die aus Pool A stammen und in Pool B erneut erstellt wurden. Wenn bei der Bereitstellung der zu verschiebenden Ankündigungen Audiodateien verwendet wurden, müssen Sie diese Dateien zum erneuten Erstellen der Ankündigungen in Pool C verwenden. Verwenden Sie zum erneuten Erstellen der Ankündigungen in Pool C die Cmdlets **New-CsAnnouncement** mit Pool C als übergeordneten Dienst.
    
      - Konfigurieren Sie in Pool C alle Bereiche nicht zugewiesener Nummern, die aus Pool A stammen und in Pool B konfiguriert wurden. Führen Sie das folgende Cmdlet für alle zu konfigurierenden Bereiche nicht zugewiesener Nummern aus:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - (Optional) Entfernen Sie aus Pool B die in Pool C erneut erstellen Ankündigungen, wenn diese in Pool B nicht mehr verwendet werden. Verwenden Sie zum Entfernen der Ankündigungen das Cmdlet **Remove-CsAnnouncement**.
        

        > [!NOTE]
        > Dieser Schritt ist für Bereiche nicht zugewiesener Nummern, die "Exchange UM" als Ankündigungsdienst verwenden, nicht erforderlich.



21. Bereinigen Sie Benutzerdaten aus Pool A in Pool B, indem Sie folgendes Cmdlet ausführen:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Führen Sie im Topologie-Generator folgende Schritte aus:
    
      - Entkoppeln Sie Pool A und Pool B. Koppeln Sie Pool B und Pool C. Entfernen Sie dann Pool A aus der Topologie, und veröffentlichen Sie sie. Gehen Sie hierzu folgendermaßen vor:
        
          - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf Pool B und dann auf **Eigenschaften bearbeiten** .
        
          - Klicken Sie im linken Bereich auf **Flexibilität** .
        
          - Wählen Sie im Feld unter **Zugeordneter Sicherungspool** Pool C aus. Im Auswahlfeld "Zugeordneter Sicherungspool" wird zunächst Pool A angezeigt, da zuvor Pool B diesem Pool zugeordnet war.
        
          - Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK** .
            
            Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität** .
        
          - Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf Pool A, und klicken Sie dann auf "Löschen".
        
          - Veröffentlichen Sie die Topologie.

23. Führen Sie in Pool C die Bootstrapping-Anwendung aus, um die Sicherungsdienstanwendung zu installieren, und starten Sie dann die Sicherungsdienstanwendung, indem Sie auf einem lokalen Computer in Pool C im Bereitstellungsordner Folgendes ausführen:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Starten Sie die Sicherungsdienstanwendung in Pool B neu, indem Sie folgende Cmdlets ausführen:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Wenn es sich bei Pool C um einen Standard Edition (SE)-Pool handelt und Pool B den CMS hostet, installieren Sie die CMS-Datenbank manuell in Pool C, indem Sie das folgende Cmdlet ausführen:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Rufen Sie den Sicherungsdienst auf um Folgendes durchzuführen: Synchronisieren von altem Konferenzinhalt, der vor der Kopplung von Pool B und Pool C generiert wurde, aus Pool B mit Pool C; Synchronisierung neuen Konferenzinhalts, der nach dem Starten von Pool C und vor der Kopplung von B und C generiert wurde, aus Pool C mit Pool B. Führen Sie dazu die folgenden Cmdlets aus:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Für jede Survivable Branch Appliance X, die Pool A zugeordnet ist:
    
      - Beenden Sie die SBA X, indem Sie folgendes Cmdlet ausführen:
        
            Stop-CsWindowsService
    
      - Erstellen Sie eine Datei, die eine Liste aller in der SBA X gehosteten Benutzer enthält. Die Liste wird benötigt, wenn die Benutzer in Schritt 30 wieder in die SBA X verschoben werden. Führen Sie dazu das folgende Cmdlet aus:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Erzwingen Sie das Verschieben von in der SBA X gehosteten Benutzern nach Pool C, indem Sie folgendes Cmdlet ausführen:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Aktualisieren Sie die Daten dieser Benutze, indem Sie zuerst folgende Cmdlets ausführen:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Führen Sie anschließend dieses Skript aus:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - }
        

        > [!NOTE]
        > Für Benutzer, die in SBAs gehostet sind, die Pool&nbsp;A zugewiesen sind, erfolgt ein Dienstausfall, bis diese Benutzer in Pool&nbsp;C verschoben werden.



28. Führen Sie im Topologie-Generator für jede SBA X, die zuvor Pool A zugeordnet war, folgende Schritte aus:
    
      - Ändern Sie die Zuordnung zu Pool C. Klicken Sie dazu auf Zweigstellenstandort, erweitern Sie den Knoten "Survivable Branch Appliances" oder "Server", und klicken Sie auf **Survivable Branch Appliance** . Wählen Sie dann den **Front-End-Pool oder Benutzerdienstepool** , zu dem diese Survivable Branch Appliance eine Verbindung als Pool C herstellt. Klicken Sie dann auf **Weiter** .
    
      - Veröffentlichen Sie die Topologie. Klicken Sie dazu in der Konsolenstruktur mit der rechten Maustaste auf das neue **Survivable Branch Appliance** , klicken Sie auf **Topologie** und dann auf **Veröffentlichen** .

29. Für jede SBA X, die jetzt Pool C zugeordnet ist:
    
      - Starten Sie die SBA X, indem Sie in der Survivable Branch Appliance folgendes Cmdlet ausführen:
        
            Start-CsWindowsService
    
      - Verschieben Sie Benutzer, die ursprünglich in der SBA X gehostet waren aus Pool C in die SBA X, indem Sie folgendes Cmdlet ausführen.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

