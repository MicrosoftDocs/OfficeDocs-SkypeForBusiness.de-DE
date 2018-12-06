---
title: Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank
TOCTitle: Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49890625
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank

 

_**Letztes Änderungsdatum des Themas:** 2013-07-29_

Führen Sie die in diesem Thema beschriebenen Schritte aus, um SQL Server 2008 R2 als Back-End-Datenbank zu verwenden.

## Konfigurieren von SQL Server 2008 R2 und SQL Server Reporting Services

Bevor Sie mit der Installation von System Center Operations Manager beginnen, müssen Sie zwei Änderungen an der SQL Server 2008 R2- und SQL Server Reporting Services-Konfiguration vornehmen. (Diese Änderungen sind nur erforderlich, wenn Sie SQL Server 2008 R2 als Operations Manager-Datenbank verwenden). Führen Sie zunächst folgende Schritte auf dem Computer aus, auf dem Ihre Operations Manager-Datenbank gehostet wird:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **AusführenC:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** ein, und drücken Sie dann die EINGABETASTE.

3.  Öffnen Sie im Ordner **ReportServer** die Datei **rsreportserver.config** in Editor oder einem anderen Text-Editor.

4.  Am Anfang der Datei finden Sie eine Reihe von "Add Key"-Knoten. Suchen Sie den Eintrag, der mit **\<Add Key="SecureConnectionLevel"** beginnt, und setzen Sie den Wert auf **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Speichern Sie die Datei **rsreportserver.config**, und schließen Sie dann den Text-Editor.

Nach dem Aktualisieren der Report Server-Konfigurationsdatei müssen Sie SQL Server Reporting Services das richtige Zertifikat zuweisen. Gehen Sie dazu folgendermaßen vor:

1.  Klicken Sie auf **Start**, **Alle Programme**, **Microsoft SQL Server 2008 R2**, **Konfigurationstools** und schließlich auf **Konfigurations-Manager für Reporting Services**.

2.  Stellen Sie im Dialogfeld **Konfigurationsverbindung für Reporting Services** sicher, dass der Name Ihres Servers im Feld **Servername** vorhanden ist. Wählen Sie in der Dropdownliste **Berichtsserverinstanz** die SQL Server-Instanz aus, auf der Ihre Operations Manager-Datenbank gehostet wird (z. B. **ARCHINST**), und klicken Sie dann auf **Verbinden**.

3.  Klicken Sie im Konfigurations-Manager für Reporting Services auf **Webdienst-URL**.

4.  Wählen Sie auf der Seite **Webdienst-URL** in der Dropdownliste **SSL-Zertifikat** das Zertifikat aus, das für Reporting Services verwendet werden soll, und klicken Sie dann auf **Anwenden**. Nach einigen Sekunden werden unter **URLs für Berichtsserver-Webdienst** zwei URLs angezeigt.

5.  Klicken Sie auf beide URLs, um sicherzustellen, dass Sie auf SQL Server Reporting Services zugreifen können.

6.  Schließen Sie den Konfigurations-Manager für Reporting Services.

## Erstellen einer System Center Operations Manager-Datenbank für die Verwendung mit SQL Server 2008 R2

Wenn Sie System Center Operations Manager für die Verwendung einer SQL Server 2008 R2-Datenbank konfigurieren möchten, müssen Sie die Operations Manager-Datenbank "manuell" auf dem Computer erstellen, auf dem SQL Server 2008 R2 ausgeführt wird. (Auch diese Schritte sind nicht erforderlich, wenn Sie SQL Server 2005 oder SQL Server 2008 als Back-End-Datenbank verwenden.)

Gehen Sie wie folgt vor, um manuell eine Operations Manager-Datenbank zu erstellen:

1.  Doppelklicken Sie in den System Center Operations Manager 2007 R2-Setupmedien im Ordner "SupportTools\\AMD64" auf **DBCreateWizard.exe**.

2.  Klicken Sie im Datenbankkonfigurations-Assistenten auf der Seite **Willkommen** auf **Weiter**.

3.  Behalten Sie auf der Seite **Datenbankinformationen** alle Einstellungen bei, und klicken Sie dann auf **Weiter**

4.  Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** im Feld **Verwaltungsgruppenname** einen Namen für Ihre Verwaltungsgruppe ein (z. B. **Lync Server-Überwachung**), und klicken Sie dann auf **Weiter**.

5.  Klicken Sie auf der Seite **Fehlerberichte für Operations Manager** auf **Weiter**.

6.  Klicken Sie auf der Seite **Zusammenfassung** auf **Fertig stellen**.

## Erstellen eines System Center Operations Manager-Data Warehouse für die Verwendung mit SQL Server 2008 R2

Microsoft Lync Server 2013 umfasst drei neue System Center Operations Manager-Berichte:

  - **Umfassender Szenarioverfügbarkeitsbericht**   Dieser Bericht enthält Details zur Verfügbarkeit/Betriebszeit wichtiger Lync Server-Dienste wie z. B. Registrierung oder Anwesenheit.

  - **Kapazitätsbericht**   Dieser Bericht verwendet Leistungsindikatoreninformationen und zeigt Trends für Systemkomponenten wie z. B. Arbeitsspeicherverfügbarkeit und Prozessorauslastung.

  - **Komponentenbericht**   In diesem Bericht sind die wichtigsten Warnungsgeneratoren gruppiert nach Lync Server-Komponente aufgeführt.

Zur Verwendung dieser neuen Berichte müssen Sie ein System Center Operations Manager-Data Warehouse erstellen. (In einem Data Warehouse werden Vorgangsdaten langfristig gespeichert.) Um ein Data Warehouse in Verbindung mit SQL Server 2008 R2 zu verwenden, müssen Sie folgende Schritte auf dem Computer ausführen, auf dem Ihre SQL Server-Datenbank gehostet ist:

1.  Doppelklicken Sie in den System Center Operations Manager-Setupmedien im Ordner "Setup\\SupportTools\\AMD64" auf **DBCreateWizard.exe**.

2.  Klicken Sie im Datenbankkonfigurations-Assistenten auf der Seite **Willkommen** auf **Weiter**.

3.  Wählen Sie auf der Seite **Datenbankinformationen** in der Dropdownliste **Datenbanktyp** die Option **Operations Manager Data Warehouse-Datenbank**, und klicken Sie dann auf **Weiter**.

4.  Klicken Sie auf der Seite **Zusammenfassung** auf **Fertig stellen**.

## Installieren der System Center Operations Manager-Konsole

Die Operations Manager-Konsole ist das wichtigste Tool beim Verwalten von System Center Operations Manager. Bevor Sie die Operations Manager-Konsole installieren, stellen Sie sicher, dass Sie eine unterstützte Version von SQL Server und SQL Server Reporting Service installiert haben. Außerdem wird empfohlen, den Konfigurations-Manager für Reporting Services von SQL Server auszuführen, um sicherzustellen, dass der Reporting Service ordnungsgemäß installiert und konfiguriert wurde.

So installieren Sie die System Center Operations Manager-Konsole

1.  Doppelklicken Sie in den System Center Operations Manager-Setupmedien auf **SetupOM.exe**.

2.  Klicken Sie im System Center Operations Manager 2007 R2-Setup auf **Voraussetzungen überprüfen**.

3.  Wählen Sie im System Center Operations Manager Prerequisite Viewer die zu installierenden System Center-Komponenten: (**Server**, **Konsole** und **PowerShell**), und klicken Sie dann auf **Überprüfen**. Stellen Sie sicher, dass keine Blockierungsprobleme berichtet wurden, und klicken Sie dann auf **Schließen**. Wenn ein Blockierungsproblem berichtet wurde, beheben Sie es, und klicken Sie dann auf **Überprüfen**, um die Überprüfung der Voraussetzungen zu wiederholen.

4.  Klicken Sie im System Center Operations Manager-Setup auf **Operations Manager installieren**.

5.  Klicken Sie im System Center Operations Manager-Setup-Assistenten auf der Seite **Willkommen beim System Center Operations Manager-Setup-Assistenten** auf **Weiter**.

6.  Wählen Sie auf der Seite **Endbenutzer-Lizenzvertrag** die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **Weiter**.

7.  Geben Sie auf der Seite **Produktregistrierung** im Feld **Benutzername** Ihren Namen und im Feld **Organisation** den Namen Ihrer Organisation ein. Geben Sie im Feld **Geben Sie den 25-stelligen CD Key ein** den System Center Operations Manager-Produktschlüssel ein, und klicken Sie dann auf **Weiter**.

8.  Wählen Sie auf der Seite **Benutzerdefiniertes Setup** die zu installierenden System Center-Optionen, und klicken Sie dann auf **Weiter**. Sie sollten **Management Server**, **Benutzeroberflächen** und **Webkonsole** zur Installation auswählen. **Datenbank** sollte nicht ausgewählt und installiert werden.

9.  Überprüfen Sie auf der Seite **Serverinstanz der SC-Datenbank**, dass der Name des Computers, auf dem die Operations Manager-Datenbanken installiert sind, im Feld **System Center-Datenbankserver** vorhanden ist. Klicken Sie auf **Weiter**.

10. Wählen Sie auf der Seite **Verwaltungsserver-Aktionskonto** die Option **Domänenkonto oder lokales Computerkonto**, und geben Sie in die Felder **Benutzerkonto**, **Kennwort** und **Domäne oder lokaler Computer** die entsprechenden Werte ein. Klicken Sie auf **Weiter**.

11. Wählen Sie auf der Seite **SDK und Konfigurationsdienstkonto** die Option **Domänenkonto oder lokales Computerkonto**, und geben Sie in die Felder **Benutzerkonto**, **Kennwort** und **Domäne oder lokaler Computer** die entsprechenden Werte ein. Klicken Sie auf **Weiter**.

12. Klicken Sie auf der Seite **Fehlerberichte für Operations Manager** auf **Weiter**.

13. Klicken Sie auf der Seite **Programm zur Verbesserung der Benutzerfreundlichkeit** auf **Weiter**.

14. Klicken Sie auf der Seite **Das Programm kann jetzt installiert werden** auf **Installieren**.

15. Deaktivieren Sie auf der Seite **Abschließen des System Center Operations Manager-Setups** die Kontrollkästchen **Sicherungsverschlüsselungsschlüssel** und **Konsole starten**, und klicken Sie dann auf **Fertig stellen**.

16. Klicken Sie im System Center Operations Manager-Setup auf **Beenden**.

## Installieren von System Center Reporting Services

Nach dem Installieren und Konfigurieren der System Center Operations Manager-Konsole müssen Sie System Center Reporting Services installieren. Wenn Sie SQL Server 2008 R2 als Operations Manager-Back-End-Datenbank verwenden, müssen Sie zunächst eine temporäre Änderung an der Sicherheitsgruppe vornehmen, die SQL Server Reporting Services zugeordnet ist. Wenn Sie SQL Server 2008 R2 verwenden, gehen Sie folgendermaßen vor:

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Erweitern Sie im Server-Manager **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Suchen Sie die folgende Gruppe, wobei "atl-sc-001" der Name Ihres Computers und "ARCHINST" die SQL Server-Instanz für die System Center-Datenbank ist: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.

4.  Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**. Benennen Sie die Gruppe um, indem Sie **\_50** aus dem Gruppennamen entfernen. Beispiel:**SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.

5.  Schließen Sie den Server-Manager.

Jetzt sind Sie bereit für die Installation von System Center Reporting Services. Gehen Sie dazu wie folgt vor:

1.  Doppelklicken Sie in den System Center Operations Manager 2007 R2-Setupmedien auf **SetupOM.exe**.

2.  Klicken Sie im System Center Operations Manager 2007 R2-Setup auf **Operations Manager Reporting installieren**.

3.  Klicken Sie im Setup-Assistenten für System Center Operations Manager 2007 R2 auf der Seite **Willkommen** auf **Weiter**.

4.  Wählen Sie auf der Seite **Endbenutzer-Lizenzvertrag** die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **Weiter**.

5.  Stellen Sie auf der Seite **Produktregistrierung** sicher, dass Ihr Name und der Name Ihrer Organisation in den Feldern **Benutzername** und **Organisation** vorhanden sind, und klicken Sie dann auf **Weiter**.

6.  Klicken Sie auf der Seite **Benutzerdefiniertes Setup** auf **Berichtsserver**, und wählen Sie die Option **Diese Komponente wird mit allen abhängigen Komponenten auf dem lokalen Laufwerk installiert**. Klicken Sie auf **Data Warehouse**, wählen Sie die Option **Diese Komponente wird nicht verfügbar sein**, und klicken Sie dann auf **Weiter**.

7.  Geben Sie auf der Seite **Verbindung mit dem Stammverwaltungsserver aufbauen** im Feld **Stammverwaltungsserver** den Namen Ihres Operations Manager-Stammverwaltungsservers ein, und klicken Sie dann auf **Weiter**.

8.  Geben Sie auf der Seite **Verbindung mit dem Operations Manager-Data Warehouse aufbauen** im Feld **SQL Server-Instanz** die SQL Server-Instanz ein, auf der sich Ihr Data Warehouse befindet. (Befindet sich Ihr Data Warehouse in der Standardinstanz, geben sie einfach den Servernamen ein, z. B. "atl-sql-001".) Stellen Sie sicher, dass der Datenbankname **OperationsManagerDW** im Feld **Name** und der Port **1433** im Feld **SQL Server-Port** vorhanden sind. Klicken Sie auf **Weiter**.

9.  Wählen Sie auf der Seite **SQL Server Reporting-Instanz** in der Dropdownliste **Geben Sie den Server mit SQL Server Reporting Services ein** Ihren SQL Server-Berichtsserver, und klicken Sie dann auf **Weiter**.

10. Geben Sie auf der Seite **Data Warehouse-Konto für Schreibvorgänge** in den Feldern **Benutzerkonto** und **Kennwort** den Namen und das Kennwort des Benutzers ein, den anfänglich Schreibberechtigungen für das Data Warehouse zugewiesen werden sollen. Wählen Sie in der Dropdownliste **Domäne** die Domäne des Benutzers, und klicken Sie dann auf **Weiter**.

11. Geben Sie auf der Seite **Datenlesekonto** in den Feldern **Benutzerkonto** und **Kennwort** den Namen und das Kennwort des Benutzers ein, der verwendet werden soll, wenn SQL Reporting Services das Data Warehouse abfragt. Wählen Sie in der Dropdownliste **Domäne** die Kontodomäne, und klicken Sie dann auf **Weiter**.

12. Klicken Sie auf der Seite **Berichte für operative Daten** auf **Weiter**.

13. Klicken Sie auf der Seite **Microsoft Update** auf **Weiter**.

14. Klicken Sie auf der Seite **Das Programm kann jetzt installiert werden** auf **Installieren**.

15. Klicken Sie auf der Seite **Fertigstellen des Assistenten** auf **Fertig stellen**.

16. Klicken Sie im System Center Operations Manager 2007 R2-Setup auf **Beenden**.

Nach der Installation von System Center Reporting verwenden Sie das folgenden Verfahren, um den Namen der Sicherheitsgruppe zurückzusetzen, der SQL Server Reporting zugeordnet ist. Auch dieses Verfahren ist nur erforderlich, wenn Sie SQL Server verwenden:

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Erweitern Sie im Server-Manager **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Suchen Sie die folgende Gruppe, wobei "atl-sc-001" der Name Ihres Computers und "ARCHINST" die SQL Server-Instanz für die Überwachungs- und Archivierungsdatenbank ist: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.

4.  Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**. Benennen Sie die Gruppe um, indem Sie am Ende des Gruppennamens und vor dem SQL Server-Instanznamen **\_50** hinzufügen. Beispiel:**SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.

5.  Schließen Sie den Server-Manager.

Wenn die System Center Operations-Konsole geöffnet ist, müssen Sie die Anwendung schließen und neu starten, andernfalls wird die Registerkarte **Berichterstellung** nicht auf der Benutzeroberfläche der Operations-Konsole angezeigt. Nach dem ersten Neustart der Operations-Konsole kann es mehrere Minuten dauern, bis alle Überwachungsberichte auf der Registerkarte **Berichterstellung** angezeigt werden.

