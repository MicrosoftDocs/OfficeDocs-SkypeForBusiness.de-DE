---
title: Lync Server 2013 Resource Kit-Tools – Dokumentation
TOCTitle: Lync Server 2013 Resource Kit-Tools – Dokumentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945604(v=OCS.15)
ms:contentKeyID: 52056035
ms.date: 09/29/2014
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 Resource Kit-Tools – Dokumentation

 

_**Letztes Änderungsdatum des Themas:** 2014-01-09_

In diesem Thema werden die Tools beschrieben, die im Lync Server 2013 Resource Kit enthalten sind, einschließlich des Verwendungszwecks des jeweiligen Tools und Beispielen für seine Verwendung. Die Resource Kit-Tools in Lync Server 2013 helfen dabei, Routineaufgaben für IT-Administratoren zu vereinfachen, die Lync Server 2013 bereitstellen und verwalten. Beispielsweise kann das **Webkonferenzdaten**-Tool verwendet werden, um bequem Daten zu kontrollieren, die von Benutzern während einer Onlinebesprechung hochgeladen werden. Mithilfe des Tools **SEFAUtil** können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten. Wir bestärken IT-Administratoren darin, diese Tools zu verwenden, um Lync Server 2013 effektiver zu verwalten.

## Installation der Resource Kit-Tools

Zum Installieren der Resource Kit-Tools in Lync Server 2013 laden Sie **OCSReskit.msi** herunter. Sie können das Installationsprogramm für die Resource Kit-Tools aus dem Download Center unter [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429) herunterladen.

Führen Sie **OCSResKit.msi** aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Tools im folgenden Pfad: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**. Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner. Tools, die über weitere Dateien verfügen, befinden sich in ihren jeweiligen Unterordnern.

## Unterstützte Umgebungen

Für eine optimale Leistung sollten die Resource Kit-Tools in Lync Server 2013 in derselben Umgebung und mit denselben Spezifikationen installiert werden, die für Lync Server 2013 erforderlich sind

## Resource Kit-Tools – Übersicht

Die folgende Liste zeigt die Tools, die im Lync Server 2013 Resource Kit enthalten sind. Im folgenden Abschnitt wird jedes Tool mit seinen Voraussetzungen und Beispielanwendungen beschrieben.

  - ABSConfig

  - Bandbreitenrichtliniendienst-Überwachung

  - Bandbreitennutzungsanalyse

  - Anrufparkuhr (Call Parkometer)

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Netzwerkkonfigurationsanzeige

  - Reaktionsgruppen-Agent Live

  - SEFAUtil

  - SYSPrep.ps1

  - Migration von Ankündigungen für nicht zugewiesene Nummern

  - Webkonferenzdaten

## ABSConfig

Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, das Administratoren bei der Anpassung der Adressbuchdienst-Konfiguration in Lync Server 2013 hilft. Dieses Tool ermöglicht Lync Server 2013-Administratoren außerdem das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts.

## Beschreibung

ABSConfig ist eine Anwendung mit einer grafischen Benutzeroberfläche, die Administratoren das Konfigurieren von Active Directory-Domänendienste-Attributen ermöglicht, die im Zusammenhang mit dem Adressbuchdienst stehen.

Die primären Verwendungsszenarios für das Tool sind folgende:

  - Administratoren das Zuordnen von Attributen in den Active Directory-Domänendiensten zu den Attributen für Lync Server 2013 ermöglichen.

  - Administratoren das Angeben des Attributs in den Active Directory-Domänendiensten ermöglichen, das in die Adressbuchdienst-Dateien aufgenommen oder daraus ausgeschlossen werden soll.

  - Administratoren das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts ermöglichen.

Das ABSConfig-Tool kann mithilfe der Datei "absConfig.exe" gestartet werden. Das Tool wird mit der Registerkarte **Configure Attributes** geöffnet. In dieser Tabelle finden Sie Optionen zum Zuordnen von Attributen der Active Directory-Domänendienste zu den Attributfeldern für Lync Server 2013. Ferner können Sie die Benutzer angeben, die auf Grundlage bestimmter Attributfilter in Adressbuchdienst-Dateien aufgenommen oder daraus ausgeschlossen werden sollen. Sie finden auch Optionen zum Anpassen des Teils der Telefonnummer, der in die Adressbuchdatei aufgenommen werden soll. Mithilfe der Option **Restore Defaults** können Administratoren die Einstellungen des Adressbuchdiensts mit ihren Standardwerten wiederherstellen.

## Änderungen gegenüber Lync Server 2010

Im ABS-Konfigurationstool von Lync Server 2013 können Attribute (Zeilen) entfernt werden, indem das Aktivierungskontrollkästchen für das jeweilige Attribut deaktiviert wird. Dies hat dieselbe Wirkung wie das Löschen der Zeile in Lync Server 2010.


> [!Note]
> Das Aktivierungskontrollkästchen befindet sich in der Spalte ganz rechts. Möglicherweise müssen Sie einen Bildlauf nach rechts durchführen, um die Spalte anzuzeigen.



## Ausgabe

ABSConfig speichert die Konfiguration des Adressbuchdiensts in der Datenbank.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

## Verwendungszweck

ABSConfig bietet eine schnelle und bequeme Möglichkeit zum Anpassen des Adressbuchdiensts von Lync Server 2013.

## Anforderungen

## Computer

ABSConfig kann nur auf einem Computer ausgeführt werden, der einer Domäne beigetreten ist und auf dem Lync Server 2013 installiert ist. Im Falle von Lync Server 2013, Enterprise Edition, kann dieses Tool nur auf Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während der Einrichtung aktiviert ist.

## Netzwerk

Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.

## Software

Die folgenden Softwarekomponenten müssen vor der Ausführung des ABSConfig-Tools installiert sein:

  - Microsoft Lync Server 2013

## Benutzer

Administratoren, die die zum Aktualisieren der Lync Server 2013-Bereitstellung erforderlichen Berechtigungen besitzen.

## Beispiele

ABSConfig kann durch Eingabe von **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie eine Abbildung der Benutzeroberfläche des ABSConfig-Tools.

![Das ABSConfig.exe-Tool](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Das ABSConfig.exe-Tool")

## Zusammenfassung

Das ABSConfig-Tool bietet Administratoren ein schnell und bequem verwendbares Tool zum Anpassen des Adressbuchdiensts von Lync Server 2013.

## Bandbreitenrichtliniendienst-Überwachung

Das Bandbreitenrichtliniendienst-Überwachungstool soll Administratoren das Anzeigen einer Liste folgender Elemente ermöglichen:

1.  Alle konfigurierten Bandbreitenrichtliniendienste (Authentifizierung und Kern) von Lync Server 2013 in der Topologie.

2.  Die Verbindungen, die jeder Dienst mit anderen Bandbreitenrichtliniendiensten und Edgeservern herstellt.

3.  Alle Verbindungen, die im Netzwerkkonfigurationsdokument konfiguriert sind, und die Echtzeitbandbreitennutzung gemäß den Meldungen jedes einzelnen Bandbreitenrichtliniendiensts.

## Beschreibung

Das Bandbreitenrichtliniendienst-Überwachungstool ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Administratoren starten das Tool durch Ausführen der Datei "PDPMonUI.exe".

Wenn das Tool startet, versucht es die Liste der Bandbreitenrichtliniendienste in der Topologie zu ermitteln. Nach Durchführung der anfänglichen Aktualisierung wird der linke Bereich im Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.

Wenn Administratoren einen bestimmten Bandbreitenrichtliniendienst auswählen, werden im rechten Bereich des Fensters die Informationen zu dem bestimmten Dienst angezeigt. In diesem Bereich sind außerdem zwei Hauptregisterkarten vorhanden, auf denen Informationen angezeigt werden.

## Registerkarte mit Computerinformationen ("Machine Info")

Auf der Registerkarte **Machine Info** werden die Details des ausgewählten Bandbreitenrichtliniendiensts angezeigt sowie die Liste und Zustände aller Verbindungen, die von dem ausgewählten Bandbreitenrichtliniendienst mit anderen Diensten hergestellt werden.

## Registerkarte mit Topologieinformationen ("Topology Info")

Auf der Registerkarte **Topology Info** wird eine Liste aller Verbindungen angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jede Verbindung wird die Audio- und Videobandbreitenkapazität angezeigt. Zusätzlich wird die aktuell verwendete Bandbreite in KB/s und als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierungen zum Hervorheben von Verbindungen, die eine Nutzung aufweisen, die fast der Kapazität entspricht, was es Administratoren ermöglicht, solche Verbindungen schnell zu isolieren.


> [!Note]
> Wenn es beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreitenrichtliniendienste zu einem Fehler im Bandbreitenrichtliniendienst-Überwachungstool kommt, werden die Informationen auf den Registerkarten <STRONG>Machine Info</STRONG> und <STRONG>Topology Info</STRONG> nicht aufgefüllt. Es ist aber möglich, dass das Tool anfangs eine Verbindung mit dem Dienst herstellt, die dann später verloren geht. In solchen Fällen werden Administratoren eventuell veraltete Informationen angezeigt. Es gibt einen Zeitstempel <STRONG>Last Updated</STRONG> auf beiden Registerkarten, mit dessen Hilfe Administratoren bestimmen können, wann die Daten zum letzten Mal für einen bestimmten Bandbreitenrichtliniendienst aktualisiert wurden.



## Ausgabe

Es gibt keine Befehlszeilenausgabe. Die Programmausgabe erfolgt in der grafischen Hauptbenutzeroberfläche.

## Verwendungszweck

Der Verwendungszweck des Bandbreitenrichtliniendienst-Überwachungstools besteht darin, Administratoren Einblick in den Zustand jedes Bandbreitenrichtliniendiensts zu verschaffen, der in der Topologie definiert ist. Zusätzlich können Administratoren die Echtzeitbandbreitennutzung für alle Verbindungen anzeigen, die im Netzwerkkonfigurationsdokument definiert sind.

## Anforderungen

Das Bandbreitenrichtliniendienst-Überwachungstool muss auf einem Computer ausgeführt werden, der Bestandteil der Lync Server-Topologie ist.

## Zusammenfassung

Das Bandbreitenrichtliniendienst-Überwachungstool kann eine wertvolle Ressource für Administratoren sein, um den Zustand aller Bandbreitenrichtliniendienste in der Topologie untersuchen zu können. Wichtiger noch ist aber, dass die Echtzeitbandbreitennutzung für die Verbindungen ermittelt werden kann, die in den Netzwerkkonfigurationseinstellungen definiert sind.

## Bandbreitennutzungsanalyse

Die Bandbreitennutzungsanalyse ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Mithilfe dieser Berichte kann das aktuelle Bandbreitennutzungsmuster analysiert werden, um die Planung der Bandbreitenkapazität zu unterstützen.

## Beschreibung

Die Bandbreitennutzungsanalyse ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Dieses Tool erzeugt Berichte speziell für die Audionutzung über das Netzwerk und hilft bei der Kapazitätsplanung. Das Tool durchläuft außerdem iterativ die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.

## Ausgabe

Die Bandbreitennutzungsanalyse bietet grafische Diagramme der Bandbreitenkapazität und -nutzung durch Audiodaten für alle WAN-Verbindungen, die im System konfiguriert sind.

## Verwendungszweck

Bei allen Sprach- und Videobereitstellungen ist es von entscheidender Bedeutung, Trends der Bandbreitennutzung durch Mediendatenverkehr im Unternehmensnetzwerk zu überwachen und zu verstehen. Genau dies ermöglicht das Bandbreitennutzungsanalyse-Tool einem Administrator. Das Tool bietet folgende Funktionen:

  - Erzeugung spezifischer Berichte für die Audionutzung über das Netzwerk.

  - Hilfe bei einer effektiveren Kapazitätsplanung und iterativer Durchlauf der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.

Die Bandbreitennutzungsanalyse kann grafische Diagramme aus Bandbreitenkapazitäts- und -nutzungsberichten generieren, nämlich folgende:

  - Alle WAN-Verbindungen im Unternehmensnetzwerk

  - Gefiltert nach ausgewählten WAN-Verbindungen

  - Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben.

  - Gefiltert nach WAN-Verbindungen, deren Nutzung der bereitgestellten Bandbreite deutlich zu niedrig ist.

  - Gefiltert nach WAN-Verbindungen, die kritische Grenzwerte erreicht haben (eine Bandbreitennutzung die größer als 90 % der Bandbreitenkapazität der WAN-Verbindung ist).

  - Gefiltert nach WAN-Verbindungstyp: Netzwerkstandortverbindungen, interregionale Verbindungen und Verbindungen innerhalb eines Standorts.

  - Gefiltert nach Netzwerkregion

## Anwendungen

Die Bandbreitennutzungsanalyse besteht aus folgenden zwei Anwendungen (Tools):

  - **WanLinkLogCollector.exe** Dieses Tool ermöglicht seinem Benutzer die Eingabe der erforderlichen Informationen.

  - **BandwidthUtilizationAnalyzer.xlsm** Ein Microsoft Excel-Arbeitsblattsoftwarebericht wird von "WanLinkLogCollector.exe" automatisch gestartet. Diese Anwendung ermöglicht es dem Benutzer, wie später in diesem Artikel gezeigt, Filter auf den Bericht anzuwenden.

## Phasen der Verwendung der Bandbreitennutzungsanalyse

Es gibt zwei Phasen bei der Verwendung der Bandbreitennutzungsanalyse:

  - Erfassung von Protokollen, die mithilfe von "WanLinkLogCollector.exe" durchgeführt wird.

  - Anpassen von Berichten, das mithilfe von "BandwidthUtilizationAnalyzer.xlsm" durchgeführt wird.


> [!IMPORTANT]
> Wir empfehlen dringend, dass "BandwidthUtilizationAnalyzer.xlsm" nicht manuell von Endbenutzern gestartet wird.



## Starten der Bandbreitennutzungsanalyse

Starten Sie "WanLinkLogCollector.exe" an der Eingabeaufforderung oder mithilfe von Windows-Explorer.

**Verwendung von "WanLinkLogCollector.exe"**

Die Verwendung von "WanLinkLogCollector.exe" erfolgt in drei Schritten:

1.  **Protokollieren des zeitlichen Ablaufs** Geben Sie den Zeitraum an, für den der Bericht erstellt werden soll.

2.  **Angeben der Dateiverzeichnisse** Geben Sie Informationen zu Dateispeicherorten an.

3.  **Erfassen der Protokolle und Starten der Berichtsanzeige** Führen Sie den Befehl aus, um den Bericht zu generieren.

## Schritt 1 – Protokollieren des zeitlichen Ablaufs

Durch die Protokollierung des Zeitraums kann der Benutzer des Tools, wie in der Abbildung unten dargestellt, Folgendes angeben.

1.  **Startdatum** Dies ist das Startdatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 1. August 2010.

2.  **Enddatum** Dies ist das Enddatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 30. September 2010.
    
    ![Start- und Enddatum in der Bandbreitennutzung A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start- und Enddatum in der Bandbreitennutzung A")  

## Schritt 2 – Angeben der Dateiverzeichnisse

Die folgenden Dateiverzeichnisse können vom Benutzer wie gezeigt angegeben werden.

  - **Speicherort der Serverprotokolldateien** Der Speicherort der Ordner, wo Bandbreitenrichtlinienserver-Protokolle gespeichert werden. Dies ist normalerweise in "\<Dateiserver\>\\\<Auswahl von FE\>\\AppServerFiles\\PDP".

  - **Speicherort für temporäre Dateien** Der Speicherort temporärer Dateien, an dem Zwischenstufen von Dateien gespeichert werden, während der Bericht generiert wird.

![Dateiverzeichnisse in der Bandbreitennutzungsanalyse](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Dateiverzeichnisse in der Bandbreitennutzungsanalyse")


> [!Note]
> Stellen Sie sicher, dass dem Benutzer des Tools ausreichender Dateizugriff auf den Ordnerspeicherort der Serverprotokolle und der temporären Dateien gewährt wird.



## Schritt 3 – Erfassen der Protokolle und Starten der Berichtsanzeige

Zum Erfassen der Protokolle und zum Starten der Berichtsanzeige klicken Sie, wie unten gezeigt, auf **Execute**. In diesem Schritt werden die erforderlichen Daten erfasst.

![Sammeln von Daten in der Bandbreitennutzungsanalyse](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Sammeln von Daten in der Bandbreitennutzungsanalyse")

Nach erfolgreicher Überprüfung der Eingabe wird die unten wiedergegebene Meldung angezeigt.

![In Protokollen erfasste Benachrichtigung im Bandbreitendienstprogramm](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "In Protokollen erfasste Benachrichtigung im Bandbreitendienstprogramm")

Klicken Sie auf **OK**. "BandwidthUtilizationAnalyzer.xlsm" wird automatisch gestartet. Befolgen Sie die im Meldungsfeld angezeigten Anweisungen. Ausführliche Informationen finden Sie im nächsten Abschnitt unter **Verwenden von "BandwidthUtilizationAnalyzer.xlsm"**.


**Verwenden von "BandwidthUtilizationAnalyzer.xlsm"**

1.  Wenn "BandwidthUtilizationAnalyzer.xlsm" automatisch gestartet wurde, klicken Sie wie unten gezeigt auf **Refresh**.
    
    ![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")

2.  Wenn ein Dateiordner geöffnet wird, wählen Sie wie unten gezeigt "consolidated.csv" an dem Speicherort aus, der im Meldungsfeld angegeben ist. Dort wird außerdem der Speicherort **C:\\Temp** angezeigt.
    
    ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Öffnen eines Ordners in BandwidthUtilizationAnalyzer")

3.  Klicken Sie auf **Import**.

4.  Das grafische Diagramm wird automatisch generiert. Es ist verfügbar, sobald der Hintergrundaktivitäts-Mauszeiger nicht mehr angezeigt wird.
    
    ![Anwenden von Filtern in der Berichtsansicht](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht")

## Anwenden von Filtern auf die Berichtsansicht

Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden im Folgenden beschrieben:

![Anwenden von Filtern in der Berichtsansicht](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht")

1.  **Name** Filtern nach WAN-Verbindungen (der Filter befindet sich rechts von der Grafik). Das Präfix identifiziert die folgenden Verbindungstypen; siehe im vertikalen (blauen) Feld:
    
      - **S Site** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion.
    
      - **IS Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten.
    
      - **R Inter-Region** Die WAN-Verbindung zwischen zwei Netzwerkregionen.

2.  **Exceeded limit** Filtern nach WAN-Verbindungen, deren Bandbreitennutzung die Bandbreitenkapazität übersteigt.

3.  **Critical levels** Filtern nach WAN-Verbindungen, deren Bandbreitennutzung mindestens 90 % der Bandbreitenkapazität erreicht hat.

4.  **Under-utilized** Filtern nach WAN-Verbindungen, deren Bandbreitennutzung weniger als 25 % der Bandbreitenkapazität beträgt.

5.  **Link type** Filtern nach folgenden WAN-Verbindungstypen:
    
      - **Network site**-Typ
    
      - **Inter-site**-Typ
    
      - **Inter-Region link**-Typ

6.  **Region** Filtern nach Netzwerkregion.

Die folgenden Abbildungen zeigen die zuvor beschriebenen Filter.

Filtern nach **Name**. Wählen Sie die Liste der Verbindungen aus, die in dem Diagramm angezeigt werden sollen.

![Filtern nach Name in BandwidthUtilizationAnalyzer](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtern nach Name in BandwidthUtilizationAnalyzer")

Filtern nach **Exceeded limit**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach Exceeded Limit](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtern nach Exceeded Limit")

Filtern nach **Critical levels**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach Critical Levels](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtern nach Critical Levels")

Filtern nach **Under utilized**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach Under Utilized](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtern nach Under Utilized")

Filtern nach **Link Type**. Wählen Sie die Typen aus, die angezeigt werden sollen.

![Filtern nach Link Type](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtern nach Link Type")

Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Verbindungen angezeigt werden sollen.

![Filtern nach Region](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtern nach Region")

## Anforderungen

  - .NET Framework 3.5

  - Microsoft Excel 2010 oder Excel 2007

## Zusammenfassung

Die Bandbreitennutzungsanalyse wird verwendet, um die Audiobandbreitennutzung für UC-Datenverkehr über das Netzwerk grafisch darzustellen. Mithilfe dieses Tools kann ebenfalls die Videobandbreitennutzung im Netzwerk dargestellt werden.

## Anrufparkuhr (Call Parkometer)

Die "Anrufparkuhr" ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Anrufparkorbit-Datenbank ermöglicht.

## Beschreibung

Die "Anrufparkuhr" ist ein Tool zum Nachverfolgen der aktuell geparkten Anrufe. Es erfasst außerdem Statistiken über Orbits und die Nutzung des Anrufparkservers. Dieses Befehlszeilentool bietet sowohl Lese- als auch Schreibzugriff auf die Anrufparkserver-Orbitdatenbank von SQL Server von einem lokal oder remote verbundenen Computer aus.

Alle Optionen schließen sich gegenseitig aus. Befehlszeilensyntax:

  - **–o** (Parameter) – Listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.

  - **–n** (Parameter) – Listet alle aktuell in diesem Pool verwendeten Orbits auf. Folgende Informationen werden angezeigt:
    
      - Der SIP-URI (Session Initiation Protocol Uniform Resource Identifier) der geparkten und der parkenden Person.
    
      - Der Hostname des Anrufparkservers, wo der Anruf geparkt ist.
    
      - Der Zeitstempel, wann der Anruf geparkt wurde.

  - **–f** (Parameter) – Listet die Anzahl der aktuell freien Orbits im Pool auf.

  - **–r \<n\>** (Parameter) – Listet die \<n\> letzten geparkten Anrufe auf. Folgende Informationen werden angezeigt:
    
      - SIP-URI der geparkten Person.
    
      - SIP-URI der parkenden Person.
    
      - Der Hostname des Anrufparkservers, wo der Anruf geparkt wurde.
    
      - Der Zeitstempel, wann der Anruf herangeholt oder abgebrochen wurde.

  - **-t\<n\>** (Parameter) – Testet die Reservierung eines Orbits in der Datenbank, um die Zufälligkeit der zugewiesenen Orbitnummern zu zeigen.

## Ausgabe

In Abhängigkeit von den Eingabeparametern, die an der Befehlszeile angegeben werden, zeigt die "Anrufparkuhr" folgende Ausgaben an:

  - Alle für diesen Pool konfigurierten Orbitbereiche

  - Aktuell geparkte Anrufe

  - Anzahl der freien (verfügbaren) Orbits

  - Zuletzt geparkte Anrufe

  - Für das Testen einheitlicher und zufälliger Orbitwerte reservierte Orbits

## Verwendungszweck

Der Verwendungszweck des Anrufparkserver-Tool besteht darin, Befehlzeilenzugriff auf die Anrufparkserver-Datenbank zu ermöglichen. Der Administrator kann die Anrufparkserver-Nutzung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.

## Anforderungen

Es liegen keine Anforderungen vor, wenn dieses Tool auf demselben Computer wie der Anrufparkserver ausgeführt wird. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von Lync Server 2013 verwendete SQL Server-Datenbank so konfiguriert sein, dass Remotezugriff zulässig ist. Die "Anrufparkuhr" muss mit einer SQL Server-Datenbankverbindungszeichenfolge so konfiguriert sein, dass sie eine Verbindung mit SQL Server des Pools herstellt. Diese SQL Server-Datenbankverbindungszeichenfolge wird in der Konfigurationsdatei **parkometer.exe.config** definiert. Diese muss sich im selben Verzeichnis wie die Datei "parkometer.exe" befinden. Die folgende 
-Datei ist ein Beispiel für eine "parkometer.exe.config"-Datei. Die Parameter, die konfiguriert werden müssen, sind Benutzername (beispielsweise meineDomäne\\Administrator), Kennwort (beispielsweise MeinKennwort) und Hostname (beispielsweise MeinServer).

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

## Beispiele

Bereitgestellt Orbitbereiche: Der Parameter "–o" listet wie gezeigt alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.

![Orbitbereiche in der Anrufparkuhr](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbitbereiche in der Anrufparkuhr")

Aktuell geparkte Anrufe: Der Parameter "–n" listet wie gezeigt alle aktuell verwendeten Orbits in diesem Pool auf.

![Aktuell in der Anrufparkuhr geparkte Anrufe](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Aktuell in der Anrufparkuhr geparkte Anrufe")

Anzahl freier Orbits: Der Parameter "–f" listet wie gezeigt die Anzahl der aktuell freien Orbits im Pool auf.

![Freie Orbitbereiche in der Anrufparkuhr](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Freie Orbitbereiche in der Anrufparkuhr")

Zuletzt geparkte Anrufe: Der Parameter "–r \<n\>" listet wie gezeigt die \<n\> letzten geparkten Anrufe auf.

![Zuletzt in der Anrufparkuhr geparkte Anrufe](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Zuletzt in der Anrufparkuhr geparkte Anrufe")

Testen der Orbitreservierung: Der Parameter "–t \<n\>" testet wie gezeigt die Reservierung eines Orbits in der Datenbank.

![Testorbitreservierungen in der Anrufparkuhr](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testorbitreservierungen in der Anrufparkuhr")

## Zusammenfassung

Die "Anrufparkuhr (Call Parkometer)" ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.

## CleanupStorageServiceData

Das Resource Kit-Tool "CleanupStorageServiceData" ermöglicht das Löschen von verwaisten Daten in der Datenbank, die vom Lync Server-Speicherdienst (LYSS) verwendet wird. Eine Funktion des Speicherdiensts besteht darin, die Kommunikation zwischen Lync Server und verschiedenen Back-End-Datenspeicherungs-Endpunkten wie SQL Server und Exchange zu puffern.

## Beschreibung

Zur Unterstützung von Hochverfügbarkeit akzeptiert und speichert LYSS temporär Kopien der Daten auf mehreren Front-End-Servern im Pool und entfernt diese Daten, sobald sie an ihrem endgültigen, langfristigen Speicherort angelangt sind. Es gibt ungewöhnliche Situationen, die während des normalen Betriebs auftreten können, in denen ein Server abstürzen kann oder es zu Verarbeitungsproblemen kommen kann, sodass eventuell Daten nicht ordnungsgemäß bereinigt werden. Diese Daten sind harmlos, belegen aber begrenzte Verarbeitungsressourcen. Viele Vorgänge der erforderlichen, normalen Datenpflege sind automatisiert, doch dieses Tool ermöglicht Ihnen die sichere Identifizierung und Entfernung solcher verwaisten Daten, wenn ein automatisiertes Entfernen nicht möglich ist. Die Nutzung dieses Tools ist angezeigt, wenn eine System Center Operations Manager-Benachrichtigung (SCOM) der Systemüberwachung ausgelöst wird, in der der Administrator aufgefordert wird, die nicht mehr benötigten Daten aus den lokalen LYSS-Datenbanken im Pool zu entfernen. Auf dem Front-End-Server, von dem die Benachrichtigung ausgelöst wurde, wird ein entsprechendes Ereignis im Ereignisprotokoll erfasst. Die Ergebnisdetails enthalten Informationen zum Umfang der verwaisten Daten, die sich auf dem Front-End-Server befinden, und die Benachrichtigung wird ausgelöst, wenn die Daten bestimmte, voreingestellte Schwellenwerte überschreiten.

## Anforderungen

Installation von Resource Kit-Tools in Lync Server 2013. Das Tool wird auf Computern ausgeführt, die einer Domäne beigetreten sind und auf denen Lync Server und Verwaltungsshell für Lync Server 2013 installiert sind. Das Tool verwendet ein Cmdlet der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren. Weiterhin muss das Tool von einem Computer im Pool aus ausgeführt werden, auf dem die **RtcLocal**-Datenbank installiert ist. Diese Datenbank wird vom CleanupStorageServiceData-Tool verwendet, um die Verbindungsdetails abzurufen, die für die Kommunikation mit dem Lync Server-Routingdienst erforderlich sind. Schließlich müssen das Konto oder die Anmeldeinformationen mit denen das Tool aufgerufen wird, Lese-/Schreibberechtigungen für die Dateifreigabe besitzen, auf die sie das Ausgabeprotokoll schreiben sollen. Außerdem ist dieses Tool davon abhängig, dass sich der Pool in einem stabilen Zustand befindet. Im Wesentlichen heißt dies, dass davon ausgegangen wird, dass jeder Front-End-Server ausgeführt wird und verfügbar ist, dass mit der LYNCLOCAL-Instanz von SQL Server und der LYSS-Datenbank eine Verbindung hergestellt werden kann, und dass jede Routinggruppe über einen vollständigen Satz aus 1 primären Front-End-Server und 2 sekundären Front-End-Servern verfügt.

## Beispiele

C:\\Programme\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

## DBAnalyze

## Beschreibung

DBAnalyze ist ein Befehlszeilentool, das Administratoren bei der Erfassung von Analyseberichten über die Lync Server 2013-Datenbank hilft. DBAnalyze verfügt über folgende Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:

  - **Diagnosemodus (Diagnostic)** Erstellt einen Bericht, der Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße) sowie die folgenden Informationen umfasst: Größe der Daten- und Protokolldateien, Zeitpunkt der letzten Sicherung, Kontaktverteilung zwischen Servern, auf denen Microsoft Office Communications Server ausgeführt wird, die durchschnittliche Anzahl von Berechtigungen, Kontakten, Containern, Abonnements, Veröffentlichungen, Endpunkten pro Benutzer, alle nicht ordnungsgemäß gehosteten Benutzer, Benutzer, die nicht geroutet werden können, die durchschnittliche Anzahl von organisierten Konferenzen pro Benutzer, geplante Konferenzen, aktive Konferenzen und die Datenbankversion.
    

    > [!Note]
    > Die Ausführung im Diagnosemodus kann die Serverleistung beeinträchtigen.



  - **Benutzerdatenmodus (User data)** Berichtet Kontakt-, Container-, Abonnement-, Veröffentlichungs-, Berechtigungs- und Kontaktgruppendaten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in ihren Kontakt- oder Berechtigungslisten haben. Dieser Modus berichtet außerdem Zusammenfassungsdaten für Konferenzen, die von einem Benutzer organisiert werden oder zu denen er eingeladen ist.

  - **Konferenzmodus (Conference)** Berichtet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Details zu Planungszeiten für die Konferenz, der Liste der eingeladenen Teilnehmer, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCUs (Multipoint Control Units), der Liste aktiver Teilnehmer sowie des Signalisierungszustands jedes Teilnehmers.

  - **Besprechungs-ID decodieren (Decode Meeting ID)** Decodiert eine PSTN-Besprechungs-ID (öffentliches Telefonnetz), die über den Parameter **/pstnid** angegeben wird, stellt aber keine Verbindung mit dem Back-End-Server her, um detaillierte Informationen abzurufen.

  - **Konferenz auflösen (Resolve conference)** Decodiert eine PSTN-Besprechungs-ID (öffentliches Telefonnetz), die über den Parameter **/pstnid** angegeben wird, und zeigt Informationen zu der durch die ID angegebenen Konferenz an.

  - **MCUs-Modus** Berichtet die ID, den Medientyp, die URL, den Taktstatus, die Konferenzauslastung und die Teilnehmerauslastung für jede MCU im Pool.

  - **Datenträgerfragmentierung-Modus (Disk fragmentation)** Zeigt den Fragmentierungsstatus aller Datenträger an.

Mithilfe dieses Tools können Sie verschiedene Probleme diagnostizieren, oder es kann Administratoren bei der Kapazitätsplanung unterstützen. Wenn beispielsweise die meisten der auf Server A gehosteten Benutzer Benutzer als Kontakte wählen, die auf Server B gehostet werden, kann der Administrator die Benutzer von Server A auf Server B verschieben, um den Datenverkehr zwischen Servern zu verringern.

## Ausgabe

Dieses Tool gibt vordefinierte Berichte über die Lync Server 2013-Datenbank aus. **Pfad:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit

## Verwendungszweck

Um "Dbanalyze.exe" zu installieren, kopieren Sie die Datei in einen lokalen Ordner, und führen Sie dann das Tool aus. Um das Tool zu verwenden, führen Sie folgenden Befehl in der Befehlszeile aus: `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Die Beschreibungen der Befehlszeilenoptionen finden Sie weiter unten.

![Befehlszeilenoptionen für Dbanalyze.exe](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Befehlszeilenoptionen für Dbanalyze.exe")

## Anforderungen

**Computer** DBAnalyze kann nur auf einem Computer ausgeführt werden, der einer Domäne beigetreten ist und auf dem Lync Server 2013 installiert ist.

**Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.

**Software** Die Lync Server 2013-Softwarekomponenten müssen installiert sein, bevor DBAnalyze ausgeführt wird.

**Benutzer** Die folgende Tabelle zeigt die Administratoren, die über die notwendigen Berechtigungen für den Zugriff auf Lync Server 2013-Datenbank verfügen.

![Berechtigungstabelle für Dbanalyze.exe](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Berechtigungstabelle für Dbanalyze.exe")


> [!Note]
> Ein lokales Administratorkonto ist erforderlich für den <STRONG>/report:disk</STRONG>-Modus.



## Beispiele

Im Folgenden finden Sie Beispiele für gültige "Dbanalyze.exe"-Befehle:

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

## Zusammenfassung

DBAnalyzer bietet Administratoren eine einfache und schnelle Möglichkeit zum Analysieren von Lync Server 2013-Datenbanken.

## ImportStorageServiceData

Das Resource Kit-Tool "ImportStorageServiceData" ermöglicht das Reimportieren von Warteschlangen- und Endpunktdaten, die aus dem Speicherdienst (LYSS) geleert wurden, zurück in den Speicherdienst.

## Beschreibung

Die Leerung der Daten aus dem Speicherdienst kann automatisch (regelmäßig) auf Grundlage des Warteschlangenelementstatus oder der Datenbankgröße erfolgt sein. Das Leeren kann aufgrund eines manuellen Aufrufs des Cmdlets für Poolfailover oder des Cmdlets "StorageServiceFullFlush" (das vom Cmdlet für Poolfailover aufgerufen wird) erfolgt sein. Beachten Sie, dass Daten idealerweise nicht reimportiert werden sollten, wenn die Größe einer der Speicherdienstdatenbanken (LYSS ) auf den Front-End-Servern das normale Niveau übersteigt, weil hierdurch sonst wahrscheinlich sogar noch mehr Daten wiederum ausgelagert werden. Darüber hinaus sollten zuerst alle Probleme behoben werden, die möglicherweise Fehler ausgelöst haben, durch die das Anwachsen der Speicherdienst-Warteschlange verursacht wurde (beispielsweise Exchange-Endpunktfehler, Netzwerkprobleme oder andere Probleme).

**Szenario 1:** Während eines Poolfailovers werden Dateien möglicherweise aus dem Speicherdienst für jeden Front-End-Server geleert. Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.

**Szenario 2:** Daten werden jeden Tag oder als Reaktion darauf, dass die Speicherdienstdatenbank bestimmte Größenschwellenwerte überschreitet (beispielsweise 60 %, 80 %, 90 % voll), automatisch geleert. Diese automatisch geleerten Daten sollten vom Administrator routinemäßig reimportiert werden. In der oben genannten Situation, wenn das SCOM-Überwachungspaket nicht bereitgestellt ist, treten Ereignisse für den Lync Server-Speicherdienst auf, die im Zusammenhang mit dem Leeren von Daten aus dem Speicherdienst stehen – die Ereignis-IDs 32075 (vollständiger Leerungsvorgang wurde gestartet), 32076 (vollständiger Leerungsvorgang wurde abgeschlossen), 32082 (Leerung auf Wartungsebene wurde gestartet), 32083 (Leerung auf Wartungsebene wurde abgeschlossen), 32089 (Leerung aufgrund des Füllens der Datenbank aufgetreten). Beachten Sie, dass diese Ereignis-IDs der RTM-Version entsprechen. Wenn ein Administrator diese Ereignisse sieht, heißt das, dass Dateien vorhanden sind, die geleert wurden. Diese Daten sollten routinemäßig mithilfe dieses Tools reimportiert werden, beispielsweise einmal pro Woche.

Bei der Onlinedienstversion, wenn das SCOM-Systemüberwachungspaket für Lync Server bereitgestellt ist, können neue Benachrichtigungen ausgelöst werden, in denen der Administrator aufgefordert wird, die geleerten Daten erneut in den Speicherdienst zu importieren. Auf dem Front-End-Server, von dem die Benachrichtigung ausgelöst wurde, wird ein entsprechendes Ereignis im Ereignisprotokoll erfasst. Das Ereignis liefert dann eine Beschreibung des übergeordneten Pfads, in dem sich die Dateien mit den geleerten Daten befinden, sowie die Anzahl der vorhandenen Dateien, die die Benachrichtigungskriterien erfüllen. Das Benachrichtigungskriterium ist, dass X oder mehr Dateien in dem bestimmten übergeordneten Pfad vorhanden sind, die mindestens Y Tage alt sind (wobei X und Y im Speicherdienst voreingestellt sind, aber durch Ändern der Datei "APPCONFIG" außer Kraft gesetzt werden können). Im Folgenden finden Sie zwei Beispiele für Ereignisse, die die Integritätsbenachrichtigung auslösen können, wobei sie sich durch ihren übergeordneten Pfad unterscheiden. Eine Möglichkeit ist auf der Webdienst-Dateifreigabe, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis auf jedem Front-End-Server ist (beispielsweise "C:\\ProgramData\\Microsoft\\Lync Server\\StorageService"). Der Administrator führt dann dieses reskit-Tool aus.

Dieses Tool erhöht die Auslastung von CPU und E/A-Vorgängen auf dem Front-End-Server, auf dem es ausgeführt wird, sowie auf anderen Front-End-Servern, wenn der Front-End-Server, auf dem das Tool ausgeführt wird, nicht Besitzer der Daten ist. Wir empfehlen die Ausführung dieses Tools, die Auslastung von CPU und E/A-Vorgängen auf den Front-End-Servern niedrig ist, beispielsweise außerhalb von Stoßzeiten. Darüber hinaus kann dieses Tool 2 bis 3 Minuten für den Import einer Datendatei benötigen. Denken Sie hieran, wenn Sie die voraussichtliche Ausführungsdauer des Tools abschätzen. Die von dem Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt. Löschen Sie sie, wenn darin keine Fehler gemeldet werden, da die Protokolldatei mehrere 10 MB und größer sein kann.

![Beispielereignisse für das Ereignisprotokoll des Speicherservers](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Beispielereignisse für das Ereignisprotokoll des Speicherservers")

## Anforderungen

Installation von Resource Kit-Tools in Lync Server 2013. Das Tool wird auf Computern ausgeführt, die einer Domäne beigetreten sind und auf denen Lync Server und Lync Server-Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren. Weiterhin muss das Tool von einem Computer im Pool aus ausgeführt werden, auf dem die **RtcLocal**-Datenbank installiert ist. Diese Datenbank wird von dem Tool verwendet, um den Speicherort der Dateifreigabe "WEBSERVICE" für den Pool abzurufen. Zusätzlich muss, bevor das Tool verwendet wird, auf jedem Front-End-Server Windows PowerShell-Remoting unter Verwendung von **Enable-PSRemoting** aktiviert werden sowie auf dem Computer, auf dem das Tool ausgeführt wird. Andernfalls schlagen Windows PowerShell-Remotebefehle dieses Tools fehl. Windows PowerShell-Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem das Tool fertig gestellt wurde. Schließlich müssen das Konto oder die Anmeldeinformationen, mit denen das Tool aufgerufen wird, über Lese-/Schreibberechtigungen für die Dateifreigabe "WEBSERVICE" des Pools verfügen, in dem dieses Tool ausgeführt wird. Andernfalls schlägt das Tool mit E/A-Berechtigungsfehlern fehl.


> [!Note]
> Unter Windows Server 2012 ist Windows PowerShell-Remoting standardmäßig aktiviert, aber nicht unter Windows Server&nbsp;2008-Betriebssystem.



## Beispiele

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

## LCSSync

Das LCSSync-Tool hilft dabei, Lync Server 2013-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen bereitzustellen. Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzergesamtstrukturen als Active Directory-Domänendienste-Kontaktobjekt in eine zentrale Gesamtstruktur zu synchronisieren, in der Lync Server 2013 installiert ist.

## Beschreibung

LCSSync verwendet die synchronisierten Active Directory-Domänendienste-Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzer für Lync Server zu aktivieren. Um einmaliges Anmelden bereitzustellen, muss das primäre Benutzerkonto dem Active Directory-Domänendienste-Kontaktobjekt in der zentralen Gesamtstruktur für Lync Server 2013 zugeordnet sein. Dieses Tool hilft bei der Durchführung dieser Zuordnung. Da Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents in Microsoft Identity Integration Server bereit.

## Zusammenfassung

Das LCSSync-Tool hilft dabei, Lync Server in einer Umgebung mit mehreren Gesamtstrukturen bereitzustellen.

## LookupUserConsole

Das LookupUserConsole-Tool zeigt interne Lync Server-Routinginformationen zu bestimmten Benutzern an. Diese Informationen können den Mitarbeitern des Microsoft-Supports dabei helfen, Probleme bei der Bereitstellung und dem Routing zu diagnostizieren.

## Beschreibung

Durch das Ausführen von "LookupUserConsole.exe" wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert und versucht, interne Lync Server-Routinginformationen zu den Adressen anzuzeigen. Geben Sie **exit** ein, um das LookupUserConsole-Tool zu beenden.

## Anforderungen

Installation von Resource Kit-Tools in Lync Server 2013. Das Tool wird auf Computern ausgeführt, die einer Domäne beigetreten sind und auf denen Lync Server installiert ist.

## Beispiele

C:\\Programme\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe

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

## MsTurnPing

Das Tool "MSTurnPing" ermöglicht einem Administrator von Microsoft Lync Server 2013-Kommunikationssoftware das Überprüfen des Status der Server, auf denen die Audio-/Video-Edge- und Audio-Video-Authentifizierungsdienste ausgeführt werden, sowie der Server, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

## Beschreibung

Das Tool "MSTurnPing" ermöglicht einem Administrator von Lync Server 2013-Kommunikationssoftware das Überprüfen des Status der Server, auf denen die Audio-/Video-Edge- und Audio-Video-Authentifizierungsdienste ausgeführt werden, sowie der Server, auf denen Bandbreitenrichtliniendienste in der Topologie ausgeführt werden.

Das Tool ermöglicht dem Administrator die Ausführung der folgenden Tests:

1.  A/V-Edgeservertest: Das Tool führt Tests mit allen A/V-Edgeservern in der Topologie durch, indem Folgendes ausgeführt wird:
    
      - Überprüfung, ob der Lync Server-Audio-Video-Authentifizierungsdienst gestartet ist und ordnungsgemäße Anmeldeinformationen ausstellen kann.
    
      - Überprüfung, ob der Lync Server-Audio-/Video-Edgedienst gestartet ist und die Ressourcen auf dem externen Edgeserver erfolgreich zuordnen kann.

2.  Bandbreitenrichtliniendienst-Test: Das Tool führt Tests mit allen Servern in der Topologie durch, auf denen die Bandbreitenrichtliniendienste ausgeführt werden, indem Folgendes ausgeführt wird:
    
      - Überprüfung, ob der Lync Server-Bandbreitenrichtliniendienst (Authentifizierung) gestartet ist und ordnungsgemäße Anmeldeinformationen ausstellen kann.
    
      - Überprüfung, ob der Lync Server-Bandbreitenrichtliniendienst (Kern) gestartet ist und die Bandbreitenprüfung erfolgreich durchführen kann.

Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist.

## Ausgabe

Das Tool gibt die Ergebnisse von jedem Vorgang aus.

  - Wenn der **AudioVideoEdgeServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:
    
      - Die Testergebnisse der Computer, die den Lync Server-Audio-Video-Authentifizierungsdienst in der Topologie bereitstellen.
    
      - Die Testergebnisse der Computer, die den Lync Server-Audio-/Video-Edgedienst in der Topologie bereitstellen.

  - Wenn der **BandwidthPolicyServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:
    
      - Die Testergebnisse der Computer, die den Lync Server-Bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen.
    
      - Die Testergebnisse der Computer, die den Lync Server-Bandbreitenrichtliniendienst (Kern) in der Topologie bereitstellen.

## Anforderungen

  - Dieses Tool muss auf einem Computer ausgeführt werden, der sich in der Topologie befindet und auf dem sich der lokale Speicher befindet.

  - Das Tool muss als Administrator mit Zugriff auf den lokalen Speicher ausgeführt werden.

## Beispiele

Im Folgenden finden Sie ein Beispiel für die Toolausgabe.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

## Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Lync Server 2013-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio-/Video- und Bandbreitenrichtliniendienste ausgeführt werden.

## Netzwerkkonfigurationsanzeige

Mithilfe der Netzwerkkonfigurationsanzeige können Administratoren von Microsoft Lync Server 2013- Kommunikationssoftware die CAC-Netzwerktopologie (Call Admission Control, Anrufsteuerung) für ein Unternehmen anzeigen, die bereitgestellt wird, um Echtzeitkommunikationssitzungen zu ermöglichen wie Sprach- oder Videoanrufe, basierend auf einer vorgegebenen Bandbreitenkapazität. Lync Server 2013-Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtliniendiensten durchgesetzt werden, die zusammen mit Lync Server 2013 installiert werden.

## Beschreibung

Mithilfe der Netzwerkkonfigurationsanzeige (NetworkConfigurationViewer.exe) können Administratoren die folgenden Aufgaben durchführen:

  - Laden und Anzeigen der CAC-Netzwerktopologie aus einer Lync Server 2013-Bereitstellung in einem Grafikformat.

  - Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat.

  - Sichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger.

  - Sichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format.

  - Anzeigen von CAC-Netzwerktopologie-Konfigurationsdaten.

  - Anzeigen der CAC-Netzwerktopologie in einer Strukturansicht.

  - Definieren benutzerdefinierter Connectors für CAC-Netzwerktopologieverbindungen (beispielsweise Standort-zu-Region-, Region-zu-Region- oder Standort-zu-Standort-Verbindungen).

  - Anzeigen von CAC-Netzwerktopologie-Standortinformationen, -Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen.

## Verwendungszweck

Anzeigen der CAC-Netzwerktopologieverbindungen des Unternehmens in einer grafischen Benutzeroberfläche.

## Beispiele

**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Lync Server 2013-Bereitstellung in einem Grafikformat:** Lync Server 2013-Administratoren können die CAC-Netzwerktopologiekonfiguration auf jedem Lync Server 2013-Computer laden und anzeigen, indem sie die Option **Download Network Configuration** wie in der Abbildung unten gezeigt verwenden. Wenn das Tool auf einem Computer bereitgestellt wird, der keine Verbindung mit dem Lync-Konfigurationsspeicher hat, kann es eine solche Konfiguration nicht herunterladen oder anzeigen.

![Herunterladen der Netzwerkkonfiguration](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Herunterladen der Netzwerkkonfiguration")

**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat:** Lync Server 2013-Bandbreitenrichtlinienserver speichern die CAC-Netzwerktopologie im Rahmen des Protokollierungsmechanismus am Speicherort der Lync Server 2013-Dateifreigabe. Lync Server-Administratoren können eine solche Datei in einem Grafikformat anzeigen, indem sie die Option **Open Network Configuration** wie unten gezeigt verwenden.

![Öffnen einer Bandbreitenrichtlinienserver-Protokolldatei](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Öffnen einer Bandbreitenrichtlinienserver-Protokolldatei")

Sichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger: Lync Server 2013-Administratoren können die CAC-Netzwerktopologie-Konfigurationsdatei in einem XML-Format speichern, indem sie die Option **Save a copy of Network Configuration** wie unten gezeigt verwenden. Die gespeicherte Konfigurationsdatei kann dann offline zum Zwecke der grafischen Anzeige verwendet werden.

![Speichern der Netzwerkkonfiguration als XML-Datei](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Speichern der Netzwerkkonfiguration als XML-Datei")

Sichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format: Lync Server 2013-Administratoren können die CAC-Netzwerktopologie-Konfiguration in einem Grafikformat speichern (Dateiformate JPG oder BMP), indem sie die Option **Save Network Configuration diagram as picture** wie unten gezeigt verwenden.

![Speichern der Netzwerkkonfiguration als Bild](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Speichern der Netzwerkkonfiguration als Bild")

**Anzeigen von CAC-Netzwerktopologie-Konfigurationsdaten:**Lync Server 2013-Administratoren können verwandte Netzwerkkonfigurationsdaten wie Netzwerkregionen, Netzwerkstandorte, Bandbreitenprofile und Standort-Subnetz-IP-Adressen in einem Textformat anzeigen, indem sie die Option "View Network Configuration data" wie unten gezeigt verwenden.

![Anzeigen von Netzwerkkonfigurationsdaten](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten")

**Anzeigen der CAC-Netzwerktopologie in einer Strukturansicht:** Lync Server 2013-Administrators können verwandte Netzwerkkonfigurationsdaten in einer grafischen Strukturansicht anzeigen, indem sie die Systemsteuerung im linken Bereich des Toolfensters wie unten gezeigt verwenden.

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht")

**Definieren benutzerdefinierter Connectors für CAC-Netzwerktopologieverbindungen (beispielsweise Standort-zu-Region-, Region-zu-Region- oder Standort-zu-Standort-Verbindungen):**Lync Server 2013-Administratoren können benutzerdefinierte grafische Connectors für CAC-Netzwerkkonfigurations-WAN-Verbindungen definieren, indem sie die Option "Settings" wie unten gezeigt verwenden. Dies hilft bei der Unterscheidung zwischen verschiedenen Typen von Netzwerkverbindungen, die in der Netzwerkkonfiguration bereitgestellt sind.

![Definieren von benutzerdefinierten Connectors für die CAC-Netzwerktopologie](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für die CAC-Netzwerktopologie")

**Anzeigen von CAC-Netzwerktopologie-Standortinformationen, -Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen:**Lync Server 2013-Administratoren können verwandte CAC-Netzwerkregionsinformationen, -Standortinformationen und CAC-Bandbreitenbereitstellungs-Informationen anzeigen, indem sie die unten angezeigten Optionen verwenden. (Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **Info**.)

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk9](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für Ihr Netzwerk9")

## Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Lync Server 2013-Administratoren sein, die die CAC-Netzwerktopologie für ihre Bereitstellung in einem Grafikformat anzeigen möchten.

## Reaktionsgruppen-Agent Live

Die Reaktionsgruppenanwendung gibt Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zuzugreifen. Unglücklicherweise sind außerhalb der Anwendung keine grafischen Ansichten dieser Daten verfügbar. Das Resource Kit-Tool "Reaktionsgruppen-Agent Live" löst dieses Problem, indem es eine einfache, grafische Möglichkeit für den Zugriff auf diese Informationen bereitstellt, erweitert durch Echtzeitinformationen der Microsoft Lync 2013-Kommunikationssoftware wie die Anwesenheit anderer Agents.

## Beschreibung

Der Reaktionsgruppen-Agent Live ist eine Windows-Anwendung, die An- und Abmeldefunktionen sowie einige Echtzeitinformationen (wie Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bietet. Das Tool ist als erweiterte Version der Seite "Agent Groups" (Zugriff hierauf über Lync 2013) gedacht.

## Verwendungszweck

Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschleife und leitet sie dann an Agentgruppen weiter. Um informierte Entscheidungen darüber treffen zu können, welche Anrufe bedient werden sollen, können Agents auf Echtzeitinformationen zu ihren Agentgruppen zugreifen, beispielsweise welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, die anfänglich nur durch den Reaktionsgruppendienst verfügbar sind, werden auf intuitive Weise von Reaktionsgruppen-Agent Live zur Verfügung gestellt.

## Features

Das Tool Reaktionsgruppen-Agent Live basiert auf dem Reaktionsgruppendienst und dem Microsoft Lync 2013 SDK. Es bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die durch den Reaktionsgruppendienst verfügbar sind (wie Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl wartender Anrufe).

Die Abbildung unten illustriert die Hauptoberfläche des Reaktionsgruppen-Agent Live.

![Das Tool "Reaktionsgruppen-Agent Live"](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Das Tool \"Reaktionsgruppen-Agent Live\"")

Folgende drei Hauptfeatures stehen Agents im Reaktionsgruppen-Agent Live zur Verfügung:

  - **An-/Abmeldung:** Im Gegensatz zur Seite "Agent Groups" (Zugriff hierauf über Lync 2013) ermöglicht der Reaktionsgruppen-Agent Live nur Agents das gleichzeitige An- oder Abmelden bei allen Agentgruppen. Diese Anwendung bietet Agents drei schnelle Methoden zum An- bzw. Abmelden:
    
      - Klicken Sie in der Anwendung auf die Schaltflächen zum An-/Abmelden (grün und rot).
    
      - Klicken Sie mit der rechten Maustaste auf das Symbol in der Taskleiste, und wählen Sie "Anmelden" oder "Abmelden".
    
      - Verwenden konfigurierbarer Tastenkombinationen

  - **Gruppenmitgliedschaft:** Wenn eine Agentgruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an. Wenn Lync 2013 auf demselben Computer wie diese Anwendung ausgeführt wird, werden im Reaktionsgruppen-Agent Live Anwesenheitsinformationen und die Visitenkarte angezeigt. Agents können eine Chatnachricht senden oder andere Agents direkt von dort aus anrufen.

  - **Echtzeitstatistiken:** Der Reaktionsgruppen-Agent Live bietet Echtzeitstatistiken für alle Agentgruppen. Die Aktualisierungshäufigkeit ist eine Minute. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein optischer Indikator mit der Anzahl aktuell wartender Anrufe hinzugefügt. Wenn Sie mit dem Mauszeiger auf einer Gruppe verweilen, wird außerdem die längste Wartezeit angezeigt.

## Anforderungen

Der Reaktionsgruppen-Agent Live erfordert .NET Framework 4.0. Zusätzlich muss, um die Anwesenheits- und Visitenkartenfeatures nutzen zu können, Lync 2013 lokal installiert sein (und ausgeführt werden).

## Konfiguration

Der Reaktionsgruppen-Agent Live kann mithilfe des Dialogfelds "Options" in der Anwendung an die individuellen Anforderungen angepasst werden. Darüber hinaus kann der Administrator die Standardhostadresse definieren, indem er die Eigenschaft "defaultHostAddress" in der Datei "RGAgentLive.exe.config" direkt bearbeitet.

Die Abbildung unten illustriert das Dialogfeld "Options", das Agents verwenden können, um die Hostadresse und Tastenkombinationen zu konfigurieren. Dieses Dialogfeld wird angezeigt, indem Sie in der Hauptbenutzeroberfläche rechts oben auf die Schaltfläche "Options" klicken.

![Das Dialogfeld mit Optionen für "Reaktionsgruppen-Agent Live"](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Das Dialogfeld mit Optionen für \"Reaktionsgruppen-Agent Live\"")

Folgende drei unterschiedliche Einstellungen können in der Konfiguration des Reaktionsgruppen-Agents Live angepasst werden:

  - Hostadresse: Dies ist normalerweise der FQDN des Webpools, der zum Home-Pool des Agents gehört. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads an den Host).

  - Tastenkombinationen: Die genauen Tastenkombinationen zum An- und Abmelden können angepasst werden. Die einzige Einschränkung dabei ist, dass beide Tastenkombinationen die WINDOWS-TASTE (Taste mit dem Windows-Logo) enthalten müssen (zusätzlich zu mindestens einer weiteren Taste).

  - Starten mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch beim Starten von Windows gestartet wird.

## Beispiele

Die Abbildung unten zeigt, wie Sie einen anderen Agent anrufen oder ihm eine Chatnachricht senden, indem Sie mit der rechten Maustaste auf den Kontakt im rechten Bereich klicken.

![Anruf tätigen oder Chatnachricht senden](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Anruf tätigen oder Chatnachricht senden")

Die Abbildung unten zeigt, wie der Reaktionsgruppen-Agent Live die aktuelle Anzahl von Anrufen in der Warteschleife sowie die längste Wartezeit all dieser eingehenden Anrufe anzeigt.

![Anzeigen von Warteschlangeninformationen](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Anzeigen von Warteschlangeninformationen")

## Zusammenfassung

Schnelles An- und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Features für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind. Mit dem Resource Kit-Tool "Reaktionsgruppen-Agent Live" können Lync-Administratoren ihren Agents eine Windows-Anwendung bereitstellen, die es ihnen erlaubt, Aufgaben schneller und grafisch basiert zu erledigen.

## SEFAUtil

SEFAUtil (Secondary Extension Feature Activation, sekundäre Erweiterungsfeatureaktivierung) ist ein Befehlszeilentool, das es Administratoren von Microsoft Lync Server 2013-Kommunikationssoftware und Helpdesk-Agents ermöglicht, Anrufen von Stellvertretungen, Anrufweiterleitung, paralleles Anrufen, Teamanrufeinstellungen und Gruppenanrufannahme im Auftrag eines Lync Server 2013-Benutzers zu konfigurieren. Das Tool ermöglicht Administratoren auch die Abfrage der Anrufweiterleitungseinstellungen, die für einen bestimmten Benutzer veröffentlicht sind.Das SEFAUtil-Tool ermöglicht es dem Administrator, die Anrufweiterleitung oder das parallele Anrufen im Auftrag des Benutzers zu aktivieren/deaktivieren/ändern. Der Administrator kann das Ziel angeben (in Form eines SIP-URIs) oder ein Ziel verwenden, das bereits von dem Benutzer veröffentlicht wurde. Dieses Tool ermöglicht Administratoren außerdem das Hinzufügen oder Entfernen von Stellvertretungen oder Mitgliedern von Teamanrufgruppen im Auftrag des Benutzers. Dieses Tool basiert auf Microsoft Unified Communications Managed-API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.

SEFAUtil (Secondary Extension Feature Activation, sekundäre Erweiterungsfeatureaktivierung) ermöglicht Lync Server 2013-Administratoren und Helpdesk-Agents Anrufen von Stellvertretungen, Anrufweiterleitung, paralleles Anrufen, Teamanrufeinstellungen und Gruppenanrufannahme im Auftrag eines Lync Server 2013-Benutzers zu konfigurieren. Dieses Tool ermöglicht Administratoren auch die Abfrage der Anrufweiterleitungseinstellungen, die für einen bestimmten Benutzer veröffentlicht sind.

## Beschreibung

Die aktuelle Version von SEFAUtil ist ein reines Befehlszeilentool. Eine unterstützende grafische Benutzeroberfläche ist nicht vorhanden. Dieses Tool basiert auf Microsoft Unified Communications Managed-API (UCMA) 3.0. Die in diesem Tool vorhandenen Features ermöglichen Administratoren und Helpdesk-Agents Folgendes:

  - Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (umfasst Anrufweiterleitung, Stellvertretung, paralleles Anrufen, Teamanruf- und Gruppenanrufannahme)

  - Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellungen (umfasst Ziel und Timer für "Keine Antwort")

  - Aktivieren/Deaktivieren/Ändern der Konfiguration für sofortige Anrufweiterleitung

  - Aktivieren/Deaktivieren/Ändern von Stellvertretungseinstellungen

  - Aktivieren/Deaktivieren/Ändern von Teamanrufgruppen-Einstellungen
    

    > [!Note]
    > Neue Funktion im Lync Server 2013 SEFAUtil-Tool



  - Aktivieren/Deaktivieren/Ändern der Einstellungen für paralleles Anrufen (umfasst Ziel)
    

    > [!Note]
    > Neue Funktion im Lync Server 2013 SEFAUtil-Tool



  - Aktivieren/Deaktivieren/Ändern von Einstellungen für Gruppenanrufannahme
    

    > [!WARNING]
    > Neue Funktion im Lync Server 2013 SEFAUtil-Tool



Dieses Tool unterliegt folgenden Beschränkungen:

  - Unterstützung nur für Benutzer, die in einem Lync Server-Pool gehostet werden.

  - Die Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer wird nicht unterstützt.

## Ausgabe

Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster Ausgaben zur Verfügung. Details hierzu finden Sie weiter unten in diesem Dokument im Abschnitt mit den Beispielen.

## Verwendungszweck

Im Folgenden finden Sie einige der Hauptszenarios, in denen dieses Tool eingesetzt werden kann:

  - Bob ist Manager und wurde zur Lync Server-Telefonie migriert. In seiner vorhandenen Telefonanlage hat er Stellvertretungen eingerichtet. Als Teil des Umzugs zu Lync kann der Administrator Bobs Umleitung so zu konfigurieren, dass sie seiner bisherigen Stellvertretungskonfiguration entspricht.

  - Alice ist auf Reisen und stellt fest, dass sie einen wichtigen Anrufe eines ihrer Kunden erwartet. Sie befindet sich aber gerade im Hotel und hat keinen Computer zur Verfügung. Sie ruft den Helpdesk an und bittet darum alle Anrufe an ihre Büronummer auf Ihr Mobiltelefon weiterzuleiten. Die Helpdeskmitarbeiter können diese Konfiguration in ihrem Auftrag vornehmen.

  - Joes Anrufe an seine Büronummer landen immer auf seiner mobilen Voicemail, wenn er bei der Arbeit ist. An den meisten anderen Standorten scheint aber alles richtig zu funktionieren. Der Helpdesktechniker kann sich Joes Weiterleitungskonfiguration ansehen und entdeckt, dass Joe paralleles Anrufen für sein Mobiltelefon konfiguriert hat. Der Techniker befragt Joe über die Qualität der mobilen Netzabdeckung an seinem Arbeitsplatz und kann so bestimmen, dass die Regel für paralleles Anrufen dafür verantwortlich ist, dass alle Anrufe bei schlechter Netzabdeckung an Joes mobile Voicemail gehen.

  - Mike ist ein neuer Mitarbeiter bei Contoso und wird Mitglied eines Teams, dessen Mitglieder alle für Teamanrufe konfiguriert sind. Bei der Aktivierung für Microsoft Lync kann der Administrator alle seine neuen Teamkollegen in seine Teamanrufgruppen-Einstellungen aufnehmen. Darüber hinaus fügt der Administrator Mike als Teamanrufgruppen-Mitglied für alle Mitglieder im Team hinzu.

  - Eine Praxis des Kundendiensts in der Personalabteilung bei Contoso ist es, allen Anrufern mit dem ersten Anruf persönlichen Service zu bieten. Wenn alle Mitglieder der Abteilung sehr nah beieinandersitzen, kann das parallele Anrufen aller Telefone durch Teamanrufe sehr störend für das Team sein. Um optimalen Service zu bieten, ohne die Teammitglieder zu stören, kann der Lync-Administrator die Funktion "Gruppenanrufannahme" ausnutzen. Der Administrator fügt alle Abteilungsmitglieder einer Annahmegruppe hinzu und teilt der Abteilung die Annahmegruppennummer mit. Wen nun Samantha nicht an ihrem Platz ist, bemerkt Joe, dass ihr Telefon klingelt, und kann den Anruf von seinem Platz aus annehmen.

## Anforderungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört. Auf diesem Computer muss UCMA 3.0 installiert sein. Um das Tool auszuführen, muss eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID in diesem Pool erstellt werden.

**Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool**

1.  Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem vertrauenswürdigen Anwendungspool gehört. Falls erforderlich, kann ein Pool als neuer vertrauenswürdiger Anwendungspool hinzugefügt werden, indem die Lync Server-Verwaltungsshell mit folgendem Cmdlet verwendet wird:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    

    > [!Note]
    > Auf dem Computer, auf dem das SEFAUtil-Tool ausgeführt werden soll, muss UCMA 3.0 installiert sein.



2.  In der Topologie muss eine vertrauenswürdige Anwendung für das SEFAUtil-Tool definiert sein. Um SEFAUtil als neue vertrauenswürdige Anwendung zu definieren, verwenden Sie die Lync Server-Verwaltungsshell, und führen sie das folgende Cmdlet aus:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    

    > [!Note]
    > Gegebenenfalls kann ein anderer Port verwendet werden.



3.  Die Topologieänderungen müssen aktiviert werden. Sie können die Topologieänderungen mithilfe der Lync Server-Verwaltungsshell aktivieren, indem Sie folgendes Cmdlet ausführen:
    
        Enable-CsToplogy

4.  Installieren Sie nötigenfalls die Tools des Lync Server 2013 Resource Kit auf dem Server, auf dem das SEFAUtil-Tool ausgeführt werden soll (der Server muss zu einem vertrauenswürdigen Anwendungspool gehören).

5.  Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie hierzu das Tool an einer Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. Standardmäßig befindet sich das Tool in: "…\\Programme\\Microsoft Lync Server 2013\\Reskit". Verwenden Sie zum Anzeigen der Anrufweiterleitungseinstellungen eines Benutzers den folgenden Befehl:
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.

## Gruppenanrufannahme

Die Gruppenanrufannahme erfordert eine zusätzliche Konfiguration in Lync Server, damit die Funktion vollständig aktiviert wird. Bevor Sie Benutzern Annahmegruppen zuweisen, lesen Sie in der Produktdokumentation der Gruppenanrufannahme die Schritte zur Planung und Bereitstellung dieser Funktion nach.

## Beispiele

## Anzeigen aktueller Anrufbehandlungseinstellungen

Der folgende Befehl zeigt die Anrufbehandlung für den entsprechenden Benutzer an. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`


> [!Note]
> Dieses Beispiel verwendet den Parameter <STRONG>/server</STRONG>, um den Lync Server anzugeben, mit dem eine Verbindung hergestellt werden soll.



**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

## Festlegen des Ziels für Anrufweiterleitung/Keine Antwort

Dieses Beispiel legt das Ziel für Anrufweiterleitung/Keine Antwort sowie die Anrufverzögerung fest. In diesem Fall wird der Parameter "/server" nicht angegeben. SEFAUtil versucht eine AutoErmittlung von Lync Server.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

## Aktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel aktiviert sofort die Anrufweiterleitung an einen anderen Benutzer.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

## Deaktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel deaktiviert sofort die Anrufweiterleitung.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Hinzufügen eines Benutzers als Stellvertretung und Einrichten des parallelen Anrufens bei Stellvertretung

Dieses Beispiel fügt einen Benutzer als Stellvertretung hinzu und richtet das parallele Anrufen bei Stellvertretung ein.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

## Ändern der Regel für paralleles Anrufen bei Stellvertretung

Dieses Beispiel ändert die Regel für paralleles Anrufen bei Stellvertretung, die im vorherigen Beispiel festgelegt wurde, in die Anrufverzögerungsregel.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

## Entfernen der Stellvertretung

Dieses Beispiel entfernt die Stellvertretung.


> [!Note]
> Wenn die letzte Stellvertretung entfernt wurde, wird das Anrufen von Stellvertretungen automatisch deaktiviert.



    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Hinzufügen einer Stellvertretung und Einrichten der Regel "Anrufweiterleitung an Stellvertretung"

Dieses Beispiel fügt eine Stellvertretung hinzu und richtet die Regel "Anrufweiterleitung an Stellvertretung" ein.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

## Aktivieren des parallelen Anrufens und Festlegen einer Zielnummer

Diese Beispiel aktiviert paralleles Anrufen und legt eine Zielnummer für paralleles Anrufen fest.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring


> [!Note]
> Um die Zielnummer für paralleles Anrufen eines Benutzers zu ändern, für den paralleles Anrufen bereits aktiviert ist, behalten Sie den Befehl mit dem Parameter "/enablesimulring" bei, da die Zielnummer sonst nicht geändert wird.



**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

## Deaktivieren des parallelen Anrufens

Dieses Beispiel deaktiviert paralleles Anrufen.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Hinzufügen eines Teammitglieds für Teamanruf und Einrichten des parallelen Anrufens für die Teamanrufgruppen-Mitglieder

Dieses Beispiel fügt der Teamanrufgruppe eines Benutzers ein Teammitglied hinzu und aktiviert paralleles Anrufen für die Teamanrufgruppe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam


> [!Note]
> Durch das Hinzufügen eines Teammitglieds zur Teamanrufgruppe eines Benutzers werden die Einstellungen der Benutzer für paralleles Anrufen automatisch auf paralleles Anrufen für die Teamanrufgruppe umgestellt.



**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

## Entfernen eines Mitglieds aus der Teamanrufgruppe

Diese Beispiel entfernt ein Teammitglied aus der Teamanrufgruppe eines Benutzers.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com


> [!Note]
> Wenn das Mitglied, das entfernt wird, das einzige Mitglied der Teamanrufgruppe ist, wird gleichzeitig automatisch das gleichzeitige Anrufen für die Teamanrufgruppe deaktiviert.



**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Festlegen der Anrufverzögerung für die Teamanrufgruppe

Dieses Beispiel ändert die Zeiteinstellung der Anrufverzögerung für die Teamanrufgruppe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

## Aktivieren von Teamanruf

Dieses Beispiel aktiviert den Teamanruf für einen angegebenen Benutzer.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam


> [!Note]
> Wenn die Teamanrufgruppe des Benutzers keine Mitglieder hat, wird Teamanruf nicht aktiviert.



**Ausgabe**

## Deaktivieren von Teamanruf

Dieses Beispiel deaktiviert den Teamanruf für einen angegebenen Benutzer.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

## Aktivieren der Gruppenanrufannahme und Zuweisen einer Annahmegruppe zu einem Benutzer

Dieses Beispiel weist einem Benutzer eine Annahmegruppe zu und aktiviert die Gruppenanrufannahme.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

## Deaktivieren der Gruppenanrufannahme

Dieses Beispiel deaktiviert die Gruppenanrufannahme für einen angegebenen Benutzer.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup


> [!Note]
> Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, bleibt die Gruppennummer, die dem Benutzer zugewiesen war, nicht erhalten. Wenn Sie die Gruppenanrufannahme für diesen Benutzer anschließend erneut aktivieren möchten, müssen Sie die Gruppennummer erneut mithilfe des Parameters "/enablegrouppickup" zuweisen.



    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

## SYSPrep.ps1

## Beschreibung

"SYSPrep.ps1" ist ein Windows PowerShell-Skript, das die folgenden erforderlichen Komponenten für Lync Server 2013 auf Ihrem Windows Server 2008-Betriebssystem-Computer installiert.

  - Microsoft .NET Framework 4.5

  - Microsoft SQL Server Express

  - Windows PowerShell, Version 3.0

  - Visual C++ 2010 Redistributable

  - Updates für Internetinformationsdienste

  - Windows Identity Foundation

  - Lync Server 2013-Hauptdateien

Zwar ähnelt der Skriptname dem Systemvorbereitungstool für das Microsoft Windows-Betriebssystem, doch beide sind unterschiedlich. Dieses Skript installiert nur die für Lync Server 2013 erforderlichen Komponenten. Sobald diese installiert sind, kann dann mithilfe des Windows-Tools "SYSPrep" ein Abbild des Servers erstellt werden.

## Anforderungen

Vor dem Ausführen des Skripts "SYSPrep.ps1" müssen Sie die erforderlichen Komponentendateien in eine lokalen Ordner auf dem Windows Server 2008-Betriebssystem-Computer kopieren (beispielsweise **D:\\Setup**). Dieser Ordner muss auch eine Kopie der Lync Server 2013-Dateien enthalten, insbesondere von **Setup.exe**. Die erforderlichen Komponentendateien können an folgenden Orten heruntergeladen werden:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Erforderliche Komponente</th>
<th>Ort</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .NET Framework 4.5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>http://www.microsoft.com/de-de/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell, Version 3.0</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 Redistributable</p></td>
<td><p>http://www.microsoft.com/de-de/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Updates für Internetinformationsdienste</p></td>
<td><p>http://www.microsoft.com/de-de/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/de-de/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup.exe</p></td>
<td><p>Von den Lync Server 2013-Medien kopieren</p></td>
</tr>
</tbody>
</table>


## Parameter

Der Parameter **–SetupFolder** nimmt als Argument den Verzeichnisspeicherort der erforderlichen Komponentendateien.

## Beispiele

Um das Skript "SYSPrep.ps1" auszuführen und die erforderlichen Komponenten für Lync Server 2013 zu installieren, führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus:

    ./SysPrep.PS1 -SetupFolder D:\Setup

## Migration von Ankündigungen für nicht zugewiesene Nummern

Das Tool für die Migration von Ankündigungen für nicht zugewiesene Nummern ermöglicht einem Lync-Administrator das Verschieben der Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quell-Lync Server oder -Pool zu einem Ziel-Lync Server oder -Pool.

## Beschreibung

Das Tool für die Migration von Ankündigungen für nicht zugewiesene Nummern ist ein Windows PowerShell-Skript, das die Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quellserver oder -pool zu einem anderen Server oder Pool verschiebt.

Bei Ausführung des Skripts für die Migration von Ankündigungen für nicht zugewiesene Nummern werden folgende Vorgänge durchgeführt:

1.  Verschieben aller Audiodateien, die von den Ankündigungen für nicht zugewiesene Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver oder -pool gehostet wird, in den Dateispeicher auf dem Zielserver oder -pool.
    

    > [!Note]
    > Die Audiodateien werden nach Abschluss des Kopiervorgangs in den Zielpool aus dem Quellpool entfernt.



2.  Verschieben aller Ankündigungen für nicht zugewiesene Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver oder -pool gehostet wird, in den Zielserver oder -pool.

3.  Erneutes Zuweisen aller nicht zugewiesene Nummernbereiche, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool gehostet wird, zum Zielserver oder -pool.

Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver oder -pool gehostet wird, nun mit derselben Konfiguration vom Zielserver oder -pool bedient.

## Ausgabe

Das Skript **Move-CsAnnouncementConfiguration** zeigt im Lync-Verwaltungsshellfenster seinen Ausführungsort sowie den Erfolg oder das Fehlschlagen des Migrationsvorgangs an.

Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die erfolgreich zum Ziel verschobenen nicht zugewiesenen Nummernbereiche am Ziel in funktionsfähiger Form, während der Rest der noch zu migrierenden nicht zugewiesenen Nummernbereiche in der Quelle verbleibt – ebenfalls in funktionsfähigem Zustand. Um die restliche Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.

## Verwendungszweck

Das Skript für die Migration von Ankündigungen für nicht zugewiesene Nummern kann in folgenden drei Szenarios eingesetzt werden:

  - **Migration von Konfigurationseinstellungen zu einer neuen Version von Lync Server:** Contoso ist dabei, zu Lync Server 2013 zu migrieren, und im Rahmen des Migrationsprozesses möchte der Lync Server-Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungsanwendung bedient wird, von der Lync Server 2010-Bereitstellung in die neue Lync Server 2013-Bereitstellung verschieben. Um die Konfigurationseinstellungen zu verschieben, verwendet der Lync Server-Administrator das Tool für die Migration von Ankündigungen für nicht zugewiesene Nummern.

  - **Rollback einer Bereitstellung von Lync Server 2013 zu Lync Server 2010:** Aufgrund unerwarteter Faktoren muss Contoso ein Rollback der Migration zur neuen Lync Server 2013-Bereitstellung durchführen. Um Dienstunterbrechungen zu minimieren, verwendet der Lync Server-Administrator das Tool für die Migration von Ankündigungen für nicht zugewiesene Nummern, um das Rollback der Konfiguration von der Lync Server 2013-Bereitstellung zur Lync Server 2010-Bereitstellung durchzuführen.

  - **Verschieben von Daten zwischen Lync-Bereitstellungen:** Contoso ist dabei, alle Server eines Pools durch neue Server zu ersetzen. Die zugrunde liegende Strategie hierbei ist es, einen neuen Lync Server 2013-Pool bereitzustellen, alle Daten aus dem alten in den neuen Pool zu verschieben und dann den alten Pool außer Dienst zu nehmen. Sobald der neue Pool bereitgestellt ist, wird die Konfiguration mithilfe des Tools für die Migration von Ankündigungen für nicht zugewiesene Nummern aus dem alten Pool in den neuen Pool verschoben.

## Anforderungen

Im Folgenden finden Sie die Hauptanforderungen für eine erfolgreiche Ausführung des Tools:

1.  Das Skript muss auf einem Computer ausgeführt werden, auf dem Verwaltungsshell für Lync Server 2013 installiert ist.

2.  Die Ankündigungsanwendung muss in den Lync-Quell- und Zielservern bzw. -pools erfolgreich bereitgestellt sein.

## "Move-CsAnnouncementConfiguration"-Skript

Das Skript "Move-CsAnnouncementConfiguration" erfordert die in der Tabelle unten beschriebenen zwei Parameter.

![Move-CsAnnouncementConfiguration-Parameter](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration-Parameter")

## Beispiele

## Verschieben der Konfiguration für Ankündigungen für nicht zugewiesene Nummern von einem Lync Server 2010-Pool zu einem Lync Server 2013-Pool

Dieses Beispiel verschiebt die Ankündigungen für nicht zugewiesene Nummern vom Quellpool (Lync Server 2010) zum Zielpool (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

## Verschieben der Konfiguration für Ankündigungen für nicht zugewiesene Nummern von einem Lync Server 2013-Pool zu einem Lync Server 2010-Pool

Dieses Beispiel verschiebt die Ankündigungen für nicht zugewiesene Nummern vom Quellpool (Lync Server 2013) zum Zielpool (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

## Webkonferenzdaten

Das Webkonferenzdaten-Tool ermöglicht einem Administrator von Lync Server 2013-Kommunikationssoftware eine stärkere Kontrolle über die Daten, die den Webkonferenzen eines Organisators zugeordnet sind. Die Szenarios umfassen unter anderem die Möglichkeit zum Löschen der Besprechungsdaten eines bestimmten Benutzers auf Grundlage eines Zeitstempelkriteriums.

## Beschreibung

Dieses Tool ermöglicht dem Administrator die Durchführung der folgenden Vorgänge:

1.  Auffinden aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

2.  Löschen aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind.

3.  Löschen aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet und älter als ein bestimmtes Kriterium sind.

4.  Verschieben aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer aus einem Pool in einen anderen Pool verschoben wird.


> [!Note]
> Von den Resource Kit-Tools für Lync Server 2010 wurde das Verschieben aller Webkonferenzdaten, die einem einzelnen Benutzer zugeordnet sind, unterstützt, wenn dieser aus einem Pool in einen anderen verschoben wurde. Diese Funktionalität wird von diesem Tool nun nicht mehr unterstützt. Stattdessen wird der Parameter <STRONG>MoveConferenceData</STRONG> bevorzugt. Details zu diesem Parameter finden Sie in der Beschreibung des Cmdlets <A href="https://technet.microsoft.com/de-de/library/gg398528(v=ocs.15)">Move-CsUser</A>.



Das Tool löscht Besprechungsdaten nur für Besprechungen, die inaktiv sind. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.

Dieses Tool muss auf einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool gehostet werden.

## Ausgabe

Dieses Tool gibt die Ergebnisse von jedem Vorgang aus:

  - Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, deren Organisator dieser Benutzer ist.

  - Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.

## Anforderungen

Das Tool muss im selben Pool ausgeführt werden, in dem der Organisator zurzeit gehostet wird.

Das Tool muss mit Administratorrechten und mit Zugriff auf den Inhaltsdateispeicher ausgeführt werden.

## Beispiele

In der folgenden Tabelle sind die Parameter beschrieben, von denen manche in den Beispielen verwendet werden.

![Parameter für das Webkonferenzdaten-Tool](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parameter für das Webkonferenzdaten-Tool")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

Die vorherigen Beispiele zeigen, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

Voranstehend sehen Sie ein Beispiel für einen Löschbefehl. Der Löschbefehl entfernt alle inaktiven Besprechungsordner dieses Benutzers.

## Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenzbesprechungsdaten benötigen.
