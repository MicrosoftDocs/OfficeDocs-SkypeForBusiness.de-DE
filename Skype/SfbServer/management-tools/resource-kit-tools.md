---
title: Skype for Business Server 2015 Resource Kit Tools Documentation
ms.reviewer: ''
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
description: In diesem Artikel werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks jedes Tools und Beispiele für seine Verwendung. Das Skype for Business Server 2015 Resource Kit erleichtert IT-Administratoren, die Skype for Business Server 2015 bereitstellen und verwalten, Routineaufgaben. Beispielsweise kann das Webkonferenz-Datentool verwendet werden, um Daten zu steuern, die von Benutzern während einer Onlinebesprechung hochgeladen werden. Das SEFAUtil-Tool kann verwendet werden, um die Weiterleitung und Beantwortung von Stellvertretungsanrufen für Benutzer einzurichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.
ms.openlocfilehash: 83777dbe16e70030b13c07fced716ffbc4d51f35
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675497"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 Resource Kit Tools Documentation

In diesem Artikel werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks jedes Tools und Beispiele für seine Verwendung. Das Skype for Business Server 2015 Resource Kit erleichtert IT-Administratoren, die Skype for Business Server 2015 bereitstellen und verwalten, Routineaufgaben. Beispielsweise kann das **Webkonferenz-Datentool** verwendet werden, um Daten zu steuern, die von Benutzern während einer Onlinebesprechung hochgeladen werden. Das **SEFAUtil-Tool** kann verwendet werden, um die Weiterleitung und Beantwortung von Stellvertretungsanrufen für Benutzer einzurichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Um das Skype for Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) aus dem Download Center herunter.

Führen Sie **OCSResKit.msi** aus, um eine einfache Installation durchzuführen. Die .msi installiert alle Tools im folgenden Pfad: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools, die eigenständige ausführbare Dateien sind, befinden sich in diesem Ordner. Tools, die auch unterstützende Dateien enthalten, befinden sich in ihren eigenen Unterordnern.

## <a name="supported-environments"></a>Unterstützte Umgebungen

Das Skype for Business Server 2015 Resource Kit sollte auf einem Server installiert werden, der die für Skype for Business Server 2015 erforderlichen Spezifikationen erfüllt, die normalerweise zum Ausführen Skype for Business Server 2015 verwendet werden.

## <a name="resource-kit-tools-overview"></a>Übersicht über Resource Kit-Tools

Im Folgenden finden Sie eine Liste der Tools, die im Skype for Business Server 2015 Resource Kit bereitgestellt werden. Eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispielnutzung, wird in den folgenden Abschnitten behandelt.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Bandbreitenrichtliniendienstüberwachung](resource-kit-tools.md#bpsm)

- [Bandwidth Utilization Analyzer](resource-kit-tools.md#bua)

- [Parkometer für Anrufe](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importieren Storage Dienstdaten](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Benutzerkonsole nachschlagen](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Netzwerkkonfigurations-Viewer](resource-kit-tools.md#NCV)

- [Reaktionsgruppen-Agent-Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Migration von Ankündigungen für nicht zugewiesene Nummern](resource-kit-tools.md#UNAM)

- [Webkonferenzdaten](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

Das Adressbuchdienstkonfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in Skype for Business Server 2015 anpassen können. Dieses Tool ermöglicht es Skype for Business Server 2015-Administratoren auch, die Standardeinstellungen des Adressbuchdiensts wiederherzustellen.

### <a name="description"></a>Beschreibung

ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory Domain Services Attribute konfigurieren können, die sich auf den Adressbuchdienst beziehen.

Die wichtigsten Szenarien für das Tool sind die folgenden:

- Damit Administratoren Attribute in Active Directory Domain Services den Attributen für Skype for Business Server 2015 zuordnen können.

- Damit Administratoren das Active Directory Domain Services Attribut angeben können, das in den Adressbuchdienstdateien enthalten oder ausgeschlossen werden soll.

- Um Administratoren das Wiederherstellen zu ermöglichen, verwenden Sie die Standardeinstellungen für den Adressbuchdienst.

Das ABSConfig-Tool kann mithilfe der ABSConfig.exe Datei gestartet werden. Das Tool wird zur Registerkarte "**Attribute konfigurieren**" geöffnet. Diese Tabelle enthält Optionen zum Zuordnen Active Directory Domain Services Attribute zu den Attributfeldern für Skype for Business Server 2015 und zum Angeben, welche Benutzer basierend auf bestimmten Attributfiltern in Adressbuchdienstdateien ein- oder ausgeschlossen werden sollen. Außerdem gibt es Optionen zum Anpassen des Werts der Telefonnummer, die in die Adressbuchdatei aufgenommen werden soll. Mit der Option **"Standardeinstellungen wiederherstellen** " können Administratoren die Einstellungen des Adressbuchdiensts auf Standardwerte zurücksetzen.

> [!NOTE]
> Die erneute Zuordnung von AD-Attributen zu verschiedenen OC-Feldnamen funktioniert nur beim Herunterladen von Adressbuchdateien und wird von der Adressbuch-Webabfrage nicht unterstützt.

### <a name="output"></a>Ausgabe

ABSConfig speichert die Adressbuchdienstkonfiguration in der Datenbank.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Zweck

ABSConfig bietet eine schnelle und einfache Möglichkeit, Skype for Business Server 2015-Adressbuchdienst anzupassen.

### <a name="requirements"></a>Anforderungen

#### <a name="computer"></a>Computer

ABSConfig kann nur von einem in die Domäne eingebundenen Computer ausgeführt werden, auf dem Skype for Business Server 2015 installiert ist. Im Fall von Skype for Business Server 2015 kann dieses Tool Enterprise Edition auf allen Front-End Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.

#### <a name="network"></a>Netzwerk

Der Computer sollte eine Verbindung mit dem Front-End Pool und der Back-End-Datenbank herstellen können.

#### <a name="software"></a>Software

Die folgenden Softwarekomponenten müssen installiert werden, bevor das ABSConfig-Tool ausgeführt wird:

- Skype for Business Server 2015

#### <a name="users"></a>Benutzer

Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der Skype for Business Server 2015-Bereitstellung verfügen.

### <a name="examples"></a>Beispiele

ABSConfig kann gestartet werden, indem **ABSConfig.exe** an einer Eingabeaufforderung eingegeben wird. Unten sehen Sie die Benutzeroberfläche des ABSConfig-Tools.

![Das tool ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Zusammenfassung

Das ABSConfig-Tool bietet Administratoren ein tool schnell und einfach zu verwenden, um Skype for Business Server 2015 Adressbuch-Dienst anpassen.

## <a name="bandwidth-policy-service-monitor"></a>Bandbreitenrichtliniendienstüberwachung
<a name="bpsm"> </a>

Mit dem Tool "Bandbreitenrichtliniendienstüberwachung" können Administratoren eine Liste der folgenden Elemente anzeigen:

1. Alle konfigurierten Skype for Business Server 2015 Bandwidth Policy Services (Authentication and Core) in der Topologie

2. Die Verbindungen, die jeder Dienst zu anderen Bandbreitenrichtliniendiensten und zu den Edgeservern macht

3. Alle Links, die im Netzwerkkonfigurationsdokument konfiguriert sind, und die Bandbreitennutzung in Echtzeit, wie von jedem der Bandbreitenrichtliniendienste angegeben.

### <a name="description"></a>Beschreibung

Das Tool Bandwidth Policy Service Monitor ist als GUI-basierte Anwendung implementiert. Administratoren starten das Tool, indem sie PDPMonUI.exe ausführen.

Beim Starten des Tools wird versucht, die Liste der Bandbreitenrichtliniendienste in der Topologie zu ermitteln. Nachdem die erste Aktualisierung abgeschlossen ist, wird der Bereich links neben dem Fenster mit einer Liste der Dienste aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.

Wenn Administratoren einen bestimmten Bandbreitenrichtliniendienst auswählen, werden im Bereich auf der rechten Seite die Informationen zu diesem bestimmten Dienst angezeigt. Dieser Bereich verfügt außerdem über zwei Hauptregisterkarten, auf denen Informationen angezeigt werden.

#### <a name="machine-info-tab"></a>Registerkarte "Computerinfo"

Auf der Registerkarte " **Computerinformationen** " werden die Details des ausgewählten Bandbreitenrichtliniendiensts sowie die Liste und der Status aller Verbindungen angezeigt, die vom ausgewählten Bandbreitenrichtliniendienst mit anderen Diensten hergestellt werden.

#### <a name="topology-info-tab"></a>Registerkarte "Topologieinformationen"

Auf der Registerkarte " **Topologieinformationen** " wird eine Liste aller Links angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jeden Link wird die Bandbreitenkapazität für Audio und Video angezeigt. Darüber hinaus wird die aktuell genutzte Bandbreite sowohl in KBit/s als auch als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierung, um Links hervorzuheben, die eine Auslastung aufweisen, die nahe an der Kapazität liegt. Auf diese Weise können Administratoren solche Links schnell isolieren.

> [!NOTE]
>  Wenn das Tool "Bandbreitenrichtliniendienstüberwachung" fehlert, wenn es eine Verbindung mit einem der konfigurierten Bandbreitenrichtliniendienste herstellt, werden die Informationen auf den Registerkarten **"Computerinformationen** " und " **Topologieinformationen** " nicht aufgefüllt. Es ist jedoch möglich, dass das Tool zunächst eine Verbindung herstellt, anschließend aber seine Verbindung mit dem Dienst verliert. In solchen Fällen werden Administratoren möglicherweise veraltete Informationen angezeigt. Auf jeder Registerkarte gibt es einen Zeitstempel für die **letzte Aktualisierung** , mit dem Administratoren sehen können, wann die Daten für einen bestimmten Bandbreitenrichtliniendienst zuletzt aktualisiert wurden.

### <a name="output"></a>Ausgabe

Es gibt keine Befehlszeilenausgabe. die Programmausgabe ist in der grafischen Haupt-Benutzeroberfläche (GUI) enthalten.

### <a name="purpose"></a>Zweck

Der Zweck des Tools "Bandbreitenrichtliniendienstüberwachung" besteht darin, Administratoren einen Einblick in den Status der einzelnen Bandbreitenrichtliniendienste zu ermöglichen, die in der Topologie definiert sind. Darüber hinaus können Administratoren die Bandbreitennutzung in Echtzeit für alle Links sehen, die im Netzwerkkonfigurationsdokument definiert sind.

### <a name="requirements"></a>Anforderungen

Das Tool "Bandbreitenrichtliniendienstüberwachung" muss auf einem Computer ausgeführt werden, der Teil der Skype for Business Server Topologie ist.

### <a name="summary"></a>Zusammenfassung

Das Tool "Bandbreitenrichtliniendienstüberwachung" kann eine wertvolle Ressource für Administratoren sein, damit sie den Status aller Bandbreitenrichtliniendienste in der Topologie überprüfen können – und was noch wichtiger ist – sie können die Bandbreitenauslastung in Echtzeit für die In den Netzwerkkonfigurationseinstellungen definierten Links abrufen.

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer
<a name="bua"> </a>

Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Diese Berichte können verwendet werden, um das aktuelle Bandbreitennutzungsmuster zu verstehen und die Planung der Bandbreitenkapazität zu unterstützen.

### <a name="description"></a>Beschreibung

Bandwidth Utilization Analyzer wird als GUI-basierte Anwendung implementiert. Dieses Tool generiert Berichte speziell für die Audionutzung im gesamten Netzwerk und hilft bei der Kapazitätsplanung. Außerdem wird die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist, durchläuft.

### <a name="output"></a>Ausgabe

Bandwidth Utilization Analyzer bietet grafische Darstellungen der Bandbreitenkapazität und Auslastung für Audio für alle WAN-Verbindungen, die im System konfiguriert sind.

### <a name="purpose"></a>Zweck

Bei jeder VoIP- und Videobereitstellung ist es wichtig, den Trend der Bandbreitennutzung des Mediendatenverkehrs im Unternehmensnetzwerk zu überwachen und zu verstehen. Das Tool "Bandwidth Utilization Analyzer" ermöglicht es einem Administrator, genau dies zu erreichen. Dieses Tool führt folgende Aktionen aus:

- Generiert spezifische Berichte für die Audionutzung im gesamten Netzwerk.

- Hilft bei der effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.

Bandbreitenauslastungsanalyse kann grafische Darstellungen von Bandbreitenkapazitäts- und Auslastungsberichten generieren. sie lauten wie folgt:

- Alle WAN-Verbindungen im Unternehmensnetzwerk

- Gefiltert nach ausgewählten WAN-Verbindungen, die ausgewählt wurden

- Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben

- Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite nicht genutzt haben

- Filtern nach WAN-Verbindungen, die kritische Werte erreicht haben (eine Bandbreitenauslastung, die mehr als 90 % der Bandbreitenkapazität der WAN-Verbindung beträgt)

- Gefiltert nach WAN-Verbindungstyp – Netzwerkstandortverbindungen, interregionale Verbindungen und Verbindungen innerhalb eines Standorts

- Gefiltert nach Netzwerkregion

#### <a name="applications"></a>Anwendungen

Bandwidth Utilization Analyzer verfügt über die folgenden zwei Anwendungen (Tools):

- **WanLinkLogCollector.exe** Dieses Tool ermöglicht es dem Benutzer, die erforderlichen Informationen einzugeben.

- **BandwidthUtilizationAnalyzer.xlsm** Ein Microsoft Excel Kalkulationstabellen-Softwarebericht wird automatisch von WanLinkLogCollector.exe gestartet. Diese Anwendung ermöglicht es dem Benutzer, Filter auf den Bericht anzuwenden, wie weiter unten in diesem Artikel gezeigt.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phasen der Verwendung von Bandwidth Utilization Analyzer

Bei Verwendung von Bandwidth Utilization Analyzer gibt es zwei Phasen:

- Erfassen von Protokollen, die mithilfe von WanLinkLogCollector.exe

- Anpassen von Berichten, die mit bandwidthUtilizationAnalyzer.xlsm ausgeführt werden

  > [!IMPORTANT]
  > Es wird dringend empfohlen, dass BandwidthUtilizationAnalyzer.xlsm nicht manuell von Endbenutzern gestartet wird.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Starten der Bandbreitenauslastungsanalyse

Starten Sie WanLinkLogCollector.exe an der Eingabeaufforderung oder mithilfe von Windows Explorer.

 **Verwenden von WanLinkLogCollector.exe**

Es gibt drei Schritte zur Verwendung von WanLinkLogCollector.exe:

1. **Protokollieren der Zeitachse** Bereitstellen der Zeitachse, für die der Bericht generiert werden muss

2. **Angeben der Dateiverzeichnisse** Angeben von Dateispeicherortinformationen

3. **Erfassen der Protokolle und Starten der Berichtsanzeige** Ausführen des Befehls zum Generieren des Berichts

#### <a name="step-1---log-the-timeline"></a>Schritt 1 : Protokollieren der Zeitachse

Die Protokollierung der Zeitachse ermöglicht es dem Toolbenutzer, Folgendes anzugeben, wie in der folgenden Abbildung dargestellt.

1. **Startdatum** Dies ist der Starttermin der Zeitachse, für die der Bericht generiert werden soll. beispiel: 1. August 2010.

2. **Enddatum** Dies ist das Enddatum der Zeitachse, für die der Bericht generiert werden soll. Beispiel: 30. September 2010.

     ![Start- und Endtermine in der Bandbreitenauslastung A.](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Schritt 2: Angeben der Dateiverzeichnisse

Die folgenden Dateiverzeichnisse können vom Benutzer wie dargestellt angegeben werden.

- **Speicherort der Serverprotokolldateien** Der Ordnerspeicherort, an dem Bandbreitenrichtlinienserverprotokolle gespeichert werden. Dies ist in der Regel in \<fileserver\>\\<Wahl von FE\>\AppServerFiles\PDP.

- **Temporärer Dateispeicherort** Der temporäre Dateispeicherort, an dem Zwischendateien gespeichert werden, während der Bericht generiert wird.

  ![Dateiverzeichnisse im Bandbreitenauslastungs-Anal.](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

  > [!NOTE]
  > Stellen Sie sicher, dass dem Toolbenutzer ausreichend Dateizugriff auf die Serverprotokolle und den temporären Dateispeicherordner zur Verfügung gestellt wird.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Schritt 3: Erfassen der Protokolle und Starten der Berichtsanzeige

Um die Protokolle zu sammeln und die Berichtsanzeige zu starten, klicken Sie auf **"Ausführen** ", wie unten gezeigt. In diesem Schritt werden die erforderlichen Daten gesammelt.

![Sammeln von Daten in der Bandbreitenauslastung Analy.](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Wenn die Eingabeüberprüfung erfolgreich ist, wird die unten angezeigte Meldung angezeigt.

![Protokolliert gesammelte Benachrichtigungen in der Bandbreiten-Utili.](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Klicken Sie auf **OK**. BandwidthUtilizationAnalyzer.xlsm wird automatisch gestartet. Folgen Sie den Anweisungen im Meldungsfeld. Ausführliche Informationen finden **Sie unter Verwenden von BandwidthUtilizationAnalyzer.xlsm** im nächsten Abschnitt.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Verwenden von BandwidthUtilizationAnalyzer.xlsm

1. Wenn BandwidthUtilizationAnalyzer.xlsm automatisch gestartet wird, klicken Sie auf **"Aktualisieren"** , wie unten dargestellt.

     ![BandwidthUtilizationAnalyzer.xlsm.](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Wenn ein Dateiordner geöffnet wird, wählen Sie consolidated.csv von dem Speicherort aus, der im Meldungsfeld angegeben ist, wie unten dargestellt. Außerdem wird der Speicherort als **C:\Temp** angezeigt.

     ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Klicken Sie auf **Importieren**.

4. Die grafische Darstellung wird automatisch generiert. Sie ist verfügbar, wenn der Arbeits-im-Hintergrund-Zeiger ausgeblendet wird.

     ![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Anwenden von Filtern auf die Berichtsansicht

Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden wie folgt beschrieben:

![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Namen** Filtern nach WAN-Verbindungen (der Filter befindet sich auf der rechten Seite des Diagramms). Das Präfix zeigt die folgenden Linktypen an: siehe vertikales (blaues) Feld:

   - **S-Website** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion

   - **Is Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten

   - **R Inter-Region** Die WAN-Verbindung zwischen zwei Netzwerkregionen

2. **Grenzwert überschritten** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung größer als die Bandbreitenkapazität ist

3. **Kritische Ebenen** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung 90 % oder mehr als die Bandbreitenkapazität erreicht hat

4. **Nicht ausgelastet** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25 % der Bandbreitenkapazität beträgt

5. **Linktyp** Filtern Sie nach den folgenden WAN-Verbindungstypen:

   - **Netzwerkstandorttyp**

   - **Standortübergreifender** Typ

   - **Interregionsverknüpfungstyp**

6. **Region** Filtern nach Netzwerkregion

Die folgenden Abbildungen zeigen die zuvor beschriebenen Filter.

Nach **Name filtern**. Wählen Sie die Liste der Links aus, die im Diagramm angezeigt werden müssen.

![Filtern nach Namen in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Nach **Grenzwert überschritten** filtern. Wählen Sie **"True"** aus, um den Filter zu erzwingen.

![Filtern nach überschrittener Grenze.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Nach **kritischen Ebenen filtern**. Wählen Sie **"True"** aus, um den Filter zu erzwingen.

![Filtern nach kritischen Ebenen.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtern nach **"Unter" verwendet**. Wählen Sie **"True"** aus, um den Filter zu erzwingen.

![Filtern nach "Unter verwendet".](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Nach **Linktyp** filtern. Wählen Sie den Typ oder die Typen aus, die angezeigt werden sollen.

![Filtern nach Linktyp.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Nach **Region** filtern. Wählen Sie eine Liste der Regionen aus, deren Verknüpfungen angezeigt werden müssen.

![Filtern nach Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Anforderungen

- Die .NET Framework 3.5

- Microsoft Excel 2010 oder Excel 2007

### <a name="summary"></a>Zusammenfassung

Bandwidth Utilization Analyzer wird verwendet, um die Audiobandbreitenauslastung für UC-Datenverkehr über das Netzwerk zu zeichnen. Dieses Tool kann auch verwendet werden, um die Auslastung der Videobandbreite im Netzwerk zu melden.

## <a name="call-parkometer"></a>Parkometer für Anrufe
<a name="callpark"> </a>

Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Orbitdatenbank für das Parken von Anrufen bietet.

### <a name="description"></a>Beschreibung

Call Parkometer ist ein Tool, um derzeit geparkte Anrufe nachzuverfolgen. Außerdem werden Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS) erfasst. Dieses Befehlszeilentool bietet lese- und schreibgeschützten Zugriff auf den CPS-Orbit SQL Server Datenbank von einem lokalen oder remote verbundenen Computer aus.

Alle Optionen schließen sich gegenseitig aus. Die Befehlszeilensyntax lautet wie folgt:

- **-o** Parameter – Listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.

- **-n-Parameter** – Listet alle derzeit verwendeten Orbits in diesem Pool auf. Die angezeigten Informationen sind wie folgt:

  - SIP Uniform Resource Identifier (URI) des Parkee- und Parkers.

  - Hostname des CPS, in dem der Anruf geparkt wird.

  - Zeitstempel des Zeitpunkts, zu dem der Anruf geparkt wurde.

- **-f-Parameter** – Listet die Anzahl der derzeit freien Orbits im Pool auf.

- **-r \<n\>** - Listet die \<n\> letzten geparkten Anrufe auf. Die angezeigten Informationen sind wie folgt:

  - SIP-URI parken.

  - Parker SIP-URI.

  - Hostname des CPS, in dem der Anruf geparkt wurde.

  - Zeitstempel, wann der Anruf abgerufen oder abgebrochen wurde.

- **-t\<n\>** parameter - testet die Reservierung eines Orbits in der Datenbank, um die Zufälligkeit der zugewiesenen Orbitnummern anzuzeigen.

### <a name="output"></a>Ausgabe

Abhängig von den Eingabeparametern, die an einer Eingabeaufforderung angegeben werden, zeigt Call Parkometer die folgende Ausgabe an:

- Alle Orbitbereiche, die für diesen Pool konfiguriert sind

- Derzeit geparkte Anrufe

- Anzahl der freien (verfügbaren) Orbits

- Kürzlich geparkte Anrufe

- Reservierte Orbits zum Testen von Werten für die einheitliche und zufällige Umlaufbahn

### <a name="purpose"></a>Zweck

Der Zweck des CPS-Tools besteht darin, den Befehlszeilenzugriff auf die CPS-Datenbank bereitzustellen. Der Administrator kann die CPS-Verwendung anzeigen und die Anzahl der Orbits ermitteln, die einem Pool zugewiesen sind.

### <a name="requirements"></a>Anforderungen

Es gibt keine Anforderungen, wenn dieses Tool auf demselben Computer ausgeführt wird, auf dem CPS ausgeführt wird. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von Skype for Business Server 2015 verwendete SQL Server-Datenbank so konfiguriert sein, dass der Remotezugriff zulässig ist. Call Parkometer muss mit einer SQL Server Datenbankverbindungszeichenfolge konfiguriert sein, um eine Verbindung mit dem SQL Server des Pools herzustellen. Diese SQL Server Datenbankverbindungszeichenfolge wird in der Konfigurationsdatei **parkometer.exe.config** definiert. Sie muss sich im selben Verzeichnis befinden, in dem sich parkometer.exe befindet. Die folgende XML-Datei ist ein Beispiel für eine parkometer.exe.config. Die parameter, die konfiguriert werden müssen, sind Benutzername (z. B. mydomain\Administrator), Kennwort (z. B. mypassword) und Hostname (z. B. myserver).

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

Bereitgestellte Orbitbereiche: Der Parameter "-o" listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind( siehe

![Orbitbereiche im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Derzeit geparkte Anrufe: Der Parameter "-n" listet alle derzeit verwendeten Orbits in diesem Pool auf, wie gezeigt.

![Derzeit geparkte Anrufe im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Anzahl der freien Orbits: Der Parameter -f listet die Anzahl der derzeit freien Orbits im Pool auf, wie gezeigt.

![Kostenlose Orbits im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Zuletzt geparkte Anrufe: Der Parameter "-r \<n\> " listet die \<n\> zuletzt geparkten Anrufe wie dargestellt auf.

![Kürzlich geparkte Anrufe im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Orbitreservierung testen: Der Parameter -t \<n\> testet die Reservierung eines Orbits in der Datenbank wie gezeigt

![Testen Sie Orbitreservierungen im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Zusammenfassung

Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Call Park Server bereitstellt.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Beschreibung

DBAnalyze ist ein Befehlszeilentool, mit dem Administratoren Analyseberichte zu den Skype for Business Server 2015-Datenbanken sammeln können. DBAnalyze verfügt über die folgenden Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:

- **Diagnosemodus** Erstellt einen Bericht, der Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten- und Protokolldateigrößen, die letzte Back-up-Zeit, die Kontaktverteilung zwischen Servern, auf denen Microsoft Office Communications Server ausgeführt wird, die durchschnittliche Anzahl von Berechtigungen, Kontakten, Containern, Abonnements, Publikationen, Endpunkten pro Benutzer, alle nicht verwalteten Benutzer, Benutzer, die nicht weitergeleitet werden können, enthält.  die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, geplante Konferenzen, aktive Konferenzen und die Datenbankversion.

    > [!NOTE]
    > Die Ausführung des Diagnosemodus kann sich auf die Serverleistung auswirken.

- **Benutzerdatenmodus** Meldet Kontakt-, Container-, Abonnement-, Publikations-, Berechtigungs- und Kontaktgruppendaten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in ihren Kontakt- und Berechtigungslisten haben. Dieser Modus meldet auch Zusammenfassungsdaten für Konferenzen, die ein Benutzer organisiert oder zu denen er eingeladen wird.

- **Konferenzmodus** Meldet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Zeitplandetails für die Konferenz, der Liste der eingeladenen Teilnehmer, der Liste der für die Konferenz zulässigen Medientypen, aktiver MCUs (Multipoint Control Units), der Liste der aktiven Teilnehmer und des Signalzustands jedes Teilnehmers.

- **Decodieren der Besprechungs-ID** Decodiert eine PSTN-Besprechungs-ID (Public Switched Telephone Network), die durch den Switch **/pstnid** angegeben wird, aber keine Verbindung mit dem Back-End herstellt, um detaillierte Informationen zu erhalten.

- **Konferenz auflösen** Decodiert eine PSTN-Besprechungs-ID, die von der Option **/pstnid** angegeben wird, und zeigt Informationen zu der Konferenz an, die durch die ID angegeben wird.

- **MCUs-Modus** Meldet die ID, den Medientyp, die URL, den Taktstatus, die Konferenzlast und die Teilnehmerlast für jede MCU im Pool.

- **Datenträgerfragmentierungsmodus** Zeigt den Fragmentierungsstatus aller Datenträger an.

Dieses Tool kann verwendet werden, um verschiedene Probleme zu diagnostizieren oder Administratoren bei der Kapazitätsplanung zu unterstützen. Wenn beispielsweise die meisten Benutzer, die auf Server A verwaltet werden, Benutzer auswählen, die auf Server B als Kontakte verwaltet werden, kann der Administrator die Benutzer auf Server A auf Server B verschieben, um den serverübergreifenden Datenverkehr zu reduzieren.

### <a name="output"></a>Ausgabe

Dieses Tool gibt vordefinierte Berichte zur Skype for Business Server 2015-Datenbank aus. **Pfad**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Zweck

Um Dbanalyze.exe zu installieren, kopieren Sie es in einen lokalen Ordner, und führen Sie dann das Tool aus. Führen Sie den folgenden Befehl über die Befehlszeile aus, um das Tool zu verwenden. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Die Beschreibungen für die Befehlszeilenoptionen sind unten dargestellt.

![Befehlszeilenoptionen für Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Anforderungen

 **Computer** DBAnalyze kann nur von einem in die Domäne eingebundenen Computer ausgeführt werden, auf dem Skype for Business Server 2015 installiert ist.

 **Netzwerk** Der Computer sollte eine Verbindung mit der Back-End-Datenbank herstellen können.

 **Software** Skype for Business Server 2015-Softwarekomponenten müssen installiert werden, bevor DBAnalyze ausgeführt wird.

 **Benutzer** Die folgende Tabelle zeigt die Administratoren, die über die erforderlichen Berechtigungen für den Zugriff auf Skype for Business Server 2015-Datenbanken verfügen.

![Berechtigungstabelle für Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Für den **Modus "/report:disk** " ist ein lokales Administratorkonto erforderlich.

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

Das Resource Kit-Tool "ImportStorageServiceData" ermöglicht das erneute Importieren von Warteschlangen- und Endpunktdaten, die aus dem Storage-Dienst (LYSS) wieder in den Storage-Dienst geleert wurden.

### <a name="description"></a>Beschreibung

Die aus dem Storage Dienst geleerten Daten könnten automatisch (periodisch) basierend auf dem Status des Warteschlangenelements oder der Datenbankgröße gewesen sein. Dies könnte aufgrund des manuellen Aufrufs des Poolfailover-Cmdlets oder des Cmdlets "StorageServiceFullFlush" (das vom Poolfailover-Cmdlet aufgerufen wird) geschehen. Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn eine der LYSS-Datenbankgrößen (Storage Service) auf den Front-Ends über der normalen Ebene liegt, da dies wahrscheinlich dazu führt, dass mehr Daten zurück exportiert werden. Darüber hinaus sollten alle Probleme, die zu Fehlern beigetragen haben könnten, die dazu geführt haben, dass die Storage Dienstwarteschlange vergrößert wurde, zuerst behoben werden (z. B. Exchange Endpunktfehler, Netzwerkprobleme oder andere Probleme).

 **Szenario 1:** Während des Poolfailovers können Dateien für jedes Front-End aus dem Speicherdienst gelöscht werden. Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.

 **Szenario 2:** Daten werden jeden Tag automatisch oder als Reaktion auf Storage Dienstdatenbank geleert, die bestimmte Größenschwellenwerte überschreitet (z. B. 60 %, 80 %, 90 % voll). Diese automatisch geleerten Daten sollten vom Administrator routinemäßig erneut importiert werden. Wenn in der obigen Situation das Überwachungs-SCOM-Paket nicht bereitgestellt wird, gibt es Ereignisse für Skype for Business Server Storage-Dienst in Bezug auf Daten, die aus dem Storage-Dienst geleert werden. Ereignis-IDs von 32075 (vollständiger Leervorgang wird gestartet), 32076 (vollständige Spülung wurde abgeschlossen), 32082 (Leerung der Wartungsebene gestartet), 32083 (Wartungsebene leer abgeschlossen), 32089 (Leerung aufgrund des Ausfüllens der Datenbank). Beachten Sie, dass diese Ereignis-IDs der RTM-Version entsprechen. Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien gelöscht wurden. Diese Daten sollten routinemäßig mit diesem Tool wieder importiert werden, z. B. einmal pro Woche.

Wenn für die Onlinedienstversion das SCOM-Paket zur Integritätsüberwachung für Skype for Business Server bereitgestellt wird, werden möglicherweise neue Warnungen ausgelöst, die den Administrator auffordern, die geleerten Daten wieder in Storage Service zu importieren. Das Ereignisprotokoll auf dem Front-End Server, der die Warnung ausgelöst hat, enthält ein entsprechendes Ereignis. Das Ereignis gibt eine Beschreibung des übergeordneten Pfads, unter dem sich die geleerten Datendateien befinden, und der Anzahl der Dateien, die die Warnungskriterien erfüllen. Die Benachrichtigungskriterien lauten, dass sich unter dem jeweiligen übergeordneten Pfad X oder mehr Dateien befinden, die mindestens Y Tage alt sind (wobei X und Y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei überschrieben werden können).) Im Folgenden werden zwei Beispiele für Ereignisse gezeigt, die die Integritätswarnung auslösen können, wobei der Unterschied der übergeordnete Pfad ist. Eine Möglichkeit ist die Dateifreigabe des Webdiensts, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist. (z. B. c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService). Der Administrator führt dann dieses Reskit-Tool aus.

Dieses Tool erhöht die CPU- und E/A-Auslastung für das Front-End, auf dem es ausgeführt wird, und andere Front-Ends, in der Situation, dass die Daten nicht im Besitz des Front-End sind, auf dem das Tool ausgeführt wird. Es wird empfohlen, dieses Tool auszuführen, wenn Front-Ends nicht unter hoher CPU- und E/A-Auslastung stehen, z. B. außerhalb von Spitzenzeiten. Zweitens kann dieses Tool 2 bis 3 Minuten dauern, um eine Datendatei zu importieren. Beachten Sie dies bei der Schätzung, wie lange das Tool ausgeführt wird. Die ausführliche Protokolldatei, die vom Tool generiert wird, wird standardmäßig in der datei-Store angezeigt. Löschen Sie sie, wenn keine Fehler gemeldet werden, da die Protokolldatei zehn MB oder mehr sein kann.

![Beispiel für Storage Server-Ereignisprotokollereignisse.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Anforderungen

Installieren Sie die Skype for Business Server 2015 Resource Kit-Tools. Das Tool wird auf Computern ausgeführt, auf denen Skype for Business Server und Skype for Business Server Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End Server im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal-Datenbank** installiert ist. Diese Datenbank wird vom Tool verwendet, um den Speicherort der WEBSERVICE-Dateifreigabe für den Pool abzurufen. Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools zuerst Windows PowerShell Remoting mit **Enable-PSRemoting** auf jedem Front-End-Server und dem Computer aktivieren, auf dem das Tool ausgeführt wird. Andernfalls schlagen remote Windows PowerShell Befehle dieses Tools fehl. Windows PowerShell Remoting kann nach abschluss auf allen Front-End Servern im Pool deaktiviert werden. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über Lese-/Schreibberechtigungen für die Webservice-Dateifreigabe für den Pool verfügen, in dem sie dieses Tool ausführen. Andernfalls schlägt das Tool mit E/A-Berechtigungsfehlern fehl.

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

Das LCSSync-Tool hilft bei der Bereitstellung Skype for Business Server 2015-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen. Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzergesamtstrukturen als Active Directory Domain Services Kontaktobjekt mit einer zentralen Gesamtstruktur zu synchronisieren, in der Skype for Business Server 2015 installiert ist.

### <a name="description"></a>Beschreibung

 LCSSync verwendet die synchronisierten Active Directory Domain Services Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzern Skype for Business Server zu ermöglichen. Um einmaliges Anmelden bereitzustellen, muss das primäre Benutzerkonto dem Active Directory Domain Services Kontaktobjekt in der zentralen Gesamtstruktur für Skype for Business Server 2015 zugeordnet werden. Dieses Tool hilft bei der Durchführung dieser Zuordnung. Dieses Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents im Microsoft Identity Integration Server bereit.

### <a name="summary"></a>Zusammenfassung

Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015 in einer Umgebung mit mehreren Gesamtstrukturen.

## <a name="lookup-user-console"></a>Benutzerkonsole nachschlagen
<a name="LUC"> </a>

Das LookupUserConsole-Tool zeigt interne Skype for Business Server Routinginformationen zu bestimmten Benutzern an. Diese Informationen sind möglicherweise hilfreich für die persönliche Unterstützung von Microsoft bei der Diagnose von Bereitstellungs- und Routingproblemen.

### <a name="description"></a>Beschreibung

 Beim Ausführen LookupUserConsole.exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert und versucht, interne Skype for Business Server routingbezogene Informationen anzuzeigen. Geben Sie **exit ein** , um das LookupUserConsole-Tool zu beenden.

### <a name="requirements"></a>Anforderungen

Installieren Sie das Skype for Business Server 2015 Resource Kit. Das Tool wird auf Computern ausgeführt, auf denen Skype for Business Server installiert ist.

### <a name="examples"></a>Beispiele

C:\Programme\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe

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

Das MSTurnPing-Tool ermöglicht es einem Administrator von Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen audio/video-Edge, Audio/Video-Authentifizierungsdienste und die Server ausgeführt werden, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

### <a name="description"></a>Beschreibung

Das MSTurnPing-Tool ermöglicht es einem Administrator von Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen audio/video-Edge, Audio/Video-Authentifizierungsdienste und die Server ausgeführt werden, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

Das Tool ermöglicht es dem Administrator, die folgenden Tests auszuführen:

1. A/V-Edgeservertest: Das Tool führt Tests für alle A/V-Edgeserver in der Topologie durch:

   - Überprüfen, ob der Skype for Business Server Audio/Video-Authentifizierungsdienst gestartet wurde und die richtigen Anmeldeinformationen ausstellen kann.

   - Überprüfen, ob der Skype for Business Server Audio-/Video-Edgedienst gestartet wurde und die Ressourcen am externen Edge erfolgreich zuordnen können.

2. Bandbreitenrichtliniendiensttest: Das Tool führt Tests für alle Server durch, auf denen die Bandbreitenrichtliniendienste in der Topologie ausgeführt werden, indem Folgendes ausgeführt wird:

   - Überprüfen, ob der Skype for Business Server Bandbreitenrichtliniendienst (Authentifizierung) gestartet wurde und die richtigen Anmeldeinformationen ausstellen kann.

   - Überprüfen, ob der Skype for Business Server Bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreitenüberprüfung erfolgreich durchführen kann.

Dieses Tool muss von einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist.

### <a name="output"></a>Ausgabe

Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.

- Wenn der **AudioVideoEdgeServer-Test** ausgeführt wird, werden die folgenden Tools ausgegeben:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Audio/Video Edge-Dienst in der Topologie bereitstellen

- Wenn der **BandwidthPolicyServer-Test** ausgeführt wird, werden die folgenden Tools ausgegeben:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Bandwidth Policy Service (Core) in der Topologie bereitstellen

### <a name="requirements"></a>Anforderungen

- Dieses Tool muss von einem Computer ausgeführt werden, der sich in der Topologie befindet und über den lokalen Speicher verfügt.

- Das Tool muss als Administrator ausgeführt werden, der Zugriff auf den lokalen Store hat.

### <a name="examples"></a>Beispiele

Es folgt ein Beispiel für die Tooleingabe.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio-/Video- und Bandbreitenrichtliniendienste ausgeführt werden.

## <a name="network-configuration-viewer"></a>Netzwerkkonfigurations-Viewer
<a name="NCV"> </a>

Network Configuration Viewer kann von Skype for Business Server 2015-Kommunikationssoftwareadministratoren verwendet werden, um die Anrufsteuerungs-Netzwerktopologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echtzeitkommunikationssitzungen wie Sprach- oder Videoanrufe basierend auf der angegebenen Bandbreitenkapazität zu ermöglichen. Skype for Business Server 2015-Administratoren definieren Anrufsteuerungsrichtlinien, die von den Bandbreitenrichtliniendiensten erzwungen werden, die mit Skype for Business Server 2015 installiert sind.

### <a name="description"></a>Beschreibung

Der Netzwerkkonfigurations-Viewer (NetworkConfigurationViewer.exe) ermöglicht Es Administratoren, die folgenden Aufgaben auszuführen:

- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format.

- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem grafischen Format.

- Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger.

- Speichern und Speichern des Cac-Netzwerktopologiediagramms im JPG- oder BMP-Format.

- Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie.

- Anzeigen der CAC-Netzwerktopologie in einem Strukturansichtsstil.

- Definieren sie benutzerdefinierte Connectors für CAC-Netzwerktopologieverbindungen (z. B. Standort-zu-Region-, Regions-zu-Region- und Standort-zu-Standort-Verknüpfungen).

- Anzeigen von Standortinformationen zur CAC-Netzwerktopologie, Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen.

### <a name="purpose"></a>Zweck

Anzeigen von Netzwerktopologielinks für die Unternehmens-CAC auf einer grafischen Benutzeroberfläche.

### <a name="examples"></a>Beispiele

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format**: Skype for Business Server 2015-Administratoren können die Konfiguration der CAC-Netzwerktopologie auf einem beliebigen Skype for Business Server 2015-Computer mithilfe der **Laden Sie die Netzwerkkonfigurationsoption** herunter, wie in der abbildung unten dargestellt. Das Tool kann eine solche Konfiguration nicht herunterladen oder anzeigen, wenn es auf einem Computer bereitgestellt wird, der keine Verbindung mit dem Konfigurationsspeicher für Skype for Business Server 2015 hat.

![Die Netzwerkkonfiguration wird heruntergeladen.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien-Serverprotokolldatei in einem grafischen Format:** Skype for Business Server 2015 Bandwidth Policy-Server speichert die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Dateifreigabespeicherort Skype for Business Server 2015. Skype for Business Server 2015-Administratoren können eine solche Datei mithilfe der Option "**Netzwerkkonfiguration** öffnen" wie unten dargestellt in einem grafischen Format anzeigen.

![Öffnen einer Bandbreitenrichtlinienserver-Protokolldatei.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger: Skype for Business Server 2015-Administratoren können die Konfigurationsdatei für die CAC-Netzwerktopologie mithilfe der Option "**Kopie der Netzwerkkonfiguration speichern**" wie unten dargestellt in einem XML-Format speichern. Die gespeicherte Konfigurationsdatei kann dann offline für grafische Anzeigezwecke verwendet werden.

![Speichern der Netzwerkkonfiguration als XML-Datei.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Speichern und Store Cac-Netzwerktopologiediagramm im JPG- oder BMP-Format: Skype for Business Server 2015-Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG- und BMP-Dateiformate) speichern, indem sie das **Diagramm "Netzwerkkonfiguration speichern" als Bildoption** verwenden, wie unten dargestellt.

![Speichern der Netzwerkkonfiguration als Bild.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:</strong>Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten wie Netzwerkregionen, Netzwerkstandorte, Bandbreitenprofile und IP-Adressen des Standortssubnetz in einem Textformat anzeigen, indem sie die Option "Netzwerkkonfigurationsdaten anzeigen" wie unten dargestellt verwenden.

![Anzeigen von Netzwerkkonfigurationsdaten.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Anzeigen der CAC-Netzwerktopologie in einem Strukturansichtsstil:** Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten in einer grafischen Strukturansicht anzeigen, indem sie die Systemsteuerung auf der linken Seite des Toolfensters verwenden, wie unten dargestellt.

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definieren Sie benutzerdefinierte Connectors für CAC-Netzwerktopologieverbindungen (z. B. Standort-zu-Region-, Regions-zu-Region- und Standort-zu-Standort-Verbindungen):** Skype for Business Server 2015-Administratoren können benutzerdefinierte grafische Connectors für WAN-Verbindungen für die CAC-Netzwerkkonfiguration definieren, indem sie die option Einstellungen wie unten dargestellt verwenden. Auf diese Weise kann zwischen verschiedenen Arten von Netzwerkverbindungen unterschieden werden, die in der Netzwerkkonfiguration bereitgestellt werden.

![Werkzeuge.](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Anzeigen von Standortinformationen, Regionsinformationen und bereitgestellten Bandbreitenrichtlinien für die Cac-Netzwerktopologie:** Skype for Business Server 2015-Administratoren können verwandte Informationen zur Cac-Netzwerkregion, Standortinformationen und Informationen zur Bereitstellung der Anrufsteuerungsbandbreite mithilfe der unten gezeigten Optionen anzeigen. (Klicken Sie z. B. auf **"Informationen** " in einer Netzwerkregion oder einem Netzwerkstandortobjekt.)

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die die CAC-Netzwerktopologie für ihre Bereitstellung in einem grafischen Format anzeigen möchten.

## <a name="response-group-agent-live"></a>Reaktionsgruppen-Agent-Live
<a name="RGAL"> </a>

Die Reaktionsgruppenanwendung bietet Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zuzugreifen. Leider ist außerhalb der Anwendung keine grafische Ansicht dieser Daten verfügbar. Der Reaktionsgruppen-Agent Live Resource Kit-Tool löst dieses Problem, indem er eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, erweitert durch Echtzeit-Skype for Business Kommunikationssoftwareinformationen wie das Vorhandensein anderer Agents.

### <a name="description"></a>Beschreibung

Response Group Agent Live ist eine Windows Anwendung, die Anmelde- und Abmeldefunktionen sowie einige Echtzeitinformationen (z. B. Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) an Reaktionsgruppen-Agents bereitstellt. Es soll eine erweiterte Version der Seite "Agent-Gruppen" sein (auf die von Skype for Business zugegriffen werden kann.

### <a name="purpose"></a>Zweck

Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschlange und leitet sie dann an Agentgruppen weiter. Um fundierte Entscheidungen darüber zu treffen, welche Anrufe an den Dienst getätigt werden sollen, können Agents auf Echtzeitinformationen über ihre Agentgruppen zugreifen, z. B. welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, auf die zunächst nur über den Reaktionsgruppendienst zugegriffen werden kann, werden vom Reaktionsgruppen-Agent auf intuitive Weise Live zur Verfügung gestellt.

#### <a name="features"></a>Features

Der Reaktionsgruppen-Agent Live-Tool basiert auf dem Reaktionsgruppendienst und dem Skype for Business Server 2015 SDK. Sie bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die über den Reaktionsgruppendienst verfügbar sind (z. B. Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).

Die folgende Abbildung veranschaulicht die Hauptschnittstelle der Reaktionsgruppen-Agent-Live.

![Der Reaktionsgruppen-Agent Live Tool.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Die folgenden drei Hauptfunktionen sind für Agents im Reaktionsgruppen-Agent Live verfügbar:

- **Anmelden/Abmelden:** Im Gegensatz zur Seite "Agent-Gruppen" (auf die von Skype for Business Server 2015 zugegriffen werden kann) ermöglicht der Reaktionsgruppen-Agent Live nur Agents, sich gleichzeitig bei allen Agentgruppen anzumelden oder abzumelden. Diese Anwendung bietet drei schnelle Möglichkeiten für Agents, sich anzumelden oder abzumelden:

  - Klicken Sie in der Anwendung auf die Schaltflächen "Anmelden/Abmelden" (grün und rot).

  - Klicken Sie mit der rechten Maustaste auf das Taskleistensymbol, und wählen Sie "Anmelden" oder "Abmelden" aus.

  - Verwenden konfigurierbarer Tastenkombinationen.

- **Gruppenmitgliedschaft:** Wenn eine Agentgruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an. Wenn Skype for Business Server 2015 auf demselben Computer wie diese Anwendung ausgeführt wird, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt. Agents können eine Chatnachricht senden oder andere Agents direkt von dort aus anrufen.

- **Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agent-Gruppen. Die Aktualisierungshäufigkeit beträgt eine Minute. Wenn ein Anruf von einer Reaktionsgruppe angenommen wird, wird neben dem Gruppennamen ein visueller Indikator mit der aktuellen Anzahl von Anrufen in der Warteschlange hinzugefügt. Wenn Sie den Mauszeiger auf eine Gruppe zeigen, wird auch die längste Wartezeit angezeigt.

### <a name="requirements"></a>Anforderungen

Response Group Agent Live erfordert die .NET Framework 4.0. Um die Anwesenheits- und Visitenkartenfeatures nutzen zu können, müssen Skype for Business lokal installiert (und ausgeführt) werden.

#### <a name="configuration"></a>Konfiguration

Response Group Agent Live können mithilfe des Dialogfelds "Optionen" in der Anwendung an einzelne Einstellungen angepasst werden. Darüber hinaus kann der Administrator die Standardhostadresse definieren, indem er die defaultHostAddress-Eigenschaft der RGAgentLive.exe.config Datei direkt bearbeitet.

Die folgende Abbildung veranschaulicht das Dialogfeld "Optionen", mit dem Agents die Hostadresse und Tastenkombinationen konfigurieren können. Auf dieses Dialogfeld wird zugegriffen, indem Sie oben rechts auf der Hauptschnittstelle auf die Schaltfläche "Optionen" klicken.

![Das Dialogfeld "Reaktionsgruppen-Agent Live Optionen".](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Die folgenden drei verschiedenen Einstellungen können im Reaktionsgruppen-Agent Live Konfiguration angepasst werden:

- Hostadresse: Dies ist in der Regel der Webpool-FQDN, der zum Home-Pool des Agents gehört. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads nach dem Host).

- Tastenkombinationen: Die genauen Tastenkombinationen für die Anmeldung/Abmeldung können angepasst werden. Die einzige Einschränkung besteht darin, dass beide Tastenkombinationen die Taste "Windows Logo" enthalten müssen (zusätzlich zu mindestens einer anderen Taste).

- Beginnen Sie mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch mit Windows beginnt.

### <a name="examples"></a>Beispiele

Die folgende Abbildung zeigt, wie Sie eine Chatnachricht an einen anderen Agent durch Klicken mit der rechten Maustaste auf den Kontakt im rechten Bereich anrufen oder senden.

![Tätigen eines Anrufs oder Senden einer Chatnachricht.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

Die folgende Abbildung zeigt, wie der Reaktionsgruppen-Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife und die längste Wartezeit unter allen diesen eingehenden Anrufen anzeigt.

![Anzeigen von Warteschlangeninformationen.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Zusammenfassung

Schnelles Anmelden und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Reaktionsgruppen-Agent-Features, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind. Mit dem Tool Response Group Agent Live Resource Kit können Skype for Business Server 2015-Administratoren ihren Agents eine Windows Anwendung bereitstellen, mit der sie Aufgaben schneller und grafisch ausführen können.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (secondary extension feature activation) ist ein Befehlszeilentool, mit dem Skype for Business Server 2015-Kommunikationssoftwareadministratoren und Helpdesk-Agents Stellvertretungs-, Anrufweiterleitungs-, gleichzeitiges Klingeln, Teamanrufeinstellungen und Gruppenanrufannahme im Namen eines benutzers Skype for Business Server 2015 konfigurieren können. Mit dem Tool können Administratoren auch die Anrufweiterleitungseinstellungen abfragen, die für einen bestimmten Benutzer veröffentlicht werden. Mit dem SEFAUtil-Tool kann der Administrator die Anrufweiterleitung aktivieren/deaktivieren/ändern oder gleichzeitig im Namen des Benutzers klingeln. Der Administrator kann das Ziel (in Form eines SIP-URI) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde. Dieses Tool ermöglicht Administratoren auch das Hinzufügen oder Entfernen von Stellvertretungen oder Teamanrufgruppenmitgliedern im Namen des Benutzers. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.

SEFAUtil (Secondary Extension Feature Activation) ermöglicht Skype for Business Server 2015-Administratoren und Helpdesk-Agents das Konfigurieren von Stellvertretungs-Klingeln, Anrufweiterleitung, gleichzeitigem Klingeln, Teamanrufeinstellungen und Gruppenanrufannahme im Namen eines Benutzers von Skype for Business Server 2015. Mit diesem Tool können Administratoren auch die Anrufweiterleitungseinstellungen abfragen, die für einen bestimmten Benutzer veröffentlicht wurden.

### <a name="description"></a>Beschreibung

Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool. Es gibt keine unterstützende grafische Benutzeroberfläche. Dieses Tool basiert auf der verwalteten Microsoft Unified Communications-API (UCMA) 3.0. Die Features in diesem Tool ermöglichen Administratoren und Helpdesk-Agents Folgendes:

- Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Delegierung, gleichzeitiges Klingeln, Teamanruf und Gruppenanrufannahme)

- Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellung (einschließlich Ziel- und Zeitgeber ohne Antwort)

- Sofortige Konfigurationen für die Anrufweiterleitung aktivieren/deaktivieren/ändern

- Delegierungseinstellungen aktivieren/deaktivieren/ändern

- Aktivieren/Deaktivieren/Ändern von Teamanrufgruppeneinstellungen

    > [!NOTE]
    > Neu im SEFAUtil-Tool Skype for Business Server 2015

- Aktivieren/Deaktivieren/Ändern von Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)

    > [!NOTE]
    > Neu im SEFAUtil-Tool Skype for Business Server 2015

- Aktivieren/Deaktivieren/Ändern der Einstellungen für die Gruppenanrufannahme

    > [!CAUTION]
    > Neu im SEFAUtil-Tool Skype for Business Server 2015

Dieses Tool hat die folgenden Einschränkungen:

- Wird nur für Benutzer unterstützt, die in einem Skype for Business Server-Pool verwaltet werden

- Die Massenbearbeitung der Anrufweiterleitungseinstellungen für mehrere Benutzer wird nicht unterstützt.

### <a name="output"></a>Ausgabe

Die aktuelle Version dieses Tools stellt die Ausgabe nur im Eingabeaufforderungsfenster bereit. Ausführliche Informationen finden Sie im Abschnitt "Beispiele" weiter unten in diesem Dokument.

### <a name="purpose"></a>Zweck

Es folgen einige der wichtigsten Szenarien, in denen dieses Tool verwendet werden kann:

- Bob ist leitender Angestellter und wurde in Skype for Business Server Telefonie umgezogen. Er ist delegiert in seinem bestehenden PBX-System. Im Rahmen der Umstellung auf Skype for Business Server 2015 kann der Administrator Bobs Routing so konfigurieren, dass seine bereits vorhandene Delegierungskonfiguration widergespiegelt wird.

- Alice ist auf Reisen und erkennt, dass sie einen wichtigen Anruf von einem ihrer Kunden erwartet. Sie befindet sich jedoch in einem Hotel und hat keinen Zugang zu einem Computer. Sie ruft den Helpdesk an und fordert sie auf, alle Anrufe an ihre Geschäftliche Nummer an ihre Mobiltelefonnummer weiterzuleiten. Das Helpdesk-Personal kann die Konfiguration in ihrem Auftrag durchführen.

- Joes Rufe an seine Rufnummer gehen zu seiner mobilen Voicemail, wann immer er bei der Arbeit ist; An den meisten anderen Standorten scheint dies jedoch ordnungsgemäß zu funktionieren. Der Helpdesktechniker kann Joes Routingkonfiguration anzeigen und stellt fest, dass Joe gleichzeitiges Klingeln auf seinem Mobiltelefon konfiguriert hat. Der Techniker fragt Joe nach der mobilen Abdeckung in seinem Büro und kann feststellen, dass die Regel zum gleichzeitigen Klingeln das ist, was dazu führt, dass die Anrufe an Joes mobile Voicemail gehen, wenn seine Netzwerkabdeckung schlecht ist.

- Mike ist ein neuer Mitarbeiter bei Contoso und tritt einem neuen Team bei, für das alle Mitglieder für Teamanrufe konfiguriert sind. Wenn er für Skype for Business Server 2015 aktiviert ist, kann der Administrator seine Teamanrufgruppeneinstellungen so festlegen, dass alle seine neuen Teammitglieder einbezogen werden. Darüber hinaus fügt der Administrator Mike als Teamanrufgruppenmitglied für jedes Mitglied in seinem Team hinzu.

- Eine Kundendienstpraxis in der Personalabteilung von Contoso besteht darin, allen Anrufern seit dem ersten Anruf persönlichen Service zu bieten. Angesichts der Tatsache, dass alle Mitglieder der Abteilung sehr nah beieinander sitzen, ist es für das Team störend, alle Telefone gleichzeitig mit Teamanrufen klingeln zu lassen. Um den besten Service bereitzustellen, ohne die Teammitglieder zu stören, nutzt der Skype for Business Server 2015-Administrator die Funktion "Gruppenanrufannahme". Der Administrator fügt alle Abteilungsmitglieder zu einer Pickup-Gruppe hinzu und teilt der Abteilung die Gruppennummer für die Abholung mit. Wenn Samantha von ihrem Schreibtisch abwesend ist, bemerkt Joe, wie ihr Telefon klingelt und er fährt fort, den Anruf von seinem Schreibtisch aus zu beantworten.

### <a name="requirements"></a>Anforderungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. UCMA 3.0 muss auf diesem Computer installiert sein. Zum Ausführen des Tools muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool

1. Das SEFAUTil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Bei Bedarf kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die Skype for Business Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:

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
    > Pool-FQDN: Der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hostet (in der Regel ein Skype for Business Front-End-Server > oder Pool).
    > FQDN der Poolregistrierungsstelle: Der FQDN des Skype for Business Front-End-Servers oder -Pools, der diesem Anwendungspool zugeordnet ist.
    > Poolwebsite: Die Website-ID des Standorts, auf dem dieser Pool verwaltet wird.

3. Die Topologieänderungen müssen aktiviert werden. Das Aktivieren der Topologieänderungen kann über die Skype for Business Server-Verwaltungsshell erfolgen, indem Sie das folgende Cmdlet ausführen:

   ```powershell
   Enable-CsToplogy
   ```

4. Installieren Sie bei Bedarf die Skype for Business Server 2015 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).

5. Stellen Sie sicher, dass SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool über eine Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. Das Tool befindet sich standardmäßig in: "...\Programme\Skype for Business Server 2015\Reskit". Verwenden Sie den folgenden Befehl, um die Anrufweiterleitungseinstellungen eines Benutzers anzuzeigen:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.

#### <a name="group-call-pickup"></a>Gruppenanrufannahme

Die Gruppenanrufannahme erfordert eine zusätzliche Konfiguration in Skype for Business Server 2015, damit die Funktion vollständig aktiviert ist. Bevor Sie Benutzern Pickup-Gruppen zuweisen, finden Sie in der Produktdokumentation zur Gruppenanrufannahme die Planungs- und Bereitstellungsschritte dieser Funktion.

### <a name="examples"></a>Beispiele

#### <a name="display-current-call-handling-settings"></a>Aktuelle Einstellungen zur Anrufbehandlung anzeigen

Der folgende Befehl zeigt die Anrufbehandlung für den Benutzer an.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> In diesem Beispiel wird der **Switch /server** verwendet, um die Skype for Business Server anzugeben, mit der eine Verbindung hergestellt werden soll.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Festlegen des Anrufweiterleitungs-/Antwortziels

In diesem Beispiel werden das Ziel für die Anrufweiterleitung/keine Antwort und die Ringverzögerung festgelegt. Hier wird der /server-Switch nicht bereitgestellt; SEFAUtil versucht, die Skype for Business Server 2015 automatisch zu ermitteln.

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

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Hinzufügen eines Benutzers als Stellvertretung und Einrichten des gleichzeitigen Klingelns von Stellvertretungen

In diesem Beispiel wird ein Benutzer als Stellvertretung hinzugefügt und gleichzeitiges Klingeln von Stellvertretungen eingerichtet.

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

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Ändern der Regel für gleichzeitiges Klingeln von Stellvertretungen

In diesem Beispiel wird die im vorherigen Beispiel festgelegte Regel für gleichzeitiges Klingeln in die Regel für verzögertes Klingeln geändert.

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

In diesem Beispiel wird der Delegat entfernt.

> [!NOTE]
> Wenn die letzte Stellvertretung entfernt wird, wird das Klingeln von Stellvertretungen automatisch deaktiviert.

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

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Hinzufügen einer Stellvertretung und Einrichten der Call-Forward zur Stellvertretungsregel

In diesem Beispiel wird eine Stellvertretung hinzugefügt und die Regel zum Weiterleiten an Stellvertretungen eingerichtet.

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

In diesem Beispiel wird gleichzeitiges Klingeln aktiviert und eine Zielnummer für gleichzeitiges Klingeln festgelegt.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Wenn Sie die Zielnummer für gleichzeitiges Klingeln eines Benutzers ändern möchten, für den das gleichzeitige Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Schalter "/enablesimulring" bei, andernfalls wird die Zielnummer nicht geändert.

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

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Hinzufügen eines Teammitglieds für Team-Call und Einrichten des gleichzeitigen Klingelns zur Gruppe Team-Call Mitglieder

In diesem Beispiel wird der Teamanrufgruppe eines Benutzers ein Teammitglied hinzugefügt und gleichzeitiges Klingeln bei der Teamanrufgruppe ermöglicht.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Durch Das Hinzufügen eines Mitglieds zur Teamanrufgruppe eines Benutzers wird automatisch die Einstellung für gleichzeitiges Klingeln der Benutzer auf das gleichzeitige Anrufen seiner Teamanrufgruppe umgestellt.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Entfernen eines Mitglieds aus der Team-Call Gruppe

In diesem Beispiel wird ein Teammitglied der Teamanrufgruppe eines Benutzers entfernt.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Wenn das entfernte Mitglied das einzige Mitglied der Teamanrufgruppe ist, wird das gleichzeitige Klingeln bei der Teamanrufgruppe automatisch deaktiviert.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Festlegen des verzögerten Rings auf die Team-Call Gruppe

In diesem Beispiel wird der verzögerte Ring in die Zeiteinstellung der Teamanrufgruppe geändert.

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

#### <a name="enable-team-call"></a>aktivieren Team-Call

In diesem Beispiel wird der Teamanruf für einen bestimmten Benutzer aktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Wenn die Teamanrufgruppe des Benutzers keine Mitglieder hat, wird der Teamanruf nicht aktiviert.

 **Ausgabe**

#### <a name="disable-team-call"></a>Team-Call deaktivieren

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

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Aktivieren der Gruppenanrufannahme und Zuweisen einer Abholgruppe zu einem Benutzer

In diesem Beispiel wird einem Benutzer eine Abholgruppe zugewiesen und die Gruppenanrufannahme aktiviert.

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

#### <a name="disable-group-call-pickup"></a>Gruppenanrufannahme deaktivieren

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

SYSPrep.ps1 ist ein Windows PowerShell Skript, das die folgenden voraussetzungen für Skype for Business Server 2015 auf Ihrem Windows Server 2008-Betriebssystemcomputer installiert.

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell Version 3.0

- Visual C++ 2010 Redistributable

- Internetinformationsserver-Updates

- Windows Identity Foundation

- Skype for Business Server 2015 Core-Dateien

  Der Name des Skripts ähnelt zwar dem Systemvorbereitungstool für die Microsoft Windows-Betriebssysteme, sie unterscheiden sich jedoch. Dieses Skript installiert nur die erforderlichen Voraussetzungen für Skype for Business Server 2015. Sobald diese Voraussetzungen installiert sind, kann das Windows SYSPrep-Tool verwendet werden, um ein Image des Servers zu erstellen.

### <a name="requirements"></a>Anforderungen

Bevor Sie das SYSPrep.ps1 Skript ausführen, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Betriebssystemcomputer Windows Server 2008 (z. B. **D:\Setup)** kopieren. Dieser Ordner muss auch eine Kopie der Skype for Business Server 2015-Dateien enthalten, insbesondere **Setup.exe.** Die erforderlichen Dateien können von den folgenden Speicherorten heruntergeladen werden:


| **Voraussetzungen**                                | **Location**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell Version 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 Redistributable  <br/>          | <https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0>  <br/>  |
| Internetinformationsserver-Updates  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Kopieren von Skype for Business Server 2015-Medien  <br/>                   |

### <a name="parameter"></a>Parameter

Der Parameter **-SetupFolder** verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.

### <a name="examples"></a>Beispiele

Führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, um das SYSPrep.ps1-Skript auszuführen und die voraussetzungen für Skype for Business Server 2015 zu installieren:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migration von Ankündigungen für nicht zugewiesene Nummern
<a name="UNAM"> </a>

Mit dem Migrationstool für Ankündigungen für nicht zugewiesene Nummern kann ein Skype for Business Server 2015-Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung bedient wird, von einer Quell-Skype for Business Server oder einem Pool an ein Ziel verschieben. Skype for Business Server oder Pool.

### <a name="description"></a>Beschreibung

Das Migrationstool für Ankündigungen nicht zugewiesener Nummern ist ein Windows PowerShell Skript, das die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung eines Quellservers oder Pools bedient wird, auf einen anderen Server oder Pool verschiebt.

Wenn es ausgeführt wird, führt das Migrationsskript "Ankündigungen nicht zugewiesener Nummern" die folgenden Vorgänge aus:

1. Verschieben Sie alle Audiodateien, die von den Ankündigungen nicht zugewiesener Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver oder -pool gehostet wird, in den Dateispeicher des Zielservers oder Pools.

    > [!NOTE]
    > Die Audiodateien werden aus dem Quellpool entfernt, nachdem sie in den Zielpool kopiert wurden.

2. Verschieben Sie alle Ankündigungen nicht zugewiesener Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver oder -pool gehostet wird, auf den Zielserver oder -pool.

3. Weisen Sie alle Bereiche nicht zugewiesener Nummern, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool gehostet wird, dem Zielserver oder -pool neu zu.

Nachdem das Skript erfolgreich ausgeführt wurde, werden alle Bereiche nicht zugewiesener Nummern, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver oder -pool gehostet wird, jetzt mit derselben Konfiguration vom Zielserver oder -pool gewartet.

### <a name="output"></a>Ausgabe

Das **Skript "Move-CsAnnouncementConfiguration**" gibt im Fenster Skype for Business Server Verwaltungsshell an, von wo aus es den Erfolg oder Fehler des Migrationsvorgangs ausführt.

Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die Bereiche nicht zugewiesener Nummern, die erfolgreich an das Ziel verschoben wurden, in betriebsbereiter Form am Ziel, und die restlichen nicht zugewiesenen Nummernbereiche, die migriert werden sollen, verbleiben in der Quelle sowie in betriebsbereiter Form. Um den Rest der Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.

### <a name="purpose"></a>Zweck

Das Migrationsskript "Ankündigungen nicht zugewiesener Nummern" kann in den folgenden drei Szenarien verwendet werden:

- **Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype for Business Server:** Contoso ist dabei, zu Skype for Business Server 2015 zu migrieren, und im Rahmen des Migrationsprozesses Skype for Business Server  Der Administrator möchte die konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung bedient wird, von der Lync Server 2013-Bereitstellung in die neue Skype for Business Server 2015-Bereitstellung verschieben. Um die Konfigurationseinstellungen zu verschieben, verwendet der Skype for Business Server Administrator das Migrationstool "Ankündigungen für nicht zugewiesene Nummern".

- **Rollback einer Bereitstellung von Skype for Business Server 2015 auf Lync Server 2013:** Aufgrund unerwarteter Faktoren muss Contoso die Migration zur neuen Skype for Business Server 2015-Bereitstellung zurücksetzen. Um Unterbrechungen des Diensts zu minimieren, verwendet der Skype for Business Server Administrator das Migrationstool für Nicht zugewiesene Nummern zum Zurücksetzen der Konfiguration von der Bereitstellung Skype for Business Server 2015 auf die Lync Server 2013-Bereitstellung.

- **Verschieben von Daten zwischen Bereitstellungen:** Contoso ist dabei, alle Server eines Pools durch neuere Server zu ersetzen. Ihre Strategie besteht darin, einen neuen Skype for Business Server 2015-Pool bereitzustellen, alle Daten aus dem alten in den neuen Pool zu verschieben und dann den alten Pool zu veralteten. Nachdem der neue Pool bereitgestellt wurde, wird das Migrationstool für Ankündigungen für nicht zugewiesene Nummern verwendet, um die Konfiguration aus dem alten Pool in den neuen zu verschieben.

#### <a name="requirements"></a>Anforderungen

Im Folgenden finden Sie die wichtigsten Anforderungen, die zum erfolgreichen Ausführen des Tools erforderlich sind:

1. Das Skript muss von einem Computer ausgeführt werden, auf dem Skype for Business Server Verwaltungsshell installiert ist.

2. Die Ankündigungsanwendung muss erfolgreich im Quell- und Ziel-Skype for Business Servern oder Pools bereitgestellt werden.

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration-Skript

Das Move-CsAnnouncementConfiguration-Skript erfordert die beiden Parameter, die in der folgenden Tabelle beschrieben werden.

![Move-CsAnnouncementConfiguration Parameter.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Beispiele

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Verschieben der Konfiguration für Ankündigungen nicht zugewiesener Nummern aus einem Lync Server 2013-Pool in einen Skype for Business Server 2015-Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quellpool (Lync Server 2013) in den Zielpool (Skype for Business Server 2015) verschoben.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Verschieben der Konfiguration für Ankündigungen für nicht zugewiesene Nummern von einem Skype for Business Server 2015-Pool in einen Lync Server 2013-Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quellpool (Skype for Business Server 2015) in den Zielpool (Lync Server 2013) verschoben.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Webkonferenzdaten
<a name="WebConfData"> </a>

Das Webkonferenz-Datentool ermöglicht es einem Administrator von Skype for Business Server 2015-Kommunikationssoftware, mehr Kontrolle über die Daten zu haben, die den Webkonferenzen eines Organisators zugeordnet sind. Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers basierend auf einem Zeitstempelkriterium zu löschen.

### <a name="description"></a>Beschreibung

Mit diesem Tool kann der Administrator die folgenden Vorgänge ausführen:

1. Suchen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

2. Löschen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

3. Löschen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, der älter als ein bestimmtes Datum ist.

4. Verschieben aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.

  > [!NOTE]
  > Die Resource Kit-Tools für Lync Server 2010 unterstützten das Verschieben aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird. Diese Funktionalität ist jetzt von diesem Tool zugunsten des **MoveConferenceData-Parameters** veraltet. Ausführliche Informationen zu diesem Parameter finden Sie im [Cmdlet Move-CsUser](/powershell/module/skype/move-csuser?) .

Das Tool löscht Besprechungsdaten nur für Besprechungen, die inaktiv sind. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.

Dieses Tool muss auf einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool verwaltet werden.

### <a name="output"></a>Ausgabe

Dieses Tool gibt die Ergebnisse der einzelnen Vorgänge aus:

- Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, die diesen Benutzer als Organisator haben.

- Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.

### <a name="requirements"></a>Anforderungen

Das Tool muss im selben Pool ausgeführt werden, in dem der Organisator derzeit verwaltet wird.

Das Tool muss mit Administratorrechten mit Zugriff auf die Inhaltsdatei Store ausgeführt werden.

### <a name="examples"></a>Beispiele

In der folgenden Tabelle werden die Parameter beschrieben, von denen einige in den Beispielen verwendet werden.

![Parameter des Webkonferenz-Datentools.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

Im Vorherigen ist ein Beispiel für einen Löschbefehl dargestellt. Der Löschbefehl entfernt alle inaktiven Besprechungsordner von diesem Benutzer.

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine genauere Kontrolle über Konferenzbesprechungsdaten benötigen.
