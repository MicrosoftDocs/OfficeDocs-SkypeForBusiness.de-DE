---
title: Bereitstellen einer Always On-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Bereitstellen (Installieren) einer Always On-Verfügbarkeitsgruppe in Ihrer Skype for Business Server-Bereitstellung.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830655"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Bereitstellen einer Always On-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server
 
Bereitstellen (Installieren) einer Always On Availability Group (AG) in Ihrer Skype for Business Server-Bereitstellung.
  
Wie Sie eine AG bereitstellen, hängt davon ab, ob Sie sie in einem neuen Pool, in einem vorhandenen Pool mit Spiegelung oder in einem vorhandenen Pool bereitstellen, der derzeit keine hohe Verfügbarkeit für die Back-End-Datenbank hat.
  
> [!NOTE]
> Die Verwendung einer AG mit einer Serverrolle für beständigen Chat wird nicht unterstützt. 
  
- [Bereitstellen einer Always On-Verfügbarkeitsgruppe in einem neuen Front-End-Pool](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Bereitstellen einer Always On-Verfügbarkeitsgruppe in einem vorhandenen Pool, der Datenbankspiegelung verwendet](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Bereitstellen einer Always On-Verfügbarkeitsgruppe in einem vorhandenen Pool ohne Datenbankspiegelung](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Bereitstellen einer Always On-Verfügbarkeitsgruppe in einem neuen Front-End-Pool
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Aktivieren Sie das Failoverclusteringfeature auf allen Datenbankservern, die Teil der AG sein werden. Gehen Sie auf jedem Server wie folgt vor:
    
   - Öffnen Sie den Server-Manager, und klicken **Sie auf "Rollen und Features hinzufügen".**
    
   - Klicken **Sie auf "Weiter",** bis Sie das Feld **"Features auswählen"** erreichen. Aktivieren Sie hier das **Kontrollkästchen Failoverclustering.**
    
   - Klicken Sie **im Feld Features hinzufügen, die für Failoverclustering erforderlich sind?** auf **"Features hinzufügen".**
    
   - Klicken Sie auf **Installieren**.
    
2. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server Manager auf das Menü **"Extras",** und klicken Sie dann auf **"Failovercluster-Manager".**
    
   - Klicken **Sie auf** der rechten Seite des Bildschirms unter "Aktionen" auf **"Konfiguration überprüfen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann **auf "Alle Tests ausführen".**
    
   - Überprüfen Sie **im Feld "Zusammenfassung"** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **"Fertig** stellen", um die Überprüfung durchzuführen.
    
     Der Assistent wird wahrscheinlich mehrere Warnungen melden, insbesondere wenn Sie keinen freigegebenen Speicher verwenden. Sie müssen keinen freigegebenen Speicher verwenden. Wenn jedoch Fehlermeldungen **angezeigt** werden, müssen Sie diese Probleme beheben, bevor Sie fortfahren.
    
3. Erstellen Sie den Windows Server-Failovercluster (WSFC).
    
   - Klicken Sie **im Assistenten für die Failoverclusterverwaltung** mit der rechten Maustaste auf **Failoverclusterverwaltung,** und klicken Sie dann **auf "Cluster erstellen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Fügen Sie den Clusternamen und die IP-Adresse hinzu. Wenn die Einstellungen überprüft werden, klicken Sie auf **"Weiter".**
    
   - Klicken Sie auf der Seite Bestätigung auf **Weiter**.
    
   - Klicken Sie nach dem Erstellen des Clusters auf **"Fertig stellen".**
    
4. Es wird empfohlen, die Clusterquorumeinstellungen für die Verwendung eines Dateifreigabezeugen zu konfigurieren. Gehen Sie dazu wie im folgenden Schritt vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, **klicken** Sie auf "Weitere Aktionen", und klicken Sie auf **"Clusterquorumeinstellungen konfigurieren".**
    
   - Klicken Sie **auf der Seite "Quorumkonfigurationsoption** auswählen" **auf "Quorumzeugen auswählen".**
    
   - Klicken Sie **auf der Seite "Quorumzeugen** auswählen" auf **"Dateifreigabenzeugen konfigurieren".**
    
   - Geben Sie auf der Seite **"Dateifreigabenzeugen** konfigurieren" den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **"Weiter".**
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
5. Aktivieren Sie auf jedem Server im Cluster das Feature AG in SQL Server Configuration Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur auf der linken Seite des Bildschirms auf **SQL Server Dienste,** und doppelklicken Sie dann auf SQL Server Dienst. 
    
   - Wählen Sie **im Feld "Eigenschaften"** die Registerkarte **"AlwaysOn High Availability"** aus. Aktivieren Sie **das Kontrollkästchen "AlwaysOn-Verfügbarkeitsgruppen** aktivieren". Starten Sie den SQL Server, wenn Sie dazu aufgefordert werden.
   
6. Verwenden Sie den Topologie-Generator, um den Front-End-Pool zu erstellen, wie unter Erstellen und Veröffentlichen einer neuen [Topologie in Skype for Business Server erläutert.](../../deploy/install/create-and-publish-new-topology.md) Geben Sie dann die AG als SQL für den Pool an.
    
7. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server herstellen.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **"Always On High Availability".** Klicken Sie mit der rechten Maustaste auf den Ordner **"Verfügbarkeitsgruppen",** und klicken Sie auf **"Neuer Verfügbarkeitsgruppen-Assistent".**
    
   - Wenn die **Seite "Einführung"** angezeigt wird, klicken Sie auf **"Weiter".**
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppenname** angeben den Namen der Verfügbarkeitsgruppe ein, und klicken Sie auf **"Weiter".**
    
   - Wählen Sie auf der Seite Datenbanken auswählen die Datenbanken aus, die Sie in die Verfügbarkeitsgruppe "AlwaysOn" hinzufügen möchten. Then click **Next**.
    
     Schließen Sie die **Datenbanken ReportServer,** **ReportServerTempDB** oder Persistent Chat nicht in die Verfügbarkeitsgruppe "AlwaysOn" ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server-Datenbanken in die Verfügbarkeitsgruppe "AlwaysOn" einplanen.
    
   - Klicken Sie **auf der Seite Replikate** angeben auf die Registerkarte **Replikate.** Klicken Sie  dann auf die Schaltfläche Replikate hinzufügen, und stellen Sie eine Verbindung mit den anderen SQL, die Sie als Knoten des Windows Server-Failoverclusters verbunden haben.
    
   - Wählen Sie für jede Instanz die Optionen **"Automatisches Failover" und** **"Synchroner Commit"** aus. Wählen Sie nicht die Option **"Lesbare sekundäre Option"** aus.
    
   - Klicken Sie **auf die Registerkarte "Endpunkte",** und stellen Sie sicher, dass **die Portnummer** auf 5022 festgelegt ist.
    
   - Klicken Sie auf **die Registerkarte "Listener",** und wählen Sie die Option **"Verfügbarkeitsgruppenlistener erstellen"** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf 1433 fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken **Sie auf**"Hinzufügen" und dann im Feld **"IPv4-Adresse",** geben Sie Ihre bevorzugte virtuelle IP-Adresse ein, und klicken Sie dann auf **"OK".**
    
   - Wählen  Sie auf der Seite "Anfängliche Datensynchronisierung auswählen" die Option "Vollständig" aus, und geben Sie einen Ordner an, auf den die Replikate zugreifen können und für den das von beiden Replikaten verwendete SQL Server-Dienstkonto schreibberechtigungen besitzt. Then click **Next**.
    
     Diese Dateifreigabe wird vorübergehend verwendet, wenn Sie die Datenbanken initialisieren. Bei großen Datenbanken wird empfohlen, diese manuell zu initialisieren, falls die Netzwerkbandbreite die Größe der Datenbanksicherungen nicht aufnehmen kann.
    
   - Überprüfen Sie auf der Seite "Überprüfung", ob alle Überprüfungen erfolgreich waren, und klicken Sie dann auf **"Weiter".**
    
   - Überprüfen Sie **auf der Seite "Zusammenfassung"** alle Einstellungen, und klicken Sie auf "Fertig stellen".
      
8. Führen Sie nach der Bereitstellung des Pools und der AG einige abschließende Schritte aus, um sicherzustellen, dass sich die SQL-Anmeldeinformationen auf jedem Replikat in der Verfügbarkeitsgruppe "AlwaysOn" befinden. 
    
   - Öffnen Sie den Topologie-Generator, wählen **Sie "Topologie aus vorhandener Bereitstellung herunterladen"** aus, und klicken Sie auf **"OK".**
    
   - Erweitern Sie Skype for Business Server, Erweitern Sie Ihre Topologie und SQL Server **Stores**. Klicken Sie mit der rechten maustaste SQL speicher der neuen AlwaysOn-Verfügbarkeitsgruppe, und klicken Sie dann **auf "Eigenschaften bearbeiten".**
    
     - Ändern Sie unten auf der Seite im Feld **SQL Server FQDN** den Wert in den FQDN des Listeners der AG.
    
   - Veröffentlichen Sie die Topologie. Klicken Sie **im Menü "Aktion"** **auf "Topologie"** und dann **auf "Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".** Warten Sie dann einige Minuten, bis die neue Topologie repliziert wurde.
    
   - Öffnen SQL Server Management Studio, und navigieren Sie zur AG. Führen Sie ein Failover auf ein sekundäres Replikat durch.
    
   - Öffnen Sie die Skype for Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL auf diesem Replikat zu erstellen:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Wiederholen Sie die beiden vorherigen Schritte (failovern Sie die Gruppe auf ein sekundäres Replikat, und verwenden Sie dann ) für jedes Replikat  `Install-CsDatabase -Update` in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Bereitstellen einer Always On-Verfügbarkeitsgruppe in einem vorhandenen Pool, der Datenbankspiegelung verwendet
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, den Sie auf eine AG aktualisieren, den zentralen Verwaltungsspeicher für Ihre Organisation hostet, müssen Sie den CMS zunächst in einen anderen Pool verschieben, bevor Sie diesen Pool aktualisieren. Verwenden Sie Move-CsManagementServer cmdlet, um den Pool zu verschieben. Wenn In Ihrer Organisation kein weiterer Pool vorhanden ist, können Sie einen Standard Edition-Server vorübergehend bereitstellen und den CMS auf diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren. 
  
1. Führen Sie ein Failover aller Daten vom Spiegel zum Prinzipalknoten durch, indem Sie die Skype for Business Server-Verwaltungsshell öffnen und das folgende Cmdlet eingeben.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Wiederholen Sie dieses Cmdlet für jeden Datenbanktyp im Pool. Mit dem folgenden Cmdlet können Sie alle in diesem Pool gespeicherten Datenbanktypen suchen.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Verwenden Sie den Topologie-Generator, um die Datenbankspiegelung aus dem Pool zu entfernen.
    
   - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie **die Enterprise Edition-Front-End-Pools,** klicken Sie mit der rechten Maustaste auf den Namen des Pools, und klicken Sie dann **auf "Eigenschaften bearbeiten".**
    
   - Aktivieren Sie für SQL im Pool das Kontrollkästchen **SQL Speicherspiegelung** aktivieren.
    
3. Veröffentlichen Sie die geänderte Topologie. Klicken Sie **im Menü "Aktion"** **auf "Topologie"** und dann **auf "Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
4. Verwenden SQL Server Management Studio, um den Spiegel zu unterbrechen.
    
   - Öffnen SQL Server Management Studio, navigieren Sie zu Ihren Datenbanken, klicken Sie mit der rechten Maustaste auf **"Aufgaben",** und klicken Sie auf **"Spiegel".** Klicken Sie dann **auf "Spiegelung entfernen"** und dann auf **"OK".**
    
   - Wiederholen Sie diesen Vorgang für alle Datenbanken im Pool, die in eine AG konvertiert werden.
    
5. Richten Sie das Failoverclusteringfeature auf allen Datenbankservern ein, die Teil der AG sein werden. Gehen Sie auf jedem Server wie folgt vor:
    
   - Öffnen Sie den Server-Manager, und klicken **Sie auf "Rollen und Features hinzufügen".**
    
   - Klicken **Sie auf "Weiter",** bis Sie das Feld **"Features auswählen"** erreichen. Aktivieren Sie hier das **Kontrollkästchen Failoverclustering.**
    
   - Klicken Sie **im Feld Features hinzufügen, die für Failoverclustering erforderlich sind?** auf **"Features hinzufügen".**
    
   - Klicken Sie auf **Installieren**.
    
6. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server Manager auf das Menü **"Extras",** und klicken Sie dann auf **"Failovercluster-Manager".**
    
   - Klicken **Sie auf** der rechten Seite des Bildschirms unter "Aktionen" auf **"Konfiguration überprüfen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann **auf "Alle Tests ausführen".**
    
   - Überprüfen Sie **im Feld "Zusammenfassung"** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **"Fertig** stellen", um die Überprüfung durchzuführen.
    
     Der Assistent wird wahrscheinlich mehrere Warnungen melden, insbesondere wenn Sie keinen freigegebenen Speicher verwenden. Sie müssen keinen freigegebenen Speicher verwenden. Wenn jedoch Fehlermeldungen **angezeigt** werden, müssen Sie diese Probleme beheben, bevor Sie fortfahren.
    
7. Erstellen Sie den Windows Server-Failovercluster.
    
   - Klicken Sie **im Assistenten für die Failoverclusterverwaltung** mit der rechten Maustaste auf **Failoverclusterverwaltung,** und klicken Sie dann **auf "Cluster erstellen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Fügen Sie den Clusternamen und die IP-Adresse hinzu. Wenn die Einstellungen überprüft werden, klicken Sie auf **"Weiter".**
    
   - Klicken Sie auf der Seite Bestätigung auf **Weiter**.
    
   - Klicken Sie nach dem Erstellen des Clusters auf **"Fertig stellen".**
    
8. Es wird empfohlen, die Clusterquorumeinstellungen für die Verwendung eines Dateifreigabezeugen zu konfigurieren. Gehen Sie dazu wie im folgenden Schritt vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, **klicken** Sie auf "Weitere Aktionen", und klicken Sie auf **"Clusterquorumeinstellungen konfigurieren".**
    
   - Klicken Sie **auf der Seite "Quorumkonfigurationsoption** auswählen" **auf "Quorumzeugen auswählen".**
    
   - Klicken Sie **auf der Seite "Quorumzeugen** auswählen" auf **"Dateifreigabenzeugen konfigurieren".**
    
   - Geben Sie auf der Seite **"Dateifreigabenzeugen** konfigurieren" den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **"Weiter".**
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
9. Aktivieren Sie auf jedem Server im Cluster das Feature AG in SQL Server Configuration Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur auf der linken Seite des Bildschirms auf **SQL Server Dienste,** und doppelklicken Sie dann auf SQL Server Dienst. 
    
   - Wählen Sie **im Feld "Eigenschaften"** die Registerkarte **"AlwaysOn High Availability"** aus. Aktivieren Sie **das Kontrollkästchen "AlwaysOn-Verfügbarkeitsgruppen** aktivieren". Starten Sie den SQL Server, wenn Sie dazu aufgefordert werden.
    
10. Erstellen Sie die Verfügbarkeitsgruppe.
    
    - Öffnen SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server herstellen.
    
    - Erweitern Sie im Objekt-Explorer den Ordner **"Always On High Availability".** Klicken Sie mit der rechten Maustaste auf den Ordner **"Verfügbarkeitsgruppen",** und klicken Sie auf **"Neuer Verfügbarkeitsgruppen-Assistent".**
    
    - Wenn die **Seite "Einführung"** angezeigt wird, klicken Sie auf **"Weiter".**
    
    - Geben Sie auf der Seite **Verfügbarkeitsgruppenname** angeben den Namen der Verfügbarkeitsgruppe ein, und klicken Sie auf **"Weiter".**
    
    - Wählen Sie auf der Seite Datenbanken auswählen die Datenbanken aus, die Sie in die Verfügbarkeitsgruppe "AlwaysOn" hinzufügen möchten. Then click **Next**.
    
    Schließen Sie die **Datenbanken ReportServer,** **ReportServerTempDB** oder Persistent Chat nicht in die Verfügbarkeitsgruppe "AlwaysOn" ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server-Datenbanken in die Verfügbarkeitsgruppe "AlwaysOn" einplanen.
    
    - Klicken Sie **auf der Seite Replikate** angeben auf die Registerkarte **Replikate.** Klicken Sie  dann auf die Schaltfläche Replikate hinzufügen, und stellen Sie eine Verbindung mit den anderen SQL, die Sie als Knoten des Windows Server-Failoverclusters verbunden haben.
    
    - Wählen Sie für jede Instanz die Optionen **"Automatisches Failover" und** **"Synchroner Commit"** aus. Wählen Sie nicht die Option **"Lesbare sekundäre Option"** aus.
    
    - Klicken Sie **auf die Registerkarte "Endpunkte",** und stellen Sie sicher, dass **die Portnummer** auf 5022 festgelegt ist.
    
      - Klicken Sie auf **die Registerkarte "Listener",** und wählen Sie die Option **"Verfügbarkeitsgruppenlistener erstellen"** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf 1433 fest (andere Ports werden für diese Option nicht unterstützt).
    
    - Klicken **Sie auf**"Hinzufügen" und dann im Feld **"IPv4-Adresse",** geben Sie Ihre bevorzugte virtuelle IP-Adresse ein, und klicken Sie dann auf **"OK".**
    
    - Wählen  Sie auf der Seite "Anfängliche Datensynchronisierung auswählen" die Option "Vollständig" aus, und geben Sie einen Ordner an, auf den die Replikate zugreifen können und für den das von beiden Replikaten verwendete SQL Server-Dienstkonto schreibberechtigungen besitzt. Then click **Next**.
    
    Diese Dateifreigabe wird vorübergehend verwendet, wenn Sie die Datenbanken initialisieren. Bei großen Datenbanken wird empfohlen, diese manuell zu initialisieren, falls die Netzwerkbandbreite die Größe der Datenbanksicherungen nicht aufnehmen kann.
    
    - Überprüfen Sie auf der Seite "Überprüfung", ob alle Überprüfungen erfolgreich waren, und klicken Sie dann auf **"Weiter".**
    
    - Überprüfen Sie **auf der Seite "Zusammenfassung"** alle Einstellungen, und klicken Sie auf "Fertig stellen".
    
11. Erstellen Sie einen neuen Speicher, in dem der Listener der AG angegeben wird, und geben Sie den Prinzipal des alten Spiegels als primären Knoten der AG an.
    
    - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie **"Freigegebene** Komponenten", klicken Sie mit der rechten Maustaste **auf SQL Server Speichern,** und klicken Sie auf **"SQL Server Store".**
    
    - Aktivieren Sie auf der Seite **"Neuen SQL Speicher** definieren" zuerst das Kontrollkästchen "Hochverfügbarkeitseinstellungen", und stellen Sie dann sicher, dass SQL -Verfügbarkeitsgruppen im Dropdownfeld angezeigt werden. 
    
    - Geben Sie **SQL Server FQDN** des Verfügbarkeitslisteners im Feld "Verfügbarkeitslistener" den FQDN des Listeners ein, den Sie beim Erstellen der Verfügbarkeitsgruppe erstellt haben.
    
    - Geben Sie **SQL Server FQDN** des primären Knotens der AG ein, und klicken Sie dann auf **OK**. Dies sollte der Prinzipal des alten Spiegels für diesen Speicher sein.
    
12. Ordnen Sie die neue AG dem Front-End-Pool zu.
    
    - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, der der AG zugeordnet werden soll, und klicken Sie dann **auf "Eigenschaften bearbeiten".**
    
    - Wählen **Sie unter Zuordnungen** **im Feld SQL Server Store** die AG aus. Wählen Sie dieselbe Gruppe für alle anderen Datenbanken im Pool aus, die Sie in die AG verschieben möchten.
    
    - Wenn Sie sicher sind, dass alle erforderlichen Datenbanken auf die AG festgelegt sind, klicken Sie auf **"OK".**
    
13. Veröffentlichen Sie die Topologie. Klicken Sie **im Menü "Aktion"** **auf "Topologie"** und dann **auf "Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
14. Führen Sie abschließende Schritte aus, um sicherzustellen, dass SQL A0 auf jedem Replikat in der Verfügbarkeitsgruppe "AlwaysOn" angezeigt werden.
    
    - Öffnen Sie den Topologie-Generator, wählen **Sie "Topologie aus vorhandener Bereitstellung herunterladen"** aus, und klicken Sie auf **"OK".**
    
    - Erweitern Sie Skype for Business Server, Erweitern Sie Ihre Topologie und SQL Server **Stores**. Klicken Sie mit der rechten maustaste SQL speicher der neuen AG, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
    - Ändern Sie unten auf der Seite im Feld **SQL Server FQDN** den Wert in den FQDN des Listeners der AG.
    
    - Veröffentlichen Sie die Topologie. Klicken Sie **im Menü "Aktion"** **auf "Topologie"** und dann **auf "Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".** Warten Sie dann einige Minuten, bis die neue Topologie repliziert wurde.
    
    - Öffnen SQL Server Management Studio, und navigieren Sie zur AG. Führen Sie ein Failover auf ein sekundäres Replikat durch.
    
    - Öffnen Sie die Skype for Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL auf diesem Replikat zu erstellen:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Wiederholen Sie die beiden vorherigen Schritte (failovern Sie die Gruppe auf ein sekundäres Replikat, und verwenden Sie dann ) für jedes Replikat  `Install-CsDatabase -Update` in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Bereitstellen einer Always On-Verfügbarkeitsgruppe in einem vorhandenen Pool ohne Datenbankspiegelung
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, den Sie auf eine AG aktualisieren, den zentralen Verwaltungsspeicher für Ihre Organisation hostet, müssen Sie den CMS zunächst in einen anderen Pool verschieben, bevor Sie diesen Pool aktualisieren. Verwenden Sie Move-CsManagementServer cmdlet, um den Pool zu verschieben. Wenn In Ihrer Organisation kein weiterer Pool vorhanden ist, können Sie einen Standard Edition-Server vorübergehend bereitstellen und den CMS auf diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren. 
  
1. Richten Sie das Failoverclusteringfeature auf allen Datenbankservern ein, die Teil der AG sein werden. Gehen Sie auf jedem Server wie folgt vor:
    
   - Öffnen Sie den Server-Manager, und klicken **Sie auf "Rollen und Features hinzufügen".**
    
   - Klicken **Sie auf "Weiter",** bis Sie das Feld **"Features auswählen"** erreichen. Aktivieren Sie hier das **Kontrollkästchen Failoverclustering.**
    
   - Klicken Sie **im Feld Features hinzufügen, die für Failoverclustering erforderlich sind?** auf **"Features hinzufügen".**
    
   - Klicken Sie auf **Installieren**.
    
2. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server Manager auf das Menü **"Extras",** und klicken Sie dann auf **"Failovercluster-Manager".**
    
   - Klicken **Sie auf** der rechten Seite des Bildschirms unter "Aktionen" auf **"Konfiguration überprüfen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann **auf "Alle Tests ausführen".**
    
   - Überprüfen Sie **im Feld "Zusammenfassung"** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **"Fertig** stellen", um die Überprüfung durchzuführen.
    
     Der Assistent wird wahrscheinlich mehrere Warnungen melden, insbesondere wenn Sie keinen freigegebenen Speicher verwenden. Sie müssen keinen freigegebenen Speicher verwenden. Wenn jedoch Fehlermeldungen **angezeigt** werden, müssen Sie diese Probleme beheben, bevor Sie fortfahren.
    
3. Erstellen Sie den Windows Server-Failovercluster (WSFC).
    
   - Klicken Sie **im Assistenten für die Failoverclusterverwaltung** mit der rechten Maustaste auf **Failoverclusterverwaltung,** und klicken Sie dann **auf "Cluster erstellen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Fügen Sie den Clusternamen und die IP-Adresse hinzu. Wenn die Einstellungen überprüft werden, klicken Sie auf **"Weiter".**
    
   - Klicken Sie auf der Seite Bestätigung auf **Weiter**.
    
   - Klicken Sie nach dem Erstellen des Clusters auf **"Fertig stellen".**
    
4. Es wird empfohlen, die Clusterquorumeinstellungen für die Verwendung eines Dateifreigabezeugen zu konfigurieren. Gehen Sie dazu wie im folgenden Schritt vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, **klicken** Sie auf "Weitere Aktionen", und klicken Sie auf **"Clusterquorumeinstellungen konfigurieren".**
    
   - Klicken Sie **auf der Seite "Quorumkonfigurationsoption** auswählen" **auf "Quorumzeugen auswählen".**
    
   - Klicken Sie **auf der Seite "Quorumzeugen** auswählen" auf **"Dateifreigabenzeugen konfigurieren".**
    
   - Geben Sie auf der Seite **"Dateifreigabenzeugen** konfigurieren" den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **"Weiter".**
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
5. Aktivieren Sie auf jedem Server im Cluster ag in SQL Server Configuration Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur auf der linken Seite des Bildschirms auf **SQL Server Dienste,** und doppelklicken Sie dann auf SQL Server Dienst. 
    
   - Wählen Sie **im Feld "Eigenschaften"** die Registerkarte **"AlwaysOn High Availability"** aus. Aktivieren Sie **das Kontrollkästchen "AlwaysOn-Verfügbarkeitsgruppen** aktivieren". Starten Sie den SQL Server, wenn Sie dazu aufgefordert werden.
    
6. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server herstellen.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **"Always On High Availability".** Klicken Sie mit der rechten Maustaste auf den Ordner **"Verfügbarkeitsgruppen",** und klicken Sie auf **"Neuer Verfügbarkeitsgruppen-Assistent".**
    
   - Wenn die **Seite "Einführung"** angezeigt wird, klicken Sie auf **"Weiter".**
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppenname** angeben den Namen der Verfügbarkeitsgruppe ein, und klicken Sie auf **"Weiter".**
    
   - Wählen Sie auf der Seite Datenbanken auswählen die Datenbanken aus, die Sie in die AG hinzufügen möchten. Then click **Next**.
    
     Schließen Sie die **Datenbanken ReportServer,** **ReportServerTempDB** oder Persistent Chat nicht in die AG ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server-Datenbanken in die AG einplanen.
    
   - Klicken Sie **auf der Seite Replikate** angeben auf die Registerkarte **Replikate.** Klicken Sie dann auf **die** Schaltfläche Replikate hinzufügen, und stellen Sie eine Verbindung mit den anderen SQL, die Sie als Knoten des WSFC verbunden haben.
    
   - Wählen Sie für jede Instanz die Optionen **"Automatisches Failover" und** **"Synchroner Commit"** aus. Wählen Sie nicht die Option **"Lesbare sekundäre Option"** aus.
    
   - Klicken Sie **auf die Registerkarte "Endpunkte",** und stellen Sie sicher, dass **die Portnummer** auf 5022 festgelegt ist.
    
   - Klicken Sie auf **die Registerkarte "Listener",** und wählen Sie die Option **"Verfügbarkeitsgruppenlistener erstellen"** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf 1433 fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken **Sie auf**"Hinzufügen" und dann im Feld **"IPv4-Adresse",** geben Sie Ihre bevorzugte virtuelle IP-Adresse ein, und klicken Sie dann auf **"OK".**
    
   - Wählen  Sie auf der Seite "Anfängliche Datensynchronisierung auswählen" die Option "Vollständig" aus, und geben Sie einen Ordner an, auf den die Replikate zugreifen können und für den das von beiden Replikaten verwendete SQL Server-Dienstkonto schreibberechtigungen besitzt. Then click **Next**.
    
     Diese Dateifreigabe wird vorübergehend verwendet, wenn Sie die Datenbanken initialisieren. Bei großen Datenbanken wird empfohlen, diese manuell zu initialisieren, falls die Netzwerkbandbreite die Größe der Datenbanksicherungen nicht aufnehmen kann.
    
     - Überprüfen Sie auf der Seite "Überprüfung", ob alle Überprüfungen erfolgreich waren, und klicken Sie dann auf **"Weiter".**
    
   - Überprüfen Sie **auf der Seite "Zusammenfassung"** alle Einstellungen, und klicken Sie auf "Fertig stellen".
    
7. Erstellen Sie einen neuen Speicher, der den Ag-Listener an gibt.
    
   - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie **"Freigegebene** Komponenten", klicken Sie mit der rechten Maustaste **auf SQL Server Speichern,** und klicken Sie auf **"SQL Server Store".**
    
   - Aktivieren Sie auf der Seite **"Neuen SQL Speicher** definieren" zuerst das Kontrollkästchen "Hochverfügbarkeitseinstellungen", und stellen Sie dann sicher, dass SQL -Verfügbarkeitsgruppen im Dropdownfeld angezeigt werden. 
    
   - Geben Sie **SQL Server FQDN** des Verfügbarkeitslisteners im Feld "Verfügbarkeitslistener" den FQDN des Listeners ein, den Sie beim Erstellen der Verfügbarkeitsgruppe erstellt haben.
    
   - Geben Sie **SQL Server FQDN** des primären Knotens der AG ein, und klicken Sie dann auf **OK**.
    
8. Ordnen Sie die neue Always On-Verfügbarkeitsgruppe dem Front-End-Pool zu.
    
   - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, der der AG zugeordnet werden soll, und klicken Sie dann **auf "Eigenschaften bearbeiten".**
    
   - Wählen **Sie unter Zuordnungen** **im Feld SQL Server Store** die AG aus. Wählen Sie dieselbe Gruppe für alle anderen Datenbanken im Pool aus, die Sie in die AG verschieben möchten.
    
   - Wenn Sie sicher sind, dass alle erforderlichen Datenbanken auf die AG festgelegt sind, klicken Sie auf **"OK".**
    
9. Veröffentlichen Sie die Topologie. Klicken Sie **im Menü "Aktion"** **auf "Topologie"** und dann **auf "Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
10. Führen Sie abschließende Schritte aus, um sicherzustellen, dass SQL A0 auf jedem Replikat in der AG befinden.
    
    - Öffnen Sie den Topologie-Generator, wählen **Sie "Topologie aus vorhandener Bereitstellung herunterladen"** aus, und klicken Sie auf **"OK".**
    
    - Erweitern Sie Skype for Business Server, Erweitern Sie Ihre Topologie und SQL Server **Stores**. Klicken Sie mit der rechten maustaste SQL speicher der neuen AG, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
    - Ändern Sie unten auf der Seite im Feld **SQL Server FQDN** den Wert in den FQDN des Listeners der AG.
    
    - Veröffentlichen Sie die Topologie. Klicken Sie **im Menü "Aktion"** **auf "Topologie"** und dann **auf "Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".** Warten Sie dann einige Minuten, bis die neue Topologie repliziert wurde.
    
    - Öffnen SQL Server Management Studio, und navigieren Sie zur AG. Führen Sie ein Failover auf ein sekundäres Replikat durch.
    
    - Öffnen Sie die Skype for Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL auf diesem Replikat zu erstellen:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Wiederholen Sie die beiden vorherigen Schritte (failovern Sie die Gruppe auf ein sekundäres Replikat, und verwenden Sie dann ) für jedes Replikat  `Install-CsDatabase -Update` in der Gruppe.
