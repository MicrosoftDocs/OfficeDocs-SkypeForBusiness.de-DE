---
title: Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Bereitstellen (Installieren) einer AlwaysOn-Verfügbarkeitsgruppe in Ihrer Skype for Business Server Bereitstellung.
ms.openlocfilehash: 69a7627850da06a2a120c0c37fbf83f87c17c277
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755644"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a>Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server
 
Bereitstellen (Installieren) einer AlwaysOn-Verfügbarkeitsgruppe (AG) in Ihrer Skype for Business Server Bereitstellung.
  
Wie Sie eine AG bereitstellen, hängt davon ab, ob Sie sie in einem neuen Pool, einem vorhandenen Pool mit Spiegelung oder einem vorhandenen Pool bereitstellen, der derzeit keine hohe Verfügbarkeit für die Back-End-Datenbank aufweist.
  
> [!NOTE]
> Die Verwendung einer AG mit einer Serverrolle für beständigen Chat wird nicht unterstützt. 
  
- [Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem neuen Front-End-Pool](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem vorhandenen Pool, der datenbankspiegelung verwendet](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem vorhandenen Pool, der keine Datenbankspiegelung verwendet](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a>Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem neuen Front-End-Pool
<a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a>

1. Aktivieren Sie das Failoverclustering-Feature auf allen Datenbankservern, die Teil der AG sein werden. Führen Sie auf jedem Server die folgenden Aktionen aus:
    
   - Öffnen Sie den Server-Manager, und klicken Sie auf **"Rollen und Features hinzufügen".**
    
   - Klicken Sie auf **"Weiter",** bis Sie das Feld **"Features auswählen"** erreichen. Aktivieren Sie hier das **Kontrollkästchen Failoverclustering.**
    
   - Klicken Sie im Feld **"Features hinzufügen, die für Failoverclustering erforderlich sind"** auf **"Features hinzufügen".**
    
   - Klicken Sie auf **Installieren**.
    
2. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server-Manager auf das Menü **Extras** und dann auf **Failovercluster-Manager.**
    
   - Klicken Sie auf der rechten Seite des Bildschirms unter **"Aktionen"** auf **"Konfiguration überprüfen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **"Alle Tests ausführen".**
    
   - Aktivieren Sie im **Kontrollkästchen Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen,** um die Überprüfung abzuschließen.
    
     Der Assistent meldet wahrscheinlich mehrere Warnungen, insbesondere wenn Sie keinen freigegebenen Speicher verwenden. Sie müssen keinen freigegebenen Speicher verwenden. Wenn jedoch **Fehlermeldungen** angezeigt werden, müssen Sie diese Probleme beheben, bevor Sie fortfahren.
    
3. Erstellen Sie den Windows Serverfailovercluster (WSFC).
    
   - Klicken Sie im **Failoverclusterverwaltungs-Assistenten** mit der rechten Maustaste auf **"Failoverclusterverwaltung",** und klicken Sie dann auf **"Cluster erstellen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Fügen Sie den Clusternamen und die IP-Adresse hinzu. Wenn die Einstellungen überprüft werden, klicken Sie auf **"Weiter".**
    
   - Klicken Sie auf der Seite Bestätigung auf **Weiter**.
    
   - Klicken Sie nach dem Erstellen des Clusters auf **"Fertig stellen".**
    
4. Es wird empfohlen, die Clusterquorumeinstellungen so zu konfigurieren, dass ein Dateifreigabezeugen verwendet wird. Gehen Sie dazu folgendermaßen vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, klicken Sie auf **Weitere Aktionen,** und klicken Sie auf **Clusterquorum Einstellungen konfigurieren.**
    
   - Klicken Sie auf der Seite **"Quorumkonfigurationsoption auswählen"** auf **"Quorumzeugen auswählen".**
    
   - Klicken Sie auf der Seite **"Quorumzeugen auswählen"** auf **"Dateifreigabezeugen konfigurieren".**
    
   - Geben Sie auf der Seite **"Dateifreigabezeugen konfigurieren"** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **"Weiter".**
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
5. Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur auf der linken Seite des Bildschirms auf **SQL Server Dienste,** und doppelklicken Sie dann auf den SQL Server Dienst. 
    
   - Wählen Sie im Feld Eigenschaften die Registerkarte **AlwaysOn High** Availability aus.  Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren.** Starten Sie den SQL Server-Dienst neu, wenn Sie dazu aufgefordert werden.
   
6. Verwenden Sie den Topologie-Generator, um den Front-End-Pool zu erstellen, wie unter [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md)erläutert. Geben Sie in diesem Fall die AG als SQL Speicher für den Pool an.
    
7. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server Instanz her.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **"Always On High Availability".** Klicken Sie mit der rechten Maustaste auf den Ordner **"Verfügbarkeitsgruppen",** und klicken Sie auf **"Neuer Verfügbarkeitsgruppen-Assistent".**
    
   - Wenn die **Einführungsseite** angezeigt wird, klicken Sie auf **"Weiter".**
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppenname angeben** den Namen der Verfügbarkeitsgruppe ein, und klicken Sie auf **"Weiter".**
    
   - Wählen Sie auf der Seite "Datenbanken auswählen" die Datenbanken aus, die Sie in die AlwaysOn-Verfügbarkeitsgruppe einschließen möchten. Klicken Sie dann auf **Weiter**.
    
     Schließen Sie die Datenbanken **"ReportServer",** **"ReportServerTempDB"** oder "Beständiger Chat" nicht in die AlwaysOn-Verfügbarkeitsgruppe ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server Datenbanken in die AlwaysOn-Verfügbarkeitsgruppe einschließen.
    
   - Klicken Sie auf der Seite **"Replikate angeben"** auf die Registerkarte **"Replikate".** Klicken Sie dann auf die Schaltfläche **"Replikate hinzufügen",** und stellen Sie eine Verbindung mit den anderen SQL Instanzen her, die Sie als Knoten des Windows Serverfailoverclusters hinzugefügt haben.
    
   - Wählen Sie für jede Instanz die Optionen **für automatisches Failover** und **synchrones Commit** aus. Wählen Sie nicht die Option **"Lesbar sekundär"** aus.
    
   - Klicken Sie auf die Registerkarte **"Endpunkte",** und stellen Sie sicher, dass die **Portnummer** auf 5022 festgelegt ist.
    
   - Klicken Sie auf die Registerkarte **"Listener",** und wählen Sie die Option **"Verfügbarkeitsgruppenlistener** erstellen" aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf 1433 fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken Sie auf **"Hinzufügen",** und geben Sie dann im Feld **"IPv4-Adresse"** Ihre bevorzugte virtuelle IP-Adresse an, und klicken Sie dann auf **"OK".**
    
   - Wählen Sie auf der Seite **"Anfängliche Datensynchronisierung auswählen"** die Option "Vollständig" aus, und geben Sie einen Ordner an, auf den die Replikate zugreifen können und für den das SQL Server von beiden Replikaten verwendete Dienstkonto über Schreibberechtigungen verfügt. Klicken Sie dann auf **Weiter**.
    
     Diese Dateifreigabe wird vorübergehend verwendet, wenn Sie die Datenbanken initialisieren. Wenn Es sich um große Datenbanken handelt, empfehlen wir, diese manuell zu initialisieren, falls ihre Netzwerkbandbreite nicht der Größe der Datenbanksicherungen entsprechen kann.
    
   - Überprüfen Sie auf der Seite "Überprüfung", ob alle Überprüfungen erfolgreich sind, und klicken Sie dann auf **"Weiter".**
    
   - Überprüfen Sie auf der Seite **"Zusammenfassung"** alle Einstellungen, und klicken Sie auf "Fertig stellen".
      
8. Führen Sie nach der Bereitstellung des Pools und der AG einige abschließende Schritte aus, um sicherzustellen, dass sich die SQL Anmeldungen für jedes Replikat in der AlwaysOn-Verfügbarkeitsgruppe befinden. 
    
   - Öffnen Sie den Topologie-Generator, wählen Sie **"Topologie aus vorhandener Bereitstellung herunterladen" aus,** und klicken Sie auf **"OK".**
    
   - Erweitern Sie Skype for Business Server, erweitern Sie Ihre Topologie, und erweitern Sie **SQL Server Stores.** Klicken Sie mit der rechten Maustaste auf den SQL Speicher der neuen AlwaysOn-Verfügbarkeitsgruppe, und klicken Sie auf **Eigenschaften bearbeiten.**
    
     - Ändern Sie unten auf der Seite im **Feld SQL Server FQDN** den Wert in den FQDN des Listeners der AG.
    
   - Veröffentlichen Sie die Topologie. Klicken Sie im Menü **"Aktion"** auf **"Topologie"** und dann auf **"Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".** Warten Sie dann einige Minuten, bis die neue Topologie repliziert wurde.
    
   - Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AG. Fail it over to a secondary replica.
    
   - Öffnen Sie Skype for Business Server Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL Anmeldungen für dieses Replikat zu erstellen:
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - Wiederholen Sie die beiden vorherigen Schritte (Führen Sie ein Failover der Gruppe zu einem sekundären Replikat durch, und verwenden Sie sie  `Install-CsDatabase -Update` dann) für jedes Replikat in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a>Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem vorhandenen Pool, der datenbankspiegelung verwendet
<a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, den Sie auf eine AG aktualisieren, den zentralen Verwaltungsspeicher für Ihre Organisation hostet, müssen Sie den CMS zuerst in einen anderen Pool verschieben, bevor Sie diesen Pool aktualisieren. Verwenden Sie das cmdlet Move-CsManagementServer, um den Pool zu verschieben. Wenn Sie keinen anderen Pool in Ihrer Organisation haben, können Sie vorübergehend einen Standard Edition Server bereitstellen und den CMS auf diesen Server verschieben, bevor Sie Ihr Pool auf die AG aktualisieren. 
  
1. Führen Sie ein Failover aller Daten vom Spiegel zum Prinzipalknoten durch, indem Sie Skype for Business Server Verwaltungsshell öffnen und das folgende Cmdlet eingeben.
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    Wiederholen Sie dieses Cmdlet für jeden Datenbanktyp im Pool. Mit dem folgenden Cmdlet können Sie alle in diesem Pool gespeicherten Datenbanktypen suchen.
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. Verwenden Sie den Topologie-Generator, um die Datenbankspiegelung aus dem Pool zu entfernen.
    
   - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie **Enterprise Edition Front-End-Pools,** klicken Sie mit der rechten Maustaste auf den Namen des Pools, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
   - Deaktivieren Sie für jeden Typ von SQL Speicher im Pool das Kontrollkästchen **SQL Store Spiegelung aktivieren.**
    
3. Veröffentlichen Sie die geänderte Topologie. Klicken Sie im Menü **"Aktion"** auf **"Topologie"** und dann auf **"Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
4. Verwenden Sie SQL Server Management Studio, um den Spiegel zu unterbrechen.
    
   - Öffnen Sie SQL Server Management Studio, navigieren Sie zu Ihren Datenbanken, klicken Sie mit der rechten Maustaste auf **"Aufgaben",** und klicken Sie auf **"Spiegelung".** Klicken Sie dann auf **"Spiegelung entfernen",** und klicken Sie auf **"OK".**
    
   - Wiederholen Sie dies für alle Datenbanken im Pool, die in eine AG konvertiert werden.
    
5. Richten Sie das Failoverclustering-Feature auf allen Datenbankservern ein, die Teil der AG sein werden. Führen Sie auf jedem Server die folgenden Aktionen aus:
    
   - Öffnen Sie den Server-Manager, und klicken Sie auf **"Rollen und Features hinzufügen".**
    
   - Klicken Sie auf **"Weiter",** bis Sie das Feld **"Features auswählen"** erreichen. Aktivieren Sie hier das **Kontrollkästchen Failoverclustering.**
    
   - Klicken Sie im Feld **"Features hinzufügen, die für Failoverclustering erforderlich sind"** auf **"Features hinzufügen".**
    
   - Klicken Sie auf **Installieren**.
    
6. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server-Manager auf das Menü **Extras** und dann auf **Failovercluster-Manager.**
    
   - Klicken Sie auf der rechten Seite des Bildschirms unter **"Aktionen"** auf **"Konfiguration überprüfen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **"Alle Tests ausführen".**
    
   - Aktivieren Sie im **Kontrollkästchen Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen,** um die Überprüfung abzuschließen.
    
     Der Assistent meldet wahrscheinlich mehrere Warnungen, insbesondere wenn Sie keinen freigegebenen Speicher verwenden. Sie müssen keinen freigegebenen Speicher verwenden. Wenn jedoch **Fehlermeldungen** angezeigt werden, müssen Sie diese Probleme beheben, bevor Sie fortfahren.
    
7. Erstellen Sie den Windows Serverfailovercluster.
    
   - Klicken Sie im **Failoverclusterverwaltungs-Assistenten** mit der rechten Maustaste auf **"Failoverclusterverwaltung",** und klicken Sie dann auf **"Cluster erstellen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Fügen Sie den Clusternamen und die IP-Adresse hinzu. Wenn die Einstellungen überprüft werden, klicken Sie auf **"Weiter".**
    
   - Klicken Sie auf der Seite Bestätigung auf **Weiter**.
    
   - Klicken Sie nach dem Erstellen des Clusters auf **"Fertig stellen".**
    
8. Es wird empfohlen, die Clusterquorumeinstellungen so zu konfigurieren, dass ein Dateifreigabezeugen verwendet wird. Gehen Sie dazu folgendermaßen vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, klicken Sie auf **Weitere Aktionen,** und klicken Sie auf **Clusterquorum Einstellungen konfigurieren.**
    
   - Klicken Sie auf der Seite **"Quorumkonfigurationsoption auswählen"** auf **"Quorumzeugen auswählen".**
    
   - Klicken Sie auf der Seite **"Quorumzeugen auswählen"** auf **"Dateifreigabezeugen konfigurieren".**
    
   - Geben Sie auf der Seite **"Dateifreigabezeugen konfigurieren"** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **"Weiter".**
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
9. Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur auf der linken Seite des Bildschirms auf **SQL Server Dienste,** und doppelklicken Sie dann auf den SQL Server Dienst. 
    
   - Wählen Sie im Feld Eigenschaften die Registerkarte **AlwaysOn High** Availability aus.  Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren.** Starten Sie den SQL Server-Dienst neu, wenn Sie dazu aufgefordert werden.
    
10. Erstellen Sie die Verfügbarkeitsgruppe.
    
    - Öffnen Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server Instanz her.
    
    - Erweitern Sie im Objekt-Explorer den Ordner **"Always On High Availability".** Klicken Sie mit der rechten Maustaste auf den Ordner **"Verfügbarkeitsgruppen",** und klicken Sie auf **"Neuer Verfügbarkeitsgruppen-Assistent".**
    
    - Wenn die **Einführungsseite** angezeigt wird, klicken Sie auf **"Weiter".**
    
    - Geben Sie auf der Seite **Verfügbarkeitsgruppenname angeben** den Namen der Verfügbarkeitsgruppe ein, und klicken Sie auf **"Weiter".**
    
    - Wählen Sie auf der Seite "Datenbanken auswählen" die Datenbanken aus, die Sie in die AlwaysOn-Verfügbarkeitsgruppe einschließen möchten. Klicken Sie dann auf **Weiter**.
    
    Schließen Sie die Datenbanken **"ReportServer",** **"ReportServerTempDB"** oder "Beständiger Chat" nicht in die AlwaysOn-Verfügbarkeitsgruppe ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server Datenbanken in die AlwaysOn-Verfügbarkeitsgruppe einschließen.
    
    - Klicken Sie auf der Seite **"Replikate angeben"** auf die Registerkarte **"Replikate".** Klicken Sie dann auf die Schaltfläche **"Replikate hinzufügen",** und stellen Sie eine Verbindung mit den anderen SQL Instanzen her, die Sie als Knoten des Windows Serverfailoverclusters hinzugefügt haben.
    
    - Wählen Sie für jede Instanz die Optionen **für automatisches Failover** und **synchrones Commit** aus. Wählen Sie nicht die Option **"Lesbar sekundär"** aus.
    
    - Klicken Sie auf die Registerkarte **"Endpunkte",** und stellen Sie sicher, dass die **Portnummer** auf 5022 festgelegt ist.
    
      - Klicken Sie auf die Registerkarte **"Listener",** und wählen Sie die Option **"Verfügbarkeitsgruppenlistener** erstellen" aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf 1433 fest (andere Ports werden für diese Option nicht unterstützt).
    
    - Klicken Sie auf **"Hinzufügen",** und geben Sie dann im Feld **"IPv4-Adresse"** Ihre bevorzugte virtuelle IP-Adresse an, und klicken Sie dann auf **"OK".**
    
    - Wählen Sie auf der Seite **"Anfängliche Datensynchronisierung auswählen"** die Option "Vollständig" aus, und geben Sie einen Ordner an, auf den die Replikate zugreifen können und für den das SQL Server von beiden Replikaten verwendete Dienstkonto über Schreibberechtigungen verfügt. Klicken Sie dann auf **Weiter**.
    
    Diese Dateifreigabe wird vorübergehend verwendet, wenn Sie die Datenbanken initialisieren. Wenn Es sich um große Datenbanken handelt, empfehlen wir, diese manuell zu initialisieren, falls ihre Netzwerkbandbreite nicht der Größe der Datenbanksicherungen entsprechen kann.
    
    - Überprüfen Sie auf der Seite "Überprüfung", ob alle Überprüfungen erfolgreich sind, und klicken Sie dann auf **"Weiter".**
    
    - Überprüfen Sie auf der Seite **"Zusammenfassung"** alle Einstellungen, und klicken Sie auf "Fertig stellen".
    
11. Erstellen Sie einen neuen Speicher, der den AG-Listener angibt und den Prinzipal der alten Spiegelung als primären Knoten der AG angibt.
    
    - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie **"Freigegebene Komponenten",** klicken Sie mit der rechten Maustaste auf **SQL Server Speicher,** und klicken Sie auf **"Neu SQL Server Store".**
    
    - Aktivieren Sie auf der Seite **"Neue SQL Store definieren"** zuerst das **Kontrollkästchen "Hohe Verfügbarkeit Einstellungen",** und stellen Sie dann sicher, dass SQL AlwaysOn-Verfügbarkeitsgruppen im Dropdownfeld angezeigt wird.
    
    - Geben Sie im **Feld SQL Server Verfügbarkeitslistener-FQDN** den FQDN des Listeners ein, den Sie beim Erstellen der Verfügbarkeitsgruppe erstellt haben.
    
    - Geben Sie im **Feld SQL Server FQDN** den FQDN des primären Knotens der AG ein, und klicken Sie dann auf **OK.** Dies sollte der Prinzipal des alten Spiegels für diesen Speicher sein.
    
12. Ordnen Sie die neue AG dem Front-End-Pool zu.
    
    - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, der der AG zugeordnet werden soll, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
    - Wählen Sie unter **Zuordnungen** im **Feld SQL Server Store** die AG aus. Wählen Sie dieselbe Gruppe für alle anderen Datenbanken im Pool aus, die Sie in die AG verschieben möchten.
    
    - Wenn Sie sicher sind, dass alle erforderlichen Datenbanken auf AG festgelegt sind, klicken Sie auf **OK.**
    
13. Veröffentlichen Sie die Topologie. Klicken Sie im Menü **"Aktion"** auf **"Topologie"** und dann auf **"Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
14. Führen Sie einige abschließende Schritte aus, um sicherzustellen, dass sich die SQL Anmeldungen für jedes Replikat in der AlwaysOn-Verfügbarkeitsgruppe befinden.
    
    - Öffnen Sie den Topologie-Generator, wählen Sie **"Topologie aus vorhandener Bereitstellung herunterladen" aus,** und klicken Sie auf **"OK".**
    
    - Erweitern Sie Skype for Business Server, erweitern Sie Ihre Topologie, und erweitern Sie **SQL Server Stores.** Klicken Sie mit der rechten Maustaste auf den SQL Speicher der neuen AG, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
    - Ändern Sie unten auf der Seite im **Feld SQL Server FQDN** den Wert in den FQDN des Listeners der AG.
    
    - Veröffentlichen Sie die Topologie. Klicken Sie im Menü **"Aktion"** auf **"Topologie"** und dann auf **"Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".** Warten Sie dann einige Minuten, bis die neue Topologie repliziert wurde.
    
    - Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AG. Fail it over to a secondary replica.
    
    - Öffnen Sie Skype for Business Server Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL Anmeldungen für dieses Replikat zu erstellen:
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - Wiederholen Sie die beiden vorherigen Schritte (Führen Sie ein Failover der Gruppe zu einem sekundären Replikat durch, und verwenden Sie sie  `Install-CsDatabase -Update` dann) für jedes Replikat in der Gruppe.
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a>Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem vorhandenen Pool, der keine Datenbankspiegelung verwendet
<a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a>

> [!NOTE]
> Wenn der Pool, den Sie auf eine AG aktualisieren, den zentralen Verwaltungsspeicher für Ihre Organisation hostet, müssen Sie den CMS zuerst in einen anderen Pool verschieben, bevor Sie diesen Pool aktualisieren. Verwenden Sie das Cmdlet Move-CsManagementServer, um den Pool zu verschieben. Wenn Sie keinen anderen Pool in Ihrer Organisation haben, können Sie vorübergehend einen Standard Edition Server bereitstellen und den CMS auf diesen Server verschieben, bevor Sie Ihr Pool auf die AG aktualisieren. 
  
1. Richten Sie das Failoverclustering-Feature auf allen Datenbankservern ein, die Teil der AG sein werden. Führen Sie auf jedem Server die folgenden Aktionen aus:
    
   - Öffnen Sie den Server-Manager, und klicken Sie auf **"Rollen und Features hinzufügen".**
    
   - Klicken Sie auf **"Weiter",** bis Sie das Feld **"Features auswählen"** erreichen. Aktivieren Sie hier das **Kontrollkästchen Failoverclustering.**
    
   - Klicken Sie im Feld **"Features hinzufügen, die für Failoverclustering erforderlich sind"** auf **"Features hinzufügen".**
    
   - Klicken Sie auf **Installieren**.
    
2. Überprüfen Sie die Clusterkonfiguration.
    
   - Klicken Sie im Server-Manager auf das Menü **Extras** und dann auf **Failovercluster-Manager.**
    
   - Klicken Sie auf der rechten Seite des Bildschirms unter **"Aktionen"** auf **"Konfiguration überprüfen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **"Alle Tests ausführen".**
    
   - Aktivieren Sie im **Kontrollkästchen Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen,** um die Überprüfung abzuschließen.
    
     Der Assistent meldet wahrscheinlich mehrere Warnungen, insbesondere wenn Sie keinen freigegebenen Speicher verwenden. Sie müssen keinen freigegebenen Speicher verwenden. Wenn jedoch **Fehlermeldungen** angezeigt werden, müssen Sie diese Probleme beheben, bevor Sie fortfahren.
    
3. Erstellen Sie den Windows Serverfailovercluster (WSFC).
    
   - Klicken Sie im **Failoverclusterverwaltungs-Assistenten** mit der rechten Maustaste auf **"Failoverclusterverwaltung",** und klicken Sie dann auf **"Cluster erstellen".**
    
   - Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.
    
   - Fügen Sie den Clusternamen und die IP-Adresse hinzu. Wenn die Einstellungen überprüft werden, klicken Sie auf **"Weiter".**
    
   - Klicken Sie auf der Seite Bestätigung auf **Weiter**.
    
   - Klicken Sie nach dem Erstellen des Clusters auf **"Fertig stellen".**
    
4. Es wird empfohlen, die Clusterquorumeinstellungen so zu konfigurieren, dass ein Dateifreigabezeugen verwendet wird. Gehen Sie dazu folgendermaßen vor:
    
   - Klicken Sie mit der rechten Maustaste auf den Clusternamen, klicken Sie auf **Weitere Aktionen,** und klicken Sie auf **Clusterquorum Einstellungen konfigurieren.**
    
   - Klicken Sie auf der Seite **"Quorumkonfigurationsoption auswählen"** auf **"Quorumzeugen auswählen".**
    
   - Klicken Sie auf der Seite **"Quorumzeugen auswählen"** auf **"Dateifreigabezeugen konfigurieren".**
    
   - Geben Sie auf der Seite **"Dateifreigabezeugen konfigurieren"** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **"Weiter".**
    
   - Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.
    
5. Aktivieren Sie auf jedem Server im Cluster AG in SQL Server-Konfigurations-Manager.
    
   - Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur auf der linken Seite des Bildschirms auf **SQL Server Dienste,** und doppelklicken Sie dann auf den SQL Server Dienst. 
    
   - Wählen Sie im Feld Eigenschaften die Registerkarte **AlwaysOn High** Availability aus.  Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren.** Starten Sie den SQL Server Dienst neu, wenn Sie dazu aufgefordert werden.
    
6. Erstellen Sie die Verfügbarkeitsgruppe.
    
   - Öffnen Sie SQL Server Management Studio, und stellen Sie eine Verbindung mit der SQL Server Instanz her.
    
   - Erweitern Sie im Objekt-Explorer den Ordner **"Always On High Availability".** Klicken Sie mit der rechten Maustaste auf den Ordner **"Verfügbarkeitsgruppen",** und klicken Sie auf **"Neuer Verfügbarkeitsgruppen-Assistent".**
    
   - Wenn die **Einführungsseite** angezeigt wird, klicken Sie auf **"Weiter".**
    
   - Geben Sie auf der Seite **Verfügbarkeitsgruppenname angeben** den Namen der Verfügbarkeitsgruppe ein, und klicken Sie auf **"Weiter".**
    
   - Wählen Sie auf der Seite "Datenbanken auswählen" die Datenbanken aus, die Sie in die AG einschließen möchten. Klicken Sie dann auf **Weiter**.
    
     Schließen Sie die Datenbanken **"ReportServer",** **"ReportServerTempDB"** oder "Beständiger Chat" nicht in die AG ein, da diese in diesem Szenario nicht unterstützt werden. Sie können alle anderen Skype for Business Server Datenbanken in die AG einschließen.
    
   - Klicken Sie auf der Seite **"Replikate angeben"** auf die Registerkarte **"Replikate".** Klicken Sie dann auf die Schaltfläche **"Replikate hinzufügen",** und stellen Sie eine Verbindung mit den anderen SQL Instanzen her, die Sie als Knoten des WSFC hinzugefügt haben.
    
   - Wählen Sie für jede Instanz die Optionen **für automatisches Failover** und **synchrones Commit** aus. Wählen Sie nicht die Option **"Lesbar sekundär"** aus.
    
   - Klicken Sie auf die Registerkarte **"Endpunkte",** und stellen Sie sicher, dass die **Portnummer** auf 5022 festgelegt ist.
    
   - Klicken Sie auf die Registerkarte **"Listener",** und wählen Sie die Option **"Verfügbarkeitsgruppenlistener** erstellen" aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf 1433 fest (andere Ports werden für diese Option nicht unterstützt).
    
   - Klicken Sie auf **"Hinzufügen",** und geben Sie dann im Feld **"IPv4-Adresse"** Ihre bevorzugte virtuelle IP-Adresse an, und klicken Sie dann auf **"OK".**
    
   - Wählen Sie auf der Seite **"Anfängliche Datensynchronisierung auswählen"** die Option "Vollständig" aus, und geben Sie einen Ordner an, auf den die Replikate zugreifen können und für den das SQL Server von beiden Replikaten verwendete Dienstkonto über Schreibberechtigungen verfügt. Klicken Sie dann auf **Weiter**.
    
     Diese Dateifreigabe wird vorübergehend verwendet, wenn Sie die Datenbanken initialisieren. Wenn Es sich um große Datenbanken handelt, empfehlen wir, diese manuell zu initialisieren, falls ihre Netzwerkbandbreite nicht der Größe der Datenbanksicherungen entsprechen kann.
    
     - Überprüfen Sie auf der Seite "Überprüfung", ob alle Überprüfungen erfolgreich sind, und klicken Sie dann auf **"Weiter".**
    
   - Überprüfen Sie auf der Seite **"Zusammenfassung"** alle Einstellungen, und klicken Sie auf "Fertig stellen".
    
7. Erstellen Sie einen neuen Speicher, der den AG-Listener angibt.
    
   - Öffnen Sie den Topologie-Generator. Erweitern Sie in Ihrer Topologie **"Freigegebene Komponenten",** klicken Sie mit der rechten Maustaste auf **SQL Server Speicher,** und klicken Sie auf **"Neu SQL Server Store".**
    
   - Aktivieren Sie auf der Seite **"Neue SQL Store definieren"** zunächst das Kontrollkästchen **"Hohe Verfügbarkeit Einstellungen",** und stellen Sie dann sicher, dass SQL AlwaysOn-Verfügbarkeitsgruppen im Dropdownfeld angezeigt wird.
    
   - Geben Sie im **Feld SQL Server Verfügbarkeitslistener-FQDN** den FQDN des Listeners ein, den Sie beim Erstellen der Verfügbarkeitsgruppe erstellt haben.
    
   - Geben Sie im **Feld SQL Server FQDN** den FQDN des primären Knotens der AG ein, und klicken Sie dann auf **OK.**
    
8. Ordnen Sie die neue AlwaysOn-Verfügbarkeitsgruppe dem Front-End-Pool zu.
    
   - Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, der der AG zugeordnet werden soll, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
   - Wählen Sie unter **Zuordnungen** im **Feld SQL Server Store** die AG aus. Wählen Sie dieselbe Gruppe für alle anderen Datenbanken im Pool aus, die Sie in die AG verschieben möchten.
    
   - Wenn Sie sicher sind, dass alle erforderlichen Datenbanken auf AG festgelegt sind, klicken Sie auf **OK.**
    
9. Veröffentlichen Sie die Topologie. Klicken Sie im Menü **"Aktion"** auf **"Topologie"** und dann auf **"Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".**
    
10. Führen Sie einige abschließende Schritte aus, um sicherzustellen, dass sich die SQL Anmeldungen auf jedem Replikat in der AG befinden.
    
    - Öffnen Sie den Topologie-Generator, wählen Sie **"Topologie aus vorhandener Bereitstellung herunterladen" aus,** und klicken Sie auf **"OK".**
    
    - Erweitern Sie Skype for Business Server, erweitern Sie Ihre Topologie, und erweitern Sie **SQL Server Stores.** Klicken Sie mit der rechten Maustaste auf den SQL Speicher der neuen AG, und klicken Sie auf **"Eigenschaften bearbeiten".**
    
    - Ändern Sie unten auf der Seite im **Feld SQL Server FQDN** den Wert in den FQDN des Listeners der AG.
    
    - Veröffentlichen Sie die Topologie. Klicken Sie im Menü **"Aktion"** auf **"Topologie"** und dann auf **"Veröffentlichen".** Klicken Sie dann auf der Bestätigungsseite auf **"Weiter".** Warten Sie dann einige Minuten, bis die neue Topologie repliziert wurde.
    
    - Öffnen Sie SQL Server Management Studio, und navigieren Sie zur AG. Fail it over to a secondary replica.
    
    - Öffnen Sie Skype for Business Server Verwaltungsshell, und geben Sie das folgende Cmdlet ein, um die SQL Anmeldungen für dieses Replikat zu erstellen:
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - Wiederholen Sie die beiden vorherigen Schritte (Führen Sie ein Failover der Gruppe zu einem sekundären Replikat durch, und verwenden Sie sie  `Install-CsDatabase -Update` dann) für jedes Replikat in der Gruppe.
