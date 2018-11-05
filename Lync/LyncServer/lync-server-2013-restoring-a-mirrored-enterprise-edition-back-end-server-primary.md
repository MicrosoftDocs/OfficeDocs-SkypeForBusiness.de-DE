---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Primär
TOCTitle: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Primär
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945648(v=OCS.15)
ms:contentKeyID: 52056448
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Primär

 

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Wenn Sie in einer gespiegelten Konfiguration einen Enterprise Edition-Back-End-Server verwenden und nur die Primärdatenbank ausfällt, folgen Sie den Verfahren in diesem Abschnitt. Wenn sowohl die Primärdatenbank als auch die Spiegeldatenbank ausfallen, lesen Sie die Informationen unter [Wiederherstellen eines Back-End-Servers der Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) aus. Wenn nur die Spiegelung ausfällt, lesen Sie die Informationen unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegel](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Wenn die Datenbank ausfällt, die den zentralen Verwaltungsspeicher hostet, lesen Sie die Informationen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Wenn ein Enterprise Edition-Mitgliedsserver ausfällt, bei dem es sich nicht um den Back-End-Server handelt, lesen Sie die Informationen unter [Wiederherstellen eines Enterprise Edition-Mitgliedsservers](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Es wird empfohlen, vor der Wiederherstellung ein Abbild des Systems zu erstellen. Sie können dieses Abbild dann als Rollbackpunkt verwenden, falls Probleme bei der Wiederherstellung auftreten. Es ist sinnvoll, das Abbild nach der Installation des Betriebssystems und von SQL Server zu erstellen und die Zertifikate wiederherzustellen oder erneut zu registrieren.

In den Beispielen in diesem Thema hat die Primärdatenbank den vollqualifizierten Domänennamen (FQDN) "BE1.contoso.com" und die Spiegeldatenbank den FQDN " BE2.contoso.com".

## So stellen Sie die Primärdatenbank für den Enterprise Edition-Back-End-Server wieder her

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist, an einem Front-End-Server an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Erzwingen Sie für alle konfigurierten Datenbanken ein Failover auf die Spiegeldatenbank. Geben Sie für jeden Datenbanktyp, den Sie auf diesem Server konfiguriert haben, das folgende Cmdlet ein:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Beispiel:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    

    > [!WARNING]
    > Wenn Sie Ihre Back-End-Datenbank so konfiguriert haben, dass eine synchronisierte Spiegelung mit einem Zeugen erfolgt, wird das Failover automatisch ausgeführt.



4.  Führen Sie nach Abschluss des Failovers die folgenden Schritte aus:
    
      - Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.
    
      - Deaktivieren Sie die Spiegelung auf dem Back-End-Server: Klicken Sie mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools**, und wählen Sie **Eigenschaften bearbeiten** aus. Deaktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen** das Kontrollkästchen **SQL Server-Speicherspiegelung aktivieren**. Führen Sie diesen Schritt bei Bedarf auch für die Archivierungs- und Überwachungsdatenbank aus. Klicken Sie anschließend auf **OK**.
    
      - Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Konten, klicken Sie auf **Topologie** und dann auf **Veröffentlichen**.
    
      - Wählen Sie das noch funktionierende Back-End (BE2.contoso.com) als neuen SQL Server-Speicher aus. Klicken Sie mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools**, und wählen Sie **Eigenschaften bearbeiten** aus. Geben Sie auf der Registerkarte **Allgemein** unter **Zuordnungen** den FQDN des funktionierenden Back-Ends im Feld **SQL Server-Speicher** ein (in unserem Beispiel "BE2.contoso.com").
    
      - Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Konten, klicken Sie auf **Topologie** und dann auf **Veröffentlichen**.
    
      - Starten Sie die Dienste neu, damit jeder Server die neue Topologie lesen kann. Führen Sie von einer Lync Server-Verwaltungsshell die folgenden Cmdlets auf jedem Front-End-Server aus, der zu diesem Pool gehört:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Deinstallieren Sie die Spiegelung. Führen Sie das folgende Cmdlet an einer Lync Server-Verwaltungsshell aus:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Beispiel:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Führen Sie diesen Schritt für alle Datenbankentypen auf diesem Server aus.

6.  Erstellen Sie einen bereinigten oder neuen Server, der denselben FQDN (in diesem Beispiel "DB1.contoso.com") wie der ausgefallene Computer hat, und installieren Sie das Betriebssystem. Stellen Sie dann die Zertifikate wieder her, oder registrieren Sie die Zertifikate erneut. Dieser Server dient als neuer Spiegel.

7.  Melden Sie sich am neuen Server mit einem Benutzerkonto an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist.

8.  Installieren Sie SQL 2012 oder SQL Server 2008 R2, wobei Sie die gleichen Instanznamen verwenden wie vor dem Ausfall.

9.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist, an einem Front-End-Server an.

10. Verwenden Sie den Topologie-Generator, um die Spiegeldatenbank zu installieren. Führen Sie die folgenden Schritte durch:
    
      - Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.
    
      - Aktivieren Sie die Spiegelung auf dem Back-End-Server. Klicken Sie hierzu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools**, und wählen Sie **Eigenschaften bearbeiten** aus. Aktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen** das Kontrollkästchen **SQL Server-Speicherspiegelung aktivieren**. Führen Sie diesen Schritt bei Bedarf auch für die Archivierungs- und Überwachungsdatenbank aus.
        
        Geben Sie dann im Feld **SQL Server-Speicher für Spiegelung** den FQDN des neuen Servers ein (in diesem Beispiel "BE1.contoso.com"). Klicken Sie anschließend auf **OK**.
    
      - Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Knoten, klicken Sie auf **Topologie** und dann auf **Datenbank installieren**.
    
      - Folgen Sie dem Assistenten zum **Installieren der Datenbank**. Wählen Sie auf der Seite **Datenbanken erstellen** die Datenbanken aus, die Sie neu erstellen möchten.
    
      - Folgen Sie den Anweisungen im Assistenten, bis die Aufforderung **Spiegeldatenbank erstellen** angezeigt wird. Wählen Sie die zu installierende Datenbank aus, und stellen Sie diesen Prozess fertig. Wählen Sie die zu installierende Datenbank aus, und stellen Sie diesen Prozess fertig.

