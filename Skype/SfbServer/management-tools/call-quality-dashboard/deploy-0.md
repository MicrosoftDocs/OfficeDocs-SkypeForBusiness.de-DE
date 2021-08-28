---
title: Bereitstellen des Anrufqualitäts-Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Zusammenfassung: Erfahren Sie mehr über den Bereitstellungsprozess für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: af43865c76b565ac126d80193b3b32b0bd870260
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596569"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Bereitstellen des Anrufqualitäts-Dashboards für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bereitstellungsprozess für das Anrufqualitäts-Dashboard. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server.
  
## <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Das Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) besteht aus drei Hauptkomponenten:
  
- **Archivdatenbank,** in der die QoE-Daten (Quality of Experience) repliziert und gespeichert werden.
    
- **Cube,** in dem Daten aus der QoE-Archivdatenbank für optimierten und schnellen Zugriff aggregiert werden.
    
- **Portal,** in dem Benutzer QoE-Daten einfach abfragen und visualisieren können.
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Der Einrichtungsprozess für das QoE-Archiv umfasst das Erstellen der QoE-Archivdatenbank, das Bereitstellen einer SQL Server gespeicherten Prozedur, mit der die Daten aus der QoE-Quellmetrikendatenbank in die QoE-Archivdatenbank verschoben werden, und das Einrichten des SQL Server Agent-Auftrags, um die gespeicherte Prozedur in einem regelmäßigen Intervall auszuführen. 
  
Die Cubebereitstellung ruft Informationen vom Benutzer ab, wo sich das QoE-Archiv befindet, stellt den Cube bereit und richtet einen regulären SQL Server Agent-Auftrag ein, der den Cube in einem regelmäßigen Intervall aktualisiert.
  
Die Portalinstallation erstellt eine Repository-Datenbank, in der die Zuordnung von CQD-Benutzern zu den Berichten/Abfragen jedes Benutzers gespeichert wird. Anschließend wird eine IIS-Webanwendung eingerichtet, die das Dashboard ist, in dem Benutzer eine vordefinierte Gruppe von Berichten sehen sowie ihre eigenen Abfragen anpassen und erstellen können, um Daten aus dem Cube zu visualisieren. Die Portalinstallation erstellt zwei zusätzliche Webanwendungen, die APIs für Benutzer verfügbar machen, um programmgesteuert auf das Repository und den Cube zuzugreifen. (Diese APIs werden auch intern vom Dashboard verwendet.)
  

|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaft**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|Installieren Sie erforderliche Hardware und Software.  <br/> |Entscheiden Sie sich für die CQD-Konfiguration, und wählen Sie einen SQL Server aus, aus dem die Installation ausgeführt werden soll.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Abschnitt "Voraussetzungen für die Vorinstallation" in der Bereitstellungsdokumentation.  <br/> |
|Installieren Sie CQD.  <br/> |Führen Sie die MSI-Datei nach dem Bereitstellungsdokument aus.  <br/> |Zum Ausführen des Setups muss das Installationskonto ein Domänenbenutzer sein, der Mitglied der lokalen Administratorgruppe ist und Lesezugriff auf die QoE-Metrikdatenbank auf dem Überwachungsserver hat.  <br/> |Abschnitte "Konten und Bereitstellungsschritte" in der Bereitstellungsdokumentation.  <br/> |
|Gewähren des Benutzerzugriffs.  <br/> |Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7.0 eingeführt wurde. Weitere Informationen finden Sie unter [Grundlegendes zur IIS 7.0-URL-Autorisierung.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Verwalten des Benutzerzugriffs für den Portal-Abschnitt in der Bereitstellungsdokumentation.  <br/> |
|Optional: Geben Sie Subnetzzuordnungsinformationen an.  <br/> |Füllen Sie Netzwerk- und Gebäudezuordnungstabellen in der QoE-Archivdatenbank auf.  <br/> |Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.  <br/> |Abschnitt "Bereitstellen von Subnetzinformationen" in der Benutzerdokumentation.  <br/> |
   


Die Bereitstellung des Anrufqualitätsdashboards umfasst das Einrichten der Infrastruktur und die Installation der Software. Im folgenden Verfahren wird der Prozess beschrieben.
  
## <a name="deployment-steps"></a>Bereitstellungsschritte

1. Kopieren Sie die CallQualityDashboard.msi auf den Computer, auf dem die Archivdatenbankkomponente von CQD installiert werden soll (dies ist der Computer, auf dem SQL Server installiert ist). 
    
2. Führen Sie die MSI-Datei aus (Windows wird aufgefordert, mit Administratorrechten auszuführen). 
    
3. Akzeptieren Sie die Lizenzbedingungen.
    
4. Wählen Sie den Zielordner aus, in dem sich Dateien im Zusammenhang mit den Komponenten des Anrufqualitätsdashboards befinden, oder akzeptieren Sie den Standardspeicherort.
    
5. Wählen Sie alle Features aus.
    
6. Geben Sie auf der Seite "QoE-Archivkonfiguration" die folgenden Informationen an:
    
   - **QoE Metrics SQL Server:** SQL Server Instanzname für den Speicherort der QoE-Metrik-DB (dies ist die Datenquelle).
    
   - **QoE-Archiv SQL Server Name:** Dieses Feld ist schreibgeschützt und wird auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt. Archiv-DB kann nur auf dem lokalen Computer installiert werden.
    
   - **QoE-Archiv SQL Server Instanz:** Ein lokaler SQL Server Instanzname, für den die Archiv-DB erstellt werden soll. Wenn Sie eine Standardinstanz SQL Server verwenden möchten, lassen Sie dieses Feld leer. Um einen benannten SQL Server Instanz zu verwenden, geben Sie den Instanznamen an (z. B. den Namen nach dem " \" ).
    
   - **QoE-Archivdatenbank:** Standardmäßig ist diese Option auf "Neue Datenbank erstellen" festgelegt. Da das Archiv-DB-Upgrade nicht unterstützt wird, kann die Option "Vorhandene Datenbank verwenden" nur verwendet werden, wenn die vorhandene Archivdatenbank das gleiche Schema wie der zu installierende Build aufweist.
    
   - **Datenbankdateiverzeichnis:** Pfad zum Speicherort der Datenbankdateien (MDF und LDF) für die Archiv-DB. Dies sollte sich auf einem Laufwerk (HDD2 in der empfohlenen Hardwarekonfiguration) unabhängig vom Betriebssystem bef?tigt haben. Da die Dateinamen in der Installation behoben sind, empfiehlt es sich, ein leeres Verzeichnis ohne Dateien zu verwenden, um potenzielle Konflikte zu vermeiden.
    
   - **Verwenden Sie mehrere Partitionen:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server. Wählen Sie für die Standard edition die Option "Einzelne Partition" aus. Beachten Sie, dass die Cubeverarbeitungsleistung möglicherweise beeinträchtigt wird, wenn eine einzelne Partition verwendet wird.
    
     > [!NOTE]
     > Die Auswahl für die Option "Mehrere Partitionen verwenden" kann nach Abschluss des Setups nicht mehr geändert werden. Um es zu ändern, muss das Cube-Feature zuerst deinstalliert und dann mit der Option "Ändern" in der Systemsteuerung neu installiert werden. 
  
   - **Partitionsdateiverzeichnis:** Pfad zum Speicherort der Partitionen für die QoE-Archivdatenbank. Dies sollte sich auf einem Laufwerk (HDD3 in der empfohlenen Hardwarekonfiguration) befinden, das vom Betriebssystemlaufwerk und SQL Datenbankprotokolldateien getrennt ist. Da die Dateinamen in der Installation behoben sind, empfiehlt es sich, ein leeres Verzeichnis ohne Dateien zu verwenden, um potenzielle Konflikte zu vermeiden.
    
   - **SQL Agent-Auftragsbenutzer – Benutzername &amp; Kennwort:** Name und Kennwort des Domänendienstkontos (maskiert), die zum Ausführen des Schritts "QoE-Archivdaten" des SQL Server Agent-Auftrags verwendet werden (wodurch die gespeicherte Prozedur ausgeführt wird, um Daten von QoE Metrics DB in Archive DB abzurufen. Dieses Konto muss also über Lesezugriff auf QoE Metrics DB verfügen, wie im Abschnitt "Konten" angegeben. Dieses Konto muss sich auch im QoE-Archiv SQL Server Instanz anmelden).
    
     > [!NOTE]
     > Das Konto, unter dem die SQL Server Instanz ausgeführt wird, z. B. NT SERVICE\MSSQLSERVER, muss über Zugriff/Berechtigung auf die oben angegebenen Verzeichnisse verfügen, damit die Installation erfolgreich ausgeführt werden kann. Ausführliche Informationen finden Sie unter [Konfigurieren von Dateisystemberechtigungen für Datenbank-Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. Beim Klicken auf das nächste Element führt das Installationsprogramm die erforderlichen Überprüfungen durch und meldet, ob Probleme auftreten. Wenn alle erforderlichen Überprüfungen erfolgreich sind, wechselt das Installationsprogramm zur Seite "Cubekonfiguration". 
    
    > [!NOTE]
    > Wenn das Installationsprogramm eine Warnmeldung anzeigt, dass der SQL Server-Agent-Dienst für das QoE-Archiv SQL Server Instanz derzeit nicht ausgeführt wird, kann die Installation fortgesetzt werden. Stellen Sie nach der Installation jedoch sicher, dass SQL Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf "Automatisch" fest, damit der geplante Auftrag ausgeführt wird. 
  
8. Geben Sie auf der Seite "Cubekonfiguration" die folgenden Informationen an:
    
   - **QoE-Archiv SQL Server Name:** Dieses Feld ist schreibgeschützt und wird auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt. Cube kann nur auf dem Computer installiert werden, der über eine QoE-Archivdatenbank verfügt (Hinweis. Cube selbst kann auf einem Remotecomputer installiert werden. Siehe unten)
    
   - **QoE-Archiv SQL Server Instanz:** SQL Server Instanzname, in dem sich die QoE-Archiv-DB befindet. Wenn Sie eine Standardinstanz SQL Server angeben möchten, lassen Sie dieses Feld leer. Um einen benannten SQL Server Instanz anzugeben, geben Sie den Instanznamen ein (z. B. den Namen nach dem " \" ). Wenn die QoE-Archivkomponente für die Installation ausgewählt wurde, wird dieses Feld vorab mit dem Auffüllen des Werts auf der QoE-Archivkonfigurationsseite ausgefüllt.
    
   - **Cube Analysis Server:** SQL Server Analysis Service-Instanzname für den Ort, an dem der Cube erstellt werden soll. Dies kann ein anderer Computer sein, aber der installierende Benutzer muss Ein Mitglied der Serveradministratoren des Ziels SQL Server Analysis Service-Instanz sein.
    
     > [!NOTE]
     >  Weitere Informationen zum Konfigurieren von Analysis Services Server-Administratorberechtigungen finden Sie unter [Erteilen von Serveradministratorberechtigungen (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **Verwenden Sie mehrere Partitionen:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server. Wählen Sie für die Standard edition die Option "Einzelne Partition" aus. Beachten Sie, dass die Cubeverarbeitungsleistung möglicherweise beeinträchtigt wird, wenn eine einzelne Partition verwendet wird.
    
     > [!NOTE]
     >  Die Auswahl für die Option "Mehrere Partitionen verwenden" kann nach Abschluss des Setups nicht mehr geändert werden. Um es zu ändern, muss das Cube-Feature zuerst deinstalliert und dann mit der Option "Ändern" in der Systemsteuerung neu installiert werden.
  
   - **Cube-Benutzer – Benutzername &amp; Kennwort:** Name und Kennwort des Domänendienstkontos (maskiert), die die Cubeverarbeitung auslösen. Wenn die QoE-Archivkomponente für die Installation ausgewählt wurde, wird dieses Feld vorab mit dem Wert aufgefüllt, der auf der Seite "Archivkonfiguration" für den SQL Agent-Auftragsbenutzer bereitgestellt wird. Es wird jedoch empfohlen, ein anderes Domänendienstkonto anzugeben, damit Setup ihm die am wenigsten erforderlichen Berechtigungen erteilen kann.
    
9. Wenn Sie auf das nächste Klicken klicken, wird eine weitere Überprüfungsrunde durchgeführt, und alle Probleme werden gemeldet. Nach erfolgreichem Abschluss der Überprüfung wechselt das Installationsprogramm zur Seite "Portalkonfiguration". 
    
10. Geben Sie auf der Seite "Portalkonfiguration" die folgenden Informationen an:
    
    - **QoE-Archiv SQL Server:** SQL Server Instanzname für den Speicherort der QoE-Archivdatenbank. Beachten Sie, dass im Gegensatz zur Seite "QoE-Archivkonfiguration" und der Seite "Cubekonfiguration" der Computername nicht festgelegt ist und angegeben werden muss. Wenn die QoE-Archivkomponente für die Installation ausgewählt wurde, wird dieses Feld vorab mit dem Auffüllen des Werts auf der QoE-Archivkonfigurationsseite ausgefüllt.
    
    - **Cube Analysis Server:** SQL Server Analysis Service-Instanzname für den Speicherort des Cubes. Wenn die Cube-Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem Auffüllwert auf der Seite "Cubekonfiguration" ausgefüllt.
    
    - **Repository SQL Server:** SQL Server Instanzname, in dem die Repositorydatenbank erstellt werden soll. Wenn der SQL Server Instanzname, in dem sich die QoE-Archivdatenbank befindet, bereits im Setup (in anderen Komponenten) angegeben wurde, wird dieses Feld mit dem Namen der QoE-Archivdatenbank SQL Server Instanz bereits ausgefüllt. Dies kann eine beliebige SQL Server Instanz sein.
    
    - **Repositorydatenbank:** Standardmäßig ist die Option auf "Neue Datenbank erstellen" festgelegt. Da das Repository DB-Upgrade nicht unterstützt wird, kann die Option "Vorhandene Datenbank verwenden" nur verwendet werden, wenn die vorhandene Repository-DATENBANK das gleiche Schema wie der zu installierende Build aufweist.
    
    - **IIS-App-Poolbenutzer – Benutzername &amp; Kennwort:** Das Konto, unter dem der IIS-Anwendungspool ausgeführt werden soll. Die Felder "Benutzername" und "Kennwort" werden ausgegraut, wenn integrierte Systemkonten ausgewählt sind. Diese Felder werden nur aktiviert, wenn im Dropdownfeld "Other" ausgewählt ist, damit der Benutzer die Kontoinformationen des Domänendiensts eingeben kann.
    
11. Wenn Sie auf "Weiter" klicken, wird die letzte Überprüfungsrunde durchgeführt, um sicherzustellen, dass auf die SQL Server Instanzen mithilfe der bereitgestellten Anmeldeinformationen zugegriffen werden kann und IIS auf dem Computer verfügbar ist. Nach erfolgreichem Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortfahren. 
    
Wenn das Installationsprogramm abgeschlossen ist, wird wahrscheinlich der SQL Server Agent-Auftrag ausgeführt, wobei die anfängliche Auslastung der QoE-Daten und die Cubeverarbeitung ausgeführt wird. Abhängig von der Datenmenge in QoE stehen dem Portal noch keine Daten zur Verfügung. Um den Status der Datenlast und cubeverarbeitung zu überprüfen, wechseln Sie zu  `http://<machinename>/CQD/#/Health` . 
> [!NOTE]
> Beachten Sie, dass bei der URL zum Überprüfen des Status der Download-Cubeverarbeitung die Groß-/Kleinschreibung beachtet wird. Wenn Sie "Integrität" eingeben, funktioniert die URL nicht. Sie müssen "Health" am Ende der URL mit dem Großbuchstaben H eingeben. 
  
Detaillierte Protokollmeldungen werden angezeigt, wenn der Debugmodus aktiviert ist. Um den Debugmodus zu aktivieren, wechseln Sie zu **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config,** und aktualisieren Sie die folgende Zeile so, dass der Wert auf **"True"** festgelegt ist:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Auf die Hauptportalseite kann über  `http://<machinename>/CQD` zugegriffen werden. 
## <a name="managing-user-access-for-the-portal"></a>Verwalten des Benutzerzugriffs für das Portal

Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7.0 eingeführt wurde. Weitere Informationen zur IIS-Sicherheit finden Sie unter Grundlegendes zur [IIS 7.0-URL-Autorisierung.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)
  
Jede Website oder Webanwendung erbt die Standard-URL-Autorisierung, die für den gesamten IIS konfiguriert ist, in der Regel "Alle Benutzer zulassen". Wenn der Zugriff auf das Portal restriktiver sein muss, können Administratoren nur der bestimmten Benutzergruppe Zugriff gewähren, indem sie die "Autorisierungsregeln" bearbeiten.
  
![Bereitstellen der Anrufqualität – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> Das Symbol "Autorisierungsregeln" darf nicht mit der ".NET-Autorisierung" im Abschnitt ASP.NET verwechselt werden, bei dem es sich um einen anderen Autorisierungsmechanismus handelt. 
  
Administratoren sollten zuerst die geerbte Regel "Alle Benutzer zulassen" entfernen. Dadurch wird verhindert, dass nicht autorisierte Benutzer auf das Portal zugreifen.
  
![Bereitstellen von CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Als Nächstes sollten Administratoren neue Zulassungsregeln hinzufügen und bestimmten Benutzern die Berechtigung erteilen, auf das Portal zuzugreifen. Es wird empfohlen, eine lokale Gruppe namens "CQDPortalUsers" zu erstellen, um die Benutzer zu verwalten.
  
![Bereitstellen des Anrufqualitäts-Dashboards](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Die Konfigurationsdetails werden in der web.config gespeichert, die sich im physischen Verzeichnis des Portals befindet.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

Der nächste Schritt besteht darin, das Dashboard des CQD zu konfigurieren. Nachdem Benutzer von IIS authentifiziert wurden, müssen sie über Dateiberechtigungen für das CQD-Verzeichnis verfügen, um auf die Webportalinhalte zugreifen zu können. Es ist möglich, die ACLs über die Sicherheitsregisterkarte der CQD-Verzeichniseigenschaften zu ändern, um einzelne Benutzer oder Gruppen hinzuzufügen. Der empfohlene Ansatz besteht jedoch darin, die Dateiberechtigungen unverändert zu lassen. Ändern Sie stattdessen die IIS-Einstellung, um den IIS-Arbeitsprozess für den Zugriff auf das CQD-Verzeichnis zu verwenden, unabhängig davon, welcher Benutzer authentifiziert ist. 
  
> [!IMPORTANT]
> Es ist wichtig, diese Einstellung nur für die CQD-Anwendung und nicht für die beiden API-Anwendungen QoEDataService und QoERepositoryService zu ändern. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Konfigurieren des Dateizugriffs für das CQD (Dashboard)

1. Öffnen Sie den Konfigurations-Editor für CQD.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Wählen Sie im Abschnitt **"system.webServer/serverRuntime"** aus.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Ändern Sie authenticatedUserOverride in **UseWorkerProcessUser**.
    
     ![Bereitstellen des Anrufqualitätsdashboards – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Klicken Sie auf der rechten Seite der Seite auf **"Übernehmen".**
    
## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-cqd-shows-no-data-after-deployment"></a>Das CQD zeigt nach der Bereitstellung keine Daten an.

Möglicherweise wird der folgende Fehler angezeigt:

*Die Abfrage konnte nicht ausgeführt werden, während sie auf dem Cube ausgeführt wurde. Verwenden Sie den Abfrage-Editor, um die Abfrage zu ändern und probleme zu beheben. Stellen Sie außerdem sicher, dass auf den Cube zugegriffen werden kann.*

Dies bedeutet, dass der Cube in SQL Server Analysis Services verarbeitet werden muss, bevor er in CQD verwendet wird. Sie können dies beheben, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie SQL Management Studio, und wählen Sie **Analysis Services** aus.

2. Erweitern Sie das **QoECube-Objekt,** wählen Sie **QoE Metric** aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Durchsuchen** aus. 

    Wenn dadurch ein leerer Browser zurückgegeben wird, wurde der Cube noch nicht fortgesetzt.

3. Klicken Sie mit der rechten Maustaste auf **"QoE Metric** angain", und wählen Sie **"Prozess"** aus.

4. Klicken Sie nach Abschluss der Verarbeitung erneut mit der rechten Maustaste auf das Objekt, und wählen Sie **"Durchsuchen"** aus, um zu bestätigen, dass auf der Browserseite jetzt Daten angezeigt werden. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Benutzer haben Probleme bei der Anmeldung, da das Installationsprogramm die richtigen Einstellungen in IIS nicht erstellen kann

In seltenen Fällen kann das Installationsprogramm die richtigen Einstellungen in IIS nicht erstellen. Manuelle Änderungen sind erforderlich, damit sich Benutzer beim CQD anmelden können. Wenn Benutzer Probleme bei der Anmeldung haben, führen Sie die folgenden Schritte aus:
  
1. Öffnen Sie den IIS-Manager, und navigieren Sie zur Standardwebsite.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Klicken Sie auf "Authentifizierung". Wenn die Optionen "Anonyme Authentifizierung", "ASP.NET Identitätswechsel", "Formularauthentifizierung" und "Windows-Authentifizierung" nicht mit den unten aufgeführten Einstellungen übereinstimmen, ändern Sie diese manuell so, dass sie den unten aufgeführten Einstellungen entsprechen. Alle anderen Authentifizierungsmechanismen sollten deaktiviert werden.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Klicken Sie für "Windows Authentifizierung" auf der rechten Seite auf "Erweitert Einstellungen".
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Legen Sie "Erweiterter Schutz" auf "Akzeptieren" fest, und aktivieren Sie das Kontrollkästchen "Kernelmodusauthentifizierung aktivieren".
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Wiederholen Sie die obigen Schritte für die Einträge "CQD", "QoEDataService" und "QoERepositoryService" unter "Standardwebsite".
    
Für HTTP- und HTTPS-Portbindungen erstellt das Installationsprogramm Portbindungen für die Standardportnummern (Port 80 für HTTP und Port 443 für HTTPS). Wenn auf dem Computer eine andere Website vorhanden ist, die diese Bindungen verwendet, gibt es einen Konflikt, und das IIS-Verhalten kann nicht vorhergesagt werden. Die beste Möglichkeit, dieses Problem zu vermeiden, besteht darin, vor der Installation von CQD sicherzustellen, dass keine anderen Websites den Ports 80 und 443 zugeordnet sind. 
  
So aktivieren Sie SSL/TLS in IIS und erzwingen, dass Benutzer eine Verbindung über sicheres HTTPS anstelle von HTTP herstellen:
  
1. Konfigurieren von Secure Sockets Layer in IIS, siehe [Konfigurieren von Secure Sockets Layer in IIS 7.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)) Ersetzen Sie nach Abschluss  `http` durch `https` .
    
2. Anweisungen zum Aktivieren von TLS in den SQL Server Verbindungen finden Sie unter [Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe der Microsoft Management Console.](https://support.microsoft.com/kb/316898/)
    
## <a name="cube-sync-fails"></a>Cubesynchronisierung schlägt fehl

QoEMetrics kann einige ungültige Datensätze basierend auf Endbenutzeruhren enthalten. Wenn die Zeitverzerrung größer als 60 yrs ist, schlägt der Cubeimport fehl.
  
 Überprüfen Sie die Min- und Max StartTime/EndTime mithilfe der folgenden Auswahl. Suchen und löschen Sie Datensätze in der fernen vergangenheit und sehr entfernten Zukunft, sie können ignoriert werden, und sie werden die Synchronisierungsprozesse aufbrechen.
  
- Min(StartTime) aus CqdPartitionedStreamView auswählen
    
- Auswählen von MAX(StartTime) FROM CqdPartitionedStreamView
    
- MIN(EndTime) FROM CqdPartitionedStreamView auswählen
    
- Auswählen von MAX(EndTime) FROM CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Aufgaben nach der Installation

### <a name="importing-buildings-and-networks"></a>Importieren von Gebäuden und Netzwerken

Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:
  
1. Definieren von Gebäudetypen (empfohlen)
    
2. Definieren von Building Ownership-Typen (empfohlen)
    
3. Definieren von Netzwerktypen (dringend empfohlen)
    
4. Importieren von Gebäuden (empfohlen)
    
5. Importieren von Subnetzen (empfohlen)
    
### <a name="define-building-types"></a>Definieren von Gebäudetypen

Gebäudetypen werden verwendet, um die verschiedenen Gebäudedefinitionen oder -typen in Ihrer Organisation zu beschreiben. 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Headquarters
    
- Remote-Office
    
- Gemeinsame Standorte
    
  **Beispielsyntax SQL**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Die Parameter BuildingTypeId und BuildingTypeDesc sind erforderlich.
  
### <a name="define-building-ownership-types"></a>Definieren von Gebäudebesitzertypen

Besitzertypen werden verwendet, um zwischen eigenen und geleasten Ressourcen zu unterscheiden.
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Contoso Leased non-RE &amp; F
    
- Contoso Leased RE &amp; F
    
- Contoso Owned
    
- Tochtergesellschaft geleast
    
  **Beispielsyntax SQL**
  
```SQL
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

Die Parameter "OwnershipTypeId" und "OwnershipTypeDesc" sind erforderlich. 
  
### <a name="define-network-names"></a>Definieren von Netzwerknamen

Netzwerktypen werden verwendet, um verschiedene Arten von Netzwerken innerhalb der Organisation zu beschreiben. Auf diese Weise können Sie nach bestimmten Netzwerktypen filtern (oder herausfiltern).
  
> [!NOTE]
> Es wird dringend empfohlen, Netzwerknamen zu definieren, ist jedoch optional. Wenn Sie keine Netzwerknamen definieren möchten, stellen Sie sicher, dass jeder CqdNetwork-Eintrag die BuildingId 0 aufweist. 
  
Beispiele
  
- VPN
    
- LABOR
    
  **Beispielsyntax SQL**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Die Parameter "NetworkNameID" und "NetworkName" sind erforderlich, der Parameter "NetworkType" ist optional, wird jedoch empfohlen.
  
### <a name="import-buildings"></a>Importieren von Gebäuden

Das Importieren von Gebäuden bietet Ihnen die Möglichkeit, bestimmte Einblicke zu erhalten (Anrufe schlechter Qualität pro Gebäude mit WLAN/Kabel usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Bevor Sie ein neues Gebäude importieren, sollten Sie bereits einen vordefinierten BuildingKey identifiziert haben. Geben Sie dazu den Befehl "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL aus, um den aktuellen Wert zu identifizieren und dem Ergebnis 1 hinzuzufügen.
  
 **Beispielsyntax SQL**
  
```SQL
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

Die Parameter BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId und BuildingTypeId sind erforderlich, die anderen Parameter sind optional.
  
### <a name="import-subnets"></a>Importieren von Subnetzen

Das Importieren von Gebäuden bietet Ihnen die Möglichkeit, bestimmte Einblicke zu erhalten (Anrufe schlechter Qualität pro Gebäude mit WLAN/Kabel usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen.
  
Importieren Sie Subnetze, und ordnen Sie sie den im letzten Schritt importierten Gebäuden zu. Wenn Sie sich entschieden haben, NetworkName nicht aufzufüllen, stellen Sie sicher, dass jeder Eintrag in dieser Tabelle eine NetworkNameID von 0 verwendet. Weitere Informationen zu SQL Syntax und Parametern für das Anrufqualitäts-Dashboard finden Sie unter [Verwenden des Anrufqualitätsdashboards für Skype for Business Server.](./use.md)
  
 **Beispielsyntax SQL**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

Die Parameter "Network" und "UpdatedDate" sind erforderlich, die anderen Parameter sind optional.
  
### <a name="optional-bssid"></a>Optional: BSSID

Durch das Auffüllen von BSSID-Informationen erhalten Sie zusätzliche WLAN-Datenstromkorrelationen nach Controller oder Funk. Dies erfolgt zusätzlich zur Filterung nach Gebäude oder Subnetz. 
  
 **Beispielsyntax SQL**
  
```SQL
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

**CqdBssidTable Details**

|**Wie im CQD dargestellt**|**CQDBssid-Tabelle**|**Beispieleingaben**|
|:-----|:-----|:-----|
|Ap NName  <br/> |LD  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (Sie müssen das durch Trennzeichen getrennte Fformat verwenden)  <br/> |
|Controller  <br/> |Gebäude  <br/> |Die API 7  <br/> |
|Gerät  <br/> |Ess  <br/> |Controller1  <br/> |
|Radio  <br/> |Phy  <br/> |Bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Verarbeiten der importierten Daten

Nach dem Importieren von Gebäude-/Netzwerkdaten gelten sie standardmäßig nur für Datensätze, die nach diesem Zeitpunkt generiert wurden. 
  
Um alle vorherigen Datensätze mit diesen neuen Daten zu kennzeichnen, müssen Sie die gespeicherte CqdUpdateBuilding-Prozedur wie unten dargestellt ausführen: 
  
Geben Sie ihr das Datum Ihres ersten Datensatzes (identifizieren Sie, dass sie mithilfe des Befehls "MIN(StartTime) FROM CqdPartitionedStreamView SQL") ein EndDate von morgen und dann NULL für die letzten beiden Werte verwenden.
  
Sobald die Daten Streamdaten zugeordnet sind, muss der SSIS-Cube alle Datensätze erneut verarbeiten. Dies gilt auch beim Massenbeifügung von BSSID/ISP-Daten. Stellen Sie sicher, dass "Prozess vollständig" ausgewählt ist.
