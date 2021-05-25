---
title: Skype for Business Server 2015 Resource Kit Tools Documentation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: In diesem Artikel werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit hilft, Routineaufgaben für IT-Administratoren zu vereinfachen, die 2015 bereitstellen und Skype for Business Server verwalten. Beispielsweise kann das Web Conf Data-Tool verwendet werden, um daten, die von Benutzern während einer Online-Besprechung hochgeladen werden, einfach zu steuern. Das SEFAUtil-Tool kann zum Einrichten der Weiterleitung und Beantwortung von Stellvertretungsanrufen für Benutzer verwendet werden. Wir empfehlen IT-Administratoren, diese Tools zur effektiveren Verwaltung von Skype for Business Server 2015 zu verwenden.
ms.openlocfilehash: 6c68a94d331f2ad5f9ffaa169228aa9d64e41293
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629044"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Skype for Business Server 2015 Resource Kit Tools Documentation

In diesem Artikel werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit hilft, Routineaufgaben für IT-Administratoren zu vereinfachen, die 2015 bereitstellen und Skype for Business Server verwalten. Beispielsweise kann das **Web Conf Data-Tool** verwendet werden, um daten, die von Benutzern während einer Online-Besprechung hochgeladen werden, einfach zu steuern. Das **SEFAUtil-Tool** kann zum Einrichten der Weiterleitung und Beantwortung von Stellvertretungsanrufen für Benutzer verwendet werden. Wir empfehlen IT-Administratoren, diese Tools zur effektiveren Verwaltung von Skype for Business Server 2015 zu verwenden.

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit Tools

Um das Skype for Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) Download Center herunter.

Führen **OCSResKit.msi** für eine einfache Installation aus. Die .msi installiert alle Tools im folgenden Pfad: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools, die eigenständige ausführbare Dateien sind, befinden sich in diesem Ordner. Tools, die auch über unterstützende Dateien verfügen, befinden sich in ihren eigenen Unterordnern.

## <a name="supported-environments"></a>Unterstützte Umgebungen

Das Skype for Business Server 2015 Resource Kit sollte auf einem Server installiert werden, der die für Skype for Business Server 2015 erforderlichen Spezifikationen erfüllt, normalerweise einen, der für die Ausführung von Skype for Business Server 2015 verwendet wird.

## <a name="resource-kit-tools-overview"></a>Resource Kit Tools (Übersicht)

Im Folgenden finden Sie eine Liste der Tools, die im Skype for Business Server 2015 Resource Kit bereitgestellt werden. Eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispielverwendung, finden Sie in den folgenden Abschnitten.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Bandbreitenrichtliniendienstüberwachung](resource-kit-tools.md#bpsm)

- [Bandbreitenauslastungsanalyse](resource-kit-tools.md#bua)

- [Parkometer für Anrufe](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importieren Storage Dienstdaten](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Nachschlagebenutzerkonsole](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Netzwerkkonfigurationsanzeige](resource-kit-tools.md#NCV)

- [Reaktionsgruppe Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Migration nicht zugewiesener Nummernansagen](resource-kit-tools.md#UNAM)

- [Web Conf Data](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

Das Adressbuchdienstkonfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in Skype for Business Server 2015 anpassen können. Mit diesem Tool können Skype for Business Server 2015-Administratoren die Standardeinstellungen für den Adressbuchdienst wiederherstellen.

### <a name="description"></a>Beschreibung

ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory Domain Services-Attribute konfigurieren können, die mit dem Adressbuchdienst in Zusammenhang stehen.

Die wichtigsten Szenarien für das Tool sind die folgenden:

- So können Administratoren Attribute in Active Directory Domain Services den Attributen für Skype for Business Server 2015 zuordnungen.

- So können Administratoren das Active Directory Domain Services-Attribut angeben, das in die Adressbuchdienstdateien eingeschlossen oder ausgeschlossen werden soll.

- Um Administratoren die Wiederherstellung zu ermöglichen, verwenden Sie standardmäßige Adressbuchdiensteinstellungen.

Das TOOL ABSConfig kann mithilfe der Datei ABSConfig.exe werden. Das Tool wird zur Registerkarte **Attribute konfigurieren** geöffnet. Diese Tabelle enthält Optionen zum Zuordnung von Active Directory-Domänendienstattributen zu den Attributfeldern für Skype for Business Server 2015 und zum Angeben, welche Benutzer in Adressbuchdienstdateien basierend auf bestimmten Attributfiltern ein- oder ausgeschlossen werden. Außerdem gibt es Optionen, um den Wert der Telefonnummer anzupassen, die in die Adressbuchdatei aufgenommen werden soll. Mit **der Option Standardeinstellungen** wiederherstellen können Administratoren adressbuchdiensteinstellungen auf Standardwerte wiederherstellen.

> [!NOTE]
> Die erneute Zuordnung von AD-Attributen zu unterschiedlichen OC-Feldnamen funktioniert nur für den Adressbuchdateidownload und wird von der Adressbuchwebabfrage nicht unterstützt.

### <a name="output"></a>Ausgabe

ABSConfig speichert die Adressbuchdienstkonfiguration in der Datenbank.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Zweck

ABSConfig bietet eine schnelle und einfache Möglichkeit, den Adressbuchdienst Skype for Business Server 2015 anzupassen.

### <a name="requirements"></a>Anforderungen

#### <a name="computer"></a>Computer

ABSConfig kann nur von einem Computer ausgeführt werden, der der Domäne beigetreten ist, auf dem Skype for Business Server 2015 installiert ist. Im Fall von Skype for Business Server 2015 Enterprise Edition kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.

#### <a name="network"></a>Netzwerk

Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End und der Back-End-Datenbank herzustellen.

#### <a name="software"></a>Software

Die folgenden Softwarekomponenten müssen installiert werden, bevor Sie das ABSConfig-Tool ausführen:

- Skype for Business Server 2015

#### <a name="users"></a>Benutzer

Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der Skype for Business Server 2015 verfügen.

### <a name="examples"></a>Beispiele

ABSConfig kann gestartet werden, indemABSConfig.exe Eingabeaufforderung eingeben. Unten sehen Sie die Benutzeroberfläche des ABSConfig-Tools.

![Das ABSConfig.exe Tool.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Zusammenfassung

Das ABSConfig-Tool bietet Administratoren ein schnell und einfach zu verwendende Tool zum Anpassen Skype for Business Server 2015-Adressbuchdiensts.

## <a name="bandwidth-policy-service-monitor"></a>Bandbreitenrichtliniendienstüberwachung
<a name="bpsm"> </a>

Das Tool Bandbreitenrichtliniendienstüberwachung soll Administratoren das Anzeigen einer Liste der folgenden Optionen ermöglichen:

1. Alle konfigurierten Skype for Business Server 2015 Bandbreitenrichtliniendienste (Authentifizierung und Kern) in der Topologie

2. Die Verbindungen, die jeder Dienst mit anderen Bandbreitenrichtliniendiensten und den Edgeservern macht

3. Alle Links, die im Netzwerkkonfigurationsdokument konfiguriert sind, und Die Bandbreitennutzung in Echtzeit, wie von jedem Bandbreitenrichtliniendienst gemeldet

### <a name="description"></a>Beschreibung

Das Tool Bandbreitenrichtliniendienstüberwachung wird als GUI-basierte Anwendung implementiert. Administratoren starten das Tool, indem sie PDPMonUI.exe.

Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreitenrichtliniendienste in der Topologie zu ermitteln. Nach der ersten Aktualisierung wird der Bereich links vom Fenster mit einer Liste von Diensten gefüllt, die nach den Clustern, zu denen sie gehören, gruppieren.

Wenn Administratoren einen bestimmten Bandbreitenrichtliniendienst auswählen, werden im rechten Bereich die Informationen zu diesem bestimmten Dienst angezeigt. Dieser Bereich verfügt auch über zwei Hauptregisterkarten, die Informationen anzeigen.

#### <a name="machine-info-tab"></a>Registerkarte "Computerinformationen"

Auf **der Registerkarte Computerinformationen** werden die Details des ausgewählten Bandbreitenrichtliniendiensts sowie die Liste und der Status aller Verbindungen angezeigt, die vom ausgewählten Bandbreitenrichtliniendienst mit anderen Diensten hergestellt werden.

#### <a name="topology-info-tab"></a>Registerkarte "Topologieinformationen"

Auf **der Registerkarte Topologieinformationen** wird eine Liste aller Links angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jeden Link wird die Audio- und Videobandbreite angezeigt. Darüber hinaus wird die derzeit genutzte Bandbreite sowohl in KBit/s als auch als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierung, um Links mit auslastungsnaher Auslastung zu markieren. Dadurch können Administratoren diese Links schnell isolieren.

> [!NOTE]
>  Wenn beim Tool Bandbreitenrichtliniendienstüberwachung beim Verbinden mit einem der konfigurierten Bandbreitenrichtliniendienste ein Fehler auft wird, werden die Informationen auf den Registerkarten Computerinformationen und **Topologieinformationen** nicht aufgefüllt.  Es ist jedoch möglich, dass das Tool zunächst eine Verbindung herstellen kann, aber anschließend seine Verbindung zum Dienst verliert. In solchen Fällen werden Administratoren möglicherweise veraltete Informationen sehen. Auf jeder **registerkarten ist** ein Zeitstempel "Last Updated" enthalten, mit dem Administratoren sehen können, wann die Daten zuletzt für einen bestimmten Bandbreitenrichtliniendienst aktualisiert wurden.

### <a name="output"></a>Ausgabe

Es gibt keine Befehlszeilenausgabe. die Programmausgabe ist in der haupt grafischen Benutzeroberfläche (GUI) enthalten.

### <a name="purpose"></a>Zweck

Mit dem Tool Bandbreitenrichtliniendienstüberwachung können Administratoren den Status der einzelnen Bandbreitenrichtliniendienste, die in der Topologie definiert sind, sichtbar machen. Darüber hinaus können Administratoren die Echtzeitbandbreitennutzung für alle Links sehen, die im Netzwerkkonfigurationsdokument definiert sind.

### <a name="requirements"></a>Anforderungen

Das Tool Bandbreitenrichtliniendienstüberwachung muss auf einem Computer ausgeführt werden, der Teil der Skype for Business Server ist.

### <a name="summary"></a>Zusammenfassung

Das Tool Bandbreitenrichtliniendienstüberwachung kann eine wertvolle Ressource für Administratoren sein, damit sie den Status aller Bandbreitenrichtliniendienste in der Topologie überprüfen können – und noch wichtiger: Sie können eine Echtzeitbandbreitenauslastung für die In den Netzwerkkonfigurationseinstellungen definierten Links abrufen.

## <a name="bandwidth-utilization-analyzer"></a>Bandbreitenauslastungsanalyse
<a name="bua"> </a>

Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Diese Berichte können verwendet werden, um das aktuelle Bandbreitennutzungsmuster zu verstehen und die Planung der Bandbreitenkapazität zu helfen.

### <a name="description"></a>Beschreibung

Bandwidth Utilization Analyzer wird als GUI-basierte Anwendung implementiert. Dieses Tool generiert Berichte speziell für die Audionutzung im Netzwerk und hilft bei der Kapazitätsplanung. Außerdem wird die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist, durch iteriert.

### <a name="output"></a>Ausgabe

Bandwidth Utilization Analyzer bietet grafische Darstellungen der Bandbreitenkapazität und -auslastung für Audio für alle im System konfigurierten WAN-Verbindungen.

### <a name="purpose"></a>Zweck

In jeder Sprach- und Videobereitstellung ist es wichtig, den Trend der Bandbreitenauslastung des Mediendatenverkehrs über das Unternehmensnetzwerk zu überwachen und zu verstehen. Das Tool Bandwidth Utilization Analyzer ermöglicht es einem Administrator, genau dies zu erreichen. Dieses Tool führt die folgenden Schritte aus:

- Generiert bestimmte Berichte für die Audionutzung im Netzwerk

- Hilft bei der effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Links zugewiesen ist

Bandbreitenauslastungsanalyse kann grafische Darstellungen von Bandbreitenkapazitäts- und Auslastungsberichten generieren. Sie sind wie folgt:

- Alle WAN-Verbindungen im Unternehmensnetzwerk

- Gefiltert nach ausgewählten WAN-Links, die ausgewählt wurden

- Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben

- Gefiltert nach WAN-Links, die die bereitgestellte Bandbreite nicht nutzen

- Filtern nach WAN-Verbindungen, die kritische Ebenen erreicht haben (eine Bandbreitenauslastung von mehr als 90 % der Bandbreitenkapazität der WAN-Verbindung)

- Gefiltert nach WAN-Linktyp– Netzwerk-Standort-Links, überregionale Verbindungen und Links innerhalb eines Standorts

- Gefiltert nach Netzwerkregion

#### <a name="applications"></a>Anwendungen

Bandwidth Utilization Analyzer hat die folgenden beiden Anwendungen (Tools):

- **WanLinkLogCollector.exe** Mit diesem Tool kann der Benutzer die erforderlichen Informationen eingeben.

- **BandwidthUtilizationAnalyzer.xlsm** Ein Microsoft Excel Kalkulationstabellensoftwarebericht wird automatisch von der WanLinkLogCollector.exe. Mit dieser Anwendung kann der Benutzer Filter auf den Bericht anwenden, wie weiter unten in diesem Artikel gezeigt.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phasen der Verwendung der Bandbreitenauslastungsanalyse

Bei verwendung der Bandbreitenauslastungsanalyse gibt es zwei Phasen:

- Sammeln von Protokollen, die mithilfe von WanLinkLogCollector.exe

- Anpassen von Berichten, die mithilfe von BandwidthUtilizationAnalyzer.xlsm ausgeführt werden

    > [!IMPORTANT]
    > Es wird dringend empfohlen, BandwidthUtilizationAnalyzer.xlsm nicht manuell von Endbenutzern gestartet werden.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Starten der Bandbreitenauslastungsanalyse

Starten WanLinkLogCollector.exe an der Eingabeaufforderung oder mithilfe des Windows Explorers.

 **Verwenden WanLinkLogCollector.exe**

Es gibt drei Schritte für die Verwendung WanLinkLogCollector.exe:

1. **Protokollieren der Zeitachse** Bereitstellen der Zeitachse, für die der Bericht generiert werden muss

2. **Angeben der Dateiverzeichnissen** Bereitstellen von Dateispeicherortinformationen

3. **Sammeln der Protokolle und Starten der Berichtsanzeige** Ausführen des Befehls zum Generieren des Berichts

#### <a name="step-1---log-the-timeline"></a>Schritt 1 – Protokollieren der Zeitachse

Durch protokollieren der Zeitachse kann der Toolbenutzer Folgendes angeben, wie in der folgenden Abbildung dargestellt.

1. **Startdatum** Dies ist das Startdatum der Zeitachse, für die der Bericht generiert werden soll. Beispiel: 1. August 2010.

2. **Enddatum** Dies ist das Enddatum der Zeitachse, für die der Bericht generiert werden soll. Beispiel: 30. September 2010.

     ![Start- und Enddaten in bandbreitenauslastung A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Schritt 2 – Angeben der Dateiverzeichnissen

Die folgenden Dateiverzeichnissen können vom Benutzer wie gezeigt angegeben werden.

- **Speicherort der Serverprotokolldateien** Der Ordnerspeicherort, an dem Bandbreitenrichtlinienserverprotokolle gespeichert werden. Dies ist in \<fileserver\> \\ der<fe \> \AppServerFiles\PDP.

- **Speicherort für temporäre Dateien** Der temporäre Dateispeicherort, an dem Zwischendateien gespeichert werden, während der Bericht generiert wird.

    ![Dateiverzeichnissen in der Bandbreitenauslastung anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > Stellen Sie sicher, dass dem Toolbenutzer ausreichend Dateizugriff auf die Serverprotokolle und den temporären Dateispeicherordner bereitgestellt wird.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Schritt 3 – Erfassen der Protokolle und Starten der Berichtsanzeige

Klicken Sie wie unten gezeigt auf **Ausführen,** um die Protokolle zu erfassen und die Berichtsanzeige zu starten. In diesem Schritt werden die erforderlichen Daten gesammelt.

![Sammeln von Daten in der Analyse der Bandbreitenauslastung](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Wenn die Eingabeüberprüfung erfolgreich ist, wird die unten gezeigte Meldung angezeigt.

![Protokollierte Benachrichtigungen im Bandwidth Utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Klicken Sie auf **OK**. BandwidthUtilizationAnalyzer.xlsm wird automatisch gestartet. Befolgen Sie die Anweisungen im Meldungsfeld. Weitere Informationen finden Sie **unter Using BandwidthUtilizationAnalyzer.xlsm** im nächsten Abschnitt.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Verwenden BandwidthUtilizationAnalyzer.xlsm

1. Wenn BandwidthUtilizationAnalyzer.xlsm automatisch gestartet wird, klicken Sie auf **Aktualisieren** wie unten gezeigt.

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Wenn ein Dateiordner geöffnet wird, wählen consolidated.csv im Meldungsfeld angegebenen Speicherort aus, wie unten gezeigt. Außerdem wird der Speicherort als **C:\Temp gezeigt.**

     ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Klicken Sie auf **Importieren**.

4. Die grafische Zeichnung wird automatisch generiert. Sie ist verfügbar, wenn der Zeiger im Hintergrund nicht mehr funktioniert.

     ![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Anwenden von Filtern auf die Berichtsansicht

Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden wie folgt beschrieben:

![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Name** Nach WAN-Links filtern (der Filter befindet sich auf der rechten Seite des Diagramms). Das Präfix kennzeichnet die folgenden Linktypen. siehe vertikales (blaues) Feld:

   - **S-Website** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion

   - **Is-Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten

   - **R Regionenübergreifendes** Die WAN-Verbindung zwischen zwei Netzwerkregion

2. **Grenzwert überschritten** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung größer als die Bandbreitenkapazität ist

3. **Kritische Ebenen** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung 90 % oder mehr als die Bandbreitenkapazität erreicht hat

4. **Nicht ausgelastet** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung unter 25 % der Bandbreitenkapazität liegt

5. **Linktyp** Filtern nach den folgenden WAN-Linktypen:

   - **Netzwerkstandorttyp**

   - **Standortübergreifender** Typ

   - **Linktyp für regionenübergreifende Verbindungen**

6. **Region** Filtern nach Netzwerkregion

Die folgenden Abbildungen zeigen die zuvor beschriebenen Filter.

Filter nach **Name**. Wählen Sie die Liste der Links aus, die im Diagramm angezeigt werden müssen.

![Filtern nach Name in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filter by **Exceeded limit**. Wählen **Sie True aus,** um den Filter zu erzwingen.

![Filtern nach Grenzwertüberschreitung.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtern nach **kritischen Ebenen**. Wählen **Sie True aus,** um den Filter zu erzwingen.

![Filtern nach kritischen Ebenen.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtern nach **Unter verwendet**. Wählen **Sie True aus,** um den Filter zu erzwingen.

![Filtern nach Under Utilized.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtern nach **Linktyp**. Wählen Sie den Typ oder die Typen aus, die angezeigt werden müssen.

![Filtern nach Linktyp.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Links angezeigt werden müssen.

![Filtern nach Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Anforderungen

- The .NET Framework 3.5

- Microsoft Excel 2010 oder Excel 2007

### <a name="summary"></a>Zusammenfassung

Bandbreitenauslastungsanalyse wird verwendet, um die Audiobandbreitenauslastung für den UC-Datenverkehr über das Netzwerk zu plotten. Dieses Tool kann auch verwendet werden, um die Auslastung der Videobandbreite im Netzwerk zu melden.

## <a name="call-parkometer"></a>Parkometer für Anrufe
<a name="callpark"> </a>

Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Orbitdatenbank zum Parken von Anrufen bietet.

### <a name="description"></a>Beschreibung

Call Parkometer ist ein Tool zum Nachverfolgen derzeit geparkter Anrufe. Außerdem werden Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS) gesammelt. Dieses Befehlszeilentool bietet Lese- und Schreibzugriff auf den CPS-Orbit SQL Server von einem lokalen oder remote verbundenen Computer aus.

Alle Optionen schließen sich gegenseitig aus. Die Befehlszeilensyntax lautet wie folgt:

- **-o-Parameter–** Listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.

- **-n-Parameter–** Listet alle derzeit verwendeten Orbits in diesem Pool auf. Die angezeigten Informationen sind wie folgt:

  - SIP Uniform Resource Identifier (URI) des Parkenten und Parkers.

  - Hostname des CPS, in dem der Anruf geparkt wird.

  - Zeitstempel des Zeitpunkts, zu dem der Anruf geparkt wurde.

- **-f-Parameter–** Listet die Anzahl der derzeit freien Orbits im Pool auf.

- **-r \<n\>** -Parameter– Listet \<n\> die letzten geparkten Anrufe auf. Die angezeigten Informationen sind wie folgt:

  - Parkee SIP URI.

  - Parker-SIP-URI.

  - Hostname des CPS, in dem der Anruf geparkt wurde.

  - Zeitstempel, wann der Anruf abgerufen oder gelöscht wurde.

- **-t \<n\>** -Parameter – testet das Reservieren eines Orbits in der Datenbank, um die Zufälligkeit der zugewiesenen Orbitnummern zu zeigen.

### <a name="output"></a>Ausgabe

Abhängig von den Eingabeparametern, die an einer Eingabeaufforderung angegeben werden, zeigt Call Parkometer die folgende Ausgabe an:

- Alle Orbitbereiche, die für diesen Pool konfiguriert sind

- Derzeit geparkte Anrufe

- Anzahl der freien (verfügbaren) Orbits

- Kürzlich geparkte Anrufe

- Reservierte Orbits zum Testen einheitlicher und zufälliger Orbitwerte

### <a name="purpose"></a>Zweck

Der Zweck des CPS-Tools besteht in der Bereitstellung von Befehlszeilenzugriff auf die CPS-Datenbank. Der Administrator kann die CPS-Nutzung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.

### <a name="requirements"></a>Anforderungen

Es gibt keine Anforderungen, wenn dieses Tool auf demselben Computer ausgeführt wird, auf dem CPS ausgeführt wird. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die SQL Server, die von Skype for Business Server 2015 verwendet wird, so konfiguriert sein, dass der Remotezugriff zulässig ist. Das Anrufparkometer muss mit einer SQL Server datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem Pool herzustellen, SQL Server. Diese SQL Server datenbankverbindungszeichenfolge ist in der Konfigurationsdatei definiert, **parkometer.exe.config**. Sie muss sich in dem Verzeichnis befinden, in dem sich parkometer.exe befindet. Die folgende XML-Datei ist ein Beispiel für parkometer.exe.config. Die Parameter, die konfiguriert werden müssen, sind Benutzername (z. B. mydomain\Administrator), Kennwort (z. B. mypassword) und Hostname (z. B. myserver).

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

Bereitgestellte Orbitbereiche: Der -o-Parameter listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind, wie gezeigt

![Orbitbereiche im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Derzeit geparkte Anrufe: Der Parameter -n listet alle derzeit verwendeten Orbits in diesem Pool auf, wie gezeigt

![Derzeit geparkte Anrufe im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Anzahl der freien Orbits: Der Parameter -f listet die Anzahl der derzeit freien Orbits im Pool auf, wie dargestellt.

![Kostenlose Orbits im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Zuletzt geparkte Anrufe: Der \<n\> -r-Parameter listet die \<n\> letzten geparkten Anrufe wie gezeigt auf.

![Kürzlich geparkte Anrufe im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Test orbit reservation: The -t \<n\> parameter tests reserving an orbit in the database as shown

![Testen Sie Orbitreservierungen im Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Zusammenfassung

Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver enthält.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Beschreibung

DBAnalyze ist ein Befehlszeilentool, mit dem Administratoren Analyseberichte zu den Skype for Business Server 2015-Datenbanken sammeln können. DBAnalyze verfügt über die folgenden Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:

- **Diagnosemodus** Erstellt einen Bericht mit Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten- und Protokolldateigrößen, der letzten Back-up-Zeit, der Kontaktverteilung auf Servern, auf denen Microsoft Office Communications Server ausgeführt wird, der durchschnittlichen Anzahl von Berechtigungen, Kontakten, Containern, Abonnements, Publikationen, Endpunkten pro Benutzer, nicht ordnungsgemäß untergebrachten Benutzern, Benutzern, die nicht geroutet werden können, der durchschnittlichen Anzahl von Konferenzen, die pro Benutzer organisiert werden, geplanten Konferenzen, aktiven Konferenzen und der Datenbankversion.

    > [!NOTE]
    > Das Ausführen des Diagnosemodus kann sich auf die Serverleistung auswirken.

- **Benutzerdatenmodus** Meldet Kontakt-, Container-, Abonnement-, Publikations-, Berechtigungs- und Kontaktgruppendaten für einen angegebenen Benutzer oder für Benutzer, die über den Benutzer in seinen Kontakt- und Berechtigungslisten verfügen. Dieser Modus meldet auch Zusammenfassungsdaten für Konferenzen, die ein Benutzer organisiert oder zu der er eingeladen wird.

- **Konferenzmodus** Meldet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Termindetails für die Konferenz, der Liste der Eingeladenen, der Liste der für die Konferenz zulässigen Medientypen, aktiver MCUs (Mehrpunktsteuerungseinheiten), der Liste der aktiven Teilnehmer und des Signalstatus der einzelnen Teilnehmer.

- **Decodieren der Besprechungs-ID** Decodiert eine PSTN(Public Switched Telephone Network)-Besprechungs-ID, die von der **Option /pstnid** angegeben wird, aber keine Verbindung mit dem Back-End für detaillierte Informationen herstellen kann.

- **Konferenz auflösen** Decodiert eine PSTN-Besprechungs-ID, die von der **Option /pstnid** angegeben wird, und zeigt Informationen zu der durch die ID angegebenen Konferenz an.

- **MCUs-Modus** Meldet die ID, den Medientyp, die URL, den Taktstatus, die Konferenzlast und die Teilnehmerlast für jede MCU im Pool.

- **Datenträgerfragmentierungsmodus** Zeigt den Fragmentierungsstatus aller Datenträger an.

Dieses Tool kann verwendet werden, um verschiedene Probleme zu diagnostizieren oder Administratoren bei der Kapazitätsplanung zu unterstützen. Wenn beispielsweise die meisten Benutzer, die auf Server A gespeichert sind, Benutzer auswählen, die auf Server B als Kontakte gespeichert sind, kann der Administrator die Benutzer auf Server A auf Server B verschieben, um den serverübergreifenden Datenverkehr zu reduzieren.

### <a name="output"></a>Ausgabe

Mit diesem Tool werden vordefinierte Berichte zur Skype for Business Server 2015-Datenbank ausgegeben. **Pfad**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Zweck

Wenn Sie Dbanalyze.exe, kopieren Sie sie in einen lokalen Ordner, und führen Sie das Tool aus. Führen Sie den folgenden Befehl an der Befehlszeile aus, um das Tool zu verwenden. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Die Beschreibungen für die Befehlszeilenoptionen sind unten dargestellt.

![Befehlszeilenoptionen für Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Anforderungen

 **Computer** DBAnalyze kann nur von einem Computer ausgeführt werden, der der Domäne beigetreten ist, auf dem Skype for Business Server 2015 installiert ist.

 **Netzwerk** Der Computer sollte eine Verbindung mit der Back-End-Datenbank herstellen können.

 **Software** Skype for Business Server 2015-Softwarekomponenten müssen installiert werden, bevor DBAnalyze ausgeführt wird.

 **Benutzer** In der folgenden Tabelle sind die Administratoren aufgeführt, die über die erforderlichen Berechtigungen für den Zugriff auf Skype for Business Server 2015-Datenbanken verfügen.

![Berechtigungstabelle für Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Für den **/report:disk-Modus** ist ein lokales Administratorkonto erforderlich.

### <a name="examples"></a>Beispiele

Nachfolgend finden Sie Beispiele für gültige Dbanalyze.exe Befehle:

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

Das ImportStorageServiceData-Ressourcenkittool ermöglicht das erneute Importieren von Warteschlangen- und Endpunktdaten, die aus dem Storage Service (LYSS) wieder in den Storage dienst gelöscht wurden.

### <a name="description"></a>Beschreibung

Die daten, die aus dem Storage gelöscht wurden, könnten automatisch (regelmäßig) basierend auf dem Status des Warteschlangenelements oder der Datenbankgröße sein. Dies könnte aufgrund des manuellen Aufrufs des Poolfailover-Cmdlets oder des StorageServiceFullFlush-Cmdlets (das vom Poolfailover-Cmdlet aufgerufen wird) geschehen. Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn eine der Storage Service (LYSS )-Datenbankgrößen an den Front-Ends über der normalen Ebene liegt, da dadurch wahrscheinlich nur mehr Daten zurück exportiert werden. Darüber hinaus sollten alle Probleme, die zu Fehlern beigetragen haben könnten, die zu einem Wachstum der Storage-Dienstwarteschlange beigetragen haben, zuerst behoben werden (z. B. Exchange Endpunktfehler, Netzwerkprobleme oder andere Probleme).

 **Szenario 1:** Während des Poolfailover können Dateien für jedes Front-End aus dem Speicherdienst geleert werden. Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.

 **Szenario 2:** Daten werden täglich automatisch geleert oder als Reaktion auf Storage Dienstdatenbank, die bestimmte Größenschwellenwerte überschreitet (z. B. 60 %, 80 %, 90 % voll). Diese automatisch geleerten Daten sollten vom Administrator routinemäßig erneut importiert werden. Wenn das Überwachungs-SCOM-Pack nicht bereitgestellt wird, gibt es in der obigen Situation Ereignisse für Skype for Business Server Storage Service im Zusammenhang mit Daten, die aus dem Storage werden. Ereignis-IDs von 32075 (Der vollständige Leerungsvorgang wird gestartet), 32076 (vollständige Leerung wurde abgeschlossen), 32082 (Wartungslevel flush started), 32083 (Wartungslevel flush complete), 32089 (flush occurred due to filling up of database). Beachten Sie, dass diese Ereignis-IDs der RTM-Version entsprechen. Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass es Dateien gibt, die geleert wurden. Diese Daten sollten routinemäßig mit diesem Tool zurück importiert werden, z. B. einmal pro Woche.

Wenn für die Onlinedienstversion SCOM Pack für die Integritätsüberwachung für Skype for Business Server bereitgestellt wird, werden möglicherweise neue Warnungen ausgelöst, die den Administrator bitten, die geleerten Daten wieder in den Storage zu importieren. Das Ereignisprotokoll enthält ein entsprechendes Ereignis auf dem Front-End, das die Warnung ausgelöst hat. Das Ereignis enthält eine Beschreibung des übergeordneten Pfads, unter dem sich die geleerten Datendateien befinden, und der Anzahl der Dateien, die die Warnungskriterien erfüllen. Die Warnungskriterien sind, dass X oder mehr Dateien unter dem bestimmten übergeordneten Pfad enthalten sind, die mindestens Y Tage alt sind (wobei X und Y innerhalb des StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei außer Kraft gesetzt werden können.) Zwei Beispiele für Ereignisse, die die Integritätswarnung auslösen können, werden unten gezeigt, mit dem Unterschied, dass der übergeordnete Pfad der Fall ist. Eine Möglichkeit ist unter Webdienstdateifreigabe, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-Ends ist. (z. B. c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService). Der Administrator wird dann dieses Reskit-Tool ausführen.

Dieses Tool erhöht die CPU- und E/A-Last auf dem Front-End, auf dem es ausgeführt wird, und anderen Front-Ends, wenn die Daten nicht im Besitz des Front-Ends sind, für das das Tool ausgeführt wird. Es wird empfohlen, dieses Tool zu verwenden, wenn die Front-Ends nicht unter einer hohen CPU- und E/A-Last stehen, z. B. außerhalb der Spitzenzeiten. Zweitens kann dieses Tool 2 bis 3 Minuten dauern, um eine Datendatei zu importieren. Denken Sie daran, wenn Sie schätzen, wie lange das Tool ausgeführt wird. Die ausführliche Protokolldatei, die vom Tool generiert wird, wird standardmäßig auf der Datei Store. Löschen Sie sie, wenn keine Fehler gemeldet werden, da die Protokolldatei mehrere zehn MB oder mehr haben kann.

![Beispiel Storage Server-Ereignisprotokollereignisse.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Anforderungen

Installieren Sie Skype for Business Server 2015 Resource Kit-Tools. Das Tool wird auf Computern ausgeführt, die der Domäne Skype for Business Server und Skype for Business Server Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal-Datenbank** installiert ist. Diese Datenbank wird vom Tool verwendet, um den Speicherort der WEBSERVICE-Dateifreigabe für den Pool abzurufen. Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools zunächst Windows PowerShell Remoting mithilfe von **Enable-PSRemoting** auf jedem Front-End-Server und dem Computer aktivieren, von dem das Tool ausgeführt wird. Andernfalls Windows PowerShell Remotebefehle aus diesem Tool fehl. Windows PowerShell Das Remoting kann auf allen Front-End im Pool deaktiviert werden, nachdem es abgeschlossen ist. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über Lese-/Schreibberechtigungen für die Webservicedateifreigabe für den Pool verfügen, in dem dieses Tool ausgeführt wird. Andernfalls kann das Tool mit Io-Berechtigungsfehlern fehlschlagen.

> [!NOTE]
> Auf Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht unter dem betriebssystem Windows Server 2008.

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

Das LCSSync-Tool hilft beim Bereitstellen Skype for Business Server 2015-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen. Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzer gesamtstrukturen als Active Directory Domain Services-Kontaktobjekt mit einer zentralen Gesamtstruktur zu synchronisieren, in der Skype for Business Server 2015 installiert ist.

### <a name="description"></a>Beschreibung

 LCSSync verwendet die synchronisierten Active Directory Domain Services-Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzer für Skype for Business Server. Zum Bereitstellen einer einmaligen Anmeldung muss das primäre Benutzerkonto dem Active Directory Domain Services-Kontaktobjekt in der zentralen Gesamtstruktur für Skype for Business Server 2015 zugeordnet werden. Dieses Tool hilft bei der Durchführung dieser Zuordnung. Dieses Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents auf dem Microsoft Identity Integration Server bereit.

### <a name="summary"></a>Zusammenfassung

Das LCSSync-Tool hilft bei der Skype for Business Server 2015 in einer Umgebung mit mehreren Gesamtstrukturen.

## <a name="lookup-user-console"></a>Nachschlagebenutzerkonsole
<a name="LUC"> </a>

Das Tool LookupUserConsole zeigt interne Skype for Business Server Routinginformationen zu bestimmten Benutzern an. Diese Informationen können hilfreich sein, wenn Microsoft persönliche Probleme bei der Diagnose von Bereitstellungs- und Routingproblemen unterstützt.

### <a name="description"></a>Beschreibung

 Beim Ausführen LookupUserConsole.exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert und versucht, interne Skype for Business Server routinginformationen zu diesen zu zeigen. Geben **Sie Exit** ein, um das Tool LookupUserConsole zu beenden.

### <a name="requirements"></a>Anforderungen

Installieren Sie das Skype for Business Server 2015 Resource Kit. Das Tool wird auf Computern ausgeführt, die der Domäne beigetreten sind, Skype for Business Server installiert ist.

### <a name="examples"></a>Beispiele

C:\Program Files\Skype for Business Server 2015\ResKit \>LookupUserConsole.exe

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

Das MSTurnPing-Tool ermöglicht es einem Administrator von Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen der Audio-/Video-Edge-, Audio-/Videoauthentifizierungsdienst und die Server ausgeführt werden, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

### <a name="description"></a>Beschreibung

Das MSTurnPing-Tool ermöglicht es einem Administrator von Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen der Audio-/Video-Edge-, Audio-/Videoauthentifizierungsdienst und die Server ausgeführt werden, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

Das Tool ermöglicht es dem Administrator, die folgenden Tests durchzuführen:

1. A/V-Edgeservertest: Das Tool führt Tests für alle A/V-Edgeserver in der Topologie durch:

   - Überprüfen, ob der Skype for Business Server-/Videoauthentifizierungsdienst gestartet wurde und ordnungsgemäße Anmeldeinformationen aus dem Dienst aussenden kann.

   - Überprüfen Sie, Skype for Business Server der Audio-/Video-Edgedienst gestartet wurde und die Ressourcen auf dem externen Edge erfolgreich zugewiesen werden können.

2. Bandbreitenrichtliniendiensttest: Das Tool führt Tests für alle Server durch, auf denen die Bandbreitenrichtliniendienste in der Topologie ausgeführt werden, indem folgendes ausgeführt wird:

   - Überprüfen, ob der Skype for Business Server Bandbreitenrichtliniendienst (Authentication) gestartet wurde und ordnungsgemäße Anmeldeinformationen aussenden kann.

   - Überprüfen, ob Skype for Business Server Bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreitenüberprüfung erfolgreich durchführen kann.

Dieses Tool muss von einem Computer ausgeführt werden, der Teil der Topologie ist und den lokalen Speicher installiert hat.

### <a name="output"></a>Ausgabe

Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.

- Wenn der **AudioVideoEdgeServer-Test** ausgeführt wird, werden die folgenden Toolausgänge ausgegeben:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015-Audio-/Videoauthentifizierungsdienst in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Audio/Video Edge Service in der Topologie bereitstellen

- Wenn der **BandwidthPolicyServer-Test** ausgeführt wird, werden die folgenden Toolausgänge ausgegeben:

  - Die Testergebnisse der Computer, die Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die Skype for Business Server 2015 Bandwidth Policy Service (Core) in der Topologie bereitstellen

### <a name="requirements"></a>Anforderungen

- Dieses Tool muss von einem Computer ausgeführt werden, der sich in der Topologie befindet und über den lokalen Speicher verfügt.

- Das Tool muss als Administrator ausgeführt werden, der Zugriff auf den lokalen Speicher hat.

### <a name="examples"></a>Beispiele

Im Folgenden finden Sie ein Beispiel für die Tooleingabe.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio-/Video- und Bandbreitenrichtliniendienste ausgeführt werden.

## <a name="network-configuration-viewer"></a>Netzwerkkonfigurationsanzeige
<a name="NCV"> </a>

Die Netzwerkkonfigurationsanzeige kann von Skype for Business Server 2015-Kommunikationssoftwareadministratoren zum Anzeigen der Anrufsteuerungsnetzwerktopologie für ein Unternehmen verwendet werden, das bereitgestellt wird, um Kommunikationssitzungen in Echtzeit zu ermöglichen, z. B. Sprach- oder Videoanrufe basierend auf der angegebenen Bandbreitenkapazität. Skype for Business Server 2015-Administratoren definieren KSG-Richtlinien, die von den Bandbreitenrichtliniendiensten erzwungen werden, die mit Skype for Business Server 2015 installiert sind.

### <a name="description"></a>Beschreibung

Die Netzwerkkonfigurationsanzeige (NetworkConfigurationViewer.exe) ermöglicht Es Administratoren, die folgenden Aufgaben auszuführen:

- Laden und Anzeigen der Cac-Netzwerktopologie aus Skype for Business Server 2015-Bereitstellung in einem grafischen Format.

- Laden und Anzeigen der Cac-Netzwerktopologie aus einer Protokolldatei des Bandbreitenrichtlinienservers in einem grafischen Format.

- Speichern und speichern Sie die Cac-Netzwerktopologie in einem XML-Format auf dem Datenträger.

- Speichern und speichern Sie das Diagramm für die Cac-Netzwerktopologie im JPG- oder BMP-Format.

- Anzeigen von Konfigurationsdaten für die Cac-Netzwerktopologie.

- Zeigen Sie die Cac-Netzwerktopologie in einer Strukturansicht an.

- Definieren sie benutzerdefinierte Connectors für Verbindungen mit der KS-Netzwerktopologie (z. B. Standort-zu-Region-, Region-zu-Region- und Standort-zu-Standort-Links).

- Anzeigen von Standortinformationen, Regioneninformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen für die Cac-Netzwerktopologie.

### <a name="purpose"></a>Zweck

Anzeigen von Unternehmens-CAC-Netzwerktopologielinks in einer grafischen Schnittstelle.

### <a name="examples"></a>Beispiele

 Laden und Anzeigen der Cac-Netzwerktopologie aus einer **Skype for Business Server 2015-Bereitstellung** in einem grafischen Format: Skype for Business Server 2015-Administratoren können die Konfiguration der Cac-Netzwerktopologie auf jedem beliebigen Skype for Business Server 2015-Computer mithilfe der Option Netzwerkkonfiguration herunterladen laden und anzeigen, wie in der folgenden Abbildung dargestellt.  Das Tool kann eine solche Konfiguration nicht herunterladen oder anzeigen, wenn es auf einem Computer bereitgestellt wird, der keine Verbindung zum Skype for Business Server 2015-Konfigurationsspeicher hat.

![Herunterladen der Netzwerkkonfiguration.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 Laden und Anzeigen der Cac-Netzwerktopologie aus einer Protokolldatei des Bandbreitenrichtlinienservers in einem grafischen **Format:** Skype for Business Server 2015 Bandbreitenrichtlinienserver speichern die Cac-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Dateifreigabespeicherort von Skype for Business Server 2015. Skype for Business Server 2015-Administratoren können eine solche Datei mithilfe der Option **Netzwerkkonfiguration** öffnen wie unten gezeigt in einem grafischen Format anzeigen.

![Öffnen einer Protokolldatei des Bandbreitenrichtlinienservers.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Speichern und speichern Sie die Cac-Netzwerktopologie in einem XML-Format auf dem Datenträger: Skype for Business Server 2015 können  Administratoren die Konfigurationsdatei für die KS-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option Speichern einer Kopie der Netzwerkkonfiguration wie unten gezeigt verwenden. Die gespeicherte Konfigurationsdatei kann dann offline für grafische Anzeigezwecke verwendet werden.

![Speichern der Netzwerkkonfiguration als XML-Datei.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Speichern und Store Diagramm der Cac-Netzwerktopologie im JPG- oder BMP-Format: Skype for Business Server 2015 können Administratoren die Konfiguration der Cac-Netzwerktopologie in einem grafischen Format (JPG- und BMP-Dateiformate) speichern, indem Sie das Diagramm Netzwerkkonfiguration als Bild speichern wie unten gezeigt verwenden. 

![Speichern der Netzwerkkonfiguration als Bild.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 Konfigurationsdaten der Cac-Netzwerktopologie <strong>anzeigen:</strong>Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten wie Netzwerkregionen, Netzwerkstandorte, Bandbreitenprofile und Standortsubnetz-IP-Adressen in einem Textformat anzeigen, indem Sie die Datenoption Netzwerkkonfiguration anzeigen wie unten gezeigt verwenden.

![Anzeigen von Netzwerkkonfigurationsdaten.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 Ansicht der Cac-Netzwerktopologie in einer **Strukturansichtsart:** Skype for Business Server 2015 können Administratoren verwandte Netzwerkkonfigurationsdaten in einer grafischen Strukturansicht anzeigen, indem sie die Systemsteuerung auf der linken Seite des Toolfensters verwenden, wie unten gezeigt.

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 Definieren von benutzerdefinierten Connectors für KS-Netzwerktopologielinks (z. B. **Standort-zu-Region-, Region-zu-Region-** und Standort-zu-Standort-Links): Skype for Business Server 2015-Administratoren können benutzerdefinierte grafische Connectors für DIE NETZWERKkonfigurations-WAN-Verbindungen mit der Option Einstellungen definieren, wie unten gezeigt. Dadurch wird zwischen verschiedenen Typen von Netzwerkverbindungen unterschieden, die in der Netzwerkkonfiguration bereitgestellt werden.

![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

  Anzeigen von Standortinformationen, Regioneninformationen und bereitgestellten Bandbreitenrichtlinien für die KSK-Netzwerktopologie: Skype for Business Server 2015 können Administratoren verwandte Standortinformationen, Standortinformationen und Bandbreitenbereitstellungsinformationen für die KSB mithilfe der unten gezeigten Optionen anzeigen. (Klicken Sie beispielsweise in einer **Netzwerkregion** oder einem Netzwerkstandortobjekt auf Info.)

![Definieren benutzerdefinierter Connectors für Ihr Netzwerk.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die die Cac-Netzwerktopologie für ihre Bereitstellung in einem grafischen Format anzeigen möchten.

## <a name="response-group-agent-live"></a>Reaktionsgruppe Agent Live
<a name="RGAL"> </a>

Die Reaktionsgruppe bietet Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zu zugreifen. Leider ist außerhalb der Anwendung keine grafische Ansicht dieser Daten verfügbar. Das Tool Response Group Agent Live Resource Kit löst dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zu zugreifen, die mit Skype for Business-Kommunikationssoftwareinformationen wie dem Vorhandensein anderer Agents Skype for Business Echtzeit erweitert wird.

### <a name="description"></a>Beschreibung

Response Group Agent Live ist eine Windows-Anwendung, die Anmelde- und Abmeldefunktionen sowie einige Echtzeitinformationen (z. B. Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppe-Agents bietet. Es soll eine erweiterte Version der Seite "Agentgruppen" sein (auf die sie über Skype for Business.

### <a name="purpose"></a>Zweck

Die Reaktionsgruppenanwendung warteschlanget eingehende Anrufe in die Warteschlange und leitet sie dann an Agentgruppen weiter. Um fundierte Entscheidungen darüber zu treffen, welche Anrufe an den Dienst gesendet werden, können Agents auf Echtzeitinformationen zu ihren Agentgruppen zugreifen, z. B. welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschlange warten. Diese Informationen, auf die zunächst nur über den Reaktionsgruppesdienst zugegriffen werden kann, werden von Response Group Agent Live intuitiv verfügbar gemacht.

#### <a name="features"></a>Features

Das Tool Response Group Agent Live baut auf dem Reaktionsgruppesdienst und dem Skype for Business Server 2015 SDK auf. Es stellt Reaktionsgruppe-Agents die Informationen und Funktionen bereit, die vom Reaktionsgruppesdienst verfügbar sind (z. B. Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).

Die folgende Abbildung veranschaulicht die Hauptschnittstelle von Response Group Agent Live.

![Das Tool Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Die folgenden drei Hauptfeatures sind für Agents in Response Group Agent Live verfügbar:

- **Anmeldung/Abmelden:** Im Gegensatz zur Seite Agentgruppen (auf die ab Skype for Business Server 2015 zugegriffen werden kann), können sich nur Agents gleichzeitig bei allen Agentgruppen anmelden oder abmelden. Diese Anwendung bietet drei schnelle Möglichkeiten für Agents zum Anmelden oder Abmelden:

  - Klicken Sie in der Anwendung auf die Schaltflächen Anmeldung/Abmelden (grün und rot).

  - Klicken Sie mit der rechten Maustaste auf das Systemablagesymbol, und wählen Sie Anmelden oder Abmelden aus.

  - Verwenden konfigurierbarer Tastenkombinationen.

- **Gruppenmitgliedschaft:** Wenn eine Agentgruppe ausgewählt ist, zeigt Response Group Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an. Wenn Skype for Business Server 2015 auf demselben Computer wie diese Anwendung ausgeführt wird, werden Anwesenheitsinformationen und die Visitenkarte im Response Group Agent Live angezeigt. Agents können sofort eine Sofortbenachrichtigung senden oder andere Agents direkt von dort anrufen.

- **Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agentgruppen. Die Aktualisierungshäufigkeit beträgt eine Minute. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein visueller Indikator mit der aktuellen Anzahl von Anrufen in der Warteschlange hinzugefügt. Beim Anhalten des Zeigers auf eine Gruppe wird auch die längste Wartezeit angezeigt.

### <a name="requirements"></a>Anforderungen

Response Group Agent Live erfordert die .NET Framework 4.0. Um die Anwesenheits- und Visitenkartenfunktionen nutzen zu können, muss Skype for Business lokal installiert werden (und ausgeführt werden).

#### <a name="configuration"></a>Konfiguration

Response Group Agent Live kann mithilfe des Dialogfelds Optionen in der Anwendung an einzelne Einstellungen angepasst werden. Darüber hinaus kann der Administrator die Standardhostadresse definieren, indem er die defaultHostAddress-Eigenschaft der RGAgentLive.exe.config bearbeitet.

Die folgende Abbildung veranschaulicht das Dialogfeld Optionen, das Agents zum Konfigurieren der Hostadresse und der Tastenkombinationen verwenden können. Auf dieses Dialogfeld wird zugegriffen, indem sie oben rechts auf der Hauptschnittstelle auf die Schaltfläche Optionen klicken.

![Das Dialogfeld Reaktionsgruppe Agent Live-Optionen.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Die folgenden drei verschiedenen Einstellungen können in der Reaktionsgruppe Agent Live-Konfiguration angepasst werden:

- Hostadresse: Dies ist in der Regel der FQDN des Webpools, der zum Startpool des Agents gehört. Die genaue Dienstadresse der Reaktionsgruppe wird automatisch im Hintergrund aus diesen Informationen abgeleitet (indem der richtige Pfad hinter dem Host angefügt wird).

- Verknüpfungen: Die genauen Verknüpfungen zum Anmelden/Abmelden können angepasst werden. Die einzige Einschränkung ist, dass beide Verknüpfungen die Taste "Windows Logo" enthalten müssen (zusätzlich zu mindestens einer anderen Taste).

- Beginnen Sie Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch mit Windows.

### <a name="examples"></a>Beispiele

In der folgenden Abbildung wird veranschaulicht, wie Sie eine Sofortbenachrichtigung an einen anderen Agent anrufen oder an einen anderen Agent senden, indem Sie mit der rechten Maustaste auf den Kontakt im rechten Bereich klicken.

![Einen Anruf oder das Senden eines Anrufs.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

Die folgende Abbildung zeigt, wie Reaktionsgruppe Agent Live die aktuelle Anzahl von Anrufen in der Warteschlange und die längste Wartezeit unter all diesen eingehenden Anrufen anzeigt.

![Anzeigen von Warteschlangeninformationen.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Zusammenfassung

Schnelles Anmelden und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Reaktionsgruppe-Agent-Features, die nur außerhalb der Anwendung über den Reaktionsgruppesdienst verfügbar sind. Mit dem Tool Response Group Agent Live Resource Kit können Skype for Business Server 2015-Administratoren ihren Agents eine Windows-Anwendung bereitstellen, mit der sie Aufgaben schneller und grafisch ausführen können.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (sekundäre Aktivierung von Erweiterungsfeatures) ist ein Befehlszeilentool, mit dem Skype for Business Server 2015-Kommunikationssoftwareadministratoren und Helpdesk-Agents delegiertes Klingeln, Anrufleitung, gleichzeitiges Klingeln, Teamanrufeinstellungen und Gruppenanrufannahme im Namen eines Skype for Business Server 2015-Benutzers konfigurieren können. Das Tool ermöglicht Administratoren auch das Abfragen der Anrufroutingeinstellungen, die für einen bestimmten Benutzer veröffentlicht werden. Das SEFAUtil-Tool ermöglicht es dem Administrator, die Anruf weiterleitung zu aktivieren/zu deaktivieren/zu ändern oder gleichzeitig im Namen des Benutzers zu klingeln. Der Administrator kann das Ziel (in Form eines SIP-URI) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde. Mit diesem Tool können Administratoren auch Stellvertretungs- oder Teamanrufgruppenmitglieder im Namen des Benutzers hinzufügen oder entfernen. Dieses Tool baut auf microsoft Unified Communications Managed API (UCMA) 3.0 auf und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.

SEFAUtil (Aktivierung der sekundären Erweiterungsfunktion) ermöglicht Skype for Business Server 2015-Administratoren und Helpdesk-Agents das Konfigurieren von Stellvertretungsringen, Anrufanrufen, gleichzeitigen Klingeln, Teamanrufeinstellungen und Gruppenanrufannahmen im Namen eines Skype for Business Server 2015-Benutzers. Mit diesem Tool können Administratoren auch die Anrufroutingeinstellungen abfragen, die für einen bestimmten Benutzer veröffentlicht werden.

### <a name="description"></a>Beschreibung

Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool. es gibt keine unterstützende grafische Benutzeroberfläche. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0. Die Features in diesem Tool ermöglichen Administratoren und Helpdesk-Agents folgendes:

- Anzeigen aller Anrufroutingeinstellungen für einen Benutzer (einschließlich Anrufleitung, Delegierung, gleichzeitiges Klingeln, Teamanruf und Gruppenanrufannahme)

- Aktivieren/Deaktivieren/Ändern der Anruf weiterleitungseinstellung (einschließlich Ziel- und No-Answer-Timer)

- Aktivieren/Deaktivieren/Ändern sofortiger Konfigurationen für die Anruf weiterleitung

- Delegierungseinstellungen aktivieren/deaktivieren/ändern

- Aktivieren/Deaktivieren/Ändern von Gruppeneinstellungen für Teamanrufe

    > [!NOTE]
    > Neu in Skype for Business Server 2015 SEFAUtil-Tool

- Aktivieren/Deaktivieren/Ändern gleichzeitiger Klingeleinstellungen (einschließlich Ziel)

    > [!NOTE]
    > Neu in Skype for Business Server 2015 SEFAUtil-Tool

- Aktivieren/Deaktivieren/Ändern von Gruppenanrufannahmeeinstellungen

    > [!CAUTION]
    > Neu in Skype for Business Server 2015 SEFAUtil-Tool

Dieses Tool hat die folgenden Einschränkungen:

- Wird nur für Benutzer unterstützt, die in einem Skype for Business Server werden

- Massenbearbeitung von Anrufroutingeinstellungen für mehrere Benutzer wird nicht unterstützt

### <a name="output"></a>Ausgabe

Die aktuelle Version dieses Tools stellt nur die Ausgabe im Eingabeaufforderungsfenster zur Ausgabe. Weitere Informationen finden Sie im Abschnitt Beispiele weiter später in diesem Dokument.

### <a name="purpose"></a>Zweck

Nachfolgend finden Sie einige der wichtigsten Szenarien, in denen dieses Tool verwendet werden kann:

- Bob ist Führungskraft und wurde in die Skype for Business Server verschoben. Er verfügt über delegierung auf seinem vorhandenen Nebenstellenanlagesystem. Im Rahmen des Wechsels zu Skype for Business Server 2015 ist der Administrator in der Lage, Bobs Routing so zu konfigurieren, dass es seine bereits vorhandene Delegierungskonfiguration wiederspiegelt.

- Alice ist unterwegs und erkennt, dass sie einen wichtigen Anruf von einem ihrer Kunden erwartet. Sie befindet sich jedoch in einem Hotel und hat keinen Zugriff auf einen Computer. Sie ruft den Helpdesk an und fordert sie auf, alle Anrufe, die an ihre Arbeitsnummer vorgenommen wurden, an ihre Mobiltelefonnummer weiter zu weiterleiten. Die Helpdeskmitarbeiter sind in der Lage, die Konfiguration in ihrem Namen zu tun.

- Joes Anrufe an seine Arbeitsnummer gehen an seine mobile Voicemail, wenn er bei der Arbeit ist. An den meisten anderen Standorten scheint dies jedoch ordnungsgemäß zu funktionieren. Der Helpdesktechniker kann Joes Routingkonfiguration anzeigen und ermittelt, dass Joe gleichzeitig klingelt und auf seinem Mobiltelefon konfiguriert ist. Der Techniker fragt Joe nach der mobilen Abdeckung in seinem Büro und kann feststellen, dass die gleichzeitige Klingelregel dazu führt, dass die Anrufe zu Joes mobiler Voicemail gehen, wenn seine Netzwerkabdeckung schlecht ist.

- Mike ist ein neuer Mitarbeiter bei Contoso und kommt zu einem neuen Team, in dem alle Mitglieder für den Teamanruf konfiguriert sind. Wenn er für Skype for Business Server 2015 aktiviert ist, kann der Administrator seine Teamanrufgruppeneinstellungen so festlegen, dass alle seine neuen Teammitglieder enthalten sind. Darüber hinaus fügt der Administrator Mike als Teamanrufgruppenmitglied für jedes Mitglied seines Teams hinzu.

- Eine Kundendienstpraxis in der Personalabteilung von Contoso besteht in der Bereitstellung von persönlichem Dienst für alle Anrufer seit dem ersten Anruf. Da alle Mitglieder der Abteilung sehr nah beieinander sitzen, ist es für das Team störend, alle Telefone gleichzeitig mit Teamanrufen klingeln zu haben. Um den besten Dienst zu bieten, ohne die Teammitglieder zu stören, nutzt der Skype for Business Server 2015-Administrator die Funktion "Gruppenanrufannahme". Der Administrator fügt alle Abteilungsmitglieder zu einer Pickupgruppe hinzu und teilt der Abteilung die Pickupgruppennummer mit. Wenn Samantha nicht am Schreibtisch ist, bemerkt Joe, dass ihr Telefon klingelt, und er geht weiter, um den Anruf von seinem Schreibtisch aus zu beantworten.

### <a name="requirements"></a>Anforderungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. UCMA 3.0 muss auf diesem Computer installiert sein. Zum Ausführen des Tools muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool

1. Das SEFAUTil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Bei Bedarf kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die Skype for Business Server-Verwaltungsshell mit dem folgenden Cmdlet durchgeführt werden:

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
    > Pool-FQDN: Der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hostet (in der Regel ein Skype for Business-Front-End-Server > oder Pool).
    > FQDN der Poolregistrierungsstelle: Der FQDN des Skype for Business Front-End-Servers oder Pools, der diesem Anwendungspool zugeordnet ist.
    > Poolwebsite: Die Standort-ID des Standorts, auf dem dieser Pool befindet.

3. Die Topologieänderungen müssen aktiviert werden. Das Aktivieren der Topologieänderungen kann über die Skype for Business Server-Verwaltungsshell ausgeführt werden, indem Das folgende Cmdlet ausgeführt wird:

   ```powershell
   Enable-CsToplogy
   ```

4. Installieren Sie bei Bedarf die Skype for Business Server 2015 Resource Kit Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).

5. Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool über eine Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anruf weiterleitungseinstellungen eines Benutzers in der Bereitstellung anzeigen zu können. Standardmäßig befindet sich das Tool in: "...\Programme\Skype for Business Server 2015\Reskit". Verwenden Sie den folgenden Befehl, um die Anruf weiterleitungseinstellungen eines Benutzers anzeigen zu können:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Die Einstellungen für die Anruf weiterleitung des Benutzers sollten angezeigt werden.

#### <a name="group-call-pickup"></a>Gruppenanrufannahme

Für die Gruppenanrufannahme ist in Skype for Business Server 2015 eine zusätzliche Konfiguration erforderlich, damit die Funktion vollständig aktiviert ist. Lesen Sie vor dem Zuweisen von Pickupgruppen zu Benutzern in der Produktdokumentation zur Gruppenanrufannahme die Planungs- und Bereitstellungsschritte dieser Funktion.

### <a name="examples"></a>Beispiele

#### <a name="display-current-call-handling-settings"></a>Aktuelle Anrufbehandlungs-Einstellungen

Der folgende Befehl zeigt die Anrufbehandlung für den Benutzer an.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> In diesem Beispiel wird die **Option /server** verwendet, um die Skype for Business Server, mit der eine Verbindung hergestellt werden soll, anzugeben.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Festlegen des Ziels "Anruf weiterleiten/Keine Antwort"

In diesem Beispiel werden das Ziel für die Weiterleitung/kein Antwort und die Ringverzögerung bestimmt. Hier wird der Switch /server nicht bereitgestellt. SEFAUtil versucht, die Skype for Business Server 2015 automatisch zuermittlungen.

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

#### <a name="enable-call-forwarding-immediately"></a>Sofortiges Aktivieren der Anruf weiterleitung

In diesem Beispiel wird sofort die Anruf-Weiterleitung an einen anderen Benutzer aktiviert.

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

#### <a name="disable-call-forwarding-immediately"></a>Deaktivieren der Anruf weiterleitung sofort

In diesem Beispiel wird die Anruf weiterleitung sofort deaktiviert.

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

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Hinzufügen eines Benutzers als Stellvertretung und Einrichten des gleichzeitigen Klingelns von Stellvertretern

In diesem Beispiel wird ein Benutzer als Stellvertretung hinzufügt und gleichzeitiges Klingeln von Stellvertretern eingerichtet.

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

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Ändern der Regel für das gleichzeitige Klingeln von Stellvertretern

In diesem Beispiel wird die im vorherigen Beispiel festgelegte Regel für das gleichzeitige Klingeln in die Regel für verzögertes Klingeln geändert.

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
> Wenn der letzte Stellvertreter entfernt wird, wird das Stellvertretungsringen automatisch deaktiviert.

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

In diesem Beispiel wird eine Stellvertretung hinzufügt und die Weiterleitung für Stellvertretungsregel eingerichtet.

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

In diesem Beispiel wird das gleichzeitige Klingeln aktiviert und eine gleichzeitig klingende Zielnummer bestimmt.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Um die gleichzeitige Klingelzielnummer eines Benutzers zu ändern, der bereits das gleichzeitige Klingeln aktiviert hat, behalten Sie den Befehl mit dem Schalter /enablesimulring bei, andernfalls wird die Zielnummer nicht geändert.

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

In diesem Beispiel wird der Teamanrufgruppe eines Benutzers ein Teammitglied hinzufügt und gleichzeitiges Klingeln für die Teamanrufgruppe aktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Durch das Hinzufügen eines Mitglieds zur Teamanrufgruppe eines Benutzers werden die gleichzeitigen Klingelgruppen der Benutzer automatisch so umschalten, dass gleichzeitig seine Teamanrufgruppe klingelt.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Entfernen eines Mitglieds aus Team-Call Gruppe

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

In diesem Beispiel wird der verzögerte Ring in die Gruppenzeiteinstellung für Teamanrufe geändert.

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

In diesem Beispiel wird der Teamanruf für einen bestimmten Benutzer aktiviert.

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

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Aktivieren der Gruppenanrufannahme und Zuweisen einer Pickupgruppe zu einem Benutzer

In diesem Beispiel wird einem Benutzer eine Pickupgruppe zugewiesen und die Gruppenanrufannahme aktiviert.

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
> Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, wird die dem Benutzer zugewiesene Gruppennummer nicht beibehalten. Wenn Sie anschließend die Gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie die Gruppennummer erneut mit der Option /enablegrouppickup zuweisen.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Beschreibung

SYSPrep.ps1 ist ein Windows PowerShell, mit dem die folgenden Skype for Business Server 2015-Voraussetzungen auf dem Windows Server 2008-Betriebssystemcomputer installiert werden.

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell Version 3.0

- Visual C++ 2010 Redistributable

- Internetinformationsserverupdates

- Windows Identity Foundation

- Skype for Business Server 2015 Core-Dateien

  Der Skriptname ähnelt zwar dem Systemvorbereitungstool für microsoft Windows Betriebssysteme, sie unterscheiden sich jedoch. Dieses Skript installiert nur die erforderlichen Voraussetzungen für Skype for Business Server 2015. Sobald diese Voraussetzungen installiert sind, kann das Windows SYSPrep-Tool verwendet werden, um ein Abbild des Servers zu erstellen.

### <a name="requirements"></a>Anforderungen

Vor dem Ausführen des SYSPrep.ps1 müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Betriebssystemcomputer Windows Server 2008 kopieren (z. B. **D:\Setup).** Dieser Ordner muss auch eine Kopie der Skype for Business Server 2015-Dateien enthalten, insbesondere **Setup.exe.** Die erforderlichen Dateien können von den folgenden Speicherorten heruntergeladen werden:


| **Voraussetzungen**                                | **Ort**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell Version 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 Redistributable  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| Internetinformationsserverupdates  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Kopieren von Skype for Business Server 2015-Medien  <br/>                   |

### <a name="parameter"></a>Parameter

Der **Parameter -SetupFolder** verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.

### <a name="examples"></a>Beispiele

Führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, SYSPrep.ps1 Ausführen des Skripts Skype for Business Server 2015 installieren:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migration nicht zugewiesener Nummernansagen
<a name="UNAM"> </a>

Das Migrationstool Nicht zugewiesene Nummernansagen ermöglicht es einem Skype for Business Server 2015-Administrator, die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung verwendet wird, aus einer Quell-Skype for Business Server oder einem Pool in einen Ziel-Skype for Business Server-Pool zu verschieben.

### <a name="description"></a>Beschreibung

Das Migrationstool Nicht zugewiesene Nummernansagen ist ein Windows PowerShell-Skript, mit dem die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung eines Quellservers oder Pools verwendet wird, auf einen anderen Server oder Pool verlagert wird.

Wenn die Ausführung ausgeführt wird, führt das Migrationsskript Nicht zugewiesene Nummernansagen die folgenden Vorgänge aus:

1. Verschieben Sie alle Audiodateien, die von den nicht zugewiesenen Nummernansagen der ankündigungsanwendung verwendet werden, die im Quellserver oder -pool gehostet werden, in den Dateispeicher des Zielservers oder -pools.

    > [!NOTE]
    > Die Audiodateien werden aus dem Quellpool entfernt, nachdem sie in den Zielpool kopiert wurden.

2. Verschieben Sie alle Nicht zugewiesenen Nummernansagen, die für die ankündigungsanwendung konfiguriert sind, die im Quellserver oder -pool gehostet wird, auf den Zielserver oder -pool.

3. Zuweisen Sie alle Bereiche nicht zugewiesener Nummern, die von der ankündigungsanwendung, die im Quellserver oder -pool gehostet wird, dem Zielserver oder -pool erneut zu.

Nach der erfolgreichen Ausführung des Skripts werden alle Bereiche nicht zugewiesener Nummern, die von der im Quellserver oder -pool gehosteten Ankündigungsanwendung verwendet wurden, jetzt mit derselben Konfiguration vom Zielserver oder -pool verwendet.

### <a name="output"></a>Ausgabe

Das **Move-CsAnnouncementConfiguration-Skript** gibt im Fenster Skype for Business Server-Verwaltungsshell an, von wo aus es den Erfolg oder Fehler des Migrationsvorgangs ausgeführt hat.

Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die nicht zugewiesenen Nummernbereiche, die erfolgreich an das Ziel verschoben wurden, im Ziel in einer betriebsbereiten Form, und die restlichen nicht zugewiesenen Nummernbereiche, die migriert werden sollen, verbleiben auch in der Quelle in einer betriebsbereiten Form. Führen Sie das Skript nach dem Beheben des Fehlers erneut aus, um den Rest der Konfiguration vollständig zu migrieren.

### <a name="purpose"></a>Zweck

Das Migrationsskript Nicht zugewiesene Nummernansagen kann in den folgenden drei Szenarien verwendet werden:

- **Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype for Business Server:** Contoso ist dabei, zu Skype for Business Server 2015 zu migrieren, und im Rahmen des Migrationsprozesses möchte der Skype for Business Server-Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung unterstützt wird, von der Lync Server 2013-Bereitstellung in die neue Skype for Business Server 2015-Bereitstellung verschieben. Zum Verschieben der Konfigurationseinstellungen verwendet Skype for Business Server Administrator das Migrationstool Nicht zugewiesene Nummernansagen.

- **Rollback einer Bereitstellung von Skype for Business Server 2015 auf Lync Server 2013:** Aufgrund unerwarteter Faktoren muss Contoso die Migration auf die neue Skype for Business Server 2015-Bereitstellung zurückrollen. Um Dienstunterbrechungen zu minimieren, verwendet der Skype for Business Server-Administrator das Migrationstool Nicht zugewiesene Nummernansagen, um die Konfiguration von der Skype for Business Server 2015-Bereitstellung auf die Lync Server 2013-Bereitstellung zurückzurollen.

- **Verschieben von Daten zwischen Bereitstellungen:** Contoso ist dabei, alle Server eines Pools durch neuere Server zu ersetzen. Ihre Strategie besteht in der Bereitstellung eines neuen Skype for Business Server 2015-Pools, dem Verschieben aller Daten aus dem alten in den neuen Pool und dem veralteten Pool. Sobald der neue Pool bereitgestellt wurde, wird das Migrationstool Nicht zugewiesene Nummernansagen verwendet, um die Konfiguration aus dem alten Pool in den neuen zu verschieben.

#### <a name="requirements"></a>Anforderungen

Für die erfolgreiche Ausführung des Tools sind die folgenden Hauptanforderungen erforderlich:

1. Das Skript muss von einem Computer ausgeführt werden, auf dem Skype for Business Server Verwaltungsshell installiert ist.

2. Die Ankündigungsanwendung muss erfolgreich in der Quell- und Zielanwendung Skype for Business Oder Pools bereitgestellt werden.

#### <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration Skript

Das Move-CsAnnouncementConfiguration erfordert die beiden Parameter, die in der folgenden Tabelle beschrieben sind.

![Move-CsAnnouncementConfiguration Parameter.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Beispiele

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Verschieben der Konfiguration nicht zugewiesener Nummernansagen aus einem Lync Server 2013-Pool in einen Skype for Business Server 2015-Pool

In diesem Beispiel werden die Nicht zugewiesenen Nummernansagen aus dem Quellpool (Lync Server 2013) in den Zielpool (Skype for Business Server 2015) verlagert.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Verschieben der Konfiguration nicht zugewiesener Nummernansagen aus einem Skype for Business Server 2015-Pool in einen Lync Server 2013-Pool

In diesem Beispiel werden die Nicht zugewiesenen Nummernansagen aus dem Quellpool (Skype for Business Server 2015) in den Zielpool (Lync Server 2013) verlagert.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Web Conf Data
<a name="WebConfData"> </a>

Das Web Conf Data Tool ermöglicht einem Administrator der Skype for Business Server 2015-Kommunikationssoftware, mehr Kontrolle über die Daten zu haben, die den Webkonferenzen eines Organisators zugeordnet sind. Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers basierend auf einem Zeitstempelkriterium zu löschen.

### <a name="description"></a>Beschreibung

Mit diesem Tool kann der Administrator die folgenden Vorgänge ausführen:

1. Suchen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

2. Löschen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

3. Löschen Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, der älter als ein bestimmtes Datum ist.

4. Verschieben Sie alle Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.

    > [!NOTE]
    > Die Resource Kit Tools für Lync Server 2010 unterstützten das Verschieben aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird. Diese Funktionalität ist nun von diesem Tool zugunsten des **Parameters MoveConferenceData veraltet.** Weitere Informationen zu diesem Parameter finden Sie im [Cmdlet Move-CsUser.](/powershell/module/skype/move-csuser?)

Das Tool löscht Besprechungsdaten nur für inaktive Besprechungen. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.

Dieses Tool muss von einem Computer ausgeführt werden, der sich im gleichen Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im gleichen Benutzerpool verwaltet werden.

### <a name="output"></a>Ausgabe

Dieses Tool gibt die Ergebnisse der einzelnen Vorgänge aus:

- Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, die diesen Benutzer als Organisator haben.

- Wenn ein Löschprogramm ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.

### <a name="requirements"></a>Anforderungen

Das Tool muss in demSelben Pool ausgeführt werden, in dem der Organisator derzeit erstellt wird.

Das Tool muss mithilfe von Administratorrechten mit Zugriff auf die Inhaltsdatei ausgeführt Store.

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

Das vorherige Beispiel ist ein Beispiel für einen Löschbefehl. Mit dem Befehl löschen werden alle inaktiven Besprechungsordner aus diesem Benutzer entfernt.

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine genauere Kontrolle über Konferenzdaten benötigen.
