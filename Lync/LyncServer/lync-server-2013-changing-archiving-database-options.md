---
title: Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013
TOCTitle: Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204814(v=OCS.15)
ms:contentKeyID: 49293674
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn Sie die Archivierung bereitstellen und den SQL Server-Speicher als Archivierungsspeicher für beliebige Benutzer verwenden, können Sie die folgenden Änderungen für die Datenbankspeicherung vornehmen:

  - Verwenden Sie eine andere SQL Server-Datenbank für den Archivierungsspeicher. Hierzu gehören die primäre Archivierungsdatenbank und jede Datenbank, die Sie für die SQL Server-Spiegelung verwenden.

  - Wechseln Sie zur Microsoft Exchange-Integration, um Archivierungsdaten und -dateien auf Exchange 2013-Servern zu speichern. Wenn all Ihre Benutzer auf Exchange 2013-Servern verwaltet werden und Sie Microsoft Exchange-Speicher für alle Benutzer in der Bereitstellung verwenden, sollten Sie die SQL Server-Speicherdatenbanken aus der Topologie entfernen.

Für beide Änderungen müssen Sie den Topologie-Generator ausführen, die Änderungen durchführen und die Topologie dann erneut veröffentlichen. Hierzu können Sie den Topologie-Generator verwenden. Geben Sie keine Informationen unter **SQL Server-Speicher für Archivierung** oder **SQL Server-Speicherspiegelung aktivieren** an, sofern sich in Ihrer Bereitstellung keine Lync-Benutzer befinden, die auf Exchange 2013-Servern verwaltet werden.

## So ändern Sie die Archivierungsdatenbankoption

1.  Melden Sie sich auf einem Computer, auf dem Lync Server 2013 ausgeführt wird oder auf dem die Lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe **Benutzer** ist (oder mit einem Konto mit äquivalenten Benutzerrechten).
    

    > [!NOTE]
    > Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Gruppe <STRONG>Benutzer</STRONG> ist. Zum Veröffentlichen einer Topologie (erforderlich zum Hinzufügen einer Komponente zur Topologie) müssen Sie aber ein Konto verwenden, das Mitglied der Gruppe <STRONG>Domänen-Admins</STRONG> und der Gruppe <STRONG>RTCUniversalServerAdmins</STRONG> ist und über Vollzugriff (Lesen, Schreiben und Ändern) für die Dateifreigabe verfügt, die Sie für den Lync Server 2013-Dateispeicher verwenden, damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) konfigurieren kann. Alternativ dazu können Sie ein Konto mit äquivalenten Rechten verwenden.



2.  Starten Sie den Topologie-Generator.

3.  Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitgestellt haben, und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Datenbankoptionen ändern möchten.

4.  Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.

5.  Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.

6.  Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.

7.  Führen Sie im Dialogfeld **Archivierung** die folgenden Schritte aus:
    
      - Wenn Sie zu einem anderen SQL Server-Speicher wechseln möchten, gehen Sie unter **SQL Server-Speicher für Archivierung** im Dropdown-Listenfeld wie folgt vor:
        
          - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
        
          - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:
            
              - Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.
            
              - Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** die folgenden Schritte aus:
                
                  - Geben Sie im Feld **SQL Server-FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
                
                  - Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
                
                  - Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung**, und geben Sie dann im Feld **Spiegelportnummer** die Portnummer an.
    
      - Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus, und gehen Sie dann wie folgt vor:
        
          - Zum Verwenden eines vorhandenen SQL Server-Speichers zur Spiegelung klicken Sie im Dropdown-Listenfeld **SQL Server-Speicherspiegel für Archivierung** auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.
        
          - Zum Angeben eines neuen SQL Server-Speichers zur Spiegelung klicken Sie auf **Neu**, und führen Sie dann im Dialogfeld **Neuen SQL Server-Speicher definieren** einen der folgenden Schritte aus:
            
            1.  Geben Sie in **SQL-Server-FQDN** den FQDN des Computers mit SQL Server an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.
            
            2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.
            
            3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung**, und geben Sie dann im Feld **Spiegelportnummer** die Portnummer an.
        
          - Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungszeugen hinzufügen oder ändern möchten (eine dritte, separate SQL Server-Instanz, die die Integrität des primären SQL Server-Servers und der Spiegelinstanzen erkennen kann), aktivieren Sie das Kontrollkästchen **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, und führen Sie dann einen der folgenden Schritte aus:
            
            1.  Geben Sie im Feld **SQL Server-FQDN** den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungszeugen erstellen möchten.
            
            2.  Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.
            
            3.  Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungsbeziehung befindet, aktivieren Sie das Kontrollkästchen **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung**, und geben Sie dann im Feld **Spiegelportnummer** die Portnummer an.
    
      - Wenn Sie zur Microsoft Exchange-Integration wechseln möchten, um Archivierungsdaten und -dateien auf Exchange 2013-Servern zu speichern (falls all Ihre Benutzer in der Bereitstellung auf Exchange 2013-Servern verwaltet werden), löschen Sie alle Informationen für Archivierungsdatenbanken.
    

    > [!IMPORTANT]
    > Wenn sich in Ihrer Bereitstellung Lync-Benutzer befinden, die nicht auf Exchange 2013-Servern verwaltet werden, löschen Sie die SQL Server-Speicherinformationen nicht.



8.  Klicken Sie zum Speichern der Konfiguration auf **OK**.
    

    > [!IMPORTANT]
    > Die Änderungen, die Sie in Topologie-Generator vornehmen, werden erst wirksam, wenn Sie die neue Topologie veröffentlichen. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken</A> in der Bereitstellungsdokumentation.


