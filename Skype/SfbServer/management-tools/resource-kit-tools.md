---
title: Dokumentation zu Skype for Business Server 2015 Resource Kit-Tools
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: 'Dieser Artikel beschreibt die Tools im Skype for Business Server 2015 Resource Kit, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit erleichtert IT-Administratoren, die Skype for Business Server 2015 bereitstellen und verwalten, Routineaufgaben. Beispielsweise kann das Web Conf Data-Tool zum einfachen Steuern von Daten verwendet werden, die von Benutzern während einer Onlinebesprechung hochgeladen werden. Das SEFAUtil-Tool kann verwendet werden, um die Weiterleitung und Beantwortung von Stellvertretungsanrufen für Benutzer einzurichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.'
---

# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Dokumentation zu Skype for Business Server 2015 Resource Kit-Tools

Dieser Artikel beschreibt die Tools im Skype for Business Server 2015 Resource Kit, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit erleichtert IT-Administratoren, die Skype for Business Server 2015 bereitstellen und verwalten, Routineaufgaben. Beispielsweise kann das **Web Conf Data-Tool** zum einfachen Steuern von Daten verwendet werden, die von Benutzern während einer Onlinebesprechung hochgeladen werden. Das **SEFAUtil-Tool** kann verwendet werden, um die Weiterleitung und Beantwortung von Stellvertretungsanrufen für Benutzer einzurichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Laden SieOCSReskit.msiaus dem Download Center herunter, um [ das ](https://www.microsoft.com/download/details.aspx?id=52631) Skype for Business Server 2015 Resource Kit zu installieren.

Führen Sie **OCSResKit.msi** aus, um eine einfache Installation durchzuführen. Das .msi installiert alle Tools im folgenden Pfad: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools, die eigenständige ausführbare Dateien sind, befinden sich in diesem Ordner. Tools, die auch über unterstützende Dateien verfügen, befinden sich in ihren eigenen Unterordnern.

## <a name="supported-environments"></a>Unterstützte Umgebungen

Das Skype for Business Server 2015 Resource Kit sollte auf einem Server installiert werden, der die für Skype for Business Server 2015 erforderlichen Spezifikationen erfüllt, in der Regel eine, die zum Ausführen Skype for Business Server 2015 verwendet wird.

## <a name="resource-kit-tools-overview"></a>Übersicht über Resource Kit-Tools

Es folgt eine Liste der Tools, die im Skype for Business Server 2015 Resource Kit bereitgestellt werden. Eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispielverwendung, wird in den folgenden Abschnitten behandelt.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Bandbreitenrichtlinien-Dienstmonitor](resource-kit-tools.md#bpsm)

- [Bandwidth Utilization Analyzer](resource-kit-tools.md#bua)

- [Call Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importieren Storage Dienstdaten](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Benutzerkonsole nachschlagen](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Netzwerkkonfigurationsanzeige](resource-kit-tools.md#NCV)

- [Response Group Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Unassigned Number Announcements Migration](resource-kit-tools.md#UNAM)

- [Web Conf Data](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Adressbuchdienstkonfiguration in Skype for Business Server 2015 anpassen können. Mit diesem Tool können Skype for Business Server 2015-Administratoren auch die Standardeinstellungen des Adressbuchdiensts wiederherstellen.

### <a name="description"></a>Beschreibung

ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory Domain Services-Attribute konfigurieren können, die sich auf den Adressbuchdienst beziehen.

Die wichtigsten Szenarien für das Tool sind die folgenden:

- So ermöglichen Sie Administratoren das Zuordnen von Attributen in Active Directory Domain Services zu den Attributen für Skype for Business Server 2015.

- So ermöglichen Sie Administratoren das Angeben des Active Directory Domain Services-Attributs, das in die Adressbuchdienstdateien eingeschlossen oder ausgeschlossen werden soll.

- Um Administratoren die Wiederherstellung zu ermöglichen, verwenden Sie die Standardeinstellungen des Adressbuchdiensts.

Das ABSConfig-Tool kann mithilfe der ABSConfig.exe-Datei gestartet werden. The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters. Es verfügt auch über Optionen zum Anpassen des Werts der Telefonnummer, die in die Adressbuchdatei aufgenommen werden soll. Mit der Option **"Standardwerte wiederherstellen"** können Administratoren Adressbuchdiensteinstellungen auf Standardwerte wiederherstellen.

> [!NOTE]
> Die Neuzuordnung von AD-Attributen zu verschiedenen OC-Feldnamen funktioniert nur für den Adressbuchdateidownload und wird von der Adressbuchwebabfrage nicht unterstützt.

### <a name="output"></a>Ausgabe

ABSConfig speichert die Adressbuchdienstkonfiguration in der Datenbank.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Zweck

ABSConfig bietet eine schnelle und einfache Möglichkeit, Skype for Business Server 2015-Adressbuchdienst anzupassen.

### <a name="requirements"></a>Anforderungen

#### <a name="computer"></a>Computer

ABSConfig kann nur von einem in die Domäne eingebundenen Computer ausgeführt werden, auf dem Skype for Business Server 2015 installiert ist. Im Fall von Skype for Business Server 2015, Enterprise Edition, kann dieses Tool auf allen Front-End Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.

#### <a name="network"></a>Netzwerk

Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.

#### <a name="software"></a>Software

Die folgenden Softwarekomponenten müssen vor dem Ausführen des ABSConfig-Tools installiert werden:

- Skype for Business Server 2015

#### <a name="users"></a>Benutzer

Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der Skype for Business Server 2015-Bereitstellung verfügen.

### <a name="examples"></a>Beispiele

ABSConfig kann durch Eingabe **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie die Benutzeroberfläche des ABSConfig-Tools.

![Das tool ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Zusammenfassung

Das ABSConfig-Tool bietet Administratoren ein schnelles und benutzerfreundliches Tool zum Anpassen Skype for Business Server Adressbuchdiensts 2015.

## <a name="bandwidth-policy-service-monitor"></a>Bandbreitenrichtlinien-Dienstmonitor
<a name="bpsm"> </a>

Mit dem Tool Bandwidth Policy Service Monitor können Administratoren eine Liste der folgenden Optionen anzeigen:

1. Alle konfigurierten Skype for Business Server 2015-Bandbreitenrichtliniendienste (Authentifizierung und Kern) in der Topologie

2. Die Verbindungen, die die einzelnen Dienste mit anderen Bandbreitenrichtliniendiensten und den Edgeservern herstellen

3. Alle Verbindungen, die im Netzwerkkonfigurationsdokument konfiguriert sind, sowie die Bandbreitennutzung in Echtzeit, wie sie von den einzelnen Bandbreitenrichtliniendiensten gemeldet werden

### <a name="description"></a>Beschreibung

Das Tool Bandwidth Policy Service Monitor ist als GUI-basierte Anwendung implementiert. Administratoren starten das Tool, indem sie PDPMonUI.exe ausführen.

Beim Starten des Tools wird versucht, die Liste der Bandbreitenrichtliniendienste in der Topologie zu ermitteln. Nach Abschluss der ersten Aktualisierung wird der Bereich links vom Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.

Wenn Administratoren einen bestimmten Bandbreitenrichtliniendienst auswählen, werden im Bereich auf der rechten Seite die Informationen zu diesem bestimmten Dienst angezeigt. Dieser Bereich verfügt außerdem über zwei Hauptregisterkarten, auf denen Informationen angezeigt werden.

#### <a name="machine-info-tab"></a>Registerkarte "Computerinformationen"

Auf der Registerkarte **"Computerinformationen** " werden die Details des ausgewählten Bandbreitenrichtliniendiensts sowie die Liste und der Status aller Verbindungen angezeigt, die vom ausgewählten Bandbreitenrichtliniendienst mit anderen Diensten hergestellt werden.

#### <a name="topology-info-tab"></a>Registerkarte "Topologieinformationen"

Auf der Registerkarte **"Topologieinformationen** " wird eine Liste aller Links angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jede Verbindung wird die Bandbreitenkapazität für Audio und Video angezeigt. Darüber hinaus wird die derzeit genutzte Bandbreite sowohl in KBit/s als auch als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierung, um Links hervorzuheben, deren Auslastung nahe an der Kapazität liegt. Auf diese Weise können Administratoren solche Links schnell isolieren.

> [!NOTE]
>  Wenn beim Tool Bandwidth Policy Service Monitor ein Fehler auftritt, wenn eine Verbindung mit einem der konfigurierten Bandbreitenrichtliniendienste hergestellt wird, werden die Informationen auf den Registerkarten **"Computerinformationen** " und " **Topologieinformationen** " nicht aufgefüllt. Es ist jedoch möglich, dass das Tool zunächst eine Verbindung herstellt, aber anschließend seine Verbindung mit dem Dienst verliert. In solchen Fällen werden Administratoren möglicherweise veraltete Informationen angezeigt. Auf jeder Registerkarte ist ein Zeitstempel für die **letzte Aktualisierung** vorhanden, mit dem Administratoren sehen können, wann die Daten für einen bestimmten Bandbreitenrichtliniendienst zuletzt aktualisiert wurden.

### <a name="output"></a>Ausgabe

Es gibt keine Befehlszeilenausgabe; Die Programmausgabe ist in der hauptgrafikbasierten Benutzeroberfläche (GUI) enthalten.

### <a name="purpose"></a>Zweck

Der Zweck des Tools Bandwidth Policy Service Monitor besteht darin, Administratoren Einblicke in den Status der einzelnen Bandbreitenrichtliniendienste zu ermöglichen, die in der Topologie definiert sind. Darüber hinaus können Administratoren die Echtzeitbandbreitenauslastung für alle Verbindungen sehen, die im Netzwerkkonfigurationsdokument definiert sind.

### <a name="requirements"></a>Anforderungen

Das Tool Bandwidth Policy Service Monitor muss auf einem Computer ausgeführt werden, der Teil der Skype for Business Server Topologie ist.

### <a name="summary"></a>Zusammenfassung

Das Tool Bandwidth Policy Service Monitor kann für Administratoren eine wertvolle Ressource sein, damit sie den Status aller Bandbreitenrichtliniendienste in der Topologie überprüfen können – und noch wichtiger – sie können eine Echtzeitbandbreitenauslastung für die Verbindungen erhalten, die in den Netzwerkkonfigurationseinstellungen definiert sind.

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer
<a name="bua"> </a>

Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Diese Berichte können verwendet werden, um das aktuelle Bandbreitennutzungsmuster zu verstehen und die Bandbreitenkapazitätsplanung zu unterstützen.

### <a name="description"></a>Beschreibung

Bandwidth Utilization Analyzer wird als GUI-basierte Anwendung implementiert. Dieses Tool generiert Berichte speziell für die Audionutzung im Netzwerk und hilft bei der Kapazitätsplanung. Außerdem wird die Bandbreitenkapazität durchlaufen, die verschiedenen Verbindungen zugewiesen ist.

### <a name="output"></a>Ausgabe

Bandwidth Utilization Analyzer bietet grafische Darstellungen der Bandbreitenkapazität und -auslastung für Audio für alle WAN-Verbindungen, die im System konfiguriert sind.

### <a name="purpose"></a>Zweck

Bei jeder VoIP- und Videobereitstellung ist es wichtig, den Trend der Bandbreitenauslastung des Mediendatenverkehrs im gesamten Unternehmensnetzwerk zu überwachen und zu verstehen. Das Tool Bandwidth Utilization Analyzer ermöglicht es einem Administrator, genau dies zu erreichen. Dieses Tool führt Folgendes aus:

- Generiert spezifische Berichte für die Audionutzung über das Netzwerk

- Hilft bei einer effektiveren Kapazitätsplanung und Iteration für die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist

Bandwidth Utilization Analyzer kann grafische Darstellungen von Bandbreitenkapazitäts- und Auslastungsberichten generieren. Sie sind wie folgt:

- Alle WAN-Verbindungen im Unternehmensnetzwerk

- Gefiltert nach ausgewählten WAN-Verbindungen

- Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben

- Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite nicht genutzt haben

- Filtern nach WAN-Verbindungen, die kritische Ebenen erreicht haben (eine Bandbreitenauslastung, die größer als 90 % der Bandbreitenkapazität der WAN-Verbindung ist)

- Gefiltert nach WAN-Verbindungstyp: Netzwerkstandortverbindungen, regionenübergreifende Verbindungen und Verbindungen innerhalb eines Standorts

- Gefiltert nach Netzwerkregion

#### <a name="applications"></a>Anwendungen

Bandwidth Utilization Analyzer verfügt über die folgenden beiden Anwendungen (Tools):

- **WanLinkLogCollector.exe** Mit diesem Tool kann der Benutzer die erforderlichen Informationen eingeben.

- **BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel Spreadsheet Software Report wird automatisch von WanLinkLogCollector.exe gestartet. Mit dieser Anwendung kann der Benutzer Filter auf den Bericht anwenden, wie weiter unten in diesem Artikel gezeigt.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phasen der Verwendung von Bandwidth Utilization Analyzer

Es gibt zwei Phasen bei der Verwendung von Bandwidth Utilization Analyzer:

- Erfassen von Protokollen, die mithilfe von WanLinkLogCollector.exe

- Anpassen von Berichten, die mithilfe von BandwidthUtilizationAnalyzer.xlsm ausgeführt werden

    > [!IMPORTANT]
    > Es wird dringend empfohlen, bandwidthUtilizationAnalyzer.xlsm nicht manuell von Endbenutzern zu starten.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Starten von Bandwidth Utilization Analyzer

Starten Sie WanLinkLogCollector.exe an der Eingabeaufforderung oder mit Windows Explorer.

 **Verwenden von WanLinkLogCollector.exe**

Es gibt drei Schritte zur Verwendung von WanLinkLogCollector.exe:

1. **Protokollieren der Zeitachse** Bereitstellen der Zeitachse, für die der Bericht generiert werden muss

2. **Angeben der Dateiverzeichnisse** Bereitstellen von Dateispeicherortinformationen

3. **Erfassen der Protokolle und Starten der Berichtsanzeige** Ausführen des Befehls zum Generieren des Berichts

#### <a name="step-1---log-the-timeline"></a>Schritt 1: Protokollieren der Zeitachse

Die Protokollierung der Zeitachse ermöglicht es dem Toolbenutzer, Folgendes anzugeben, wie in der folgenden Abbildung dargestellt.

1. **Startdatum** Dies ist das Startdatum der Zeitachse, für die der Bericht generiert werden soll. Beispiel: 1. August 2010.

2. **Enddatum** Dies ist das Enddatum der Zeitachse, für die der Bericht generiert werden soll. Beispiel: 30. September 2010.

     ![Start- und Enddaten in Bandbreitenauslastung A.](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Schritt 2: Angeben der Dateiverzeichnisse

Die folgenden Dateiverzeichnisse können vom Benutzer wie dargestellt angegeben angegeben werden.

- **Speicherort der Serverprotokolldateien** Der Ordnerspeicherort, an dem Bandbreitenrichtlinienserverprotokolle gespeichert sind. Dies ist in der Regel in \<fileserver\>\\<Wahl von FE\>\AppServerFiles\PDP.

- **Temporärer Speicherort für Dateien** Der temporäre Dateispeicherort, an dem Zwischendateien gespeichert werden, während der Bericht generiert wird.

    ![Dateiverzeichnisse im Bandbreitenauslastungs-Anal.](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > Stellen Sie sicher, dass dem Toolbenutzer ausreichend dateizugriff auf die Serverprotokolle und den temporären Dateispeicherordner bereitgestellt wird.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Schritt 3: Erfassen der Protokolle und Starten der Berichtanzeige

Klicken Sie auf " **Ausführen** ", wie unten dargestellt, um die Protokolle zu erfassen und die Berichtanzeige zu starten. In diesem Schritt werden die erforderlichen Daten gesammelt.

![Sammeln von Daten in der Bandbreitenauslastung Analy.](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Wenn die Eingabeüberprüfung erfolgreich ist, wird die unten gezeigte Meldung angezeigt.

![Protokolle, die in der Bandbreiten-Utili gesammelt werden.](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Klicken Sie auf **OK**. BandwidthUtilizationAnalyzer.xlsm wird automatisch gestartet. Folgen Sie den Anweisungen im Meldungsfeld. Ausführliche Informationen finden Sie unter **"Verwenden von BandwidthUtilizationAnalyzer.xlsm** " im nächsten Abschnitt.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Verwenden von BandwidthUtilizationAnalyzer.xlsm

1. Wenn BandwidthUtilizationAnalyzer.xlsm automatisch gestartet wird, klicken Sie auf **"Aktualisieren** ", wie unten dargestellt.

     ![BandwidthUtilizationAnalyzer.xlsm.](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Wenn ein Dateiordner geöffnet wird, wählen Sie consolidated.csv aus dem Speicherort aus, der im Meldungsfeld angegeben ist, wie unten dargestellt. Außerdem wird der Ort als **C:\Temp angezeigt**.

     ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Klicken Sie auf **Importieren**.

4. Die grafische Darstellung wird automatisch generiert. Er ist verfügbar, wenn der Working-in-the-Background-Zeiger ausgeblendet wird.

     ![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Anwenden von Filtern auf die Berichtsansicht

Die Filter, die wie unten dargestellt auf die Berichtsansicht angewendet werden können, werden wie folgt beschrieben:

![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Namen** Filtern nach WAN-Verbindungen (der Filter befindet sich auf der rechten Seite des Diagramms). Das Präfix gibt die folgenden Linktypen an: siehe vertikales Feld (blau):

   - **S-Website** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion

   - **IS Site-inter-site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten

   - **R Regionenübergreifende** Die WAN-Verbindung zwischen zwei Netzwerkregionen

2. **Grenzwert überschritten** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung größer als die Bandbreitenkapazität ist

3. **Kritische Ebenen** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung 90 % oder mehr als die Bandbreitenkapazität erreicht hat

4. **Nicht ausgelastet** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25 % der Bandbreitenkapazität beträgt

5. **Linktyp** Filtern Nach den folgenden WAN-Verbindungstypen:

   - **Netzwerkstandorttyp**

   - **Websiteübergreifender** Typ

   - **Regionsübergreifender Verknüpfungstyp**

6. **Region** Filtern nach Netzwerkregion

Die folgenden Abbildungen zeigen die zuvor beschriebenen Filter.

Filtern nach **Name**. Wählen Sie die Liste der Links aus, die im Diagramm angezeigt werden müssen.

![Filtern nach Name in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtern nach **dem Grenzwert "Überschritten"**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach überschrittener Grenze.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtern nach **kritischen Ebenen**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach kritischen Ebenen.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtern nach **"Unter" verwendet**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach "Unter genutzt".](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtern nach **Linktyp**. Wählen Sie die Typen aus, die angezeigt werden müssen.

![Filtern nach Linktyp.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Links angezeigt werden müssen.

![Filtern nach Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Anforderungen

- Die .NET Framework 3.5

- Microsoft Excel 2010 oder Excel 2007

### <a name="summary"></a>Zusammenfassung

Bandwidth Utilization Analyzer wird verwendet, um die Audiobandbreitenauslastung für UC-Datenverkehr über das Netzwerk zu zeichnen. Dieses Tool kann auch verwendet werden, um die Auslastung der Videobandbreite im Netzwerk zu melden.

## <a name="call-parkometer"></a>Call Parkometer
<a name="callpark"> </a>

Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Orbitdatenbank für das Parken von Anrufen bietet.

### <a name="description"></a>Beschreibung

Call Parkometer ist ein Tool zum Nachverfolgen von derzeit geparkten Anrufen. Außerdem werden Statistiken über Orbits und die Verwendung von Anrufparkservern (Call Park Server, CPS) erfasst. Dieses Befehlszeilentool bietet sowohl Lese- als auch Schreibzugriff auf die CPS-Orbit-SQL Server-Datenbank von einem lokalen oder remote verbundenen Computer aus.

Alle Optionen schließen sich gegenseitig aus. Die Befehlszeilensyntax lautet wie folgt:

- **-o-Parameter** : Listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.

- **-n-Parameter** : Listet alle derzeit verwendeten Orbits in diesem Pool auf. Die angezeigten Informationen sind wie folgt:

  - SIP Uniform Resource Identifier (URI) des Parkempfängers und Parkers.

  - Hostname des CPS, in dem der Anruf geparkt wird.

  - Zeitstempel, wann der Anruf geparkt wurde.

- **-f-Parameter** : Listet die Anzahl der derzeit freien Orbits im Pool auf.

- **-r \<n\>** - listet die \<n\> letzten geparkten Aufrufe auf. Die angezeigten Informationen sind wie folgt:

  - SIP-URI des Parkempfängers.

  - SIP-URI des Parkers.

  - Hostname des CPS, auf dem der Anruf geparkt wurde.

  - Zeitstempel, wann der Anruf abgerufen oder verworfen wurde.

- **-t\<n\>** - testet die Reservierung eines Orbits in der Datenbank, um die Zufälligkeit der zugewiesenen Orbitnummern anzuzeigen.

### <a name="output"></a>Ausgabe

Abhängig von den Eingabeparametern, die an einer Eingabeaufforderung angegeben werden, zeigt call parkometer die folgende Ausgabe an:

- Alle Orbitbereiche, die für diesen Pool konfiguriert sind

- Derzeit geparkte Anrufe

- Anzahl der freien (verfügbaren) Orbits

- Zuletzt geparkte Anrufe

- Reservierte Orbits zum Testen uniformer und zufälliger Orbitwerte

### <a name="purpose"></a>Zweck

Der Zweck des CPS-Tools besteht darin, den Befehlszeilenzugriff auf die CPS-Datenbank bereitzustellen. Der Administrator kann die CPS-Verwendung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.

### <a name="requirements"></a>Anforderungen

Es gibt keine Anforderungen, wenn dieses Tool auf demselben Computer ausgeführt wird, auf dem CPS ausgeführt wird. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von Skype for Business Server 2015 verwendete SQL Server-Datenbank so konfiguriert werden, dass der Remotezugriff zulässig ist. Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server. Diese SQL Server Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer.exe.config** definiert. Sie muss sich in demselben Verzeichnis befinden, in dem sich parkometer.exe befindet. Die folgende XML-Datei ist ein Beispiel für eine parkometer.exe.config. Die Parameter, die konfiguriert werden müssen, sind Benutzername (z. B. "mydomain\Administrator"), Kennwort (z. B. "mypassword") und Hostname (z. B. "myserver").

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

Bereitgestellte Orbitbereiche: Der Parameter "-o" listet alle Orbitbereiche auf, die wie dargestellt für diesen Pool konfiguriert sind.

![Orbitbereiche im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Derzeit geparkte Anrufe: Der Parameter "-n" listet alle derzeit verwendeten Orbits für diesen Pool auf, wie dargestellt.

![Derzeit geparkte Anrufe im Anrufparkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Anzahl der freien Orbits: Der Parameter "-f" listet die Anzahl der derzeit freien Orbits im Pool auf, wie dargestellt.

![Freie Orbits im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Zuletzt geparkte Anrufe: Der Parameter "-r \<n\> " listet die \<n\> letzten geparkten Anrufe wie dargestellt auf.

![Kürzlich geparkte Anrufe im Anrufparkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown

![Testen sie Orbitreservierungen im Anrufparkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Zusammenfassung

Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Beschreibung

DBAnalyze ist ein Befehlszeilentool, das Administratoren hilft, Analyseberichte über die Skype for Business Server 2015-Datenbanken zu sammeln. DBAnalyze verfügt über die folgenden Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:

- **Diagnosemodus** Erstellt einen Bericht mit Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten- und Protokolldateigrößen, der letzten Sicherungszeit, der Kontaktverteilung zwischen Servern, die Microsoft Office Communications Server ausgeführt werden, der durchschnittlichen Anzahl von Berechtigungen, Kontakten, Containern, Abonnements, Publikationen, Endpunkten pro Benutzer, nicht ordnungsgemäß verwalteten Benutzern, Benutzern, die nicht weitergeleitet werden können,  Die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, geplanten Konferenzen, aktiven Konferenzen und der Datenbankversion.

    > [!NOTE]
    > Das Ausführen des Diagnosemodus kann sich auf die Serverleistung auswirken.

- **Benutzerdatenmodus** Meldet Kontakt-, Container-, Abonnement-, Veröffentlichungs-, Berechtigungs- und Kontaktgruppendaten für einen angegebenen Benutzer oder für Benutzer, die diesen Benutzer in ihren Kontakt- und Berechtigungslisten haben. Dieser Modus meldet auch Zusammenfassungsdaten für Konferenzen, die ein Benutzer organisiert oder zu denen er eingeladen wird.

- **Konferenzmodus** Berichtet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Zeitplan-Zeit-Details für die Konferenz, der Liste der eingeladenen Teilnehmer, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCUs (Multipoint-Steuerungseinheiten), der Liste der aktiven Teilnehmer und des Signalisierungsstatus jedes Teilnehmers.

- **Decodieren der Besprechungs-ID** Decodiert eine PSTN-Besprechungs-ID (Public Switched Telephone Network), die durch den **Schalter "/pstnid** " angegeben wird, aber keine Verbindung mit dem Back-End herstellt, um detaillierte Informationen zu erhalten.

- **Konferenz auflösen** Decodiert eine PSTN-Besprechungs-ID, die durch den Schalter **/pstnid** angegeben ist, und zeigt Informationen über die Konferenz an, die durch die ID angegeben wird.

- **MCUs-Modus** Meldet die ID, den Medientyp, die URL, den Taktstatus, die Konferenzlast und die Teilnehmerauslastung für jede MCU im Pool.

- **Datenträgerfragmentierungsmodus** Zeigt den Fragmentierungsstatus aller Datenträger an.

Dieses Tool kann verwendet werden, um verschiedene Probleme zu diagnostizieren oder Administratoren bei der Kapazitätsplanung zu unterstützen. Wenn beispielsweise die meisten Benutzer, die auf Server A verwaltet werden, benutzer, die auf Server B verwaltet werden, als Kontakte auswählen, kann der Administrator die Benutzer auf Server A auf Server B verschieben, um den serverübergreifenden Datenverkehr zu reduzieren.

### <a name="output"></a>Ausgabe

Dieses Tool gibt vordefinierte Berichte über die Skype for Business Server 2015-Datenbank aus. **Pfad**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Zweck

Um Dbanalyze.exe zu installieren, kopieren Sie ihn in einen lokalen Ordner, und führen Sie das Tool aus. Führen Sie den folgenden Befehl über die Befehlszeile aus, um das Tool zu verwenden. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Die Beschreibungen für die Befehlszeilenoptionen sind unten dargestellt.

![Befehlszeilenoptionen für Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Anforderungen

 **Computer** DBAnalyze kann nur von einem computer ausgeführt werden, der einer Domäne angehört, auf dem Skype for Business Server 2015 installiert ist.

 **Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.

 **Software** Skype for Business Server 2015-Softwarekomponenten müssen installiert werden, bevor DBAnalyze ausgeführt wird.

 **Benutzer** In der folgenden Tabelle sind die Administratoren aufgeführt, die über die erforderlichen Berechtigungen für den Zugriff auf Skype for Business Server 2015-Datenbanken verfügen.

![Berechtigungstabelle für Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Für den **/report:disk-Modus** ist ein lokales Administratorkonto erforderlich.

### <a name="examples"></a>Beispiele

Es folgen Beispiele für gültige Dbanalyze.exe Befehle:

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Zusammenfassung

DBAnalyzer bietet Administratoren eine schnelle und einfache Analyse Skype for Business Server 2015-Datenbanken.

## <a name="import-storage-service-data"></a>Importieren Storage Dienstdaten
<a name="Issd"> </a>

Das Resource Kit-Tool "ImportStorageServiceData" ermöglicht das erneute Importieren von Warteschlangen- und Endpunktdaten, die aus dem Storage-Dienst (LYSS) zurück in den Storage-Dienst geleert wurden.

### <a name="description"></a>Beschreibung

Die aus dem Storage Dienst geleerten Daten könnten automatisch (regelmäßig) basierend auf dem Status des Warteschlangenelements oder der Datenbankgröße sein. Dies könnte aufgrund des manuellen Aufrufs des Poolfailover-Cmdlets oder des Cmdlets StorageServiceFullFlush (das vom Poolfailover-Cmdlet aufgerufen wird) geschehen sein. Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn eine der Datenbankgrößen des Storage Diensts (LYSS) auf den Front-Ends über der normalen Ebene liegt, da dies wahrscheinlich nur dazu führt, dass mehr Daten zurück exportiert werden. Darüber hinaus sollten alle Probleme, die zu Fehlern beigetragen haben könnten, die zu einer Vergrößerung der Storage Dienstwarteschlange geführt haben, zuerst behoben werden (z. B. Exchange Endpunktfehler, Netzwerkprobleme oder andere Probleme).

 **Szenario 1:** Während des Poolfailovers werden Dateien möglicherweise aus dem Speicherdienst für jedes Front-End geleert. Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.

 **Szenario 2:** Daten werden täglich automatisch geleert oder als Reaktion auf Storage Dienstdatenbank, die bestimmte Größenschwellenwerte überschreitet (z. B. 60 %, 80 %, 90 % voll). Diese automatisch geleerten Daten sollten vom Administrator routinemäßig neu importiert werden. Wenn das Überwachungs-SCOM-Paket nicht bereitgestellt wird, gibt es in der obigen Situation Ereignisse für Skype for Business Server Storage Dienst, die sich auf Daten beziehen, die vom Storage Dienst geleert werden. Ereignis-IDs von 32075 (vollständiger Leerungsvorgang wird gestartet), 32076 (vollständige Leerung wurde abgeschlossen), 32082 (Leerung der Wartungsstufe gestartet), 32083 (Leerung der Wartungsstufe abgeschlossen), 32089 (Leerung aufgrund des Auffüllens der Datenbank aufgetreten). Beachten Sie, dass diese Ereignis-IDs der RTM-Version entsprechen. Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien geleert wurden. Diese Daten sollten mit diesem Tool routinemäßig zurück importiert werden, z. B. einmal pro Woche.

Wenn das SCOM-Paket für die Integritätsüberwachung für Skype for Business Server bereitgestellt wird, gibt es für die Onlinedienstversion neue Warnungen, die den Administrator auffordern, die geleerten Daten wieder in Storage Dienst zu importieren. Es gibt ein entsprechendes Ereignis im Ereignisprotokoll auf dem Front-End Server, der die Warnung ausgelöst hat. Das Ereignis gibt eine Beschreibung des übergeordneten Pfads an, unter dem sich die geleerten Datendateien befinden, und wie viele Dateien vorhanden sind, die die Warnungskriterien erfüllen. Das Warnungskriterium besteht darin, dass unter dem jeweiligen übergeordneten Pfad X oder mehr Dateien vorhanden sind, die mindestens Y Tage alt sind (wobei X und Y innerhalb von StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei außer Kraft gesetzt werden können).) Unten sind zwei Beispiele für Ereignisse aufgeführt, die die Integritätswarnung auslösen können, wobei der Unterschied der übergeordnete Pfad ist. Eine Möglichkeit besteht in der Webdienstdateifreigabe, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-Ends ist. (z. B. c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService). Der Administrator führt dann dieses Reskit-Tool aus.

Dieses Tool erhöht die CPU- und E/A-Last auf dem Front-End, auf dem es ausgeführt wird, und auf anderen Front-Ends, in der Situation, dass die Daten nicht im Besitz des Front-Ends sind, auf dem das Tool ausgeführt wird. Es wird empfohlen, dieses Tool auszuführen, wenn Front-Ends nicht unter hoher CPU- und E/A-Last liegen, z. B. außerhalb der Spitzenzeiten. Zweitens kann dieses Tool 2 bis 3 Minuten dauern, um eine Datendatei zu importieren. Beachten Sie dies bei der Schätzung, wie lange das Tool ausgeführt wird. Die ausführliche Protokolldatei, die vom Tool generiert wird, wird standardmäßig im Datei-Store angezeigt. Löschen Sie sie, wenn keine Fehler gemeldet werden, da die Protokolldatei zehn MB oder mehr sein kann.

![Beispielereignisse für Storage Serverereignisprotokoll.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Anforderungen

Installieren Sie die Skype for Business Server 2015 Resource Kit-Tools. Das Tool wird auf Computern ausgeführt, die in die Domäne eingebunden sind, auf denen Skype for Business Server und Skype for Business Server Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End Server im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal-Datenbank** installiert ist. Diese Datenbank wird vom Tool verwendet, um den Speicherort der WEBSERVICE-Dateifreigabe für den Pool abzurufen. Darüber hinaus muss jeder Front-End Server vor der Verwendung des Tools zuerst Windows PowerShell Remoting mit **enable-PSRemoting** auf jedem Front-End Server und dem Computer aktivieren, von dem das Tool ausgeführt wird. Andernfalls schlagen remote Windows PowerShell Befehle dieses Tools fehl. Windows PowerShell Remoting kann nach Abschluss des Vorgangs auf allen Front-End Servern im Pool deaktiviert werden. Schließlich muss das Konto oder die Anmeldeinformationen, mit denen das Tool aufgerufen wird, über Lese-/Schreibberechtigungen für die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird. Andernfalls schlägt das Tool mit E/A-Berechtigungsfehlern fehl.

> [!NOTE]
> Auf Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht unter dem Betriebssystem Windows Server 2008.

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

Das LCSSync-Tool hilft bei der Bereitstellung Skype for Business Server 2015-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen. Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzergesamtstrukturen als Active Directory Domain Services-Kontaktobjekt mit einer zentralen Gesamtstruktur zu synchronisieren, in der Skype for Business Server 2015 installiert ist.

### <a name="description"></a>Beschreibung

 LCSSync verwendet die synchronisierten Active Directory Domain Services-Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzern Skype for Business Server zu ermöglichen. Um einmalige Anmeldung bereitzustellen, muss das primäre Benutzerkonto dem Active Directory Domain Services-Kontaktobjekt in der zentralen Gesamtstruktur für Skype for Business Server 2015 zugeordnet werden. Dieses Tool hilft bei der Durchführung dieser Zuordnung. Dieses Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents im Microsoft Identity Integration Server bereit.

### <a name="summary"></a>Zusammenfassung

Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015 in einer Umgebung mit mehreren Gesamtstrukturen.

## <a name="lookup-user-console"></a>Benutzerkonsole nachschlagen
<a name="LUC"> </a>

Das Tool LookupUserConsole zeigt interne Skype for Business Server Routinginformationen zu bestimmten Benutzern an. Diese Informationen können für Microsoft hilfreich sein, um persönliche Informationen bei der Diagnose von Bereitstellungs- und Routingproblemen zu unterstützen.

### <a name="description"></a>Beschreibung

 Beim Ausführen von LookupUserConsole.exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert und versucht, interne Skype for Business Server Routinginformationen zu diesen anzuzeigen. Geben Sie **"exit" ein** , um das LookupUserConsole-Tool zu beenden.

### <a name="requirements"></a>Anforderungen

Installieren Sie das Skype for Business Server 2015 Resource Kit. Das Tool wird auf Computern ausgeführt, die in die Domäne eingebunden sind, auf denen Skype for Business Server installiert ist.

### <a name="examples"></a>Beispiele

C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe

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

Mit dem MSTurnPing-Tool kann ein Administrator von Skype for Business Server 2015-Kommunikationssoftware den Status der Server überprüfen, auf denen die Audio-/Video-Edge-, Audio-/Videoauthentifizierungsdienste und die Server ausgeführt werden, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

### <a name="description"></a>Beschreibung

Mit dem MSTurnPing-Tool kann ein Administrator von Skype for Business Server 2015-Kommunikationssoftware den Status der Server überprüfen, auf denen die Audio-/Video-Edge-, Audio-/Videoauthentifizierungsdienste und die Server ausgeführt werden, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

Mit dem Tool kann der Administrator die folgenden Tests ausführen:

1. A/V-Edgeservertest: Das Tool führt Tests für alle A/V-Edgeserver in der Topologie durch:

   - Überprüfen, ob der Skype for Business Server Audio-/Video-Authentifizierungsdienst gestartet wurde und geeignete Anmeldeinformationen ausgeben kann.

   - Überprüfen, ob der Skype for Business Server Audio-/Video-Edgedienst gestartet wurde und die Ressourcen auf dem externen Edge erfolgreich zuordnen kann.

2. Bandbreitenrichtliniendienst-Test: Das Tool führt Tests für alle Server aus, auf denen die Bandbreitenrichtliniendienste in der Topologie ausgeführt werden, indem folgende Schritte ausgeführt werden:

   - Überprüfen, ob der Skype for Business Server Bandbreitenrichtliniendienst (Authentifizierung) gestartet wurde und geeignete Anmeldeinformationen ausgeben kann.

   - Überprüfen, ob der Skype for Business Server Bandwidth Policy Service (Core) gestartet wurde und die Bandbreitenüberprüfung erfolgreich durchführen kann.

Dieses Tool muss von einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist.

### <a name="output"></a>Ausgabe

Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.

- Wenn der **AudioVideoEdgeServer-Test** ausgeführt wird, gibt das Tool Folgendes aus:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Audio/Video Edge-Dienst in der Topologie bereitstellen

- Wenn der **BandwidthPolicyServer-Test** durchgeführt wird, gibt das Tool folgende Ausgaben aus:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Bandwidth Policy Service (Core) in der Topologie bereitstellen

### <a name="requirements"></a>Anforderungen

- Dieses Tool muss von einem Computer ausgeführt werden, der sich in der Topologie befindet und über den lokalen Speicher verfügt.

- Das Tool muss als Administrator ausgeführt werden, der Zugriff auf den lokalen Speicher hat.

### <a name="examples"></a>Beispiele

Nachfolgend sehen Sie ein Beispiel für die Tooleingabe.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio-/Video- und Bandbreitenrichtliniendienste ausgeführt werden.

## <a name="network-configuration-viewer"></a>Netzwerkkonfigurationsanzeige
<a name="NCV"> </a>

Der Netzwerkkonfigurations-Viewer kann von Skype for Business Server 2015-Kommunikationssoftwareadministratoren verwendet werden, um die Anrufsteuerungs-Netzwerktopologie für ein Unternehmen anzuzeigen, die bereitgestellt wird, um Echtzeitkommunikationssitzungen wie Sprach- oder Videoanrufe basierend auf der angegebenen Bandbreitenkapazität zu ermöglichen. Skype for Business Server 2015 definieren Administratoren Anrufsteuerungsrichtlinien, die von den Bandbreitenrichtliniendiensten erzwungen werden, die mit Skype for Business Server 2015 installiert sind.

### <a name="description"></a>Beschreibung

Der Netzwerkkonfigurations-Viewer (NetworkConfigurationViewer.exe) ermöglicht Administratoren das Ausführen der folgenden Aufgaben:

- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem Grafikformat.

- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat.

- Speichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger.

- Speichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format.

- Anzeigen der Konfigurationsdaten der Cac-Netzwerktopologie.

- Anzeigen der Cac-Netzwerktopologie in einer Strukturansichtsart.

- Definieren sie benutzerdefinierte Connectors für CAC-Netzwerktopologieverbindungen (z. B. Standort-zu-Region-, Regions-zu-Region- und Standort-zu-Standort-Verbindungen).

- Anzeigen von Cac-Netzwerktopologie-Standortinformationen, Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen.

### <a name="purpose"></a>Zweck

Anzeigen von Unternehmens-CAC-Netzwerktopologieverbindungen auf einer grafischen Oberfläche.

### <a name="examples"></a>Beispiele

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafikgrafischen Format**: Skype for Business Server 2015-Administratoren können die Cac-Netzwerktopologiekonfiguration auf jedem Skype for Business Server 2015-Computer mithilfe der **Laden Sie die Netzwerkkonfigurationsoption** herunter, wie in der folgenden Abbildung dargestellt. Das Tool kann eine solche Konfiguration nicht herunterladen oder anzeigen, wenn sie auf einem Computer bereitgestellt wird, der keine Verbindung mit dem Skype for Business Server 2015-Konfigurationsspeicher hat.

![Herunterladen der Netzwerkkonfiguration.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien-Serverprotokolldatei in einem grafikgrafischen Format:** Skype for Business Server 2015-Bandbreitenrichtlinienserver speichert die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Speicherort der Skype for Business Server 2015-Dateifreigabe. Skype for Business Server 2015 können Administratoren eine solche Datei in einem Grafikformat anzeigen, indem sie die Option **"Netzwerkkonfiguration öffnen**" wie unten dargestellt verwenden.

![Öffnen einer Protokolldatei des Bandbreitenrichtlinienservers.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Speichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger: Skype for Business Server 2015-Administratoren können die Konfigurationsdatei für die CAC-Netzwerktopologie in einem XML-Format speichern, indem sie die Option **"Kopie der Netzwerkkonfiguration** speichern" wie unten dargestellt verwenden. Die gespeicherte Konfigurationsdatei kann dann offline für grafische Anzeigezwecke verwendet werden.

![Speichern der Netzwerkkonfiguration als XML-Datei.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Speichern und Store CAC-Netzwerktopologiediagramm im JPG- oder BMP-Format: Skype for Business Server 2015-Administratoren können die Konfiguration der Cac-Netzwerktopologie in einem Grafikformat (JPG- und BMP-Dateiformat) speichern, indem sie das **Diagramm "Netzwerkkonfiguration speichern" als Bildoption** wie unten dargestellt verwenden.

![Speichern der Netzwerkkonfiguration als Bild.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Anzeigen von Konfigurationsdaten für die Cac-Netzwerktopologie:</strong> Skype for Business Server 2015 können Administratoren verwandte Netzwerkkonfigurationsdaten wie Netzwerkregionen, Netzwerkstandorte, Bandbreitenprofile und Standortsubnetz-IP-Adressen in einem Textformat anzeigen, indem sie die Option "Netzwerkkonfigurationsdaten anzeigen" wie unten dargestellt verwenden.

![Anzeigen von Netzwerkkonfigurationsdaten.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Anzeigen der Cac-Netzwerktopologie in einer Strukturansicht:** Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Strukturansichtsstil anzeigen, indem sie die Systemsteuerung auf der linken Seite des Toolfensters verwenden, wie unten dargestellt.

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definieren sie benutzerdefinierte Connectors für CAC-Netzwerktopologieverbindungen (z. B. Standort-zu-Region-, Regions-zu-Region- und Standort-zu-Standort-Verbindungen):** Skype for Business Server 2015-Administratoren können benutzerdefinierte grafische Connectors für WAN-Verbindungen der CAC-Netzwerkkonfiguration definieren, indem sie die option Einstellungen wie unten dargestellt verwenden. Dadurch wird zwischen verschiedenen Typen von Netzwerkverbindungen unterschieden, die in der Netzwerkkonfiguration bereitgestellt werden.

![Werkzeuge.](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Anzeigen von Standortinformationen, Regionsinformationen und bereitgestellten Bandbreitenrichtlinien für die Anrufsteuerungsnetzwerktopologie:** Skype for Business Server 2015 können Administratoren mithilfe der unten gezeigten Optionen verwandte Cac-Netzwerkregioneninformationen, Standortinformationen und Informationen zur Bereitstellung von Cac-Bandbreite anzeigen. (Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **"Info** ".)

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die die CAC-Netzwerktopologie für ihre Bereitstellung in einem Grafikformat anzeigen möchten.

## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

Die Reaktionsgruppenanwendung bietet Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zuzugreifen. Leider ist außerhalb der Anwendung keine grafische Ansicht dieser Daten verfügbar. Das Tool Response Group Agent Live Resource Kit löst dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die durch Echtzeit-Skype for Business Kommunikationssoftwareinformationen wie das Vorhandensein anderer Agents erweitert wird.

### <a name="description"></a>Beschreibung

Response Group Agent Live ist eine Windows-Anwendung, die Anmelde- und Abmeldefunktionen sowie einige Echtzeitinformationen (z. B. Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bereitstellt. Es soll eine erweiterte Version der Seite "Agentgruppen" sein (auf die über Skype for Business zugegriffen werden kann.

### <a name="purpose"></a>Zweck

Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschlange und leitet sie dann an Agentgruppen weiter. Um fundierte Entscheidungen darüber zu treffen, welche Anrufe an den Dienst erfolgen, können Agents auf Echtzeitinformationen zu ihren Agentgruppen zugreifen, z. B. welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, auf die anfänglich nur über den Reaktionsgruppendienst zugegriffen werden kann, werden von Response Group Agent Live intuitiv zur Verfügung gestellt.

#### <a name="features"></a>Features

Das Tool Response Group Agent Live basiert auf dem Reaktionsgruppendienst und dem Skype for Business Server 2015 SDK. Es stellt Reaktionsgruppen-Agents die Informationen und Funktionen bereit, die über den Reaktionsgruppendienst verfügbar sind (z. B. Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).

Die abbildung unten zeigt die Hauptschnittstelle von Response Group Agent Live.

![Das Reaktionsgruppen-Agent-Live-Tool.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Die folgenden drei Hauptfunktionen sind für Agents in Response Group Agent Live verfügbar:

- **Anmelden/Abmelden:** Im Gegensatz zur Seite "Agent-Gruppen" (auf die von Skype for Business Server 2015 aus zugegriffen werden kann), ermöglicht Response Group Agent Live nur Agents, sich bei allen Agentgruppen gleichzeitig anzumelden oder sie zu abmelden. Diese Anwendung bietet Agents drei schnelle Möglichkeiten zum Anmelden oder Abmelden:

  - Klicken Sie auf die Schaltflächen "Anmelden/Abmelden" (grün und rot) innerhalb der Anwendung.

  - Klicken Sie mit der rechten Maustaste auf das Taskleistensymbol des Systems, und wählen Sie "Anmelden" oder "Abmelden" aus.

  - Verwenden konfigurierbarer Tastenkombinationen.

- **Gruppenmitgliedschaft:** Wenn eine Agentgruppe ausgewählt ist, zeigt Response Group Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an. Wenn Skype for Business Server 2015 auf demselben Computer wie diese Anwendung ausgeführt wird, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt. Agents können eine Chatnachricht senden oder andere Agents direkt von dort aus anrufen.

- **Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agentgruppen. Die Updatehäufigkeit beträgt eine Minute. Wenn ein Anruf von einer Reaktionsgruppe angenommen wird, wird neben dem Gruppennamen ein visueller Indikator mit der aktuellen Anzahl von Anrufen in der Warteschlange hinzugefügt. Beim Anhalten des Zeigers über einer Gruppe wird auch die längste Wartezeit angezeigt.

### <a name="requirements"></a>Anforderungen

Response Group Agent Live erfordert die .NET Framework 4.0. Um die Anwesenheits- und Visitenkartenfeatures nutzen zu können, müssen Skype for Business außerdem lokal installiert werden (und ausgeführt werden).

#### <a name="configuration"></a>Konfiguration

Response Group Agent Live kann mithilfe des Dialogfelds "Optionen" in der Anwendung an einzelne Einstellungen angepasst werden. Darüber hinaus kann der Administrator die Standardhostadresse definieren, indem er die defaultHostAddress-Eigenschaft der RGAgentLive.exe.config-Datei direkt bearbeitet.

Die abbildung unten zeigt das Dialogfeld Optionen, das Agents zum Konfigurieren der Hostadresse und der Tastenkombinationen verwenden können. Auf dieses Dialogfeld wird zugegriffen, indem Sie auf die Schaltfläche "Optionen" oben rechts auf der Hauptschnittstelle klicken.

![Das Dialogfeld "Live-Optionen für Reaktionsgruppen-Agent".](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Die folgenden drei verschiedenen Einstellungen können in der Response Group Agent Live-Konfiguration angepasst werden:

- Hostadresse: Dies ist in der Regel der Webpool-FQDN, der zum Home-Pool des Agents gehört. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund von diesen Informationen abgeleitet (durch Anfügen des rechten Pfads nach dem Host).

- Tastenkombinationen: Die genauen Verknüpfungen zum Anmelden/Abmelden können angepasst werden. Die einzige Einschränkung besteht darin, dass beide Tastenkombinationen die Taste "Windows Logo" enthalten müssen (zusätzlich zu mindestens einer anderen Taste).

- Beginnen Sie mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch mit Windows gestartet wird.

### <a name="examples"></a>Beispiele

In der folgenden Abbildung wird veranschaulicht, wie Sie eine Chatnachricht an einen anderen Agent senden oder anrufen, indem Sie im rechten Bereich mit der rechten Maustaste auf den Kontakt klicken.

![Tätigen eines Anrufs oder Senden einer Chatnachricht.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

Die abbildung unten zeigt, wie Response Group Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife und die längste Wartezeit zwischen all diesen eingehenden Anrufen anzeigt.

![Anzeigen von Warteschlangeninformationen.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Zusammenfassung

Schnelles Anmelden und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Funktionen für Reaktionsgruppen-Agent, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind. Mit dem Tool Response Group Agent Live Resource Kit können Skype for Business Server 2015-Administratoren ihren Agents eine Windows-Anwendung bereitstellen, mit der sie Aufgaben schneller und grafischer ausführen können.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (secondary extension feature activation) ist ein Befehlszeilentool, das es Skype for Business Server 2015-Kommunikationssoftwareadministratoren und Helpdesk-Agents ermöglicht, Delegatenringe, Anrufweiterleitung, gleichzeitiges Klingeln, Teamanrufeinstellungen und Gruppenanrufannahme im Auftrag eines Skype for Business Server 2015-Benutzers zu konfigurieren. Mit dem Tool können Administratoren auch die Anrufweiterleitungseinstellungen abfragen, die für einen bestimmten Benutzer veröffentlicht wurden. Mit dem SEFAUtil-Tool kann der Administrator die Anrufweiterleitung oder das gleichzeitige Klingeln im Namen des Benutzers aktivieren/deaktivieren/ändern. Der Administrator kann das Ziel (in Form eines SIP-URI) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde. Mit diesem Tool können Administratoren auch Stellvertretungen oder Teamanrufgruppenmitglieder im Namen des Benutzers hinzufügen oder entfernen. Dieses Tool basiert auf microsoft Unified Communications Managed API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.

SEFAUtil (secondary extension feature activation) ermöglicht Skype for Business Server 2015-Administratoren und Helpdesk-Agents das Konfigurieren von Delegatenringen, Anrufweiterleitung, gleichzeitiges Klingeln, Teamanrufeinstellungen und Gruppenanrufannahme im Namen eines Skype for Business Server 2015-Benutzers. Mit diesem Tool können Administratoren auch die Anrufweiterleitungseinstellungen abfragen, die für einen bestimmten Benutzer veröffentlicht wurden.

### <a name="description"></a>Beschreibung

Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool. es gibt keine unterstützende grafische Benutzeroberfläche. Dieses Tool basiert auf microsoft Unified Communications Managed API (UCMA) 3.0. Die Features in diesem Tool ermöglichen Administratoren und Helpdesk-Agents Folgendes:

- Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Delegierung, gleichzeitiges Klingeln, Teamanruf und Gruppenanrufannahme)

- Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellung (einschließlich Ziel- und No-Answer-Timer)

- Sofortige Konfigurationen für die Anrufweiterleitung aktivieren/deaktivieren/ändern

- Aktivieren/Deaktivieren/Ändern von Delegierungseinstellungen

- Aktivieren/Deaktivieren/Ändern von Gruppeneinstellungen für Teamanrufe

    > [!NOTE]
    > Neues SEFAUtil-Tool in Skype for Business Server 2015

- Aktivieren/Deaktivieren/Ändern der Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)

    > [!NOTE]
    > Neues SEFAUtil-Tool in Skype for Business Server 2015

- Aktivieren/Deaktivieren/Ändern der Einstellungen für die Gruppenanrufannahme

    > [!CAUTION]
    > Neues SEFAUtil-Tool in Skype for Business Server 2015

Für dieses Tool gelten die folgenden Einschränkungen:

- Wird nur für Benutzer unterstützt, die in einem Skype for Business Server-Pool verwaltet werden

- Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer wird nicht unterstützt.

### <a name="output"></a>Ausgabe

Die aktuelle Version dieses Tools stellt die Ausgabe nur im Eingabeaufforderungsfenster bereit. Ausführliche Informationen finden Sie im Abschnitt "Beispiele" weiter unten in diesem Dokument.

### <a name="purpose"></a>Zweck

Es folgen einige der wichtigsten Szenarien, in denen dieses Tool verwendet werden kann:

- Bob ist Führungskraft und wurde zu Skype for Business Server Telefonie verschoben. Er verfügt über eine Delegierung für sein vorhandenes PBX-System. Im Rahmen der Umstellung auf Skype for Business Server 2015 kann der Administrator Bobs Routing konfigurieren, um seine bereits vorhandene Delegierungskonfiguration widerzuspiegeln.

- Andrea ist unterwegs und erkennt, dass sie einen wichtigen Anruf von einem ihrer Kunden erwartet. Sie befindet sich jedoch in einem Hotel und hat keinen Zugriff auf einen Computer. Sie ruft das Helpdesk an und fordert sie auf, alle Anrufe, die an ihre Geschäftliche Nummer getätigt wurden, an ihre Mobiltelefonnummer weiterzuleiten. Das Helpdesk-Personal ist in der Lage, die Konfiguration in ihrem Auftrag durchzuführen.

- Joes Anrufe an seine Arbeitsnummer gehen immer dann zu seiner mobilen Voicemail, wenn er bei der Arbeit ist; In den meisten anderen Speicherorten scheint dies jedoch ordnungsgemäß zu funktionieren. Der Helpdesk-Techniker kann Joes Routingkonfiguration anzeigen und erkennt, dass Joe das gleichzeitige Klingeln auf seinem Mobiltelefon konfiguriert hat. Der Techniker fragt Joe nach der Mobilen Abdeckung in seinem Büro und kann feststellen, dass die Regel für gleichzeitiges Klingeln dazu führt, dass die Anrufe an Joes mobile Voicemail weitergeleitet werden, wenn seine Netzwerkabdeckung schlecht ist.

- Michael ist ein neuer Mitarbeiter bei Contoso und tritt einem neuen Team bei, in dem alle Mitglieder für Teamanrufe konfiguriert sind. Wenn er für Skype for Business Server 2015 aktiviert wird, kann der Administrator seine Teamanrufgruppeneinstellungen so festlegen, dass alle seine neuen Teammitglieder einbezogen werden. Darüber hinaus fügt der Administrator Contoso als Teamanrufgruppenmitglied für jedes Mitglied in seinem Team hinzu.

- Eine Kundendienstpraxis in der Personalabteilung bei Contoso besteht darin, seit dem ersten Anruf persönlichen Service für alle Anrufer bereitzustellen. Da sich alle Mitglieder der Abteilung sehr nah beieinander befinden, ist das gleichzeitige Klingeln aller Telefone mit Teamanrufen für das Team störend. Um den besten Dienst bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der Skype for Business Server 2015-Administrator die Funktion "Gruppenanrufannahme". Der Administrator fügt alle Abteilungsmitglieder zu einer Pickup-Gruppe hinzu und teilt der Abteilung die Nummer der Pickup-Gruppe mit. Wenn Samantha auf ihrem Schreibtisch nicht vorhanden ist, bemerkt Joe, dass ihr Telefon klingelt, und er nimmt den Anruf von seinem Schreibtisch aus entgegen.

### <a name="requirements"></a>Anforderungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. UCMA 3.0 muss auf diesem Computer installiert sein. Zum Ausführen des Tools muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool

1. Das SEFAUTil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die Skype for Business Server Verwaltungsshell mit dem folgenden Cmdlet erfolgen:

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3.0 muss auf jedem Computer installiert sein, der zum Ausführen des SEFAUtil-Tools verwendet wird.

2. Eine vertrauenswürdige Anwendung muss in der Topologie für das SEFAUtil-Tool definiert werden. Um SEFAUtil als neue vertrauenswürdige Anwendung zu definieren, verwenden Sie die Skype for Business Server-Verwaltungsshell, und führen Sie das folgende Cmdlet aus:

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Bei Bedarf kann ein anderer Port verwendet werden.
    
    > [!NOTE]
    > Pool-FQDN: Der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hosten soll (in der Regel ein Skype for Business Front-End-Server > oder Pool).
    > Poolregistrierungsstellen-FQDN: Der FQDN des Skype for Business Front-End-Servers oder -Pools, der diesem Anwendungspool zugeordnet ist.
    > Poolstandort: Die Standort-ID des Standorts, auf dem dieser Pool verwaltet wird.

3. Die Topologieänderungen müssen aktiviert werden. Das Aktivieren der Topologieänderungen kann über die Skype for Business Server Verwaltungsshell erfolgen, indem Das folgende Cmdlet ausgeführt wird:

   ```powershell
   Enable-CsToplogy
   ```

4. Installieren Sie bei Bedarf die Skype for Business Server 2015 Resource Kit Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).

5. Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool über eine Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. Standardmäßig befindet sich das Tool in: "...\Programme\Skype for Business Server 2015\Reskit". Verwenden Sie den folgenden Befehl, um die Anrufweiterleitungseinstellungen eines Benutzers anzuzeigen:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.

#### <a name="group-call-pickup"></a>Gruppenanrufannahme

Die Gruppenanrufannahme erfordert eine zusätzliche Konfiguration in Skype for Business Server 2015, damit die Funktion vollständig aktiviert ist. Bevor Sie Benutzern Pickup-Gruppen zuweisen, finden Sie in der Produktdokumentation zur Gruppenanrufannahme die Planungs- und Bereitstellungsschritte dieser Funktion.

### <a name="examples"></a>Beispiele

#### <a name="display-current-call-handling-settings"></a>Anzeigen der aktuellen Anrufbehandlung Einstellungen

Der folgende Befehl zeigt die Anrufbehandlung für den Benutzer an.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> In diesem Beispiel wird der Switch **"/server**" verwendet, um die Skype for Business Server anzugeben, mit der eine Verbindung hergestellt werden soll.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Festlegen des Anrufweiterleitungs-/Kein-Antwort-Ziels

In diesem Beispiel werden das Anrufweiterleitungs-/kein Antwortziel und die Anrufverzögerung festgelegt. Hier wird der /server-Switch nicht bereitgestellt. SEFAUtil versucht, die Skype for Business Server 2015 automatisch zu ermitteln.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
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

#### <a name="enable-call-forwarding-immediately"></a>Sofortiges Aktivieren der Anrufweiterleitung

In diesem Beispiel wird sofort die Anrufweiterleitung an einen anderen Benutzer aktiviert.

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

#### <a name="disable-call-forwarding-immediately"></a>Sofortiges Deaktivieren der Anrufweiterleitung

In diesem Beispiel wird die Anrufweiterleitung sofort deaktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
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

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Hinzufügen eines Benutzers als Stellvertretung und Einrichten des gleichzeitigen Klingelns von Delegaten

In diesem Beispiel wird ein Benutzer als Delegat hinzugefügt und gleichzeitiges Klingeln von Delegaten eingerichtet.

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

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Ändern der Regel für gleichzeitiges Klingeln von Delegaten

In diesem Beispiel wird die Regel für gleichzeitiges Klingeln, die im vorherigen Beispiel festgelegt wurde, in die Regel für verzögertes Klingeln geändert.

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

#### <a name="remove-the-delegate"></a>Entfernen des Delegaten

In diesem Beispiel wird der Delegat entfernt.

> [!NOTE]
> Wenn der letzte Delegat entfernt wird, wird das Stellvertretungsringen automatisch deaktiviert.

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

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Hinzufügen eines Delegaten und Einrichten der Call-Forward zu Stellvertretungsregel

In diesem Beispiel wird ein Delegat hinzugefügt und die Regel zum Weiterleiten von Anrufen an Stellvertretungen eingerichtet.

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

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Aktivieren des gleichzeitigen Klingelns und Festlegen einer Zielnummer

In diesem Beispiel wird das gleichzeitige Klingeln aktiviert und eine Zielnummer für gleichzeitiges Klingeln festgelegt.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Um die Zielnummer des gleichzeitigen Klingelns eines Benutzers zu ändern, für den das gleichzeitige Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Schalter "/enablesimulring" bei, andernfalls wird die Zielnummer nicht geändert.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Deaktivieren des gleichzeitigen Klingelns

In diesem Beispiel wird das gleichzeitige Klingeln deaktiviert.

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

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Hinzufügen eines Teammitglieds für Team-Call und Einrichten des gleichzeitigen Klingelns zur Gruppe "Team-Call Mitglieder"

In diesem Beispiel wird der Teamanrufgruppe eines Benutzers ein Teammitglied hinzugefügt und gleichzeitiges Klingeln an die Teamanrufgruppe ermöglicht.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Wenn Sie ein Mitglied zur Teamanrufgruppe eines Benutzers hinzufügen, werden die gleichzeitigen Anrufanleitungssätze der Benutzer automatisch in das gleichzeitige Klingeln seiner Teamanrufgruppe umgeschaltet.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Entfernen eines Mitglieds aus der Team-Call-Gruppe

In diesem Beispiel wird ein Teammitglied der Teamanrufgruppe eines Benutzers entfernt.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Wenn das entfernte Mitglied das einzige Mitglied der Teamanrufgruppe ist, wird das gleichzeitige Klingeln an die Teamanrufgruppe automatisch deaktiviert.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Festlegen des verzögerten Rings auf die Team-Call-Gruppe

In diesem Beispiel wird der verzögerte Ring in die Einstellung für die Teamanruf-Gruppenzeit geändert.

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

#### <a name="enable-team-call"></a>Aktivieren Team-Call

In diesem Beispiel wird teamanrufen für einen bestimmten Benutzer aktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Wenn die Teamanrufgruppe des Benutzers keine Mitglieder hat, wird der Teamanruf nicht aktiviert.

 **Ausgabe**

#### <a name="disable-team-call"></a>Deaktivieren Team-Call

In diesem Beispiel wird der Teamanruf für einen bestimmten Benutzer deaktiviert.

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

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Aktivieren der Gruppenanrufannahme und Zuweisen einer Pickup-Gruppe zu einem Benutzer

In diesem Beispiel wird einem Benutzer eine Annahmegruppe zugewiesen und die Gruppenanrufannahme aktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Deaktivieren der Gruppenanrufannahme

In diesem Beispiel wird die Gruppenanrufannahme für einen bestimmten Benutzer deaktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, wird die Gruppennummer, die dem Benutzer zugewiesen wurde, nicht beibehalten. Wenn Sie anschließend die Gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie die Gruppennummer erneut mit dem Schalter "/enablegrouppickup" zuweisen.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Beschreibung

SYSPrep.ps1 ist ein skript Windows PowerShell, das die folgenden Skype for Business Server 2015-Komponenten auf ihrem Windows Server 2008-Betriebssystemcomputer installiert.

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell Version 3.0

- Visual C++ 2010 Redistributable

- Updates für Internetinformationsserver

- Windows Identity Foundation

- Skype for Business Server 2015 Core-Dateien

  Der Name des Skripts ähnelt zwar dem Systemvorbereitungstool für die Microsoft Windows-Betriebssysteme, unterscheidet sich jedoch. Dieses Skript installiert nur die erforderlichen Komponenten für Skype for Business Server 2015. Sobald diese Voraussetzungen installiert sind, kann das Windows SYSPrep-Tool verwendet werden, um ein Image des Servers zu erstellen.

### <a name="requirements"></a>Anforderungen

Bevor Sie das Skript SYSPrep.ps1 ausführen, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Betriebssystemcomputer Windows Server 2008 kopieren (z. B. **D:\Setup).** Dieser Ordner muss auch eine Kopie der Skype for Business Server 2015-Dateien enthalten, insbesondere **Setup.exe.** Die erforderlichen Dateien können von den folgenden Speicherorten heruntergeladen werden:


| **Voraussetzungen**                                | **Ort**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell Version 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 Redistributable  <br/>          | <https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0>  <br/>  |
| Updates für Internetinformationsserver  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Kopieren von Skype for Business Server 2015-Medien  <br/>                   |

### <a name="parameter"></a>Parameter

Der Parameter **"-SetupFolder** " verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.

### <a name="examples"></a>Beispiele

Führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, um das Skript SYSPrep.ps1 auszuführen und die voraussetzungen für Skype for Business Server 2015 zu installieren:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration
<a name="UNAM"> </a>

Das Migrationstool "Ankündigungen nicht zugewiesener Nummern" ermöglicht es einem Skype for Business Server 2015-Administrator, die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung bedient wird, von einer Quell-Skype for Business Server oder einem Pool an ein Ziel zu verschieben. Skype for Business Server oder Pool.

### <a name="description"></a>Beschreibung

Das Migrationstool "Unassigned Number Announcements" ist ein Windows PowerShell Skript, das die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung eines Quellservers oder -pools bedient wird, auf einen anderen Server oder Pool verschiebt.

Wenn das Skript "Unassigned Number Announcements Migration" ausgeführt wird, werden die folgenden Vorgänge ausgeführt:

1. Verschieben Sie alle Audiodateien, die von den Ankündigungen nicht zugewiesener Nummern der ankündigungsanwendung verwendet werden, die auf dem Quellserver oder -pool gehostet wird, in den Dateispeicher des Zielservers oder -pools.

    > [!NOTE]
    > Die Audiodateien werden aus dem Quellpool entfernt, nachdem sie in den Zielpool kopiert wurden.

2. Verschieben Sie alle Ankündigungen nicht zugewiesener Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver oder -pool gehostet wird, auf den Zielserver oder -pool.

3. Weisen Sie alle Bereiche nicht zugewiesener Nummern, die von der ankündigungsanwendung gewartet werden, die auf dem Quellserver oder -pool gehostet wird, dem Zielserver oder -pool neu zu.

Nach der erfolgreichen Ausführung des Skripts werden alle Bereiche nicht zugewiesener Nummern, die von der ankündigungsanwendung gewartet wurden, die auf dem Quellserver oder -pool gehostet wurde, jetzt mit derselben Konfiguration vom Zielserver oder -pool bedient.

### <a name="output"></a>Ausgabe

Das **Skript "Move-CsAnnouncementConfiguration**" gibt im Fenster Skype for Business Server Verwaltungsshell an, von wo aus der Migrationsvorgang erfolgreich oder fehlgeschlagen ist.

Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die Bereiche nicht zugewiesener Nummern, die erfolgreich an das Ziel verschoben wurden, im Ziel in einer betriebsbereiten Form, und die restlichen bereiche nicht zugewiesener Nummern, die migriert werden sollen, verbleiben in der Quelle sowie in einer betriebsbereiten Form. Führen Sie das Skript nach dem Beheben des Fehlers erneut aus, um den Rest der Konfiguration vollständig zu migrieren.

### <a name="purpose"></a>Zweck

Das Migrationsskript "Unassigned Number Announcements" kann in den folgenden drei Szenarien verwendet werden:

- **Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype for Business Server:** Contoso ist gerade dabei, zu Skype for Business Server 2015 zu migrieren, und im Rahmen des Migrationsprozesses wird die Skype for Business Server  Der Administrator möchte die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung bedient wird, aus der Lync Server 2013-Bereitstellung in die neue Skype for Business Server 2015-Bereitstellung verschieben. Um die Konfigurationseinstellungen zu verschieben, verwendet der Skype for Business Server Administrator das Migrationstool "Unassigned Number Announcements".

- **Zurücksetzen einer Bereitstellung von Skype for Business Server 2015 auf Lync Server 2013:** Aufgrund unerwarteter Faktoren muss Contoso die Migration zur neuen Skype for Business Server 2015-Bereitstellung zurücksetzen. Um Unterbrechungen des Diensts zu minimieren, verwendet der Skype for Business Server Administrator das Migrationstool "Unassigned Number Announcements", um ein Rollback der Konfiguration von der Bereitstellung Skype for Business Server 2015 auf die Lync Server 2013-Bereitstellung durchzuführen.

- **Verschieben von Daten zwischen Bereitstellungen:** Contoso ist dabei, alle Server eines Pools durch neuere Server zu ersetzen. Ihre Strategie besteht darin, einen neuen Skype for Business Server 2015-Pool bereitzustellen, alle Daten aus dem alten in den neuen Pool zu verschieben und dann den alten Pool als veraltet zu markieren. Nachdem der neue Pool bereitgestellt wurde, wird das Migrationstool "Ankündigungen für nicht zugewiesene Nummern" verwendet, um die Konfiguration aus dem alten Pool in den neuen pool zu verschieben.

#### <a name="requirements"></a>Anforderungen

Im Folgenden sind die wichtigsten Voraussetzungen aufgeführt, die zum erfolgreichen Ausführen des Tools erforderlich sind:

1. Das Skript muss auf einem Computer ausgeführt werden, auf dem Skype for Business Server Verwaltungsshell installiert ist.

2. Die Ankündigungsanwendung muss erfolgreich in der Quell- und Zielanwendung Skype for Business Servern oder Pools bereitgestellt werden.

#### <a name="move-csannouncementconfiguration-script"></a>skript Move-CsAnnouncementConfiguration

Das skript Move-CsAnnouncementConfiguration erfordert die beiden Parameter, die in der folgenden Tabelle beschrieben sind.

![Move-CsAnnouncementConfiguration Parameter.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Beispiele

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Verschieben der Konfiguration für Ankündigungen nicht zugewiesener Nummern aus einem Lync Server 2013-Pool in einen Skype for Business Server 2015-Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quellpool (Lync Server 2013) in den Zielpool verschoben (Skype for Business Server 2015).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Verschieben der Konfiguration für Ankündigungen nicht zugewiesener Nummern aus einem Skype for Business Server 2015-Pool in einen Lync Server 2013-Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quellpool (Skype for Business Server 2015) in den Zielpool (Lync Server 2013) verschoben.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

Das Web Conf Data Tool ermöglicht es einem Administrator von Skype for Business Server 2015-Kommunikationssoftware, mehr Kontrolle über die Daten zu haben, die den Webkonferenzen eines Organisators zugeordnet sind. Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers basierend auf einem Zeitstempelkriterium zu löschen.

### <a name="description"></a>Beschreibung

Mit diesem Tool kann der Administrator die folgenden Vorgänge ausführen:

1. Suchen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

2. Löschen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

3. Löschen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, der älter als ein bestimmtes Datum ist.

4. Verschieben Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.

    > [!NOTE]
    > Die Resource Kit-Tools für Lync Server 2010 unterstützten das Verschieben aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird. Diese Funktionalität ist nun von diesem Tool zugunsten des **MoveConferenceData-Parameters** veraltet. Ausführliche Informationen zu diesem Parameter finden Sie im Cmdlet ["Move-CsUser](/powershell/module/skype/move-csuser?) ".

Das Tool löscht Besprechungsdaten nur für Besprechungen, die inaktiv sind. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.

Dieses Tool muss von einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool verwaltet werden.

### <a name="output"></a>Ausgabe

Dieses Tool gibt die Ergebnisse der einzelnen Vorgänge aus:

- Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, die diesen Benutzer als Organisator haben.

- Wenn ein Löschen durchgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.

### <a name="requirements"></a>Anforderungen

Das Tool muss in demselben Pool ausgeführt werden, in dem der Organisator derzeit verwaltet wird.

Das Tool muss mit Administratorrechten mit Zugriff auf die Inhaltsdatei Store ausgeführt werden.

### <a name="examples"></a>Beispiele

In der folgenden Tabelle werden die Parameter beschrieben, von denen einige in den Beispielen verwendet werden.

![Web Conf Data Tool-Parameter.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

Das vorstehende Beispiel ist ein Beispiel für einen Löschbefehl. Mit dem Löschbefehl werden alle inaktiven Besprechungsordner von diesem Benutzer entfernt.

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präziseere Kontrolle über Konferenzbesprechungsdaten benötigen.
