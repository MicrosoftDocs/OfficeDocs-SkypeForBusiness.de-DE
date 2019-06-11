---
title: Dokumentation zur lync Server 2013 Resource Kit-Tools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1589285948bd9d3f82fae0ed7c7916029716514f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Dokumentation zur lync Server 2013 Resource Kit-Tools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-09_

In diesem Thema werden die Tools beschrieben, die Teil des lync Server 2013 Resource Kits sind, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Die lync Server 2013, Resource Kit-Tools helfen Ihnen, Routineaufgaben einfacher für IT-Administratoren zu machen, die lync Server 2013 bereitstellen und verwalten. Beispielsweise kann das Tool **Web Conf Data** verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden. Mithilfe des **SEFAUtil**-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um lync Server 2013 effektiver zu verwalten.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installation der Resource Kit-Tools

Zum Installieren der lync Server 2013, Resource Kit-Tools, laden Sie **OCSReskit. msi**herunter. Sie können das Resource Kit Tools-Installationsprogramm aus dem Download Center [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)unter herunterladen.

Führen Sie **OCSResKit.msi ** aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Tools im folgenden Pfad: **% Program Files%\\Microsoft lync Server 2013\\**-reskit. Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner. Tools, die auch Dateien enthalten, befinden sich in ihren eigenen Unterordnern.

</div>

<div>

## <a name="supported-environments"></a>Unterstützte Umgebungen

Um eine optimale Leistung zu erzielen, sollten die lync Server 2013, Resource Kit-Tools in der gleichen Umgebung und mit den gleichen Spezifikationen installiert werden, die für lync Server 2013 erforderlich sind.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Resource Kit-Tools – Übersicht

In der folgenden Liste werden die Tools beschrieben, die im lync Server 2013 Resource Kit bereitgestellt werden. Eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispiel Verwendung, wird im folgenden Abschnitt erläutert.

  - ABSConfig

  - Bandwidth Policy Service Monitor

  - Bandwidth Utilization Analyzer

  - Call Parkometer

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Network Configuration Viewer

  - Response Group Agent Live

  - SEFAUtil

  - SYSPrep.ps1

  - Unassigned Number Announcements Migration

  - Web Conf Data

</div>

<div>

## <a name="absconfig"></a>ABSConfig

Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in lync Server 2013 anpassen können. Mit diesem Tool können lync Server 2013-Administratoren auch die Standardeinstellungen für den Adressbuchdienst wiederherstellen.

<div>

## <a name="description"></a>Beschreibung

ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory-Domänendienst Attribute konfigurieren können, die mit dem Adressbuchdienst verknüpft sind.

Dies sind die primären Verwendungsszenarien für das Tool:

  - So können Administratoren Attribute in den Active Directory-Domänendiensten den Attributen für lync Server 2013 zuordnen.

  - Administratoren das Angeben des Attributs in Active Directory Domain Services ermöglichen, das in die Adressbuchdienst-Dateien aufgenommen oder aus diesen ausgeschlossen werden soll

  - Administratoren das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts ermöglichen

Das ABSConfig-Tool kann mithilfe der Datei "ABSConfig. exe" gestartet werden. Das Tool wird auf der Registerkarte **Attribute konfigurieren** geöffnet. Diese Tabelle enthält Optionen zum Zuordnen von Active Directory-Domänendienst Attributen zu den Attributfeldern für lync Server 2013 und zum Angeben der Benutzer, die in Adressbuchdienst Dateien basierend auf bestimmten Attribut Filtern enthalten oder ausgeschlossen werden sollen. Darüber hinaus gibt es Optionen, um den Wert der Telefonnummer anzupassen, der in die Adressbuchdatei aufgenommen werden soll. Mit der Option **Standard wiederherstellen** können Administratoren die Einstellungen des Adressbuchdiensts auf Standardwerte zurücksetzen.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Änderungen von lync Server 2010

Im lync Server 2013 ABS-Konfigurationstool können Attribute (Zeilen) entfernt werden, indem Sie das Kontrollkästchen "aktivieren" für das Attribut deaktivieren. Dies hat dieselbe Wirkung wie das Löschen der Zeile in lync Server 2010.

<div>


> [!NOTE]  
> Das Kontrollkästchen "aktivieren" befindet sich in der äußerst rechten Spalte. Möglicherweise müssen Sie nach rechts scrollen, um die Spalte anzuzeigen.



</div>

</div>

<div>

## <a name="output"></a>Ausgabe

ABSConfig speichert die Konfiguration des Adressbuchdiensts in der Datenbank.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen des lync Server 2013-Adressbuchdiensts.

</div>

<div>

## <a name="requirements"></a>Anforderungen

<div>

## <a name="computer"></a>Computer

ABSConfig kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem lync Server 2013 installiert ist. Im Fall von lync Server 2013, Enterprise Edition, kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.

</div>

<div>

## <a name="network"></a>Netzwerk

Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.

</div>

<div>

## <a name="software"></a>Software

Die folgenden Softwarekomponenten müssen vor der Ausführung des ABSConfig-Tools installiert werden:

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>Nutzer

Administratoren, die über die erforderlichen Berechtigungen verfügen, um die lync Server 2013-Bereitstellung zu aktualisieren.

</div>

</div>

<div>

## <a name="examples"></a>Beispiele

ABSConfig kann durch Eingeben von **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie eine Abbildung der Benutzeroberfläche des ABSConfig-Tools.

![Das Tool "ABSConfig. exe".] (images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Das Tool \"ABSConfig. exe\".")

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Das ABSConfig-Tool bietet Administratoren ein schnelles und einfach zu Bedientool zum Anpassen des lync Server 2013-Adressbuchdiensts.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Bandwidth Policy Service Monitor

Mit dem Tool Bandwidth Policy Service Monitor können Administratoren eine Liste der folgenden Elemente anzeigen:

1.  Alle konfigurierten lync Server 2013-Bandbreitenrichtlinien Dienste (Authentifizierung und Kern) in der Topologie

2.  Die Verbindungen, die jeder Dienst mit anderen Bandbreiten-Richtliniendiensten und Edgeservern herstellt

3.  Alle Verbindungen, die im Netzwerkkonfigurationsdokument konfiguriert sind, und die von den einzelnen Bandbreiten-Richtliniendiensten gemeldete Echtzeit-Bandbreitennutzung

<div>

## <a name="description"></a>Beschreibung

Das Tool Bandwidth Policy Service Monitor ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Administratoren starten das Tool durch Ausführen der Datei „PDPMonUI.exe“.

Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreiten-Richtliniendienste in der Topologie zu ermitteln. Nach Abschluss der anfänglichen Aktualisierung wird der linke Bereich im Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.

Wenn Administratoren einen bestimmten Bandbreiten-Richtliniendienst auswählen, werden im rechten Bereich die Informationen zu dem jeweiligen Dienst angezeigt. Dieser Bereich enthält außerdem zwei Hauptregisterkarten, auf denen Informationen angezeigt werden.

<div>

## <a name="machine-info-tab"></a>Registerkarte „Machine Info“

Auf der Registerkarte **Machine Info** werden die Details des ausgewählten Bandbreiten-Richtliniendiensts angezeigt sowie die Liste und die Zustände aller Verbindungen, die der ausgewählte Bandbreiten-Richtliniendienst mit anderen Diensten herstellt.

</div>

<div>

## <a name="topology-info-tab"></a>Registerkarte „Topology Info“

Auf der Registerkarte **Topology Info** wird eine Liste aller Verbindungen angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jede Verbindung wird die Bandbreitenkapazität für Audio und Video angezeigt. Zusätzlich wird die zurzeit verwendete Bandbreite in KB/s und als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierungen zum Hervorheben von Verbindungen, deren Nutzung fast der Kapazität entspricht. So können Administratoren solche Verbindungen schnell erkennen.

<div>


> [!NOTE]  
>  Wenn es beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreiten-Richtliniendienste zu einem Fehler im Tool Bandwidth Policy Service Monitor kommt, werden die Informationen auf den Registerkarten <STRONG>Machine Info</STRONG> und <STRONG>Topology Info</STRONG> nicht aufgefüllt. Es ist aber möglich, dass das Tool anfangs eine Verbindung mit dem Dienst herstellt, die dann später verloren geht. In solchen Fällen werden Administratoren eventuell veraltete Informationen angezeigt. Beide Registerkarten enthalten einen Zeitstempel <STRONG>Last Updated</STRONG>, mit dessen Hilfe Administratoren bestimmen können, wann die Daten für einen bestimmten Bandbreiten-Richtliniendienst zum letzten Mal aktualisiert wurden.



</div>

</div>

</div>

<div>

## <a name="output"></a>Ausgabe

Es gibt keine Befehlszeilenausgabe. Die Programmausgabe erfolgt auf der grafischen Hauptbenutzeroberfläche.

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Das Tool Bandwidth Policy Service Monitor soll Administratoren Einblick in den Zustand jedes Bandbreiten-Richtliniendiensts zu verschaffen, der in der Topologie definiert ist. Zusätzlich können Administratoren die Echtzeit-Bandbreitennutzung für alle Verbindungen anzeigen, die im Netzwerkkonfigurationsdokument definiert sind.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Das Tool für bandbreitenrichtliniendienst Monitor muss auf einem Computer ausgeführt werden, der Teil der lync Server-Topologie ist.

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Das Tool Bandwidth Policy Service Monitor kann eine wertvolle Ressource für Administratoren sein, um den Zustand aller Bandbreiten-Richtliniendienste in der Topologie untersuchen zu können. Wichtiger noch ist, dass die Echtzeit-Bandbreitenauslastung für die Verbindungen ermittelt werden kann, die in den Netzwerkkonfigurationseinstellungen definiert sind.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Bandwidth Utilization Analyzer

Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten des Bandbreitenverbrauchs durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Mithilfe dieser Berichte kann das aktuelle Muster des Bandbreitenverbrauchs analysiert werden, um die Planung der Bandbreitenkapazität zu unterstützen.

<div>

## <a name="description"></a>Beschreibung

Bandwidth Utilization Analyzer ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Dieses Tool erzeugt Berichte speziell für die Audionutzung über das Netzwerk und hilft bei der Kapazitätsplanung. Das Tool durchläuft außerdem die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.

</div>

<div>

## <a name="output"></a>Ausgabe

Bandwidth Utilization Analyzer bietet grafische Diagramme der Bandbreitenkapazität und -auslastung durch Audio für alle WAN-Verbindungen, die im System konfiguriert sind.

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Bei allen VoIP- und Videobereitstellungen ist es von entscheidender Bedeutung, Trends der Bandbreitenauslastung durch Mediendatenverkehr im Unternehmensnetzwerk zu überwachen und zu verstehen. Genau dies ermöglicht das Tool Bandwidth Utilization Analyzer Administratoren. Das Tool bietet folgende Funktionen:

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

<div>

## <a name="applications"></a>Anwendungen

Bandwidth Utilization Analyzer besteht aus den zwei folgenden Anwendungen (Tools):

  - **WanLinkLogCollector. exe**   mit diesem Tool kann der Benutzer die erforderlichen Informationen eingeben.

  - **BandwidthUtilizationAnalyzer. xlsm**  ein Microsoft Excel-Kalkulationstabellen-softwarebericht wird automatisch von WanLinkLogCollector. exe gestartet. Mit dieser Anwendung können Benutzer, wie später in diesem Artikel gezeigt, Filter auf den Bericht anwenden.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Phasen der Verwendung von Bandwidth Utilization Analyzer

Es gibt zwei Phasen bei der Verwendung von Bandwidth Utilization Analyzer:

  - Erfassen von Protokollen mithilfe von „WanLinkLogCollector.exe“

  - Anpassen von Berichten mithilfe von „BandwidthUtilizationAnalyzer.xlsm“

<div>


> [!IMPORTANT]  
> „BandwidthUtilizationAnalyzer.xlsm“ sollte auf keinen Fall manuell von Endbenutzern gestartet werden.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Starten von Bandwidth Utilization Analyzer

Starten Sie „WanLinkLogCollector.exe“ an der Eingabeaufforderung oder mithilfe von Windows-Explorer.

**Verwenden von „WanLinkLogCollector.exe“**

„WanLinkLogCollector.exe“ wird in drei Schritten verwendet:

1.  **Protokollieren der Zeitachse**   geben Sie die Zeitachse an, für die der Bericht generiert werden muss.

2.  **Angeben der Dateiverzeichnisse**   zur Bereitstellung von Dateispeicherort Informationen

3.  **Sammeln der Protokolle und Starten der Berichtsanzeige**  führen Sie den Befehl aus, um den Bericht zu generieren.

<div>

## <a name="step-1---log-the-timeline"></a>Schritt 1 – Protokollieren des Zeitraums

Durch die Protokollierung des Zeitraums können die Benutzer des Tools, wie in der Abbildung unten dargestellt, Folgendes angeben. 

1.  **Startdatum** Dies ist das Startdatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 1. August 2010.

2.  **Enddatum** Dies ist das Enddatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 30. September 2010.
    
    ![Anfangs-und Endtermine in der Bandbreitennutzung A] (images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Anfangs-und Endtermine in der Bandbreitennutzung A")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>Schritt 2 – Angeben der Dateiverzeichnisse

Die folgenden Dateiverzeichnisse können von den Benutzern wie gezeigt angegeben werden.

  - **Speicherort für Server Protokolldateien** Der Speicherort des Ordners, in dem die Bandbreitenrichtlinien Serverprotokolle gespeichert werden. Dies ist normal \<erweise in\>\\\<der Fileserver\>\\-\\Auswahl von FE AppServerFiles PDP.

  - **Speicherort für temporären Dateispeicher** Der Speicherort der temporären Datei, in dem zwischen Dateien gespeichert werden, während der Bericht generiert wird.

![Dateiverzeichnisse in der Bandbreitennutzung Anal] (images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Dateiverzeichnisse in der Bandbreitennutzung Anal")

<div>


> [!NOTE]  
> Stellen Sie sicher, dass den Benutzern des Tools ausreichender Dateizugriff auf den Speicherort der Serverprotokolle und der temporären Dateien gewährt wird.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Schritt 3 – Erfassen der Protokolle und Starten der Berichtanzeige

Um die Protokolle zu erfassen und die Berichtanzeige zu starten, klicken Sie, wie unten gezeigt, auf **Execute**. In diesem Schritt werden die erforderlichen Daten erfasst.

![Sammeln von Daten in der Bandbreitennutzung Analy] (images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Sammeln von Daten in der Bandbreitennutzung Analy")

Nach erfolgreicher Überprüfung der Eingabe wird die unten wiedergegebene Meldung angezeigt.

![Protokolliert die gesammelte Benachrichtigung in der Bandbreiten] -utili (images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Protokolliert die gesammelte Benachrichtigung in der Bandbreiten") -utili

Klicken Sie auf **OK**. „BandwidthUtilizationAnalyzer.xlsm“ wird automatisch gestartet. Befolgen Sie die im Meldungsfeld angezeigten Anweisungen. Ausführliche Informationen finden Sie im nächsten Abschnitt unter **Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**.

</div>

<div>


**Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**

1.  Wenn „BandwidthUtilizationAnalyzer.xlsm“ automatisch gestartet wurde, klicken Sie wie unten gezeigt auf **Refresh**.
    
    ![BandwidthUtilizationAnalyzer. xlsm] (images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer. xlsm")

2.  Wenn ein Dateiordner geöffnet wird, wählen Sie die Datei „consolidated.csv“ an dem Speicherort aus, der in dem unten gezeigten Meldungsfeld angegeben ist. Außerdem wird die Position als **C:\\Temp**angezeigt.
    
    ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer] (images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Öffnen eines Ordners in BandwidthUtilizationAnalyzer")

3.  Klicken Sie auf **Import**.

4.  Das grafische Diagramm wird automatisch generiert. Es ist verfügbar, sobald der Hintergrundaktivitäts-Mauszeiger nicht mehr angezeigt wird.
    
    ![Anwenden von Filtern in der Berichtsansicht] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>Anwenden von Filtern auf die Berichtsansicht

Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden nachfolgend beschrieben:

![Anwenden von Filtern in der Berichtsansicht] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht")

1.  **Name** Filtern nach WAN-Verbindungen (der Filter befindet sich rechts von der Grafik). Das Präfix identifiziert die folgenden Verbindungstypen, siehe im vertikalen (blauen) Feld:
    
      - **S Site** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion
    
      - **IS Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten
    
      - **R Inter-Region** Die WAN-Verbindung zwischen zwei Netzwerkregionen

2.  **Exceeded limit** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung die Bandbreitenkapazität übersteigt

3.  **Critical levels** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mindestens 90 % der Bandbreitenkapazität erreicht hat

4.  **Under-utilized** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25 % der Bandbreitenkapazität beträgt

5.  **Link type** Filtern nach den folgenden WAN-Verbindungstypen:
    
      - 
            Typ **Network site**
    
      - 
            Typ **Inter-site**
    
      - 
            Typ **Inter-Region link**

6.  **Region** Filtern nach Netzwerkregion

Die folgenden Abbildungen zeigen die oben beschriebenen Filter.

Filtern nach **Name**. Wählen Sie die Liste der Verbindungen aus, die in dem Diagramm angezeigt werden sollen.

![Filtern nach Name in BandwidthUtilizationAnalyzer] (images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtern nach Name in BandwidthUtilizationAnalyzer")

Filtern nach **Exceeded limit**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filterung nach Überschreitung des Grenzwerts.] (images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filterung nach Überschreitung des Grenzwerts.")

Filtern nach **Critical levels**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach kritischen Ebenen.] (images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtern nach kritischen Ebenen.")

Filtern nach **Under utilized**. Wählen Sie **True** aus, um den Filter zu erzwingen.

![Filtern nach unter verwendet.] (images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtern nach unter verwendet.")

Filtern nach **Link Type**. Wählen Sie die Typen aus, die angezeigt werden sollen.

![Filtern nach Verknüpfungstyp.] (images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtern nach Verknüpfungstyp.")

Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Verbindungen angezeigt werden sollen.

![Filtern nach Region.] (images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtern nach Region.")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Anforderungen

  - .NET Framework 3.5

  - Microsoft Excel 2010 oder Excel 2007

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Bandwidth Utilization Analyzer wird verwendet, um die Bandbreitenauslastung durch Audio für UC-Datenverkehr über das Netzwerk grafisch darzustellen. Mithilfe dieses Tools kann auch die Bandbreitenauslastung durch Video im Netzwerk dargestellt werden.

</div>

</div>

<div>

## <a name="call-parkometer"></a>Call Parkometer

Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Datenbank mit den Orbits der geparkten Anrufe ermöglicht.

<div>

## <a name="description"></a>Beschreibung

Call Parkometer ist ein Tool zum Nachverfolgen der zurzeit geparkten Anrufe. Es erfasst außerdem Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS). Dieses Befehlszeilentool bietet Lese-und Schreibzugriff auf die CPS-Orbit-SQL Server-Datenbank von einem lokalen oder Remote verbundenen Computer.

Alle Optionen schließen sich gegenseitig aus. Befehlszeilensyntax:

  - **–o** (Parameter) – Listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.

  - **–n** (Parameter) – Listet alle zurzeit in diesem Pool verwendeten Orbits auf. Folgende Informationen werden angezeigt:
    
      - Der SIP-URI (Session Initiation Protocol Uniform Resource Identifier) der geparkten und der parkenden Person
    
      - Der Hostname des Anrufparkservers, auf dem der Anruf geparkt ist
    
      - Der Zeitstempel, aus dem hervorgeht, wann der Anruf geparkt wurde

  - **–f** (Parameter) – Listet die Anzahl der zurzeit freien Orbits im Pool auf.

  - **– r \<n\> ** -Parameter – listet \<die\> n letzten geparkten Anrufe auf. Folgende Informationen werden angezeigt:
    
      - SIP-URI der geparkten Person
    
      - SIP-URI der parkenden Person
    
      - Der Hostname des Anrufparkservers, auf dem der Anruf geparkt wurde
    
      - Der Zeitstempel, aus dem hervorgeht, wann der Anruf herangeholt oder abgebrochen wurde

  - **-t\<n\> ** Parameter – testet, wie eine Umlaufbahn in der Datenbank reserviert wird, um die Zufälligkeit der zugewiesenen Orbit-Nummern anzuzeigen.

</div>

<div>

## <a name="output"></a>Ausgabe

Abhängig von den Eingabeparametern, die an der Eingabeaufforderung angegeben werden, zeigt Call Parkometer folgende Ausgaben an:

  - Alle für diesen Pool konfigurierten Orbitbereiche

  - Zurzeit geparkte Anrufe

  - Anzahl der freien (verfügbaren) Orbits

  - Zuletzt geparkte Anrufe

  - Für das Testen einheitlicher und zufälliger Orbitwerte reservierte Orbits

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Das Anrufparkserver-Tool soll Befehlszeilenzugriff auf die Anrufparkserver-Datenbank ermöglichen. Administratoren können die Anrufparkserver-Nutzung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Wenn das Tool auf dem gleichen Computer wie der Anrufparkserver ausgeführt wird, gelten keine Anforderungen. Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von lync Server 2013 verwendete SQL Server-Datenbank so konfiguriert sein, dass der Remotezugriff zulässig ist. Anruf Parkometer muss mit einer SQL Server-Datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem SQL Server des Pools herzustellen. Diese SQL Server-Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer. exe. config**definiert. Sie muss sich im gleichen Verzeichnis befinden, in dem sich parkometer. exe befindet. Die folgende XML-Datei ist ein Beispiel für eine parkometer. exe. config. Bei den zu konfigurierbaren Parametern handelt es sich um den Benutzernamen\\(beispielsweise mydomain Administrator), ein Kennwort (beispielsweise mypassword) und einen Hostnamen (beispielsweise MyServer).

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

</div>

<div>

## <a name="examples"></a>Beispiele

Bereitgestellte Orbitbereiche: Der Parameter „–o“ listet wie gezeigt alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.

![Umlaufbahn Bereiche in der Anruf Parkometer.] (images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Umlaufbahn Bereiche in der Anruf Parkometer.")

Zurzeit geparkte Anrufe: Der Parameter „–n“ listet wie gezeigt alle zurzeit verwendeten Orbits in diesem Pool auf.

![Zurzeit geparkte Anrufe in Anruf Parkometer.] (images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Zurzeit geparkte Anrufe in Anruf Parkometer.")

Anzahl freier Orbits: Der Parameter „–f“ listet wie gezeigt die Anzahl der zurzeit freien Orbits im Pool auf.

![Freie Umlaufbahnen in Anruf Parkometer.] (images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Freie Umlaufbahnen in Anruf Parkometer.")

Zuletzt geparkte Anrufe: der Parameter \<–\> r n listet \<die\> n letzten geparkten Anrufe auf, wie hier gezeigt.

![Vor kurzem geparkte Anrufe in Anruf Parkometer.] (images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Vor kurzem geparkte Anrufe in Anruf Parkometer.")

Test Orbit-Reservierung: der – \<t\> n-Parameter testet, wie eine Umlaufbahn in der Datenbank reserviert wird (siehe Abbildung)

![Testen Sie Orbit-Reservierungen in Anruf Parkometer.] (images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testen Sie Orbit-Reservierungen in Anruf Parkometer.")

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

Das CleanupStorageServiceData Resource Kit-Tool ermöglicht das Löschen von verwaisten Daten aus der Datenbank, die vom lync Server-Speicherdienst (LYSS) verwendet wird. Eine Funktion des Speicher Diensts besteht darin, die Kommunikation zwischen lync Server und verschiedenen Endpunkten des Back-End-Datenspeichers zu puffern, wie SQL Server und Exchange.

<div>

## <a name="description"></a>Beschreibung

Um eine hohe Verfügbarkeit zu unterstützen, akzeptiert und speichert LYSS Kopien der Daten auf mehreren Front-End-Servern im Pool temporär und entfernt diese Daten, sobald Sie an den endgültigen langfristigen Speicherplatz übermittelt wurden. Es gibt ungewöhnliche Situationen, die bei einem ansonsten normalen Betrieb auftreten können, wenn ein Server abstürzt oder ein Verarbeitungsproblem auftritt und einige Daten möglicherweise nicht ordnungsgemäß bereinigt werden. Diese Daten sind harmlos, aber es werden nur begrenzte Verarbeitungsressourcen beansprucht. Ein Großteil der normalen erforderlichen Datenwartung ist automatisiert, aber dieses Tool ermöglicht die sichere Identifikation und Entfernung solcher verwaister Daten, wenn eine automatisierte Entfernung nicht möglich ist. Die Verwendung dieses Tools wird angezeigt, wenn eine Integritäts Überwachungs System Center Operations Manager (SCOM)-Warnung ausgelöst wird, die den Administrator auffordert, die nicht benötigten Daten aus den lokalen LYSS-Datenbanken im Pool zu entfernen. Im Ereignisprotokoll auf dem Front-End, das die Benachrichtigung ausgelöst hat, wird ein entsprechendes Ereignis angezeigt. Die Ereignisdetails enthalten Informationen über die Anzahl der verwaisten Daten, die auf dem Front-End enthalten sind, und werden ausgelöst, wenn diese Daten bestimmte vordefinierte Schwellenwerte überschreiten.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Installieren Sie die lync Server 2013, Resource Kit-Tools. Das Tool wird auf Domänen verbundenen Computern ausgeführt, auf denen lync Server und lync Server 2013-Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist. Diese Datenbank wird vom CleanupStorageServiceData-Tool verwendet, um die Verbindungsdetails abzurufen, die für die Kommunikation mit dem lync Server-Routing Dienst erforderlich sind. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über die Berechtigung "Lesen/Schreiben" für die Dateifreigabe verfügen, auf die Sie möchten das Ausgabeprotokoll schreiben. Dieses Tool hängt auch davon ab, dass sich der Pool in einem stabilen Zustand befindet. Im Wesentlichen bedeutet dies, dass jeder Front-End-Server ausgeführt werden soll, dass die SQL Server LYNCLOCAL-Instanz und die LYSS-Datenbank eine Verbindung herstellen können, und jede Routinggruppe einen vollständigen Satz von 1 primären Front-End-Servern und 2 sekundären Front-End-Servern aufweisen muss. Server aufgelistet.

</div>

<div>

## <a name="examples"></a>Beispiele

C:\\Programmdateien\\Microsoft lync Server 2013\\reskit\\StorageService\> ImportStorageServiceData. exe

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

</div>

</div>

<div>

## <a name="dbanalyze"></a>DBAnalyze

<div>

## <a name="description"></a>Beschreibung

Dbanalyze ist ein Befehlszeilentool, das Administratoren hilft, Analyseberichte zu den lync Server 2013-Datenbanken zu sammeln. DBAnalyze verfügt über folgende Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:

  - **Im Diagnosemodus**   wird ein Bericht erstellt, der Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten-und Protokolldateigrößen, die letzte Sicherungszeit, die Kontaktverteilung zwischen Servern, auf denen Microsoft ausgeführt wird, enthält. Office Communications Server, die durchschnittliche Anzahl von Berechtigungen, Kontakten, Containern, Abonnements, Publikationen, Endpunkten pro Benutzer, nicht ordnungsgemäß vernetzte Benutzer, Benutzer, die nicht weitergeleitet werden können, die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, geplant Konferenzen, aktive Konferenzen und die Datenbankversion.
    
    <div>
    

    > [!NOTE]  
    > Die Ausführung im Diagnosemodus kann die Serverleistung beeinträchtigen.

    
    </div>

  - **Benutzerdaten Modus**  Meldet Kontakt-, Container-, Abonnement-, Veröffentlichungs-, Genehmigungs-und Kontaktgruppen Daten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in seinen Kontakt-und Berechtigungslisten haben. Dieser Modus berichtet außerdem Zusammenfassungsdaten für Konferenzen, die von einem Benutzer organisiert werden oder zu denen er eingeladen ist.

  - **Im Konferenzmodus**   werden detaillierte Daten für eine bestimmte Konferenz gemeldet, einschließlich aller Details zur Terminplanung für die Konferenz, der Liste der eingeladenen Personen, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCU (Multipoint Control Units), der aktiven Teilnehmerliste und den Signalisierungs Status jedes Teilnehmers.

  - **Decodieren der Besprechungs-ID**  dekodiert eine vom **/pstnid** -Schalter angegebene PSTN-Besprechungs-ID (Public Switched Telephone Network), die jedoch nicht mit dem Back-End verbunden ist, um detaillierte Informationen zu erhalten.

  - **Konferenz auflösen**   decodiert eine PSTN-Besprechungs-ID, die vom **/pstnid** -Schalter angegeben wird, und zeigt Informationen zu der Konferenz an, die von der ID angegeben wird.

  - **Im MCU-Modus**  werden die ID, der Medientyp, die URL, der Heartbeat-Status, die Konferenz Auslastung und die Teilnehmer Auslastung für jede MCU im Pool gemeldet.

  - **Der Datenträger Fragmentierungs Modus**  zeigt den Fragmentierungs Status aller Datenträger an.

Dieses Tool kann zum Diagnostizieren verschiedener Probleme verwendet werden oder Administratoren bei der Kapazitätsplanung unterstützen. Wenn beispielsweise die meisten der auf Server A verwalteten Benutzer auf Server B verwaltete Benutzer als Kontakte wählen, kann der Administrator die Benutzer von Server A auf Server B verschieben, um den Datenverkehr zwischen den Servern zu verringern.

</div>

<div>

## <a name="output"></a>Ausgabe

Dieses Tool gibt vordefinierte Berichte zur lync Server 2013-Datenbank aus. **Pfad:** % Programme%\\Microsoft lync Server 2013\\-reskit

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Wenn Sie Dbanalyze. exe installieren möchten, kopieren Sie Sie in einen lokalen Ordner, und führen Sie dann das Tool aus. Führen Sie den folgenden Befehl in der Befehlszeile aus, um das Tool zu verwenden.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Die Beschreibungen für die Befehlszeilenoptionen sind unten dargestellt.

![Befehlszeilenoptionen für "Dbanalyze. exe".] (images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Befehlszeilenoptionen für \"Dbanalyze. exe\".")

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

**Computer** Dbanalyze kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem lync Server 2013 installiert ist.

**Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.

**Software** Die lync Server 2013-Softwarekomponenten müssen vor der Ausführung von Dbanalyze installiert werden.

**Benutzer** In der folgenden Tabelle sind die Administratoren aufgeführt, die über die erforderlichen Berechtigungen für den Zugriff auf lync Server 2013-Datenbanken verfügen.

![Berechtigungstabelle für "Dbanalyze. exe".] (images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Berechtigungstabelle für \"Dbanalyze. exe\".")

<div>


> [!NOTE]  
> Für den <STRONG>/report:disk</STRONG>-Modus ist ein lokales Administratorkonto erforderlich.



</div>

</div>

<div>

## <a name="examples"></a>Beispiele

Hier sind Beispiele für gültige „Dbanalyze.exe“-Befehle:

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Dbanalyzer bietet Administratoren eine schnelle und einfache Analyse von lync Server 2013-Datenbanken.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

Mit dem Resource Kit-Tool „ImportStorageServiceData“ können Warteschlangen- und Endpunktdaten, die aus dem Speicherdienst (LYSS) geleert wurden, wieder zurück in den Speicherdienst importiert werden.

<div>

## <a name="description"></a>Beschreibung

Die Leerung der Daten aus dem Speicherdienst kann automatisch (regelmäßig) auf Grundlage des Warteschlangenelementstatus oder der Datenbankgröße erfolgt sein. Das Leeren kann aufgrund eines manuellen Aufrufs des Cmdlets für Poolfailover oder des Cmdlets „StorageServiceFullFlush“ (das vom Cmdlet für Poolfailover aufgerufen wird) erfolgt sein. Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn sich die Datenbankgröße des Speicher Diensts (LYSS) auf den Front-Ends über der normalen Ebene befindet, weil dies wahrscheinlich dazu führt, dass mehr Daten wieder exportiert werden. Darüber hinaus sollten alle Probleme, die zu Fehlern beigetragen haben, die dazu geführt haben, dass die Speicherdienst Warteschlange anwächst, zunächst aufgelöst werden (beispielsweise Exchange-Endpunkt Fehler, Netzwerkprobleme oder andere Probleme).

**Szenario 1:** während des Pool-Failovers können Dateien für jedes Front-End vom Speicherdienst geleert werden. Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.

**Szenario 2:** die Daten werden jeden Tag automatisch geleert oder als Antwort auf eine Speicherdienst Datenbank, die bestimmte Größengrenzwerte überschreitet (beispielsweise 60%, 80%, 90% voll). Diese automatisch geleerten Daten sollten vom Administrator routinemäßig erneut importiert werden. Wenn das SCOM-Überwachungspaket nicht bereitgestellt wird, gibt es in der obigen Situation Ereignisse für den lync Server-Speicherdienst, die sich auf Daten beziehen, die vom Speicherdienst geleert werden. Ereignis-IDs von 32075 (vollständiger Flush-Vorgang wird gestartet), 32076 (vollständiger Flush wurde abgeschlossen), 32082 (Wartungsebene wurde gestartet), 32083 (Maintenance Level Flush Complete), 32089 (Flush ist aufgrund des Auffüllens der Datenbank aufgetreten). Hinweis Diese Ereignis-IDs entsprechen der RTM-Version. Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien vorhanden sind, die geleert wurden. Diese Daten sollten routinemäßig mit diesem Tool wieder importiert werden, beispielsweise einmal pro Woche.

Wenn für die Online Dienstversion die Statusüberwachung SCOM Pack für lync Server bereitgestellt wird, gibt es neue Warnungen, die möglicherweise ausgelöst werden, die den Administrator auffordern, die leeren Daten wieder in den Speicherdienst zu importieren. Im Ereignisprotokoll auf dem Front-End-Server befindet sich ein entsprechendes Ereignis, das die Benachrichtigung ausgelöst hat. Das Ereignis enthält eine Beschreibung des übergeordneten Pfads, unter dem sich die gelesenen Datendateien befinden, sowie die Anzahl der Dateien, die den Warnungskriterien entsprechen. Bei den Warnungskriterien handelt es sich um x oder mehr Dateien unter dem bestimmten übergeordneten Pfad, die mindestens Y Tage alt sind (wobei x und Y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei überschrieben werden können). Nachfolgend werden zwei Beispiele für Ereignisse angezeigt, die die Integritäts Warnung auslösen können, wobei der Unterschied der übergeordnete Pfad ist. Eine Möglichkeit ist unter Web Service File Share zu finden, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist. (Beispiel: c:\\ProgramData\\Microsoft\\lync Server\\StorageService). Der Administrator führt dann dieses reskit-Tool aus.

Dieses Tool erhöht die Auslastung von CPU und E/A-Vorgängen auf dem Front-End-Server, auf dem es ausgeführt wird, sowie auf anderen Front-End-Servern, wenn der Front-End-Server, auf dem das Tool ausgeführt wird, nicht Besitzer der Daten ist. Wir empfehlen die Ausführung dieses Tools, wenn die Auslastung von CPU und E/A-Vorgängen auf den Front-End-Servern niedrig ist, beispielsweise außerhalb der Spitzenzeiten. Darüber hinaus kann dieses Tool zwei bis drei Minuten für den Import einer Datendatei benötigen. Beachten Sie Folgendes, wenn Sie schätzen, wie lange das Tool ausgeführt wird. Die vom Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt. Löschen Sie sie, wenn darin keine Fehler gemeldet werden, da die Protokolldatei mehrere 10 MB übersteigen kann.

![Beispiel Ereignisse für das Speicher Server-Ereignisprotokoll.] (images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Beispiel Ereignisse für das Speicher Server-Ereignisprotokoll.")

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Installieren Sie die lync Server 2013, Resource Kit-Tools. Das Tool wird auf Domänen verbundenen Computern ausgeführt, auf denen lync Server und lync Server-Verwaltungsshell installiert sind. Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren. Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist. Diese Datenbank wird vom Tool verwendet, um den Speicherort der Webservice-Dateifreigabe für den Pool abzurufen. Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools zunächst Windows PowerShell-Remoting mithilfe von **enable-PSRemoting** auf jedem Front-End-Server und dem Computer aktivieren, von dem aus das Tool ausgeführt wird. Andernfalls schlagen die Remote-Windows PowerShell-Befehle dieses Tools fehl. Windows PowerShell-Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem Sie fertig sind. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über die Berechtigung "Lesen/Schreiben" für die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird. Andernfalls schlägt das Tool mit IO-Berechtigungsfehlern fehl.

<div>


> [!NOTE]  
> Unter Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht unter dem BetriebssystemWindows Server 2008.



</div>

</div>

<div>

## <a name="examples"></a>Beispiele

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

</div>

</div>

<div>

## <a name="lcssync"></a>LCSSync

Das LCSSync-Tool hilft beim Bereitstellen von lync Server 2013-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen. Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzergesamtstrukturen als ein Active Directory-Domänendienst-Kontaktobjekt mit einer zentralen Gesamtstruktur zu synchronisieren, in der lync Server 2013 installiert ist.

<div>

## <a name="description"></a>Beschreibung

LCSSync verwendet die synchronisierten Active Directory-Domänendienste-Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzer für lync Server zu aktivieren. Zum Bereitstelleneiner einmaligen Anmeldung muss das primäre Benutzerkonto dem Active Directory-Domänendienste-Kontaktobjekt in der zentralen Gesamtstruktur für lync Server 2013 zugeordnet sein. Dieses Tool hilft bei der Durchführung dieser Zuordnung. Das Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents in Microsoft Identity Integration Server bereit.

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Das LCSSync-Tool hilft beim Bereitstellen von lync Server in einer Umgebung mit mehreren Gesamtstrukturen.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

Das LookupUserConsole-Tool zeigt interne lync Server-Routinginformationen zu bestimmten Benutzern an. Diese Informationen können den Mitarbeitern des Microsoft-Supports dabei helfen, Probleme bei der Bereitstellung und beim Routing zu diagnostizieren.

<div>

## <a name="description"></a>Beschreibung

Beim Ausführen von "LookupUserConsole. exe" wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert, und versucht, interne lync Server-Routinginformationen in Bezug auf diese anzuzeigen. Geben Sie **exit** ein, um das LookupUserConsole-Tool zu beenden.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Installieren Sie die lync Server 2013, Resource Kit-Tools. Das Tool wird auf von der Domäne verbundenen Computern ausgeführt, auf denen lync Server installiert ist.

</div>

<div>

## <a name="examples"></a>Beispiele

C:\\Programmdateien\\Microsoft lync Server 2013\\reskit\>LookupUserConsole. exe

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

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

Mit dem MSTurnPing-Tool kann ein Administrator der Microsoft lync Server 2013-Kommunikationssoftware den Status der Server überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien ausgeführt werden. Dienste in der Topologie.

<div>

## <a name="description"></a>Beschreibung

Das MSTurnPing-Tool ermöglicht einem Administrator der lync Server 2013-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien Dienste ausgeführt werden, im Topologie.

Mit dem Tool können Administratoren die folgenden Tests durchführen:

1.  A/V-Edgeservertest: Das Tool führt mit allen A/V-Edgeservern in der Topologie die folgenden Tests durch:
    
      - Vergewissern Sie sich, dass der lync Server-Audio/Video-Authentifizierungsdienst gestartet wurde, und können Sie die richtigen Anmeldeinformationen ausgeben.
    
      - Überprüfen, ob der lync Server-Audio/Video-Edgedienst gestartet wurde und die Ressourcen auf dem externen Edge erfolgreich zuweisen können.

2.  Test für Bandbreiten-Richtliniendienste: Das Tool führt mit allen Servern in der Topologie, auf denen die Bandbreiten-Richtliniendienste ausgeführt werden, die folgenden Tests durch:
    
      - Überprüfen, ob der lync Server-bandbreitenrichtliniendienst (Authentication) gestartet wurde und geeignete Anmeldeinformationen ausgeben kann.
    
      - Überprüfen, ob der lync Server-bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreiten Überprüfung erfolgreich durchführen kann.

Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist. 

</div>

<div>

## <a name="output"></a>Ausgabe

Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.

  - Wenn der **AudioVideoEdgeServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:
    
      - Die Testergebnisse der Computer, die den lync Server-Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen
    
      - Die Testergebnisse der Computer, die den lync Server-Audio/Video-Edgedienst in der Topologie bereitstellen

  - Wenn der **BandwidthPolicyServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:
    
      - Die Testergebnisse der Computer, die den lync Server-bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen
    
      - Die Testergebnisse der Computer, die den lync Server-bandbreitenrichtliniendienst (Core) in der Topologie bereitstellen

</div>

<div>

## <a name="requirements"></a>Anforderungen

  - Dieses Tool muss auf einem Computer ausgeführt werden, der zur Topologie gehört und auf dem sich der lokale Speicher befindet.

  - Das Tool muss als Administrator mit Zugriff auf den lokalen Speicher ausgeführt werden.

</div>

<div>

## <a name="examples"></a>Beispiele

Hier ist ein Beispiel für die Tooleingabe.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für lync Server 2013-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio/Video-und Bandbreitenrichtlinien Dienste ausgeführt werden.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Network Configuration Viewer

Die Netzwerkkonfigurations-Anzeige kann von Microsoft lync Server 2013-Kommunikationssoftware Administratoren verwendet werden, um die Anruf Zulassungs Steuerung (CAC)-Netzwerktopologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echt Zeit Kommunikationssitzungen zu ermöglichen, wie etwa sprach-oder Videoanrufe auf der Grundlage der angegebenen Bandbreitenkapazität. Lync Server 2013-Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtlinien Diensten erzwungen werden, die mit lync Server 2013 installiert werden.

<div>

## <a name="description"></a>Beschreibung

Mit Network Configuration Viewer („NetworkConfigurationViewer.exe“) können Administratoren die folgenden Aufgaben durchführen:

  - Laden und Anzeigen der CAC-Netzwerktopologie aus einer lync Server 2013-Bereitstellung in einem grafischen Format

  - Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat

  - Sichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger

  - Sichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format

  - Anzeigen von Konfigurationsdaten der CAC-Netzwerktopologie

  - Anzeigen der CAC-Netzwerktopologie in einer Strukturansicht

  - Definieren benutzerdefinierter Connectors für Verbindungen in der CAC-Netzwerktopologie (beispielsweise Standort-zu-Region-, Region-zu-Region- oder Standort-zu-Standort-Verbindungen)

  - Anzeigen von CAC-Netzwerktopologie-Standortinformationen, -Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Anzeigen der Verbindungen in der CAC-Netzwerktopologie des Unternehmens auf einer grafischen Benutzeroberfläche

</div>

<div>

## <a name="examples"></a>Beispiele

**Laden und Anzeigen der CAC-Netzwerktopologie aus einer lync Server 2013-Bereitstellung in einem grafischen Format:** Lync Server 2013-Administratoren können die Konfiguration der CAC-Netzwerktopologie auf jedem lync Server 2013-Computer mithilfe der Option **Netzwerkkonfiguration herunterladen** wie in der folgenden Abbildung gezeigt laden und anzeigen. Bei der Bereitstellung auf einem Computer, der keine Verbindung zum lync-Konfigurationsspeicher hat, kann das Tool keine derartige Konfiguration herunterladen oder anzeigen.

![Herunterladen der Netzwerkkonfiguration.] (images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Herunterladen der Netzwerkkonfiguration.")

**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei in einem grafischen Format:** Lync Server 2013-Bandbreitenrichtlinien Server speichern die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Dateifreigabespeicherort von lync Server 2013. Lync Server-Administratoren können eine solche Datei in einem grafischen Format anzeigen, indem Sie die Option **Netzwerkkonfiguration öffnen** verwenden, wie unten dargestellt.

![Öffnen einer Protokolldatei für den Bandbreitenrichtlinien Server] (images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Öffnen einer Protokolldatei für den Bandbreitenrichtlinien Server")

Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger: lync Server 2013-Administratoren können die Konfigurationsdatei der CAC-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option **Kopie der Netzwerkkonfiguration speichern** verwenden, wie unten dargestellt. Die gespeicherte Konfigurationsdatei kann dann offline als Grafik angezeigt werden.

![Speichern Sie die Netzwerkkonfiguration als XML-Datei.] (images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Speichern Sie die Netzwerkkonfiguration als XML-Datei.")

Speichern und Speichern der CAC-Netzwerktopologie im JPG-oder BMP-Format: lync Server 2013-Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG-und BMP-Dateiformate) speichern, indem Sie das **Diagramm "Netzwerkkonfiguration speichern als Bild** " verwenden. (siehe unten).

![Speichern der Netzwerkkonfiguration als Bild] (images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Speichern der Netzwerkkonfiguration als Bild")

**Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:** Lync Server 2013-Administratoren können verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerk Websites, Bandbreiten Profile und IP-Adressen von Standort-Subnetzen in einem Text Format anzeigen, indem Sie die Option Netzwerkkonfigurationsdaten anzeigen verwenden, wie unten dargestellt.

![Anzeigen von Netzwerkkonfigurationsdaten] (images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten")

**Anzeigen der CAC-Netzwerktopologie in einer Struktur Ansichtsformatvorlage:** Lync Server 2013-Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Struktur Ansichtsformat anzeigen, indem Sie die Systemsteuerung auf der linken Seite des Toolfensters verwenden, wie unten dargestellt.

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht] (images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht")

**Definieren von benutzerdefinierten Connectors für CAC-Netzwerktopologie-Links (wie Website-zu-Region-, Region-zu-Region-und Standort-zu-Standort-Links):** Lync Server 2013-Administratoren können benutzerdefinierte grafische Connectors für CAC-Netzwerkkonfigurations-WAN-Links definieren, indem Sie die Option Einstellungen verwenden, wie unten dargestellt. Dies erleichtert die Unterscheidung zwischen verschiedenen Netzwerkverbindungstypen, die in der Netzwerkkonfiguration bereitgestellt sind.

![Definieren von benutzerdefinierten Connectors für die CAC-Netzwerktopologie] (images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für die CAC-Netzwerktopologie")

**Anzeigen der Informationen zur CAC-Netzwerktopologie, der Regionsinformationen und der bereitgestellten Bandbreitenrichtlinien:** Lync Server 2013-Administratoren können verwandte CAC-Netzwerk Regionsinformationen, Website Informationen und Informationen zur Bereitstellung von CAC-Bandbreiten mithilfe der nachstehend aufgeführten Optionen anzeigen. (Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **Info**.)

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk] (images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für Ihr Netzwerk")

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für lync Server 2013-Administratoren sein, die die CAC-Netzwerktopologie für Ihre Bereitstellung in einem grafischen Format anzeigen möchten.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Response Group Agent Live

Die reaktionsgruppenanwendung bietet Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zuzugreifen. Leider ist keine grafische Ansicht dieser Daten außerhalb der Anwendung verfügbar. Das Tool für den Reaktionsgruppen-Agent Live Resource Kit löst dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die mit Microsoft lync 2013-Kommunikationssoftware Informationen wie dem vorhanden sein anderer Agents verbessert wurde.

<div>

## <a name="description"></a>Beschreibung

Response Group Agent Live ist eine Windows-Anwendung, die An- und Abmeldefunktionen sowie einige Echtzeitinformationen (wie Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bietet. Es handelt sich um eine erweiterte Version der Seite "Agentengruppen" (auf die von lync 2013 aus zugegriffen werden kann.

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschleife und leitet sie dann an Agent-Gruppen weiter. Um informierte Entscheidungen darüber treffen zu können, welche Anrufe bedient werden sollen, können Agents auf Echtzeitinformationen zu ihren Agent-Gruppen zugreifen. Dabei erfahren sie beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst verfügbar sind, werden auf intuitive Weise von Response Group Agent Live zur Verfügung gestellt.

<div>

## <a name="features"></a>Funktionen

Das Live Tool für Reaktionsgruppen-Agents basiert auf dem Reaktionsgruppendienst und dem Microsoft lync 2013 SDK. Es bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die durch den Reaktionsgruppendienst zur Verfügung gestellt werden (beispielsweise Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).

Die Abbildung unten zeigt die Hauptoberfläche von Response Group Agent Live.

![Das Live Tool für Reaktionsgruppen-Agents] (images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Das Live Tool für Reaktionsgruppen-Agents")

Folgende drei Hauptfeatures stehen Agents in Response Group Agent Live zur Verfügung:

  - **Anmeldung/** Abmeldung: Im Gegensatz zur Seite "Agentengruppen" (auf die von lync 2013 aus zugegriffen werden kann) kann der Reaktionsgruppen-Agent Live nur die Anmeldung oder Abmeldung aller Agentengruppen gleichzeitig ermöglichen. Diese Anwendung bietet drei schnelle Methoden zum Anmelden oder Abmelden für Agents:
    
      - Klicken auf die Schaltflächen zum An-/Abmelden (grün und rot) in der Anwendung
    
      - Klicken auf das Taskleistensymbol mit der rechten Maustaste und Auswählen von „Sign-in“ oder „Sign-out“
    
      - Verwenden konfigurierbarer Tastenkombinationen

  - **Gruppenmitgliedschaft:** Wenn eine Agentengruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an. Wenn lync 2013 auf demselben Computer wie diese Anwendung ausgeführt wird, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt. Agents können direkt von dort aus eine Chatnachricht senden oder andere Agents anrufen.

  - **Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agent-Gruppen. Die Statistiken werden minütlich aktualisiert. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein optischer Indikator mit der aktuellen Anzahl der wartenden Anrufe hinzugefügt. Wenn Sie mit dem Mauszeiger auf einer Gruppe verweilen, wird außerdem die längste Wartezeit angezeigt.

</div>

</div>

<div>

## <a name="requirements"></a>Anforderungen

Response Group Agent Live erfordert .NET Framework 4.0. Um die Anwesenheits-und Visitenkarten Features nutzen zu können, muss lync 2013 auch lokal installiert sein (und ausgeführt werden).

<div>

## <a name="configuration"></a>Konfiguration

Response Group Agent Live kann mithilfe des Dialogfelds „Options“ in der Anwendung an die individuellen Anforderungen angepasst werden. Darüber hinaus können Administratoren die Standardhostadresse definieren, indem sie die Eigenschaft „defaultHostAddress“ in der Datei „RGAgentLive.exe.config“ direkt bearbeiten.

Die Abbildung unten zeigt das Dialogfeld „Options“, in dem Agents die Hostadresse und Tastenkombinationen konfigurieren können. Auf dieses Dialogfeld können Sie zugreifen, indem Sie auf der Hauptbenutzeroberfläche rechts oben auf die Schaltfläche „Options“ klicken.

![Das Dialogfeld "Live Optionen" des Reaktionsgruppen-Agents] (images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Das Dialogfeld \"Live Optionen\" des Reaktionsgruppen-Agents")

Folgende drei unterschiedliche Einstellungen können in der Konfiguration von Response Group Agent Live angepasst werden:

  - Hostadresse: Dies ist normalerweise der FQDN des Webpools, der zum Home-Pool des Agents gehört. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads an den Host).

  - Tastenkombinationen: Die genauen Tastenkombinationen zum An- und Abmelden können angepasst werden. Die einzige Einschränkung besteht darin, dass beide Tastenkombinationen die Windows-Logo-Taste enthalten müssen (zusätzlich zu mindestens einer weiteren Taste).

  - Starten mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch beim Starten von Windows gestartet wird.

</div>

</div>

<div>

## <a name="examples"></a>Beispiele

Die Abbildung unten zeigt, wie Sie andere Agents anrufen oder ihnen eine Chatnachricht senden, indem Sie mit der rechten Maustaste im rechten Bereich auf den Kontakt klicken.

![Tätigen eines Anrufs oder Senden einer Chatnachricht] (images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Tätigen eines Anrufs oder Senden einer Chatnachricht")

Die Abbildung unten zeigt, wie Response Group Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife sowie die längste Wartezeit all dieser eingehenden Anrufe anzeigt.

![Anzeigen von Warteschlangeninformationen] (images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Anzeigen von Warteschlangeninformationen")

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Schnelles An- und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Funktionen für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind. Mit dem Live Resource Kit-Tool für Reaktionsgruppen-Agents können lync-Administratoren ihren Agents eine Windows-Anwendung zur Verfügung stellen, die es Ihnen ermöglicht, Aufgaben auf eine schnellere und grafische Weise durchzuführen.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (Secondary Extension Feature Activation) ist ein Befehlszeilentool, mit dem Microsoft lync Server 2013 Communications Software-Administratoren und Helpdesk-Agents Stellvertretungen, Anrufweiterleitung, gleichzeitiges Klingeln, Team Anruf konfigurieren können. Einstellungen und Gruppenanruf Abholung im Auftrag eines lync Server 2013-Benutzers. Das Tool ermöglicht es Administratoren auch, die für einen bestimmten Benutzer veröffentlichten Anrufweiterleitungseinstellungen abzufragen. Das SEFAUtil-Tool ermöglicht es dem Administrator, die Anrufweiterleitung zu aktivieren/zu deaktivieren/zu ändern oder gleichzeitig im Namen des Benutzers Klingeln zu lassen. Der Administrator kann das Ziel (in Form eines SIP-URIs) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde. Dieses Tool ermöglicht es Administratoren auch, Stellvertretungen oder Teamanrufgruppen Mitglieder im Namen des Benutzers hinzuzufügen oder zu entfernen. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.

SEFAUtil (Aktivierung der sekundären Erweiterungsfunktion) ermöglicht lync Server 2013-Administratoren und Helpdesk-Agents die Konfiguration von Delegate-Ringing, Anrufweiterleitung, gleichzeitiges Klingeln, Team Anrufeinstellungen und Abholung von Gruppen anrufen im Auftrag eines lync Server 2013-Benutzers . Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind.

<div>

## <a name="description"></a>Beschreibung

Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool; Es gibt keine unterstützende grafische Benutzeroberfläche. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0. Mit den Features in diesem Tool können Administratoren und Helpdesk-Agents die folgenden Aktionen ausführen:

  - Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Stellvertretung, gleichzeitiges Klingeln, Teamanruf- und Gruppenanrufannahme)

  - Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellungen (einschließlich Ziel und Timer für „Keine Antwort“)

  - Aktivieren/Deaktivieren/Ändern der Konfiguration für sofortige Anrufweiterleitung

  - Aktivieren/Deaktivieren/Ändern von Stellvertretungseinstellungen

  - Aktivieren/Deaktivieren/Ändern von Teamanrufgruppen-Einstellungen
    
    <div>
    

    > [!NOTE]  
    > Neu im lync Server 2013 SEFAUtil-Tool

    
    </div>

  - Aktivieren/Deaktivieren/Ändern der Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)
    
    <div>
    

    > [!NOTE]  
    > Neu im lync Server 2013 SEFAUtil-Tool

    
    </div>

  - Aktivieren/Deaktivieren/Ändern von Einstellungen für Gruppenanrufannahme
    
    <div>
    

    > [!WARNING]  
    > Neu im lync Server 2013 SEFAUtil-Tool

    
    </div>

Für das Tool gelten die folgenden Einschränkungen:

  - Nur für Benutzer unterstützt, die in einem lync Server-Pool verwaltet werden

  - Keine Unterstützung für die Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer

</div>

<div>

## <a name="output"></a>Ausgabe

Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster Ausgaben zur Verfügung. Details hierzu finden Sie weiter unten in diesem Dokument im Abschnitt mit den Beispielen.

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Hier sind einige der Hauptszenarien, in denen dieses Tool eingesetzt werden kann:

  - Bob ist ein Executive-Mitarbeiter und wurde in die lync Server-Telefonie verschoben. In seiner vorhandenen Nebenstellenanlage hat er Stellvertretungen eingerichtet. Im Rahmen des Wechsels zu lync kann der Administrator das Routing von Bobs so konfigurieren, dass es seine bereits vorhandene Delegierungs Konfiguration widerspiegelt.

  - Alice ist auf Reisen und stellt fest, dass sie einen wichtigen Anruf eines ihrer Kunden erwartet. Sie befindet sich aber gerade im Hotel und hat keinen Computer zur Verfügung. Sie ruft den Helpdesk an und bittet darum, alle Anrufe an ihre Büronummer an ihr Mobiltelefon weiterzuleiten. Die Helpdeskmitarbeiter können diese Konfiguration in ihrem Auftrag vornehmen.

  - Die Anrufe an Joes Büronummer landen immer auf seiner mobilen Voicemail, wenn er bei der Arbeit ist. An den meisten anderen Standorten scheint aber alles richtig zu funktionieren. Der Helpdesktechniker kann sich Joes Weiterleitungskonfiguration ansehen und entdeckt, dass Joe für sein Mobiltelefon gleichzeitiges Klingeln konfiguriert hat. Der Techniker fragt Joe nach der Qualität der mobilen Netzabdeckung an seinem Arbeitsplatz und kann so bestimmen, dass die Regel für gleichzeitiges Klingeln dafür verantwortlich ist, dass bei schlechter Netzabdeckung alle Anrufe an Joes mobile Voicemail gehen.

  - Mike ist ein neuer Mitarbeiter bei Contoso und er nimmt an einem neuen Team Teil, bei dem alle Mitglieder für die Team anrufkonfiguration konfiguriert sind, wenn der Administrator für Microsoft lync aktiviert ist, kann der Administrator seine Teamanrufgruppen Einstellungen so festlegen, dass er alle seine neuen Teammitglieder enthält, darüber hinaus die der Administrator fügt Mike als Team Anruf-Gruppenmitglied für alle Mitglieder in seinem Team hinzu.

  - Eine Praxis des Kundendiensts in der Personalabteilung bei Contoso besteht darin, allen Anrufern vom ersten Anruf an persönlichen Service zu bieten. Da alle Mitglieder der Abteilung sehr nah beieinander sitzen, kann das gleichzeitige Klingeln auf allen Telefonen bei Teamanrufen sehr störend für das Team sein. Um den besten Service bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der lync-Administrator die Funktion zur Abhol Funktion für Gruppenanrufe. Der Administrator fügt alle Abteilungsmitglieder einer Annahmegruppe hinzu und teilt der Abteilung die Annahmegruppennummer mit. Wenn nun Samantha nicht an ihrem Platz ist, bemerkt Joe, dass ihr Telefon klingelt, und kann den Anruf von seinem Platz aus annehmen.

</div>

<div>

## <a name="requirements"></a>Voraussetzungen

Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Auf diesem Computer muss UCMA 3.0 installiert sein. Um das Tool auszuführen, muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.

**Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool**

1.  Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die lync Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > Auf allen Computern, auf denen das SEFAUtil-Tool ausgeführt werden soll, muss UCMA 3.0 installiert sein.

    
    </div>

2.  In der Topologie muss eine vertrauenswürdige Anwendung für das SEFAUtil-Tool definiert sein. Wenn Sie SEFAUtil als neue vertrauenswürdige Anwendung definieren möchten, verwenden Sie die lync Server-Verwaltungsshell, und führen Sie das folgende Cmdlet aus:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Gegebenenfalls kann ein anderer Port verwendet werden.

    
    </div>

3.  Die Topologieänderungen müssen aktiviert werden. Das Aktivieren der Topologie-Änderungen kann über die lync Server-Verwaltungsshell erfolgen, indem Sie das folgende Cmdlet ausführen:
    
        Enable-CsToplogy

4.  Installieren Sie bei Bedarf die lync Server 2013 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).

5.  Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie hierzu das Tool an einer Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. Standardmäßig befindet sich das Tool in: "... \\Programmdateien\\Microsoft lync Server 2013\\reskit ". Verwenden Sie zum Anzeigen der Anrufweiterleitungseinstellungen eines Benutzers den folgenden Befehl:
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.

<div>

## <a name="group-call-pickup"></a>Gruppenanrufannahme

Für die Gruppenanruf Abholung ist eine zusätzliche Konfiguration in lync Server erforderlich, damit die Funktion vollständig aktiviert werden kann. Bevor Sie Benutzern Annahmegruppen zuweisen, sollten Sie in der Produktdokumentation der Gruppenanrufannahme die Schritte zur Planung und Bereitstellung dieser Funktion nachlesen.

</div>

</div>

<div>

## <a name="examples"></a>Beispiele

<div>

## <a name="display-current-call-handling-settings"></a>Anzeigen aktueller Anrufbehandlungseinstellungen

Der folgende Befehl zeigt die Anrufbehandlung für den entsprechenden Benutzer an. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> In diesem Beispiel wird <STRONG></STRONG> der Server-Schalter verwendet, um den lync-Server anzugeben, mit dem eine Verbindung hergestellt werden soll.



</div>

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>Festlegen des Ziels für Anrufweiterleitung/Keine Antwort

In diesem Beispiel wird das Ziel des Anruf Weiterleitungs-/Nein-Anrufs und die Klingelverzögerung festgelegt. Hier wird der Schalter//////-Schalter nicht bereitgestellt. SEFAUtil versucht, den lync-Server zu autodiscover.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>Aktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel aktiviert sofort die Anrufweiterleitung an einen anderen Benutzer.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>Deaktivieren der sofortigen Anrufweiterleitung

Dieses Beispiel deaktiviert sofort die Anrufweiterleitung.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Hinzufügen eines Benutzers als Stellvertretung und Einrichten von gleichzeitigem Klingeln bei Stellvertretungen

Dieses Beispiel fügt einen Benutzer als Stellvertretung hinzu und richtet das gleichzeitige Klingeln bei Stellvertretungen ein.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>Ändern der Regel für gleichzeitiges Klingeln bei Stellvertretungen

Dieses Beispiel ändert die Regel für gleichzeitiges Klingeln bei Stellvertretungen, die im vorherigen Beispiel festgelegt wurde, in die Anrufverzögerungsregel.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>Entfernen der Stellvertretung

Dieses Beispiel entfernt die Stellvertretung.

<div>


> [!NOTE]  
> Wenn die letzte Stellvertretung entfernt wurde, wird das Anrufen von Stellvertretungen automatisch deaktiviert.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Hinzufügen einer Stellvertretung und Einrichten der Regel „Anrufweiterleitung an Stellvertretungen“

Dieses Beispiel fügt eine Stellvertretung hinzu und richtet die Regel „Anrufweiterleitung an Stellvertretungen“ ein.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Aktivieren von gleichzeitigem Klingeln und Festlegen einer Zielnummer

Diese Beispiel aktiviert gleichzeitiges Klingeln und legt eine Zielnummer für diese Funktion fest.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> Um die Zielnummer für gleichzeitiges Klingeln eines Benutzers zu ändern, für den gleichzeitiges Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Parameter „/enablesimulring“. Andernfalls wird die Zielnummer nicht geändert.



</div>

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>Deaktivieren von gleichzeitigem Klingeln

Dieses Beispiel deaktiviert gleichzeitiges Klingeln.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Teamanrufgruppen-Mitglieder

Dieses Beispiel fügt der Teamanrufgruppe eines Benutzers ein Teammitglied hinzu und aktiviert gleichzeitiges Klingeln für die Teamanrufgruppe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> Durch das Hinzufügen eines Teammitglieds zur Teamanrufgruppe eines Benutzers werden die Einstellungen der Benutzer für gleichzeitiges Klingeln automatisch auf gleichzeitiges Klingeln für die Teamanrufgruppe umgestellt.



</div>

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>Entfernen eines Mitglieds aus der Teamanrufgruppe

Diese Beispiel entfernt ein Teammitglied aus der Teamanrufgruppe eines Benutzers.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> Wenn das einzige Mitglied der Teamanrufgruppe entfernt wird, wird automatisch das gleichzeitige Klingeln für die Teamanrufgruppe deaktiviert.



</div>

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>Festlegen der Anrufverzögerung für die Teamanrufgruppe

Dieses Beispiel ändert die Zeiteinstellung der Anrufverzögerung für die Teamanrufgruppe.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Aktivieren des Teamanrufs

Dieses Beispiel aktiviert den Teamanruf für einen angegebenen Benutzer.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> Wenn die Teamanrufgruppe des Benutzers keine Mitglieder hat, wird der Teamanruf nicht aktiviert.



</div>

**Ausgabe**

</div>

<div>

## <a name="disable-team-call"></a>Deaktivieren des Teamanrufs

Dieses Beispiel deaktiviert den Teamanruf für einen angegebenen Benutzer.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Aktivieren der Gruppenanrufannahme und Zuweisen einer Annahmegruppe zu einem Benutzer

Dieses Beispiel weist einem Benutzer eine Annahmegruppe zu und aktiviert die Gruppenanrufannahme.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Ausgabe**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>Deaktivieren der Gruppenanrufannahme

Dieses Beispiel deaktiviert die Gruppenanrufannahme für einen angegebenen Benutzer.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, bleibt die Gruppennummer, die dem Benutzer zugewiesen war, nicht erhalten. Wenn Sie die Gruppenanrufannahme für diesen Benutzer anschließend wieder aktivieren möchten, müssen Sie die Gruppennummer erneut mithilfe des Parameters „/enablegrouppickup“ zuweisen.



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep.ps1

<div>

## <a name="description"></a>Beschreibung

"SYSPrep. ps1" ist ein Windows PowerShell-Skript, mit dem die folgenden lync Server 2013-Voraussetzungen auf Ihrem Windows Server 2008-Betriebssystem Computer installiert werden.

  - Microsoft .NET Framework 4.5

  - Microsoft SQL Server Express

  - Windows PowerShell, Version 3.0

  - Visual C++ 2010 Redistributable

  - Updates für Internetinformationsdienste

  - Windows Identity Foundation

  - Core-Dateien für lync Server 2013

Zwar ähnelt der Skriptname dem des Systemvorbereitungsprogramms für die Microsoft Windows-Betriebssysteme, doch sind beide unterschiedlich. Mit diesem Skript werden nur die erforderlichen Voraussetzungen für lync Server 2013 installiert. Sobald diese installiert sind, kann mit dem Windows-Tool für die Systemvorbereitung ein Image des Servers erstellt werden.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Bevor Sie das SYSPrep. ps1-Skript ausführen können, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (zum Beispiel **D:\\Setup)**. Dieser Ordner muss auch eine Kopie der lync Server 2013-Dateien, insbesondere **Setup. exe** , beinhalten. Die erforderlichen Dateien können Sie an folgenden Orten herunterladen:


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
<td><p>Microsoft .NET Framework 4.5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell, Version 3.0</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 Redistributable</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Updates für Internetinformationsdienste</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup. exe</p></td>
<td><p>Kopieren von lync Server 2013-Medien</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>Parameter

Der Parameter **–SetupFolder** akzeptiert als Argument den Verzeichnisspeicherort der erforderlichen Dateien.

</div>

<div>

## <a name="examples"></a>Beispiele

Führen Sie an einer Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl aus, um das Skript "SYSPrep. ps1" auszuführen und die Voraussetzungen für lync Server 2013 zu installieren:

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Unassigned Number Announcements Migration

Mit dem Migrationstool "nicht zugewiesene Nummern Ankündigungen" kann ein lync-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von einem lync-Quellserver oder-Pool zu einem lync-Zielserver oder-Pool verschieben.

<div>

## <a name="description"></a>Beschreibung

Das Tool Unassigned Number Announcements Migration ist ein Windows PowerShell-Skript, das die Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quellserver oder -pool zu einem anderen Server oder Pool verschiebt.

Bei Ausführung des Unassigned Number Announcements Migration-Skripts werden folgende Vorgänge durchgeführt:

1.  Verschieben aller Audiodateien, die von den Ankündigungen für nicht zugewiesene Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Dateispeicher des Zielservers oder -pools
    
    <div>
    

    > [!NOTE]  
    > die Audiodateien werden aus dem Quell Pool entfernt, nachdem Sie in den Ziel Pool kopiert wurden.

    
    </div>

2.  Verschieben aller Ankündigungen für nicht zugewiesene Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Zielserver oder -pool

3.  Erneutes Zuweisen aller nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool verwaltet wird, zum Zielserver oder -pool

Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, nun mit derselben Konfiguration vom Zielserver oder -pool bedient.

</div>

<div>

## <a name="output"></a>Ausgabe

Das **CsAnnouncementConfiguration-** Skript zeigt im Fenster der lync-Verwaltungsshell an, wo es den Erfolg oder Misserfolg des Migrationsvorgangs ausgeführt hat.

Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die erfolgreich in das Ziel verschobenen nicht zugewiesenen Nummernbereiche in funktionsfähiger Form am Ziel, während der Rest der noch zu migrierenden nicht zugewiesenen Nummernbereiche in der Quelle verbleibt – ebenfalls in funktionsfähigem Zustand. Um die restliche Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.

</div>

<div>

## <a name="purpose"></a>Verwendungszweck

Das Unassigned Number Announcements Migration-Skript kann in den drei folgenden Szenarien eingesetzt werden:

  - **Migrieren von Konfigurationseinstellungen zu einer neuen Version von lync Server:** Contoso ist dabei, zu lync Server 2013 zu migrieren, und im Rahmen des Migrationsprozesses möchte der lync Server-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von der lync Server 2010-Bereitstellung auf die neue lync Server 2013-Bereitstellung. Um die Konfigurationseinstellungen zu verschieben, verwendet der lync Server-Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen.

  - Rollback **einer Bereitstellung von lync Server 2013 auf lync Server 2010:** Aufgrund unerwarteter Faktoren muss Contoso die Migration auf die neue lync Server 2013-Bereitstellung zurücksetzen. Um die Unterbrechungen des Diensts zu minimieren, verwendet der lync Server-Administrator das Migrationstool "nicht zugewiesene Nummern Ankündigungen", um die Konfiguration von der lync Server 2013-Bereitstellung auf die lync Server 2010-Bereitstellung zurückzusetzen.

  - **Verschieben von Daten zwischen lync-Bereitstellungen:** Contoso ersetzt alle Server eines Pools durch neuere Server. Ihre Strategie ist die Bereitstellungeines neuen lync Server 2013-Pools, das Verschieben aller Daten aus dem alten in den neuen Pool und das anschließende verwerfen des alten Pools. Sobald der neue Pool bereitgestellt ist, wird die Konfiguration mit dem Tool Unassigned Number Announcements Migration aus dem alten Pool in den neuen verschoben.

<div>

## <a name="requirements"></a>Voraussetzungen

Hier sind die Hauptanforderungen für eine erfolgreiche Ausführung des Tools:

1.  Das Skript muss von einem Computer ausgeführt werden, auf dem die lync Server 2013-Verwaltungsshell installiert ist.

2.  Die Ankündigungs Anwendung muss erfolgreich auf den lync-Servern oder-Pools für Quell-und Zielserver bereitgestellt werden.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Skript „Move-CsAnnouncementConfiguration“

Das Skript „Move-CsAnnouncementConfiguration“ erfordert die in der Tabelle unten beschriebenen zwei Parameter. 

![Move-CsAnnouncementConfiguration-Parameter.] (images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration-Parameter.")

</div>

</div>

</div>

<div>

## <a name="examples"></a>Beispiele

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem lync Server 2010-Pool in einen lync Server 2013-Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2010) in den Ziel Pool (lync Server 2013) verschoben.

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem lync Server 2013-Pool in einen lync Server 2010-Pool

In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2013) in den Ziel Pool (lync Server 2010) verschoben.

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Web Conf Data

Das Tool Web conf Data ermöglicht einem Administrator der lync Server 2013-Kommunikationssoftware, mehr Kontrolle über die Daten zu haben, die den Webkonferenzen eines Organisators zugeordnet sind. Die Szenarien umfassen unter anderem die Möglichkeit, die Besprechungsdaten bestimmter Benutzer auf Grundlage eines Zeitstempelkriteriums zu löschen.

<div>

## <a name="description"></a>Beschreibung

Mit diesem Tool können Administratoren die folgenden Vorgänge durchführen:

1.  Suchen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind

2.  Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind

3.  Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind und deren Alter einen bestimmten Wert überschreitet

4.  Verschieben aller Webkonferenzdaten, die einem Benutzern zugeordnet sind, wenn diese Benutzer aus einem Pool in einen anderen verschoben werden

<div>


> [!NOTE]  
> Die Resource Kit-Tools für lync Server 2010 unterstützt das Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool zu einem anderen verschoben wird. Diese Funktionalität ist jetzt aus diesem Tool für den <STRONG>MoveConferenceData</STRONG> -Parameter veraltet. Details zu diesem Parameter finden Sie unter dem Cmdlet <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> .



</div>

Das Tool löscht Besprechungsdaten nur für inaktive Besprechungen. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.

Dieses Tool muss auf einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool verwaltet werden.

</div>

<div>

## <a name="output"></a>Ausgabe

Dieses Tool gibt die Ergebnisse der folgenden Vorgänge aus:

  - Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, deren Organisator dieser Benutzer ist.

  - Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.

</div>

<div>

## <a name="requirements"></a>Anforderungen

Das Tool muss im selben Pool ausgeführt werden, in dem der Organisator zurzeit verwaltet wird.

Das Tool muss mit Administratorrechten und mit Zugriff auf den Inhaltsdateispeicher ausgeführt werden.

</div>

<div>

## <a name="examples"></a>Beispiele

In der folgenden Tabelle werden die Parameter beschrieben, die zum Teil in den Beispielen verwendet werden.

![Parameter des Web conf-Datentools.] (images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parameter des Web conf-Datentools.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

Oben sehen Sie ein Beispiel für einen Löschbefehl. Der Löschbefehl entfernt alle inaktiven Besprechungsordner dieses Benutzers.

</div>

<div>

## <a name="summary"></a>Zusammenfassung

Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenzbesprechungsdaten benötigen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
