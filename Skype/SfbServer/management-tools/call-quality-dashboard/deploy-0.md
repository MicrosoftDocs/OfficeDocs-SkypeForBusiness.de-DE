---
title: Bereitstellen des Anruf Qualitäts Dashboards für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Zusammenfassung: Hier erfahren Sie mehr über den Bereitstellungsprozess für das Anruf Qualitäts Dashboard. Das Anruf Qualitäts Dashboard ist ein Tool für Skype for Business Server.'
ms.openlocfilehash: d42d735ab5a60ec02ad2e1f4f696908996457c0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042262"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Bereitstellen des Anruf Qualitäts Dashboards für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über den Bereitstellungsprozess für das Anruf Qualitäts Dashboard. Das Anruf Qualitäts Dashboard ist ein Tool für Skype for Business Server.
  
## <a name="deployment-overview"></a>Übersicht über die Bereitstellung

Das Anruf Qualitäts Dashboard (CQD) besteht aus drei Hauptkomponenten:
  
- **Archivdatenbank**, in der die QoE-Daten (Quality of Experience) repliziert und gespeichert werden.
    
- **Cube**, in dem Daten aus QoE-Archivdatenbanken für einen optimierten und schnellen Zugriff aggregiert werden.
    
- **Portal**, in dem Benutzer QoE-Daten problemlos Abfragen und visualisieren können.
    
![CQD-Komponenten](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Der Setupvorgang für QoE-Archiven umfasst das Erstellen der QoE-Archivdatenbank, die Bereitstellung einer SQL Server gespeicherten Prozedur, die die Daten aus der Datenbank für QoE-Metriken in die QoE-Archivdatenbank verschiebt, und das Einrichten des SQL Server-Agent-Auftrags zum Ausführen der gespeicherten Prozedur in einem regulären Intervall. 
  
Die Cube-Bereitstellung ruft Informationen vom Benutzer auf der Position des QoE-Archivs ab, stellt den Cube bereit und richtet einen regulären SQL Server-Agent-Auftrag ein, mit dem der Cube in einem regulären Intervall aktualisiert wird.
  
Die Portal Installation erstellt eine Repository-Datenbank, in der die Zuordnung von CQD-Benutzern zu den Berichten/Abfragen jedes Benutzers gespeichert wird. Anschließend wird eine IIS-Webanwendung eingerichtet, die das Dashboard ist, in dem Benutzer eine vordefinierte Gruppe von Berichten anzeigen sowie ihre eigenen Abfragen anpassen und erstellen können, um Daten aus dem Cube zu visualisieren. Die Portal Installation erstellt zwei zusätzliche Webanwendungen, die APIs für Benutzer zur programmgesteuerten Zugriff auf das Repository und den Cube verfügbar macht. (Diese APIs werden auch intern vom Dashboard verwendet.)
  

|**Phase**|**Schritte**|**Rollen und Gruppenmitgliedschaft**|**Dokumentation**|
|:-----|:-----|:-----|:-----|
|Installieren Sie die erforderliche Hardware und Software.  <br/> |Entscheiden Sie sich für die CQD-Konfiguration, und wählen Sie einen SQL Server aus, aus dem die Installation ausgeführt werden soll.  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Abschnitt "Anforderungen vor der Installation" in der Bereitstellungsdokumentation.  <br/> |
|Installieren Sie CQD.  <br/> |Führen Sie die MSI-Datei nach dem Bereitstellungs Dokument aus.  <br/> |Um das Setup durchführen zu können, muss das Installationskonto ein Domänenbenutzer sein, der Mitglied der lokalen Gruppe Administratoren ist und über Lesezugriff auf die Datenbank für QoE-Metriken auf der Monitoring Server verfügt.  <br/> |Abschnitte "Konten und Bereitstellungsschritte" in der Bereitstellungsdokumentation.  <br/> |
|Erteilen Sie dem Benutzer Zugriff.  <br/> |Für die Verwaltung der Benutzerautorisierung im Portal wird die Verwendung der URL-Autorisierung empfohlen, die in IIS 7,0 eingeführt wurde. Weitere Informationen finden Sie unter [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist.  <br/> |Verwalten des Benutzerzugriffs für den Portal Abschnitt in der Bereitstellungsdokumentation.  <br/> |
|Optional: Geben Sie Informationen zur Subnetz-Zuordnung an.  <br/> |Füllen Sie Netzwerk-und Gebäude Zuordnungstabellen in der QoE-Archivdatenbank auf.  <br/> |Ein Konto mit Schreibzugriff auf die QoE-Archivdatenbank.  <br/> |Abschnitt "Bereitstellen von Subnetz-Informationen" in der Benutzerdokumentation.  <br/> |
   


Die Bereitstellung des Anruf Qualitäts Dashboards umfasst das Einrichten der Infrastruktur und die Installation der Software. Im folgenden Verfahren wird der Prozess beschrieben.
  
## <a name="deployment-steps"></a>Bereitstellungsschritte

1. Kopieren Sie die Datei CallQualityDashboard. msi auf den Computer, auf dem die Archivdaten Bank Komponente von CQD installiert werden soll (Dies ist der Computer, auf dem SQL Server installiert ist). 
    
2. Führen Sie die MSI-Verwaltungskonsole aus (Windows wird aufgefordert, die Ausführung mit Administratorrechten auszuführen). 
    
3. Akzeptieren Sie den EULA.
    
4. Wählen Sie den Zielordner aus, in dem Dateien im Zusammenhang mit den Dashboard-Komponenten für die Anrufqualität gefunden werden, oder übernehmen Sie den Standardspeicherort.
    
5. Wählen Sie alle Features aus.
    
6. Geben Sie auf der Seite QoE-Archivkonfiguration die folgenden Informationen an:
    
   - **QoE-Metriken SQL Server:** SQL Server Instanzname, in dem sich die QoE-Metriken DB befindet (Dies ist die Datenquelle).
    
   - **QoE-Archiv SQL Server Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers fixiert ist. Die Archivdatenbank kann nur auf dem lokalen Computer installiert werden.
    
   - **QoE-Archiv SQL Server Instanz:** Ein Name der lokalen SQL Server Instanz, in der die Archivdatenbank erstellt werden soll. Wenn Sie eine Standard SQL Server Instanz verwenden möchten, lassen Sie dieses Feld leer. Um eine benannte SQL Server Instanz zu verwenden, geben Sie den Namen der Instanz an (beispielsweise den\"Namen nach dem ").
    
   - **QoE-Archivdatenbank:** Diese Option ist standardmäßig auf "neue Datenbank erstellen" festgelegt. Da das Archiv-DB-Upgrade nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Archivdatenbank das gleiche Schema wie das zu installierende Build aufweist.
    
   - **Datenbankdatei Verzeichnis:** Pfad zu dem Speicherort, an dem die Datenbankdateien (MDF und LDF) für die Archivdatenbank gespeichert werden sollen. Dies sollte sich auf einem Laufwerk (in der empfohlenen Hardwarekonfiguration) befinden, das sich vom Betriebssystem getrennt HDD2. Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, um mögliche Konflikte zu vermeiden, empfohlen wird, ein leeres Verzeichnis ohne Dateien zu verwenden.
    
   - **Verwenden Sie mehrere Partitionen:** Der Standardwert ist auf "Multiple Partition" festgelegt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert. Wählen Sie für Standard Edition die Option "einzelne Partition" aus. Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn eine einzelne Partition verwendet wird.
    
     > [!NOTE]
     > Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden. Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "Change" in der Systemsteuerung erneut installiert werden. 
  
   - **Partitionsdatei Verzeichnis:** Pfad zu dem Speicherort, an dem die Partitionen für die QoE-Archivdatenbank gespeichert werden sollen. Dies sollte sich auf einem Laufwerk (in der empfohlenen Hardwarekonfiguration) befinden, das sich von dem Laufwerk "OS Drive" (HDD3) und dem SQL-Datenbankprotokolldateien unterscheidet. Beachten Sie, dass, da die Dateinamen in der Installation behoben werden, um mögliche Konflikte zu vermeiden, empfohlen wird, ein leeres Verzeichnis ohne Dateien zu verwenden.
    
   - **SQL-Agent-Auftrags Benutzer – &amp; Benutzernamen Kennwort:** Domänendienstkonto Name und Kennwort (maskiert), die verwendet werden, um den Schritt "QoE-Archivdaten" des SQL Server-Agent-Auftrags auszuführen (mit dem die gespeicherte Prozedur ausgeführt wird, um Daten aus QoE-Metriken DB in die Archivdatenbank zu übertragen, sodass dieses Konto über Lesezugriff auf QoE-Metriken verfügt, wie unter Konten Abschnitt dargestellt. Dieses Konto muss außerdem über eine Anmeldung im QoE-Archiv SQL Server Instanz) verfügen.
    
     > [!NOTE]
     > Das Konto, unter dem die SQL Server Instanz ausgeführt wird, beispielsweise NT SERVICE\MSSQLSERVER, muss Zugriff/Berechtigung für die oben angegebenen Verzeichnisse haben, damit die Installation erfolgreich abgeschlossen werden kann. Ausführliche Informationen finden Sie unter [configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)
  
7. Wenn Sie auf Weiter klicken, führt das Installationsprogramm vorab erforderliche Prüfungen durch und meldet, wenn Probleme auftreten. Wenn alle Voraussetzungen überprüft werden, wird das Installationsprogramm zur Seite mit der Cube-Konfiguration weitergeleitet. 
    
    > [!NOTE]
    > Wenn das Installationsprogramm eine Warnmeldung anzeigt, dass der SQL Server Agent-Dienst für die QoE-Archiv SQL Server Instanz derzeit nicht ausgeführt wird, kann die Installation fortgesetzt werden, aber nach der Installation stellen Sie sicher, dass der SQL Agent-Dienst ausgeführt wird, und legen Sie den Starttyp auf Automatisch, sodass der geplante Auftrag ausgeführt wird. 
  
8. Geben Sie auf der Seite Cube-Konfiguration die folgenden Informationen ein:
    
   - **QoE-Archiv SQL Server Name:** Hierbei handelt es sich um ein schreibgeschütztes Feld, das auf den vollqualifizierten Domänennamen des lokalen Computers fixiert ist. Cube kann nur auf dem Computer installiert werden, auf dem die QoE-Archivdatenbank vorhanden ist (Hinweis. Cube selbst kann auf einem Remotecomputer installiert werden. Siehe unten)
    
   - **QoE-Archiv SQL Server Instanz:** SQL Server Name der Instanz, in der sich die QoE-Archiv-DB befindet. Lassen Sie dieses Feld leer, um eine Standard SQL Server Instanz anzugeben. Geben Sie zum Angeben einer benannten SQL Server Instanz den Namen der Instanz ein (beispielsweise den Namen nach\"dem "). Wenn die QoE-Archiv Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab aufgefüllt.
    
   - **Cube Analysis Server:** SQL Server Name der Analysis Services-Instanz, unter der der Cube erstellt werden soll. Hierbei kann es sich um einen anderen Computer handeln, aber der Installationsbenutzer muss Mitglied der Server Administratoren der Ziel-SQL Server Analysis Service-Instanz sein.
    
     > [!NOTE]
     >  Weitere Informationen zum Konfigurieren von Analysis Services Server-Administratorberechtigungen finden Sie unter [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)
  
   - **Verwenden Sie mehrere Partitionen:** Der Standardwert ist auf "Multiple Partition" festgelegt, was Business Intelligence Edition oder Enterprise Edition von SQL Server erfordert. Wählen Sie für Standard Edition die Option "einzelne Partition" aus. Beachten Sie, dass die Leistung der Cube-Verarbeitung beeinträchtigt werden kann, wenn eine einzelne Partition verwendet wird.
    
     > [!NOTE]
     >  Die Option Auswahl für mehrere Partitionen verwenden kann nach Abschluss des Setups nicht mehr geändert werden. Um Sie zu ändern, muss das Cube-Feature zunächst deinstalliert und dann mithilfe der Option "Change" in der Systemsteuerung erneut installiert werden.
  
   - **Cube-Benutzer – Benutzer &amp; Namen Kennwort:** Domänendienstkonto Name und Kennwort (maskiert), mit denen die Verarbeitung des Cubes ausgelöst wird. Wenn die QoE-Archiv Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite Archivierungskonfiguration für den SQL-Agent-Auftrags Benutzer bereitgestellten Wert vorab aufgefüllt, es wird jedoch empfohlen, ein anderes Domänendienstkonto anzugeben, damit das Setup die die am wenigsten erforderliche Berechtigung dafür.
    
9. Wenn Sie auf Weiter klicken, wird eine weitere Validierungs Runde ausgeführt, und jedes Problem wird gemeldet. Nach erfolgreichem Abschluss der Überprüfung wird das Installationsprogramm zur Seite Portal Konfiguration wechseln. 
    
10. Geben Sie auf der Seite Portal Konfiguration die folgenden Informationen an:
    
    - **QoE-Archiv SQL Server:** SQL Server Name der Instanz, in der sich die QoE-Archivdatenbank befindet. Beachten Sie, dass der Computername im Gegensatz zur Konfigurationsseite von QoE-Archiven und der Seite Cube-Konfiguration nicht festgelegt und angegeben werden muss. Wenn die QoE-Archiv Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite QoE-Archivkonfiguration bereitgestellten Wert vorab aufgefüllt.
    
    - **Cube Analysis Server:** SQL Server Name der Analysis Services-Instanz, für den der Cube gespeichert ist. Wenn die Cube-Komponente für die Installation ausgewählt wurde, wird dieses Feld mit dem auf der Seite Cube-Konfiguration bereitgestellten Wert vorab aufgefüllt.
    
    - **Repository-SQL Server:** SQL Server Instanzname, in dem die Repository-Datenbank erstellt werden soll. Wenn der Name der SQL Server Instanz, in der sich die QoE-Archivdatenbank befindet, zuvor in der Einrichtung (in anderen Komponenten) bereitgestellt wurde, wird dieses Feld vorab mit dem Namen der QoE-Archiv-DB-SQL Server Instanz aufgefüllt. Hierbei kann es sich um eine beliebige SQL Server Instanz handeln.
    
    - **Repository-Datenbank:** Standardmäßig ist die Option auf "neue Datenbank erstellen" festgelegt. Da das Repository-DB-Upgrade nicht unterstützt wird, ist der einzige Umstand, unter dem die Option "vorhandene Datenbank verwenden" verwendet werden kann, wenn die vorhandene Repository-DB das gleiche Schema wie das zu installierende Build aufweist.
    
    - **Benutzer Name &amp; Kennwort des IIS-App-Pools:** Das Konto, unter dem der IIS-Anwendungspool ausgeführt werden soll. Die Felder Benutzer Name und Kennwort werden abgeblendet, wenn integrierte Systemkonten ausgewählt sind. Diese Felder werden nur aktiviert, wenn im Dropdownfeld andere ausgewählt ist, damit der Benutzer die Informationen zum Domänendienstkonto eingeben kann.
    
11. Wenn Sie auf Weiter klicken, wird die abschließende Runde der Überprüfung durchgeführt, um sicherzustellen, dass auf die SQL Server Instanzen mithilfe der bereitgestellten Anmeldeinformationen zugegriffen werden kann und dass IIS auf dem Computer verfügbar ist. Nach erfolgreichem Abschluss der Überprüfung wird das Installationsprogramm mit dem Setup fortfahren. 
    
Wenn das Installationsprogramm fertig ist, wird wahrscheinlich der SQL Server-Agent-Auftrag ausgeführt, wobei die anfängliche Auslastung der QoE-Daten und die Verarbeitung des Cubes erfolgt. Je nach Datenmenge in QoE stehen dem Portal keine Daten zur Verfügung, die noch angezeigt werden können. Wechseln Sie zum Überprüfen des Status der Daten-und Cube-Verarbeitung zu `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Beachten Sie, dass bei der URL zum Überprüfen des Status der Download Cube-Verarbeitung die Groß-/Kleinschreibung beachtet wird. Wenn Sie "Integrität" eingeben, kann die URL nicht verwendet werden. Sie müssen "Integrität" am Ende der URL mit einem Haupt-H eingeben. 
  
Wenn der Debugmodus aktiviert ist, werden ausführliche Protokollmeldungen angezeigt. Wechseln Sie zum Aktivieren des Debugmodus zu **%SystemDrive%\Programme\Gemeinsame Files\Skype for Business 2015 CQD\QoEDataService\web.config**, und aktualisieren Sie die folgende Folge, sodass der Wert auf **true**festgelegt ist:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

Die Hauptportal Seite ist über `http://<machinename>/CQD`verfügbar. 
## <a name="managing-user-access-for-the-portal"></a>Verwalten des Benutzerzugriffs für das Portal

Für die Verwaltung der Benutzerautorisierung im Portal wird die Verwendung der URL-Autorisierung empfohlen, die in IIS 7,0 eingeführt wurde. Weitere Informationen zur IIS-Sicherheit finden Sie unter [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Jede Website oder Webanwendung erbt die standardmäßige URL-Autorisierung, die für den gesamten IIS konfiguriert ist, in der Regel "alle Benutzer zulassen". Wenn der Zugriff auf das Portal restriktiver sein muss, können Administratoren nur Zugriff auf die bestimmte Benutzergruppe gewähren, indem Sie die "Autorisierungsregeln" bearbeiten.
  
![Bereitstellen der Anrufqualität – Autorisierungsregeln in IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> Das Symbol für Autorisierungsregeln ist nicht mit der ".NET-Autorisierung" im Abschnitt ASP.net zu verwechseln, bei dem es sich um einen anderen Autorisierungsmechanismus handelt. 
  
Administratoren sollten zunächst die geerbte Regel "alle Benutzer zulassen" entfernen. Dadurch wird verhindert, dass nicht autorisierte Benutzer auf das Portal zugreifen.
  
![Bereitstellen von CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Als nächstes sollten Administratoren neue Zulassungsregeln hinzufügen und bestimmten Benutzern die Berechtigung für den Zugriff auf das Portal erteilen. Es wird empfohlen, eine lokale Gruppe mit dem Namen "CQDPortalUsers" zum Verwalten der Benutzer zu erstellen.
  
![Bereitstellen des Anruf Qualitäts Dashboards](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Die Konfigurationsdetails werden in der Datei "Internet. config" gespeichert, die sich im physikalischen Verzeichnis des Portals befindet.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

Der nächste Schritt besteht darin, das Dashboard des CQD zu konfigurieren. Nachdem Benutzer von IIS authentifiziert wurden, müssen Sie über Dateiberechtigungen für das CQD-Verzeichnis verfügen, um auf den Inhalt des Webportals zugreifen zu können. Es ist möglich, die ACLs über die Registerkarte Sicherheit der CQD-Verzeichniseigenschaften zu ändern, um einzelne Benutzer oder Gruppen hinzuzufügen. die empfohlene Vorgehensweise besteht jedoch darin, die Dateiberechtigungen unberührt zu lassen. Ändern Sie stattdessen die IIS-Einstellung so, dass der IIS-Arbeitsprozess für den Zugriff auf das CQD-Verzeichnis verwendet wird, unabhängig davon, welcher Benutzer authentifiziert ist. 
  
> [!IMPORTANT]
> Es ist wichtig, diese Einstellung nur für die CQD-Anwendung und nicht für die beiden API-Anwendungen zu ändern: im und QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Konfigurieren des Dateizugriffs für das CQD (Dashboard)

1. Öffnen Sie den Konfigurations-Editor für CQD.
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Wählen Sie unter Abschnitt **System. Webserver/serverRuntime**.
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Ändern Sie authenticatedUserOverride in **UseWorkerProcessUser**.
    
     ![Bereitstellen des Anruf Qualitäts Dashboards – Konfigurations-Editor](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Klicken Sie auf der rechten Seite auf **Apply** .
    
## <a name="known-issues"></a>Bekannte Probleme

### <a name="the-cqd-shows-no-data-after-deployment"></a>Das CQD zeigt nach der Bereitstellung keine Daten

Möglicherweise wird die folgende Fehlermeldung angezeigt:

*Die Abfrage konnte nicht ausgeführt werden, während Sie im Cube ausgeführt wird. Verwenden Sie den Abfrage-Editor, um die Abfrage zu ändern und Probleme zu beheben. Stellen Sie außerdem sicher, dass auf den Cube zugegriffen werden kann.*

Dies bedeutet, dass der Cube vor der Verwendung in CQD in SQL Server Analysis Services verarbeitet werden muss. Sie können dieses Problem beheben, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie SQL Management Studio, und wählen Sie **Analysis Services**aus.

2. Erweitern Sie das **QoECube** -Objekt, wählen Sie **QoE Metric**aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Durchsuchen**. 

    Wenn dieser leere Browser zurückgibt, wurde der Cube noch nicht fortgesetzt.

3. Klicken Sie mit der rechten Maustaste auf **QoE Metric** angain, und wählen Sie **Prozess**.

4. Wenn die Verarbeitung abgeschlossen ist, klicken Sie mit der rechten Maustaste erneut auf das Objekt, und wählen Sie **Durchsuchen** aus, um zu bestätigen, dass auf der Browser Seite nun Daten angezeigt werden. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Benutzer haben Probleme bei der Anmeldung, da das Installationsprogramm nicht die richtigen Einstellungen in IIS erstellt.

In seltenen Fällen kann das Installationsprogramm nicht die richtigen Einstellungen in IIS erstellen. Manuelle Änderungen sind erforderlich, damit sich Benutzer bei der CQD anmelden können. Wenn Benutzer Probleme beim Anmelden haben, führen Sie die folgenden Schritte aus:
  
1. Öffnen Sie den IIS-Manager, und navigieren Sie zur Standardwebsite.
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Klicken Sie auf "Authentifizierung". Wenn die "anonyme Authentifizierung", "ASP.NET-Identitätswechsel", "Formularauthentifizierung" und "Windows-Authentifizierung" nicht mit den unten gezeigten Einstellungen übereinstimmen, müssen Sie Sie manuell ändern, damit Sie den unten angegebenen Einstellungen entsprechen. Alle anderen Authentifizierungsmechanismen sollten deaktiviert werden.
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Klicken Sie für "Windows-Authentifizierung" auf der rechten Seite auf Erweiterte Einstellungen.
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Legen Sie "Extended Protection" so fest, dass die Option "Kernel Modus-Authentifizierung aktivieren" aktiviert ist.
    
     ![Bereitstellen des Anruf Qualitäts Dashboards](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Wiederholen Sie die obigen Schritte für jeden der Einträge "CQD", "im" und "QoERepositoryService" unter "Default Web Site".
    
Für http-und HTTPS-Portbindungen erstellt das Installationsprogramm Portbindungen für die Standardportnummern (Port 80 für http und Port 443 für HTTPS). Wenn auf dem Computer eine andere Website vorhanden ist, die diese Bindungen verwendet, tritt ein Konflikt auf, und das IIS-Verhalten kann nicht vorhergesagt werden. Am besten vermeiden Sie dieses Problem, indem Sie sicherstellen, dass keine anderen Websites den Ports 80 und 443 vor der Installation von CQD zugeordnet werden. 
  
So aktivieren Sie SSL/TLS in IIS und erzwingen, dass Benutzer über sicheres HTTPS anstelle von http eine Verbindung herstellen:
  
1. Konfigurieren von Secure Sockets Layer in IIS finden Sie unter [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx). Ersetzen `http` Sie einmal durch `https`.
    
2. Anweisungen zum Aktivieren von TLS in den SQL Server-Verbindungen finden Sie unter [Aktivieren der SSL-Verschlüsselung für eine Instanz von SQL Server mithilfe der Microsoft Management Console](https://support.microsoft.com/kb/316898/).
    
## <a name="cube-sync-fails"></a>Cube-Synchronisierung schlägt fehl

QoEMetrics kann einige ungültige Datensätze enthalten, die auf Endbenutzer Uhren basieren. Wenn die Zeitabweichung größer als 60 Jahre ist, tritt beim Cube-Import ein Fehler auf.
  
 Überprüfen Sie die min-und Max-StartTime/EndTime mit den unten aufgeführten Optionen. Suchen nach und Löschen von Datensätzen in der fernen und sehr ferneren Zukunft können Sie ignoriert werden, und Sie werden die Synchronisierungsprozesse aufheben.
  
- Wählen Sie min (StartTime) aus CqdPartitionedStreamView
    
- Wählen Sie Max (StartTime) aus CqdPartitionedStreamView
    
- Wählen Sie min (EndTime) aus CqdPartitionedStreamView
    
- Wählen Sie Max (EndTime) aus CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Aufgaben nach der Installation

### <a name="importing-buildings-and-networks"></a>Importieren von Gebäuden und Netzwerken

Führen Sie nach der Installation von CQD die folgenden Konfigurationsaufgaben aus:
  
1. Definieren von Gebäudetypen (empfohlen)
    
2. Definieren von Besitzer Typen für Gebäude (empfohlen)
    
3. Definieren von Netzwerktypen (dringend empfohlen)
    
4. Importieren von Gebäuden (empfohlen)
    
5. Subnetze importieren (empfohlen)
    
### <a name="define-building-types"></a>Definieren von Gebäudetypen

Gebäudetypen werden verwendet, um die verschiedenen Gebäude Definitionen oder-Typen in Ihrer Organisation zu beschreiben. 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Zentrale
    
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
  
### <a name="define-building-ownership-types"></a>Definieren von Besitzer Typen für Gebäude

Besitzer Typen werden verwendet, um Besitz-und Leasingobjekte zu unterscheiden.
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Beispiele
  
- Contoso-Leased Non-&amp;Re F
    
- Contoso-Leased&amp;Re F
    
- Contoso-Besitzer
    
- Tochterunternehmen geleast
    
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

Netzwerktypen werden verwendet, um verschiedene Typen von Netzwerken innerhalb der Organisation zu beschreiben. Auf diese Weise können Sie bestimmte Netzwerktypen filtern oder filtern.
  
> [!NOTE]
> Es wird dringend empfohlen, Netzwerknamen zu definieren, ist aber optional. Wenn Sie keine Netzwerknamen definieren möchten, stellen Sie sicher, dass für jeden CqdNetwork-Eintrag eine Build-Nr von 0 festgelegt ist. 
  
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

Die Parameter NetworkNameID und networkName sind erforderlich, der Parameter NetworkType ist optional, wird jedoch empfohlen.
  
### <a name="import-buildings"></a>Importieren von Gebäuden

Durch das Importieren von Gebäuden haben Sie die Möglichkeit, spezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Bevor Sie ein neues Gebäude importieren, sollten Sie bereits eine vordefinierte BuildingKey identifiziert haben. Geben Sie dazu den SQL-Befehl "Max (BuildingKey) aus CqdBuilding" aus, um den aktuellen Wert zu identifizieren und dem Ergebnis 1 hinzuzufügen.
  
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

Durch das Importieren von Gebäuden haben Sie die Möglichkeit, spezifische Einblicke zu erhalten (schlechte Anrufe pro Gebäude auf WiFi/Wired usw.). 
  
> [!NOTE]
> Dieser Schritt ist optional, wird jedoch empfohlen. 
  
Importieren Sie Subnetze, und ordnen Sie Sie den im letzten Schritt importierten Gebäuden zu. Wenn Sie networkName nicht auffüllen möchten, stellen Sie sicher, dass für jeden Eintrag in dieser Tabelle ein NetworkNameID von 0 verwendet wird.
  
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

Die Parameter "Network" und "UpdatedDate" sind erforderlich, die anderen Parameter sind optional.
  
### <a name="optional-bssid"></a>Optional: BSSID

Durch das Auffüllen von BSSID-Informationen erhalten Sie zusätzliche WLAN-Datenstrom Korrelation durch Controller oder Radio. Dies ist zusätzlich zum Filtern nach Gebäude oder Subnetz. 
  
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

**CqdBssidTable-Details**

|**Wie in CQD gezeigt**|**CQDBssid-Tabelle**|**Beispieleingaben**|
|:-----|:-----|:-----|
|AP-NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (Sie müssen das getrennte Fformat verwenden)  <br/> |
|Controller  <br/> |Erstellen  <br/> |Aruba AP 7  <br/> |
|Gerät  <br/> |ESS  <br/> |Controller1  <br/> |
|Radio  <br/> |PHY  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Verarbeiten der importierten Daten

Standardmäßig wird nach dem Importieren von Gebäude-/Netzwerkdaten nur auf Datensätze angewendet, die nach diesem Zeitpunkt generiert wurden. 
  
Um alle vorherigen Datensätze mit diesen neuen Daten zu markieren, müssen Sie die gespeicherte Prozedur CqdUpdateBuilding wie unten gezeigt ausführen: 
  
Geben Sie ihm das Datum Ihres ersten Datensatzes (identifizieren Sie anhand des SQL-Befehls Select min (StartTime) aus CqdPartitionedStreamView), ein EndDate von morgen, dann NULL für die letzten beiden Werte.
  
Nachdem die Daten Datenstromdaten zugeordnet wurden, muss der SSIS-Cube alle Datensätze erneut verarbeiten. Dies gilt auch beim Massen Hinzufügen von BSSID/ISP-Daten. Stellen Sie sicher, dass "vollständig verarbeiten" ausgewählt ist.
  

