---
title: 'Lync Server 2013: Front-End-Pool ABC-Failover-Verfahren'
description: 'Lync Server 2013: Front-End-Pool ABC-Failover-Verfahren.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86f196d53afdc1dcad6fe41191c2aa1582f717e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567141"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Front-End-Pool ABC-Failover-Verfahren in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-22_

Führen Sie die folgenden Schritte aus, um das ABC-Failover-Verfahren durchzuführen. Dieses Verfahren enthält eine allgemeine Beschreibung der einzelnen Schritte, gefolgt von Befehlen und Cmdlets, die für jeden Schritt ausgeführt werden sollen.

Öffnen Sie zum Ausführen der Cmdlets ein lync Server-Verwaltungsshell verwenden Sie als Administrator ausführen.

<div>

## <a name="to-perform-an-abc-failover"></a>So führen Sie ein ABC-Failover aus

1.  Überprüfen Sie, ob der Pool A der Host für den zentralen Verwaltungs Server (CMS) ist.
    
      - Führen Sie das folgende Cmdlet aus:
        
            Get-CsService -CentralManagement
        
        Wenn das Feld "Identity" des aktiven CMS auf den vollqualifizierten Domänennamen (FQDN) von Pool A verweist, verwenden Sie die Schritte 2 und 3 dieses Verfahrens, um zuerst einen Failover des zentralen Verwaltungsservers durchführen zu müssen. Fahren Sie andernfalls mit Schritt 4 fort.

2.  Führen Sie einen Failover des CMS zu Pool B im Notfall Wiederherstellungsmodus durch, indem Sie das folgende Cmdlet ausführen:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Nachdem Sie dies getan haben, empfehlen wir Ihnen, den CMS von Pool B in einen anderen vorhandenen gekoppelten Pool zu versetzen, um zusätzliche Ausfallsicherheit zu erreichen. Ausführliche Informationen finden Sie unter [CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Wenn Pool a CMS enthält, importieren Sie die LIS-Konfiguration aus Pool a in die LIS-Datenbank von Pool B (LIS. mdf). Dies ist nur möglich, wenn Sie regelmäßig LIS-Daten gesichert haben. Führen Sie die folgenden Cmdlets aus, um die LIS-Konfiguration zu importieren:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importieren Sie die gesicherten lync Server-Reaktionsgruppendienst-Workflows von Pool a in Pool B.
    
    <div>
    

    > [!NOTE]  
    > Das Cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> erfordert derzeit, dass sich die Warteschlangen-und Workflownamen in Pool a von den Warteschlangen-und Workflownamen in Pool B unterscheiden. Wenn die Namen nicht unterschiedlich sind, erhalten Sie eine Fehlermeldung, wenn Sie das <STRONG>Import-CsRgsConfiguration-</STRONG> Cmdlet ausführen, und die Warteschlangen und Workflows müssen in Pool B umbenannt werden, bevor Sie mit <STRONG>Import-CsRgsConfiguration-</STRONG> Cmdlet fortfahren.

    
    </div>
    
    Sie haben zwei Optionen zum Importieren der Reaktionsgruppen Konfiguration von Pool a in Pool B. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool B mit den Einstellungen auf Anwendungsebene in Pool A überschreiben möchten.
    
      - Wenn Sie die Pool B-Einstellungen überschreiben möchten, führen Sie das **Import-CsRgsConfiguration-** Cmdlet mit der Option **ReplaceExistingSettings** aus:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Wenn Sie die Einstellungen für Pool B nicht überschreiben möchten, verwenden Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Beachten Sie, dass, wenn Sie die Einstellungen auf Anwendungsebene des Sicherungs Pools (Pool B) nicht mit den Einstellungen des primären Pools (Pool a) überschreiben möchten, die Einstellungen auf Anwendungsebene von Pool a verloren gehen, wenn Pool a verloren geht, da die Reaktionsgruppenanwendung nur eine Gruppe von Einstellungen auf Anwendungsebene pro Pool speichern kann. Wenn Pool C zum Ersetzen von Pool A bereitgestellt wird, müssen die Einstellungen auf Anwendungsebene neu konfiguriert werden, einschließlich der standardmäßigen Musikarchiv-Audiodatei.

    
    </div>

5.  Stellen Sie sicher, dass der Konfigurations Import für Reaktionsgruppen erfolgreich war, indem Sie die folgenden Cmdlets ausführen, um die importierten Reaktionsgruppen anzuzeigen. Beachten Sie, dass die importierten Reaktionsgruppen weiterhin im Besitz von Pool A sind.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Für nicht zugewiesene Nummern müssen Sie die Bereiche mit der nicht zugewiesenen Nummer, die "Ansage" verwenden, als ausgewählten Ankündigungsdienst von Pool a in Pool B verlagern. Dazu:
    
      - Erstellen Sie alle Ankündigungen neu, die in Pool a in Pool B bereitgestellt wurden. Wenn beim Bereitstellen der Ankündigungen in Pool A Audiodateien verwendet wurden, werden diese Dateien benötigt, um die Ankündigungen in Pool B neu zu erstellen. Um die Ankündigungen in Pool b neu zu erstellen, verwenden Sie die Cmdlets **New-CsAnnouncement** , wobei Pool b als übergeordneter Dienst verwendet wird.
    
      - Richten Sie alle nicht zugewiesenen Nummernbereiche, die auf eine Ansage in Pool a Zielen, auf die neu bereitgestellten Ankündigungen in Pool B aus. führen Sie das folgende Cmdlet für jeden nicht zugewiesenen Nummernbereich aus, der auf eine Ankündigung von Pool a abzielt:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Dieser Schritt ist für nicht zugewiesene Nummernbereiche nicht erforderlich, die "Exchange um" als ausgewählten Ankündigungsdienst verwenden.

    
    </div>

7.  Führen Sie ein Failover von Pool a an Pool B im Notfall Wiederherstellungsmodus (Dr) durch, indem Sie das folgende Cmdlet ausführen:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Erstellen Sie Pool c, starten Sie jedoch keine Dienste in Pool c.
    
    Beachten Sie, dass dieser Schritt gleichzeitig mit den Schritten 5 und 6 ausgeführt werden kann.

9.  Erzwingen, dass Benutzer in Pool A in Pool C verschoben werden, indem Sie das folgende Cmdlet ausführen:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    Zu diesem Zeitpunkt beginnt der Benutzer, der in Pool A verwaltet wird, einen Dienstausfall zu erfahren. Dieser Ausfall wird fortgesetzt, bis Schritt 16, an dem Punkt Dienste in Pool C gestartet werden.

10. Erzwingen Sie, dass das Konferenzverzeichnis von Pool A in Pool C wechselt, indem Sie das folgende Cmdlet ausführen:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Erzwingen Sie, dass das Kontaktobjekt der automatischen Telefonzentrale (CAA) von Pool A zu Pool C wechselt, indem Sie das folgende Cmdlet ausführen:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Kopieren von Konferenz Inhalten von Pool B in Pool C.

13. Exportieren Sie Benutzerdaten aus Pool B, und importieren Sie die Benutzerdaten in Pool C, indem Sie die folgenden Cmdlets ausführen:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Stellen Sie die gesicherten Anwendung zum Parken von Anrufen Daten von Pool a in Pool c wieder her, und weisen Sie den orbitbereich des Anruf Parks von Pool a dem Pool c zu.
    
      - Sie können einen orbitbereich für das Parken von Anrufen an Pool C entweder über die lync Server-Systemsteuerung oder den lync Server-Verwaltungsshell neu zuweisen. Führen Sie für den lync Server-Verwaltungsshell das folgende Cmdlet für jeden orbitbereich für das Parken von Anrufen aus, der Pool a zugewiesen ist (Beachten Sie, dass der Parameter Identity auf die orbitbereiche zum Parken von Anrufen verweist, die zu Pool a gehören):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Wenn ein benutzerdefiniertes Music-on-Hold-Objekt in Pool a für das Parken von Anrufen konfiguriert wurde, stellen Sie die angepasste Music-on-Hold-Datei für das Parken von Anrufen in Pool C wieder her.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Zum Beispiel:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Konfigurieren Sie schließlich die Einstellungen für das Parken von Anrufen in Pool C mithilfe des Cmdlets " **CsCpsConfiguration** ". Das Anwendung zum Parken von anrufen kann nur einen Einstellungssatz und eine benutzerdefinierte Audiodatei pro Pool speichern, und diese Einstellungen werden im Falle eines Notfalls nicht gesichert oder beibehalten.

15. Wenn der Pool für den nächsten Hop für den beständigen Chat auf Pool A zeigt, stellen und veröffentlichen Sie Topologie-Änderungen, sodass der Server des nächsten Hops auf Pool C verweist.
    
      - Ändern Sie im Topologie-Generator den Pool für beständigen Chat so, dass er als nächster Hop auf Pool C verweist. Klicken Sie dazu mit der rechten Maustaste auf den Pool für beständigen Chat, klicken Sie auf die Registerkarte **Allgemein** , und geben Sie dann den Namen des Pools C im **Pool nächster Hop**ein.
    
      - Starten Sie die Dienste in Pool C, indem Sie das folgende Cmdlet ausführen:
        
            Start-csWindowsService
    
    An diesem Punkt endet der Dienstausfall für Benutzer, die ursprünglich in Pool A verwaltet wurden.

16. Exportieren Sie lync Server Workflows für Reaktionsgruppen Dienste von Pool B im Besitz von Pool a für den Import in Pool C, indem Sie das folgende Cmdlet ausführen:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importieren Sie lync Server Workflows für Reaktionsgruppen Dienste in Pool C aus Pool B.
    
    Sie haben zwei Möglichkeiten zum Importieren der Reaktionsgruppen Konfiguration von Pool B in Pool C. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool C mit den Einstellungen auf Anwendungsebene in Pool B überschreiben möchten.
    
      - Wenn Sie die Pool-C-Einstellungen überschreiben möchten, führen Sie das **Import-CsRgsConfiguration-** Cmdlet mit der Option **ReplaceExistingSettings** aus:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Wenn Sie die Pool C-Einstellungen nicht überschreiben möchten, verwenden Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Beachten Sie, dass, wenn Sie die Einstellungen auf Anwendungsebene von Pool C nicht mit den Einstellungen des Sicherungs Pools (Pool b) überschreiben möchten, die Einstellungen auf Anwendungsebene von Pool b verloren gehen, da der Reaktionsgruppenanwendung nur eine Gruppe von Einstellungen auf Anwendungsebene pro Pool speichern kann.

    
    </div>

18. Stellen Sie sicher, dass der Konfigurations Import für Reaktionsgruppen erfolgreich war, indem Sie die folgenden Cmdlets ausführen, um die Reaktionsgruppen anzuzeigen, die in Pool C importiert wurden.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Wenn die importierte Konfiguration in Pool C überprüft wurde, entfernen Sie die Reaktionsgruppen im Besitz des primären Pools aus Pool B. Dadurch wird die Ausfallzeit der Reaktionsgruppen minimiert.
    
    In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt, und die Datei wird dann aus Pool B entfernt.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Verschieben Sie den Bereich nicht zugewiesene Nummernbereiche, die von Pool a in Pool B verschoben wurden, in Pool C.
    
      - Erstellen Sie alle Ankündigungen, die aus Pool a in Pool B neu erstellt wurden, in Pool C neu. Wenn beim Bereitstellen der zu verschiebenden Ankündigungen Audiodateien verwendet wurden, müssen Sie diese Dateien verwenden, um die Ankündigungen in Pool C neu zu erstellen. Um die Ankündigungen in Pool c neu zu erstellen, verwenden Sie die Cmdlets **New-CsAnnouncement** , wobei Pool c als übergeordneter Dienst verwendet wird.
    
      - Retarget to Pool C alle nicht zugewiesenen Nummernbereiche, die von Pool a auf Pool B umzielt wurden führen Sie das folgende Cmdlet für jeden nicht zugewiesenen Nummernbereich aus, der neu ausgerichtet werden muss:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Optional Entfernen Sie aus Pool b die Ankündigungen, die in Pool C neu erstellt wurden, wenn Sie in Pool b nicht mehr verwendet werden. Verwenden Sie das Cmdlet **Remove-CsAnnouncement** , um Ankündigungen zu entfernen.
        
        <div>
        

        > [!NOTE]  
        > Dieser Schritt ist für nicht zugewiesene Nummernbereiche nicht erforderlich, die "Exchange um" als Ankündigungsdienst verwenden.

        
        </div>

21. Bereinigen Sie die Benutzerdaten von Pool a in Pool B, indem Sie das folgende Cmdlet ausführen:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Führen Sie im Topologie-Generator folgende Schritte aus:
    
      - Unpair Pool a und Pool b. Pair Pool b und Pool C. Entfernen Sie dann Pool A aus der Topologie, und veröffentlichen Sie es. Gehen Sie hierzu folgendermaßen vor:
        
          - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf Pool B, und klicken Sie dann auf **Eigenschaften bearbeiten**.
        
          - Klicken Sie im linken Bereich auf **Ausfallsicherheit** .
        
          - Wählen Sie im Feld unter **zugeordneter Sicherungspool**die Option Pool C. Beachten Sie, dass im zugehörigen Auswahlfeld Sicherungspool zunächst Pool a angezeigt wird, da Pool B zuvor diesem Pool zugeordnet wurde.
        
          - Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.
            
            Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**.
        
          - Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf Pool A, und klicken Sie dann auf Löschen.
        
          - Veröffentlichen Sie die Topologie.

23. Führen Sie die Bootstrapping-Anwendung in Pool c aus, um die Sicherungsdienst Anwendung zu installieren, und starten Sie dann die Sicherungsdienst Anwendung, indem Sie den folgenden Befehl aus dem Bereitstellungsordner auf einem lokalen Computer in Pool c ausführen:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Starten Sie die Sicherungsdienst Anwendung in Pool B neu, indem Sie die folgenden Cmdlets ausführen:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Wenn Pool c ein Standard Edition-Pool (SE) ist und Pool B über einen CMS verfügt, installieren Sie die CMS-Datenbank manuell in Pool c, indem Sie das folgende Cmdlet ausführen:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Rufen Sie den Sicherungsdienst auf, um alte Konferenzinhalte von Pool b mit Pool c zu synchronisieren, die vor dem Koppeln von b und c generiert wurden, und um neue Konferenzinhalte von Pool c zu Pool b zu synchronisieren, die nach dem Starten von Pool c generiert wurden und bevor b und c zusammen gekoppelt wurden. Führen Sie dazu die folgenden Cmdlets aus:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Für jede Survivable Branch Appliance X, die mit Pool A verbunden ist:
    
      - Fahren Sie SBA X herunter, indem Sie das folgende Cmdlet ausführen:
        
            Stop-CsWindowsService
    
      - Erstellen Sie eine Datei, die eine Liste der Benutzer enthält, die in SBA X verwaltet werden. Die Liste wird benötigt, wenn die Benutzer in Schritt 30 zurück zu SBA X verschoben werden. Führen Sie dazu das folgende Cmdlet aus:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Erzwingen Sie, dass Benutzer, die in SBA X verwaltet werden, zu Pool C migrieren, indem Sie das folgende Cmdlet ausführen:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Aktualisieren Sie die Daten dieser Benutzer, indem Sie zunächst die folgenden Cmdlets ausführen:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Und führen Sie dann dieses Skript aus:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > Für Benutzer, die in SBAS verwaltet werden, die mit Pool a verbunden sind, tritt ein Dienstausfall auf, bis diese Benutzer zu Pool C verschoben werden.

        
        </div>

28. Führen Sie im Topologie-Generator für jede SBA X, die zuvor mit Pool A verbunden ist, folgende Schritte aus:
    
      - Ändern Sie die Zuordnung zu Pool C. Klicken Sie dazu auf den Zweigstellenstandort, erweitern Sie den Knoten Survivable Branch Appliances oder Servers, und klicken Sie auf **Survivable Branch Appliance**. Wählen Sie dann die **Front-End-Pool, den Benutzer Dienste-Pool** , mit dem dieser Survivable Branch Appliance eine Verbindung herstellen wird, als Pool C aus, und klicken Sie dann auf **weiter**.
    
      - Veröffentlichen Sie die Topologie. Klicken Sie dazu in der Konsolenstruktur mit der rechten Maustaste auf den neuen **Survivable Branch Appliance**, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.

29. Für jede SBA X, die jetzt mit Pool C verbunden ist:
    
      - Starten Sie SBA X, indem Sie das folgende Cmdlet auf der Survivable Branch Appliance ausführen:
        
            Start-CsWindowsService
    
      - Führen Sie das folgende Cmdlet aus, um Benutzer zu migrieren, die ursprünglich in SBA x von Pool C nach SBA x verwaltet wurden.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

