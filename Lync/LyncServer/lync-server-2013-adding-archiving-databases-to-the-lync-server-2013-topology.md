---
title: Hinzufügen von Archivierungsdatenbanken zur Lync Server 2013-Topologie
TOCTitle: Hinzufügen von Archivierungsdatenbanken zur Lync Server 2013-Topologie
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204654(v=OCS.15)
ms:contentKeyID: 49293096
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen von Archivierungsdatenbanken zur Lync Server 2013-Topologie

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können. In diesem Thema wird erläutert, wie Sie mit dem Topologie-Generator Ihrer vorhandenen Topologie die Archivierungsfunktion hinzufügen.


> [!NOTE]
> Wenn Sie Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und -dateien auf Exchange 2013-Servern für alle Benutzer in der Bereitstellung verwenden möchten, geben Sie nicht <STRONG>SQL Server-Speicher für Archivierung</STRONG> oder <STRONG>SQL ServerSpeicherspiegelung verwenden</STRONG> an.



## So fügen Sie Ihrer Topologie Archivierungsdatenbankunterstützung hinzu

1.  Melden Sie sich auf einem Computer, auf dem Lync Server 2013 ausgeführt oder auf dem die Lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit äquivalenten Benutzerrechten).
    

    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist. Zum Veröffentlichen einer Topologie, die zum Hinzufügen eines Servers zur Topologie erforderlich ist, benötigen Sie jedoch ein Konto, das Mitglied der Gruppe <STRONG>Domänen-Admins</STRONG> sowie der Gruppe <STRONG>RTCUniversalServerAdmins</STRONG> ist und über Vollzugriff (Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den Lync Server 2013-Dateispeicher verwenden, damit der Topologie-Generator die erforderliche DACL (Discretionary Access Control List, besitzerverwaltete Zugriffssteuerungsliste) konfigurieren kann. Alternativ dazu können Sie ein Konto mit äquivalenten Rechten verwenden.



2.  Starten Sie Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des entsprechenden Front-End-Pools.

4.  Klicken Sie im Menü **Aktion** auf **Eigenschaften bearbeiten**.

5.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.

6.  Führen Sie einen Bildlauf nach unten zu **Archivierung** durch.

7.  Aktivieren Sie das Kontrollkästchen **Archivierung**.

8.  Führen Sie unter **SQL Server-Speicher für Aktivierung** eine der folgenden Aktionen aus:
    
      - Klicken Sie zur Verwendung eines vorhandenen SQL Server-Speichers im Dropdownlistenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten. Werden alle Benutzer in Microsoft Exchange Server 2013 oder höher verwaltet, können Sie die Lync-Kommunikation für alle Benutzer Exchange archivieren. In diesem Fall muss der SQL Server-Archivierungsspeicher nicht konfiguriert werden.
    
      - Klicken Sie zum Angeben eines neuen SQL Server-Speichers auf **Neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** folgende Schritte aus:
        
          - Geben Sie in **SQL Server FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
        
          - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden, oder auf **Benannte Instanz**, um eine andere Instanz anzugeben. Geben Sie anschließend die zu verwendende Instanz an.
        
          - Steht die angegebene SQL Server-Instanz in einer Spiegelungsbeziehung, aktivieren Sie das Kontrollkästchen **This SQL instance is in mirroring relation**, und geben Sie dann unter **Spiegelportnummer** die Portnummer an.

9.  Wenn Sie die SQL Server-Speicherspiegelung verwenden möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren**, und führen Sie folgende Schritte aus:
    
      - Klicken Sie zur Verwendung eines vorhandenen SQL Server-Speichers für die Spiegelung im Dropdownlistenfeld **SQL Server-Speicherspiegel für Archivierung** auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
    
      - Klicken Sie zum Angeben eines neuen SQL Server-Speichers für die Spiegelung auf **Neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** eine der folgenden Aktionen aus:
        
        1.  Geben Sie in **SQL Server FQDN** den FQDN des Servers mit SQL Server an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
        
        2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden, oder auf **Benannte Instanz**, um eine andere Instanz anzugeben. Geben Sie anschließend die zu verwendende Instanz an.
        
        3.  Steht die angegebene SQL Server-Instanz in einer Spiegelungsbeziehung, aktivieren Sie das Kontrollkästchen **This SQL instance is in mirroring relation**, und geben Sie dann unter **Spiegelportnummer** die Portnummer an.
    
      - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungszeugen (eine dritte, separate SQL Server-Instanz, die die Integrität des primären SQL Server-Servers und der Spiegelinstanzen ermitteln kann) aufnehmen möchten, aktivieren Sie das Kontrollkästchen **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, und führen Sie eine der folgenden Aktionen aus:
        
        1.  Geben Sie in **SQL Server FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungszeugen erstellen möchten.
        
        2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden, oder auf **Benannte Instanz**, um eine andere Instanz anzugeben. Geben Sie anschließend die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
        
        3.  Steht die angegebene SQL Server-Instanz in einer Spiegelungsbeziehung, aktivieren Sie das Kontrollkästchen **This SQL instance is in mirroring relation**, und geben Sie dann unter **Spiegelportnummer** die Portnummer an.

10. Klicken Sie zum Speichern der Konfiguration auf **OK**.

