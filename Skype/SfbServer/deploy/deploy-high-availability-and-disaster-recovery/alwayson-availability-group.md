---
title: Bereitstelleneiner Gruppe "immer auf Verfügbarkeit" auf einem Back-End-Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Bereitstellen (installieren) einer immer auf verfügbarkeitsgruppe in Ihrer Skype for Business Server-Bereitstellung.
ms.openlocfilehash: d69e370716af2b23c57ad463ea7f4651ea0ea89a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798272"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Bereitstelleneiner Gruppe "immer auf Verfügbarkeit" auf einem Back-End-Server in Skype for Business Server
 
Stellen Sie in Ihrer Skype for Business Server-Bereitstellung eine immer verfügbare verfügbarkeitsgruppe (AG) bereit.
  
Wie Sie eine AG bereitstellen, hängt davon ab, ob Sie Sie in einem neuen Pool, in einem vorhandenen Pool, in dem Spiegelung verwendet wird, oder in einem vorhandenen Pool bereitstellen, für den derzeit keine höhere Verfügbarkeit für die Back-End-Datenbank zur Verfügung steht.
  
> [!NOTE]
> Die Verwendung einer AG mit einer beständigen Chat Server Rolle wird nicht unterstützt. 
  
- [Bereitstelleneiner immer auf verfügbarkeitsgruppe in einem neuen Front-End-Pool](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Bereitstelleneiner immer verfügbaren verfügbarkeitsgruppe in einem vorhandenen Pool, in dem die Datenbankspiegelung verwendet wird](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Bereitstelleneiner immer auf verfügbarkeitsgruppe in einem vorhandenen Pool, in dem keine Datenbankspiegelung verwendet wird](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Bereitstelleneiner immer auf verfügbarkeitsgruppe in einem neuen Front-End-Pool
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Aktivieren Sie das Feature Failover-Clustering auf allen Datenbankservern, die Teil der AG sind. Führen Sie auf jedem Server die folgenden Schritte aus:
    
   - Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.
    
   - Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.
    
   - Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.
    
   - Klicken Sie auf **Installieren**.
    
2. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.
    
   - Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.
    
   - Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.
    
   - Überprüfen Sie im Kästchen **Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.
    
     Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.
    
3. Erstellen Sie den Windows Server-Failovercluster (WSFC).
    
   - Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.
    
   - Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.
    
   - Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.
    
   - Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.
    
   - Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.
    
4. Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.
    
   - Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.
    
   - Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.
    
   - Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
5. Aktivieren Sie auf jedem Server im Cluster das Feature AG im SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf.  
    
   - Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.
   
6. Verwenden Sie den Topologie-Generator zum Erstellen des Front-End-Pools, wie unter [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md)erläutert wird. Wenn Sie dies tun, geben Sie die AG als SQL Store für den Pool an.
    
7. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **immer für die höchste Verfügbarkeit** . Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.
    
   - Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.
    
   - Wählen Sie auf der Seite Datenbanken auswählen die Datenbanken aus, die Sie in die AlwaysOn-verfügbarkeitsgruppe einbeziehen möchten. Klicken Sie dann auf **Weiter**.
    
     Schließen Sie die Datenbank **Report Server**, **ReportServerTempDB**oder persistent Chat nicht in die AlwaysOn-verfügbarkeitsgruppe ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server-Datenbanken in die AlwaysOn-verfügbarkeitsgruppe einbeziehen.
    
   - Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.
    
   - Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.
    
   - Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.
    
   - Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.
    
   - Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.
    
     Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.
    
   - Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.
    
   - Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.
      
8. Nachdem der Pool und die AG bereitgestellt wurden, führen Sie einige abschließende Schritte aus, um sicherzustellen, dass sich die SQL-Anmeldungen auf jedem Replikat in der AlwaysOn-verfügbarkeitsgruppe befinden. 
    
   - Öffnen Sie den Topologie-Generator, wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie auf **OK**.
    
   - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Klicken Sie mit der rechten Maustaste auf den SQL Store der neuen AlwaysOn-verfügbarkeitsgruppe, und klicken Sie auf **Eigenschaften bearbeiten**.
    
     - Ändern Sie unten auf der Seite im Feld **SQL Server-FQDN** den Wert in den FQDN des Listener der AG.
    
   - Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.
    
   - Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AG. Führen Sie ein Failover zu einem sekundären Replikat aus.
    
   - Öffnen Sie die Skype for Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL-Anmeldungen für dieses Replikat zu erstellen:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Wiederholen Sie die beiden vorherigen Schritte (Failover der Gruppe zu einem sekundären Replikat, `Install-CsDatabase -Update`dann verwenden) für jedes Replikat in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Bereitstelleneiner immer verfügbaren verfügbarkeitsgruppe in einem vorhandenen Pool, in dem die Datenbankspiegelung verwendet wird
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, auf den Sie ein Upgrade auf eine AG durchführen, den zentralen Verwaltungsspeicher für Ihre Organisation hostet, müssen Sie zuerst den CMS in einen anderen Pool verschieben, bevor Sie diesen Pool aktualisieren. Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“. Wenn Sie nicht über einen anderen Pool in Ihrer Organisation verfügen, können Sie einen Standard Edition-Server vorübergehend bereitstellen und den CMS auf diesen Server verschieben, bevor Sie Ihr Pool auf die AG aktualisieren. 
  
1. Führen Sie einen Failover für alle Daten von der Spiegelung zum Prinzipal Knoten durch, indem Sie die Skype for Business Server-Verwaltungsshell öffnen und das folgende Cmdlet eingeben.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Wiederholen Sie dieses cmdlet für jeden Datenbanktypen im Pool. Mit dem folgenden cmdlet können Sie alle Datenbanktypen finden, die im Pool gespeichert sind.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Verwenden Sie den Topologie-Generator, um die Datenbankspiegelung aus dem Pool zu entfernen.
    
   - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie den Eintrag **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
   - Deaktivieren Sie für jeden SQL-Speichertyp des Pools das Kontrollkästchen **SQL-Speicherspiegelung aktivieren**.
    
3. Veröffentlichen der geänderten Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.
    
4. Teilen Sie mit SQL Server Management Studio den Spiegel auf.
    
   - Öffnen SQL Server Management Studio, navigieren Sie zu Ihren Datenbanken, klicken Sie mit der rechten Maustaste auf **Aufgaben** und klicken Sie auf **Spiegel**. Klicken Sie dann auf **Spiegel entfernen** und klicken Sie auf **OK**.
    
   - Wiederholen Sie diesen Vorgang für alle Datenbanken im Pool, die in eine AG konvertiert werden.
    
5. Richten Sie die Failover-Clusterfunktion auf allen Datenbankservern ein, die Teil der AG sind. Führen Sie auf jedem Server die folgenden Schritte aus:
    
   - Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.
    
   - Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.
    
   - Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.
    
   - Klicken Sie auf **Installieren**.
    
6. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.
    
   - Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.
    
   - Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.
    
   - Überprüfen Sie im Kästchen **Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.
    
     Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.
    
7. Erstellen Sie den Windows Server-Failovercluster.
    
   - Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.
    
   - Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.
    
   - Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.
    
   - Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.
    
   - Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.
    
8. Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.
    
   - Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.
    
   - Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.
    
   - Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
9. Aktivieren Sie auf jedem Server im Cluster das Feature AG im SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf.  
    
   - Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.
    
10. Erstellen Sie die Verfügbarkeitsgruppe.
    
    - Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.
    
    - Erweitern Sie im Objekt-Explorer den Ordner **immer für die höchste Verfügbarkeit** . Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.
    
    - Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.
    
    - Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.
    
    - Wählen Sie auf der Seite Datenbanken auswählen die Datenbanken aus, die Sie in die AlwaysOn-verfügbarkeitsgruppe einbeziehen möchten. Klicken Sie dann auf **Weiter**.
    
    Schließen Sie die Datenbank **Report Server**, **ReportServerTempDB**oder persistent Chat nicht in die AlwaysOn-verfügbarkeitsgruppe ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server-Datenbanken in die AlwaysOn-verfügbarkeitsgruppe einbeziehen.
    
    - Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.
    
    - Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.
    
    - Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.
    
      - Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).
    
    - Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.
    
    - Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.
    
    Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.
    
    - Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.
    
    - Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.
    
11. Erstellen Sie einen neuen Store, der den AG-Listener angibt, und geben Sie den Prinzipal des alten Spiegels als primären Knoten der AG an.
    
    - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.
    
    - Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.
    
    - Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.
    
    - Geben Sie im Feld **SQL Server-FQDN** den FQDN des primären Knotens der AG ein, und klicken Sie dann auf **OK**. Dies sollte der Prinzipal des alten Spiegels dieses Speichers sein.
    
12. Ordnen Sie die neue AG dem Front-End-Pool zu.
    
    - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, der der AG zugeordnet werden soll, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
    - Wählen Sie unter **Zuordnungen**im Feld **SQL Server Store** die Option AG aus. Wählen Sie dieselbe Gruppe für alle anderen Datenbanken im Pool aus, die Sie in die AG verschieben möchten.
    
    - Wenn Sie sicher sind, dass alle benötigten Datenbanken auf die AG festgesetzt sind, klicken Sie auf **OK**.
    
13. Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.
    
14. Führen Sie einige abschließende Schritte aus, um sicherzustellen, dass sich die SQL-Anmeldungen auf den einzelnen Replikaten in der AlwaysOn-verfügbarkeitsgruppe befinden.
    
    - Öffnen Sie den Topologie-Generator, wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie auf **OK**.
    
    - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Klicken Sie mit der rechten Maustaste auf den SQL Store der neuen AG, und klicken Sie auf **Eigenschaften bearbeiten**.
    
    - Ändern Sie unten auf der Seite im Feld **SQL Server-FQDN** den Wert in den FQDN des Listener der AG.
    
    - Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.
    
    - Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AG. Führen Sie ein Failover zu einem sekundären Replikat aus.
    
    - Öffnen Sie die Skype for Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL-Anmeldungen für dieses Replikat zu erstellen:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Wiederholen Sie die beiden vorherigen Schritte (Failover der Gruppe zu einem sekundären Replikat, `Install-CsDatabase -Update`dann verwenden) für jedes Replikat in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Bereitstelleneiner immer auf verfügbarkeitsgruppe in einem vorhandenen Pool, in dem keine Datenbankspiegelung verwendet wird
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, auf den Sie ein Upgrade auf eine AG durchführen, den zentralen Verwaltungsspeicher für Ihre Organisation hostet, müssen Sie zuerst den CMS in einen anderen Pool verschieben, bevor Sie diesen Pool aktualisieren. Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“. Wenn Sie nicht über einen anderen Pool in Ihrer Organisation verfügen, können Sie einen Standard Edition-Server vorübergehend bereitstellen und den CMS auf diesen Server verschieben, bevor Sie Ihr Pool auf die AG aktualisieren. 
  
1. Richten Sie die Failover-Clusterfunktion auf allen Datenbankservern ein, die Teil der AG sind. Führen Sie auf jedem Server die folgenden Schritte aus:
    
   - Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.
    
   - Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.
    
   - Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.
    
   - Klicken Sie auf **Installieren**.
    
2. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.
    
   - Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.
    
   - Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.
    
   - Überprüfen Sie im Kästchen **Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.
    
     Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.
    
3. Erstellen Sie den Windows Server-Failovercluster (WSFC).
    
   - Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.
    
   - Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.
    
   - Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.
    
   - Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.
    
   - Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.
    
4. Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.
    
   - Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.
    
   - Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.
    
   - Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
5. Aktivieren Sie im SQL Server-Konfigurations-Manager auf jedem Server im Cluster die Option AG.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf.  
    
   - Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.
    
6. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **immer für die höchste Verfügbarkeit** . Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.
    
   - Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.
    
   - Wählen Sie auf der Seite Datenbanken auswählen die Datenbanken aus, die Sie in die AG einbeziehen möchten. Klicken Sie dann auf **Weiter**.
    
     Schließen Sie die Datenbank **Report Server**, **ReportServerTempDB**oder persistent Chat nicht in die AG ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server-Datenbanken in die AG aufnehmen.
    
   - Klicken Sie auf der Seite **Replikate angeben** auf die Registerkarte **Replikate** . Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** , und stellen Sie eine Verbindung mit den anderen SQL-Instanzen her, die Sie als Knoten des WSFC.
    
   - Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.
    
   - Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.
    
   - Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.
    
   - Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.
    
     Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.
    
     - Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.
    
   - Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.
    
7. Erstellen Sie einen neuen Store, der den AG-Listener angibt.
    
   - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.
    
   - Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.
    
   - Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.
    
   - Geben Sie im Feld **SQL Server-FQDN** den FQDN des primären Knotens der AG ein, und klicken Sie dann auf **OK**.
    
8. Ordnen Sie die neue Gruppe immer auf Verfügbarkeit dem Front-End-Pool zu.
    
   - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, der der AG zugeordnet werden soll, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
   - Wählen Sie unter **Zuordnungen**im Feld **SQL Server Store** die Option AG aus. Wählen Sie dieselbe Gruppe für alle anderen Datenbanken im Pool aus, die Sie in die AG verschieben möchten.
    
   - Wenn Sie sicher sind, dass alle benötigten Datenbanken auf die AG festgesetzt sind, klicken Sie auf **OK**.
    
9. Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.
    
10. Führen Sie einige abschließende Schritte aus, um sicherzustellen, dass sich die SQL-Anmeldungen auf jeder der Replikate der AG befinden.
    
    - Öffnen Sie den Topologie-Generator, wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie auf **OK**.
    
    - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Klicken Sie mit der rechten Maustaste auf den SQL Store der neuen AG, und klicken Sie auf **Eigenschaften bearbeiten**.
    
    - Ändern Sie unten auf der Seite im Feld **SQL Server-FQDN** den Wert in den FQDN des Listener der AG.
    
    - Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.
    
    - Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AG. Führen Sie ein Failover zu einem sekundären Replikat aus.
    
    - Öffnen Sie die Skype for Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL-Anmeldungen für dieses Replikat zu erstellen:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Wiederholen Sie die beiden vorherigen Schritte (Failover der Gruppe zu einem sekundären Replikat, `Install-CsDatabase -Update`dann verwenden) für jedes Replikat in der Gruppe.
