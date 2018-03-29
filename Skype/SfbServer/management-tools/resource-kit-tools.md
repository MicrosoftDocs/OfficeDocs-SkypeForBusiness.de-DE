---
title: Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: In diesem Thema werden die Tools in der Skype für Business Server 2015 Resource Kit, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung beschrieben. Die Skype für Business Server 2015 Resource Kit können Sie Routineaufgaben für IT-Administratoren erleichtern, die Bereitstellung und Verwaltung von Skype für Business Server 2015. Beispielsweise kann das Tool Web Conf Daten verwendet werden, auf einfache Weise Daten steuern, die Benutzer während einer onlinebesprechung hochgeladen wird. Das Tool SEFAUtil kann zum Einrichten von Delegaten Anruf weiterleiten und-Annahme für Benutzer verwendet werden. Wir empfehlen IT-Administratoren mit diesen Tools Skype für Business Server 2015 effektiver verwalten.
ms.openlocfilehash: 8367400ea7730eabbd2686c3bb2b7c16cdf9a1f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015
 
In diesem Thema werden die Tools in der Skype für Business Server 2015 Resource Kit, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung beschrieben. Die Skype für Business Server 2015 Resource Kit können Sie Routineaufgaben für IT-Administratoren erleichtern, die Bereitstellung und Verwaltung von Skype für Business Server 2015. Beispielsweise kann das Tool **Web Conf Data** verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden. Mithilfe des **SEFAUtil**-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten. Wir empfehlen IT-Administratoren mit diesen Tools Skype für Business Server 2015 effektiver verwalten.
  
## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Um die Skype für Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) aus dem Download Center herunter.
  
Führen Sie **OCSResKit.msi ** aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Tools im folgenden Pfad: **%ProgramFiles%\Skype for Business Server 2015\ResKit**. Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner. Tools, die über Hilfsdateien verfügen, befinden sich in eigenen Unterordnern.
  
## <a name="supported-environments"></a>Unterstützte Umgebungen

Auf einem Server, der für Skype für Business Server 2015, normalerweise auf einem verwendet wird, um das Ausführen von Skype für Business Server 2015 benötigt erfüllt, sollte die Skype für Business Server 2015 Resource Kit installiert werden.
  
## <a name="resource-kit-tools-overview"></a>Resource Kit-Tools – Übersicht

Es folgt eine Liste der Tools, die in der Skype für Business Server 2015 Resource Kit bereitgestellt werden. Im folgenden Abschnitt wird jedes Tool mit seinen Anforderungen und Beispielanwendungen beschrieben.
  
- [ABSConfig](resource-kit-tools.md#ABSConfig)
    
- [Bandwidth Policy Service Monitor](resource-kit-tools.md#bpsm)
    
- [Bandwidth Utilization Analyzer](resource-kit-tools.md#bua)
    
- [Call Parkometer](resource-kit-tools.md#callpark)
    
- [DBAnalyze](resource-kit-tools.md#dba)
    
- [Import Storage Service Data](resource-kit-tools.md#Issd)
    
- [LCSSync](resource-kit-tools.md#LCSSync)
    
- [Lookup User Console](resource-kit-tools.md#LUC)
    
- [MsTurnPing](resource-kit-tools.md#MsTurnPing)
    
- [Network Configuration Viewer](resource-kit-tools.md#NCV)
    
- [Response Group Agent Live](resource-kit-tools.md#RGAL)
    
- [SEFAUtil](resource-kit-tools.md#SEFAUtil)
    
- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)
    
- [Unassigned Number Announcements Migration](resource-kit-tools.md#UNAM)
    
- [Web Conf Data](resource-kit-tools.md#WebConfData)
    
## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

Das Dienst Adressbuchkonfiguration-Tool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren Adressbuchdienst-Konfiguration in Skype für Business Server 2015 anpassen kann. Mit diesem Tool können außerdem Skype für Business Server 2015 Administratoren die Standardeinstellungen für den Adressbuchdienst wiederherstellen.
  
### <a name="description"></a>Beschreibung

ABSConfig ist eine graphical User Interface-Anwendung, die ermöglicht Administratoren, Active Directory Domain Services Attribute konfigurieren, die im Zusammenhang mit Adressbuchdienst.
  
Dies sind die primären Verwendungsszenarien für das Tool:
  
- So aktivieren Sie Administratoren Attribute in Active Directory-Domänendiensten die Attribute für Skype für Business Server 2015 zuzuordnen.
    
- Administratoren das Angeben des Attributs in Active Directory Domain Services ermöglichen, das in die Adressbuchdienst-Dateien aufgenommen oder aus diesen ausgeschlossen werden soll
    
- Administratoren das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts ermöglichen
    
Das Tool ABSConfig kann mithilfe der Datei ABSConfig.exe gestartet werden. Das Tool zur Registerkarte **Attribute konfigurieren** wird geöffnet. Diese Tabelle enthält die Optionen zum Zuordnen von Attribute von Active Directory-Domänendienste zu Attributfelder für Skype für Business Server 2015 und welche Benutzer ein-oder ausschließen in Adressbuchdienst-Dateien basierend auf bestimmten Attribut Filter angeben. Außerdem bietet die Optionen zum Anpassen der Wert der Telefonnummer an, die in der Adressbuch-Datei eingeschlossen werden. Die Option **Wiederherstellen** kann Administratoren Adressbuchdienst Standardwerte wiederherstellen.
  
### <a name="output"></a>Ausgabe

ABSConfig speichert die Konfiguration des Adressbuchdiensts in der Datenbank.
  
```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Verwendungszweck

ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen von Skype für Business Server 2015 Adressbuchdienst.
  
### <a name="requirements"></a>Anforderungen

#### <a name="computer"></a>Computer

ABSConfig kann nur von einer Domäne gehörenden Computer ausgeführt werden, Skype für Business Server 2015 installiert sind. Im Fall von Skype für Business Server 2015, Enterprise Edition, kann dieses Tool auf jedem Front-End-Server ausgeführt werden, die den Adressbuchdienst während des Setups aktiviert haben.
  
#### <a name="network"></a>Netzwerk

Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.
  
#### <a name="software"></a>Software

Die folgenden Softwarekomponenten müssen vor der Ausführung des ABSConfig-Tools installiert werden:
  
- Skype for Business Server 2015
    
#### <a name="users"></a>Benutzer

Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der Skype für Business Server 2015 Bereitstellung.
  
### <a name="examples"></a>Beispiele

ABSConfig kann durch Eingeben von **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie eine Abbildung der Benutzeroberfläche des ABSConfig-Tools.
  
![Das Tool ABSConfig.exe](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)
  
### <a name="summary"></a>Zusammenfassung

Das Tool ABSConfig bietet Administratoren ein schnelles und einfach zu verwendenden Tools zum Anpassen von Skype für Business Server 2015 Adressbuchdienst.
  
## <a name="bandwidth-policy-service-monitor"></a>Bandwidth Policy Service Monitor
<a name="bpsm"> </a>

Mit dem Tool Bandwidth Policy Service Monitor können Administratoren eine Liste der folgenden Elemente anzeigen:
  
1. Alle konfigurierten Skype für Business Server 2015 Bandbreitenrichtlinie Services (Authentifizierung und Core) in der Topologie
    
2. Die Verbindungen, die jeder Dienst mit anderen Bandbreiten-Richtliniendiensten und Edgeservern herstellt
    
3. Alle Verbindungen, die im Netzwerkkonfigurationsdokument konfiguriert sind, und die von den einzelnen Bandbreiten-Richtliniendiensten gemeldete Echtzeit-Bandbreitennutzung
    
### <a name="description"></a>Beschreibung

Das Tool Bandwidth Policy Service Monitor ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Administratoren starten das Tool durch Ausführen der Datei „PDPMonUI.exe“.
  
Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreiten-Richtliniendienste in der Topologie zu ermitteln. Nach Abschluss der anfänglichen Aktualisierung wird der linke Bereich im Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.
  
Wenn Administratoren einen bestimmten Bandbreiten-Richtliniendienst auswählen, werden im rechten Bereich die Informationen zu dem jeweiligen Dienst angezeigt. Dieser Bereich enthält außerdem zwei Hauptregisterkarten, auf denen Informationen angezeigt werden.
  
#### <a name="machine-info-tab"></a>Registerkarte „Machine Info“

Auf der Registerkarte **Machine Info** werden die Details des ausgewählten Bandbreiten-Richtliniendiensts angezeigt sowie die Liste und die Zustände aller Verbindungen, die der ausgewählte Bandbreiten-Richtliniendienst mit anderen Diensten herstellt.
  
#### <a name="topology-info-tab"></a>Registerkarte „Topology Info“

Auf der Registerkarte **Topology Info** wird eine Liste aller Verbindungen angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jede Verbindung wird die Bandbreitenkapazität für Audio und Video angezeigt. Zusätzlich wird die zurzeit verwendete Bandbreite in KB/s und als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierungen zum Hervorheben von Verbindungen, deren Nutzung fast der Kapazität entspricht. So können Administratoren solche Verbindungen schnell erkennen.
  
> [!NOTE]
>  Wenn das Tool Bandbreite Richtlinie Service Monitor Fehler beim Verbinden mit den konfigurierten Bandbreitenrichtlinie Dienste auftritt, wird nicht die Informationen in den **Computer Info** und die **Topologie Info** Registerkarten aufgefüllt werden. Es ist aber möglich, dass das Tool anfangs eine Verbindung mit dem Dienst herstellt, die dann später verloren geht. In solchen Fällen werden Administratoren eventuell veraltete Informationen angezeigt. Beide Registerkarten enthalten einen Zeitstempel **Last Updated**, mit dessen Hilfe Administratoren bestimmen können, wann die Daten für einen bestimmten Bandbreiten-Richtliniendienst zum letzten Mal aktualisiert wurden.
  
### <a name="output"></a>Ausgabe

Es gibt keine Befehlszeilenausgabe. Die Programmausgabe erfolgt auf der grafischen Hauptbenutzeroberfläche.
  
### <a name="purpose"></a>Verwendungszweck

Das Tool Bandwidth Policy Service Monitor soll Administratoren Einblick in den Zustand jedes Bandbreiten-Richtliniendiensts zu verschaffen, der in der Topologie definiert ist. Zusätzlich können Administratoren die Echtzeit-Bandbreitennutzung für alle Verbindungen anzeigen, die im Netzwerkkonfigurationsdokument definiert sind.
  
### <a name="requirements"></a>Anforderungen

Das Tool Bandbreite Richtlinie Service Monitor muss auf einem Computer ausgeführt werden, die Bestandteil der Skype für Business Server-Topologie ist.
  
### <a name="summary"></a>Zusammenfassung

Das Tool Bandwidth Policy Service Monitor kann eine wertvolle Ressource für Administratoren sein, um den Zustand aller Bandbreiten-Richtliniendienste in der Topologie untersuchen zu können. Wichtiger noch ist, dass die Echtzeit-Bandbreitenauslastung für die Verbindungen ermittelt werden kann, die in den Netzwerkkonfigurationseinstellungen definiert sind.
  
## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer
<a name="bua"> </a>

Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten des Bandbreitenverbrauchs durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Mithilfe dieser Berichte kann das aktuelle Muster des Bandbreitenverbrauchs analysiert werden, um die Planung der Bandbreitenkapazität zu unterstützen.
  
### <a name="description"></a>Beschreibung

Bandwidth Utilization Analyzer ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Dieses Tool erzeugt Berichte speziell für die Audionutzung über das Netzwerk und hilft bei der Kapazitätsplanung. Das Tool durchläuft außerdem die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.
  
### <a name="output"></a>Ausgabe

Bandwidth Utilization Analyzer bietet grafische Diagramme der Bandbreitenkapazität und -auslastung durch Audio für alle WAN-Verbindungen, die im System konfiguriert sind.
  
### <a name="purpose"></a>Verwendungszweck

In jeder Sprach- und Videodaten Bereitstellung ist es wichtig, überwachen und verstehen, die Entwicklung der Auslastung der Bandbreite der Mediendatenverkehr über das Unternehmensnetzwerk. Genau dies ermöglicht das Tool Bandwidth Utilization Analyzer Administratoren. Das Tool bietet folgende Funktionen:
  
- Erzeugung spezifischer Berichte für die Audionutzung über das Netzwerk
    
- Hilfe bei einer effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist
    
Bandwidth Utilization Analyzer kann aus Bandbreitenkapazitäts- und -auslastungsberichten die folgenden grafischen Diagramme generieren:
  
- Alle WAN-Verbindungen im Unternehmensnetzwerk
    
- Gefiltert nach ausgewählten WAN-Verbindungen
    
- Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben
    
- Gefiltert nach WAN-Verbindungen, die nicht die gesamte bereitgestellte Bandbreite nutzen
    
- Gefiltert nach WAN-Verbindungen, die kritische Grenzwerte erreicht haben (eine Bandbreitenauslastung von mehr als 90 % der Bandbreitenkapazität der WAN-Verbindung)
    
- Gefiltert nach WAN-Verbindungstyp: Netzwerkstandortverbindungen, interregionale Verbindungen und Verbindungen innerhalb eines Standorts
    
- Gefiltert nach Netzwerkregion
    
#### <a name="applications"></a>Anwendungen

Bandwidth Utilization Analyzer besteht aus den zwei folgenden Anwendungen (Tools):
  
- **WanLinkLogCollector.exe** dieses Tool ermöglicht die Benutzer die erforderliche Informationen eingeben.
    
- **BandwidthUtilizationAnalyzer.xlsm** Bericht für eine Microsoft Excel-Kalkulationstabelle wird durch WanLinkLogCollector.exe automatisch gestartet. Mit dieser Anwendung können Benutzer, wie später in diesem Artikel gezeigt, Filter auf den Bericht anwenden.
    
#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phasen der Verwendung von Bandwidth Utilization Analyzer

Es gibt zwei Phasen bei der Verwendung von Bandwidth Utilization Analyzer:
  
- Erfassen von Protokollen mithilfe von „WanLinkLogCollector.exe“
    
- Anpassen von Berichten mithilfe von „BandwidthUtilizationAnalyzer.xlsm“
    
> [!IMPORTANT]
> „BandwidthUtilizationAnalyzer.xlsm“ sollte auf keinen Fall manuell von Endbenutzern gestartet werden. 
  
#### <a name="starting-bandwidth-utilization-analyzer"></a>Starten von Bandwidth Utilization Analyzer

Starten Sie „WanLinkLogCollector.exe“ an der Eingabeaufforderung oder mithilfe von Windows-Explorer.
  
 **Verwenden von „WanLinkLogCollector.exe“**
  
„WanLinkLogCollector.exe“ wird in drei Schritten verwendet:
  
1. **Melden Sie sich die Zeitachse** Geben Sie den Zeitplan an, dem der Bericht für generiert werden soll
    
2. **Geben Sie die Dateiverzeichnisse** Bereitstellen von Informationen zum Dateispeicherort
    
3. **Sammeln Sie die Protokolle und starten Sie den Bericht-viewer** Führen Sie den Befehl zum Generieren von Berichten
    
#### <a name="step-1---log-the-timeline"></a>Schritt 1 – Protokollieren des Zeitraums

Durch die Protokollierung des Zeitraums können die Benutzer des Tools, wie in der Abbildung unten dargestellt, Folgendes angeben.  
  
1. **Startdatum** Dies ist das Startdatum des Zeitplans, die der Bericht wird generiert werden soll. beispielsweise 1 August 2010.
    
2. **Enddatum** Dies ist das Enddatum des Zeitplans, die der Bericht wird generiert werden soll. beispielsweise 30 September 2010.
    
     ![Start- und Enddatum in der Bandbreitennutzung A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)
  
#### <a name="step-2---specify-the-file-directories"></a>Schritt 2 – Angeben der Dateiverzeichnisse

Die folgenden Dateiverzeichnisse können von den Benutzern wie gezeigt angegeben werden.
  
- **Speicherort für Protokolldateien Server** Der Ordnerspeicherort, in dem die Bandbreite Richtlinie Serverprotokolle gespeichert werden. Dies ist in der Regel in \<Dateiserver\>\\< Choice der FE\>\AppServerFiles\PDP.
    
- **Temporären Dateispeicherort** Am temporären Dateispeicherort, in dem temporäre Dateien gespeichert sind, während der Bericht generiert wird.
    
![Dateiverzeichnisse in der Bandbreitennutzungsanalyse](../media/Reskit_2012_Tools_Documentation_Image5.jpg)
  
> [!NOTE]
> Stellen Sie sicher, dass den Benutzern des Tools ausreichender Dateizugriff auf den Speicherort der Serverprotokolle und der temporären Dateien gewährt wird. 
  
#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Schritt 3 – Erfassen der Protokolle und Starten der Berichtanzeige

Um die Protokolle zu erfassen und die Berichtanzeige zu starten, klicken Sie, wie unten gezeigt, auf **Execute**. In diesem Schritt werden die erforderlichen Daten erfasst.
  
![Sammeln von Daten in der Bandbreitennutzungsanalyse](../media/Reskit_2012_Tools_Documentation_Image6.jpg)
  
Nach erfolgreicher Überprüfung der Eingabe wird die unten wiedergegebene Meldung angezeigt.
  
![In Protokollen erfasste Benachrichtigung im Bandbreitendienstprogramm](../media/Reskit_2012_Tools_Documentation_Image7.jpg)
  
Klicken Sie auf **OK**. „BandwidthUtilizationAnalyzer.xlsm“ wird automatisch gestartet. Befolgen Sie die im Meldungsfeld angezeigten Anweisungen. Ausführliche Informationen finden Sie im nächsten Abschnitt unter **Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**.
  
#### 

### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Verwenden von „BandwidthUtilizationAnalyzer.xlsm“

1. Wenn „BandwidthUtilizationAnalyzer.xlsm“ automatisch gestartet wurde, klicken Sie wie unten gezeigt auf **Refresh**.
    
     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)
  
2. Wenn ein Dateiordner geöffnet wird, wählen Sie die Datei „consolidated.csv“ an dem Speicherort aus, der in dem unten gezeigten Meldungsfeld angegeben ist. Dort wird außerdem der Speicherort **C:\Temp** angezeigt.
    
     ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer](../media/Reskit_2012_Tools_Documentation_Image9.jpg)
  
3. Klicken Sie auf **Import**.
    
4. Das grafische Diagramm wird automatisch generiert. Es ist verfügbar, sobald der Hintergrundaktivitäts-Mauszeiger nicht mehr angezeigt wird.
    
     ![Anwenden von Filtern in der Berichtsansicht](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
#### <a name="applying-filters-to-the-report-view"></a>Anwenden von Filtern auf die Berichtsansicht

Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden nachfolgend beschrieben:
  
![Anwenden von Filtern in der Berichtsansicht](../media/Reskit_2012_Tools_Documentation_Image11.jpg)
  
1. **Name** Filtern nach WAN-Verbindungen (der Filter befindet sich rechts von der Grafik). Das Präfix identifiziert die folgenden Verbindungstypen, siehe im vertikalen (blauen) Feld:
    
  - **S Site** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion
    
  - **IS Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten
    
  - **R Inter-Region** Die WAN-Verbindung zwischen zwei Netzwerkregionen
    
2. **Exceeded limit** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung die Bandbreitenkapazität übersteigt
    
3. **Critical levels** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mindestens 90 % der Bandbreitenkapazität erreicht hat
    
4. **Under-utilized** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25 % der Bandbreitenkapazität beträgt
    
5. **Link type** Filtern nach den folgenden WAN-Verbindungstypen:
    
  - 
            Typ **Network site**
    
  - 
            Typ **Inter-site**
    
  - 
            Typ **Inter-Region link**
    
6. **Region** Filtern nach Netzwerkregion
    
Die folgenden Abbildungen zeigen die oben beschriebenen Filter.
  
Filtern nach **Name**. Wählen Sie die Liste der Verbindungen aus, die in dem Diagramm angezeigt werden sollen.
  
![Filtern nach Name in BandwidthUtilizationAnalyzer](../media/Reskit_2012_Tools_Documentation_Image12.jpg)
  
Filtern nach **Exceeded limit**. Wählen Sie **True** aus, um den Filter zu erzwingen.
  
![Filtern nach Exceeded Limit](../media/Reskit_2012_Tools_Documentation_Image13.jpg)
  
Filtern nach **Critical levels**. Wählen Sie **True** aus, um den Filter zu erzwingen.
  
![Filtern nach Critical Levels](../media/Reskit_2012_Tools_Documentation_Image14.jpg)
  
Filtern nach **Under utilized**. Wählen Sie **True** aus, um den Filter zu erzwingen.
  
![Filtern nach Under Utilized](../media/Reskit_2012_Tools_Documentation_Image15.jpg)
  
Filtern nach **Link Type**. Wählen Sie die Typen aus, die angezeigt werden sollen.
  
![Filtern nach Link Type](../media/Reskit_2012_Tools_Documentation_Image16.jpg)
  
Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Verbindungen angezeigt werden sollen.
  
![Filtern nach Region](../media/Reskit_2012_Tools_Documentation_Image17.jpg)
  
### <a name="requirements"></a>Anforderungen

- .NET Framework 3.5
    
- Microsoft Excel 2010 oder Excel 2007
    
### <a name="summary"></a>Zusammenfassung

Bandwidth Utilization Analyzer wird verwendet, um die Bandbreitenauslastung durch Audio für UC-Datenverkehr über das Netzwerk grafisch darzustellen. Mithilfe dieses Tools kann auch die Bandbreitenauslastung durch Video im Netzwerk dargestellt werden.
  
## <a name="call-parkometer"></a>Call Parkometer
<a name="callpark"> </a>

Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Datenbank mit den Orbits der geparkten Anrufe ermöglicht.
  
### <a name="description"></a>Beschreibung

Call Parkometer ist ein Tool zum Nachverfolgen der zurzeit geparkten Anrufe. Es erfasst außerdem Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS). Dieses Command-Line Tool bietet Lese- und Schreibzugriff auf den Orbit CPS SQL Server-Datenbank von einem Computer lokale oder Remote verbunden sind.
  
Alle Optionen schließen sich gegenseitig aus. Befehlszeilensyntax:
  
- **o -** Parameter – alle Bereiche, die für diesen Pool konfiguriert orbit Listen.
    
- **-n** -Parameter – alle derzeit verwendeten Listen Orbits in diesem Pool. Folgende Informationen werden angezeigt:
    
  - Der SIP-URI (Session Initiation Protocol Uniform Resource Identifier) der geparkten und der parkenden Person
    
  - Der Hostname des Anrufparkservers, auf dem der Anruf geparkt ist
    
  - Der Zeitstempel, aus dem hervorgeht, wann der Anruf geparkt wurde
    
- Parameter **-f** – die Anzahl der derzeit kostenlose Orbits im Pool aufgelistet.
    
- **R - \<n\> ** Parameter – Listet die \<n\> letzten geparkt Anrufe. Folgende Informationen werden angezeigt:
    
  - SIP-URI der geparkten Person
    
  - SIP-URI der parkenden Person
    
  - Der Hostname des Anrufparkservers, auf dem der Anruf geparkt wurde
    
  - Der Zeitstempel, aus dem hervorgeht, wann der Anruf herangeholt oder abgebrochen wurde
    
- **-t\<n\> ** Parameter - getestet, reservieren eine Orbit in die Datenbank Auswahl von der zugewiesenen orbitnummern anzeigen.
    
### <a name="output"></a>Ausgabe

Abhängig von den Eingabeparametern, die an der Eingabeaufforderung angegeben werden, zeigt Call Parkometer folgende Ausgaben an:
  
- Alle für diesen Pool konfigurierten Orbitbereiche
    
- Zurzeit geparkte Anrufe
    
- Anzahl der freien (verfügbaren) Orbits
    
- Zuletzt geparkte Anrufe
    
- Für das Testen einheitlicher und zufälliger Orbitwerte reservierte Orbits
    
### <a name="purpose"></a>Verwendungszweck

Das Anrufparkserver-Tool soll Befehlszeilenzugriff auf die Anrufparkserver-Datenbank ermöglichen. Administratoren können die Anrufparkserver-Nutzung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.
  
### <a name="requirements"></a>Anforderungen

Wenn das Tool auf dem gleichen Computer wie der Anrufparkserver ausgeführt wird, gelten keine Anforderungen. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die SQL Server-Datenbank von Skype für Business Server 2015 verwendet Remotezugriff konfiguriert werden. Anruf Parkometer muss mit einer SQL Server-Datenbank-Verbindungszeichenfolge für die Verbindung zu des Pools SQL Server konfiguriert werden. Diese SQL Server-Datenbank-Verbindungszeichenfolge ist in der Konfigurationsdatei **parkometer.exe.config**definiert. Es muss im gleichen Verzeichnis platziert werden parkometer.exe gespeichert ist. Die folgende XML-Datei ist ein Beispiel für eine parkometer.exe.config. Die Parameter, die konfiguriert werden müssen sind Benutzernamen ein (beispielsweise Mydomain\Administrator), Kennwort (z. B. Mypassword) und Hostnamen (z. B. "Myserver").
  
```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a>Beispiele

Bereiche für den anrufparkorbit bereitgestellt: der -o Parameter Listet alle orbitbereiche, die für diesen Pool konfiguriert sind, siehe
  
![Orbitbereiche in der Anrufparkuhr](../media/Reskit_2012_Tools_Documentation_Image18.jpg)
  
Derzeit geparkt Anrufe: - n-Parameter werden alle derzeit verwendeten Orbits für diesen Pool aufgelistet, siehe
  
![Aktuell in der Anrufparkuhr geparkte Anrufe](../media/Reskit_2012_Tools_Documentation_Image19.jpg)
  
Anzahl der freien Orbits: der Parameter-f Listet die Anzahl der derzeit kostenlose Orbits im Pool, siehe
  
![Freie Orbitbereiche in der Anrufparkuhr](../media/Reskit_2012_Tools_Documentation_Image20.jpg)
  
Kürzlich geparkt Anrufe: R - \<n\> Parameterlisten der \<n\> letzten Anrufe geparkt, siehe
  
![Zuletzt in der Anrufparkuhr geparkte Anrufe](../media/Reskit_2012_Tools_Documentation_Image21.jpg)
  
Testen der Orbit Reservierung: -t \<n\> Parameter getestet, reservieren eine orbitbereiche in der Datenbank, siehe
  
![Testorbitreservierungen in der Anrufparkuhr](../media/Reskit_2012_Tools_Documentation_Image22.jpg)
  
### <a name="summary"></a>Zusammenfassung

Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.
  
## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Beschreibung

Dbanalyze aus ist ein Befehlszeilentool, mit dem Administratoren die Analyseberichte über die Skype für Business Server 2015 Datenbanken zu erfassen kann. DBAnalyze verfügt über folgende Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:
  
- **Diagnose-Modus** Erstellt einen Bericht, enthält Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten- und Protokolldateien Dateigrößen, die Sicherung im letzten Kontakt Verteilung auf Servern mit Microsoft Office Communications Server, die Durchschnittliche Anzahl von Berechtigungen, Kontakte, Containern, Abonnements, Publikationen, Endpunkten pro Benutzer, nicht ordnungsgemäß verwaltete Benutzer, die Benutzer, die weitergeleitet werden können, werden die durchschnittliche Anzahl der Konferenzen pro Benutzer, geplante Konferenzen und aktiven Konferenzen organisiert, und die Version der Datenbank.
    
    > [!NOTE]
    > Die Ausführung im Diagnosemodus kann die Serverleistung beeinträchtigen. 
  
- **Datenmodus Benutzer** Berichte Kontakt, Container, Abonnements, Publikation, Berechtigung und Kontaktgruppe Daten für einen angegebenen Benutzer oder für Benutzer, die diesen Benutzer in ihre Kontakt- und Berechtigung verfügen. Dieser Modus berichtet außerdem Zusammenfassungsdaten für Konferenzen, die von einem Benutzer organisiert werden oder zu denen er eingeladen ist.
    
- **Konferenzmodus** Berichte detaillierte Daten zu einer bestimmten Konferenz, einschließlich aller Zeit planen Details zu der Konferenz, die Liste eingeladenen Benutzer, die Liste der Medientypen zulässig für die Konferenz, aktive MCUs (multipoint Control Einheiten), die Liste der aktiven Teilnehmer und jeweils Signalisierung Zustand des Teilnehmers.
    
- **Decodieren Besprechungs-ID** Decodiert ein öffentliches Telefonfestnetz (PSTN) meeting-ID, die durch die Option **/pstnid** angegeben wird, aber stellt keine Verbindung zum Back-End ausführliche Informationen her.
    
- **Auflösen der Konferenz** Decodiert eine PSTN-besprechungs-ID, die durch die Option **/pstnid** angegeben ist und zeigt Informationen über die Konferenz von der ID angegeben
    
- **MCUs-Modus** ID, Medientyp, URL, Heartbeat-Status, Konferenz laden und Teilnehmer Load-Berichte für jede MCU im Pool.
    
- **Festplatten Fragmentierung-Modus** Zeigt den Fragmentierung Status aller Festplatten.
    
Dieses Tool kann zum Diagnostizieren verschiedener Probleme verwendet werden oder Administratoren bei der Kapazitätsplanung unterstützen. Wenn beispielsweise die meisten der auf Server A verwalteten Benutzer auf Server B verwaltete Benutzer als Kontakte wählen, kann der Administrator die Benutzer von Server A auf Server B verschieben, um den Datenverkehr zwischen den Servern zu verringern.
  
### <a name="output"></a>Ausgabe

Dieses Tool gibt vordefinierte Berichte über die Skype für Business Server 2015 Datenbank aus. **Pfad**: %ProgramFiles%\Skype for Business Server 2015\Reskit
  
### <a name="purpose"></a>Verwendungszweck

Um Dbanalyze.exe zu installieren, kopieren Sie sie in einen lokalen Ordner, und führen Sie das Tool. Wenn das Tool verwenden möchten, führen Sie den folgenden Befehl an der Befehlszeile. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Die Beschreibungen für die Befehlszeilenoptionen sind unten aufgeführt.
  
![Befehlszeilenoptionen für Dbanalyze.exe](../media/Reskit_2012_Tools_Documentation_Image35.JPG)
  
### <a name="requirements"></a>Anforderungen

 **Computer** Dbanalyze aus kann nur von einer Domäne gehörenden Computer ausgeführt werden, Skype für Business Server 2015 installiert sind.
  
 **Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.
  
 **Software** Skype für Business Server 2015 Softwarekomponenten muss installiert sein, vor dem Ausführen von Dbanalyze aus.
  
 **Benutzer** Die nachstehende Tabelle zeigt den Administratoren besitzen die erforderlichen Berechtigungen zum Skype für Business Server 2015 Datenbanken zugreifen.
  
![Berechtigungstabelle für Dbanalyze.exe](../media/Reskit_2012_Tools_Documentation_Image36.JPG)
  
> [!NOTE]
> Für den **/report:disk**-Modus ist ein lokales Administratorkonto erforderlich.
  
### <a name="examples"></a>Beispiele

Hier sind Beispiele für gültige „Dbanalyze.exe“-Befehle:
  
```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Zusammenfassung

DBAnalyzer bietet Administratoren eine schnelle und einfache Skype für Business Server 2015 Datenbanken zu analysieren.
  
## <a name="import-storage-service-data"></a>Import Storage Service Data
<a name="Issd"> </a>

Mit dem Resource Kit-Tool „ImportStorageServiceData“ können Warteschlangen- und Endpunktdaten, die aus dem Speicherdienst (LYSS) geleert wurden, wieder zurück in den Speicherdienst importiert werden.
  
### <a name="description"></a>Beschreibung

Die Leerung der Daten aus dem Speicherdienst kann automatisch (regelmäßig) auf Grundlage des Warteschlangenelementstatus oder der Datenbankgröße erfolgt sein. Das Leeren kann aufgrund eines manuellen Aufrufs des Cmdlets für Poolfailover oder des Cmdlets „StorageServiceFullFlush“ (das vom Cmdlet für Poolfailover aufgerufen wird) erfolgt sein. Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollen Wenn keines der Datenbankgröße Storage Service (LYSS) auf den front-Ends ist über die normale Ebene, da dadurch wahrscheinlich nur weitere Daten wieder exportiert werden sollen verursacht. Darüber hinaus sollte die Fehler können, die die Speicherung Service Warteschlange beigetragen haben wachsen verursacht Probleme zunächst (zum Beispiel Exchange Endpunkt Fehler, Netzwerkprobleme oder andere Probleme) aufgelöst werden.
  
 **Szenario 1:** während des Failovers Pool Dateien möglicherweise geleert Skalieren von Speicherdienst für jeden Front-End. Nach dem Failover abgeschlossen ist, sollte das Tool ausgeführt werden, um die Daten erneut importieren.
  
 **Szenario 2:** Daten wird geleert automatisch jeden Tag oder als Reaktion auf Speicherdienst Datenbank überschreiten bestimmte Schwellenwerte Größe (z. B. 60 % 80 %, 90 % voll). Diese Daten automatisch wurden sollten routinemäßig erneut vom Administrator importiert werden. In der obigen Situation Wenn das monitoring SCOM nicht bereitgestellt wird, sind Ereignisse für Skype für Business Server Speicherdienst im Zusammenhang mit Daten aus der Speicherdienst geleert wird. Ereignis-IDs der 32075 (vollständige Schreibvorgang wurde gestartet wird), 32076 (vollständige Flush abgeschlossen ist), 32082 (Wartung Level flush gestartet), 32083 (zu leeren vollständige Wartung Level), 32089 (Fehler aufgrund der Datenbank füllen leeren). Beachten Sie, dass diese Ereignis-Ids mit der RTM-Version übereinstimmen. Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien, die Sie übertragen wurden. Diese Daten sollten routinemäßig dieses Tool back beispielsweise einmal pro Woche mit importiert werden.
  
Für die Version Onlinedienst Wenn Health monitoring Pack für SCOM für Skype für Business Server bereitgestellt wird, sind neue Warnungen, die möglicherweise ausgelöst werden die bitten Sie den Administrator, um die Daten wurden wieder Speicherdienst erneutes importieren. Im Ereignisprotokoll wird ein entsprechendes Ereignis vorhanden sein, auf dem Front-End-Server, der Warnung ausgelöst. Das Ereignis erhalten eine Beschreibung des Pfads zur übergeordneten unter dem die Daten wurden Dateien befinden, sind sowie wie viele Dateien vorhanden sind, die die Warnungen Kriterien erfüllen. Die Warnung Kriterium darstellen, ist es wurden X oder mehrere Dateien unter dem bestimmten übergeordneten Pfad die sind am wenigsten Y Tage (wobei X und Y sind innerhalb der StorageService Voreinstellung jedoch überschrieben werden kann, indem Sie die Datei APPCONFIG ändern.) Zwei Beispiele für Ereignisse, die die Integrität Warnung ausgelöst werden können, mit dem Unterschied, deren übergeordneten Pfad nachfolgend. Eine Möglichkeit ist unter Web-Service-Dateifreigabe, während die anderen Möglichkeit das lokale Verzeichnis Anwendungsdaten von jedem Front-End ist. (beispielsweise c:\ProgramData\Microsoft\Skype für Business Server 2015\StorageService). Der Administrator wird dieses Tool Reskit ausgeführt wird.
  
Dieses Tool erhöht die Auslastung von CPU und E/A-Vorgängen auf dem Front-End-Server, auf dem es ausgeführt wird, sowie auf anderen Front-End-Servern, wenn der Front-End-Server, auf dem das Tool ausgeführt wird, nicht Besitzer der Daten ist. Wir empfehlen die Ausführung dieses Tools, wenn die Auslastung von CPU und E/A-Vorgängen auf den Front-End-Servern niedrig ist, beispielsweise außerhalb der Spitzenzeiten. Darüber hinaus kann dieses Tool zwei bis drei Minuten für den Import einer Datendatei benötigen. Denken Sie hieran, wenn Sie die voraussichtliche Ausführungsdauer des Tools schätzen. Die von dem Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt. Löschen Sie sie, wenn darin keine Fehler gemeldet werden, da die Protokolldatei mehrere 10 MB übersteigen kann.
  
![Beispielereignisse für das Ereignisprotokoll des Speicherservers](../media/Reskit_2012_Tools_Documentation_Image1.jpg)
  
### <a name="requirements"></a>Anforderungen

Installieren Sie die Skype für Business Server 2015 Resource Kit-Tools. Das Tool wird ausgeführt auf Domäne gehörenden Computer, auf dem Skype für Business Server und Skype für Business Server-Verwaltungsshell installiert. Das Tool verwendet ein Cmdlet aus der-Verwaltungsshell auf um allen Front-End-Servern im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, die die **RtcLocal** -Datenbank installiert hat. Diese Datenbank wird vom Programm verwendet, um den Speicherort der WEBSERVICE Dateifreigabe für den Pool abzurufen. Darüber hinaus muss vor der Verwendung des Tools, jedem Front-End-Server aktivieren, Windows PowerShell-Remoting mit **Enable-psremoting sieht** auf jedem Front-End-Server als auch den Computer aus, dem das Tool ausgeführt wird. Andernfalls werden von diesem Tool remote Windows PowerShell-Befehle fehl. Windows PowerShell-Remoting kann deaktiviert werden auf allen Front-End-Servern im Pool nachdem der Importvorgang abgeschlossen ist. Schließlich muss das Tool aufrufen Anmeldeinformationen Lese-/Schreibberechtigung für die Webservice-Dateifreigabe für den Pool verfügen, die sie für dieses Tool ausgeführt werden. Andernfalls wird das Tool Berechtigung e/a-Fehler auftreten.
  
> [!NOTE]
> Unter Windows Server 2012 ist Windows PowerShell-Remoting standardmäßig, jedoch nicht auf dem Betriebssystem Windows Server 2008 aktiviert. 
  
### <a name="examples"></a>Beispiele

```
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                    
-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a>LCSSync
<a name="LCSSync"> </a>

Das Tool LCSSync unterstützt Skype für Business Server 2015 Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen bereitgestellt. Dieses Tool dient zum Synchronisieren von Benutzern und Gruppen aus verschiedenen Benutzergesamtstrukturen als Active Directory-Domänendienste-Kontaktobjekt und der zentralen Gesamtstruktur, in Skype für Business Server 2015 installiert ist.
  
### <a name="description"></a>Beschreibung

 LCSSync Verwendungsmöglichkeiten der synchronisierten Active Directory-Domänendienste Kontaktobjekte in der zentralen Gesamtstruktur so aktivieren Benutzer für Skype für Business Server. Um das einmalige Anmelden zu ermöglichen, muss das primäre Benutzerkonto das Active Directory-Domänendienste-Kontaktobjekt in der zentralen Gesamtstruktur für Skype für Business Server 2015 zugeordnet werden. Dieses Tool hilft bei der Durchführung dieser Zuordnung. Das Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents in Microsoft Identity Integration Server bereit.
  
### <a name="summary"></a>Zusammenfassung

Das Tool LCSSync unterstützt Skype für Business Server 2015 in einer Umgebung mit mehreren Gesamtstrukturen bereitgestellt.
  
## <a name="lookup-user-console"></a>Lookup User Console
<a name="LUC"> </a>

Das LookupUserConsole-Verwaltungstool zeigt interne Skype für Business Server Routinginformationen über einzelne Benutzer. Diese Informationen können den Mitarbeitern des Microsoft-Supports dabei helfen, Probleme bei der Bereitstellung und beim Routing zu diagnostizieren.
  
### <a name="description"></a>Beschreibung

 LookupUserConsole.exe ausgeführt wird ein Eingabeaufforderungsfenster geöffnet, die SIP-Adressen akzeptiert und versucht, interne Skype Business Server routing Informationen über diese anzuzeigen. Geben Sie **exit** ein, um das LookupUserConsole-Tool zu beenden.
  
### <a name="requirements"></a>Anforderungen

Installieren Sie die Skype für Business Server 2015 Resource Kit enthalten. Das Tool wird ausgeführt auf Domäne gehörenden Computer, auf dem Skype für Business Server installiert ist.
  
### <a name="examples"></a>Beispiele

C:\Programme\Microsoft Files\Skype für Business Server 2015\ResKit\>LookupUserConsole.exe
  
```
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a>MsTurnPing
<a name="MsTurnPing"> </a>

Das Tool MSTurnPing ermöglicht es einem Administrator der Skype für die Kommunikationssoftware Business Server 2015 zum Überprüfen des Status des Servers mit der a/v-Edgeserver und Audio-Video-Authentifizierung Dienste als auch auf den Servern, die Bandbreitenrichtlinie ausgeführt werden Dienste in der Topologie.
  
### <a name="description"></a>Beschreibung

Das Tool MSTurnPing ermöglicht es einem Administrator der Skype für die Kommunikationssoftware Business Server 2015 zum Überprüfen des Status des Servers mit der a/v-Edgeserver und Audio-Video-Authentifizierung Dienste als auch auf den Servern, die Bandbreitenrichtlinie ausgeführt werden Dienste in der Topologie.
  
Mit dem Tool können Administratoren die folgenden Tests durchführen:
  
1. A/V-Edgeservertest: Das Tool führt mit allen A/V-Edgeservern in der Topologie die folgenden Tests durch:
    
  - Überprüfen, dass die Skype für Business Server Audio/Video-Authentifizierungsdienst kann die richtige Anmeldeinformationen ausstellen gestartet wird.
    
  - Überprüfen, dass die Skype für Business Server a/v-edgedienst bereits gestartet, sodass die Ressourcen auf die externe Schnittstelle erfolgreich zuweisen kann.
    
2. Test für Bandbreiten-Richtliniendienste: Das Tool führt mit allen Servern in der Topologie, auf denen die Bandbreiten-Richtliniendienste ausgeführt werden, die folgenden Tests durch:
    
  - Überprüfen, dass die Skype für Business Server-Bandbreitenrichtliniendienst (Authentifizierung) kann die richtige Anmeldeinformationen ausstellen gestartet wird.
    
  - Überprüfen, dass die Skype für Business Server-Bandbreitenrichtliniendienst (Core) bereits gestartet, sodass das Bandbreite Kontrollkästchen erfolgreich ausführen kann.
    
Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist.  
  
### <a name="output"></a>Ausgabe

Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.
  
- Wenn der **AudioVideoEdgeServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:
    
  - Die Testergebnisse Computer, auf denen die Skype für Business Server 2015 Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen
    
  - Die Testergebnisse Computer, auf denen die Skype für Business Server 2015 a/v-edgedienst in der Topologie bereitstellen
    
- Wenn der **BandwidthPolicyServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:
    
  - Die Testergebnisse Computer, auf denen die Skype für 2015-Bandbreitenrichtliniendienst für Business Server (Authentifizierung) in der Topologie bereitstellen
    
  - Die Testergebnisse Computer, auf denen die Skype für 2015-Bandbreitenrichtliniendienst für Business Server (Core) in der Topologie bereitstellen
    
### <a name="requirements"></a>Anforderungen

- Dieses Tool muss auf einem Computer ausgeführt werden, der zur Topologie gehört und auf dem sich der lokale Speicher befindet.
    
- Das Tool muss als Administrator mit Zugriff auf den lokalen Speicher ausgeführt werden.
    
### <a name="examples"></a>Beispiele

Hier ist ein Beispiel für die Tooleingabe.
  
```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource Skype für Business Server 2015 Administratoren sein, die den Status der Server, auf dem a/v ausgeführt werden und Bandbreite Richtlinie Dienste überprüfen möchten.
  
## <a name="network-configuration-viewer"></a>Network Configuration Viewer
<a name="NCV"> </a>

Viewer für Netzwerke Konfiguration kann verwendet werden von Skype für Business Server 2015 Communications Software Administratoren Anruf Admission Control (, CAC)-Netzwerktopologie für ein Unternehmen anzeigen, die bereitgestellt wird, um Kommunikation in Echtzeit-Sitzungen, z. B. zulassen VoIP- oder Videoanrufe basierend auf angegebenen Bandbreitenkapazität. Skype für Business Server 2015 Administratoren definieren CAC-Richtlinien, die von den Diensten Bandbreitenrichtlinie erzwungen werden, die mit Skype für Business Server 2015 installiert sind.
  
### <a name="description"></a>Beschreibung

Mit Network Configuration Viewer („NetworkConfigurationViewer.exe“) können Administratoren die folgenden Aufgaben durchführen:
  
- Laden und CAC-Netzwerktopologie aus einer Skype für Business Server 2015 Bereitstellung in einem Grafikformat anzeigen.
    
- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat
    
- Sichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger
    
- Sichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format
    
- Anzeigen von Konfigurationsdaten der CAC-Netzwerktopologie
    
- Anzeigen der CAC-Netzwerktopologie in einer Strukturansicht
    
- Definieren benutzerdefinierter Connectors für Verbindungen in der CAC-Netzwerktopologie (beispielsweise Standort-zu-Region-, Region-zu-Region- oder Standort-zu-Standort-Verbindungen)
    
- Anzeigen von CAC-Netzwerktopologie-Standortinformationen, -Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen
    
### <a name="purpose"></a>Verwendungszweck

Anzeigen der Verbindungen in der CAC-Netzwerktopologie des Unternehmens auf einer grafischen Benutzeroberfläche
  
### <a name="examples"></a>Beispiele

 **Laden und Anzeigen der CAC Netzwerktopologie aus einer Skype für die Bereitstellung in einem Grafikformat Business Server 2015**: Skype für Business Server 2015 Administratoren kann laden und Anzeigen von CAC Topologie Netzwerkkonfiguration auf eine beliebige Skype für Business Server 2015 Computer durch verwenden die Option **Netzwerkkonfiguration herunterladen** aus, wie in der folgenden Abbildung dargestellt. Das Tool nicht laden oder Anzeigen einer Konfigurations bei der Bereitstellung auf einem Computer, die keine Verbindung mit der Skype für Business Server 2015 Konfigurationsspeicher verfügt.
  
![Herunterladen der Netzwerkkonfiguration](../media/Reskit_2012_Tools_Documentation_Image23.jpg)
  
 **Laden und anzeigen CAC Netzwerktopologie aus einer Bandbreitenrichtlinie Server-Protokolldatei in einem Grafikformat:** Skype für Business Server 2015 Bandbreitenrichtlinie Server speichern die Netzwerktopologie CAC als Teil der Protokollierungsmechanismen unter der Skype für Business Server 2015 Dateispeicherort freigeben. Skype für Business Server 2015-Administratoren kann eine solche Datei in einem Grafikformat anzeigen, mithilfe der Option **Open Netzwerkkonfiguration** wie unten dargestellt.
  
![Öffnen einer Bandbreitenrichtlinienserver-Protokolldatei](../media/Reskit_2012_Tools_Documentation_Image24.jpg)
  
Speichern und CAC-Netzwerktopologie in XML-Format auf dem Datenträger speichern: Skype für Business Server 2015-Administratoren kann die CAC Netzwerk Topologie Konfiguration-Datei in einem XML-Format speichern, mithilfe der Option zum **Speichern einer Kopie der Netzwerkkonfiguration** wie unten dargestellt. Die gespeicherte Konfigurationsdatei kann dann offline als Grafik angezeigt werden.
  
![Speichern der Netzwerkkonfiguration als XML-Datei](../media/Reskit_2012_Tools_Documentation_Image25.jpg)
  
Speichern und Store CAC Netzwerktopologie JPG- oder BMP-Format: Skype für Business Server 2015-Administratoren kann die Netzwerkkonfiguration Topologie CAC in einem Grafikformat (JPG und BMP-Dateiformate) mithilfe des Netzwerkkonfiguration speichern **Diagramms als speichern Bild** option wie unten dargestellt.
  
![Speichern der Netzwerkkonfiguration als Bild](../media/Reskit_2012_Tools_Documentation_Image26.jpg)
  
 **Ansicht CAC Netzwerk topologiekonfigurationsdaten:** Skype für Business Server 2015-Administratoren kann verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerkstandorten, Bandbreite Profile und Website Subnetz-IP-Adressen in einem Textformat anzeigen mithilfe der Option Ansicht Netzwerkkonfiguration Daten wie dargestellt unten. 
  
![Anzeigen von Netzwerkkonfigurationsdaten](../media/Reskit_2012_Tools_Documentation_Image27.jpg)
  
 **Netzwerktopologie ausgezeichnet Strukturansicht Ansicht CAC:** Skype für Business Server 2015 Administratoren kann verwandte Netzwerkkonfigurationsdaten ausgezeichnet Ansicht graphical Struktur anzeigen, mithilfe der Systemsteuerung auf der linken Seite des Toolfensters wie unten dargestellt.
  
![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht](../media/Reskit_2012_Tools_Documentation_Image28.jpg)
  
 **Definieren benutzerdefinierte Konnektoren für die Anrufsteuerung Netzwerk-Topologie Links (beispielsweise Standort-zu-Region und regional-Standort-zu-Standort-Verknüpfungen):** Skype für Business Server 2015-Administratoren kann benutzerdefinierte graphical Connectors für CAC Netzwerk Konfiguration WAN-Verbindungen mithilfe der Option Einstellungen wie folgt definieren. Dies erleichtert die Unterscheidung zwischen verschiedenen Netzwerkverbindungstypen, die in der Netzwerkkonfiguration bereitgestellt sind.
  
![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)
  
 **Ansicht CAC netzwerkstandortinformationen Topologie und Regionsinformationen bereitgestellten Bandbreitenrichtlinien:** Skype für Business Server 2015-Administratoren kann verwandte CAC netzwerkregionsinformationen, Websiteinformationen und CAC Bandbreite, die Bereitstellung von Informationen mithilfe der unten gezeigten Optionen anzeigen. (Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **Info**.)
  
![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk](../media/Reskit_2012_Tools_Documentation_Image30.jpg)
  
### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource Skype für Business Server 2015 Administratoren sein, die in einem Grafikformat CAC-Netzwerktopologie für ihre Bereitstellung anzeigen möchten.
  
## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

Die Anwendung "Reaktionsgruppe" ermöglicht Agents nützlich Echtzeitinformationen mit den integrierten Web-Dienst zugreifen. Leider ist keine grafisch dieser Daten außerhalb der Anwendung verfügbar. Das Antwort Gruppe Agent Live Resource Kit-Tool löst dieses Problem, indem er eine einfache und graphical Möglichkeit Zugriff auf diese Informationen, die in Echtzeit Skype Business Communications Software Informationen wie die Anwesenheit von anderen Agents erweitert.
  
### <a name="description"></a>Beschreibung

Response Group Agent Live ist eine Windows-Anwendung, die An- und Abmeldefunktionen sowie einige Echtzeitinformationen (wie Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bietet. Hierbei handelt es sich wird eine erweiterte Version der Seite Agentgruppen (Zugriff über Skype für Unternehmen.
  
### <a name="purpose"></a>Verwendungszweck

Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschleife und leitet sie dann an Agent-Gruppen weiter. Um informierte Entscheidungen darüber treffen zu können, welche Anrufe bedient werden sollen, können Agents auf Echtzeitinformationen zu ihren Agent-Gruppen zugreifen. Dabei erfahren sie beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst verfügbar sind, werden auf intuitive Weise von Response Group Agent Live zur Verfügung gestellt.
  
#### <a name="features"></a>Funktionen

Das Tool Antwort Gruppe Agent Live baut auf der reaktionsgruppendienst und die Skype für Business Server 2015 SDK. Es bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die durch den Reaktionsgruppendienst zur Verfügung gestellt werden (beispielsweise Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).
  
Die Abbildung unten zeigt die Hauptoberfläche von Response Group Agent Live.
  
![Das Tool „Reaktionsgruppen-Agent Live“](../media/Reskit_2012_Tools_Documentation_Image37.JPG)
  
Folgende drei Hauptfeatures stehen Agents in Response Group Agent Live zur Verfügung:
  
- **Sign-in/Out:** Im Gegensatz zu der Seite Agent-Gruppen (Zugriff über Skype für Business Server 2015) können nur Agenten-Anmeldung oder alle Gruppen gleichzeitig Antwort Gruppe Agent Live. Diese Anwendung bietet drei Verfahren für Agents zum Signieren in oder out:
    
  - Klicken auf die Schaltflächen zum An-/Abmelden (grün und rot) in der Anwendung
    
  - Klicken auf das Taskleistensymbol mit der rechten Maustaste und Auswählen von „Sign-in“ oder „Sign-out“
    
  - Verwenden konfigurierbarer Tastenkombinationen
    
- **Gruppenmitgliedschaft:** Bei eine agentgruppe ausgewählt ist, werden Antwort Gruppe Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich angezeigt. Wenn Skype für Business Server 2015 auf demselben Computer wie diese Anwendung ausgeführt wird, werden in der Antwort Gruppe Agent Live Anwesenheitsinformationen und der Visitenkarte angezeigt. Agents können direkt von dort aus eine Chatnachricht senden oder andere Agents anrufen.
    
- **Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agent-Gruppen. Die Statistiken werden minütlich aktualisiert. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein optischer Indikator mit der aktuellen Anzahl der wartenden Anrufe hinzugefügt. Wenn Sie mit dem Mauszeiger auf einer Gruppe verweilen, wird außerdem die längste Wartezeit angezeigt.
    
### <a name="requirements"></a>Anforderungen

Response Group Agent Live erfordert .NET Framework 4.0. Darüber hinaus um die Anwesenheits- und Kontaktinformationen Karte-Features nutzen zu können, Skype für Unternehmen muss lokal installiert werden (und ausgeführt werden).
  
#### <a name="configuration"></a>Konfiguration

Response Group Agent Live kann mithilfe des Dialogfelds „Options“ in der Anwendung an die individuellen Anforderungen angepasst werden. Darüber hinaus können Administratoren die Standardhostadresse definieren, indem sie die Eigenschaft „defaultHostAddress“ in der Datei „RGAgentLive.exe.config“ direkt bearbeiten.
  
Die Abbildung unten zeigt das Dialogfeld „Options“, in dem Agents die Hostadresse und Tastenkombinationen konfigurieren können. Auf dieses Dialogfeld können Sie zugreifen, indem Sie auf der Hauptbenutzeroberfläche rechts oben auf die Schaltfläche „Options“ klicken.
  
![Das Dialogfeld mit Optionen für „Reaktionsgruppen-Agent Live“](../media/Reskit_2012_Tools_Documentation_Image38.JPG)
  
Folgende drei unterschiedliche Einstellungen können in der Konfiguration von Response Group Agent Live angepasst werden:
  
- Hosten von Adresse: Dies ist üblicherweise im Web pool-FQDN, der Agent im home-Pool angehören. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads an den Host).
    
- Tastenkombinationen: Die genauen Tastenkombinationen zum An- und Abmelden können angepasst werden. Die einzige Einschränkung ist, dass beide Tastenkombinationen Schlüssels "Windows-Logo" (zusätzlich zu mindestens einem anderen Schlüssel) enthalten müssen.
    
- Starten mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch beim Starten von Windows gestartet wird.
    
### <a name="examples"></a>Beispiele

Die Abbildung unten zeigt, wie Sie andere Agents anrufen oder ihnen eine Chatnachricht senden, indem Sie mit der rechten Maustaste im rechten Bereich auf den Kontakt klicken.
  
![Anruf tätigen oder Chatnachricht senden](../media/Reskit_2012_Tools_Documentation_Image39.JPG)
  
Die Abbildung unten zeigt, wie Response Group Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife sowie die längste Wartezeit all dieser eingehenden Anrufe anzeigt.
  
![Anzeigen von Warteschlangeninformationen](../media/Reskit_2012_Tools_Documentation_Image40.JPG)
  
### <a name="summary"></a>Zusammenfassung

Schnelles An- und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Funktionen für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind. Mit dem Tool Antwort Gruppe Agent Live Resource Kit kann Skype für Business Server 2015 Administratoren ihre Agents mit einer Windows-Anwendung bereitstellen, das zum Ausführen von Aufgaben in einer Weise schneller und grafische ermöglicht.
  
## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (sekundäre Erweiterung der Aktivierung des Features) ist ein Befehlszeilentool, mit dem Skype Business Server 2015 Communications-Software-Administratoren und Helpdesk-Agents Delegaten klingeln, anrufweiterleitung, Gleichzeitiges Klingeln konfigurieren kann, Rufen Sie teamanrufgruppen-Einstellungen und Gruppe Pickup im Namen einer Skype für Business Server 2015 Benutzer. Das Tool ermöglicht auch Administratoren die Einstellungen Anrufrouting Abfragen, die für einen bestimmten Benutzer veröffentlicht werden. Das Tool SEFAUtil ermöglicht dem Administrator, Enable, Disable, ändern Anruf weiterleiten oder Gleichzeitiges Anrufen im Namen des Benutzers. Der Administrator kann das Ziel (in Form einer SIP-URI) angeben oder eine Ziel, die bereits vom Benutzer veröffentlicht wurde verwenden. Dieses Tool ermöglicht auch Administratoren hinzufügen oder Entfernen von Stellvertretungen oder Team-anrufgruppe Mitglieder im Auftrag des Benutzers. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.
  
SEFAUtil (sekundäre Erweiterung der Aktivierung des Features) ermöglicht Skype für Business Server 2015 Administratoren und Helpdesk-Agents konfigurieren Delegaten klingeln, anrufweiterleitung, Gleichzeitiges Klingeln, teamanrufe-Einstellungen und Pickup-Anruf im Namen einer Skype gruppieren für Benutzer Business Server 2015. Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind.
  
### <a name="description"></a>Beschreibung

Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool. Es ist keine unterstützenden GUI. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0. Die Features in dieses Tool ermöglichen Administratoren und Helpdesk-Agenten, die folgenden Aufgaben ausführen:
  
- Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Stellvertretung, gleichzeitiges Klingeln, Teamanruf- und Gruppenanrufannahme)
    
- Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellungen (einschließlich Ziel und Timer für „Keine Antwort“)
    
- Aktivieren/Deaktivieren/Ändern der Konfiguration für sofortige Anrufweiterleitung
    
- Aktivieren/Deaktivieren/Ändern von Stellvertretungseinstellungen
    
- Aktivieren/Deaktivieren/Ändern von Teamanrufgruppen-Einstellungen
    
    > [!NOTE]
    > Neu in Skype für Business Server 2015 SEFAUtil tool 
  
- Aktivieren/Deaktivieren/Ändern der Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)
    
    > [!NOTE]
    > Neu in Skype für Business Server 2015 SEFAUtil tool 
  
- Aktivieren/Deaktivieren/Ändern von Einstellungen für Gruppenanrufannahme
    
    > [!CAUTION]
    > Neu in Skype für Business Server 2015 SEFAUtil tool 
  
Für das Tool gelten die folgenden Einschränkungen:
  
- Unterstützt nur für Benutzer in einer Skype für Business Server-Pool verwaltet
    
- Keine Unterstützung für die Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer
    
### <a name="output"></a>Ausgabe

Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster Ausgaben zur Verfügung. Details hierzu finden Sie weiter unten in diesem Dokument im Abschnitt mit den Beispielen.
  
### <a name="purpose"></a>Verwendungszweck

Hier sind einige der Hauptszenarien, in denen dieses Tool eingesetzt werden kann:
  
- Bob ist Führungskraft und an Skype für Telefonie Business Server verschoben wurde. In seiner vorhandenen Nebenstellenanlage hat er Stellvertretungen eingerichtet. Als Teil der Wechsel zu Skype für Business Server 2015 kann der Administrator Bobs routing seine vorhandenem Delegierung Konfiguration entsprechend konfigurieren.
    
- Alice ist auf Reisen und stellt fest, dass sie einen wichtigen Anruf eines ihrer Kunden erwartet. Sie befindet sich aber gerade im Hotel und hat keinen Computer zur Verfügung. Sie ruft den Helpdesk an und bittet darum, alle Anrufe an ihre Büronummer an ihr Mobiltelefon weiterzuleiten. Die Helpdeskmitarbeiter können diese Konfiguration in ihrem Auftrag vornehmen.
    
- Joes Anrufe an seine Dienstnummer sollte werden auf seinem mobilen Voicemail, wenn er bei der Arbeit ist; Dinge werden jedoch in den meisten anderen Stellen ordnungsgemäß angezeigt. Der Helpdesk-Techniker Routingkonfiguration des Joe angezeigt und feststellt, dass Joe Gleichzeitiges Klingeln an seinem Mobiltelefon konfiguriert hat. Der Techniker bittet Joe über die mobilen Abdeckung in seinem Büro und feststellen, dass die gleichzeitige Klingeln Regel ist, wodurch die Anrufe beim seine Netzwerk Abdeckung schlecht ist Joes mobilen Voicemail weitergeleitet wird.
    
- Mike wird ein neuer Mitarbeiter bei Contoso und er wird ein neues Team auf dem alle Mitglieder für Team-anrufgruppe konfiguriert sind, wenn für Skype für Business Server 2015 aktiviert ist, beitreten, der Administrator ist seine teamanrufgruppe Clientgruppen Einbeziehung seiner neuen Teammitglieder festlegen , der Administrator darüber hinaus als Mitglied einer teamanrufgruppe für jedes Mitglied in seinem Team Mike hinzugefügt.
    
- Eine Praxis des Kundendiensts in der Personalabteilung bei Contoso besteht darin, allen Anrufern vom ersten Anruf an persönlichen Service zu bieten. Da alle Mitglieder der Abteilung sehr nah beieinander sitzen, kann das gleichzeitige Klingeln auf allen Telefonen bei Teamanrufen sehr störend für das Team sein. Um den besten Service bereitzustellen, ohne Beeinträchtigung der Teammitglieder, nutzt die Skype für Business Server 2015 Administrator der Gruppe anrufen Pickup-Funktion. Der Administrator fügt alle Abteilungsmitglieder einer Annahmegruppe hinzu und teilt der Abteilung die Annahmegruppennummer mit. Wenn nun Samantha nicht an ihrem Platz ist, bemerkt Joe, dass ihr Telefon klingelt, und kann den Anruf von seinem Platz aus annehmen.
    
### <a name="requirements"></a>Anforderungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Auf diesem Computer muss UCMA 3.0 installiert sein. Um das Tool auszuführen, muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.
  
### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool

1. Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Bei Bedarf kann hinzufügen, die einen Pool einen neuen vertrauenswürdigen Anwendungspool über die Skype für Business Server-Verwaltungsshell das folgende Cmdlet ausführen:
    
  ```
  New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
  ```

    > [!NOTE]
    > Auf allen Computern, auf denen das SEFAUtil-Tool ausgeführt werden soll, muss UCMA 3.0 installiert sein. 
  
2. In der Topologie muss eine vertrauenswürdige Anwendung für das SEFAUtil-Tool definiert sein. Um SEFAUtil als eine neue vertrauenswürdige Anwendung definieren möchten, verwenden Sie die Skype für Business Server-Verwaltungsshell, und führen Sie das folgende Cmdlet: 
    
  ```
  New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
  ```

    > [!NOTE]
    > Gegebenenfalls kann ein anderer Port verwendet werden. 
  
3. Die Topologieänderungen müssen aktiviert werden. Aktivieren der Topologie kann über die Skype für Business Server-Verwaltungsshell erfolgen durch das folgende Cmdlet ausführen: 
    
  ```
  Enable-CsToplogy
  ```

4. Falls erforderlich, installieren Sie die Skype für Business Server 2015 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil (der Server muss Bestandteil einer vertrauenswürdigen Anwendungspool) verwendet werden.
    
5. Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie hierzu das Tool an einer Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. Standardmäßig wird das Tool im gespeichert: "...\Programme\Microsoft Files\Skype für Business Server 2015\Reskit". Verwenden Sie zum Anzeigen der Anrufweiterleitungseinstellungen eines Benutzers den folgenden Befehl: 
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
  ```

    Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.
    
#### <a name="group-call-pickup"></a>Gruppenanrufannahme

Gruppe aufrufen Pickup-erfordert zusätzliche Konfiguration in Skype für Business Server 2015 für die Funktion vollständig aktiviert werden soll. Bevor Sie Benutzern Annahmegruppen zuweisen, sollten Sie in der Produktdokumentation der Gruppenanrufannahme die Schritte zur Planung und Bereitstellung dieser Funktion nachlesen.
  
### <a name="examples"></a>Beispiele

#### <a name="display-current-call-handling-settings"></a>Anzeigen aktueller Anrufbehandlungseinstellungen

Der folgende Befehl zeigt die Anrufbehandlung für den entsprechenden Benutzer an.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`
  
> [!NOTE]
> In diesem Beispiel wird die **Option/Server** die Skype für Business Server für die Verbindung angeben.
  
 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Festlegen des Ziels für Anrufweiterleitung/Keine Antwort

In diesem Beispiel wird der Anruf weiterleiten/Nein-Antwort Ziel und die anrufverzögerung. Die Option/Server ist hier nicht enthalten. SEFAUtil versucht, AutoErmittlung der Skype für Business Server 2015.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Aktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel aktiviert sofort die Anrufweiterleitung an einen anderen Benutzer.
  
```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Deaktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel deaktiviert sofort die Anrufweiterleitung.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Hinzufügen eines Benutzers als Stellvertretung und Einrichten von gleichzeitigem Klingeln bei Stellvertretungen

Dieses Beispiel fügt einen Benutzer als Stellvertretung hinzu und richtet das gleichzeitige Klingeln bei Stellvertretungen ein.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Ändern der Regel für gleichzeitiges Klingeln bei Stellvertretungen

Dieses Beispiel ändert die Regel für gleichzeitiges Klingeln bei Stellvertretungen, die im vorherigen Beispiel festgelegt wurde, in die Anrufverzögerungsregel.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>Entfernen der Stellvertretung

Dieses Beispiel entfernt die Stellvertretung.
  
> [!NOTE]
> Wenn die letzte Stellvertretung entfernt wurde, wird das Anrufen von Stellvertretungen automatisch deaktiviert. 
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Hinzufügen einer Stellvertretung und Einrichten der Regel „Anrufweiterleitung an Stellvertretungen“

Dieses Beispiel fügt eine Stellvertretung hinzu und richtet die Regel „Anrufweiterleitung an Stellvertretungen“ ein.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Aktivieren von gleichzeitigem Klingeln und Festlegen einer Zielnummer

Diese Beispiel aktiviert gleichzeitiges Klingeln und legt eine Zielnummer für diese Funktion fest.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Um die Zielnummer für gleichzeitiges Klingeln eines Benutzers zu ändern, für den gleichzeitiges Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Parameter „/enablesimulring“. Andernfalls wird die Zielnummer nicht geändert. 
  
 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Deaktivieren von gleichzeitigem Klingeln

Dieses Beispiel deaktiviert gleichzeitiges Klingeln.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Teamanrufgruppen-Mitglieder

Dieses Beispiel fügt der Teamanrufgruppe eines Benutzers ein Teammitglied hinzu und aktiviert gleichzeitiges Klingeln für die Teamanrufgruppe.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Durch das Hinzufügen eines Teammitglieds zur Teamanrufgruppe eines Benutzers werden die Einstellungen der Benutzer für gleichzeitiges Klingeln automatisch auf gleichzeitiges Klingeln für die Teamanrufgruppe umgestellt. 
  
 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Entfernen eines Mitglieds aus der Teamanrufgruppe

Diese Beispiel entfernt ein Teammitglied aus der Teamanrufgruppe eines Benutzers.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Wenn das einzige Mitglied der Teamanrufgruppe entfernt wird, wird automatisch das gleichzeitige Klingeln für die Teamanrufgruppe deaktiviert. 
  
 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Festlegen der Anrufverzögerung für die Teamanrufgruppe

Dieses Beispiel ändert die Zeiteinstellung der Anrufverzögerung für die Teamanrufgruppe.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Aktivieren des Teamanrufs

Dieses Beispiel aktiviert den Teamanruf für einen angegebenen Benutzer.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Wenn teamanrufgruppe des Benutzers keine Member aufweist, nicht teamanrufgruppe aktiviert. 
  
 **Ausgabe**
  
#### <a name="disable-team-call"></a>Deaktivieren des Teamanrufs

Dieses Beispiel deaktiviert den Teamanruf für einen angegebenen Benutzer.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Aktivieren der Gruppenanrufannahme und Zuweisen einer Annahmegruppe zu einem Benutzer

Dieses Beispiel weist einem Benutzer eine Annahmegruppe zu und aktiviert die Gruppenanrufannahme.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Ausgabe**
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Deaktivieren der Gruppenanrufannahme

Dieses Beispiel deaktiviert die Gruppenanrufannahme für einen angegebenen Benutzer.
  
```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, bleibt die Gruppennummer, die dem Benutzer zugewiesen war, nicht erhalten. Wenn Sie die Gruppenanrufannahme für diesen Benutzer anschließend wieder aktivieren möchten, müssen Sie die Gruppennummer erneut mithilfe des Parameters „/enablegrouppickup“ zuweisen. 
  
```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Beschreibung

SYSPrep.ps1 ist ein Windows PowerShell-Skript, das die folgenden Skype Business Server 2015 erforderliche Komponenten auf Ihrem Computer der Windows Server 2008-Betriebssystem installiert.
  
- Microsoft .NET Framework 4.5
    
- Microsoft SQL Server Express
    
- Windows PowerShell, Version 3.0
    
- Visual C++ 2010 Redistributable
    
- Updates für Internetinformationsdienste
    
- Windows Identity Foundation
    
- Skype für Business Server 2015 Hauptdateien
    
 Zwar ähnelt der Skriptname dem des Systemvorbereitungsprogramms für die Microsoft Windows-Betriebssysteme, doch sind beide unterschiedlich. Mit diesem Skript wird nur die erforderlichen Komponenten für Skype für Business Server 2015 installieren. Sobald diese installiert sind, kann mit dem Windows-Tool für die Systemvorbereitung ein Image des Servers erstellt werden.
  
### <a name="requirements"></a>Anforderungen

Vor dem Ausführen des Skripts SYSPrep.ps1, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (beispielsweise **D:\Setup)**. In diesem Ordner muss auch enthalten eine Kopie der Skype für Dateien, Business Server 2015, insbesondere **Setup.exe.** Die erforderlichen Dateien können Sie an folgenden Orten herunterladen:
  
|**Voraussetzung**|**Standort**|
|:-----|:-----|
|Microsoft .NET Framework 4.5  <br/> |http://go.microsoft.com/?linkid=9816306  <br/> |
|Microsoft SQL Server Express 2008 R2  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=23650  <br/> |
|Windows PowerShell, Version 3.0  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34595  <br/> |
|Visual C++ 2010 Redistributable  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=5555  <br/> |
|Updates für Internetinformationsdienste  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=34869  <br/> |
|Windows Identity Foundation  <br/> |http://www.microsoft.com/en-us/download/details.aspx?id=17331  <br/> |
|Skype für Business Server 2015 Setup.exe  <br/> |Kopieren von Skype für Business Server 2015 Medien  <br/> |
   
### <a name="parameter"></a>Parameter

Der Parameter **- SetupFolder** nimmt als Argument an den Speicherort des erforderlichen Dateien
  
### <a name="examples"></a>Beispiele

Zum Ausführen des Skripts SYSPrep.ps1 und die Skype Business Server 2015 erforderliche Komponenten installieren, führen Sie den folgenden Befehl aus einer Eingabeaufforderung mit erhöhten Rechten aus:
  
```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration
<a name="UNAM"> </a>

Das nicht zugewiesene Nummer Ankündigungen Migrationstool ermöglicht eine Skype Business Server 2015 Administrator verschieben Sie die Konfiguration nicht zugewiesener Nummern, die von der ankündigungsanwendung aus einer Quelle Skype für zu Business Server oder Pool bedient wird ein Ziel Skype für Business Server oder Pool.
  
### <a name="description"></a>Beschreibung

Das Tool Unassigned Number Announcements Migration ist ein Windows PowerShell-Skript, das die Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quellserver oder -pool zu einem anderen Server oder Pool verschiebt.
  
Bei Ausführung des Unassigned Number Announcements Migration-Skripts werden folgende Vorgänge durchgeführt:
  
1. Verschieben aller Audiodateien, die von den Ankündigungen für nicht zugewiesene Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Dateispeicher des Zielservers oder -pools
    
    > [!NOTE]
    > Die Audiodateien werden aus dem Quellpool entfernt, sobald sie in der Zielpool kopiert haben. 
  
2. Verschieben aller Ankündigungen für nicht zugewiesene Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Zielserver oder -pool
    
3. Erneutes Zuweisen aller nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool verwaltet wird, zum Zielserver oder -pool
    
Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, nun mit derselben Konfiguration vom Zielserver oder -pool bedient.
  
### <a name="output"></a>Ausgabe

Das Skript **Move-CsAnnouncementConfiguration** gibt an, in der Skype für Business Server-Verwaltungsshell-Fenster aus, in dem sie den Erfolg oder das Fehlschlagen des Migrationsvorgangs ausgeführt hat.
  
Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die erfolgreich in das Ziel verschobenen nicht zugewiesenen Nummernbereiche in funktionsfähiger Form am Ziel, während der Rest der noch zu migrierenden nicht zugewiesenen Nummernbereiche in der Quelle verbleibt – ebenfalls in funktionsfähigem Zustand. Um die restliche Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.
  
### <a name="purpose"></a>Verwendungszweck

Das Unassigned Number Announcements Migration-Skript kann in den drei folgenden Szenarien eingesetzt werden:
  
- **Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype für Business Server:** Contoso ist bei der Migration zu Skype für Business Server 2015 und im Rahmen des Migrationsvorgangs der Skype für Business Server Administrator möchte die von der ankündigungsanwendung von Lync bedient nicht zugewiesener Nummern Konfiguration verschieben Zu den neuen Skype für die Bereitstellung von Business Server 2015 Server 2013-Bereitstellung. Um die Konfigurationseinstellungen zu verschieben, verwendet der Skype für Business Server-Administrator das nicht zugewiesene Nummer Ankündigungen Migration Tool.
    
- **Rollbacks einer bereitstellungs von Skype für Business Server 2015 zu Lync Server 2013:** Fälligkeitsdatum unerwarteten Faktoren verfügt über einen Rollback die Migration zu den neuen Skype für die Bereitstellung von Business Server 2015 Contoso. Um mit dem Dienst Systemausfallzeit zu minimieren, verwendet die Skype für Business Server-Administrator das nicht zugewiesene Nummer Ankündigungen Migrationstool die Konfiguration aus der Skype für Business Server 2015 Bereitstellung der Lync Server 2013-Bereitstellung Rollback zu.
    
- **Verschieben von Daten zwischen Bereitstellungen:** Contoso wird gerade Ersetzen von allen Servern eines Pools mit neueren Servern. Verschieben Sie ihre Strategie besteht darin, eine neue Skype für Business Server 2015-Pool bereitstellen alle Daten vom alten auf den neuen Pool, und klicken Sie dann verwerfen der alten Pools. Sobald der neue Pool bereitgestellt ist, wird die Konfiguration mit dem Tool Unassigned Number Announcements Migration aus dem alten Pool in den neuen verschoben.
    
#### <a name="requirements"></a>Anforderungen

Hier sind die Hauptanforderungen für eine erfolgreiche Ausführung des Tools:
  
1. Das Skript muss von einem Computer ausgeführt werden, Skype für Business Server-Verwaltungsshell installiert sind.
    
2. Der ankündigungsanwendung wurde erfolgreich in die Quell- und Skype für Business Server oder Pools bereitgestellt werden.
    
#### <a name="move-csannouncementconfiguration-script"></a>Skript „Move-CsAnnouncementConfiguration“

Das Skript „Move-CsAnnouncementConfiguration“ erfordert die in der Tabelle unten beschriebenen zwei Parameter.  
  
![Parameter „Move-CsAnnouncementConfiguration“](../media/Reskit_2012_Tools_Documentation_Image41.JPG)
  
### <a name="examples"></a>Beispiele

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Verschieben Sie die nicht zugewiesenen Nummern Ansagen Konfiguration aus einem Lync Server 2013-Pool in einen Skype für Business Serverpool 2015

Dieses Beispiel verschiebt die nicht zugewiesenen Nummern Ansagen aus dem Quellpool (Lync Server 2013) an die Zielpool (Skype für Business Server 2015).
  
```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com

```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Verschieben der nicht zugewiesenen Nummern Ansagen Konfigurations aus einer Skype für Business Serverpool 2015 in einer Lync Server 2013-Pool

Dieses Beispiel verschiebt die nicht zugewiesenen Nummern Ansagen aus dem Quellpool (Skype für Business Server 2015) an die Zielpool (Lync Server 2013).
  
```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

Das Tool zum Web Conf Daten kann der Administrator von Skype für die Kommunikationssoftware Business Server 2015 mehr Kontrolle über die Daten des Organisators Webkonferenzen zugeordnet haben. Szenarien umfassen die Möglichkeit, einen bestimmten Benutzer Besprechungsdaten basierend auf einer Zeitkriterien Stempel zu löschen.
  
### <a name="description"></a>Beschreibung

Mit diesem Tool können Administratoren die folgenden Vorgänge durchführen:
  
1. Suchen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind
    
2. Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind
    
3. Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind und deren Alter einen bestimmten Wert überschreitet
    
4. Verschieben aller Webkonferenzdaten, die einem Benutzern zugeordnet sind, wenn diese Benutzer aus einem Pool in einen anderen verschoben werden
    
> [!NOTE]
> Resource Kit-Tools für Lync Server 2010 unterstützt das Verschieben von allen Web Conferencing Daten mit einem einzelnen Benutzer verknüpft ist, wenn der Benutzer von einem Pool in einen anderen verschoben wird. Diese Funktionalität wird von diesem Tool wird der Parameter **MoveConferenceData** jetzt veraltet. Weitere Informationen zu diesem Parameter finden Sie unter [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) -Cmdlet.
  
Das Tool löscht Besprechungsdaten nur für inaktive Besprechungen. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.
  
Dieses Tool muss auf einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool verwaltet werden.
  
### <a name="output"></a>Ausgabe

Dieses Tool gibt die Ergebnisse der folgenden Vorgänge aus:
  
- Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, deren Organisator dieser Benutzer ist.
    
- Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.
    
### <a name="requirements"></a>Anforderungen

Das Tool muss im selben Pool ausgeführt werden, in dem der Organisator zurzeit verwaltet wird.
  
Das Tool muss mit Administratorrechten und mit Zugriff auf den Inhaltsdateispeicher ausgeführt werden.
  
### <a name="examples"></a>Beispiele

In der folgenden Tabelle werden die Parameter beschrieben, die zum Teil in den Beispielen verwendet werden.
  
![Parameter für das Webkonferenzdaten-Tool](../media/Reskit_2012_Tools_Documentation_Image51.JPG)
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.
  
```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

Oben sehen Sie ein Beispiel für einen Löschbefehl. Der Löschbefehl entfernt alle inaktiven Besprechungsordner dieses Benutzers.
  
### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenzbesprechungsdaten benötigen.
  

