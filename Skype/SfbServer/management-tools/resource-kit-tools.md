---
title: Dokumentation zu Skype for Business Server 2015 Resource Kit-Tools
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
description: In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit unterstützt IT-Administratoren bei der Bereitstellung und Verwaltung von Skype for Business Server 2015 bei der Vereinfachung von Routineaufgaben. Beispielsweise kann das Tool webconf-Daten verwendet werden, um Daten, die von Benutzern während einer Onlinebesprechung hochgeladen werden, ganz einfach zu steuern. Das SEFAUtil-Tool kann zum Einrichten von Delegate-Anrufweiterleitung und-Beantwortung für Benutzer verwendet werden. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.
ms.openlocfilehash: 7269d7c82736be8e533a0782548a94d14aafcfb5
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160769"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Dokumentation zu Skype for Business Server 2015 Resource Kit-Tools

In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit unterstützt IT-Administratoren bei der Bereitstellung und Verwaltung von Skype for Business Server 2015 bei der Vereinfachung von Routineaufgaben. Beispielsweise kann das Tool **webconf-Daten** verwendet werden, um Daten, die von Benutzern während einer Onlinebesprechung hochgeladen werden, ganz einfach zu steuern. Das **SEFAUtil** -Tool kann zum Einrichten von Delegate-Anrufweiterleitung und-Beantwortung für Benutzer verwendet werden. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Um das Skype for Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit. msi](https://www.microsoft.com/download/details.aspx?id=52631) aus dem Download Center herunter.

Führen Sie **OCSResKit. msi** aus, um eine einfache Installation durchzuführen. Die MSI-Installation aller Tools im folgenden Pfad: **% Program Files%\Skype for Business Server 2015 \ reskit**. Tools mit eigenständigen ausführbaren Dateien befinden sich in diesem Ordner. Tools, die auch unterstützende Dateien haben, befinden sich in ihren eigenen Unterordnern.

## <a name="supported-environments"></a>Unterstützte Umgebungen

Das Skype for Business Server 2015 Resource Kit sollte auf einem Server installiert sein, der die für Skype for Business Server 2015 erforderlichen Spezifikationen erfüllt, in der Regel wird Skype for Business Server 2015 ausgeführt.

## <a name="resource-kit-tools-overview"></a>Resource Kit-Tools (Übersicht)

Im folgenden finden Sie eine Liste der im Skype for Business Server 2015 Resource Kit bereitgestellten Tools. Die folgenden Abschnitte enthalten eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispiel Verwendung.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Bandbreitenrichtlinie-Dienst Monitor](resource-kit-tools.md#bpsm)

- [Bandbreiten Auslastungsanalyse](resource-kit-tools.md#bua)

- [Parkometer aufrufen](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importieren von Speicherdienst Daten](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Lookup-Benutzerkonsole](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Netzwerk Konfigurationsanzeige](resource-kit-tools.md#NCV)

- [Reaktionsgruppen-Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep. ps1](resource-kit-tools.md#SYSPrep)

- [Migration nicht zugewiesener Nummern Ankündigungen](resource-kit-tools.md#UNAM)

- [Webconf-Daten](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in Skype for Business Server 2015 anpassen können. Mit diesem Tool können Skype for Business Server 2015 Administratoren auch die Standardeinstellungen für den Adressbuchdienst wiederherstellen.

### <a name="description"></a>Beschreibung

ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory-Domänendienste Attribute konfigurieren können, die sich auf den Adressbuchdienst beziehen.

Die primären Szenarien für das Tool lauten wie folgt:

- Damit Administratoren den Attributen für Skype for Business Server 2015 Attribute in Active Directory-Domänendienste zuordnen können.

- Damit Administratoren das Active Directory-Domänendienste Attribut angeben können, das in die Adressbuchdienst Dateien eingeschlossen oder ausgeschlossen werden soll.

- Damit Administratoren Standardeinstellungen für den Adressbuchdienst wiederherstellen können.

Das ABSConfig-Tool kann mithilfe der Datei ABSConfig. exe gestartet werden. Das Tool wird auf der Registerkarte **Configure Attributes** geöffnet. Diese Tabelle enthält Optionen zum Zuordnen Active Directory-Domänendienste Attribute zu den Attributfeldern für Skype for Business Server 2015 und zum Angeben der Benutzer, die in Adressbuchdienst Dateien basierend auf bestimmten Attribut Filtern eingeschlossen oder ausgeschlossen werden sollen. Außerdem gibt es Optionen, um den Wert der Telefonnummer anzupassen, der in die Adressbuchdatei aufgenommen werden soll. Die Option **Standardeinstellungen wiederherstellen** ermöglicht Administratoren das Wiederherstellen von Einstellungen für den Adressbuchdienst auf Standardwerte.

> [!NOTE]
> Das erneute Zuordnen von AD-Attributen zu unterschiedlichen OC-Feldnamen funktioniert nur beim Herunterladen von Adressbuchdateien und wird von der Adressbuch-Webabfrage nicht unterstützt.

### <a name="output"></a>Output

In ABSConfig wird die Konfiguration des Adressbuchdiensts in der Datenbank gespeichert.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Zweck

ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen Skype for Business Server 2015 Adressbuchdiensts.

### <a name="requirements"></a>Anforderungen

#### <a name="computer"></a>Computer

ABSConfig kann nur von einem Computer ausgeführt werden, der der Domäne angehört und auf dem Skype for Business Server 2015 installiert ist. Im Fall von Skype for Business Server 2015 Enterprise Edition kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.

#### <a name="network"></a>Netzwerk

Der Computer sollte in der Lage sein, eine Verbindung mit der Front-End-Pool-und Back-End-Datenbank herzustellen.

#### <a name="software"></a>Software

Die folgenden Softwarekomponenten müssen installiert sein, bevor Sie das ABSConfig-Tool ausführen:

- Skype for Business Server 2015

#### <a name="users"></a>Benutzer

Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der Skype for Business Server 2015-Bereitstellung verfügen.

### <a name="examples"></a>Beispiele

ABSConfig kann gestartet werden, indem Sie **ABSConfig. exe** an einer Eingabeaufforderung eingeben. Unten sehen Sie die Benutzeroberfläche des ABSConfig-Tools.

![Das Tool ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Zusammenfassung

Mit dem ABSConfig-Tool können Administratoren schnell und einfach Tools verwenden, um Skype for Business Server 2015 Adressbuchdienst anzupassen.

## <a name="bandwidth-policy-service-monitor"></a>Bandbreitenrichtlinie-Dienst Monitor
<a name="bpsm"> </a>

Das Tool Bandbreitenrichtlinien-Dienstüberwachung soll Administratoren die Möglichkeit geben, eine Liste der folgenden anzuzeigen:

1. Alle konfigurierten Skype for Business Server 2015 Bandbreitenrichtlinien Dienste (Authentifizierung und Kern) in der Topologie

2. Die Verbindungen, die von jedem Dienst für andere Bandbreitenrichtlinien Dienste und für die Edgeserver erstellt werden

3. Alle Links, die im Netzwerk Konfigurationsdokument konfiguriert sind, sowie die Echtzeitbandbreite, die von den einzelnen Bandbreitenrichtlinien Diensten gemeldet werden

### <a name="description"></a>Beschreibung

Das Tool Bandwidth Policy Service Monitor wird als GUI-basierte Anwendung implementiert. Administratoren starten das Tool durch Ausführung von PDPMonUI. exe.

Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreitenrichtlinien Dienste in der Topologie zu ermitteln. Nachdem die anfängliche Aktualisierung abgeschlossen ist, wird der Bereich links neben dem Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen Sie gehören.

Wenn Administratoren einen bestimmten bandbreitenrichtliniendienst auswählen, zeigt der Bereich auf der rechten Seite die Informationen zu diesem bestimmten Dienst an. Dieser Bereich verfügt auch über zwei Hauptregisterkarten, in denen Informationen angezeigt werden.

#### <a name="machine-info-tab"></a>Registerkarte "Machine Info"

Auf der Registerkarte **Computer Informationen** werden die Details des ausgewählten Bandbreitenrichtlinien Diensts sowie die Liste und der Status aller Verbindungen angezeigt, die vom ausgewählten bandbreitenrichtliniendienst für andere Dienste vorgenommen wurden.

#### <a name="topology-info-tab"></a>Registerkarte "Topologieinformationen"

Auf der Registerkarte **Topologieinformationen** wird eine Liste aller Links angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jeden Link wird die Kapazität der Audio-und Videobandbreite angezeigt. Darüber hinaus wird die derzeit verwendete Bandbreite sowohl in Kbit/s als auch als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierung, um Links hervorzuheben, deren Auslastung der Kapazität nahe liegt, sodass Administratoren solche Links schnell isolieren können.

> [!NOTE]
>  Wenn beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreitenrichtlinien Dienste beim bandbreitenrichtliniendienst Monitor ein Fehler auftritt, werden die Informationen in den Registerkarten **Computer Info** und **Topologieinformationen** nicht aufgefüllt. Es kann jedoch sein, dass das Tool anfänglich eine Verbindung herstellen kann, aber die Verbindung mit dem Dienst anschließend verloren geht. In diesen Fällen werden Administratoren möglicherweise veraltete Informationen angezeigt. Auf jeder Registerkarte gibt es einen **letzten aktualisierten** Zeitstempel, mit dem Administratoren sehen können, wann die Daten zuletzt für einen bestimmten bandbreitenrichtliniendienst aktualisiert wurden.

### <a name="output"></a>Output

Es gibt keine Befehlszeilenausgabe; die Programmausgabe ist in der Haupt grafischen Benutzeroberfläche (Graphical User Interface, GUI) enthalten.

### <a name="purpose"></a>Zweck

Der Zweck des Bandwidth Policy Service Monitor-Tools besteht darin, Administratoren Einblick in den Status der einzelnen Bandbreitenrichtlinien Dienste zu gewähren, die in der Topologie definiert sind. Darüber hinaus können Administratoren die Echtzeitbandbreite für alle im Netzwerk Konfigurationsdokument definierten Links sehen.

### <a name="requirements"></a>Anforderungen

Das Tool für Bandbreitenrichtlinien-Dienstüberwachung muss auf einem Computer ausgeführt werden, der Teil der Skype for Business Server Topologie ist.

### <a name="summary"></a>Zusammenfassung

Das Tool Bandbreitenrichtlinien-Dienstüberwachung kann eine wertvolle Ressource für Administratoren sein, damit Sie den Status aller Bandbreitenrichtlinien Dienste in der Topologie überprüfen können-und was noch wichtiger ist-Sie können eine Echtzeitbandbreite für die Links erhalten, die in den Netzwerkkonfigurationseinstellungen definiert.

## <a name="bandwidth-utilization-analyzer"></a>Bandbreiten Auslastungsanalyse
<a name="bua"> </a>

Bandwidth Auslastung Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Diese Berichte können verwendet werden, um das aktuelle Muster der Bandbreitennutzung zu verstehen und die Planung von Bandbreitenkapazitäten zu unterstützen.

### <a name="description"></a>Beschreibung

Bandbreiten Auslastungsanalyse wird als GUI-basierte Anwendung implementiert. Dieses Tool generiert Berichte speziell für die audionutzung im gesamten Netzwerk und hilft bei der Kapazitätsplanung. Außerdem wird die Bandbreitenkapazität durchlaufen, die verschiedenen Links zugewiesen ist.

### <a name="output"></a>Output

Bandbreiten Auslastungsanalyse bietet Grafik Al-Plots mit Bandbreitenkapazität und-Nutzung für alle im System konfigurierten WAN-Verbindungen.

### <a name="purpose"></a>Zweck

In jeder sprach-und Videobereitstellung ist es wichtig, den Trend der Bandbreitenauslastung des Mediendaten Verkehrs im gesamten Unternehmensnetzwerk zu überwachen und zu verstehen. Das Tool Bandbreiten Auslastungsanalyse ermöglicht es einem Administrator, genau dies zu erreichen. Dieses Tool führt folgende Schritte aus:

- Generiert spezifische Berichte für die audionutzung im gesamten Netzwerk

- Hilft bei der effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Links zugeordnet ist.

Bandbreiten Auslastungsanalyse kann grafische Plots von Bandbreitenkapazität und Auslastungsberichten generieren. Dabei handelt es sich um folgende:

- Alle WAN-Verbindungen im Unternehmensnetzwerk

- Gefiltert nach ausgewählten WAN-Verbindungen, die ausgewählt wurden

- Gefiltert nach WAN-Verbindungen, die die Link Kapazität überschritten haben

- Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite unter Verwenden

- Filtern nach WAN-Verbindungen, die kritische Ebenen erreicht haben (Bandbreitenauslastung, die größer ist als 90% der Bandbreitenkapazität der WAN-Verbindung)

- Gefiltert nach WAN-Linktyp – Netzwerkstandort Verknüpfungen, interregionale Links und Links innerhalb eines Standorts

- Gefiltert nach netzwerkregion

#### <a name="applications"></a>Applications

Bandbreiten Auslastungsanalyse verfügt über die beiden folgenden Anwendungen (Tools):

- **"Wanlinklogcollector. exe** mit diesem Tool können die Benutzer die erforderlichen Informationen eingeben.

- **"Bandwidthutilizationanalyzer. xlsm** ein Microsoft Excel-Tabellenkalkulationssoftware Bericht wird automatisch von" wanlinklogcollector. exe gestartet. Diese Anwendung ermöglicht dem Benutzer das Anwenden von Filtern auf den Bericht, wie weiter unten in diesem Artikel dargestellt.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phasen der Verwendung des Analyseprogramms für Bandbreitenauslastung

Es gibt zwei Phasen bei der Verwendung des Bandbreiten Auslastungsanalyse Programms:

- Sammeln von Protokollen, die mithilfe von "wanlinklogcollector. exe ausgeführt werden

- Anpassen von Berichten, die mithilfe von "bandwidthutilizationanalyzer. xlsm ausgeführt werden

    > [!IMPORTANT]
    > Es wird dringend empfohlen, dass "bandwidthutilizationanalyzer. xlsm nicht von Endbenutzern manuell gestartet wird.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Starten der Bandbreiten Auslastungsanalyse

Starten Sie "wanlinklogcollector. exe an der Eingabeaufforderung oder mithilfe von Windows Explorer.

 **Verwenden von "wanlinklogcollector. exe**

Es gibt drei Schritte zur Verwendung von "wanlinklogcollector. exe:

1. **Protokollieren des Zeitplans** Geben Sie die Zeitachse an, für die der Bericht generiert werden muss.

2. **Angeben der Dateiverzeichnisse** Angeben von Dateispeicherort Informationen

3. **Erfassen der Protokolle und Starten der Berichtsanzeige** Ausführen des Befehls zum Generieren des Berichts

#### <a name="step-1---log-the-timeline"></a>Schritt 1 – Protokollieren der Zeitachse

Durch die Protokollierung der Zeitachse kann der Benutzer des Tools Folgendes angeben: wie in der Abbildung unten dargestellt.

1. **Start Datum** Dies ist der Anfangstermin des Zeitplans, für den der Bericht generiert werden soll. Beispiel: August 1, 2010.

2. **Enddatum** Dies ist das Enddatum des Zeitplans, für den der Bericht generiert werden soll. Beispiel: 30. September 2010.

     ![Start-und Enddatum in der Bandbreitenauslastung A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Schritt 2 – angeben der Dateiverzeichnisse

Die folgenden Dateiverzeichnisse können vom Benutzer wie dargestellt angegeben werden.

- **Speicherort der Server Protokolldateien** Der Speicherort des Ordners, in dem die Bandbreitenrichtlinien Serverprotokolle gespeichert werden. Dies ist in der \<Regel in\> \\ Fileserver<Auswahl\>von FE \AppServerFiles\PDP.

- **Speicherplatz für temporäre Dateien** Der temporäre Dateispeicherort, an dem zwischen Dateien gespeichert werden, während der Bericht generiert wird.

    ![Dateiverzeichnisse in der Bandbreitenauslastung Anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > Stellen Sie sicher, dass der Benutzer des Tools über einen ausreichenden Dateizugriff auf die Serverprotokolle und den temporären Dateispeicherordner verfügt.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Schritt 3: Erfassen der Protokolle und Starten der Berichtanzeige

Um die Protokolle zu sammeln und die Berichtsanzeige zu starten, klicken Sie wie unten gezeigt auf **Ausführen** . In diesem Schritt werden die erforderlichen Daten erfasst.

![Sammeln von Daten in der Bandbreitenauslastung Anal](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Wenn die Eingabeüberprüfung erfolgreich ist, wird die unten gezeigte Meldung angezeigt.

![Protokolliert erfasste Benachrichtigung in der Bandbreite utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Klicken Sie auf **OK**. "Bandwidthutilizationanalyzer. xlsm wird automatisch gestartet. Befolgen Sie die Anweisungen im Meldungsfeld. Ausführliche Informationen finden Sie unter **using "bandwidthutilizationanalyzer. xlsm** im nächsten Abschnitt.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Verwenden von "bandwidthutilizationanalyzer. xlsm

1. Wenn "bandwidthutilizationanalyzer. xlsm automatisch gestartet wird, klicken Sie wie unten gezeigt auf **Aktualisieren** .

     !["Bandwidthutilizationanalyzer. xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Wenn ein Datei Ordner geöffnet wird, wählen Sie konsolidiert. CSV aus dem Speicherort aus, der im Meldungsfeld angegeben ist, wie unten dargestellt. Außerdem wird der Speicherort als **C:\temp**angezeigt.

     ![Öffnen eines Ordners in "bandwidthutilizationanalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Klicken Sie auf **Importieren**.

4. Die grafische Darstellung wird automatisch generiert. Sie ist verfügbar, wenn der Zeiger für die Hintergrundarbeit ausgeblendet wird.

     ![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Anwenden von Filtern auf die Berichtsansicht

Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden wie folgt beschrieben:

![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Name** Nach WAN-Links Filtern (der Filter befindet sich auf der rechten Seite des Diagramms). Das Präfix kennzeichnet die folgenden Verknüpfungstypen; Siehe vertikales Feld (blau):

   - **S-Website** Die WAN-Verbindung von einem Netzwerkstandort zu einer netzwerkregion

   - **Ist Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten

   - **R Inter-Region** Die WAN-Verbindung zwischen zwei netzwerkregionen

2. **Überschreitungs Grenzwert** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mehr als die Bandbreitenkapazität beträgt

3. **Kritische Ebenen** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung 90% oder mehr als die Bandbreitenkapazität erreicht hat

4. Nicht **ausgelastet** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25% der Bandbreitenkapazität beträgt

5. **Verknüpfungstyp** Filtern Sie nach den folgenden WAN-Verbindungstypen:

   - Typ des **Netzwerkstandorts**

   - **Standortübergreifender** Typ

   - **Zwischen Regionen-Linktyp**

6. **Region** Nach netzwerkregion Filtern

Die folgenden Abbildungen zeigen die zuvor beschriebenen Filter.

Nach **Name**filtern. Wählen Sie die Liste der Links aus, die im Diagramm angezeigt werden müssen.

![Filtern nach Namen in "bandwidthutilizationanalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtern nach **überschreitungs Grenzwert**. Wählen Sie **true** aus, um den Filter zu erzwingen.

![Filterung nach Überschreitung des Grenzwerts.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Nach **kritischen Ebenen**filtern. Wählen Sie **true** aus, um den Filter zu erzwingen.

![Filtern nach kritischen Ebenen.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtern nach **unter verwendet**. Wählen Sie **true** aus, um den Filter zu erzwingen.

![Filterung nach unter verwendet.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Nach **Linktyp**filtern. Wählen Sie die Typen aus, die angezeigt werden sollen.

![Filterung nach Linktyp.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Verknüpfungen angezeigt werden müssen.

![Filtern nach Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Anforderungen

- Die Microsoft .NET Framework 3.5

- Microsoft Excel 2010 oder Excel 2007

### <a name="summary"></a>Zusammenfassung

Bandbreiten Auslastungsanalyse wird verwendet, um die Nutzung der Audiobandbreite für UC-Datenverkehr über das Netzwerk darzustellen. Dieses Tool kann verwendet werden, um die Nutzung der Videobandbreite auch im Netzwerk zu melden.

## <a name="call-parkometer"></a>Parkometer aufrufen
<a name="callpark"> </a>

Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Orbit-Datenbank für das Parken von Anrufen bietet.

### <a name="description"></a>Beschreibung

Call Parkometer ist ein Tool zum Nachverfolgen von zurzeit geparkten anrufen. Außerdem werden Statistiken zu Orbits und zur Verwendung durch den Anruf Park Server (CPS) gesammelt. Dieses Befehlszeilentool bietet sowohl Lese-als auch Schreibzugriff auf die CPS-Umlaufbahn SQL Server Datenbank von einem lokalen oder Remote verbundenen Computer.

Alle Optionen schließen sich gegenseitig aus. Die Befehlszeilensyntax lautet wie folgt:

- **-o-** Parameter – listet alle orbitbereiche auf, die für diesen Pool konfiguriert sind.

- **-n-** Parameter – listet alle aktuell verwendeten Umlaufbahnen in diesem Pool auf. Die angezeigten Informationen lauten wie folgt:

  - SIP-URI (Uniform Resource Identifier) der parkee und Parker.

  - Hostname des CPS, in dem der Anruf geparkt wird.

  - Zeitstempel des Zeitraums, in dem der Anruf geparkt wurde.

- **-f-** Parameter – listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf.

- **-r \<n\> ** Parameter – listet die \<n\> zuletzt geparkten Anrufe auf. Die angezeigten Informationen lauten wie folgt:

  - SIP-URI des geparkten.

  - Parker-SIP-URI.

  - Hostname des CPS, in dem der Anruf geparkt wurde.

  - Zeitstempel für den Zeitpunkt, zu dem der Anruf abgerufen oder gelöscht wurde.

- **-t\<n\> ** Parameter-testet das Reservieren einer Umlaufbahn in der Datenbank, um die Zufälligkeit der zugewiesenen Umlaufbahn Nummern anzuzeigen.

### <a name="output"></a>Output

Abhängig von den Eingabeparametern, die an einer Eingabeaufforderung angegeben werden, zeigt Call Parkometer die folgende Ausgabe an:

- Alle Umlaufbahn Bereiche, die für diesen Pool konfiguriert sind

- Zurzeit geparkte Anrufe

- Anzahl freier (verfügbarer) Umlaufbahnen

- Zuletzt geparkte Anrufe

- Reservierte Umlaufbahnen zum Testen von einheitlichen und zufälligen Umlaufbahn Werten

### <a name="purpose"></a>Zweck

Der Zweck des CPS-Tools besteht darin, den Befehlszeilenzugriff auf die CPS-Datenbank bereitzustellen. Der Administrator kann die CPS-Verwendung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.

### <a name="requirements"></a>Anforderungen

Es gibt keine Anforderungen, wenn dieses Tool auf demselben Computer ausgeführt wird, auf dem CPS ausgeführt wird. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von Skype for Business Server 2015 verwendete SQL Server Datenbank so konfiguriert werden, dass der Remotezugriff zulässig ist. Der Aufruf Parkometer muss mit einer SQL Server Datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem SQL Server des Pools herzustellen. Diese SQL Server Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer. exe. config**definiert. Es muss sich in demselben Verzeichnis befinden, in dem sich parkometer. exe befindet. Die folgende XML-Datei ist ein Beispiel für eine parkometer. exe. config. Die Parameter, die konfiguriert werden müssen, sind Benutzername (beispielsweise mydomain\Administrator), Kennwort (beispielsweise mypassword) und Hostname (beispielsweise MyServer).

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

Bereitgestellte Umlaufbahn Bereiche: der-o-Parameter listet alle orbitbereiche auf, die für diesen Pool konfiguriert sind (siehe Abbildung).

![Orbitbereiche in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Zurzeit geparkte Anrufe: der Parameter-n listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf (siehe Abbildung).

![Zurzeit geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Anzahl der freien Umlaufbahnen: der-f-Parameter listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf (siehe Abbildung).

![Freie Umlaufbahnen in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Zuletzt geparkte Anrufe: der Parameter \<-\> r n listet \<die\> n zuletzt geparkten Anrufe wie dargestellt auf.

![Zuletzt geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Test Orbit-Reservierung: der- \<t\> n-Parameter testet, wie in der Abbildung gezeigt, eine Umlaufbahn in der Datenbank reserviert

![Testen Sie die Orbit-Reservierungen in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Zusammenfassung

Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Server für das Parken von Anrufen bereitstellt.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Beschreibung

Dbanalyze ist ein Befehlszeilentool, mit dem Administratoren Analyseberichte zu den Skype for Business Server 2015 Datenbanken sammeln können. Dbanalyze verfügt über die folgenden Modi: Diagnose, Benutzerdaten, Konferenz, MCU und Datenträgerfragmentierung:

- **Diagnosemodus** Erstellt einen Bericht mit Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten-und Protokolldateigrößen, die letzte Sicherungszeit, die Kontaktverteilung zwischen Servern mit Microsoft Office Communications Server, die durchschnittliche Anzahl von Berechtigungen, Kontakte, Container, Abonnements, Publikationen, Endpunkte pro Benutzer, nicht ordnungsgemäß verwaltete Benutzer, Benutzer, die nicht weitergeleitet werden können, die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, geplante Konferenzen, aktive Konferenzen, und die Datenbankversion.

    > [!NOTE]
    > Die Ausführung des Diagnosemodus kann sich auf die Serverleistung auswirken.

- **Benutzerdaten Modus** Meldet Kontakt-, Container-, Abonnement-, Publikations-, Berechtigungs-und Kontaktgruppen Daten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in seinen Kontakt-und Berechtigungslisten haben. In diesem Modus werden auch Zusammenfassungsdaten für Konferenzen gemeldet, die ein Benutzer organisiert oder dazu eingeladen wird.

- **Konferenzmodus** Meldet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Terminplanzeit Details für die Konferenz, der Einladungsliste, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCU (Multipoint Control Units), der aktiven Teilnehmerliste und des Signalisierungs Status jedes Teilnehmers.

- **Decodieren der Besprechungs-ID** Decodiert eine PSTN-Besprechungs-ID (Public Switched Telephone Network), die durch den **Parameter/pstnid** -Switch angegeben wird, aber keine Verbindung zum Back-End für detaillierte Informationen.

- **Konferenz auflösen** Decodiert eine von der **Parameter/pstnid** -Option angegebene PSTN-Besprechungs-ID und zeigt Informationen über die durch die ID angegebene Konferenz an.

- **MCU-Modus** Meldet die ID, den Medientyp, die URL, den Takt Status, die Konferenz Last und die Teilnehmer Auslastung für jede MCU im Pool.

- **Datenträger Fragmentierungs Modus** Zeigt den Fragmentierungs Status aller Datenträger an.

Dieses Tool kann verwendet werden, um verschiedene Probleme zu diagnostizieren oder Administratoren bei der Kapazitätsplanung zu unterstützen. Wenn beispielsweise die meisten der Benutzer, die sich auf dem Server a befinden, Benutzer auf Server b als Kontakte verwaltet haben, kann der Administrator die Benutzer auf Server a auf Server b umstellen, um den serverübergreifenden Datenverkehr zu reduzieren.

### <a name="output"></a>Output

Dieses Tool gibt vordefinierte Berichte zur Skype for Business Server 2015 Datenbank aus. **Pfad**:%ProgramFiles%\Skype for Business Server 2015 \ reskit

### <a name="purpose"></a>Zweck

Um Dbanalyze. exe zu installieren, kopieren Sie Sie in einen lokalen Ordner, und führen Sie das Tool aus. Führen Sie den folgenden Befehl an der Befehlszeile aus, um das Tool zu verwenden. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Die Beschreibungen der Befehlszeilenoptionen werden unten angezeigt.

![Befehlszeilenoptionen für Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Anforderungen

 **Computer** Dbanalyze kann nur von einem Computer ausgeführt werden, der der Domäne angehört und auf dem Skype for Business Server 2015 installiert ist.

 **Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.

 **Software** Skype for Business Server 2015 Softwarekomponenten müssen vor dem Ausführen von Dbanalyze installiert werden.

 **Benutzer** Die folgende Tabelle zeigt die Administratoren, die über die erforderlichen Berechtigungen für den Zugriff auf Skype for Business Server 2015-Datenbanken verfügen.

![Berechtigungstabelle für Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Für/Report ist ein lokales Administratorkonto erforderlich **: Datenträger** Modus.

### <a name="examples"></a>Beispiele

Im folgenden sind Beispiele für gültige Dbanalyze. exe-Befehle aufgeführt:

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Zusammenfassung

Dbanalyzer bietet Administratoren eine schnelle und einfache Analyse Skype for Business Server 2015 Datenbanken.

## <a name="import-storage-service-data"></a>Importieren von Speicherdienst Daten
<a name="Issd"> </a>

Das ImportStorageServiceData Resource Kit-Tool ermöglicht das erneute Importieren von Warteschlangen-und Endpunkt Daten, die aus dem Speicherdienst (LYSS) wieder in den Speicherdienst geleert wurden.

### <a name="description"></a>Beschreibung

Die aus dem Speicherdienst gelöschten Daten konnten auf der Grundlage des Warteschlangenelement Status oder der Datenbankgröße automatisch (regelmäßig) sein. Möglicherweise ist dies auf den manuellen Aufruf des Cmdlets "Pool Failover" oder auf das StorageServiceFullFlush-Cmdlet zurückzuführen, das vom Pool-Failover-Cmdlet aufgerufen wird. Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn sich die Datenbankgröße des Speicher Diensts (LYSS) auf den Front-Ends über der normalen Ebene befindet, da dies wahrscheinlich dazu führt, dass mehr Daten zurück exportiert werden. Außerdem sollten alle Probleme, die zu Fehlern beigetragen haben, die dazu geführt haben, dass die Speicherdienst Warteschlange ansteigt, zuerst aufgelöst werden (beispielsweise Exchange-Endpunkt Fehler, Netzwerkprobleme oder andere Probleme).

 **Szenario 1:** während des Pool Failovers können Dateien für jedes Front-End aus dem Speicherdienst geleert werden. Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.

 **Szenario 2:** die Daten werden jeden Tag automatisch oder als Reaktion auf die Speicherdienst Datenbank geleert, die bestimmte größenschwellenwerte überschreitet (beispielsweise 60%, 80%, 90% vollständig). Diese automatisch gespülten Daten sollten vom Administrator routinemäßig erneut importiert werden. Wenn das Monitoring-SCOM-Paket nicht bereitgestellt ist, gibt es in der obigen Situation Ereignisse für Skype for Business Server Speicherdienst, die sich auf Daten beziehen, die vom Speicherdienst geleert werden. Ereignis-IDs von 32075 (vollständiger Löschvorgang wird gestartet), 32076 (vollständiger Flush wurde abgeschlossen), 32082 (Wartungsebene wurde gestartet), 32083 (Wartungsebene ist leer), 32089 (Flush erfolgte aufgrund des Füllens der Datenbank). Hinweis Diese Ereignis-IDs entsprechen der RTM-Version. Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien geleert wurden. Diese Daten sollten mit diesem Tool routinemäßig wieder importiert werden, beispielsweise einmal pro Woche.

Wenn für die Online Dienstversion die SCOM Pack for Skype for Business Server-Integritätsüberwachung bereitgestellt wird, werden möglicherweise neue Warnungen ausgelöst, die den Administrator auffordern, die gelöschten Daten wieder in den Speicherdienst zu importieren. Im Ereignisprotokoll auf dem Front-End-Server, der die Warnung ausgelöst hat, ist ein entsprechendes Ereignis vorhanden. Das Ereignis gibt eine Beschreibung des übergeordneten Pfads an, unter dem sich die geleerten Datendateien befinden, sowie die Anzahl der Dateien, die den Warnungskriterien entsprechen. Die Warnungskriterien sind, dass es x oder mehr Dateien unter dem bestimmten übergeordneten Pfad gibt, die mindestens Y Tage alt sind (wobei x und y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei außer Kraft gesetzt werden können). Im folgenden werden zwei Beispiele für Ereignisse angezeigt, die die Integritäts Warnung auslösen können: der Unterschied ist der übergeordnete Pfad. Eine Möglichkeit besteht unter Webdienst-Dateifreigabe, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist. (beispielsweise c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService). Der Administrator führt dann dieses reskit-Tool aus.

Dieses Tool erhöht die CPU-und e/a-Last auf dem Front-End, auf dem es ausgeführt wird, sowie anderen Front-Ends in der Situation, dass die Daten nicht dem Front-End gehören, auf dem das Tool ausgeführt wird. Es wird empfohlen, dieses Tool Ausführung, wenn die Front-Ends nicht unter starker CPU-und e/a-Last stehen, beispielsweise außerhalb der Spitzenzeiten. Zweitens kann dieses Tool 2 bis 3 Minuten, um eine Datendatei zu importieren. Beachten Sie dies, wenn Sie schätzen, wie lange das Tool in Betrieb sein wird. Die vom Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt. Löschen Sie es, wenn keine Fehler gemeldet werden, da die Protokolldatei zehn MB oder mehr sein kann.

![Beispiele für Ereignisprotokoll Ereignisse des Speicherservers.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Anforderungen

Installieren Sie die Skype for Business Server 2015 Resource Kit-Tools. Das Tool wird auf Computern mit Domänenbeitritt ausgeführt, auf denen Skype for Business Server und Skype for Business Server Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist. Diese Datenbank wird vom Tool zum Abrufen des Speicherorts der Webservice-Dateifreigabe für den Pool verwendet. Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools Windows PowerShell Remoting mithilfe von **enable-PSRemoting** auf jedem Front-End-Server und dem Computer, von dem aus das Tool ausgeführt wird, aktivieren. Andernfalls tritt für Remote Windows PowerShell-Befehle dieses Tools ein Fehler auf. Windows PowerShell Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem Sie fertig gestellt wurde. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über Lese-/Schreibzugriff auf die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird. Andernfalls kann das Tool mit e/a-Berechtigungsfehlern fehlschlagen.

> [!NOTE]
> In Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht auf dem Betriebssystem Windows Server 2008.

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

Das LCSSync-Tool hilft bei der Bereitstellung Skype for Business Server 2015 Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen. Dieses Tool dient zum Synchronisieren von Benutzern und Gruppen aus unterschiedlichen Benutzergesamtstrukturen als Active Directory-Domänendienste Kontaktobjekt mit einer zentralen Gesamtstruktur, in der Skype for Business Server 2015 installiert ist.

### <a name="description"></a>Beschreibung

 LCSSync verwendet die synchronisierten Active Directory-Domänendienste Contact-Objekte in der zentralen Gesamtstruktur, um Benutzer für Skype for Business Server zu aktivieren. Um die einmalige Anmeldung bereitstellen zu können, muss das primäre Benutzerkonto dem Active Directory-Domänendienste Contact-Objekt in der zentralen Gesamtstruktur für Skype for Business Server 2015 zugeordnet werden. Dieses Tool unterstützt Sie bei der Durchführung dieser Zuordnung. Dieses Tool enthält Vorlagen zum Erstellen von Verwaltungs-Agents auf dem Microsoft Identity Integration Server.

### <a name="summary"></a>Zusammenfassung

Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015 in einer Umgebung mit mehreren Gesamtstrukturen.

## <a name="lookup-user-console"></a>Lookup-Benutzerkonsole
<a name="LUC"> </a>

Das LookupUserConsole-Tool zeigt interne Skype for Business Server Routinginformationen zu bestimmten Benutzern an. Diese Informationen können für den Microsoft-Support persönlich hilfreich sein, wenn Sie Bereitstellungs-und Routingprobleme diagnostizieren.

### <a name="description"></a>Beschreibung

 Durch die Ausführung von LookupUserConsole. exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert, und versucht, interne Skype for Business Server Routinginformationen anzuzeigen, die Sie betreffen. Geben Sie **Exit** ein, um das LookupUserConsole-Tool zu beenden.

### <a name="requirements"></a>Anforderungen

Installieren Sie das Skype for Business Server 2015 Resource Kit. Das Tool wird auf Computern mit Domänenbeitritt ausgeführt, auf denen Skype for Business Server installiert ist.

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

Mit dem MSTurnPing-Tool kann ein Administrator von Skype for Business Server 2015 Kommunikationssoftware den Status der Server, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste durchführen, sowie die Server überprüfen, auf denen Bandbreitenrichtlinien Dienste in der Topologie verwendet werden.

### <a name="description"></a>Beschreibung

Mit dem MSTurnPing-Tool kann ein Administrator von Skype for Business Server 2015 Kommunikationssoftware den Status der Server, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste durchführen, sowie die Server überprüfen, auf denen Bandbreitenrichtlinien Dienste in der Topologie verwendet werden.

Das Tool ermöglicht es dem Administrator, die folgenden Tests auszuführen:

1. A/v-Edgeserver Test: das Tool führt Tests für alle A/v-Edgeserver in der Topologie aus, indem Sie folgende Schritte ausführen:

   - Überprüfen, ob der Skype for Business Server Audio/Video-Authentifizierungsdienst gestartet wurde, und Sie können ordnungsgemäße Anmeldeinformationen ausgeben.

   - Überprüfen, ob der Skype for Business Server Audio/Video-Edgedienst gestartet wurde, und die Ressourcen auf dem externen edgevorgang erfolgreich zuordnen können.

2. Bandbreitenrichtliniendienst Test: das Tool führt Tests für alle Server aus, auf denen die Bandbreitenrichtlinien Dienste in der Topologie ausgeführt werden, indem Sie folgende Schritte ausführen:

   - Überprüfen, ob der Skype for Business Server bandbreitenrichtliniendienst (Authentication) gestartet wurde und ordnungsgemäße Anmeldeinformationen ausgeben kann.

   - Überprüfen, ob der Skype for Business Server bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreiten Überprüfung erfolgreich durchführen kann.

Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist.

### <a name="output"></a>Output

Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.

- Wenn der **AudioVideoEdgeServer** -Test durchgeführt wird, werden die Ausgaben des Tools folgendermaßen ausgeführt:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015-Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 Audio/Video-Edgedienst in der Topologie bereitstellen

- Wenn der **BandwidthPolicyServer** -Test durchgeführt wird, werden die Ausgaben des Tools folgendermaßen ausgeführt:

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen

  - Die Testergebnisse der Computer, die den Skype for Business Server 2015 bandbreitenrichtliniendienst (Core) in der Topologie bereitstellen

### <a name="requirements"></a>Anforderungen

- Dieses Tool muss von einem Computer ausgeführt werden, der sich in der Topologie befindet und über den lokalen Speicher verfügt.

- Das Tool muss als Administrator ausgeführt werden, der Zugriff auf den lokalen Speicher hat.

### <a name="examples"></a>Beispiele

Nachfolgend sehen Sie ein Beispiel für die Tool Eingabe.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015 Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio/Video-und Bandbreitenrichtlinien Dienste durchführen.

## <a name="network-configuration-viewer"></a>Netzwerk Konfigurationsanzeige
<a name="NCV"> </a>

Die Netzwerkkonfigurations-Anzeige kann von Skype for Business Server 2015 Kommunikationssoftware Administratoren verwendet werden, um die Anruf Steuerungs Netzwerk-Topologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echt Zeit Kommunikationssitzungen zuzulassen, beispielsweise Sprach-oder Videoanrufe basierend auf der angegebenen Bandbreitenkapazität. Skype for Business Server 2015 Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtlinien Diensten erzwungen werden, die mit Skype for Business Server 2015 installiert werden.

### <a name="description"></a>Beschreibung

Network Configuration Viewer (NetworkConfigurationViewer. exe) ermöglicht Administratoren das Ausführen der folgenden Aufgaben:

- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format.

- Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei in einem grafischen Format.

- Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger.

- Speichern und speichern Sie das Diagramm der CAC-Netzwerktopologie im JPG-oder BMP-Format.

- Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie.

- View CAC Network Topology in a Tree-View Style.

- Definieren Sie benutzerdefinierte Connectors für CAC-Netzwerktopologie-Links (beispielsweise Standort-zu-Region-, Region-zu-Region-und Standort-zu-Standort-Links).

- Anzeigen der Informationen zur CAC-Netzwerktopologie, Regionsinformationen sowie Richtlinien für die verfügbare Bandbreite und Netzwerkverbindungen

### <a name="purpose"></a>Zweck

Anzeigen der Verknüpfungen der Enterprise-CAC-Netzwerktopologie in einer grafischen Benutzeroberfläche.

### <a name="examples"></a>Beispiele

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung im grafischen Format**: Skype for Business Server 2015 Administratoren können die Konfiguration der CAC-Netzwerktopologie auf einem beliebigen Skype for Business Server 2015 Computer mithilfe der Option " **Netzwerkkonfiguration herunterladen** " Laden und anzeigen, wie in der Abbildung unten dargestellt. Das Tool kann eine solche Konfiguration nicht herunterladen oder anzeigen, wenn Sie auf einem Computer bereitgestellt wird, der nicht über eine Verbindung mit dem Skype for Business Server 2015 Konfigurationsspeicher verfügt.

![Herunterladen der Netzwerkkonfiguration.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei im grafischen Format:** Skype for Business Server 2015 Bandbreitenrichtlinien Server speichern die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Skype for Business Server 2015 Dateifreigabespeicherort. Skype for Business Server 2015 Administratoren können eine solche Datei mit der **Open Network Configuration** -Option wie unten gezeigt in einem grafischen Format anzeigen.

![Öffnen einer Bandbreitenrichtlinien Server-Protokolldatei.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Speichern und speichern Sie die Anrufsteuerung-Netzwerktopologie in einem XML-Format auf dem Datenträger: Skype for Business Server 2015 Administratoren können die Konfigurationsdatei der CAC-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option **Kopie der Netzwerkkonfiguration speichern** wie unten gezeigt verwenden. Die gespeicherte Konfigurationsdatei kann dann offline für grafische Anzeigezwecke verwendet werden.

![Speichern der Netzwerkkonfiguration als XML-Datei.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Speichern und Speichern von Diagrammen der CAC-Netzwerktopologie im JPG-oder BMP-Format: Skype for Business Server 2015 Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG-und BMP-Dateiformate) speichern, indem Sie die Option **Netzwerk Konfigurations Diagramm als Bild speichern** wie unten gezeigt verwenden.

![Speichern der Netzwerkkonfiguration als Bild.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:</strong> Skype for Business Server 2015 Administratoren können verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerkstandorte, Bandbreiten Profile und IP-Adressen von Standort Netzwerken in einem Text Format anzeigen, indem Sie die Option "Netzwerkkonfigurationsdaten anzeigen" wie unten dargestellt verwenden.

![Anzeigen von Netzwerkkonfigurationsdaten.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Anzeigen der Anruf Steuerungs Netzwerktopologie in einem Struktur Ansichtsstil:** Skype for Business Server 2015 Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Struktur Ansichtsformat mithilfe der Systemsteuerung auf der linken Seite des Toolfensters anzeigen, wie unten dargestellt.

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definieren von benutzerdefinierten Connectors für CAC-Netzwerktopologie-Links (wie Standort-zu-Region, Region-zu-Region und Standort-zu-Standort-Links):** Skype for Business Server 2015 Administratoren können benutzerdefinierte grafische Konnektoren für Netzwerk Konfigurations-WAN-Verbindungen mithilfe der Einstellungsoption wie unten dargestellt definieren. Dies hilft bei der Unterscheidung zwischen verschiedenen Typen von Netzwerkverbindungen, die in der Netzwerkkonfiguration bereitgestellt werden.

![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Anzeigen der Informationen zur CAC-Netzwerktopologie, Regionsinformationen und Richtlinien für die verfügbare Bandbreite:** Skype for Business Server 2015 Administratoren können Informationen zu zugehörigen CAC-netzwerkregionen, Standortinformationen und Informationen zur Anruf Steuerungs Bandbreite mithilfe der unten aufgeführten Optionen anzeigen. (Klicken Sie beispielsweise in einer netzwerkregion oder einem Netzwerkstandort Objekt auf **Info** .)

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015 Administratoren sein, die die CAC-Netzwerktopologie für Ihre Bereitstellung in einem grafischen Format anzeigen möchten.

## <a name="response-group-agent-live"></a>Reaktionsgruppen-Agent Live
<a name="RGAL"> </a>

Mit dem Reaktionsgruppenanwendung können Agents mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zugreifen. Leider ist keine grafische Ansicht dieser Daten außerhalb der Anwendung verfügbar. Das Reaktionsgruppen-Agent-Live Resource Kit-Tool löst dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die mit Echt Zeit Skype for Business Kommunikationssoftware Informationen wie etwa dem vorhanden sein anderer Agents erweitert wurde.

### <a name="description"></a>Beschreibung

Bei Agent Live für Reaktionsgruppen handelt es sich um eine Windows-Anwendung, die die Funktionen für die Anmeldung und Abmeldung sowie einige Echtzeitinformationen (beispielsweise die Gruppenmitgliedschaft und die aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bereitstellt. Es handelt sich um eine erweiterte Version der Seite "Agentgruppen" (verfügbar über Skype for Business.

### <a name="purpose"></a>Zweck

In der Reaktionsgruppenanwendung werden eingehende Anrufe in die Warteschlange eingereiht und an Agentgruppen weitergeleitet. Um fundierte Entscheidungen darüber zu treffen, welche Anrufe für Dienste durchzuführen sind, können Agents auf Echtzeitinformationen zu ihren Agentgruppen zugreifen, beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschlange warten. Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst zugänglich sind, werden auf intuitive Weise vom Reaktionsgruppen-Agent Live zur Verfügung gestellt.

#### <a name="features"></a>Features

Das Live-Tool für Reaktionsgruppen-Agents basiert auf dem Reaktionsgruppendienst und dem Skype for Business Server 2015 SDK. Sie stellt Reaktionsgruppen-Agents die Informationen und Funktionen zur Verfügung, die über den Reaktionsgruppendienst verfügbar sind (wie Gruppenmitgliedschaft, Anwesenheit von anderen Agents und Anzahl der wartenden Anrufe).

In der folgenden Abbildung ist die Hauptschnittstelle des Reaktionsgruppen-Agents Live dargestellt.

![Das Live-Tool für Reaktionsgruppen-Agents.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Die folgenden drei Hauptfeatures stehen für Agents im Reaktionsgruppen-Agent Live zur Verfügung:

- **Anmelden/Auschecken:** Im Gegensatz zur Seite "Agentgruppen" (auf die von Skype for Business Server 2015 zugegriffen werden kann) kann der Reaktionsgruppen-Agent Live nur Agents auf einmal anmelden oder sich bei allen Agentgruppen abmelden. Diese Anwendung bietet drei schnelle Methoden für die Anmeldung von Agents:

  - Klicken Sie in der Anwendung auf die Schaltflächen zum Anmelden/Auschecken (grün und rot).

  - Klicken Sie mit der rechten Maustaste auf das Symbol in der Taskleiste, und wählen Sie anmelden oder Abmelden aus.

  - Verwenden von konfigurierbaren Tastenkombinationen

- **Gruppenmitgliedschaft:** Wenn eine Agentgruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an. Wenn Skype for Business Server 2015 auf demselben Computer wie diese Anwendung läuft, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt. Agents können direkt von dort aus einen Chat senden oder andere Agents anrufen.

- **Echtzeitstatistik:** Der Reaktionsgruppen-Agent Live bietet Echtzeitstatistiken für alle Agentgruppen. Die Aktualisierungshäufigkeit beträgt eine Minute. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein visuelles Symbol mit der aktuellen Anzahl von in der Warteschlange befindlichen anrufen hinzugefügt. Wenn Sie den Zeiger über eine Gruppe anhalten, wird auch die längste Wartezeit angezeigt.

### <a name="requirements"></a>Anforderungen

Für den Reaktionsgruppen-Agent Live ist der .NET Framework 4,0 erforderlich. Darüber hinaus müssen Skype for Business lokal installiert sein (und ausgeführt werden), um die Anwesenheits-und Visitenkarten Funktionen nutzen zu können.

#### <a name="configuration"></a>Konfiguration

Der Live Reaktionsgruppen-Agent kann mithilfe des Dialogfelds Optionen in der Anwendung an individuelle Einstellungen angepasst werden. Darüber hinaus kann der Administrator die Standardhost Adresse definieren, indem er die defaultHostAddress-Eigenschaft der Datei RGAgentLive. exe. config direkt bearbeitet.

Die folgende Abbildung zeigt das Dialogfeldoptionen, mit dem Agents die Hostadresse und die Tastenkombinationen konfigurieren können. Der Zugriff auf dieses Dialogfeld erfolgt durch Klicken auf die Schaltfläche Optionen oben rechts auf der Hauptoberfläche.

![Das Dialogfeld Reaktionsgruppen-Agent-Live Optionen.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Die folgenden drei unterschiedlichen Einstellungen können in der Live-Konfiguration des Reaktionsgruppen-Agents angepasst werden:

- Host Adresse: Dies ist normalerweise der FQDN des webpools, der zum Home-Pool des Agents gehört. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch aus diesen Informationen im Hintergrund abgeleitet (durch Anfügen des richtigen Pfads nach dem Host).

- Shortcuts: die genauen Verknüpfungen zum Anmelden/Auschecken können angepasst werden. Die einzige Einschränkung besteht darin, dass beide Verknüpfungen die Taste "Windows-Logo" (zusätzlich zu mindestens einem anderen Schlüssel) enthalten müssen.

- Beginnen mit Windows: die Anwendung kann so konfiguriert werden, dass Sie automatisch mit Windows gestartet wird.

### <a name="examples"></a>Beispiele

Die folgende Abbildung zeigt, wie Sie eine Sofortnachricht an einen anderen Agent aufrufen oder senden, indem Sie mit der rechten Maustaste auf den Kontakt im rechten Bereich klicken.

![Tätigen eines Anrufs oder Sendens eines Chats.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

Die folgende Abbildung zeigt, wie der Reaktionsgruppen-Agent Live die aktuelle Anzahl von Anrufen in der Warteschlange und die längste Wartezeit unter all diesen eingehenden Anrufen anzeigt.

![Anzeigen von Warteschlangeninformationen.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Zusammenfassung

Schnelle Anmeldung und Abmeldung, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Features für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung aus dem Reaktionsgruppendienst verfügbar sind. Mit dem Reaktionsgruppen-Agent Live Resource Kit-Tool können Skype for Business Server 2015 Administratoren ihren Agents eine Windows-Anwendung zur Verfügung stellen, die es Ihnen ermöglicht, Aufgaben schneller und grafischer auszuführen.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (sekundäre Erweiterung Feature Activation) ist ein Befehlszeilentool, mit dem Skype for Business Server 2015 Kommunikationssoftware Administratoren und Helpdesk-Agents Delegierten Klingeln, Anrufweiterleitung, gleichzeitiges Klingeln konfigurieren können, Team Anrufeinstellungen und gruppenanrufannahme im Auftrag eines Skype for Business Server 2015 Benutzers. Das Tool ermöglicht es Administratoren auch, die Anrufweiterleitungseinstellungen abzufragen, die für einen bestimmten Benutzer veröffentlicht werden. Das SEFAUtil-Tool ermöglicht dem Administrator das aktivieren/deaktivieren/Ändern der Anrufweiterleitung oder das gleichzeitige Klingeln im Namen des Benutzers. Der Administrator kann das Ziel (in Form eines SIP-URI) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde. Mit diesem Tool können Administratoren auch Stellvertretungen oder Teamanrufgruppen Mitglieder im Namen des Benutzers hinzufügen oder entfernen. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.

SEFAUtil (sekundäre Erweiterung Feature Activation) ermöglicht es Skype for Business Server 2015 Administratoren und Helpdesk-Agents, Stellvertreter-Klingeln, Anrufweiterleitung, gleichzeitiges Klingeln, Team Anrufeinstellungen und gruppenanrufannahme im Namen eines Skype-Benutzers zu konfigurieren. for Business Server 2015-Benutzer. Mit diesem Tool können Administratoren auch die Anrufweiterleitungseinstellungen Abfragen, die für einen bestimmten Benutzer veröffentlicht werden.

### <a name="description"></a>Beschreibung

Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool; Es gibt keine unterstützende grafische Benutzeroberfläche. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0. Die Funktionen in diesem Tool ermöglichen Administratoren und Helpdesk-Agents Folgendes:

- Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Delegierung, gleichzeitiges Klingeln, Team-und gruppenanrufannahme)

- Aktivieren/Deaktivieren/Ändern der Einstellung für die Anrufweiterleitung (schließt den Ziel-und den nicht-Antwort-Timer ein)

- Aktivieren/Deaktivieren/Ändern der unmittelbaren Konfigurationen für die Anrufweiterleitung

- Aktivieren/Deaktivieren/ändern von Delegierungseinstellungen

- Aktivieren/Deaktivieren/ändern von Einstellungen für die Teamanrufgruppe

    > [!NOTE]
    > Neu in Skype for Business Server 2015 SEFAUtil-Tool

- Aktivieren/Deaktivieren/ändern gleichzeitiger Klingel Einstellungen (umfasst das Ziel)

    > [!NOTE]
    > Neu in Skype for Business Server 2015 SEFAUtil-Tool

- Aktivieren/Deaktivieren/ändern von Einstellungen für die gruppenanrufannahme

    > [!CAUTION]
    > Neu in Skype for Business Server 2015 SEFAUtil-Tool

Dieses Tool hat die folgenden Einschränkungen:

- Nur für Benutzer unterstützt, die in einem Skype for Business Server-Pool verwaltet werden

- Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer wird nicht unterstützt

### <a name="output"></a>Output

Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster eine Ausgabe bereit. Ausführliche Informationen finden Sie im Abschnitt "Beispiele" weiter unten in diesem Dokument.

### <a name="purpose"></a>Zweck

Im folgenden finden Sie einige der wichtigsten Szenarien, in denen dieses Tool verwendet werden kann:

- Bob ist eine Führungskraft und wurde in Skype for Business Server Telefonie verschoben. Er verfügt über eine Delegation für sein vorhandenes PBX-System. Im Rahmen des Umstiegs auf Skype for Business Server 2015 kann der Administrator Bobs Routing so konfigurieren, dass er seine bereits vorhandene Delegierungs Konfiguration widerspiegelt.

- Alice reist und erkennt, dass Sie einen wichtigen Anruf von einem ihrer Kunden erwartet. Sie befindet sich jedoch in einem Hotel und hat keinen Zugriff auf einen Computer. Sie ruft den Helpdesk an und fordert an, dass Sie alle Anrufe an Ihre Telefonnummer an Ihre Mobiltelefonnummer weiterleiten. Das Helpdesk-Personal kann die Konfiguration in Ihrem Auftrag durchführen.

- Joes Anrufe an seine Arbeitsnummer gehen zu seiner mobilen Voicemail, wenn er bei der Arbeit ist; in den meisten anderen Speicherorten scheinen die Dinge jedoch korrekt zu funktionieren. Der Helpdesk-Techniker kann Joes Routingkonfiguration anzeigen und feststellt, dass Joe das gleichzeitige Klingeln auf seinem Mobiltelefon konfiguriert hat. Der Techniker fragt Joe nach der mobilen Abdeckung in seinem Büro und kann feststellen, dass die gleichzeitige Klingel Regel ist, was dazu führt, dass die Anrufe an Joes Mobile Voicemail gehen, wenn seine Netzwerkabdeckung schlecht ist.

- Mike ist ein neuer Mitarbeiter bei Contoso und er nimmt an einem neuen Team Teil, für das alle Mitglieder für Teamanrufe konfiguriert sind, wenn es für Skype for Business Server 2015 aktiviert ist, kann der Administrator seine Teamanrufgruppen Einstellungen so festlegen, dass er alle neuen Teammitglieder einschließt. Zusätzlich fügt der Administrator Mike für jedes Mitglied in seinem Team als Teamanrufgruppe hinzu.

- Eine Kundendienst Praxis in der Personalabteilung von Contoso ist die Bereitstellung persönlicher Dienste für alle Anrufer seit dem ersten Anruf. Da alle Mitglieder der Abteilung sehr nahe beieinander sitzen, ist es für das Team sehr störend, dass alle Telefone gleichzeitig mit dem Team Anruf Klingeln. Um den besten Dienst bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der Skype for Business Server 2015 Administrator die Möglichkeit der gruppenanrufannahme. Der Administrator fügt alle Abteilungsmitglieder zu einer Pickup-Gruppe hinzu und kommuniziert mit der Abteilung mit der Abhol Gruppennummer. Wenn Samantha von Ihrem Schreibtisch abwesend ist, merkt Joe, dass Ihr Telefon klingelt und er den Anruf von seinem Schreibtisch aus beantwortet.

### <a name="requirements"></a>Anforderungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. UCMA 3.0 muss auf diesem Computer installiert sein. Zum Ausführen des Tools muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool

1. Das SEFAUTil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist. Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die Skype for Business Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:

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
    > Pool-FQDN: der FQDN des Servers oder Pools, der als Host für die SEFAUtil-Anwendung verwendet wird (in der Regel ein Skype for Business-Front-End-Server-> oder-Pool).
    > FQDN des Pool Registrierungsstelle: der FQDN des Skype for Business Front-End-Servers oder Pools, der diesem Anwendungspool zugeordnet ist.
    > Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.

3. Die Topologie-Änderungen müssen aktiviert sein. Das Aktivieren der Topologie-Änderungen kann über die Skype for Business Server Management Shell durch Ausführen des folgenden Cmdlets erfolgen:

   ```powershell
   Enable-CsToplogy
   ```

4. Installieren Sie bei Bedarf die Skype for Business Server 2015 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).

5. Stellen Sie sicher, dass die SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool über eine Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. Das Tool befindet sich standardmäßig in: ". ..\Programme\Microsoft Files\Skype for Business Server 2015 \ reskit". Verwenden Sie den folgenden Befehl, um die Anrufweiterleitungseinstellungen eines Benutzers anzuzeigen:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Die Einstellungen für die Anrufweiterleitung des Benutzers sollten angezeigt werden.

#### <a name="group-call-pickup"></a>Gruppenanrufannahme

Für die gruppenanrufannahme ist eine zusätzliche Konfiguration in Skype for Business Server 2015 erforderlich, damit die Funktion vollständig aktiviert werden kann. Vor dem Zuweisen von Pickup-Gruppen zu Benutzern finden Sie in der Group Call Pickup-Produktdokumentation die Planungs-und Bereitstellungsschritte dieser Funktion.

### <a name="examples"></a>Beispiele

#### <a name="display-current-call-handling-settings"></a>Anzeigen der aktuellen Einstellungen für die Anrufverarbeitung

Mit dem folgenden Befehl wird die Anrufbehandlung für den Benutzer angezeigt.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> In diesem Beispiel wird **die Option/** Tausch verwendet, um die Skype for Business Server anzugeben, mit der eine Verbindung hergestellt werden soll.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Festlegen des Ziels "Anrufweiterleitung/Nein-Antwort"

In diesem Beispiel werden das Ziel für die Anrufweiterleitung/keine Antwort und die Ring Verzögerung festgelegt. Hier wird die Option// SEFAUtil versucht, die Skype for Business Server 2015 zu AutoErmittlung.

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

In diesem Beispiel wird die Anrufweiterleitung sofort an einen anderen Benutzer aktiviert.

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

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Hinzufügen eines Benutzers als Stellvertreter und Einrichten des gleichzeitigen Klingelns von Stellvertretern

In diesem Beispiel wird ein Benutzer als Stellvertreter hinzugefügt und das gleichzeitige Klingeln von Stellvertretern eingerichtet.

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

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Ändern der gleichzeitigen Klingel Regel für Stellvertretungen

In diesem Beispiel wird die Regel für das gleichzeitige Klingeln, die im vorherigen Beispiel festgelegt wurde, auf die verzögerte Klingel Regel geändert.

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

In diesem Beispiel wird die Stellvertretung entfernt.

> [!NOTE]
> Wenn der letzte Stellvertreter entfernt wird, wird das Delegieren von Klingeln automatisch deaktiviert.

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

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Hinzufügen einer Stellvertretung und Einrichten der Regel "Anrufweiterleitung an Stellvertretungen"

In diesem Beispiel wird eine Stellvertretung hinzugefügt und die Regel "Anrufweiterleitung an Stellvertretungen" eingerichtet.

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

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Gleichzeitiges Klingeln aktivieren und Zielrufnummer festlegen

In diesem Beispiel wird das gleichzeitige Klingeln aktiviert und eine Ziel Nummer für das gleichzeitige Klingeln festgelegt.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Wenn Sie die Ziel Nummer für das gleichzeitige Klingeln eines Benutzers ändern möchten, der bereits das gleichzeitige Klingeln aktiviert hat, halten Sie den Befehl mit dem/enablesimulring-Schalter an, andernfalls wird die Zielrufnummer nicht geändert.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Gleichzeitiges Klingeln deaktivieren

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

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Gruppe "Team Anruf Mitglieder"

In diesem Beispiel wird der Teamanrufgruppe eines Benutzers ein Teammitglied hinzugefügt und das gleichzeitige Klingeln für die Teamanrufgruppe aktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> Durch das Hinzufügen eines Mitglieds zur Teamanrufgruppe eines Benutzers wird automatisch das gleichzeitige Klingeln der Einstellungen der Benutzer zu gleich seiner Teamanrufgruppe gewechselt.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Entfernen eines Mitglieds aus der Team anrufgruppe

In diesem Beispiel wird ein Teammitglied der Teamanrufgruppe eines Benutzers entfernt.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Wenn das zu entfernende Element das einzige Mitglied der Teamanrufgruppe ist, wird das gleichzeitige Klingeln für die Teamanrufgruppe automatisch deaktiviert.

 **Ausgabe**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Festlegen des verzögerten Rings auf die Team anrufgruppe

In diesem Beispiel wird der verzögerte Ring in die Zeiteinstellung für die Teamanrufgruppe geändert.

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

#### <a name="enable-team-call"></a>Aktivieren des Team Anrufs

In diesem Beispiel wird der Team Aufruf für einen bestimmten Benutzer aktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Wenn die Teamanrufgruppe des Benutzers keine Mitglieder enthält, wird die Teamanruffunktion nicht aktiviert.

 **Ausgabe**

#### <a name="disable-team-call"></a>Team Anruf deaktivieren

In diesem Beispiel wird der Team Aufruf für einen bestimmten Benutzer deaktiviert.

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

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Aktivieren der gruppenanrufannahme und Zuweisen einer Abhol Gruppe zu einem Benutzer

In diesem Beispiel wird einem Benutzer eine Abhol Gruppe zugewiesen, und es wird eine gruppenanrufannahme aktiviert.

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

#### <a name="disable-group-call-pickup"></a>Deaktivieren der gruppenanrufannahme

In diesem Beispiel wird die gruppenanrufannahme für einen bestimmten Benutzer deaktiviert.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Wenn Sie die gruppenanrufannahme für einen Benutzer deaktivieren, wird die dem Benutzer zugewiesene Gruppennummer nicht beibehalten. Wenn Sie anschließend die gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie die Gruppennummer mit dem/enablegrouppickup-Schalter erneut zuweisen.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep. ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Beschreibung

SYSPrep. ps1 ist ein Windows PowerShell Skript, mit dem die folgenden Skype for Business Server 2015 erforderlichen Komponenten auf Ihrem Windows Server 2008-Betriebssystem Computer installiert werden.

- Microsoft .NET Framework 4,5

- Microsoft SQL Server Express

- Windows PowerShell, Version 3,0

- Visual C++ 2010 Redistributable

- Internet Informations Server-Updates

- Windows Identity Foundation

- Skype for Business Server 2015 Kerndateien

  Während der Skriptname dem System Vorbereitungs Tool für Microsoft Windows-Betriebssysteme ähnelt, sind Sie unterschiedlich. Mit diesem Skript werden nur die erforderlichen Voraussetzungen für Skype for Business Server 2015 installiert. Sobald diese Voraussetzungen installiert sind, kann das Windows-SYSPrep-Tool verwendet werden, um ein Abbild des Servers zu erstellen.

### <a name="requirements"></a>Anforderungen

Vor dem Ausführen des Skripts "SYSPrep. ps1" müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (beispielsweise **D:\setup)**. Dieser Ordner muss auch eine Kopie der Skype for Business Server 2015 Dateien enthalten, insbesondere **Setup. exe.** Die erforderlichen Dateien können von den folgenden Speicherorten heruntergeladen werden:


| **Voraussetzung**                                | **Standort**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4,5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell, Version 3,0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 Redistributable  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| Internet Informations Server-Updates  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup. exe  <br/> | Kopieren von Skype for Business Server 2015 Medien  <br/>                   |

### <a name="parameter"></a>Parameter

Der **-SetupFolder-** Parameter verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.

### <a name="examples"></a>Beispiele

Führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, um das Skript "SYSPrep. ps1" auszuführen und die erforderlichen Komponenten für Skype for Business Server 2015 zu installieren:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migration nicht zugewiesener Nummern Ankündigungen
<a name="UNAM"> </a>

Mit dem Migrationstool für nicht zugewiesene Nummern Ankündigungen kann ein Skype for Business Server 2015 Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung aus einer Quell Skype for Business Server oder einem Pool gewartet wird, in eine Ziel-Skype for Business Server oder-Pool.

### <a name="description"></a>Beschreibung

Das Migrationstool für nicht zugewiesene Nummern Ankündigungen ist ein Windows PowerShells Skript, mit dem die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung eines Quellservers oder Pools aus gewartet wird, auf einen anderen Server oder Pool verschoben wird.

Bei der Ausführung des Migrationsskripts für unassigned number Announcements werden die folgenden Vorgänge ausgeführt:

1. Verschiebt alle Audiodateien, die von den Ankündigungen nicht zugewiesener Nummern der in dem Quellserver oder Pool gehosteten Ankündigungs Anwendung verwendet werden, in den Dateispeicher des Zielservers oder-Pools.

    > [!NOTE]
    > Die Audiodateien werden aus dem Quell Pool entfernt, nachdem Sie in den Ziel Pool kopiert wurden.

2. Verschiebt alle Ankündigungen für nicht zugewiesene Nummern, die für die im Quellserver oder Pool gehostete Ankündigungs Anwendung konfiguriert sind, auf den Zielserver oder-Pool.

3. Weisen Sie dem Zielserver oder-Pool alle nicht zugewiesenen Nummernbereiche, die von der auf dem Quellserver oder Pool gehosteten Ankündigungs Anwendung gewartet werden, neu zu.

Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der auf dem Quellserver oder Pool gehosteten Ankündigungs Anwendung gewartet wurden, jetzt mit der gleichen Konfiguration vom Zielserver oder-Pool aus gewartet.

### <a name="output"></a>Output

Das **CsAnnouncementConfiguration-** Skript zeigt im Fenster der Skype for Business Server-Verwaltungsshell an, wo es den Erfolg oder Misserfolg des Migrationsvorgangs ausgeführt wird.

Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die nicht zugewiesenen Nummernbereiche, die erfolgreich in das Ziel verschoben wurden, in einem operativen Formular im Ziel und die restlichen nicht zugewiesenen Nummernbereiche, die migriert werden sollen, werden in die Quelle als auch in einem operativen Formular. Um den Rest der Konfiguration vollständig zu migrieren, führen Sie das Skript nach dem Beheben des Fehlers erneut aus.

### <a name="purpose"></a>Zweck

Das Migrationsskript "nicht zugewiesene Nummern Ankündigungen" kann in den folgenden drei Szenarien verwendet werden:

- **Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype for Business Server:** Contoso wird gerade zu Skype for Business Server 2015 migriert, und im Rahmen des Migrationsprozesses möchte der Skype for Business Server Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung gewartet wird, von der lync Server 2013-Bereitstellung in die neue Skype for Business Server 2015-Bereitstellung verschieben. Zum Migrieren der Konfigurationseinstellungen verwendet der Skype for Business Server Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen.

- **Rollback einer Bereitstellung von Skype for Business Server 2015 auf lync Server 2013:** Aufgrund unerwarteter Faktoren muss Contoso die Migration in die neue Skype for Business Server 2015-Bereitstellung rückgängig gemacht werden. Zum Minimieren von Unterbrechungen des Diensts verwendet der Skype for Business Server Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen, um die Konfiguration von der Skype for Business Server 2015-Bereitstellung auf die lync Server 2013-Bereitstellung zurückzusetzen.

- **Verschieben von Daten zwischen Bereitstellungen:** Contoso ist dabei, alle Server eines Pools durch neuere Server zu ersetzen. Ihre Strategie besteht darin, einen neuen Skype for Business Server 2015 Pool bereitzustellen, alle Daten aus dem alten in den neuen Pool zu verlagern und dann den alten Pool zu veraltern. Nachdem der neue Pool bereitgestellt wurde, wird das Migrationstool für unassigned number Announcements verwendet, um die Konfiguration aus dem alten Pool in die neue zu verlagern.

#### <a name="requirements"></a>Anforderungen

Die folgenden Hauptanforderungen müssen erfüllt sein, um das Tool erfolgreich auszuführen:

1. Das Skript muss von einem Computer aus ausgeführt werden, auf dem Skype for Business Server Management Shell installiert ist.

2. Die Ankündigungs Anwendung muss erfolgreich in den Quell-und Ziel Skype for Business-Servern oder-Pools bereitgestellt werden.

#### <a name="move-csannouncementconfiguration-script"></a>CsAnnouncementConfiguration-Skript

Das CsAnnouncementConfiguration-Skript erfordert die beiden Parameter, die in der folgenden Tabelle beschrieben werden.

![CsAnnouncementConfiguration-Parameter.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Beispiele

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Verschieben der Konfiguration nicht zugewiesener Nummern Ankündigungen von einem lync Server 2013 Pool in einen Skype for Business Server 2015 Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2013) in den Ziel Pool (Skype for Business Server 2015) verschoben.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Verschieben der Konfiguration nicht zugewiesener Nummern Ankündigungen von einem Skype for Business Server 2015 Pool in einen lync Server 2013 Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (Skype for Business Server 2015) in den Ziel Pool (lync Server 2013) verschoben.

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Webconf-Daten
<a name="WebConfData"> </a>

Mit dem Tool "webconf Data" kann ein Administrator von Skype for Business Server 2015 Kommunikationssoftware mehr Kontrolle über die Daten haben, die den Webkonferenzen eines Organisators zugeordnet sind. Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers basierend auf einem Zeitstempel Kriterium zu löschen.

### <a name="description"></a>Beschreibung

Mit diesem Tool kann der Administrator die folgenden Vorgänge ausführen:

1. Hier finden Sie alle mit einem einzelnen Benutzer verknüpften Webkonferenz Daten.

2. Löschen Sie alle Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind.

3. Löschen Sie alle Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, der älter als ein bestimmtes Datum ist.

4. Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.

    > [!NOTE]
    > Die Resource Kit-Tools für lync Server 2010 unterstützt das Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird. Diese Funktionalität ist nun in diesem Tool für den **MoveConferenceData** -Parameter veraltet. Ausführliche Informationen zu diesem Parameter finden Sie unter dem Cmdlet " [Verschiebe-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) ".

Das Tool löscht Besprechungsdaten nur für nicht aktive Besprechungen. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.

Dieses Tool muss von einem Computer aus ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhalts Daten von diesem Tool verwaltet werden, muss sich in demselben Benutzerpool befinden.

### <a name="output"></a>Output

Dieses Tool gibt die Ergebnisse der einzelnen Vorgänge aus:

- Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdaten Ordner aus, die diesen Benutzer als Organisator haben.

- Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdaten Ordner aus, deren Daten gelöscht werden.

### <a name="requirements"></a>Anforderungen

Das Tool muss in demselben Pool ausgeführt werden, in dem der Organisator derzeit verwaltet wird.

Das Tool muss mit Administratorrechten mit Zugriff auf die Inhalts Dateispeicher ausgeführt werden.

### <a name="examples"></a>Beispiele

In der folgenden Tabelle werden die Parameter beschrieben, von denen einige in den Beispielen verwendet werden.

![Parameter des webconf-Datentools.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

Das obige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Bei der Ausgabe eines solchen Befehls handelt es sich um eine Liste aller Besprechungsinhalts Ordner, die von diesem Tool betroffen wären.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

Das vorangehende ist ein Beispiel für einen DELETE-Befehl. Mit dem Befehl Delete werden alle inaktiven Besprechungs Ordner von diesem Benutzer entfernt.

### <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenz Besprechungsdaten benötigen.


