---
title: Wiederherstellen eines Back-End-Servers der Enterprise Edition
TOCTitle: Wiederherstellen eines Back-End-Servers der Enterprise Edition
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202163(v=OCS.15)
ms:contentKeyID: 52056287
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen eines Back-End-Servers der Enterprise Edition

 

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Verwenden Sie in den folgenden beiden Fällen das in diesem Thema beschriebene Verfahren:

  - Sowohl die primäre als auch die gespiegelte Datenbank eines Back-End-Servers der Enterprise Edition fallen aus.

  - Ein nicht gespiegelter Back-End-Server der Enterprise-Edition fällt aus.

Wenn Sie einen Back-End-Server der Enterprise-Edition gespiegelt haben und nur die gespiegelte oder nur die primäre Datenbank ausfällt, finden Sie Informationen zum Wiederherstellen der primären Datenbank unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Primär](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) und zum Wiederherstellen der Spiegeldatenbank unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegel](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).

Wenn der zentrale Verwaltungsspeicher ausfällt, lesen Sie die Anleitungen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Bei einem Fehler auf dem Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, lesen Sie die Anleitungen unter [Wiederherstellen eines Enterprise Edition-Mitgliedsservers](lync-server-2013-restoring-an-enterprise-edition-member-server.md).


> [!TIP]
> Es wird empfohlen, vor der Wiederherstellung ein Abbild des Systems zu erstellen. Sie können dieses Abbild dann als Rollbackpunkt verwenden, falls Probleme bei der Wiederherstellung auftreten. Es ist sinnvoll, das Abbild nach der Installation des Betriebssystems und von SQL&nbsp;Server zu erstellen und die Zertifikate wiederherzustellen oder erneut zu registrieren.



## So stellen Sie einen Back-End-Server der Enterprise Edition wieder her

1.  Voraussetzung ist ein bereinigter oder neuer Server, der denselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer aufweist. Installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her bzw. registrieren Sie sie erneut.
    

    > [!NOTE]
    > Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.



2.  Melden Sie sich von einem Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist, bei dem Server an, den Sie wiederherstellen.

3.  Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, wobei Sie die gleichen Instanznamen verwenden wie vor dem Ausfall.
    

    > [!NOTE]
    > Je nach vorhandener Bereitstellung umfasst der Back-End-Server möglicherweise mehrere verbundene oder separate Datenbanken. Führen Sie das gleiche Verfahren zum Installieren von SQL&nbsp;Server durch, mit dem Sie auch ursprünglich den Server bereitgestellt haben, einschließlich SQL&nbsp;Server-Berechtigungen und -Anmeldungen.



4.  Führen Sie nach dem Installieren von SQL Server folgende Schritte aus:
    
    1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.
    
    2.  Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.
    
    3.  Wählen Sie die Topologie aus, und klicken Sie auf **Speichern**. Klicken Sie auf **Ja**, um die Auswahl zu bestätigen.
    
    4.  Klicken Sie mit der rechten Maustaste auf den Knoten **Lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
    5.  Folgen Sie den Anweisungen im Assistenten zum **Veröffentlichen der Topologie**. Wählen Sie auf der Seite **Datenbanken erstellen** die Datenbanken aus, die erneut erstellt werden sollen.
        

        > [!NOTE]
        > Auf der Seite <STRONG>Datenbanken erstellen</STRONG> werden nur eigenständige Datenbanken angezeigt.

    
    6.  Wenn Sie einen gespiegelten Back-End-Server wiederherstellen, führen Sie die Schritte des Assistenten weiter aus, bis die Aufforderung **Spiegeldatenbank erstellen** angezeigt wird. Wählen Sie die zu installierende Datenbank aus, und stellen Sie den Prozess fertig.
    
    7.  Folgen Sie den Anweisungen auf den weiteren Seiten des Assistenten, und klicken Sie dann auf **Fertig stellen**.
    

    > [!TIP]
    > Anstatt den Topologie-Generator auszuführen, können Sie die einzelnen Datenbanken mithilfe des <STRONG>Install-CsDatabase</STRONG>-Cmdlets erstellen und die Spiegelung mithilfe des Cmdlets <STRONG>Install-CsMirrorDatabase</STRONG> konfigurieren. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.



5.  Stellen Sie die Benutzerdaten wieder her, indem Sie die folgenden Schritte ausführen:
    
    1.  Kopieren Sie **ExportedUserData.zip** aus **$Backup\\** in ein lokales Verzeichnis.
    
    2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.
    
    3.  Vor dem Wiederherstellen der Benutzerdaten müssen Sie Lync-Dienste beenden. Geben Sie dazu Folgendes ein:
        
            Stop-CsWindowsService
    
    4.  Geben Sie an der Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Beispiel:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Geben Sie zum erneuten Starten der Lync-Dienste Folgendes ein:
        
            Start-CsWindowsService

6.  Wenn Sie Reaktionsgruppe in diesem Pool bereitgestellt haben, stellen Sie die Konfigurationsdaten für Reaktionsgruppe wieder her. Einzelheiten finden Sie unter [Wiederherstellen der Reaktionsgruppeneinstellungen](lync-server-2013-restoring-response-group-settings.md).

7.  Wenn Sie einen Back-End-Server wiederherstellen, auf dem sich Archivierungs- oder Überwachungsdatenbanken befanden, stellen Sie die Archivierungs- oder Überwachungsdaten mithilfe eines SQL Server-Tools wie etwa SQL Server Management Studio wieder her. Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs- oder Archivierungsdaten](lync-server-2013-restoring-monitoring-or-archiving-data.md).

