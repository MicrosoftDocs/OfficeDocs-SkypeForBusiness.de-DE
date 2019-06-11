---
title: 'Lync Server 2013: Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher gehostet wird'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet wird

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Eine lync Server-Bereitstellung verfügt über einen einzelnen zentralen Verwaltungsspeicher, dessen Kopie auf jeden Server repliziert wird, auf dem eine lync Server-Serverrolle ausgeführt wird. In diesem Thema wird beschrieben, wie Sie einen Back-End-Server oder Standard Edition-Server wiederherstellen, der den zentralen Verwaltungsspeicher hostet.

Zum Auffinden des Pools, in dem sich der zentrale Verwaltungsserver befindet, öffnen Sie den Topologie-Generator, klicken Sie auf **lync Server**, und suchen Sie im rechten Bereich unter **zentraler Verwaltungsserver**.

Wenn sich der Back-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet, in einem gespiegelten Setup befindet und die Spiegeldatenbank weiterhin funktionsfähig ist, empfehlen wir, dass Sie eine Sicherungskopie dieser noch funktionierenden Spiegelung erstellen und dann eine vollständige Wiederherstellung sowohl auf der primären als auch auf der primären Datenbank durchführen. spiegeln Sie die Datenbank mithilfe dieser Sicherung, indem Sie das nachstehende Wiederherstellungsverfahren ausführen. Dies ist erforderlich, da für die Back-End-Wiederherstellung die Topologie geändert und veröffentlicht werden muss und dies nur möglich ist, wenn die primäre Datenbank-Hosting-CMS funktionsfähig ist. Beachten Sie auch, dass die Primär-und Spiegel Datenbankrollen nicht austauschbar sind, wenn die Topologie nicht veröffentlicht werden kann.

<div>


> [!NOTE]  
> Wenn ein Back-End-Server oder Standard Edition-Server, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird, fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</A> oder <A href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</A>. Wenn sich ein Back-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet, in einer gespiegelten Konfiguration befindet und nur der Spiegel Fehler aufgetreten ist, lesen Sie <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013</A> Wenn ein anderer Server fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</A>.



</div>

<div>


> [!TIP]  
> Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>So stellen Sie den zentralen Verwaltungsspeicher wieder her

1.  Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Befolgen Sie die Server Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt ausführen zu können.

    
    </div>

2.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe und der lokalen Gruppe Administratoren ist, bei dem Server an, den Sie wiederherstellen möchten.

3.  Wenn Sie einen Standard Edition-Server wiederherstellen, stellen Sie den Dateispeicher wieder her, indem Sie den entsprechenden Dateispeicher aus $Backup in den Dateispeicher Speicherort auf dem Server kopieren und dann den Ordner freigeben.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Pfad und Dateinamen für den wiederhergestellten Dateispeicher sollten exakt mit dem gesicherten Dateispeicher identisch sein, damit die Komponenten, die die Dateien verwenden, darauf zugreifen können.

    
    </div>

4.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie einen Standard Edition-Server installieren, suchen Sie nach dem lync Server-Installationsordner oder-Medium, und starten Sie dann den lync Server \\-\\Bereitstellungs-Assistenten, der sich unter Setup amd64\\Setup. exe befindet. Klicken Sie im Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten** , und folgen Sie dem Assistenten, um den zentralen Verwaltungsspeicher zu installieren.
    
      - Wenn Sie einen Enterprise-Back-End-Server installieren, installieren Sie SQL Server 2012 oder SQL Server 2008 R2, wobei die Namen der Instanz wie vor dem Fehler identisch sind.
        
        <div>
        

        > [!NOTE]  
        > Je nach dem Server, den Sie wiederherstellen, und bei der Bereitstellung umfasst der Server möglicherweise mehrere zusammengefasste oder getrennte Datenbanken. Führen Sie die gleichen Schritte aus, um SQL Server zu installieren, den Sie ursprünglich für die Bereitstellung des Servers verwendet haben, einschließlich SQL Server-Berechtigungen und-Anmeldungen.

        
        </div>

5.  Starten Sie die lync Server-Verwaltungsshell von einem Front-End-Server: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

6.  Erstellen Sie den zentralen Verwaltungsspeicher erneut. Geben Sie in der Befehlszeile Folgendes ein:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Beispiel:
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  Legen Sie den Active Directory-Domänendienste-Kontrollpunkt für den zentralen Verwaltungsspeicher fest. Geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    Beispiel:
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie den Verbindungspunkt verloren haben, können Sie dieses Cmdlet erneut ausführen.

    
    </div>

8.  Importieren Sie die Daten des zentralen Verwaltungsspeichers aus $Backup. Geben Sie in der Befehlszeile Folgendes ein:
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    Beispiel:
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  Aktivieren Sie die soeben vorgenommenen Änderungen. Geben Sie in der Befehlszeile Folgendes ein:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Nachdem Sie die Topologie aktiviert haben, können Sie das Topologie-Dokument in der Datenbank finden.

    
    </div>

10. Wenn Sie einen Enterprise Edition-Back-End-Server wiederherstellen, der auch den CMS gehostet hat, oder wenn Sie eine Spiegelung des CMS neu erstellen müssen, führen Sie diesen Schritt aus. Fahren Sie andernfalls mit Schritt 11 fort.
    
    Führen Sie die folgenden Schritte aus, um die eigenständigen Datenbanken zu installieren:
    
    1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.
    
    2.  Klicken Sie auf **Topologie aus vorhandener Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie dann auf **Speichern**. Klicken Sie auf **Ja** , um die Auswahl zu bestätigen.
    
    4.  Klicken Sie mit der rechten Maustaste auf den **lync Server 2013** -Knoten, und klicken Sie dann auf **Datenbank installieren**.
    
    5.  Folgen Sie dem Assistenten zum **Installieren der Datenbank** . Wenn Sie eine andere Datenbank als den zentralen Verwaltungsspeicher auf diesem Server wiederherstellen, wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.
        
        <div>
        

        > [!NOTE]  
        > Auf der Seite " <STRONG>Datenbankenerstellen</STRONG> " werden nur eigenständige Datenbanken angezeigt. Wenn Sie den lync Server-Bereitstellungs-Assistenten ausführen, werden die Datenbanken erstellt.

        
        </div>
    
    6.  Wenn Sie einen gespiegelten Back-End-Server wiederherstellen, folgen Sie dem restlichen Assistenten, bis Sie zu einer Aufforderung zum Erstellen einer Spiegeldatenbank gelangen. Wählen Sie die Datenbank aus, die Sie installieren möchten, und schließen Sie den Vorgang ab.
    
    7.  Führen Sie den restlichen Assistenten aus, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!TIP]  
    > Anstelle des Topologie-Generators können Sie das Cmdlet " <STRONG>install-CsDatabase</STRONG> " verwenden, um jede Datenbank zu erstellen, und das Cmdlet " <STRONG>install-CsMirrorDatabase</STRONG> ", um die Spiegelung zu konfigurieren. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Installieren-CsDatabase</A> und <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Installieren-CsMirrorDatabase</A>.

    
    </div>

11. Wenn Sie einen Standard Edition-Server wiederherstellen, wechseln Sie zum lync Server-Installationsordner oder-Medium, und starten Sie den lync Server \\-\\Bereitstellungs-Assistenten unter Setup amd64\\Setup. exe. Verwenden Sie den lync Server-Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:
    
    1.  Führen Sie **Schritt 1: Installieren des lokalen Konfigurationsspeichers** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** aus, um die lync Server-Serverrollen zu installieren.
    
    3.  Führen Sie **Schritt 3 aus: anfordern, installieren oder Zuweisen von Zertifikaten** zum Zuweisen der Zertifikate.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um Dienste auf dem Server zu starten.
    
    Details zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.

12. Wiederherstellen von Benutzerdaten durch Ausführen der folgenden Schritte:
    
    1.  Kopieren Sie ExportedUserData. zip aus\\ $Backup in ein lokales Verzeichnis.
    
    2.  Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    3.  Geben Sie zum Wiederherstellen der Benutzerdaten in der Befehlszeile Folgendes ein:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Starten Sie lync Services neu, indem Sie Folgendes eingeben:
        
            Start-CsWindowsService

13. Wiederherstellen von Standort Informationsdaten im zentralen Verwaltungsspeicher Geben Sie in der Befehlszeile Folgendes ein:
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    Beispiel:
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. Wenn Sie die Reaktionsgruppe auf diesem Pool oder Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Einstellungen für die Reaktionsgruppe in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

15. Wenn Sie einen Back-End-Server wiederherstellen, der Archivierungs-oder Überwachungsdatenbanken umfasst, stellen Sie die Archivierungs-oder Überwachungsdaten mithilfe eines SQL Server-Verwaltungstools wie SQL Server Management Studio wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

