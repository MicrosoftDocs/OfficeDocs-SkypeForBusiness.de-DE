---
title: 'Lync Server 2013: Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2af346baefbbf1084debed4e7f8fd98eada4a34e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Eine lync Server-Bereitstellung verfügt über einen einzelnen zentralen Verwaltungsspeicher, dessen Kopie auf jeden Server repliziert wird, auf dem eine lync Server-Serverrolle ausgeführt wird. In diesem Thema wird beschrieben, wie Sie einen Back-End-Server oder Standard Edition-Server wiederherstellen, der den zentralen Verwaltungsspeicher hostet.

Um den Pool zu finden, in dem sich der zentrale Verwaltungsserver befindet, öffnen Sie den Topologie-Generator, klicken Sie auf **lync Server**, und suchen Sie im rechten Bereich unter **zentrale Verwaltungsserver**.

Wenn sich der Back-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet, in einem gespiegelten Setup befindet und die Spiegeldatenbank weiterhin funktionsfähig ist, wird empfohlen, dass Sie eine Sicherung dieser noch funktionsfähigen Spiegelung durchführen und dann eine vollständige Wiederherstellung der primären Datenbank und der Spiegeldatenbank mit dieser Sicherung, indem Sie das folgende Wiederherstellungsverfahren ausführen. Dies ist erforderlich, da für die Back-End-Wiederherstellung die Topologie geändert und veröffentlicht werden muss, und dies ist nur möglich, wenn die primäre Datenbank, die CMS hostet, betriebsbereit ist. Beachten Sie auch, dass die primäre und die Spiegel Datenbankrolle nicht ausgetauscht werden können, wenn die Topologie nicht veröffentlicht werden kann.

<div>


> [!NOTE]  
> Wenn ein Back-End-Server oder Standard Edition-Server, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird, fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</A> oder <A href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</A>. Wenn sich ein Back-End-Server, der den zentralen Verwaltungsspeicher hostet, in einer gespiegelten Konfiguration befindet und nur die Spiegelung fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror</A>. Wenn ein anderer Server fehlgeschlagen ist, finden Sie weitere Informationen unter <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</A>.



</div>

<div>


> [!TIP]  
> Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>So stellen Sie den zentralen Verwaltungsspeicher wieder her

1.  Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.

    
    </div>

2.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins und der lokalen Administratoren ist, bei dem Server an, den Sie wiederherstellen möchten.

3.  Wenn Sie ein Standard Edition-Server wiederherstellen, stellen Sie das Dateispeicher wieder her, indem Sie das entsprechende Dateispeicher aus $Backup in den Dateispeicher Speicherort auf dem Server kopieren und dann den Ordner freigeben.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Pfad und der Dateiname für das wiederhergestellte Dateispeicher sollten genau mit dem gesicherten Dateispeicher identisch sein, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.

    
    </div>

4.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie ein Standard Edition-Server installieren möchten, wechseln Sie zum Installationsordner für lync Server oder Medien, und starten Sie dann den lync Server-Bereitstellungs\\-\\Assistenten unter \\Setup amd64 Setup. exe. Klicken Sie im Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten** , und führen Sie den Assistenten aus, um den zentralen Verwaltungsspeicher zu installieren.
    
      - Wenn Sie einen Enterprise-Back-End-Server installieren, installieren Sie SQL Server 2012 oder SQL Server 2008 R2, wobei die Instanznamen wie vor dem Fehler beibehalten werden.
        
        <div>
        

        > [!NOTE]  
        > Je nach dem Server, den Sie wiederherstellen, und in der Bereitstellung kann der Server mehrere zusammenhängende oder getrennte Datenbanken umfassen. Führen Sie das gleiche Verfahren zum Installieren von SQL Server durch, mit dem Sie auch ursprünglich den Server bereitgestellt haben, einschließlich SQL Server-Berechtigungen und -Anmeldungen.

        
        </div>

5.  Starten Sie in einem Front-End-Server das lync Server-Verwaltungsshell: Klicken Sie auf **Start**, auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

6.  Erstellen Sie den zentralen Verwaltungsspeicher erneut. Geben Sie in die Befehlszeile Folgendes ein:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Beispiel:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Legen Sie den Active Directory-Domänendienste Kontrollpunkt für den zentralen Verwaltungsspeicher fest. Geben Sie in die Befehlszeile Folgendes ein:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Beispiel:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Sollten Sie den Verbindungspunkt verlieren, können Sie dieses Cmdlet erneut ausführen.

    
    </div>

8.  Importieren Sie die Daten des zentralen Verwaltungsspeichers aus $Backup. Geben Sie in die Befehlszeile Folgendes ein:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Beispiel:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Aktivieren Sie die eben vorgenommenen Änderungen. Geben Sie in die Befehlszeile Folgendes ein:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Nach dem Aktivieren der Topologie wird das Topologiedokument in der Datenbank angezeigt.

    
    </div>

10. Wenn Sie einen Enterprise Edition-Back-End-Server wiederherstellen, der auch den CMS gehostet hat, oder wenn Sie eine Spiegelung des CMS neu erstellen müssen, führen Sie diesen Schritt aus. Fahren Sie andernfalls mit Schritt 11 fort.
    
    Installieren Sie die eigenständigen Datenbanken, indem Sie die folgenden Schritte ausführen:
    
    1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.
    
    2.  Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie auf **Speichern**. Klicken Sie auf **Ja**, um die Auswahl zu bestätigen.
    
    4.  Klicken Sie mit der rechten Maustaste auf den Knoten **lync Server 2013** , und klicken Sie dann auf **Datenbank installieren**.
    
    5.  Führen Sie den Assistenten zum **Installieren einer Datenbank** aus. Wenn Sie eine andere Datenbank als den zentralen Verwaltungsspeicher auf diesem Server wiederherstellen, wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.
        
        <div>
        

        > [!NOTE]  
        > Auf der Seite <STRONG>Erstellen von Datenbanken</STRONG> werden nur eigenständige Datenbanken angezeigt. Zusammengeführte Datenbankenwerden erstellt, wenn Sie den lync Server-Bereitstellungs-Assistenten ausführen.

        
        </div>
    
    6.  Wenn Sie einen gespiegelten Back-End-Server wiederherstellen, fahren Sie mit dem Rest des Assistenten fort, bis Sie eine Eingabeaufforderung zum Erstellen einer Spiegeldatenbank erhalten. Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie den Vorgang aus.
    
    7.  Folgen Sie den Anweisungen auf den weiteren Seiten des Assistenten, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!TIP]  
    > Anstatt den Topologie-Generator auszuführen, können Sie das Cmdlet <STRONG>install-CsDatabase</STRONG> verwenden, um die einzelnen Datenbanken zu erstellen, und das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> , um die Spiegelung zu konfigurieren. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> und <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.

    
    </div>

11. Wenn Sie ein Standard Edition-Server wiederherstellen, wechseln Sie zum Installationsordner lync Server oder Medien, und starten Sie den lync Server-Bereitstellungs \\-\\Assistenten\\unter Setup amd64 Setup. exe. Verwenden Sie den lync Server-Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:
    
    1.  Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server Komponenten** aus, um die lync Server-Server Rollen zu installieren.
    
    3.  Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um die Dienste auf dem Server zu starten.
    
    Ausführliche Informationen zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.

12. Gehen Sie folgendermaßen vor, um Benutzerdaten wiederherzustellen:
    
    1.  Kopieren Sie ExportedUserData. zip aus\\ $Backup in ein lokales Verzeichnis.
    
    2.  Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    3.  Geben Sie in die Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Starten Sie lync Services neu, indem Sie Folgendes eingeben:
        
            Start-CsWindowsService

13. Stellen Sie Standort Informationsdaten im zentralen Verwaltungsspeicher wieder her. Geben Sie in die Befehlszeile Folgendes ein:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Beispiel:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Wenn Sie die Reaktionsgruppe in diesem Pool oder Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Reaktionsgruppeneinstellungen in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Wenn Sie einen Back-End-Server, der Archivierungs-oder Überwachungsdatenbanken enthält, wiederherstellen, stellen Sie die Archivierungs-oder Überwachungsdaten mithilfe eines SQL Server Verwaltungstools wie SQL Server Management Studio wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

