---
title: Bereitstellen des Anrufqualitätsdashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Zusammenfassung: Erfahren Sie mehr über den Bereitstellungsprozess für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: 1f59209575284035fcdca52e4f18220aa05337af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114111"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Bereitstellen des Anrufqualitätsdashboards für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bereitstellungsprozess für das Anrufqualitätsdashboard. Das Anrufqualitätsdashboard ist ein Tool für Skype for Business Server.
  
## <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Das Call Quality Dashboard (CQD) besteht aus drei Hauptkomponenten:
  
- **Archivdatenbank**, in der die QoE-Daten (Quality of Experience) repliziert und gespeichert werden.
    
- **Cube**, in dem Daten aus der QoE-Archivdatenbank für optimierten und schnellen Zugriff aggregiert werden.
    
- **Portal**, in dem Benutzer QoE-Daten problemlos abfragen und visualisieren können.
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Der Einrichtungsprozess für QoE Archive umfasst das Erstellen der QoE-Archivdatenbank, die Bereitstellung einer SQL Server-gespeicherten Prozedur, die die Daten aus der QoE-Metrik-Quelldatenbank in die QoE-Archivdatenbank verschiebt, und das Einrichten des SQL Server-Agent-Auftrags, um die gespeicherte Prozedur in einem regelmäßigen Intervall auszuführen. 
  
Die Cubebereitstellung ruft Informationen vom Benutzer ab, wo sich das QoE-Archiv befindet, stellt den Cube zur Verfügung und richtet einen regulären SQL Server-Agentauftrag ein, der den Cube in einem regelmäßigen Intervall aktualisiert.
  
Die Portalinstallation erstellt eine Repositorydatenbank, in der die Zuordnung von CQD-Benutzern zu den Berichten/Abfragen der einzelnen Benutzer gespeichert wird. Anschließend wird eine IIS-Webanwendung eingerichtet, die das Dashboard ist, in dem Benutzer einen vordefinierten Satz von Berichten sehen sowie eigene Abfragen anpassen und erstellen können, um Daten aus dem Cube zu visualisieren. Die Portalinstallation erstellt zwei zusätzliche Webanwendungen, die APIs für Benutzer für den programmgesteuerten Zugriff auf das Repository und den Cube verfügbar machen. (Diese APIs werden auch intern vom Dashboard verwendet.)
  

|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaft**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|Installieren Sie erforderliche Hardware und Software.  <br/> |Entscheiden Sie sich für die CQD-Konfiguration, und wählen Sie SQL Server, aus dem sie installiert werden soll.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Abschnitt "Voraussetzungen vor der Installation" in der Bereitstellungsdokumentation.  <br/> |
|Installieren Sie CQD.  <br/> |Führen Sie den MSI nach dem Bereitstellungsdokument aus.  <br/> |Zum Ausführen des Setups muss das Installationskonto ein Domänenbenutzer sein, der Mitglied der lokalen Administratorgruppe ist und Lesezugriff auf die QoE-Metrikdatenbank auf dem Monitoring Server hat.  <br/> |Abschnitte "Konten und Bereitstellungsschritte" in der Bereitstellungsdokumentation.  <br/> |
|Gewähren des Benutzerzugriffs.  <br/> |Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7.0 eingeführt wurde. Weitere Informationen finden Sie unter [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Verwalten des Benutzerzugriffs für den Abschnitt Portal in der Bereitstellungsdokumentation.  <br/> |
|Optional: Bereitstellen von Subnetzzuordnungsinformationen.  <br/> |Füllen Sie Netzwerk- und Gebäudezuordnungstabellen in der QoE-Archivdatenbank auf.  <br/> |Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.  <br/> |Abschnitt "Bereitstellen von Subnetzinformationen" in der Benutzerdokumentation.  <br/> |
   


Die Bereitstellung des Anrufqualitätsdashboards umfasst das Einrichten der Infrastruktur und das Installieren der Software. Im folgenden Verfahren wird der Prozess erläutert.
  
## <a name="deployment-steps"></a>Bereitstellungsschritte

1. Kopieren Sie CallQualityDashboard.msi auf den Computer, auf dem die Archivdatenbankkomponente von CQD installiert werden soll (dies ist der Computer, auf dem SQL Server ist). 
    
2. Führen Sie den MSI aus (Windows wird aufgefordert, mit Administratorrechten auszuführen, tun Sie dies). 
    
3. Akzeptieren Sie die EULA.
    
4. Wählen Sie den Zielordner aus, in dem sich Dateien im Zusammenhang mit Komponenten des Anrufqualitätsdashboards befinden oder den Standardspeicherort akzeptieren.
    
5. Wählen Sie alle Features aus.
    
6. Geben Sie auf der Seite QoE-Archivkonfiguration die folgenden Informationen an:
    
   - **QoE-Metriken SQL Server:** SQL Server instanznamen für den Standort der QoE-Metrik-DB (dies ist die Datenquelle).
    
   - **QoE Archive SQL Server Name:** Dies ist ein schreibgeschütztes Feld, das auf dem vollqualifizierten Domänennamen des lokalen Computers festgelegt ist. Archiv-DB kann nur auf dem lokalen Computer installiert werden.
    
   - **QoE Archive SQL Server Instanz:** Ein lokaler SQL Server Instanzname, für den die Archiv-DB erstellt werden soll. Wenn Sie eine Standardinstanz SQL Server, lassen Sie dieses Feld leer. Um eine benannte SQL Server zu verwenden, geben Sie den Instanznamen an (z. B. den Namen nach dem " \" ).
    
   - **QoE-Archivdatenbank:** Standardmäßig ist diese Option auf "Neue Datenbank erstellen" festgelegt. Da das Archiv-DB-Upgrade nicht unterstützt wird, kann die Option "Vorhandene Datenbank verwenden" nur dann verwendet werden, wenn die vorhandene Archivdatenbank das gleiche Schema wie der zu installierende Build besitzt.
    
   - **Datenbankdateiverzeichnis:** Pfad zu dem Ort, an dem die Datenbankdateien (MDF und LDF) für die Archiv-DB platziert werden sollen. Dies sollte auf einem Laufwerk (HDD2 in der empfohlenen Hardwarekonfiguration) sein, das vom Betriebssystem getrennt ist. Beachten Sie, dass es empfohlen wird, ein leeres Verzeichnis ohne Dateien zu verwenden, um potenzielle Konflikte zu vermeiden, da die Dateinamen in der Installation festgelegt sind.
    
   - **Verwenden mehrerer Partitionen:** Der Standardwert ist auf "Mehrere Partitionen" festgelegt, was business Intelligence edition oder Enterprise edition von SQL Server. Wählen Sie für standard edition die Option "Einzelne Partition" aus. Beachten Sie, dass sich die Leistung der Cubeverarbeitung auswirken kann, wenn eine einzelne Partition verwendet wird.
    
     > [!NOTE]
     > Die Auswahl für die Option Mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden. Um es zu ändern, muss das Cubefeature zuerst deinstalliert und dann mithilfe der Option "Ändern" in der Systemsteuerung neu installiert werden. 
  
   - **Partition File Directory:** Pfad zu dem Ort, an dem die Partitionen für die QoE-Archivdatenbank platziert werden sollen. Dies sollte sich auf einem Laufwerk (HDD3 in der empfohlenen Hardwarekonfiguration) befinden, das vom Betriebssystemlaufwerk getrennt ist, und SQL Datenbankprotokolldateienlaufwerk. Beachten Sie, dass es empfohlen wird, ein leeres Verzeichnis ohne Dateien zu verwenden, um potenzielle Konflikte zu vermeiden, da die Dateinamen in der Installation festgelegt sind.
    
   - **SQL -Agent-Auftrag-Benutzer – Benutzername &amp; Kennwort:** Domänendienstkontoname und -kennwort (maskiert), die zum Ausführen des Schritts "QoE-Archivdaten" des SQL Server-Agent-Auftrags verwendet werden (in dem die gespeicherte Prozedur ausgeführt wird, um Daten aus QoE Metrics DB in Archive DB zu abrufen, sodass dieses Konto über Lesezugriff auf QoE Metrics DB verfügen muss, wie im Abschnitt Konten angegeben. Dieses Konto benötigt auch eine Anmeldung im QoE-Archiv SQL Server Instanz).
    
     > [!NOTE]
     > Das Konto, unter dem die SQL Server ausgeführt wird, z. B. NT SERVICE\MSSQLSERVER, muss über Zugriff/Berechtigung auf die oben angegebenen Verzeichnisse verfügen, damit die Installation erfolgreich ausgeführt werden kann. Weitere Informationen finden Sie unter [Configure File System Permissions for Database Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. Wenn Sie auf weiter klicken, führt das Installationsprogramm erforderliche Überprüfungen durch und berichtet, ob Probleme auftreten. Wenn alle erforderlichen Prüfungen bestehen, wird das Installationsprogramm zur Seite Cubekonfiguration wechseln. 
    
    > [!NOTE]
    > Wenn das Installationsprogramm eine Warnmeldung zeigt, dass der SQL Server-Agentdienst für die QoE Archive SQL Server-Instanz derzeit nicht ausgeführt wird, kann die Installation fortgesetzt werden. Stellen Sie nach der Installation jedoch sicher, dass der SQL-Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf Automatisch fest, damit der geplante Auftrag ausgeführt wird. 
  
8. Geben Sie auf der Seite Cubekonfiguration die folgenden Informationen an:
    
   - **QoE Archive SQL Server Name:** Dies ist ein schreibgeschütztes Feld, das auf dem vollqualifizierten Domänennamen des lokalen Computers festgelegt ist. Cube kann nur auf dem Computer installiert werden, auf dem die QoE-Archivdatenbank vorhanden ist (Hinweis. Cube selbst kann auf einem Remotecomputer installiert werden. Siehe unten)
    
   - **QoE Archive SQL Server Instanz:** SQL Server Instanzname für den Standort der QoE-Archiv-DB. Wenn Sie eine Standardinstanz SQL Server, lassen Sie dieses Feld leer. Um eine benannte SQL Server anzugeben, geben Sie den Instanznamen ein (z. B. den Namen nach dem " \" ). Wenn die QoE-Archivkomponente für die Installation ausgewählt wurde, wird dieses Feld mit dem wert auf der Seite QoE-Archivkonfiguration vorab aufgefüllt.
    
   - **Cube Analysis Server:** SQL Server Analysis Service-Instanznamen für den Ort, an dem der Cube erstellt werden soll. Dies kann ein anderer Computer sein, aber der installierende Benutzer muss Mitglied der Serveradministratoren der Zielinstanz SQL Server Analysis Service-Instanz sein.
    
     > [!NOTE]
     >  Weitere Informationen zum Konfigurieren von Analysis Services Server-Administratorberechtigungen finden Sie unter [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **Verwenden mehrerer Partitionen:** Der Standardwert ist auf "Mehrere Partitionen" festgelegt, was business Intelligence edition oder Enterprise edition von SQL Server. Wählen Sie für standard edition die Option "Einzelne Partition" aus. Beachten Sie, dass sich die Leistung der Cubeverarbeitung auswirken kann, wenn eine einzelne Partition verwendet wird.
    
     > [!NOTE]
     >  Die Auswahl für die Option Mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden. Um es zu ändern, muss das Cubefeature zuerst deinstalliert und dann mithilfe der Option "Ändern" in der Systemsteuerung neu installiert werden.
  
   - **Cubebenutzer – &amp; Benutzername Kennwort: Name** und Kennwort des Domänendienstkontos (maskiert), die die Cubeverarbeitung auslösen. Wenn die QoE-Archivkomponente für die Installation ausgewählt wurde, wird dieses Feld mit dem Wert auf der Seite Archivkonfiguration für den SQL-Agentauftragsbenutzer ausgefüllt. Es wird jedoch empfohlen, ein anderes Domänendienstkonto anzugeben, damit Setup ihm die am wenigsten erforderlichen Berechtigungen erteilen kann.
    
9. Wenn Sie auf weiter klicken, wird eine weitere Überprüfungsrunde ausgeführt, und alle Probleme werden gemeldet. Nach erfolgreichem Abschluss der Überprüfung wird das Installationsprogramm zur Seite Portalkonfiguration wechseln. 
    
10. Geben Sie auf der Seite Portalkonfiguration die folgenden Informationen an:
    
    - **QoE Archive SQL Server:** SQL Server instanznamen für den Ort, an dem sich die QoE-Archivdatenbank befindet. Beachten Sie, dass im Gegensatz zur Seite QoE-Archivkonfiguration und der Seite Cubekonfiguration der Computername nicht festgelegt ist und angegeben werden muss. Wenn die QoE-Archivkomponente für die Installation ausgewählt wurde, wird dieses Feld mit dem wert auf der Seite QoE-Archivkonfiguration vorab aufgefüllt.
    
    - **Cube Analysis Server:** SQL Server Analysis Service-Instanznamen für den Ort, an dem sich der Cube befindet. Wenn die Cubekomponente für die Installation ausgewählt wurde, wird dieses Feld mit dem wert auf der Seite Cubekonfiguration vorab aufgefüllt.
    
    - **Repository-SQL Server:** SQL Server Instanzname, in dem die Repositorydatenbank erstellt werden soll. Wenn der SQL Server-Instanzname für den Standort der QoE-Archivdatenbank bereits im Setup (in anderen Komponenten) angegeben wurde, wird dieses Feld mit dem QoE-Archiv-DB-SQL Server-Instanznamen ausgefüllt. Dies kann eine beliebige SQL Server sein.
    
    - **Repositorydatenbank:** Standardmäßig ist die Option auf "Neue Datenbank erstellen" festgelegt. Da das Repository -DB-Upgrade nicht unterstützt wird, kann die Option "Vorhandene Datenbank verwenden" nur verwendet werden, wenn die vorhandene Repository-DB das gleiche Schema wie der zu installierende Build besitzt.
    
    - **BENUTZER des IIS-App-Pools – Benutzername &amp; Kennwort:** Das Konto, unter dem der IIS-Anwendungspool ausgeführt werden soll. Die Felder Benutzername und Kennwort sind ausgegraut, wenn integrierte Systemkonten ausgewählt sind. Diese Felder werden nur aktiviert, wenn "Other" im Dropdownfeld ausgewählt ist, damit der Benutzer die Domänendienstkontoinformationen eingeben kann.
    
11. Wenn Sie auf weiter klicken, wird die letzte Überprüfungsrunde durchgeführt, um sicherzustellen, dass auf die SQL Server-Instanzen mithilfe der bereitgestellten Anmeldeinformationen zugegriffen werden kann und IIS auf dem Computer verfügbar ist. Nach erfolgreichem Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortfahren. 
    
Wenn das Installationsprogramm fertig ist, wird wahrscheinlich der SQL Server-Agent-Auftrag ausgeführt, der die anfänglichen Lasten der QoE-Daten und die Cubeverarbeitung überschreitet. Abhängig von der Datenmenge in QoE stehen dem Portal noch keine Daten zur Anzeige zur Verfügung. Um den Status der Datenlade- und Cubeverarbeitung zu überprüfen, wechseln Sie zu  `http://<machinename>/CQD/#/Health` . 
> [!NOTE]
> Beachten Sie, dass bei der URL zum Überprüfen des Status der Verarbeitung des Downloadcubes die Zwischenschreibung beachtet wird. Wenn Sie "Health" eingeben, funktioniert die URL nicht. Sie müssen "Health" am Ende der URL mit dem Hauptbuchstaben H eingeben. 
  
Detaillierte Protokollmeldungen werden angezeigt, wenn der Debugmodus aktiviert ist. Wechseln Sie zum Aktivieren des Debugmodus zu **%SYSTEMDRIVE%\Programme\Skype For Business 2015 CQD\QoEDataService\web.config**, und aktualisieren Sie die folgende Zeile, sodass der Wert auf **True festgelegt ist:**

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Auf die Hauptportalseite kann über zugegriffen  `http://<machinename>/CQD` werden. 
## <a name="managing-user-access-for-the-portal"></a>Verwalten des Benutzerzugriffs für das Portal

Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7.0 eingeführt wurde. Weitere Informationen zur IIS-Sicherheit finden Sie unter [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Jede Website oder Webanwendung erbt die für den gesamten IIS konfigurierte Standard-URL-Autorisierung, die in der Regel "Alle Benutzer zulassen" ist. Wenn der Zugriff auf das Portal restriktiver sein muss, können Administratoren nur der bestimmten Gruppe von Benutzern Zugriff gewähren, indem sie die "Autorisierungsregeln" bearbeiten.
  
![Bereitstellen der Anrufqualität – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> Das Symbol Autorisierungsregeln darf nicht mit dem ".NET Authorization" im Abschnitt ASP.NET verwechselt werden, bei dem es sich um einen anderen Autorisierungsmechanismus handelt. 
  
Administratoren sollten zuerst die geerbte Regel "Alle Benutzer zulassen" entfernen. Dadurch wird verhindert, dass nicht autorisierte Benutzer auf das Portal zugreifen.
  
![Bereitstellen von CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Als Nächstes sollten Administratoren neue Zulässige Regeln hinzufügen und bestimmten Benutzern die Berechtigung zum Zugriff auf das Portal erteilen. Es wird empfohlen, eine lokale Gruppe mit dem Namen "CQDPortalUsers" zum Verwalten der Benutzer zu erstellen.
  
![Bereitstellen des Anrufqualitäts-Dashboards](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Die Konfigurationsdetails werden im web.config im physischen Verzeichnis des Portals gespeichert.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

Der nächste Schritt besteht im Konfigurieren des Dashboards der CQD. Nachdem Benutzer von IIS authentifiziert wurden, müssen sie über Dateiberechtigungen für das CQD-Verzeichnis verfügen, um auf die Webportalinhalte zugreifen zu können. Es ist möglich, die ACLs über die Sicherheitsregisterkarte der CQD-Verzeichniseigenschaften zu ändern, um einzelne Benutzer oder Gruppen hinzuzufügen. Es wird jedoch empfohlen, die Dateiberechtigungen unverändert zu lassen. Ändern Sie stattdessen die IIS-Einstellung, um den IIS-Arbeitsprozess für den Zugriff auf das CQD-Verzeichnis zu verwenden, unabhängig davon, welcher Benutzer authentifiziert wird. 
  
> [!IMPORTANT]
> Es ist wichtig, diese Einstellung nur für die CQD-Anwendung und nicht für die beiden API-Anwendungen zu ändern: QoEDataService und QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Konfigurieren des Dateizugriffs für das CQD (Dashboard)

1. Öffnen Sie den Konfigurations-Editor für CQD.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Wählen Sie unter Abschnitt **system.webServer/serverRuntime aus.**
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Ändern Sie authenticatedUserOverride in **UseWorkerProcessUser**.
    
     ![Bereitstellen des Anrufqualitätsdashboards – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Klicken **Sie auf** der rechten Seite der Seite auf Übernehmen.
    
## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-cqd-shows-no-data-after-deployment"></a>Der CQD zeigt nach der Bereitstellung keine Daten an.

Möglicherweise wird der folgende Fehler angezeigt:

*Die Abfrage konnte beim Ausführen des Cubes nicht ausgeführt werden. Verwenden Sie den Abfrage-Editor, um die Abfrage zu ändern und alle Probleme zu beheben. Stellen Sie außerdem sicher, dass auf den Cube zugegriffen werden kann.*

Dies bedeutet, dass der Cube in SQL Server Analysis Services verarbeitet werden muss, bevor er in CQD verwendet wird. Sie können dies beheben, indem Sie die folgenden Schritte ausführen:

1. Öffnen SQL Management Studio, und wählen Sie **Analysis Services aus.**

2. Erweitern Sie **das QoECube-Objekt,** wählen **Sie QoE-Metrik** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **dann Durchsuchen aus.** 

    Wenn dadurch ein leerer Browser zurückgegeben wird, wurde der Cube noch nicht fortgesetzt.

3. Klicken Sie mit der **rechten Maustaste auf QoE-Metrik-Angain,** und wählen Sie **Prozess aus.**

4. Klicken Sie nach Abschluss der Verarbeitung erneut mit der rechten Maustaste auf das Objekt, und wählen Sie **Durchsuchen** aus, um zu bestätigen, dass auf der Browserseite jetzt Daten angezeigt werden. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Benutzer haben Probleme bei der Anmeldung, da beim Installationsprogramm die richtigen Einstellungen in IIS nicht erstellt werden können

In seltenen Fällen kann das Installationsprogramm die richtigen Einstellungen in IIS nicht erstellen. Manuelle Änderungen sind erforderlich, damit sich Benutzer bei der CQD anmelden können. Wenn Benutzer Probleme bei der Anmeldung haben, führen Sie die folgenden Schritte aus:
  
1. Öffnen Sie den IIS-Manager, und navigieren Sie zu Standardwebsite.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Klicken Sie auf "Authentifizierung". Wenn die Einstellungen "Anonyme Authentifizierung", "ASP.NET Identitätswechsel", "Formularauthentifizierung" und "Windows-Authentifizierung" nicht mit den unten aufgeführten Einstellungen übereinstimmen, ändern Sie sie manuell so, dass sie den folgenden Einstellungen entsprechen. Alle anderen Authentifizierungsmechanismen sollten deaktiviert werden.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Klicken Sie für "Windows-Authentifizierung" auf der rechten Seite auf Erweiterte Einstellungen.
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Legen Sie "Erweiterter Schutz" auf Akzeptieren und aktivieren Sie das Kontrollkästchen "Kernelmodusauthentifizierung aktivieren".
    
     ![Bereitstellen des Anrufqualitäts-Dashboards](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Wiederholen Sie die obigen Schritte für jeden der Einträge "CQD", "QoEDataService" und "QoERepositoryService" unter "Standardwebsite".
    
Für HTTP- und HTTPS-Portbindungen erstellt das Installationsprogramm Portbindungen für die Standardportnummern (Port 80 für HTTP und Port 443 für HTTPS). Wenn auf dem Computer eine andere Website vorhanden ist, die diese Bindungen verwendet, tritt ein Konflikt auf, und das IIS-Verhalten kann nicht vorhergesagt werden. Dieses Problem kann am besten vermieden werden, indem Sie sicherstellen, dass keine anderen Websites den Ports 80 und 443 zugeordnet sind, bevor Sie CQD installieren. 
  
So aktivieren Sie SSL/TLS in IIS und erzwingen, dass Benutzer eine Verbindung über sicheres HTTPS anstelle von HTTP herstellen:
  
1. Konfigurieren von Secure Sockets Layer in IIS finden Sie unter [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)). Ersetzen Sie nach getaner  `http` Arbeit durch `https` .
    
2. Anweisungen zum Aktivieren von TLS in den SQL Server finden Sie unter Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe der [Microsoft Management Console](https://support.microsoft.com/kb/316898/).
    
## <a name="cube-sync-fails"></a>Fehler bei der Cubesynchronisierung

QoEMetrics kann einige ungültige Datensätze basierend auf Endbenutzeruhren enthalten. Wenn die Zeitschrägung größer als 60 Jahre ist, wird beim Cubeimport ein Fehler angezeigt.
  
 Überprüfen Sie min und Max StartTime/EndTime mit den folgenden Auswahlen. Suchen und löschen Sie Datensätze in der weit vergangenen und sehr fernen Zukunft, sie können ignoriert werden, und sie werden die Synchronisierungsprozesse aufbrechen.
  
- Select MIN(StartTime) FROM CqdPartitionedStreamView
    
- Select MAX(StartTime) FROM CqdPartitionedStreamView
    
- Select MIN(EndTime) FROM CqdPartitionedStreamView
    
- Wählen Sie MAX(EndTime) FROM CqdPartitionedStreamView aus.
    
## <a name="post-install-tasks"></a>Aufgaben nach der Installation

### <a name="importing-buildings-and-networks"></a>Importieren von Gebäuden und Netzwerken

Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:
  
1. Definieren von Gebäudetypen (empfohlen)
    
2. Definieren von Gebäudebesitztypen (empfohlen)
    
3. Definieren von Netzwerktypen (dringend empfohlen)
    
4. Importieren von Gebäuden (empfohlen)
    
5. Importieren von Subnetzen (empfohlen)
    
### <a name="define-building-types"></a>Definieren von Gebäudetypen

Gebäudetypen werden verwendet, um die verschiedenen Gebäudedefinitionen oder -typen in Ihrer Organisation zu beschreiben. 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Headquarters
    
- Remote Office
    
- Joint-Venture-Standort
    
  **Beispiel SQL Syntax**
  
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
  
### <a name="define-building-ownership-types"></a>Definieren von Gebäudebesitztypen

Besitzertypen werden verwendet, um besitzeigene und geleaste Objekte zu unterscheiden.
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Contoso Leased non-RE &amp; F
    
- Contoso Leased RE &amp; F
    
- Contoso im Besitz
    
- Niederlassung geleast
    
  **Beispiel SQL Syntax**
  
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

Die Parameter OwnershipTypeId und OwnershipTypeDesc sind erforderlich. 
  
### <a name="define-network-names"></a>Definieren von Netzwerknamen

Netzwerktypen werden verwendet, um verschiedene Netzwerktypen innerhalb der Organisation zu beschreiben. Dadurch können Sie bestimmte Netzwerktypen filtern (oder herausfiltern).
  
> [!NOTE]
> Es wird dringend empfohlen, Netzwerknamen zu definieren, ist jedoch optional. Wenn Sie keine Netzwerknamen definieren möchten, stellen Sie sicher, dass jeder CqdNetwork-Eintrag eine BuildingId von 0 hat. 
  
Beispiele
  
- VPN
    
- LAB
    
  **Beispiel SQL Syntax**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Die Parameter NetworkNameID und NetworkName sind erforderlich, der Parameter NetworkType ist optional, wird jedoch empfohlen.
  
### <a name="import-buildings"></a>Importieren von Gebäuden

Das Importieren von Gebäuden bietet Ihnen die Möglichkeit, bestimmte Einblicke zu gewinnen (schlechte Anrufe pro Gebäude über WLAN/Kabel usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Bevor Sie ein neues Gebäude importieren, sollten Sie bereits einen vordefinierten BuildingKey identifiziert haben. Geben Sie dazu den Befehl "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL aus, um den aktuellen Wert zu identifizieren und dem Ergebnis 1 hinzuzufügen.
  
 **Beispiel SQL Syntax**
  
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

Das Importieren von Gebäuden bietet Ihnen die Möglichkeit, bestimmte Einblicke zu gewinnen (schlechte Anrufe pro Gebäude über WLAN/Kabel usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen.
  
Importieren Sie Subnetze, und ordnen Sie sie den im letzten Schritt importierten Gebäuden zu. Wenn Sie sich entschieden haben, NetworkName nicht zu füllen, stellen Sie sicher, dass jeder Eintrag in dieser Tabelle eine NetworkNameID von 0 verwendet. Weitere Informationen zu SQL und Parametern für das Anrufqualitätsdashboard finden Sie unter [Use Call Quality Dashboard for Skype for Business Server](./use.md).
  
 **Beispiel SQL Syntax**
  
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

Die Parameter Network und UpdatedDate sind erforderlich, die anderen Parameter sind optional.
  
### <a name="optional-bssid"></a>Optional: BSSID

Wenn Sie BSSID-Informationen auffüllen, erhalten Sie zusätzliche WLAN-Streamkorrelation durch Controller oder Funk. Dies ist zusätzlich zur Filterung nach Gebäude oder Subnetz. 
  
 **Beispiel SQL Syntax**
  
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

**CqdBssidTable-Details**

|**Wie in CQD dargestellt**|**CQDBssid Table**|**Beispieleingaben**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (Sie müssen das getrennte fformat verwenden)  <br/> |
|Controller  <br/> |Erstellen  <br/> |Aruba AP 7  <br/> |
|Gerät  <br/> |ess  <br/> |Controller1  <br/> |
|Radio  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Verarbeiten der importierten Daten

Nach dem Importieren von Gebäude-/Netzwerkdaten gilt dies standardmäßig nur für Datensätze, die nach diesem Zeitpunkt generiert wurden. 
  
Um alle vorherigen Datensätze mit diesen neuen Daten zu kennzeichnen, müssen Sie die gespeicherte Prozedur CqdUpdateBuilding wie unten gezeigt ausführen: 
  
Geben Sie ihm das Datum Ihres ersten Datensatzes (identifizieren Sie, dass mithilfe des Befehls MIN(StartTime auswählen) FROM CqdPartitionedStreamView SQL ) ein EndDate von morgen und dann NULL für die letzten beiden Werte verwendet wird.
  
Sobald die Daten Streamdaten zugeordnet sind, muss der SSIS-Cube alle Datensätze erneut bearbeiten. Dies gilt auch beim Massen hinzufügen von BSSID/ISP-Daten. Stellen Sie sicher, dass "Prozess vollständig" ausgewählt ist.
