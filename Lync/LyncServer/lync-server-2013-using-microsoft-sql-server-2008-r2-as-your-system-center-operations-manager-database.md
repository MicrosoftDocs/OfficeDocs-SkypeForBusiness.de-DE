---
title: 'Lync Server 2013: Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dbff3748f342bd630c33fc867a4249b386c00c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518822"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Verwenden von Microsoft SQL Server 2008 R2 als System Center Operations Manager-Datenbank für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-29_

Führen Sie die in diesem Thema beschriebenen Schritte aus, um SQL Server 2008 R2 als Back-End-Datenbank zu verwenden.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Konfigurieren SQL Server 2008 R2-und SQL Server Reporting Services

Bevor Sie mit der Installation von System Center Operations Manager beginnen, müssen Sie zwei Änderungen an Ihrer SQL Server 2008 R2 und Ihrer SQL Server Reporting Services-Konfiguration vornehmen. (Diese Änderungen sind nur erforderlich, wenn Sie SQL Server 2008 R2 als Operations Manager-Datenbank verwenden.) Führen Sie zunächst die folgenden Schritte auf dem Computer aus, auf dem die Operations Manager-Datenbank gehostet wird:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Text **C: \\ Programmdateien \\ Microsoft SQL Server \\ MSRS10 \_ 50. ARCHINST \\ Reporting Services \\ Report Server** ein, und drücken Sie dann die EINGABETASTE.

3.  Öffnen Sie im Ordner **Report Server** die Datei **rsreportserver.config** im Editor oder einem anderen Text-Editor.

4.  In der Nähe des Datei Beginns wird eine Reihe von "Schlüssel hinzufügen"-Knoten angezeigt. Suchen Sie den Eintrag, der ** \< Hinzufügen von Key = "SecureConnectionLevel"** beginnt, und legen Sie den Wert auf **0**fest:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Speichern Sie die Datei **rsreportserver.config** , und schließen Sie dann den Text-Editor.

Nach dem Aktualisieren der Berichts Server-Konfigurationsdatei müssen Sie SQL Server Reporting Services das richtige Zertifikat zuweisen. Gehen Sie dazu wie folgt vor:

1.  Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2008 R2**, dann auf **Konfigurations Tools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.

2.  Stellen Sie im Dialogfeld **Reporting Services-Konfigurationsverbindung** sicher, dass der Name des Servers im Feld **Servername** angezeigt wird. Wählen Sie in der Dropdownliste **Berichts Server Instanz** die SQL Server Instanz aus, in der die Operations Manager-Datenbank gehostet wird (beispielsweise **ARCHINST**), und klicken Sie dann auf **verbinden**.

3.  Klicken Sie im Konfigurations-Manager für Reporting Services auf **Webdienst-URL**.

4.  Wählen Sie auf der Seite **Webdienst-URL** das Zertifikat aus der Dropdownliste **SSL-Zertifikat** aus, das für Ihre Reporting Services verwendet werden soll, und klicken Sie dann auf über **nehmen**. Nach ein paar Sekunden wird ein paar von URLs angezeigt, die unter **Report Server-Webdienst-URLs**aufgeführt sind.

5.  Klicken Sie auf beide URLs, um sicherzustellen, dass Sie auf SQL Server Reporting Services zugreifen können.

6.  Schließen Sie den Reporting Services-Konfigurations-Manager.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Erstellen einer System Center Operations Manager-Datenbank für die Verwendung mit SQL Server 2008 R2

Wenn Sie System Center Operations Manager für die Verwendung einer SQL Server 2008 R2-Datenbank konfigurieren möchten, müssen Sie "manuell" die Operations Manager-Datenbank auf dem Computer erstellen, auf dem SQL Server 2008 R2 ausgeführt wird. (Wieder sind diese Schritte nicht erforderlich, wenn Sie SQL Server 2005 oder SQL Server 2008 als Back-End-Datenbank verwenden.)

Führen Sie die folgenden Schritte aus, um eine Operations Manager-Datenbank manuell zu erstellen:

1.  Doppelklicken Sie auf dem System Center Operations Manager 2007 R2-Setup Medium im Support Tools \\ amd64-Ordner auf **DBCreateWizard.exe**.

2.  Klicken Sie im Assistenten für die Datenbankkonfiguration auf der Seite **Willkommen beim Assistenten für die Datenbankkonfiguration** auf **weiter**.

3.  Lassen Sie auf der Seite **Datenbankinformationen** alle Einstellungen unverändert, und klicken Sie dann auf **weiter** .

4.  Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** in das Feld **Verwaltungsgruppenname** einen Namen für die Verwaltungsgruppe ein (beispielsweise **lync Server Überwachung**), und klicken Sie dann auf **weiter**.

5.  Klicken Sie auf der Seite **Fehlerberichte von Operations Manager** auf **weiter**.

6.  Klicken Sie auf der **Zusammenfassungs** Seite auf **Fertig stellen**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Erstellen eines System Center Operations Manager-Data Warehouse für die Verwendung mit SQL Server 2008 R2

Microsoft lync Server 2013 werden mit drei neuen System Center Operations Manager-Berichten ausgeliefert:

  - Bericht zur Verfüg **barkeit von End-to-End-Szenarien**     In diesem Bericht wird die Verfügbarkeit/Uptime für wichtige lync Server Dienste wie Registrierung oder Anwesenheit erläutert.

  - **Kapazitäts Bericht**     In diesem Bericht werden mithilfe von Leistungsindikatorinformationen Trends für Systemkomponenten wie Arbeitsspeicher Verfügbarkeit und Prozessorauslastung dargestellt.

  - **Komponentenbericht**     In diesem Bericht werden die wichtigsten Warnungs Generatoren aufgelistet, die nach lync Server-Komponente gruppiert sind.

Um diese neuen Berichte verwenden zu können, müssen Sie ein System Center Operations Manager-Data Warehouse installieren. (Ein Data Warehouse ermöglicht die langfristige Speicherung von Betriebsdaten.) Wenn Sie ein Data Warehouse mit SQL Server 2008 R2 verwenden möchten, müssen Sie die folgenden Schritte auf dem Computer ausführen, auf dem die SQL Server-Datenbank gehostet wird:

1.  Doppelklicken Sie auf dem System Center Operations Manager-Setup Medium \\ im \\ Ordner Setup Support Tools amd64 auf **DBCreateWizard.exe**.

2.  Klicken Sie im Assistenten für die Datenbankkonfiguration auf der Seite **Willkommen beim Assistenten für die Datenbankkonfiguration** auf **weiter**.

3.  Wählen Sie auf der Seite Daten **Bankinformationen** in der Dropdownliste **Datenbanktyp** die Option **Operations Manager-Data Warehouse-Datenbank** aus, und klicken Sie dann auf **weiter**.

4.  Klicken Sie auf der **Zusammenfassungs** Seite auf **Fertig stellen**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Installieren der System Center Operations Manager-Konsole

Die Operations Manager-Konsole ist das primäre Tool, das zum Verwalten von System Center Operations Manager verwendet wird. Stellen Sie vor dem Installieren der Operations Manager-Konsole sicher, dass Sie eine unterstützte Version von SQL Server zusammen mit dem SQL Server-Berichterstellungsdienst installiert haben. Es wird außerdem empfohlen, den Reporting Services-Konfigurations-Manager von SQL Server auszuführen, um zu überprüfen, ob der Berichterstellungsdienst ordnungsgemäß installiert und konfiguriert wurde.

So installieren Sie die System Center Operations Manager-Konsole:

1.  Doppelklicken Sie auf dem System Center Operations Manager-Setup Medium auf **SetupOM.exe**.

2.  Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Voraussetzungen überprüfen**.

3.  Wählen Sie in der Voraussetzungs Anzeige von System Center Operations Manager die zu installierenden System Center-Komponenten aus: (**Server**; **Konsole**; und **PowerShell**), und klicken Sie dann auf **überprüfen**. Stellen Sie sicher, dass keine Blockierungsprobleme gemeldet wurden, und klicken Sie dann auf **Schließen**. Wenn ein Blockierungsproblem gemeldet wurde, beheben Sie das Problem, und klicken Sie dann auf **überprüfen** , um die erforderlichen Tests erneut auszuführen.

4.  Klicken Sie im System Center Operations Manager-Setup auf **Operations Manager installieren**.

5.  Klicken Sie im System Center Operations Manager-Setup-Assistenten auf der Seite **Willkommen beim Setup-Assistenten von System Center Operations Manager** auf **weiter**.

6.  Wählen Sie auf der Seite **Endbenutzer-Lizenzvertrag** **die Option Ich stimme den Bedingungen des Lizenzvertrags** zu, und klicken Sie dann auf **weiter**.

7.  Geben Sie auf der Seite **Produktregistrierung** ihren Namen in das Feld **Benutzername** und den Namen Ihrer Organisation in das Feld **Organisation** ein. Geben Sie den Product Key für System Center Operations Manager in das Feld **Geben Sie Ihre 25-stellige CD ein** , und klicken Sie dann auf **weiter**.

8.  Wählen Sie auf der Seite **benutzerdefinierte Installation** die System Center-Optionen aus, die installiert werden sollen, und klicken Sie dann auf **weiter**. Sie sollten **Verwaltungs Server**, **Benutzeroberflächen**und **Webkonsolen** auswählen, die installiert werden sollen. Die **Datenbank** sollte nicht ausgewählt werden und sollte nicht installiert werden.

9.  Stellen Sie auf der Seite **SC-Datenbankserverinstanz** sicher, dass der Name des Computers, auf dem die Operations Manager-Datenbanken installiert sind, im Feld **System Center-Datenbankserver** angezeigt wird. Klicken Sie auf **Weiter**.

10. Wählen Sie auf der Seite **Verwaltungs Server-Aktionskonto** die Option **Domäne oder lokales Computerkonto** aus, und geben Sie dann die entsprechenden Werte in die Felder **Benutzerkonto**, **Kennwort**und **Domäne oder lokaler Computer** ein. Klicken Sie auf **Weiter**.

11. Wählen Sie auf der Seite **SDK-und Konfigurationsdienstkonto** die Option **Domäne oder lokales Computerkonto** aus, und geben Sie dann die entsprechenden Werte in die Felder **Benutzerkonto**, **Kennwort**und **Domäne oder lokaler Computer** ein. Klicken Sie auf **Weiter**.

12. Klicken Sie auf der Seite **Fehlerberichte von Operations Manager** auf **weiter**.

13. Klicken Sie auf der Seite **Programm zur Verbesserung der Benutzerfreundlichkeit** auf **weiter**.

14. Klicken Sie auf der Seite **Programm kann** installiert werden auf **Installieren**.

15. Deaktivieren Sie auf der Seite **System Center Operations Manager-Setup abschließen** die Kontrollkästchen **Verschlüsselungsschlüssel sichern** und **Konsole starten** , und klicken Sie dann auf **Fertig stellen**.

16. Klicken Sie im System Center Operations Manager-Setup auf **Beenden**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Installieren von System Center Reporting Services

Nachdem Sie die System Center Operations Manager-Konsole installiert und konfiguriert haben, müssen Sie System Center Reporting Services installieren. Wenn Sie SQL Server 2008 R2 als Back-End-Datenbank für Operations Manager verwenden, müssen Sie zunächst eine temporäre Änderung an der Sicherheitsgruppe vornehmen, die SQL Server Reporting Services zugeordnet ist. Wenn Sie SQL Server 2008 R2 verwenden, müssen Sie folgende Schritte ausführen:

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Erweitern Sie im Server-Manager die Optionen **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Suchen Sie die folgende Gruppe, wobei ATL-SC-001 den Namen Ihres Computers darstellt und ARCHINST die SQL Server Instanz für die System Center-Datenbank darstellt: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.

4.  Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**. Benennen Sie die Gruppe um, indem Sie ** \_ 50** aus dem Gruppennamen löschen. Beispiel: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Schließen Sie den Server-Manager.

An diesem Punkt sind Sie für die Installation von System Center Reporting Services gerüstet. Gehen Sie hierfür folgendermaßen vor:

1.  Doppelklicken Sie auf dem System Center Operations Manager 2007 R2-Setup Medium auf **SetupOM.exe**.

2.  Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Operations Manager-Berichterstellung installieren**.

3.  Klicken Sie im System Center Operations Manager 2007 R2-Bericht Erstellungs-Assistenten auf der Seite Willkommen bei der **Installation von Operations Manager** auf **weiter**.

4.  Wählen Sie auf der Seite **Endbenutzer-Lizenzvertrag** **die Option Ich stimme den Bedingungen des Lizenzvertrags** zu, und klicken Sie dann auf **weiter**.

5.  Stellen Sie auf der Seite **Produktregistrierung** sicher, dass Ihr Name und der Name Ihrer Organisation in den Feldern **Benutzername** und **Organisation** angezeigt werden, und klicken Sie dann auf **weiter**.

6.  Klicken Sie auf der Seite **benutzerdefinierte Installation** auf **Berichts Server** , und wählen Sie **Diese Komponente aus, und alle abhängigen Komponenten werden auf dem lokalen Datenträger installiert**. Klicken Sie auf **Data Warehouse** , und wählen Sie **Diese Komponente ist nicht verfügbar**, und klicken Sie dann auf **weiter**.

7.  Geben Sie auf der Seite mit **dem Stammverwaltungsserver verbinden** den Namen des Operations Manager-Stammverwaltungsservers in das Feld **Stamm Verwaltungs** Server ein, und klicken Sie dann auf **weiter**.

8.  Geben Sie auf der Seite **Verbindung mit dem Operations Manager-Data Warehouse herstellen** die SQL Server Instanz ein, in der sich Ihr Data Warehouse im Feld **SQL Server Instanz** befindet. (Wenn sich Ihr Data Warehouse in der Standardinstanz befindet, geben Sie einfach den Servernamen ein; Beispiel: ATL-SQL-001.) Stellen Sie sicher, dass der Datenbankname **OperationsManagerDW** im Feld **Name** angezeigt wird und dass Port **1433** im Feld **SQL Server Port** angezeigt wird. Klicken Sie auf **Weiter**.

9.  Wählen Sie auf der Seite **SQL Server Berichtsinstanz** Ihren SQL Server Berichts Server aus der Dropdownliste **Geben Sie den SQL Server Reporting Services-Server ein** , und klicken Sie dann auf **weiter**.

10. Geben Sie auf der Seite **Data Warehouse-Schreib Konto** den Namen und das Kennwort des Benutzers ein, dem zunächst Schreibberechtigungen für das Data Warehouse in den Feldern **Benutzerkonto** und **Kennwort** zugewiesen werden sollen. Wählen Sie in der Dropdownliste **Domäne** die Domäne des Benutzers aus, und klicken Sie dann auf **weiter**.

11. Geben Sie auf der Seite **Datenleser Konto** den Namen und das Kennwort des Benutzerkontos ein, das verwendet werden soll, wenn SQL Reporting Services das Data Warehouse in den Feldern **Benutzerkonto** und **Kennwort** fragt. Wählen Sie in der Dropdownliste **Domäne** die Kontodomäne aus, und klicken Sie dann auf **weiter**.

12. Klicken Sie auf der Seite **operative Daten Berichte** auf **weiter**.

13. Klicken Sie auf der Seite **Microsoft Update** auf **weiter**.

14. Klicken Sie auf der Seite **Programm kann** installiert werden auf **Installieren**.

15. Klicken Sie auf der Seite zum **abschließen des Setup-Assistenten für die Operations Manager-Berichtskomponenten** auf **Fertig stellen**.

16. Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Beenden**.

Nachdem Sie die System Center-Berichterstellung installiert haben, verwenden Sie das folgende Verfahren, um den Namen der Sicherheitsgruppe zurückzusetzen, die SQL Server Berichterstellung zugeordnet ist. Dieses Verfahren ist wiederum nur erforderlich, wenn Sie SQL Server verwenden:

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Erweitern Sie im Server-Manager die Optionen **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Suchen Sie die folgende Gruppe, wobei ATL-SC-001 den Namen Ihres Computers darstellt und ARCHINST die SQL Server Instanz für die Archivierungs-und Überwachungsdatenbanken darstellt: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**. Benennen Sie die Gruppe um, indem Sie ** \_ 50** an das Ende des Gruppennamens, direkt vor dem Namen der SQL Server Instanz, hinzufügen. Beispiel: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10 \_ 50. ARCHINST**.

5.  Schließen Sie den Server-Manager.

Wenn die System Center-Betriebskonsole geöffnet ist, müssen Sie die Anwendung schließen und neu starten. Wenn Sie dies nicht tun, wird die Registerkarte " **Berichterstellung** " nicht auf der Benutzeroberfläche der Betriebskonsole angezeigt. Beachten Sie, dass es nach dem ersten Neustart der Betriebskonsole einige Minuten dauern kann, bis alle Überwachungsberichte auf der Registerkarte " **Berichterstellung** " angezeigt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

