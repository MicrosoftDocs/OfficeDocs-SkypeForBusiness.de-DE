---
title: Bereitstellen einer immer auf Verfügbarkeitsgruppe auf einem Back-End-Server in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Bereitstellen Sie Bereitstellung (Installation) immer auf Verfügbarkeit in eine Gruppe Ihrer Skype zu Business Server.
ms.openlocfilehash: fcdae233e81f7c2dde3f1bdb4a79f06c95f640d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897157"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Bereitstellen einer immer auf Verfügbarkeitsgruppe auf einem Back-End-Server in Skype für Business Server
 
Bereitstellen Sie Bereitstellung (Installation) ein immer auf Availability Group (AG) in Ihrer Skype zu Business Server.
  
Wie Sie eine AG bereitstellen, hängt davon ab, ob Sie bereitstellen werden sie in einen neuen Pool, einem vorhandenen Pool, das Spiegelung verwendet oder einen vorhandenen Pool aus, der derzeit keine hohen Verfügbarkeit für die Back-End-Datenbank verfügt.
  
> [!NOTE]
> Verwendung einer AG mit einer Persistent Chat Server-Rolle wird nicht unterstützt. 
  
- [Bereitstellen einer immer auf Availability Group auf einen neuen Front-End-pool](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das der datenbankspiegelung verwendet](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das nicht-datenbankspiegelung verwendet wird](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Bereitstellen einer immer auf Availability Group auf einen neuen Front-End-pool
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Aktivieren Sie das Feature Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird. Führen Sie auf jedem Server die folgenden Schritte aus:
    
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
    
3. Erstellen Sie die Windows Server-Failovercluster (WSFC).
    
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
    
5. Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf.  
    
   - Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.
   
6. Topologie-Generator zum Erstellen des Front-End-Pools verwenden, wie im erläutert [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server](../../deploy/install/create-and-publish-new-topology.md). Wenn Sie dies tun, geben Sie die AG als SQL-Speicher für den Pool.
    
7. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** . Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.
    
   - Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.
    
   - Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten. Klicken Sie dann auf **Weiter**.
    
     Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.
    
   - Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.
    
   - Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.
    
   - Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.
    
   - Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.
    
   - Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.
    
     Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.
    
   - Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.
    
   - Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.
      
8. Führen Sie nach dem Pool und die AG bereitgestellt werden, einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind. 
    
   - Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.
    
   - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.
    
     - Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.
    
   - Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.
    
   - Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG. Führen Sie ein Failover zu einem sekundären Replikat aus.
    
   - Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:
    
   ```
   Install-CsDatabase -Update
   ```

   - Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das der datenbankspiegelung verwendet
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, für den Sie zu einer AG Upgrade des zentralen Verwaltungsspeichers für Ihre Organisation gehostet wird, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool. Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“. Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren. 
  
1. Alle Daten aus dem Spiegel zum Prinzipal Knoten, Öffnen von Skype für Business Server-Verwaltungsshell und geben das folgende Cmdlet ein Failover.
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Wiederholen Sie dieses cmdlet für jeden Datenbanktypen im Pool. Mit dem folgenden cmdlet können Sie alle Datenbanktypen finden, die im Pool gespeichert sind.
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Verwenden Sie Topologie-Generator zum Entfernen der datenbankspiegelung aus dem Pool.
    
   - Topologie-Generator zu öffnen. Erweitern Sie in Ihrer Topologie den Eintrag **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
   - Deaktivieren Sie für jeden SQL-Speichertyp des Pools das Kontrollkästchen **SQL-Speicherspiegelung aktivieren**.
    
3. Veröffentlichen der geänderten Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.
    
4. Teilen Sie mit SQL Server Management Studio den Spiegel auf.
    
   - Öffnen SQL Server Management Studio, navigieren Sie zu Ihren Datenbanken, klicken Sie mit der rechten Maustaste auf **Aufgaben** und klicken Sie auf **Spiegel**. Klicken Sie dann auf **Spiegel entfernen** und klicken Sie auf **OK**.
    
   - Wiederholen Sie diesen Schritt für alle Datenbanken im Pool die an ein AG konvertiert werden.
    
5. Richten Sie die Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird. Führen Sie auf jedem Server die folgenden Schritte aus:
    
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
    
7. Erstellen Sie Windows Server-Failovercluster.
    
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
    
9. Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf.  
    
   - Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.
    
10. Erstellen Sie die Verfügbarkeitsgruppe.
    
    - Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.
    
    - Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** . Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.
    
    - Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.
    
    - Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.
    
    - Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten. Klicken Sie dann auf **Weiter**.
    
    Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.
    
    - Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.
    
    - Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.
    
    - Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.
    
      - Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).
    
    - Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.
    
    - Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.
    
    Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.
    
    - Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.
    
    - Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.
    
11. Erstellen eines neuen Speichers AG Listener angeben und den Prinzipal der alten Spiegelung als dem primären Knoten, der die AG angeben.
    
    - Topologie-Generator zu öffnen. Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.
    
    - Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.
    
    - Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.
    
    - Klicken Sie im **SQL Server-FQDN** Geben Sie den FQDN für den primären Knoten des dem AG, und klicken Sie dann auf **OK**. Dies sollte der Prinzipal des alten Spiegels dieses Speichers sein.
    
12. Ordnen Sie den Front-End-Pool mit die neue AG.
    
    - Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, die die AG zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.
    
    - Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** die AG aus. Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AG verschieben möchten.
    
    - Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AG festgelegt sind, klicken Sie auf **OK**.
    
13. Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.
    
14. Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.
    
    - Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.
    
    - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Mit der rechten Maustaste in des SQL-Speichers, der die neue AG, und klicken Sie auf **Eigenschaften bearbeiten**.
    
    - Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.
    
    - Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.
    
    - Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG. Führen Sie ein Failover zu einem sekundären Replikat aus.
    
    - Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:
    
    ```
    Install-CsDatabase -Update
    ```

    - Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das nicht-datenbankspiegelung verwendet wird
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, für den Sie zu einer AG Upgrade des zentralen Verwaltungsspeichers für Ihre Organisation gehostet wird, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool. Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“. Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren. 
  
1. Richten Sie die Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird. Führen Sie auf jedem Server die folgenden Schritte aus:
    
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
    
3. Erstellen Sie die Windows Server-Failovercluster (WSFC).
    
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
    
5. Aktivieren Sie auf jedem Server im Cluster AG in SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf.  
    
   - Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.
    
6. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** . Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.
    
   - Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.
    
   - Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AG einschließen möchten. Klicken Sie dann auf **Weiter**.
    
     Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in AG, wie diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype für Business Server-Datenbanken in der AG einschließen.
    
   - Klicken Sie auf der Registerkarte **Replikate** , auf der Seite **Replikate angeben** . Anschließend klicken Sie auf die Schaltfläche **Hinzufügen Replikate** und Verbinden mit anderen SQL-Instanzen, die Sie als Knoten des dem WSFC verbunden.
    
   - Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.
    
   - Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.
    
   - Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.
    
   - Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.
    
     Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.
    
     - Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.
    
   - Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.
    
7. Erstellen eines neuen Speichers AG Listener angeben.
    
   - Topologie-Generator zu öffnen. Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.
    
   - Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.
    
   - Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.
    
   - Klicken Sie im **SQL Server-FQDN** Geben Sie den FQDN für den primären Knoten des dem AG, und klicken Sie dann auf **OK**.
    
8. Ordnen Sie den Front-End-Pool mit der neuen immer auf Availability Group.
    
   - Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, die die AG zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.
    
   - Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** die AG aus. Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AG verschieben möchten.
    
   - Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AG festgelegt sind, klicken Sie auf **OK**.
    
9. Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.
    
10. Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Benutzernamen aller Replikate in die AG sind.
    
    - Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.
    
    - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Mit der rechten Maustaste in des SQL-Speichers, der die neue AG, und klicken Sie auf **Eigenschaften bearbeiten**.
    
    - Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.
    
    - Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.
    
    - Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG. Führen Sie ein Failover zu einem sekundären Replikat aus.
    
    - Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:
    
      ```
      Install-CsDatabase -Update
      ```

      - Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.
