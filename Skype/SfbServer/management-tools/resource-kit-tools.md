---
title: Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit hilft Ihnen, Routineaufgaben für IT-Administratoren zu vereinfachen, die Skype for Business Server 2015 bereitstellen und verwalten. Beispielsweise kann das Tool Web Conf Data verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden. Mithilfe des SEFAUtil-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.
ms.openlocfilehash: 1a0b787f8cd82291d408e3e3ad30e58e0b8a3627
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888884"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015

In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit hilft Ihnen, Routineaufgaben für IT-Administratoren zu vereinfachen, die Skype for Business Server 2015 bereitstellen und verwalten. Beispielsweise kann das Tool **Web Conf Data** verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden. Mithilfe des **SEFAUtil**-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Um das Skype for Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) aus dem Download Center herunter.

Führen Sie **OCSResKit.msi ** aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Tools im folgenden Pfad: **%ProgramFiles%\Skype for Business Server 2015\ResKit**. Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner. Tools, die über Hilfsdateien verfügen, befinden sich in eigenen Unterordnern.

## <a name="supported-environments"></a>Unterstützte Umgebungen

Das Resource Kit für Skype for Business Server 2015 sollte auf einem Server installiert werden, der die für Skype for Business Server 2015 erforderlichen Spezifikationen erfüllt, in der Regel für die Ausführung von Skype for Business Server 2015.

## <a name="resource-kit-tools-overview"></a>Resource Kit-Tools – Übersicht

Im folgenden finden Sie eine Liste der Tools, die im Skype for Business Server 2015 Resource Kit bereitgestellt werden. Im folgenden Abschnitt wird jedes Tool mit seinen Anforderungen und Beispielanwendungen beschrieben.

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

Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in Skype for Business Server 2015 anpassen können. Mit diesem Tool können auch Administratoren von Skype for Business Server 2015 die Standardeinstellungen für den Adressbuchdienst wiederherstellen.

### <a name="description"></a>Beschreibung

ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory-Domänendienst Attribute konfigurieren können, die mit dem Adressbuchdienst verknüpft sind.

Dies sind die primären Verwendungsszenarien für das Tool:

- So können Administratoren Attribute in den Active Directory-Domänendiensten den Attributen für Skype for Business Server 2015 zuordnen.

- Administratoren das Angeben des Attributs in Active Directory Domain Services ermöglichen, das in die Adressbuchdienst-Dateien aufgenommen oder aus diesen ausgeschlossen werden soll

- Administratoren das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts ermöglichen

Das ABSConfig-Tool kann mithilfe der Datei "ABSConfig. exe" gestartet werden. Das Tool wird auf der Registerkarte **Attribute konfigurieren** geöffnet. Diese Tabelle enthält Optionen zum Zuordnen von Active Directory-Domänendienst Attributen zu den Attributfeldern für Skype for Business Server 2015 und zum Angeben der Benutzer, die in Adressbuchdienst Dateien basierend auf bestimmten Attribut Filtern enthalten oder ausgeschlossen werden sollen. Darüber hinaus gibt es Optionen, um den Wert der Telefonnummer anzupassen, der in die Adressbuchdatei aufgenommen werden soll. Mit der Option **Standard wiederherstellen** können Administratoren die Einstellungen des Adressbuchdiensts auf Standardwerte zurücksetzen.

> [!NOTE]
> Die erneute Zuordnung von anzeigen Attributen zu unterschiedlichen OC-Feldnamen funktioniert nur für den Download von Adressbuchdateien und wird von der Adressbuch-Webabfrage nicht unterstützt.

### <a name="output"></a>Ausgabe

ABSConfig speichert die Konfiguration des Adressbuchdiensts in der Datenbank.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Verwendungszweck

ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen des Skype for Business Server 2015-Adressbuchdiensts.

### <a name="requirements"></a>Anforderungen

#### <a name="computer"></a>Computer

ABSConfig kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem Skype for Business Server 2015 installiert ist. Im Fall von Skype for Business Server 2015, Enterprise Edition, kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.

#### <a name="network"></a>Netzwerk

Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.

#### <a name="software"></a>Software

Die folgenden Softwarekomponenten müssen vor der Ausführung des ABSConfig-Tools installiert werden:

- Skype for Business Server 2015

#### <a name="users"></a>Benutzer

Administratoren, die über die erforderlichen Berechtigungen verfügen, um die Bereitstellung von Skype for Business Server 2015 zu aktualisieren.

### <a name="examples"></a>Beispiele

ABSConfig kann durch Eingeben von **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie eine Abbildung der Benutzeroberfläche des ABSConfig-Tools.

![Das Tool "ABSConfig. exe".](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Zusammenfassung

Das ABSConfig-Tool bietet Administratoren ein schnelles und einfach zu Bedientool zum Anpassen des Skype for Business Server 2015-Adressbuchdiensts.

## <a name="bandwidth-policy-service-monitor"></a>Bandwidth Policy Service Monitor
<a name="bpsm"> </a>

Mit dem Tool Bandwidth Policy Service Monitor können Administratoren eine Liste der folgenden Elemente anzeigen:

1. Alle konfigurierten Skype for Business Server 2015-Bandbreitenrichtlinien Dienste (Authentifizierung und Kern) in der Topologie

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
>  Wenn das Tool für den bandbreitenrichtliniendienst Monitor beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreitenrichtlinien Dienste einen Fehler auftritt, werden die Informationen in den **Computer Informationen** und auf den Registerkarteninformationen zur **Topologie** nicht ausgefüllt. Es ist aber möglich, dass das Tool anfangs eine Verbindung mit dem Dienst herstellt, die dann später verloren geht. In solchen Fällen werden Administratoren eventuell veraltete Informationen angezeigt. Beide Registerkarten enthalten einen Zeitstempel **Last Updated**, mit dessen Hilfe Administratoren bestimmen können, wann die Daten für einen bestimmten Bandbreiten-Richtliniendienst zum letzten Mal aktualisiert wurden.

### <a name="output"></a>Ausgabe

Es gibt keine Befehlszeilenausgabe. Die Programmausgabe erfolgt auf der grafischen Hauptbenutzeroberfläche.

### <a name="purpose"></a>Verwendungszweck

Das Tool Bandwidth Policy Service Monitor soll Administratoren Einblick in den Zustand jedes Bandbreiten-Richtliniendiensts zu verschaffen, der in der Topologie definiert ist. Zusätzlich können Administratoren die Echtzeit-Bandbreitennutzung für alle Verbindungen anzeigen, die im Netzwerkkonfigurationsdokument definiert sind.

### <a name="requirements"></a>Anforderungen

Das Tool für bandbreitenrichtliniendienst Monitor muss auf einem Computer ausgeführt werden, der Teil der Skype for Business Server-Topologie ist.

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

Bei jeder sprach-und Videobereitstellung ist es wichtig, den Trend der Bandbreitennutzung von Mediendatenverkehr im gesamten Unternehmensnetzwerk zu überwachen und zu verstehen. Genau dies ermöglicht das Tool Bandwidth Utilization Analyzer Administratoren. Das Tool bietet folgende Funktionen:

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

- **WanLinkLogCollector. exe** mit diesem Tool kann der Benutzer die erforderlichen Informationen eingeben.

- **BandwidthUtilizationAnalyzer. xlsm** ein Microsoft Excel-Kalkulationstabellen-softwarebericht wird automatisch von WanLinkLogCollector. exe gestartet. Mit dieser Anwendung können Benutzer, wie später in diesem Artikel gezeigt, Filter auf den Bericht anwenden.

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

1. **Protokollieren der Zeitachse** Bereitstellen der Zeitachse, für die der Bericht generiert werden muss

2. **Angeben der Dateiverzeichnisse** Bereitstellen von Dateispeicherort Informationen

3. **Sammeln der Protokolle und Starten der Berichtsanzeige** Ausführen des Befehls zum Generieren des Berichts

#### <a name="step-1---log-the-timeline"></a>Schritt 1 – Protokollieren des Zeitraums

Durch die Protokollierung des Zeitraums können die Benutzer des Tools, wie in der Abbildung unten dargestellt, Folgendes angeben. 

1. **Startdatum** Dies ist das Startdatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 1. August 2010.

2. **Enddatum** Dies ist das Enddatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 30. September 2010.

     ![Anfangs-und Endtermine in der Bandbreitennutzung A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Schritt 2 – Angeben der Dateiverzeichnisse

Die folgenden Dateiverzeichnisse können von den Benutzern wie gezeigt angegeben werden.

- **Speicherort für Server Protokolldateien** Der Speicherort des Ordners, in dem die Bandbreitenrichtlinien Serverprotokolle gespeichert werden. Dies ist in der \<Regel in\> \\ Fileserver<Wahl\>von FE \AppServerFiles\PDP.

- **Speicherort für temporären Dateispeicher** Der Speicherort der temporären Datei, in dem zwischen Dateien gespeichert werden, während der Bericht generiert wird.

    ![Dateiverzeichnisse in der Bandbreitennutzung Anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > Stellen Sie sicher, dass den Benutzern des Tools ausreichender Dateizugriff auf den Speicherort der Serverprotokolle und der temporären Dateien gewährt wird.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Schritt 3 – Erfassen der Protokolle und Starten der Berichtanzeige

Um die Protokolle zu erfassen und die Berichtanzeige zu starten, klicken Sie, wie unten gezeigt, auf **Execute**. In diesem Schritt werden die erforderlichen Daten erfasst.

![Sammeln von Daten in der Bandbreitennutzung Analy](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Nach erfolgreicher Überprüfung der Eingabe wird die unten wiedergegebene Meldung angezeigt.

![Protokolliert die gesammelte Benachrichtigung in der Bandbreiten-utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Klicken Sie auf **OK**. „BandwidthUtilizationAnalyzer.xlsm“ wird automatisch gestartet. Befolgen Sie die im Meldungsfeld angezeigten Anweisungen. Ausführliche Informationen finden Sie im nächsten Abschnitt unter **Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**.


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

![Filterung nach Überschreitung des Grenzwerts.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtern nach **Critical levels**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach kritischen Ebenen.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtern nach **Under utilized**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach unter verwendet.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtern nach **Link Type**. Wählen Sie die Typen aus, die angezeigt werden sollen.

![Filtern nach Verknüpfungstyp.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Verbindungen angezeigt werden sollen.

![Filtern nach Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Anforderungen

- .NET Framework 3.5

- Microsoft Excel 2010 oder Excel 2007

### <a name="summary"></a>Zusammenfassung

Bandwidth Utilization Analyzer wird verwendet, um die Bandbreitenauslastung durch Audio für UC-Datenverkehr über das Netzwerk grafisch darzustellen. Mithilfe dieses Tools kann auch die Bandbreitenauslastung durch Video im Netzwerk dargestellt werden.

## <a name="call-parkometer"></a>Call Parkometer
<a name="callpark"> </a>

Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Datenbank mit den Orbits der geparkten Anrufe ermöglicht.

### <a name="description"></a>Beschreibung

Call Parkometer ist ein Tool zum Nachverfolgen der zurzeit geparkten Anrufe. Es erfasst außerdem Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS). Dieses Befehlszeilentool bietet Lese-und Schreibzugriff auf die CPS-Orbit-SQL Server-Datenbank von einem lokalen oder Remote verbundenen Computer.

Alle Optionen schließen sich gegenseitig aus. Befehlszeilensyntax:

- **-o-** Parameter – listet alle für diesen Pool konfigurierten Umlaufbahn Bereiche auf.

- **-n-** Parameter – listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf. Folgende Informationen werden angezeigt:

  - Der SIP-URI (Session Initiation Protocol Uniform Resource Identifier) der geparkten und der parkenden Person

  - Der Hostname des Anrufparkservers, auf dem der Anruf geparkt ist

  - Der Zeitstempel, aus dem hervorgeht, wann der Anruf geparkt wurde

- **-f-** Parameter: Listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf.

- **-r \<n\> -** Parameter: listet \<die\> n letzten geparkten Anrufe auf. Folgende Informationen werden angezeigt:

  - SIP-URI der geparkten Person

  - SIP-URI der parkenden Person

  - Der Hostname des Anrufparkservers, auf dem der Anruf geparkt wurde

  - Der Zeitstempel, aus dem hervorgeht, wann der Anruf herangeholt oder abgebrochen wurde

- **-t\<n\> ** Parameter – testet, wie eine Umlaufbahn in der Datenbank reserviert wird, um die Zufälligkeit der zugewiesenen Orbit-Nummern anzuzeigen.

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

Wenn das Tool auf dem gleichen Computer wie der Anrufparkserver ausgeführt wird, gelten keine Anforderungen. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von Skype for Business Server 2015 verwendete SQL Server-Datenbank so konfiguriert sein, dass der Remotezugriff zulässig ist. Anruf Parkometer muss mit einer SQL Server-Datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem SQL Server des Pools herzustellen. Diese SQL Server-Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer. exe. config**definiert. Sie muss sich im gleichen Verzeichnis befinden, in dem sich parkometer. exe befindet. Die folgende XML-Datei ist ein Beispiel für eine parkometer. exe. config. Die Parameter, die konfiguriert werden müssen, sind Benutzername (beispielsweise mydomain\Administrator), Kennwort (beispielsweise mypassword) und Hostname (beispielsweise MyServer).

```xml
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

Bereitgestellte Umlaufbahn Bereiche: der Parameter-o listet alle für diesen Pool konfigurierten Umlaufbahn Bereiche auf (siehe Abbildung).

![Umlaufbahn Bereiche in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Derzeit geparkte Anrufe: der Parameter-n listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf (siehe Abbildung).

![Zurzeit geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Anzahl der freien Umlaufbahnen: der Parameter-f zeigt die Anzahl der derzeit freien Umlaufbahnen im Pool an (siehe Abbildung).

![Freie Umlaufbahnen in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Zuletzt geparkte Anrufe: der Parameter \<-\> r n listet \<die\> n letzten geparkten Anrufe auf, wie hier gezeigt.

![Vor kurzem geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Test Orbit-Reservierung: der- \<t\> n-Parameter testet, wie eine Umlaufbahn in der Datenbank reserviert wird (siehe Abbildung).

![Testen Sie Orbit-Reservierungen in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Zusammenfassung

Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Beschreibung

Dbanalyze ist ein Befehlszeilentool, das Administratoren hilft, Analyseberichte zu den Skype for Business Server 2015-Datenbanken zu sammeln. DBAnalyze verfügt über folgende Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:

- **Diagnosemodus** Erstellt einen Bericht, der Informationen zu Tabellen enthält (Anzahl der Datensätze, Fragmentierung, Datengröße, und Indexgröße), Daten-und Protokolldateigrößen, die letzte Sicherungszeit, die Kontaktverteilung zwischen Servern, auf denen Microsoft Office Communications Server ausgeführt wird, die durchschnittliche Anzahl der Berechtigungen, Kontakte, Container, Abonnements, Publikationen, Endpunkte pro Benutzer, nicht ordnungsgemäß vernetzte Benutzer, Benutzer, die nicht weitergeleitet werden können, die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, und die Datenbankversion.

    > [!NOTE]
    > Die Ausführung im Diagnosemodus kann die Serverleistung beeinträchtigen.

- **Benutzerdaten Modus** Meldet Kontakt-, Container-, Abonnement-, Veröffentlichungs-, Genehmigungs-und Kontaktgruppen Daten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in seinen Kontakt-und Berechtigungslisten haben. Dieser Modus berichtet außerdem Zusammenfassungsdaten für Konferenzen, die von einem Benutzer organisiert werden oder zu denen er eingeladen ist.

- **Konferenzmodus** Meldet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Details zur Terminplanung für die Konferenz, der Liste der eingeladenen Personen, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCU (Multipoint Control Units), der aktiven Teilnehmerliste und des Signalisierungs Status jedes Teilnehmers.

- **Decodieren der Besprechungs-ID** Decodiert eine vom **/pstnid** -Schalter angegebene PSTN-Besprechungs-ID (Public Switched Telephone Network), aber keine Verbindung zum Back-End, um detaillierte Informationen zu erhalten.

- **Konferenz auflösen** Dekodiert eine vom **/pstnid** -Schalter angegebene PSTN-Besprechungs-ID und zeigt Informationen zu der Konferenz an, die von der ID angegeben wird.

- **MCU-Modus** Meldet die ID, den Medientyp, die URL, den Heartbeat-Status, die Konferenz Auslastung und die Teilnehmer Auslastung für jede MCU im Pool.

- **Datenträger-Fragmentierungs Modus** Zeigt den Fragmentierungs Status aller Datenträger an.

Dieses Tool kann zum Diagnostizieren verschiedener Probleme verwendet werden oder Administratoren bei der Kapazitätsplanung unterstützen. Wenn beispielsweise die meisten der auf Server A verwalteten Benutzer auf Server B verwaltete Benutzer als Kontakte wählen, kann der Administrator die Benutzer von Server A auf Server B verschieben, um den Datenverkehr zwischen den Servern zu verringern.

### <a name="output"></a>Ausgabe

Dieses Tool gibt vordefinierte Berichte über die Skype for Business Server 2015-Datenbank aus. **Pfad**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Verwendungszweck

Wenn Sie Dbanalyze. exe installieren möchten, kopieren Sie Sie in einen lokalen Ordner, und führen Sie dann das Tool aus. Führen Sie den folgenden Befehl in der Befehlszeile aus, um das Tool zu verwenden. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Die Beschreibungen für die Befehlszeilenoptionen sind unten dargestellt.

![Befehlszeilenoptionen für "Dbanalyze. exe".](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Voraussetzungen

 **Computer** Dbanalyze kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem Skype for Business Server 2015 installiert ist.

 **Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.

 **Software** Die Softwarekomponenten von Skype for Business Server 2015 müssen vor der Ausführung von Dbanalyze installiert werden.

 **Benutzer** In der folgenden Tabelle sind die Administratoren aufgeführt, die über die erforderlichen Berechtigungen für den Zugriff auf Skype for Business Server 2015-Datenbanken verfügen.

![Berechtigungstabelle für "Dbanalyze. exe".](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Für den **/report:disk**-Modus ist ein lokales Administratorkonto erforderlich.

### <a name="examples"></a>Beispiele

Hier sind Beispiele für gültige „Dbanalyze.exe“-Befehle:

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Zusammenfassung

Dbanalyzer bietet Administratoren eine schnelle und einfache Analyse von Skype for Business Server 2015-Datenbanken.

## <a name="import-storage-service-data"></a>Import Storage Service Data
<a name="Issd"> </a>

Mit dem Resource Kit-Tool „ImportStorageServiceData“ können Warteschlangen- und Endpunktdaten, die aus dem Speicherdienst (LYSS) geleert wurden, wieder zurück in den Speicherdienst importiert werden.

### <a name="description"></a>Beschreibung

Die Leerung der Daten aus dem Speicherdienst kann automatisch (regelmäßig) auf Grundlage des Warteschlangenelementstatus oder der Datenbankgröße erfolgt sein. Das Leeren kann aufgrund eines manuellen Aufrufs des Cmdlets für Poolfailover oder des Cmdlets „StorageServiceFullFlush“ (das vom Cmdlet für Poolfailover aufgerufen wird) erfolgt sein. Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn sich die Datenbankgröße des Speicher Diensts (LYSS) auf den Front-Ends über der normalen Ebene befindet, weil dies wahrscheinlich dazu führt, dass mehr Daten wieder exportiert werden. Darüber hinaus sollten alle Probleme, die zu Fehlern beigetragen haben, die dazu geführt haben, dass die Speicherdienst Warteschlange anwächst, zunächst aufgelöst werden (beispielsweise Exchange-Endpunkt Fehler, Netzwerkprobleme oder andere Probleme).

 **Szenario 1:** während des Pool-Failovers können Dateien für jedes Front-End vom Speicherdienst geleert werden. Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.

 **Szenario 2:** die Daten werden jeden Tag automatisch geleert oder als Antwort auf eine Speicherdienst Datenbank, die bestimmte Größengrenzwerte überschreitet (beispielsweise 60%, 80%, 90% voll). Diese automatisch geleerten Daten sollten vom Administrator routinemäßig erneut importiert werden. Wenn das SCOM-Überwachungspaket nicht bereitgestellt wird, gibt es in der obigen Situation Ereignisse für den Skype for Business Server-Speicherdienst, die sich auf Daten beziehen, die vom Speicherdienst geleert werden. Ereignis-IDs von 32075 (vollständiger Flush-Vorgang wird gestartet), 32076 (vollständiger Flush wurde abgeschlossen), 32082 (Wartungsebene wurde gestartet), 32083 (Maintenance Level Flush Complete), 32089 (Flush ist aufgrund des Auffüllens der Datenbank aufgetreten). Hinweis Diese Ereignis-IDs entsprechen der RTM-Version. Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien vorhanden sind, die geleert wurden. Diese Daten sollten routinemäßig mit diesem Tool wieder importiert werden, beispielsweise einmal pro Woche.

Wenn für die Online Dienstversion die Statusüberwachung SCOM Pack für Skype for Business Server bereitgestellt wird, gibt es neue Benachrichtigungen, die vom Administrator aufgefordert werden, die leeren Daten wieder in den Speicherdienst zu importieren. Im Ereignisprotokoll auf dem Front-End-Server befindet sich ein entsprechendes Ereignis, das die Benachrichtigung ausgelöst hat. Das Ereignis enthält eine Beschreibung des übergeordneten Pfads, unter dem sich die gelesenen Datendateien befinden, sowie die Anzahl der Dateien, die den Warnungskriterien entsprechen. Bei den Warnungskriterien handelt es sich um x oder mehr Dateien unter dem bestimmten übergeordneten Pfad, die mindestens Y Tage alt sind (wobei x und Y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei überschrieben werden können). Nachfolgend werden zwei Beispiele für Ereignisse angezeigt, die die Integritäts Warnung auslösen können, wobei der Unterschied der übergeordnete Pfad ist. Eine Möglichkeit ist unter Web Service File Share zu finden, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist. (Beispiel: c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService). Der Administrator führt dann dieses reskit-Tool aus.

Dieses Tool erhöht die Auslastung von CPU und E/A-Vorgängen auf dem Front-End-Server, auf dem es ausgeführt wird, sowie auf anderen Front-End-Servern, wenn der Front-End-Server, auf dem das Tool ausgeführt wird, nicht Besitzer der Daten ist. Wir empfehlen die Ausführung dieses Tools, wenn die Auslastung von CPU und E/A-Vorgängen auf den Front-End-Servern niedrig ist, beispielsweise außerhalb der Spitzenzeiten. Darüber hinaus kann dieses Tool zwei bis drei Minuten für den Import einer Datendatei benötigen. Denken Sie hieran, wenn Sie die voraussichtliche Ausführungsdauer des Tools schätzen. Die von dem Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt. Löschen Sie sie, wenn darin keine Fehler gemeldet werden, da die Protokolldatei mehrere 10 MB übersteigen kann.

![Beispiel Ereignisse für das Speicher Server-Ereignisprotokoll.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Voraussetzungen

Installieren Sie die Skype for Business Server 2015 Resource Kit-Tools. Das Tool wird auf von der Domäne verbundenen Computern ausgeführt, auf denen Skype for Business Server und die Skype for Business Server-Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist. Diese Datenbank wird vom Tool verwendet, um den Speicherort der Webservice-Dateifreigabe für den Pool abzurufen. Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools zunächst Windows PowerShell-Remoting mithilfe von **enable-PSRemoting** auf jedem Front-End-Server und dem Computer aktivieren, von dem aus das Tool ausgeführt wird. Andernfalls schlagen die Remote-Windows PowerShell-Befehle dieses Tools fehl. Windows PowerShell-Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem Sie fertig sind. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über die Berechtigung "Lesen/Schreiben" für die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird. Andernfalls schlägt das Tool mit IO-Berechtigungsfehlern fehl.

> [!NOTE]
> Unter Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht unter dem BetriebssystemWindows Server 2008.

### <a name="examples"></a>Beispiele

```console
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

Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen. Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzergesamtstrukturen als ein Active Directory-Domänendienst-Kontaktobjekt mit einer zentralen Gesamtstruktur zu synchronisieren, in der Skype for Business Server 2015 installiert ist.

### <a name="description"></a>Beschreibung

 LCSSync verwendet die synchronisierten Active Directory-Domänendienste-Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzer für Skype for Business Server zu aktivieren. Zum Bereitstelleneiner einmaligen Anmeldung muss das primäre Benutzerkonto dem Active Directory-Domänendienst-Kontaktobjekt in der zentralen Gesamtstruktur für Skype for Business Server 2015 zugeordnet sein. Dieses Tool hilft bei der Durchführung dieser Zuordnung. Das Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents in Microsoft Identity Integration Server bereit.

### <a name="summary"></a>Zusammenfassung

Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015 in einer Multi-Forest-Umgebung.

## <a name="lookup-user-console"></a>Lookup User Console
<a name="LUC"> </a>

Das LookupUserConsole-Tool zeigt interne Skype for Business Server-Routinginformationen zu bestimmten Benutzern an. Diese Informationen können den Mitarbeitern des Microsoft-Supports dabei helfen, Probleme bei der Bereitstellung und beim Routing zu diagnostizieren.

### <a name="description"></a>Beschreibung

 Durch Ausführen von LookupUserConsole. exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert, und versucht, interne Skype for Business Server-Routinginformationen in Bezug auf diese anzuzeigen. Geben Sie **exit** ein, um das LookupUserConsole-Tool zu beenden.

### <a name="requirements"></a>Anforderungen

Installieren Sie das Skype for Business Server 2015 Resource Kit. Das Tool wird auf von der Domäne verbundenen Computern ausgeführt, auf denen Skype for Business Server installiert ist.

### <a name="examples"></a>Beispiele

C:\Program Files\Skype for Business Server 2015 \ reskit\>LookupUserConsole. exe

```console
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

Das MSTurnPing-Tool ermöglicht es einem Administrator der Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien Dienste in der Topologie ausgeführt werden.

### <a name="description"></a>Beschreibung

Das MSTurnPing-Tool ermöglicht es einem Administrator der Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien Dienste in der Topologie ausgeführt werden.

Mit dem Tool können Administratoren die folgenden Tests durchführen:

1. A/V-Edgeservertest: Das Tool führt mit allen A/V-Edgeservern in der Topologie die folgenden Tests durch:

   - Überprüfen, ob der Skype for Business Server-Audio/Video-Authentifizierungsdienst gestartet wurde, und kann korrekte Anmeldeinformationen ausgeben.

   - Überprüfen, ob der Skype for Business Server-Audio/Video-Edgedienst gestartet wurde und die Ressourcen auf dem externen Edge erfolgreich zuweisen können.

2. Test für Bandbreiten-Richtliniendienste: Das Tool führt mit allen Servern in der Topologie, auf denen die Bandbreiten-Richtliniendienste ausgeführt werden, die folgenden Tests durch:

   - Überprüfen, ob der Skype for Business Server-bandbreitenrichtliniendienst (Authentication) gestartet wurde und geeignete Anmeldeinformationen ausgeben kann.

   - Überprüfen, ob der Skype for Business Server-bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreiten Überprüfung erfolgreich durchführen kann.

Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist. 

### <a name="output"></a>Ausgabe

Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.

- Wenn der **AudioVideoEdgeServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015-Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015-Audio/Video-Edgedienst in der Topologie bereitstellen

- Wenn der **BandwidthPolicyServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015-bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015-bandbreitenrichtliniendienst (Core) in der Topologie bereitstellen

### <a name="requirements"></a>Anforderungen

- Dieses Tool muss auf einem Computer ausgeführt werden, der zur Topologie gehört und auf dem sich der lokale Speicher befindet.

- Das Tool muss als Administrator mit Zugriff auf den lokalen Speicher ausgeführt werden.

### <a name="examples"></a>Beispiele

Hier ist ein Beispiel für die Tooleingabe.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio/Video-und Bandbreitenrichtlinien Dienste ausgeführt werden.

## <a name="network-configuration-viewer"></a>Network Configuration Viewer
<a name="NCV"> </a>

Die Netzwerkkonfigurations-Anzeige kann von Skype for Business Server 2015 Communications Software-Administratoren verwendet werden, um die Anruf Zulassungs Steuerung (CAC)-Netzwerktopologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echt Zeit Kommunikationssitzungen zu ermöglichen, wie etwa Sprach-oder Videoanrufe auf der Grundlage der angegebenen Bandbreitenkapazität. Skype for Business Server 2015-Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtlinien Diensten erzwungen werden, die mit Skype for Business Server 2015 installiert werden.

### <a name="description"></a>Beschreibung

Mit Network Configuration Viewer („NetworkConfigurationViewer.exe“) können Administratoren die folgenden Aufgaben durchführen:

- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format.

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

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format**: Skype for Business Server 2015-Administratoren können die Konfiguration der CAC-Netzwerktopologie auf jedem Skype for Business Server 2015-Computer mithilfe der Option **Netzwerkkonfiguration herunterladen** wie in der folgenden Abbildung dargestellt laden und anzeigen. Bei der Bereitstellung auf einem Computer, der keine Verbindung zum Skype for Business Server 2015-Konfigurationsspeicher hat, kann das Tool keine derartige Konfiguration herunterladen oder anzeigen.

![Herunterladen der Netzwerkkonfiguration.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei in einem grafischen Format:** Skype for Business Server 2015 Bandbreitenrichtlinien Server speichern die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Dateifreigabespeicherort von Skype for Business Server 2015. Skype for Business Server 2015-Administratoren können eine solche Datei in einem grafischen Format anzeigen, indem Sie die Option **Netzwerkkonfiguration öffnen** verwenden, wie unten dargestellt.

![Öffnen einer Protokolldatei für den Bandbreitenrichtlinien Server](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger: Skype for Business Server 2015-Administratoren können die Konfigurationsdatei der CAC-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option **Kopie der Netzwerkkonfiguration speichern** verwenden, wie unten dargestellt. Die gespeicherte Konfigurationsdatei kann dann offline als Grafik angezeigt werden.

![Speichern Sie die Netzwerkkonfiguration als XML-Datei.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Speichern und Speichern von CAC-Netzwerktopologie-Diagrammen im JPG-oder BMP-Format: Skype for Business Server 2015-Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG-und BMP-Dateiformate) speichern, indem Sie die Option **Netzwerk Konfigurations Diagramm als Bild speichern** verwenden, wie unten dargestellt.

![Speichern der Netzwerkkonfiguration als Bild](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:</strong> Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerk Websites, Bandbreiten Profile und IP-Adressen von Standort-Subnetzen in einem Text Format anzeigen, indem Sie die Option Netzwerkkonfigurationsdaten anzeigen verwenden, wie unten dargestellt.

![Anzeigen von Netzwerkkonfigurationsdaten](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Anzeigen der CAC-Netzwerktopologie in einer Struktur Ansichtsformatvorlage:** Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Struktur Ansichtsstil anzeigen, indem Sie die Systemsteuerung auf der linken Seite des Toolfensters verwenden, wie unten dargestellt.

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definieren von benutzerdefinierten Connectors für CAC-Netzwerktopologie-Links (wie Website-zu-Region-, Region-zu-Region-und Standort-zu-Standort-Links):** Skype for Business Server 2015-Administratoren können benutzerdefinierte grafische Connectors für CAC-Netzwerkkonfigurations-WAN-Links definieren, indem Sie die Einstellungen-Option verwenden, wie unten dargestellt. Dies erleichtert die Unterscheidung zwischen verschiedenen Netzwerkverbindungstypen, die in der Netzwerkkonfiguration bereitgestellt sind.

![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Anzeigen der Informationen zur CAC-Netzwerktopologie, der Regionsinformationen und der bereitgestellten Bandbreitenrichtlinien:** Skype for Business Server 2015-Administratoren können verwandte CAC-Netzwerk Regionsinformationen, Website Informationen und Informationen zur Bereitstellung von CAC-Bandbreiten mithilfe der nachstehend aufgeführten Optionen anzeigen. (Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **Info**.)

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die die CAC-Netzwerktopologie für Ihre Bereitstellung in einem grafischen Format anzeigen möchten.

## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

Die reaktionsgruppenanwendung bietet Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zuzugreifen. Leider ist keine grafische Ansicht dieser Daten außerhalb der Anwendung verfügbar. Das Tool für den Reaktionsgruppen-Agent Live Resource Kit behebt dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die durch Echtzeitinformationen zu Skype for Business-Kommunikationssoftware, wie etwa das vorhanden sein anderer Agents, verbessert werden.

### <a name="description"></a>Beschreibung

Response Group Agent Live ist eine Windows-Anwendung, die An- und Abmeldefunktionen sowie einige Echtzeitinformationen (wie Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bietet. Es handelt sich um eine erweiterte Version der Seite "Agentengruppen" (Zugriff über Skype for Business.

### <a name="purpose"></a>Verwendungszweck

Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschleife und leitet sie dann an Agent-Gruppen weiter. Um informierte Entscheidungen darüber treffen zu können, welche Anrufe bedient werden sollen, können Agents auf Echtzeitinformationen zu ihren Agent-Gruppen zugreifen. Dabei erfahren sie beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst verfügbar sind, werden auf intuitive Weise von Response Group Agent Live zur Verfügung gestellt.

#### <a name="features"></a>Funktionen

Das Live Tool für Reaktionsgruppen-Agents basiert auf dem Reaktionsgruppendienst und dem Skype for Business Server 2015 SDK. Es bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die durch den Reaktionsgruppendienst zur Verfügung gestellt werden (beispielsweise Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).

Die Abbildung unten zeigt die Hauptoberfläche von Response Group Agent Live.

![Das Live Tool für Reaktionsgruppen-Agents](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Folgende drei Hauptfeatures stehen Agents in Response Group Agent Live zur Verfügung:

- **Anmeldung/** Abmeldung: Anders als bei der Seite "Agentengruppen" (barrierefrei über Skype for Business Server 2015) können sich die Agents für Reaktionsgruppen-Agents Live nur an-und abmelden. Diese Anwendung bietet drei schnelle Methoden zum Anmelden oder Abmelden für Agents:

  - Klicken auf die Schaltflächen zum An-/Abmelden (grün und rot) in der Anwendung

  - Klicken auf das Taskleistensymbol mit der rechten Maustaste und Auswählen von „Sign-in“ oder „Sign-out“

  - Verwenden konfigurierbarer Tastenkombinationen

- **Gruppenmitgliedschaft:** Wenn eine Agentengruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an. Wenn Skype for Business Server 2015 auf demselben Computer wie diese Anwendung ausgeführt wird, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt. Agents können direkt von dort aus eine Chatnachricht senden oder andere Agents anrufen.

- **Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agent-Gruppen. Die Statistiken werden minütlich aktualisiert. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein optischer Indikator mit der aktuellen Anzahl der wartenden Anrufe hinzugefügt. Wenn Sie mit dem Mauszeiger auf einer Gruppe verweilen, wird außerdem die längste Wartezeit angezeigt.

### <a name="requirements"></a>Anforderungen

Response Group Agent Live erfordert .NET Framework 4.0. Um die Anwesenheits-und Visitenkarten Funktionen nutzen zu können, muss Skype for Business lokal installiert sein (und ausgeführt werden).

#### <a name="configuration"></a>Konfiguration

Response Group Agent Live kann mithilfe des Dialogfelds „Options“ in der Anwendung an die individuellen Anforderungen angepasst werden. Darüber hinaus können Administratoren die Standardhostadresse definieren, indem sie die Eigenschaft „defaultHostAddress“ in der Datei „RGAgentLive.exe.config“ direkt bearbeiten.

Die Abbildung unten zeigt das Dialogfeld „Options“, in dem Agents die Hostadresse und Tastenkombinationen konfigurieren können. Auf dieses Dialogfeld können Sie zugreifen, indem Sie auf der Hauptbenutzeroberfläche rechts oben auf die Schaltfläche „Options“ klicken.

![Das Dialogfeld "Live Optionen" des Reaktionsgruppen-Agents](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Folgende drei unterschiedliche Einstellungen können in der Konfiguration von Response Group Agent Live angepasst werden:

- Host Adresse: Dies ist in der Regel der FQDN des webpools, der zum Home-Pool des Agents gehört. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads an den Host).

- Tastenkombinationen: Die genauen Tastenkombinationen zum An- und Abmelden können angepasst werden. Die einzige Einschränkung besteht darin, dass beide Tastenkombinationen die "Windows-Logo"-Taste (zusätzlich zu mindestens einem anderen Schlüssel) enthalten müssen.

- Starten mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch beim Starten von Windows gestartet wird.

### <a name="examples"></a>Beispiele

Die Abbildung unten zeigt, wie Sie andere Agents anrufen oder ihnen eine Chatnachricht senden, indem Sie mit der rechten Maustaste im rechten Bereich auf den Kontakt klicken.

![Tätigen eines Anrufs oder Senden einer Chatnachricht](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

Die Abbildung unten zeigt, wie Response Group Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife sowie die längste Wartezeit all dieser eingehenden Anrufe anzeigt.

![Anzeigen von Warteschlangeninformationen](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Zusammenfassung

Schnelles An- und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Funktionen für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind. Mit dem Live Resource Kit-Tool für Reaktionsgruppen-Agents können Skype for Business Server 2015-Administratoren ihren Agenten eine Windows-Anwendung zur Verfügung stellen, die es Ihnen ermöglicht, Aufgaben auf eine schnellere und grafische Weise auszuführen.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (Secondary Extension Feature Activation) ist ein Befehlszeilentool, mit dem Skype for Business Server 2015 Communications Software-Administratoren und Helpdesk-Agents Stellvertretungen, Anrufweiterleitung und gleichzeitiges Klingeln konfigurieren können. Einstellungen für Teamanrufe und Gruppenanruf Abholung im Auftrag eines Skype for Business Server 2015-Benutzers. Das Tool ermöglicht es Administratoren auch, die für einen bestimmten Benutzer veröffentlichten Anrufweiterleitungseinstellungen abzufragen. Das SEFAUtil-Tool ermöglicht es dem Administrator, die Anrufweiterleitung zu aktivieren/zu deaktivieren/zu ändern oder gleichzeitig im Namen des Benutzers Klingeln zu lassen. Der Administrator kann das Ziel (in Form eines SIP-URIs) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde. Dieses Tool ermöglicht es Administratoren auch, Stellvertretungen oder Teamanrufgruppen Mitglieder im Namen des Benutzers hinzuzufügen oder zu entfernen. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.

SEFAUtil (Aktivierung der sekundären Erweiterungsfunktion) ermöglicht es Skype for Business Server 2015-Administratoren und Helpdesk-Agents, Stellvertretungen, Anrufweiterleitung, gleichzeitiges Klingeln, Einstellungen für den Team Anruf und Abholung des Gruppenanrufs im Auftrag eines Skype zu konfigurieren. für Business Server 2015-Benutzer. Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind.

### <a name="description"></a>Beschreibung

Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool; Es gibt keine unterstützende grafische Benutzeroberfläche. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0. Mit den Features in diesem Tool können Administratoren und Helpdesk-Agents die folgenden Aktionen ausführen:

- Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Stellvertretung, gleichzeitiges Klingeln, Teamanruf- und Gruppenanrufannahme)

- Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellungen (einschließlich Ziel und Timer für „Keine Antwort“)

- Aktivieren/Deaktivieren/Ändern der Konfiguration für sofortige Anrufweiterleitung

- Aktivieren/Deaktivieren/Ändern von Stellvertretungseinstellungen

- Aktivieren/Deaktivieren/Ändern von Teamanrufgruppen-Einstellungen

    > [!NOTE]
    > Neu im Skype for Business Server 2015 SEFAUtil-Tool

- Aktivieren/Deaktivieren/Ändern der Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)

    > [!NOTE]
    > Neu im Skype for Business Server 2015 SEFAUtil-Tool

- Aktivieren/Deaktivieren/Ändern von Einstellungen für Gruppenanrufannahme

    > [!CAUTION]
    > Neu im Skype for Business Server 2015 SEFAUtil-Tool

Für das Tool gelten die folgenden Einschränkungen:

- Nur für Benutzer unterstützt, die in einem Skype for Business-Server Pool verwaltet werden

- Keine Unterstützung für die Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer

### <a name="output"></a>Ausgabe

Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster Ausgaben zur Verfügung. Details hierzu finden Sie weiter unten in diesem Dokument im Abschnitt mit den Beispielen.

### <a name="purpose"></a>Verwendungszweck

Hier sind einige der Hauptszenarien, in denen dieses Tool eingesetzt werden kann:

- Bob ist Executive und wurde in die Skype for Business Server-Telefonie verschoben. In seiner vorhandenen Nebenstellenanlage hat er Stellvertretungen eingerichtet. Im Rahmen des Umzugs in Skype for Business Server 2015 kann der Administrator Bobs Routing so konfigurieren, dass seine bereits vorhandene Delegierungs Konfiguration wiedergegeben wird.

- Alice ist auf Reisen und stellt fest, dass sie einen wichtigen Anruf eines ihrer Kunden erwartet. Sie befindet sich aber gerade im Hotel und hat keinen Computer zur Verfügung. Sie ruft den Helpdesk an und bittet darum, alle Anrufe an ihre Büronummer an ihr Mobiltelefon weiterzuleiten. Die Helpdeskmitarbeiter können diese Konfiguration in ihrem Auftrag vornehmen.

- Joes Anrufe an seine geschäftliche Rufnummer gehen zu seinem mobilen Anrufbeantworter, wenn er bei der Arbeit ist; in den meisten anderen Speicherorten scheint es jedoch richtig zu funktionieren. Der Helpdesk-Techniker ist in der Lage, Joes Routing-Konfiguration anzuzeigen, und erkennt, dass Joe das gleichzeitige Klingeln für sein Mobiltelefon konfiguriert hat. Der Techniker fragt Joe nach der mobilen Berichterstattung in seinem Büro und kann feststellen, dass die gleichzeitige Anruf Regel ist, was bewirkt, dass Anrufe an die Mobile Voicemail von Joe weitergeleitet werden, wenn die Netzwerkabdeckung schlecht ist.

- Mike ist ein neuer Mitarbeiter bei Contoso und er nimmt an einem neuen Team Teil, bei dem alle Mitglieder für Teamanrufe konfiguriert sind, wenn es für Skype for Business Server 2015 aktiviert ist, kann der Administrator seine Teamanrufgruppen Einstellungen so festlegen, dass er alle seine neuen Teammitglieder umfasst. Darüber hinaus fügt der Administrator Mike als Team Anruf-Gruppenmitglied für alle Mitglieder in seinem Team hinzu.

- Eine Praxis des Kundendiensts in der Personalabteilung bei Contoso besteht darin, allen Anrufern vom ersten Anruf an persönlichen Service zu bieten. Da alle Mitglieder der Abteilung sehr nah beieinander sitzen, kann das gleichzeitige Klingeln auf allen Telefonen bei Teamanrufen sehr störend für das Team sein. Um den besten Service bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der Skype for Business Server 2015-Administrator die Funktion für Gruppenanruf-Pickups. Der Administrator fügt alle Abteilungsmitglieder einer Annahmegruppe hinzu und teilt der Abteilung die Annahmegruppennummer mit. Wenn nun Samantha nicht an ihrem Platz ist, bemerkt Joe, dass ihr Telefon klingelt, und kann den Anruf von seinem Platz aus annehmen.

### <a name="requirements"></a>Voraussetzungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Auf diesem Computer muss UCMA 3.0 installiert sein. Um das Tool auszuführen, muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool

1. Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die Skype for Business Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > Auf allen Computern, auf denen das SEFAUtil-Tool ausgeführt werden soll, muss UCMA 3.0 installiert sein.

2. In der Topologie muss eine vertrauenswürdige Anwendung für das SEFAUtil-Tool definiert sein. Wenn Sie SEFAUtil als neue vertrauenswürdige Anwendung definieren möchten, verwenden Sie die Skype for Business Server-Verwaltungsshell, und führen Sie das folgende Cmdlet aus:

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Gegebenenfalls kann ein anderer Port verwendet werden.
    
    > [!NOTE]
    > Pool-FQDN: der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hosten soll (in der Regel ein Skype for Business-Front-End-Server > oder Pool).
    > Pool Registrar FQDN: der FQDN des Skype for Business-Front-End-Servers oder-Pools, der diesem Anwendungspool zugeordnet ist.
    > Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.

3. Die Topologieänderungen müssen aktiviert werden. Das Aktivieren der Topologie-Änderungen kann über die Skype for Business Server-Verwaltungsshell erfolgen, indem Sie das folgende Cmdlet ausführen:

   ```powershell
   Enable-CsToplogy
   ```

4. Falls erforderlich, installieren Sie die Skype for Business Server 2015 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).

5. Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie hierzu das Tool an einer Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. Standardmäßig befindet sich das Tool in: ". ..\Programme\Microsoft Files\Skype for Business Server 2015 \ reskit". Verwenden Sie zum Anzeigen der Anrufweiterleitungseinstellungen eines Benutzers den folgenden Befehl:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.

#### <a name="group-call-pickup"></a>Gruppenanrufannahme

Für die Gruppenanruf Abholung ist in Skype for Business Server 2015 eine zusätzliche Konfiguration erforderlich, damit die Funktion vollständig aktiviert werden kann. Bevor Sie Benutzern Annahmegruppen zuweisen, sollten Sie in der Produktdokumentation der Gruppenanrufannahme die Schritte zur Planung und Bereitstellung dieser Funktion nachlesen.

### <a name="examples"></a>Beispiele

#### <a name="display-current-call-handling-settings"></a>Anzeigen aktueller Anrufbehandlungseinstellungen

Der folgende Befehl zeigt die Anrufbehandlung für den entsprechenden Benutzer an.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> In diesem Beispiel wird der Server-Schalter verwendet, um den Skype for Business-Server anzugeben, **mit dem eine** Verbindung hergestellt werden soll.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Festlegen des Ziels für Anrufweiterleitung/Keine Antwort

In diesem Beispiel wird das Ziel des Anruf Weiterleitungs-/Nein-Anrufs und die Klingelverzögerung festgelegt. Hier wird der Schalter//////-Schalter nicht bereitgestellt. SEFAUtil versucht, die Skype for Business Server 2015-AutoErmittlung zu durchsuchen.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Aktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel aktiviert sofort die Anrufweiterleitung an einen anderen Benutzer.

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Deaktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel deaktiviert sofort die Anrufweiterleitung.

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Hinzufügen eines Benutzers als Stellvertretung und Einrichten von gleichzeitigem Klingeln bei Stellvertretungen

Dieses Beispiel fügt einen Benutzer als Stellvertretung hinzu und richtet das gleichzeitige Klingeln bei Stellvertretungen ein.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Ändern der Regel für gleichzeitiges Klingeln bei Stellvertretungen

Dieses Beispiel ändert die Regel für gleichzeitiges Klingeln bei Stellvertretungen, die im vorherigen Beispiel festgelegt wurde, in die Anrufverzögerungsregel.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Ausgabe**

```console
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

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Hinzufügen einer Stellvertretung und Einrichten der Regel „Anrufweiterleitung an Stellvertretungen“

Dieses Beispiel fügt eine Stellvertretung hinzu und richtet die Regel „Anrufweiterleitung an Stellvertretungen“ ein.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Aktivieren von gleichzeitigem Klingeln und Festlegen einer Zielnummer

Diese Beispiel aktiviert gleichzeitiges Klingeln und legt eine Zielnummer für diese Funktion fest.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Um die Zielnummer für gleichzeitiges Klingeln eines Benutzers zu ändern, für den gleichzeitiges Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Parameter „/enablesimulring“. Andernfalls wird die Zielnummer nicht geändert.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Deaktivieren von gleichzeitigem Klingeln

Dieses Beispiel deaktiviert gleichzeitiges Klingeln.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Teamanrufgruppen-Mitglieder

Dieses Beispiel fügt der Teamanrufgruppe eines Benutzers ein Teammitglied hinzu und aktiviert gleichzeitiges Klingeln für die Teamanrufgruppe.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Durch das Hinzufügen eines Teammitglieds zur Teamanrufgruppe eines Benutzers werden die Einstellungen der Benutzer für gleichzeitiges Klingeln automatisch auf gleichzeitiges Klingeln für die Teamanrufgruppe umgestellt.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Entfernen eines Mitglieds aus der Teamanrufgruppe

Diese Beispiel entfernt ein Teammitglied aus der Teamanrufgruppe eines Benutzers.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Wenn das einzige Mitglied der Teamanrufgruppe entfernt wird, wird automatisch das gleichzeitige Klingeln für die Teamanrufgruppe deaktiviert.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Festlegen der Anrufverzögerung für die Teamanrufgruppe

Dieses Beispiel ändert die Zeiteinstellung der Anrufverzögerung für die Teamanrufgruppe.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Aktivieren des Teamanrufs

Dieses Beispiel aktiviert den Teamanruf für einen angegebenen Benutzer.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Wenn die Teamanrufgruppe des Benutzers keine Mitglieder hat, ist die Teamanruffunktion nicht aktiviert.

 **Ausgabe**

#### <a name="disable-team-call"></a>Deaktivieren des Teamanrufs

Dieses Beispiel deaktiviert den Teamanruf für einen angegebenen Benutzer.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Aktivieren der Gruppenanrufannahme und Zuweisen einer Annahmegruppe zu einem Benutzer

Dieses Beispiel weist einem Benutzer eine Annahmegruppe zu und aktiviert die Gruppenanrufannahme.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Deaktivieren der Gruppenanrufannahme

Dieses Beispiel deaktiviert die Gruppenanrufannahme für einen angegebenen Benutzer.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, bleibt die Gruppennummer, die dem Benutzer zugewiesen war, nicht erhalten. Wenn Sie die Gruppenanrufannahme für diesen Benutzer anschließend wieder aktivieren möchten, müssen Sie die Gruppennummer erneut mithilfe des Parameters „/enablegrouppickup“ zuweisen.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Beschreibung

"SYSPrep. ps1" ist ein Windows PowerShell-Skript, mit dem die folgenden Skype for Business Server 2015-Voraussetzungen auf Ihrem Windows Server 2008-Betriebssystem Computer installiert werden.

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell, Version 3.0

- Visual C++ 2010 Redistributable

- Updates für Internetinformationsdienste

- Windows Identity Foundation

- Skype for Business Server 2015-Core-Dateien

  Zwar ähnelt der Skriptname dem des Systemvorbereitungsprogramms für die Microsoft Windows-Betriebssysteme, doch sind beide unterschiedlich. Mit diesem Skript werden nur die erforderlichen Voraussetzungen für Skype for Business Server 2015 installiert. Sobald diese installiert sind, kann mit dem Windows-Tool für die Systemvorbereitung ein Image des Servers erstellt werden.

### <a name="requirements"></a>Anforderungen

Bevor Sie das SYSPrep. ps1-Skript ausführen, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (beispielsweise **D:\setup)**. Dieser Ordner muss auch eine Kopie der Skype for Business Server 2015-Dateien, insbesondere **Setup. exe** , beinhalten. Die erforderlichen Dateien können Sie an folgenden Orten herunterladen:


| **Erforderliche Komponente**                                | **Standort**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell, Version 3.0  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 Redistributable  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| Updates für Internetinformationsdienste  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup. exe  <br/> | Kopieren von Skype for Business Server 2015-Medien  <br/>                   |

### <a name="parameter"></a>Parameter

Der **-SetupFolder-** Parameter verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.

### <a name="examples"></a>Beispiele

Führen Sie an einer Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl aus, um das Skript "SYSPrep. ps1" auszuführen und die Voraussetzungen für Skype for Business Server 2015 zu installieren:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration
<a name="UNAM"> </a>

Mit dem Migrationstool "nicht zugewiesene Nummern Ankündigungen" kann ein Skype for Business Server 2015-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von einem Skype for Business-Quellserver oder-Pool zu einem Ziel des Skype for Business-Servers oder-Pools.

### <a name="description"></a>Beschreibung

Das Tool Unassigned Number Announcements Migration ist ein Windows PowerShell-Skript, das die Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quellserver oder -pool zu einem anderen Server oder Pool verschiebt.

Bei Ausführung des Unassigned Number Announcements Migration-Skripts werden folgende Vorgänge durchgeführt:

1. Verschieben aller Audiodateien, die von den Ankündigungen für nicht zugewiesene Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Dateispeicher des Zielservers oder -pools

    > [!NOTE]
    > Die Audiodateien werden aus dem Quell Pool entfernt, nachdem Sie in den Ziel Pool kopiert wurden.

2. Verschieben aller Ankündigungen für nicht zugewiesene Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Zielserver oder -pool

3. Erneutes Zuweisen aller nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool verwaltet wird, zum Zielserver oder -pool

Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, nun mit derselben Konfiguration vom Zielserver oder -pool bedient.

### <a name="output"></a>Ausgabe

Das **CsAnnouncementConfiguration-** Skript zeigt im Fenster "Skype for Business Server-Verwaltungsshell" an, wo es den Erfolg oder Misserfolg des Migrationsvorgangs ausgeführt hat.

Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die erfolgreich in das Ziel verschobenen nicht zugewiesenen Nummernbereiche in funktionsfähiger Form am Ziel, während der Rest der noch zu migrierenden nicht zugewiesenen Nummernbereiche in der Quelle verbleibt – ebenfalls in funktionsfähigem Zustand. Um die restliche Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.

### <a name="purpose"></a>Verwendungszweck

Das Unassigned Number Announcements Migration-Skript kann in den drei folgenden Szenarien eingesetzt werden:

- **Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype for Business Server:** Contoso ist dabei, zu Skype for Business Server 2015 zu migrieren, und im Rahmen des Migrationsprozesses möchte der Skype for Business Server-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von der lync Server 2013-Bereitstellung auf die neue Bereitstellung von Skype for Business Server 2015 verschieben. Um die Konfigurationseinstellungen zu verschieben, verwendet der Skype for Business Server-Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen.

- **Rollback einer Bereitstellung von Skype for Business Server 2015 auf lync Server 2013:** Aufgrund unerwarteter Faktoren muss Contoso die Migration auf die neue Skype for Business Server 2015-Bereitstellung zurücksetzen. Um die Unterbrechungen des Diensts zu minimieren, verwendet der Skype for Business Server-Administrator das Migrationstool "nicht zugewiesene Nummern Ankündigungen", um die Konfiguration von der Skype for Business Server 2015-Bereitstellung auf die lync Server 2013-Bereitstellung zurückzusetzen.

- **Verschieben von Daten zwischen Bereitstellungen:** Contoso ersetzt alle Server eines Pools durch neuere Server. Ihre Strategie ist die Bereitstellungeines neuen Skype for Business Server 2015-Pools, das Verschieben aller Daten aus dem alten in den neuen Pool und das anschließende verwerfen des alten Pools. Sobald der neue Pool bereitgestellt ist, wird die Konfiguration mit dem Tool Unassigned Number Announcements Migration aus dem alten Pool in den neuen verschoben.

#### <a name="requirements"></a>Voraussetzungen

Hier sind die Hauptanforderungen für eine erfolgreiche Ausführung des Tools:

1. Das Skript muss von einem Computer ausgeführt werden, auf dem die Skype for Business Server-Verwaltungsshell installiert ist.

2. Die Ankündigungs Anwendung muss erfolgreich in den Skype for Business-Servern oder-Pools für Quell-und Zielserver bereitgestellt werden.

#### <a name="move-csannouncementconfiguration-script"></a>Skript „Move-CsAnnouncementConfiguration“

Das Skript „Move-CsAnnouncementConfiguration“ erfordert die in der Tabelle unten beschriebenen zwei Parameter. 

![Move-CsAnnouncementConfiguration-Parameter.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Beispiele

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem lync Server 2013-Pool zu einem Skype for Business Server 2015-Pool

In diesem Beispiel werden die nicht zugewiesenen Nummern Ankündigungen aus dem Quell Pool (lync Server 2013) in den Ziel Pool (Skype for Business Server 2015) verschoben.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem Skype for Business Server 2015-Pool in einen lync Server 2013-Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (Skype for Business Server 2015) in den Ziel Pool (lync Server 2013) verschoben.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

Das Tool Web conf Data ermöglicht einem Administrator der Skype for Business Server 2015-Kommunikationssoftware, mehr Kontrolle über die Daten zu haben, die mit den Webkonferenzen eines Organisators verbunden sind. Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers auf Grundlage eines Zeitstempel Kriteriums zu löschen.

### <a name="description"></a>Beschreibung

Mit diesem Tool können Administratoren die folgenden Vorgänge durchführen:

1. Suchen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind

2. Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind

3. Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind und deren Alter einen bestimmten Wert überschreitet

4. Verschieben aller Webkonferenzdaten, die einem Benutzern zugeordnet sind, wenn diese Benutzer aus einem Pool in einen anderen verschoben werden

    > [!NOTE]
    > Die Resource Kit-Tools für lync Server 2010 unterstützt das Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool zu einem anderen verschoben wird. Diese Funktionalität ist jetzt aus diesem Tool für den **MoveConferenceData** -Parameter veraltet. Details zu diesem Parameter finden Sie unter dem Cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .

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

![Parameter des Web conf-Datentools.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

Oben sehen Sie ein Beispiel für einen Löschbefehl. Der Löschbefehl entfernt alle inaktiven Besprechungsordner dieses Benutzers.

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenzbesprechungsdaten benötigen.


