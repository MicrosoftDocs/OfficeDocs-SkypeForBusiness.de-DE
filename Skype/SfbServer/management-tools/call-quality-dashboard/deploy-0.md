---
title: Bereitstellen eines Anruf Qualitäts Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Zusammenfassung: erfahren Sie mehr über den Bereitstellungsprozess für das Dashboard für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: aa7f5d81fd9778e148dcf64f84c757676bd1df2d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992692"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Bereitstellen eines Anruf Qualitäts Dashboards für Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über den Bereitstellungsprozess für das Dashboard für die Anrufqualität. Das Dashboard für die Anrufqualität ist ein Tool für Skype for Business Server.
  
## <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Das Dashboard für die Anrufqualität (CQD) besteht aus drei Hauptkomponenten:
  
- **Archivdatenbank**, in der die QoE-Daten (Quality of Experience) repliziert und gespeichert werden.
    
- **Cube**, in dem Daten aus der QoE-Archivdatenbank für optimierten und schnellen Zugriff aggregiert werden.
    
- **Portal**, in dem Benutzer problemlos QoE-Daten Abfragen und visualisieren können.
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Der Setupvorgang für das QoE-Archiv umfasst das Erstellen der QoE-Archivdatenbank, das Bereitstelleneiner gespeicherten SQL Server-Prozedur, die die Daten aus der QoE-Quelldatenbank in die QoE-Archivdatenbank verschiebt, und das Einrichten des SQL Server-Agent-Auftrags zum Ausführen der gespeicherten Prozedur in regelmäßigen Abständen. 
  
Die Cube-Bereitstellung ruft Informationen des Benutzers ab, in dem sich das QoE-Archiv befindet, stellt den Cube bereit und richtet einen regulären SQL Server-Agentauftrag ein, der den Cube in regelmäßigen Abständen aktualisiert.
  
Die Portal Installation erstellt eine Repository-Datenbank, in der die Zuordnung der CQD-Benutzer zu den Berichten/Abfragen jedes Benutzers gespeichert wird. Anschließend wird eine IIS-Webanwendung eingerichtet, die das Dashboard ist, in dem Benutzer einen vordefinierten Satz von Berichten anzeigen sowie eigene Abfragen anpassen und erstellen können, um Daten aus dem Cube zu visualisieren. Die Portal-Installation erstellt zwei zusätzliche Webanwendungen, die APIs für Benutzer verfügbar macht, um programmgesteuert auf das Repository und den Cube zuzugreifen. (Diese APIs werden auch intern vom Dashboard verwendet.)
  

|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaften**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|Installieren Sie die erforderliche Hardware und Software.  <br/> |Entscheiden Sie sich für die CQD-Konfiguration, und wählen Sie einen SQL Server aus, aus dem die Installation durchgeführt werden soll.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Abschnitt "Voraussetzungen für die Installation" in der Bereitstellungsdokumentation.  <br/> |
|Installieren Sie CQD.  <br/> |Führen Sie die MSI-Datei nach dem Bereitstellungs Dokument aus.  <br/> |Zum Durchführen der Einrichtung muss das Installationskonto ein Domänenbenutzer sein, der Mitglied der lokalen Gruppe Administratoren ist und über Lesezugriff auf die QoE Metrics-Datenbank auf dem Überwachungs Server verfügt.  <br/> |Abschnitte "Konten und Bereitstellungsschritte" in der Bereitstellungsdokumentation.  <br/> |
|Gewähren des Benutzerzugriffs  <br/> |Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7,0 eingeführt wurde. Weitere Informationen finden Sie unter [Grundlegendes zur IIS 7,0-URL-Autorisierung](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Verwalten des Benutzerzugriffs für den Portal Abschnitt in der Bereitstellungsdokumentation  <br/> |
|Optional: Geben Sie Informationen zur Subnet-Zuordnung an.  <br/> |Füllen Sie Netzwerk-und Gebäude Zuordnungstabellen in der QoE-Archivdatenbank auf.  <br/> |Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.  <br/> |Abschnitt "Bereitstellen von Subnetz-Informationen" in der Benutzerdokumentation.  <br/> |
   


Die Bereitstellung des Dashboards für die Anrufqualität umfasst das Einrichten der Infrastruktur und die Installation der Software. Das folgende Verfahren beschreibt den Prozess.
  
## <a name="deployment-steps"></a>Bereitstellungsschritte

1. Kopieren Sie die Datei "CallQualityDashboard. msi" auf den Computer, auf dem die Archivierungsdaten Bank Komponente von CQD installiert werden soll (Dies ist der Computer, auf dem SQL Server installiert ist). 
    
2. Führen Sie die MSI-Abfrage aus (Windows wird zur Ausführung mit Administratorrechten aufgefordert). 
    
3. Akzeptieren Sie den Endbenutzer-Lizenzvertrag.
    
4. Wählen Sie den Zielordner aus, in dem sich die Dateien für die Dashboard-Komponenten der Anrufqualität befinden, oder übernehmen Sie den Standardspeicherort.
    
5. Wählen Sie alle Features aus.
    
6. Geben Sie auf der Seite QoE-Archivkonfiguration die folgenden Informationen an:
    
   - **QoE-Metriken SQL Server:** Name der SQL Server-Instanz für die Position, an der sich die QoE-Metrik DB befindet (Dies ist die Datenquelle).
    
   - **QoE-Archiv-SQL Server-Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt ist. Archiv DB kann nur auf dem lokalen Computer installiert werden.
    
   - **QoE-Archiv-SQL Server-Instanz:** Ein lokaler SQL Server-Instanzname für die Stelle, an der die Archivdatenbank erstellt werden soll. Wenn Sie eine Standard-SQL Server-Instanz verwenden möchten, lassen Sie dieses Feld leer. Wenn Sie eine benannte SQL Server-Instanz verwenden möchten, geben Sie den Namen der Instanz an (Beispiels\"Weise den Namen nach ").
    
   - **QoE-Archivdatenbank:** Diese Option ist standardmäßig auf "neue Datenbank erstellen" eingestellt. Da die Archiv-DB-Aktualisierung nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Archivdatenbank dasselbe Schema wie der zu installierende Build aufweist.
    
   - **Datenbank-Dateiverzeichnis:** Der Pfad, in dem die Datenbankdateien (MDF und LDF) für die Archivdatenbank gespeichert werden sollen. Dies sollte sich auf einem Laufwerk (HDD2 in der empfohlenen Hardwarekonfiguration) befinden, das vom Betriebssystem getrennt ist. Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, ein leeres Verzeichnis ohne Dateien verwendet werden sollte, um potenzielle Konflikte zu vermeiden.
    
   - **Verwenden mehrerer Partitionen:** Der Standardwert ist auf "mehrere Partitionen" eingestellt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert. Wählen Sie für Standard Edition die Option "einzelne Partition" aus. Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn einzelne Partitionen verwendet werden.
    
     > [!NOTE]
     > Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden. Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "ändern" in der Systemsteuerung erneut installiert werden. 
  
   - **Partitionsdatei Verzeichnis:** Der Pfad, in dem die Partitionen für die QoE-Archivdatenbank gespeichert werden sollen. Dies sollte sich auf einem Laufwerk (HDD3 in der empfohlenen Hardwarekonfiguration) befinden, das vom Laufwerk des Betriebssystems und vom SQL-Datenbank-Protokolldateien getrennt ist. Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, ein leeres Verzeichnis ohne Dateien verwendet werden sollte, um potenzielle Konflikte zu vermeiden.
    
   - **SQL-Agent-Auftrags Benutzer- &amp; Kennwort für Benutzer Name:** Name und Kennwort des Domänendienstkontos (maskiert), das verwendet wird, um den Schritt "QoE-Archivdaten" des SQL Server-Agent-Auftrags auszuführen (der die gespeicherte Prozedur ausführt, um Daten aus QoE-Metriken DB in Archiv DB abzurufen, damit dieses Konto über Lesezugriff auf QoE-Metriken DB verfügt, wie im Abschnitt "Konten" angegeben. Dieses Konto muss auch über eine Anmeldung in der SQL Server-Instanz des QoE-Archivs verfügen.
    
     > [!NOTE]
     > Das Konto, unter dem die SQL Server-Instanz ausgeführt wird, beispielsweise NT-SERVICE\MSSQLSERVER, muss über Zugriff/Berechtigung für die oben angegebenen Verzeichnisse verfügen, damit die Installation erfolgreich durchgeführt werden kann. Ausführliche Informationen finden Sie unter [Konfigurieren von Datei System Berechtigungen für den Zugriff auf Datenbankmodul](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Wenn Sie auf "weiter" klicken, führt das Installationsprogramm Voraussetzungen und meldet, ob Probleme aufgetreten sind. Wenn alle Voraussetzungen überprüft werden, wird das Installationsprogramm zur Seite Cube-Konfiguration weitergeleitet. 
    
    > [!NOTE]
    > Wenn im Installationsprogramm eine Warnmeldung angezeigt wird, dass der SQL Server-Agentdienst für die SQL Server-Instanz des QoE-Archivs derzeit nicht ausgeführt wird, kann die Installation fortgesetzt werden, aber nach der Installation stellen Sie sicher, dass der SQL-Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf Automatisch, damit der geplante Auftrag ausgeführt wird. 
  
8. Geben Sie auf der Seite Cube-Konfiguration die folgenden Informationen an:
    
   - **QoE-Archiv-SQL Server-Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers festgelegt ist. Cube kann nur auf dem Computer installiert werden, auf dem die QoE-Archivdatenbank vorhanden ist (Hinweis. Cube selbst kann auf einem Remotecomputer installiert sein. Siehe unten)
    
   - **QoE-Archiv-SQL Server-Instanz:** Name der SQL Server-Instanz für die Position der QoE-Archivdatenbank. Wenn Sie eine standardmäßige SQL Server-Instanz angeben möchten, lassen Sie dieses Feld leer. Wenn Sie eine benannte SQL Server-Instanz angeben möchten, geben Sie den Namen der Instanz ein (z\". b. den Namen nach "). Wenn die QoE-Archivierungs Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab ausgefüllt.
    
   - **Cube Analysis-Server:** SQL Server Analysis Service-Instanzname für die Stelle, an der der Cube erstellt werden soll. Hierbei kann es sich um einen anderen Computer handeln, aber der Installationsbenutzer muss ein Mitglied der Serveradministratoren der Ziel-SQL Server-Analysis-Dienstinstanz sein.
    
     > [!NOTE]
     >  Weitere Informationen zum Konfigurieren von Analysis Services Server-Administratorberechtigungen finden Sie unter [Erteilen von Server Administratorberechtigungen (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx) .
  
   - **Verwenden mehrerer Partitionen:** Der Standardwert ist auf "mehrere Partitionen" eingestellt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert. Wählen Sie für Standard Edition die Option "einzelne Partition" aus. Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn einzelne Partitionen verwendet werden.
    
     > [!NOTE]
     >  Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden. Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "ändern" in der Systemsteuerung erneut installiert werden.
  
   - **Cube-Benutzer-Kennwort &amp; für Benutzer Name:** Name und Kennwort des Domänendienstkontos (maskiert), mit dem die Cube-Verarbeitung ausgelöst wird. Wenn die QoE-Archivierungs Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem Wert auf der Seite Archivkonfiguration für den SQL-Agentauftrag des Auftrags Benutzers ausgefüllt, es wird jedoch empfohlen, ein anderes Domänendienstkonto anzugeben, damit Setup dem das am wenigsten erforderliche Privileg.
    
9. Wenn Sie auf Weiter klicken, wird eine weitere Gültigkeitsprüfung durchgeführt, und es werden alle Probleme gemeldet. Nach dem erfolgreichen Abschluss der Überprüfung wird das Installationsprogramm zur Seite Portal-Konfiguration wechseln. 
    
10. Geben Sie auf der Seite Portal-Konfiguration die folgenden Informationen an:
    
    - **QoE-Archiv SQL Server:** Name der SQL Server-Instanz für die Position der QoE-Archivdatenbank. Beachten Sie, dass der Computername im Gegensatz zur Seite QoE-Archivkonfiguration und der Seite Cube-Konfiguration nicht festgelegt ist und bereitgestellt werden muss. Wenn die QoE-Archivierungs Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab ausgefüllt.
    
    - **Cube Analysis-Server:** SQL Server Analysis Service-Instanzname für die Position des Cubes. Wenn die Cube-Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite Cube-Konfiguration bereitgestellten Wert vorab gefüllt.
    
    - **Repository SQL Server:** SQL Server-Instanzname, in dem die Repository-Datenbank erstellt werden soll. Wenn der SQL Server-Instanzname für den Speicherort der QoE-Archivdatenbank zuvor in der Einrichtung (in anderen Komponenten) bereitgestellt wurde, wird dieses Feld mit dem SQL Server-Instanznamen der QoE-Archivdatenbank vorab ausgefüllt. Dies kann eine beliebige SQL Server-Instanz sein.
    
    - **Repository-Datenbank:** Standardmäßig ist die Option auf "neue Datenbank erstellen" eingestellt. Da die Repository-DB-Aktualisierung nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Repository-DB das gleiche Schema wie der zu installierende Build aufweist.
    
    - **Benutzer Name &amp; -Kennwort des IIS-App-Pools:** Das Konto, unter dem der IIS-Anwendungspool ausgeführt werden soll. Die Felder Benutzer Name und Kennwort werden abgeblendet, wenn integrierte Systemkonten ausgewählt sind. Diese Felder werden nur aktiviert, wenn im Dropdownfeld "andere" ausgewählt ist, damit der Benutzer die Informationen zum Domänendienstkonto eingeben kann.
    
11. Wenn Sie auf Weiter klicken, wird die abschließende Gültigkeitsprüfung durchgeführt, um sicherzustellen, dass die SQL Server-Instanzen über die bereitgestellten Anmeldeinformationen zugänglich sind und dass IIS auf dem Computer verfügbar ist. Nach dem erfolgreichen Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortfahren. 
    
Wenn das Installationsprogramm abgeschlossen ist, wird der SQL Server-Agent-Auftrag höchstwahrscheinlich ausgeführt, wobei das anfängliche Laden der QoE-Daten und die Cube-Verarbeitung durchgeführt wird. Je nach der Datenmenge in QoE steht dem Portal noch keine Daten zur Verfügung. Wenn Sie den Status der Datenauslastung und der Cube-Verarbeitung überprüfen möchten `http://<machinename>/CQD/#/Health`, wechseln Sie zu. 
> [!NOTE]
> Beachten Sie, dass die URL für die Überprüfung des Status der Download Cube-Verarbeitung Groß-/Kleinschreibung beachtet. Wenn Sie "Gesundheit" eingeben, funktioniert die URL nicht. Sie müssen "Gesundheit" am Ende der URL mit einem Großbuchstaben H eingeben. 
  
Wenn der Debugmodus aktiviert ist, werden detaillierte Protokollmeldungen angezeigt. Zum Aktivieren des Debugmodus wechseln Sie zu **%SystemDrive%\Programme\Gemeinsame Files\Skype for Business 2015 CQD\QoEDataService\web.config**, und aktualisieren Sie die folgende Zeile, damit der Wert auf **true**festgelegt ist:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Auf die Hauptseite des Portals `http://<machinename>/CQD`kann über zugegriffen werden. 
## <a name="managing-user-access-for-the-portal"></a>Verwalten des Benutzerzugriffs für das Portal

Für die Verwaltung der Benutzerautorisierung für das Portal empfehlen wir die Verwendung der URL-Autorisierung, die in IIS 7,0 eingeführt wurde. Weitere Informationen zur IIS-Sicherheit finden Sie unter [Grundlegendes zur IIS 7,0-URL-Autorisierung](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Jede Website oder Webanwendung erbt die für das gesamte IIS konfigurierte Standard-URL-Autorisierung, die in der Regel "alle Benutzer zulassen" lautet. Wenn der Zugriff auf das Portal restriktiver sein muss, können Administratoren den Zugriff nur für bestimmte Benutzergruppen gewähren, indem Sie die "Autorisierungsregeln" bearbeiten.
  
![Anrufqualität bereitstellen – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> Das Symbol "Autorisierungsregeln" darf nicht mit der ".NET-Autorisierung" im Abschnitt ASP.net verwechselt werden, bei dem es sich um einen anderen Autorisierungsmechanismus handelt. 
  
Administratoren sollten zunächst die geerbte Regel "alle Benutzer zulassen" entfernen. Dadurch wird verhindert, dass nicht autorisierte Benutzer auf das Portal zugreifen.
  
![CQD bereitstellen](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Als nächstes sollten Administratoren neue Zulassungsregeln hinzufügen und bestimmten Benutzern die Berechtigung für den Zugriff auf das Portal erteilen. Es wird empfohlen, eine lokale Gruppe mit dem Namen "CQDPortalUsers" zu erstellen, um die Benutzer zu verwalten.
  
![Anrufqualitäts-Dashboard bereitstellen](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Die Konfigurationsdetails werden in der Web. config-Datei gespeichert, die sich im physikalischen Verzeichnis des Portals befindet.
  
```XML
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

Im nächsten Schritt wird das Dashboard des CQD-Steuerpults konfiguriert. Nachdem Benutzer von IIS authentifiziert wurden, müssen Sie über Dateiberechtigungen für das CQD-Verzeichnis verfügen, um auf den Inhalt des Webportals zugreifen zu können. Es ist möglich, die ACLs über die Registerkarte Sicherheit der CQD-Verzeichniseigenschaften zu ändern, um einzelne Benutzer oder Gruppen hinzuzufügen. die empfohlene Vorgehensweise besteht jedoch darin, die Dateiberechtigungen unangetastet zu bleiben. Ändern Sie stattdessen die IIS-Einstellung, um den IIS-Workerprozess für den Zugriff auf das CQD-Verzeichnis zu verwenden, unabhängig davon, welche Benutzer authentifiziert werden. 
  
> [!IMPORTANT]
> Es ist wichtig, diese Einstellung nur für die CQD-Anwendung und nicht für die beiden API-Anwendungen zu ändern: QoEDataService und QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Konfigurieren des Dateizugriffs für das CQD (Dashboard)

1. Öffnen Sie den Konfigurations-Editor für CQD.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Wählen Sie unter Abschnitt die Option **System. Webserver/serverRuntime**aus.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Ändern Sie authenticatedUserOverride in **UseWorkerProcessUser**.
    
     ![Anrufqualitäts-Dashboard bereitstellen – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Klicken Sie auf der rechten Seite der Seite auf über **nehmen** .
    
## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-cqd-shows-no-data-after-deployment"></a>Das CQD zeigt nach der Bereitstellung keine Daten an.

Möglicherweise wird die folgende Fehlermeldung angezeigt:

*Die Abfrage konnte nicht ausgeführt werden, während Sie auf dem Cube ausgeführt wurde. Verwenden Sie den Abfrage-Editor, um die Abfrage zu ändern und Probleme zu beheben. Stellen Sie außerdem sicher, dass der Cube barrierefrei ist.*

Dies bedeutet, dass der Cube in SQL Server Analysis Services verarbeitet werden muss, bevor er in CQD verwendet wird. Führen Sie die folgenden Schritte aus, um dies zu beheben:

1. Öffnen Sie SQL Management Studio, und wählen Sie **Analysis Services**aus.

2. Erweitern Sie das **QoECube** -Objekt, wählen Sie **QoE-Metrik**aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Durchsuchen**aus. 

    Wenn dieser leere Browser zurückgibt, wurde der Cube noch nicht fortgesetzt.

3. Klicken Sie mit der rechten Maustaste auf **QoE Metric** angain, und wählen Sie **Prozess**aus.

4. Wenn die Verarbeitung abgeschlossen ist, klicken Sie erneut mit der rechten Maustaste auf das Objekt, und wählen Sie **Durchsuchen** aus, um zu bestätigen, dass auf der Browser Seite nun Daten angezeigt werden. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Benutzer haben Probleme beim anmelden, weil das Installationsprogramm die richtigen Einstellungen in IIS nicht erstellt hat.

In seltenen Fällen kann das Installationsprogramm die richtigen Einstellungen in IIS nicht erstellen. Eine manuelle Änderung ist erforderlich, damit Benutzer sich beim CQD anmelden können. Wenn Benutzer Probleme beim Anmelden haben, führen Sie die folgenden Schritte aus:
  
1. Öffnen Sie den IIS-Manager, und navigieren Sie zur Standardwebsite.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Klicken Sie auf "Authentifizierung". Wenn die Optionen "anonyme Authentifizierung", "ASP.NET-Identitätswechsel", "Formularauthentifizierung" und "Windows-Authentifizierung" nicht den nachstehenden Einstellungen entsprechen, ändern Sie diese manuell so, dass Sie den unten angegebenen Einstellungen entsprechen. Alle anderen Authentifizierungsmechanismen sollten deaktiviert sein.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Klicken Sie unter "Windows-Authentifizierung" auf der rechten Seite auf Erweiterte Einstellungen.
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Setzen Sie "Erweiterter Schutz" auf "akzeptieren", und aktivieren Sie das Kontrollkästchen "Kernel Modus-Authentifizierung aktivieren".
    
     ![Anrufqualitäts-Dashboard bereitstellen](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Wiederholen Sie die obigen Schritte für jeden der Einträge "CQD", "QoEDataService" und "QoERepositoryService" unter "Standardwebsite".
    
Für http-und HTTPS-Portbindungen erstellt das Installationsprogramm Portbindungen auf den Standardportnummern (Port 80 für http und Port 443 für HTTPS). Wenn auf dem Computer eine andere Website vorhanden ist, die diese Bindungen verwendet, tritt ein Konflikt auf, und das IIS-Verhalten kann nicht vorhergesagt werden. Die beste Methode, um dieses Problem zu vermeiden, besteht darin, sicherzustellen, dass vor der Installation von CQD keine anderen Websites den Anschlüssen 80 und 443 zugeordnet werden. 
  
So aktivieren Sie SSL/TLS in IIS und erzwingen, dass Benutzer über sicheres HTTPS und nicht über HTTP verbunden werden:
  
1. Konfigurieren von Secure Sockets Layer in IIS finden Sie unter [Konfigurieren von Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Wenn Sie fertig sind `http` , `https`ersetzen Sie durch.
    
2. Anweisungen zum Aktivieren von TLS in den SQL Server-Verbindungen finden Sie unter [Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe der Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).
    
## <a name="cube-sync-fails"></a>Fehler bei der Cube-Synchronisierung

Datenbank QoEMetrics werden kann einige ungültige Datensätze enthalten, die auf Endbenutzer Uhren basieren. Wenn die Zeitabweichung größer als 60 Jahre ist, schlägt der Cube-Import fehl.
  
 Überprüfen Sie die min-und Max-anfangs-EndTime mit den nachstehenden Optionen. Suchen und Löschen von Datensätzen in der Vergangenheit und in sehr ferner Zukunft können Sie ignoriert werden, und Sie werden die Synchronisierungsprozesse aufteilen.
  
- Wählen Sie min (Startzeit) in CqdPartitionedStreamView aus.
    
- Wählen Sie Max (Startzeit) von CqdPartitionedStreamView
    
- Wählen Sie min (EndTime) aus CqdPartitionedStreamView
    
- Wählen Sie Max (EndTime) aus CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Aufgaben nach der Installation

### <a name="importing-buildings-and-networks"></a>Importieren von Gebäuden und Netzwerken

Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:
  
1. Definieren von Gebäudetypen (empfohlen)
    
2. Definieren von Gebäude Besitztypen (empfohlen)
    
3. Definieren von Netzwerktypen (dringend empfohlen)
    
4. Importieren von Gebäuden (empfohlen)
    
5. Importieren von Subnetzen (empfohlen)
    
### <a name="define-building-types"></a>Definieren von Gebäudetypen

Gebäudetypen werden verwendet, um die verschiedenen Gebäude Definitionen oder-Typen in Ihrer Organisation zu beschreiben. 
  
> [!NOTE]
> Dieser Schritt ist optional, wird aber empfohlen. 
  
Beispiele
  
- Hauptsitz
    
- Remote Office
    
- Joint-Venture-Standort
    
  **SQL-Beispiel Syntax**
  
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
  
### <a name="define-building-ownership-types"></a>Definieren von Gebäude Besitztypen

Besitzer Typen werden zur Unterscheidung von Besitz-vs-leasingobjekten verwendet.
  
> [!NOTE]
> Dieser Schritt ist optional, wird aber empfohlen. 
  
Beispiele
  
- Von Contoso geleaste nicht&amp;-Re F
    
- Contoso vermietet re&amp;F
    
- Contoso-Besitzer
    
- Tochtergesellschaft geleast
    
  **SQL-Beispiel Syntax**
  
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

Netzwerktypen werden verwendet, um unterschiedliche Arten von Netzwerken innerhalb der Organisation zu beschreiben. Dadurch haben Sie die Möglichkeit, bestimmte Netzwerktypen zu filtern (oder zu filtern).
  
> [!NOTE]
> Es wird dringend empfohlen, Netzwerknamen zu definieren, aber es ist optional. Wenn Sie sich entscheiden, keine Netzwerknamen zu definieren, stellen Sie sicher, dass jeder CqdNetwork-Eintrag eine Building-0 (null) hat. 
  
Beispiele
  
- VPN
    
- Labor
    
  **SQL-Beispiel Syntax**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Die Parameter NetworkNameID und networkName sind erforderlich, der NetworkType-Parameter ist optional, wird aber empfohlen.
  
### <a name="import-buildings"></a>Importieren von Gebäuden

Durch das Importieren von Gebäuden erhalten Sie die Möglichkeit, gebäudespezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird aber empfohlen. 
  
Bevor Sie ein neues Gebäude importieren, sollten Sie bereits einen vordefinierten BuildingKey identifiziert haben. Geben Sie dazu den SQL-Befehl "Select Max (BuildingKey) from CqdBuilding" ein, um den aktuellen Wert zu identifizieren und dem Ergebnis 1 hinzuzufügen.
  
 **SQL-Beispiel Syntax**
  
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

Die Parameter BuildingKey, buildingname, BuildingShortName, OwnershipTypeId, BuildingTypeId sind erforderlich, die anderen Parameter sind optional.
  
### <a name="import-subnets"></a>Importieren von Subnetzen

Durch das Importieren von Gebäuden erhalten Sie die Möglichkeit, gebäudespezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird aber empfohlen. 
  
Importieren Sie Subnets, und ordnen Sie Sie den Gebäuden zu, die im letzten Schritt importiert wurden. Wenn Sie sich entschließen, "networkName" zu füllen, stellen Sie sicher, dass jeder Eintrag in dieser Tabelle eine NetworkNameID von 0 verwendet.
  
 **SQL-Beispiel Syntax**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

Die Parameter Netzwerk und UpdatedDate sind erforderlich, die anderen Parameter sind optional.
  
### <a name="optional-bssid"></a>Optional: BSSID

Durch das Auffüllen von BSSID-Informationen erhalten Sie zusätzliche WLAN-Datenstrom Korrelation per Controller oder Radio. Dies gilt zusätzlich zum Filtern nach Gebäude oder Subnetz. 
  
 **SQL-Beispiel Syntax**
  
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

**Details zu CqdBssidTable**

|**Wie in CQD**|**CQDBssid-Tabelle**|**Beispieleingaben**|
|:-----|:-----|:-----|
|AP NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (Sie müssen die getrennte Fformat verwenden)  <br/> |
|Controller  <br/> |Gebäude  <br/> |Aruba AP 7  <br/> |
|Gerät  <br/> |ess  <br/> |Controller1  <br/> |
|Radio  <br/> |phy  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Verarbeiten der importierten Daten

Standardmäßig werden nach dem Importieren von Gebäude-/Netzwerkdaten nur Datensätze angewendet, die nach diesem Zeitpunkt generiert wurden. 
  
Wenn Sie alle vorherigen Datensätze mit diesen neuen Daten kennzeichnen möchten, müssen Sie die gespeicherte Prozedur CqdUpdateBuilding ausführen, wie unten dargestellt: 
  
Geben Sie Ihr das Datum des ersten Eintrags (identifizieren Sie die Verwendung des Befehls min (Startzeit) aus CqdPartitionedStreamView SQL auswählen), ein EndDate von morgen und dann NULL für die letzten beiden Werte.
  
Sobald die Daten Datenstromdaten zugeordnet sind, muss der SSIS-Cube alle Datensätze erneut verarbeiten. Dies gilt auch, wenn Massen BSSID/ISP-Daten hinzugefügt werden. Stellen Sie sicher, dass "vollständiger Prozess" ausgewählt ist.
  

