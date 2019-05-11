---
title: Bereitstellen Sie Anrufqualität Dashboard für Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Zusammenfassung: Informationen Sie zu den Bereitstellungsprozess für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.'
ms.openlocfilehash: d048031ad7284b16f968d0f4641f0b31f9c984a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887160"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Bereitstellen Sie Anrufqualität Dashboard für Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zu den Bereitstellungsprozess für die Qualitätsdashboard aufrufen. Anruf Qualitätsdashboard ist ein Tool für Skype für Business Server.
  
## <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Anruf Quality Dashboard (CQD) besteht aus drei Hauptkomponenten:
  
- **Archivdatenbank**, in dem die Daten Quality of Experience (QoE) repliziert und gespeichert ist.
    
- **Cubes**, auf dem die Daten aus der QoE-Archivdatenbank für optimierte und schnellen Zugriff aggregiert werden.
    
- **Portal**, wobei Benutzer können auf einfache Weise Abfragen und Visualisieren von QoE-Daten.
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Der Setup-Prozess für QoE-Archiv umfasst die QoE-Archivdatenbank erstellen, Bereitstellen einer SQL Server gespeicherte Prozedur, die die Daten aus der Quelle QoE-Metriken Datenbank in QoE-Archivdatenbank verschoben werden und Einrichten von SQL Server Agent-Auftrags zum Ausführen der gespeicherten die Prozedur in einem regelmäßigen Intervall. 
  
Cube-Bereitstellung Ruft Informationen aus der Benutzer auf, in dem das QoE-Archiv befindet sich in den Cube bereitgestellt und richtet einen regulären SQL Server-Agent-Auftrag, der den Cube in regelmäßigen Abständen aktualisiert wird.
  
Portal installieren erstellt eine Repositorydatenbank, die die Zuordnung der CQD Benutzer Berichten oder Abfragen des Benutzers gespeichert werden. Klicken Sie dann wird eingerichtet, die das Dashboard ist, in dem Benutzer können finden Sie eine vordefinierte Reihe von Berichten als auch anpassen und Erstellen ihrer eigenen Abfragen, um Daten aus dem Cube visualisieren, IIS Web-Anwendung. Das Portal installieren erstellt zwei zusätzliche Webanwendungen, die für Benutzer zum programmgesteuerten Zugriff auf das Repository und den Cube APIs verfügbar macht. (Diese APIs werden intern von sowie das Dashboard verwendet.)
  

|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaften**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|Erforderliche Hardware und Software zu installieren.  <br/> |Nach der Konfiguration CQD entscheiden Sie, und wählen Sie einen SQL Server aus dem die Installation ausgeführt werden.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Abschnitt "Vor dem Installieren von Anforderungen", in der Bereitstellungsdokumentation.  <br/> |
|Installieren Sie CQD.  <br/> |Führen Sie die MSI-Datei nach der Bereitstellungsdokumentation.  <br/> |Zum Ausführen des Setups muss das Installieren von Konto werden ein Domänenbenutzer, der Mitglied der Gruppe der lokalen Administratoren ist und verfügen über Lesezugriff auf QoE-Metriken Datenbank auf dem Monitoring Server.  <br/> |"Konten und Bereitstellungsschritte" Abschnitte in der Bereitstellungsdokumentation.  <br/> |
|Gewähren des Benutzerzugriffs.  <br/> |Es wird empfohlen, für die Verwaltung der benutzerautorisierung-Portal, mithilfe der URL-Autorisierung in IIS 7.0 eingeführt wurde. Weitere Informationen finden Sie unter [Grundlegendes zu IIS 7.0-URL-Autorisierung](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Verwalten des Benutzerzugriffs für den Abschnitt Portal in der Bereitstellungsdokumentation.  <br/> |
|Optional: Geben Sie Zuordnungsinformationen Subnetz.  <br/> |Füllen Sie auf Netzwerk- und Erstellen von Zuordnungstabellen in QoE-Archivdatenbank.  <br/> |Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.  <br/> |Abschnitt "Bereitstellung Subnetzinformationen", in der Dokumentation für die Benutzer.  <br/> |
   


Bereitstellung von Anrufqualität Dashboard umfasst Einrichten der Infrastruktur und Installieren der Software. Das folgende Verfahren beschreibt den Prozess.
  
## <a name="deployment-steps"></a>Bereitstellungsschritte

1. Kopieren Sie die CallQualityDashboard.msi auf dem Computer, auf dem die Archiv Datenbankkomponente des CQD ist installiert werden soll (Dies ist der Computer, auf SQL Server installiert ist). 
    
2. Führen Sie die MSI-Datei (Windows Sie werden aufgefordert, mit Administratorrechten ausgeführt werden, dazu). 
    
3. Akzeptieren Sie den Endbenutzer-Lizenzvertrag.
    
4. Wählen Sie den Zielordner, in dem Dateien im Zusammenhang mit Anrufqualität Dashboardkomponenten befinden oder den Standardspeicherort akzeptieren.
    
5. Wählen Sie alle Features aus.
    
6. Geben Sie auf der Seite QoE-Archive-Konfiguration die folgenden Informationen ein:
    
   - **QoE-Metriken SQLServer:** SQL Server-Instanznamen, auf dem sich die QoE-Metriken DB befindet (Dies ist die Datenquelle).
    
   - **QoE-Archiv SQL Server-Name:** Dies ist nur-Lese-Feld und auf den vollqualifizierten Domänennamen des lokalen Computers behoben. Archiv DB kann nur auf dem lokalen Computer installiert werden.
    
   - **QoE-Archiv SQL Server-Instanz:** Eine lokale SQL Server-Instanznamen für wobei ist das Archiv DB erstellt werden soll. Um eine Standardinstanz von SQL Server verwenden, lassen Sie dieses Feld leer. Um eine benannte Instanz von SQL Server verwenden, geben Sie den Namen der Instanz (z. B. Name nach der "\").
    
   - **QoE-Archivdatenbank:** Diese Option ist standardmäßig auf "Neue Datenbank erstellen" festgelegt. Da Archiv DB Upgrade nicht unterstützt wird, ist die einzige Situation, unter der die Option "Vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Archivdatenbank die Schema der Build installiert werden hat.
    
   - **Datenbank Dateiverzeichnis:** Der Pfad, in dem die Datenbankdateien (MDF- und LDF) für die Archivierung DB platziert werden soll. Dies sollte auf einem Laufwerk (HDD2 in die empfohlene Hardwarekonfiguration) getrennt vom Betriebssystem sein. Beachten Sie, dass seit die Dateinamen in der Installation behoben werden, um alle Konflikte zu vermeiden empfohlen wird, dass ein leeres Verzeichnis ohne Dateien verwendet werden.
    
   - **Verwenden Sie mehrere Partitionen:** Die Standardeinstellung von "Mehrere Partition", die Business Intelligence-Edition oder Enterprise Edition von SQL Server erforderlich sind. Wählen Sie "Einzelpartition" Option aus, für die Standard Edition. Beachten Sie, dass Cube Verarbeitung Leistung beeinträchtigt werden kann, wenn das Einzelpartition verwendet wird.
    
     > [!NOTE]
     > Die Auswahl für Verwenden mehrerer Partitionen Option kann nicht geändert werden, wenn Setup abgeschlossen ist. Um es zu ändern, der Cube Feature benötigt, erste deinstalliert und anschließend erneut installiert, mit der Option "Ändern" in der Systemsteuerung. 
  
   - **Partitionieren Dateiverzeichnis:** Der Pfad, in dem die Partitionen für die QoE-Archivdatenbank platziert werden soll. Dies sollte (HDD3 in die empfohlene Hardwarekonfiguration) getrennt vom OS Laufwerk und SQL-Datenbank Protokolllaufwerk Dateien auf einem Laufwerk sein. Beachten Sie, dass seit die Dateinamen in der Installation behoben werden, um alle Konflikte zu vermeiden empfohlen wird, dass ein leeres Verzeichnis ohne Dateien verwendet werden.
    
   - **SQL-Agent Job-Benutzer - Benutzernamen &amp; Kennwort:** Dienstkontoname Domäne und das Kennwort (maskiert), mit der der "QoE-Archivdaten" Schritt des Auftrags für SQL Server-Agent ausgeführt (die zum Abrufen von Daten aus der Datenbank der QoE-Metriken in Archiv DB, damit dieses Konto Lesezugriff auf den QoE-Metriken DB, benötigen die gespeicherte Prozedur ausgeführt wird  wie im Abschnitt Konten angegeben. Dieses Konto muss außerdem ein Benutzername in der QoE-Archiv SQL Server-Instanz haben).
    
     > [!NOTE]
     > Das Konto, das SQL Server-Instanz unter, wie beispielsweise NT-SERVICE\MSSQLSERVER ausgeführt wird benötigen Zugriffsberechtigungen für die Verzeichnisse obigen für die Installation erfolgreich ausgeführt werden kann. Weitere Informationen hierzu finden Sie unter [Konfigurieren Dateisystemberechtigungen für den Zugriff auf das Datenbankmodul](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Beim nächsten klicken, wird das Installationsprogramm Prüfungen und Untersuchung Bericht durchführen, wenn Probleme aufgetreten sind. Wenn alle vorausgesetzte Überprüfungen Durchgang gelangen das Installationsprogramm auf der Seite Cubekonfiguration. 
    
    > [!NOTE]
    > Wenn das Installationsprogramm eine Warnmeldung angezeigt, die der SQL Server-Agent-Dienst für QoE-Archiv SQL Server-Instanz derzeit nicht ausgeführt wird wird, kann die Installation fortgesetzt werden, aber Post-Installation stellen Sie sicher, dass SQL-Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf Automatische, sodass die geplante Aufgabe ausgeführt wird. 
  
8. Geben Sie auf der Seite Cubekonfiguration die folgenden Informationen ein:
    
   - **QoE-Archiv SQL Server-Name:** Dies ist nur-Lese-Feld und auf den vollqualifizierten Domänennamen des lokalen Computers behoben. Cube kann nur auf dem Computer installiert werden, sind QoE-Archivdatenbank (Notiz. Cube selbst kann auf einem Remotecomputer installiert werden. Siehe unten)
    
   - **QoE-Archiv SQL Server-Instanz:** Name der SQL Server-Instanz auf dem sich die QoE-Archiv-DB befindet. Um eine Standardinstanz von SQL Server anzugeben, lassen Sie dieses Feld leer. Um eine benannte Instanz von SQL Server anzugeben, geben Sie den Instanznamen (z. B. Name nach der "\"). Wenn QoE-Archiv-Komponente für die Installation ausgewählt wurde, wird dieses Feld bereits ausgefüllte mit dem Wert, der auf der Seite Konfiguration der QoE-Archiv bereitgestellt werden.
    
   - **-Cubes in Analysis-Server:** SQL Server Analysis Services-Instanznamen für wobei ist der Cube erstellt werden soll. Dies kann einem anderen Computer aber der installierende Benutzer muss ein Mitglied der Zielinstanz von SQL Server Analysis Services-Server-Administratoren sein.
    
     > [!NOTE]
     >  Weitere Informationen zum Konfigurieren von Analysis Services-Server-Administrator Berechtigungen finden Sie unter [Server-Administrator-Berechtigungen erteilen (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **Verwenden Sie mehrere Partitionen:** Die Standardeinstellung von "Mehrere Partition", die Business Intelligence-Edition oder Enterprise Edition von SQL Server erforderlich sind. Wählen Sie "Einzelpartition" Option aus, für die Standard Edition. Beachten Sie, dass Cube Verarbeitung Leistung beeinträchtigt werden kann, wenn das Einzelpartition verwendet wird.
    
     > [!NOTE]
     >  Die Auswahl für Verwenden mehrerer Partitionen Option kann nicht geändert werden, wenn Setup abgeschlossen ist. Um es zu ändern, der Cube Feature benötigt, erste deinstalliert und anschließend erneut installiert, mit der Option "Ändern" in der Systemsteuerung.
  
   - **Cube User - Benutzername &amp; Kennwort:** Dienstkontoname Domäne und das Kennwort (maskiert), die die Cubes Verarbeitung auslöst. Wenn QoE-Archiv-Komponente für die Installation ausgewählt wurde, in diesem Feld mit dem Wert auf der Seite Konfiguration der Archivierung für den SQL-Agent-Auftrag Benutzer bereits ausgefüllte werden, aber es wird empfohlen, ein anderes Domänenkonto Service angeben, sodass Setup gewähren kann die mindestens erforderliche Berechtigung hinzu.
    
9. Wenn Sie auf Weiter klicken, wird eine weitere runde der Überprüfung durchgeführt, und alle Problem wird gemeldet werden. Nach dem erfolgreichen Abschluss der Validierung gelangen das Installationsprogramm auf der Seite Portal-Konfiguration. 
    
10. Geben Sie auf der Seite Portal-Konfiguration die folgenden Informationen ein:
    
    - **QoE-Archiv SQLServer:** Name der SQL Server-Instanz auf dem sich die QoE-Archivdatenbank befindet. Beachten Sie, dass im Gegensatz zu der Seite QoE-Archiv-Konfiguration und der Seite Cubekonfiguration, den Namen des Computers nicht behoben und bereitgestellt werden muss. Wenn QoE-Archiv-Komponente für die Installation ausgewählt wurde, wird dieses Feld bereits ausgefüllte mit dem Wert, der auf der Seite Konfiguration der QoE-Archiv bereitgestellt werden.
    
    - **-Cubes in Analysis-Server:** SQL Server Analysis Services-Instanznamen für, in der Cube gespeichert ist. Wenn der Cube-Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem Wert auf der Seite Cubekonfiguration bereits ausgefüllte sein.
    
    - **Repository SQLServer:** Name der SQL Server-Instanz, in dem die Repositorydatenbank ist erstellt werden soll. Wenn der Name des SQL Server-Instanz für, in die QoE-Archivdatenbank gespeichert ist weiter oben in der Setup (in anderen Komponenten) bereitgestellt wurde, wird dieses Feld bereits ausgefüllte, mit dem Namen der QoE-Archiv DB SQL Server-Instanz sein. Dies kann eine beliebige SQL Server-Instanz sein.
    
    - **Repositorydatenbank:** Die Option ist standardmäßig auf "Neue Datenbank erstellen" festgelegt. Da Repository DB Upgrade nicht unterstützt wird, ist die einzige Situation, unter der die Option "Vorhandene Datenbank verwenden" verwendet werden kann, wenn der vorhandenen Repository DB die Schema der Build installiert werden hat.
    
    - **IIS-Anwendungspool-User - Benutzername &amp; Kennwort:** Das Konto, dem unter IIS-Anwendungspool ausgeführt werden soll. Die Felder Benutzername und Kennwort werden abgeblendet, wenn integrierten Systemkonten ausgewählt sind. Diese Felder werden nur aktiviert werden, wenn "Andere" aus der Dropdownliste ausgewählt ist, damit der Benutzer die Domäne Service-Kontoinformationen eingeben kann.
    
11. Wenn Sie auf Weiter klicken, wird die endgültige Rundung der Überprüfung ausgeführt, um sicherzustellen, dass die SQL Server-Instanzen mithilfe der Anmeldeinformationen und, dass IIS auf dem Computer verfügbar ist. Nach dem erfolgreichen Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortgesetzt. 
    
Wenn das Installationsprogramm abgeschlossen ist, wird sehr wahrscheinlich der Auftrag SQL Server-Agent ausgeführt wird, wie folgt das Laden des QoE-Daten und die Cubeverarbeitung sein. In Abhängigkeit vom Umfang des Datenteils QoE wird das Portal nicht Daten für die Anzeige von noch verfügbar sind. Um den Status der Cubeverarbeitung und Laden von Daten zu überprüfen, wechseln Sie zur `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Beachten Sie, dass die URL für das Überprüfen des Status des Download Cube Groß-/Kleinschreibung beachtet wird. Bei Eingabe von 'Health' die URL nicht funktionsfähig ist. Geben Sie am Ende der URL mit dem Großbuchstaben h ' Health' 
  
Ausführliches Protokollnachrichten werden angezeigt, wenn Debug-Modus aktiviert ist. Um Debug-Modus aktivieren möchten, besuchen Sie **%SystemDrive%\Programme\Microsoft Files\Skype für Business 2015 CQD\QoEDataService\web.config**, und aktualisieren Sie die folgende Zeile, sodass der Wert auf **True**festgelegt ist:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Die Hauptseite Portal ist auf den über `http://<machinename>/CQD`. 
## <a name="managing-user-access-for-the-portal"></a>Verwalten des Benutzerzugriffs für das Portal

Es wird empfohlen, für die Verwaltung der benutzerautorisierung-Portal, mithilfe der URL-Autorisierung in IIS 7.0 eingeführt wurde. Weitere Informationen zur Sicherheit von IIS finden Sie unter [Grundlegendes zu IIS 7.0-URL-Autorisierung ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Jede Web Site oder Web-Anwendung erben die Standard-URL-Autorisierung konfiguriert für die gesamte IIS, wobei es sich üblicherweise "Alle Benutzer zulassen". Wenn Zugriff auf das Portal restriktiver sein muss, können dann Administratoren Zugriff auf nur die bestimmten Gruppe von Benutzern gewähren durch Bearbeiten der "Autorisierungsregeln".
  
![Anrufqualität bereitstellen – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> Das Symbol Autorisierungsregeln darf nicht mit ".NET Authorization" unter dem ASP.NET-Bereich, einen anderen Autorisierungsmechanismus verwechselt werden. 
  
Administratoren sollten die geerbte "alle Benutzer zulassen" Regel zuerst entfernen. Dadurch wird verhindert, dass keine nicht autorisierter Benutzer den Zugriff auf das Portal.
  
![CQD bereitstellen](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Administratoren sollten Sie als Nächstes Hinzufügen neuer Regeln auf zulassen und bestimmten Benutzern die Berechtigung, um auf das Portal zugreifen. Es wird empfohlen, eine lokale Gruppe namens "CQDPortalUsers" erstellt werden, um die Benutzer zu verwalten.
  
![Anrufqualitäts-Dashboard bereitstellen](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Die Konfigurationsdetails werden in der Datei web.config befindet sich unter dem Portal physikalische Verzeichnis gespeichert.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

Im nächste Schritt wird das Dashboard, der die CQD konfigurieren. Nachdem der Benutzer von IIS authentifiziert werden, müssen sie über die Datei im Verzeichnis CQD berechtigt, um Portal Web-Inhalt zugreifen. Es ist möglich, ändern Sie die ACLs über die Sicherheitsregisterkarte CQD Directory-Eigenschaften, um einzelne Benutzer oder Gruppen hinzuzufügen. wird jedoch empfohlen, die Dateiberechtigungen unverändert lassen. Ändern Sie stattdessen die IIS-Einstellung, um die IIS-Arbeitsprozess verwenden, um das Verzeichnis CQD zugreifen, unabhängig davon, das welche Benutzer authentifiziert wird. 
  
> [!IMPORTANT]
> Es ist wichtig, nur diese Einstellung für die Anwendung CQD und nicht für die zwei API-Anwendungen ändern: QoEDataService und QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Konfigurieren von Zugriff auf die Datei für die CQD (Dashboard)

1. Öffnen Sie den Konfigurations-Editor CQD.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Klicken Sie im Abschnitt wählen Sie **system.webServer/serverRuntime**.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Ändern Sie AuthenticatedUserOverride in **UseWorkerProcessUser**.
    
     ![Anrufqualitäts-Dashboard bereitstellen – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Klicken Sie auf **Übernehmen** auf der rechten Seite der Seite.
    
## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-cqd-shows-no-data-after-deployment"></a>Die CQD zeigt keine Daten nach der Bereitstellung

Sie möglicherweise die folgende Fehlermeldung angezeigt:

*Es konnte nicht die Abfrage ausführen, während es für den Cube ausgeführt wird. Verwenden Sie den Abfrage-Editor zum Ändern der Abfrage und beheben Sie etwaige Probleme. Stellen Sie außerdem sicher, dass der Cube zugegriffen werden kann.*

Dies bedeutet, dass der Cube in SQL Server Analysis Services verarbeitet werden muss, bevor in CQD verwendet wird. Sie können diese Probleme beheben, indem Sie folgende Schritte:

1. Öffnen Sie SQL Management Studio, und wählen Sie **Analysis Services**aus.

2. Erweitern Sie die **QoECube** -Objekt, wählen Sie **QoE-Metrik**, mit der rechten Maustaste, und wählen Sie dann auf **Durchsuchen**. 

    Wenn dies leer Browser zurückgegeben wird, noch nicht der Cube wurde fahren Sie noch.

3. Mit der rechten Maustaste **QoE-Metrik** Angain, und wählen Sie **Prozess**.

4. Nach Abschluss der Verarbeitung mit der rechten Maustaste erneut auf des Objekts, und wählen Sie **Durchsuchen** aus, zu bestätigen, dass die Browserseite nun Daten zeigt. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Benutzer haben Probleme beim Anmelden, weil Installer nicht die richtigen Einstellungen in IIS erstellt.

In seltenen Fällen kann das Installationsprogramm die richtigen Einstellungen in IIS zu erstellen. Manuelle Änderung ist erforderlich, um Benutzer zur Anmeldung bei der CQD zu ermöglichen. Wenn Benutzer Probleme beim Anmelden haben, gehen Sie folgendermaßen vor:
  
1. Öffnen Sie den IIS-Manager, und navigieren Sie auf Standardwebsite.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Klicken Sie auf "Authentifizierung". Wenn die "Anonyme Authentifizierung", "ASP.NET Impersonation", "Formularauthentifizierung" und "Windows-Authentifizierung" die nachfolgend aufgeführten Einstellungen nicht übereinstimmen, auch manuell ändern Sie, um die folgenden Einstellungen übereinstimmen. Alle anderen Authentifizierungsmechanismen sollte deaktiviert werden.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Klicken Sie für "Windows-Authentifizierung" auf der rechten Seite auf Erweiterte Einstellungen.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. "Erweiterten Schutz" auf Accept festgelegt, und aktivieren Sie das Kontrollkästchen "Enable-Kernelmodusauthentifizierung".
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Wiederholen Sie die obigen Schritte für jede die Einträge "CQD", "QoEDataService" und "QoERepositoryService" unter "Default Web Site" ein.
    
Für HTTP und HTTPS Port Bindungen erstellt der Installer auf die Standard-Portnummern (Port 80 für HTTP) und Port 443 für HTTPS Port Bindungen. Liegt eine andere Website auf dem Computer, der diese Bindungen verwendet, es ist ein Konflikt und das Verhalten von IIS kann nicht vorhergesagt werden. Die beste Möglichkeit zum Vermeiden dieses Problems ist, um sicherzustellen, dass keine anderen Websites vor der Installation von CQD Ports 80 und 443 zugeordnet sind. 
  
So aktivieren SSL/TLS in IIS und erzwingen, dass Benutzer eine Verbindung herstellen über secure HTTPS anstelle von HTTP:
  
1. Konfigurieren von Secure Sockets Layer in IIS, finden Sie unter [Konfigurieren von Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Ersetzen Sie abschließend `http` mit `https`.
    
2. Anweisungen zum Aktivieren von TLS in der SQL Server-Verbindungen finden Sie unter [Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe von Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).
    
## <a name="cube-sync-fails"></a>Fehler bei der Synchronisierung Cube

QoEMetrics kann einige ungültige Datensätze basierend auf Endbenutzer Uhren enthalten. Wenn die Zeit skew größer als 60 Jahre ist, schlägt der Import Cube fehl.
  
 Überprüfen Sie die Funktionen Min und Max StartTime/EndTime nachstehend verwenden. Suchen und Löschen von Datensätzen in der Zukunft ganz vergangenen und sehr weit entfernt, können sie ignoriert, und sie werden die Sync-Prozesse unterteilen.
  
- Wählen Sie MIN(StartTime) aus CqdPartitionedStreamView
    
- Wählen Sie MAX(StartTime) aus CqdPartitionedStreamView
    
- Wählen Sie MIN(EndTime) aus CqdPartitionedStreamView
    
- Wählen Sie MAX(EndTime) aus CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Aufgaben nach der Installation

### <a name="importing-buildings-and-networks"></a>Importieren von Gebäude und Netzwerke

Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:
  
1. Definieren Sie zum Erstellen von Inhaltstypen (empfohlen)
    
2. Definieren Sie zum Erstellen von den Besitz Typen (empfohlen)
    
3. Definieren von Netzwerk-Typen (dringend empfohlen)
    
4. Importieren von Gebäude (empfohlen)
    
5. Import-Subnetze (empfohlen)
    
### <a name="define-building-types"></a>Erstellen von Typen definieren

Erstellen von Typen werden verwendet, um die verschiedenen Gebäuden Definitionen oder Typen innerhalb Ihrer Organisation beschrieben. 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Hauptsitz
    
- Zweigstellen
    
- Sofern Speicherort
    
  **Beispiel-SQL-Syntax**
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Der Parameter BuildingTypeId und BuildingTypeDesc sind erforderlich.
  
### <a name="define-building-ownership-types"></a>Erstellen von Besitz Typen definieren

Gesamtbetriebskosten Typen dienen zum Besitzer Vs geleaste Ressourcen zu unterscheiden.
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Contoso geleaste nicht-RE&amp;F
    
- Contoso geleaste RE&amp;F
    
- Contoso gehören
    
- Niederlassung geleaste
    
  **Beispiel-SQL-Syntax**
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

Der Parameter OwnershipTypeId und OwnershipTypeDesc sind erforderlich. 
  
### <a name="define-network-names"></a>Definieren von Netzwerknamen

Netzwerktypen dienen zum Beschreiben der verschiedenen Types von Netzwerken innerhalb der Organisation. Dies gibt Ihnen die Möglichkeit zu filtern (oder herauszufiltern) bestimmte Typen.
  
> [!NOTE]
> Es wird dringend empfohlen, Netzwerknamen definieren, aber es ist optional. Wenn Sie nicht Netzwerknamen definieren möchten, sicherstellen Sie, dass der einzelnen CqdNetwork Eintrag einer BuildingId 0 verfügt. 
  
Beispiele
  
- VPN
    
- Labor
    
  **Beispiel-SQL-Syntax**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Die Parameter NetworkNameID und Netzwerkname sind erforderlich, der NetworkType-Parameter ist optional, wird jedoch empfohlen.
  
### <a name="import-buildings"></a>Import Gebäude

Importieren von Gebäude können Sie bestimmte Insights (schlechter Anrufe pro erstellen WiFi/kabelgebundene usw.). erstellen möchten. 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Vor dem Importieren sollte eine neue erstellen Sie bereits eine vordefinierte BuildingKey identifiziert haben. Klicken Sie dazu Problem des "MAX(BuildingKey) aus CqdBuilding wählen Sie" SQL-Befehls zum Identifizieren des aktuellen Werts und das Ergebnis 1 hinzuzufügen.
  
 **Beispiel-SQL-Syntax**
  
```
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

Die BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId-Parameter sind erforderlich, die anderen Parameter sind optional.
  
### <a name="import-subnets"></a>Importieren von Subnetzen

Importieren von Gebäude können Sie bestimmte Insights (schlechter Anrufe pro erstellen WiFi/kabelgebundene usw.). erstellen möchten. 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Importieren Sie Subnetze und ordnen sie Sie die Gebäude im letzten Schritt importiert. Wenn Sie nicht Netzwerkname auffüllen, stellen Sie sicher, dass für jeden Eintrag in dieser Tabelle ein NetworkNameID 0 verwendet.
  
 **Beispiel-SQL-Syntax**
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

Das Netzwerk und UpdatedDate-Parameter sind erforderlich, die anderen Parameter sind optional.
  
### <a name="optional-bssid"></a>Optional: BSSID

Auffüllen BSSID Informationen erhalten Sie zusätzliche WiFi Stream Korrelation von Controller oder Radio. Dies ist zusätzlich zum Filtern nach dem Erstellen oder Subnetz. 
  
 **Beispiel-SQL-Syntax**
  
```
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**CqdBssidTable-Details**

|**Siehe CQD**|**CQDBssid-Tabelle**|**Beispiel-Eingaben**|
|:-----|:-----|:-----|
|AP NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (Sie müssen den mit Trennzeichen versehenen Fformat verwenden)  <br/> |
|Controller  <br/> |Gebäude  <br/> |Aruba AP 7  <br/> |
|Gerät  <br/> |ess  <br/> |Controller1  <br/> |
|Radio  <br/> |phy  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Verarbeitung der importierten Daten

Standardmäßig nach dem Erstellen von-Netzwerk Daten importieren gilt es nur für Datensätze, die nach diesem Zeitpunkt Punkt generiert. 
  
Um die vorherigen Datensätze mit diesen neuen Daten zu markieren, müssen Sie die gespeicherte CqdUpdateBuilding eine Ereignisprozedur ausgeführt werden wie folgt: 
  
Geben sie das Datum des ersten Datensatzes (identifizieren, die mit dem Befehl Select MIN(StartTime) aus CqdPartitionedStreamView SQL), ein Enddatum des morgen, und klicken Sie dann auf NULL für die letzten beiden Werte.
  
Sobald die Daten Streamdaten zugeordnet ist, muss der Cube SSIS alle Datensätze erneut zu verarbeiten. Dies gilt auch beim Bulk BSSID/Internetdienstanbieter Daten hinzufügen. Stellen Sie sicher, dass "Prozess Full" ausgewählt ist.
  

