---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegel
TOCTitle: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegel
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945626(v=OCS.15)
ms:contentKeyID: 52056330
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegel

 

_**Letztes Änderungsdatum des Themas:** 2013-02-19_

Wenn Sie über einen Back-End-Server der Enterprise Edition in einer Spiegelungskonfiguration verfügen und nur die Spiegelung ausfällt, führen Sie die Verfahren in diesem Abschnitt aus. Wenn sowohl die primäre Datenbank als auch die Spiegeldatenbank ausfallen, lesen Sie die Anleitungen unter [Wiederherstellen eines Back-End-Servers der Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Wenn nur die primäre Datenbank ausfällt, lesen Sie die Anleitungen unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Primär](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Wenn die Datenbank ausfällt, die den zentralen Verwaltungsspeicher hostet, lesen Sie die Anleitungen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Bei einem Fehler auf dem Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, lesen Sie die Anleitungen unter [Wiederherstellen eines Enterprise Edition-Mitgliedsservers](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Es wird empfohlen, vor der Wiederherstellung ein Abbild des Systems zu erstellen. Sie können dieses Abbild dann als Rollbackpunkt verwenden, falls Probleme bei der Wiederherstellung auftreten. Es ist sinnvoll, das Abbild nach der Installation des Betriebssystems und von SQL Server zu erstellen und die Zertifikate wiederherzustellen oder erneut zu registrieren.

## So stellen Sie eine gespiegelte Datenbank eines Back-End-Servers der Enterprise Edition wieder her

1.  Melden Sie sich mit einem Benutzerkonto an einem Front-End-Server an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Deinstallieren Sie die Spiegelung. Geben Sie zuerst folgendes Cmdlet ein:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Beispiel:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Führen Sie diesen Schritt für alle Datenbankentypen auf diesem Server aus.

4.  Erstellen Sie einen bereinigten oder neuen Server, der denselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) (DB1.contoso.com) wie der fehlerhafte Computer aufweist. Installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her bzw. registrieren Sie sie erneut. Dieser Server fungiert als neue Spiegelung.

5.  Melden Sie sich am neuen Server mit einem Benutzerkonto an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist.

6.  Installieren Sie SQL 2012 oder SQL Server 2008 R2, wobei Sie die gleichen Instanznamen verwenden wie vor dem Ausfall.

7.  Melden Sie sich mit einem Benutzerkonto an einem Front-End-Server an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist.

8.  Verwenden Sie den Topologie-Generator zum Installieren der Spiegeldatenbank. Führen Sie folgende Schritte aus:
    
      - Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.
    
      - Klicken Sie mit der rechten Maustaste auf den Lync Server 2013-Konten, klicken Sie auf **Topologie** und dann auf **Datenbank installieren**.
    
      - Folgen Sie dem Assistenten zum **Installieren der Datenbank**. Wählen Sie auf der Seite **Datenbanken erstellen** die Datenbanken aus, die Sie neu erstellen möchten.
    
      - Folgen Sie den Anweisungen des Assistenten, bis die Aufforderung **Spiegeldatenbank erstellen** angezeigt wird. Wählen Sie die zu installierende Datenbank aus, und stellen Sie dieses Prozess fertig.
        

        > [!TIP]
        > Anstatt den Topologie-Generator auszuführen, können Sie die Spiegelung mithilfe des <STRONG>Install-CsMirrorDatabase</STRONG>-Cmdlets konfigurieren. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.


