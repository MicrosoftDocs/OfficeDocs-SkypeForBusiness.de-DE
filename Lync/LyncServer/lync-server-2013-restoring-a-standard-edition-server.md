---
title: Wiederherstellen eines Standard Edition-Servers
TOCTitle: Wiederherstellen eines Standard Edition-Servers
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202190(v=OCS.15)
ms:contentKeyID: 52056458
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen eines Standard Edition-Servers

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Führen Sie die Verfahren in diesem Abschnitt beim Ausfall eines Standard Edition-Servers aus, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird. Beim Ausfall des zentralen Verwaltungsspeichers lesen Sie die Informationen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).


> [!TIP]
> Es wird empfohlen, vor der Wiederherstellung ein Abbild des Systems zu erstellen. Sie können dieses Abbild dann als Rollbackpunkt verwenden, falls Probleme bei der Wiederherstellung auftreten. Es ist sinnvoll, das Abbild nach der Installation des Betriebssystems und von SQL&nbsp;Server zu erstellen und die Zertifikate wiederherzustellen oder erneut zu registrieren.



## So stellen Sie einen Standard Edition-Server wieder her

1.  Voraussetzung ist ein bereinigter oder neuer Server, der denselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der ausgefallene Computer aufweist. Installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her bzw. registrieren Sie sie erneut.
    

    > [!NOTE]
    > Folgen Sie den Verfahren zur Bereitstellung der Server in Ihrer Organisation, um diesen Schritt durchzuführen.



2.  Melden Sie sich bei dem Server an, den Sie wiederherstellen möchten. Verwenden Sie hierzu ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" und der lokalen Administratorgruppe ist.

3.  Stellen Sie den Dateispeicher wieder her, indem Sie den entsprechenden Dateispeicher aus **$Backup** in das Verzeichnis für den Dateispeicher auf dem Server kopieren und den Ordner freigeben.
    

    > [!IMPORTANT]
    > Der Pfad und der Dateiname für den wiederhergestellten Dateispeicher sollten identisch sein mit dem gesicherten Dateispeicher, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.



4.  Führen Sie den Topologie-Generator aus:
    
    1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.
    
    2.  Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie dann auf **Speichern**. Klicken Sie zur Bestätigung der Auswahl auf **Ja**.

5.  Navigieren Sie zum Installationsordner oder Datenträger von Lync Server, und starten Sie dann den Lync Server-Bereitstellungs-Assistenten unter **\\setup\\amd64\\Setup.exe**. Führen Sie die folgenden Schritte mithilfe des Lync Server-Bereitstellungs-Assistenten aus:
    
    1.  Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen Sie **Schritt 2: Lync Server-Komponenten einrichten oder entfernen** aus, um die Lync Server-Serverrollen zu installieren.
    
    3.  Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um Dienste auf dem Server zu starten.
    
    Ausführliche Informationen über die Ausführung des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation zu der Serverrolle, die Sie wiederherstellen.

6.  Stellen Sie Benutzerdaten wieder her, indem Sie folgende Schritte ausführen:
    
    1.  Kopieren Sie **ExportedUserData.zip** aus **$Backup\\** in ein lokales Verzeichnis.
    
    2.  Vor dem Wiederherstellen der Benutzerdaten müssen Sie Lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    3.  Geben Sie zum Wiederherstellen der Benutzerdaten Folgendes an der Befehlszeile ein:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Geben Sie zum erneuten Starten der Lync-Dienste Folgendes ein:
        
            Start-CsWindowsService

7.  Wenn Sie eine Reaktionsgruppe auf diesem Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen der Reaktionsgruppeneinstellungen](lync-server-2013-restoring-response-group-settings.md).

8.  Wenn Sie auf diesem Standard Edition-Server einen beständigen Chat bereitgestellt haben, stellen Sie die Datenbank für beständigen Chat ("mgc.mdf") wieder her.
    
    Wenn Sie die SQL Server-Sicherung verwendet haben, um die Datenbank für beständigen Chat zu sichern, verwenden Sie SQL Server-Wiederherstellungsverfahren zum Wiederherstellen der Datenbank.
    
    Wenn Sie die Datenbank mit dem Export-CsPersistentChatData-Cmdlet gesichert haben, verwenden Sie das Import-CsPersistentChatData-Cmdlet, um die Datenbank wiederherzustellen.

