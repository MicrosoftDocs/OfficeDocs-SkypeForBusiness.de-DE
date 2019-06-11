---
title: 'Lync Server 2013: Verwenden von Microsoft SQL Server 2008 R2 als Ihre System Center Operations Manager-Datenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858134b4d7f2a2fbc4e15c14e121ac12679c9ddc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Verwenden von Microsoft SQL Server 2008 R2 als Ihre System Center Operations Manager-Datenbank für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-29_

Wenn Sie SQL Server 2008 R2 als Back-End-Datenbank verwenden möchten, führen Sie die in diesem Thema beschriebenen Schritte aus.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Konfigurieren von SQL Server 2008 R2 und SQL Server Reporting Services

Bevor Sie mit der Installation von System Center Operations Manager beginnen, müssen Sie zwei Änderungen an Ihrem SQL Server 2008 R2 und Ihrer SQL Server Reporting Services-Konfiguration vornehmen. (Diese Änderungen sind nur erforderlich, wenn Sie SQL Server 2008 R2 als Operations Manager-Datenbank verwenden.) Führen Sie zunächst die folgenden Schritte auf dem Computer aus, auf dem Ihre Operations Manager-Datenbank gehostet wird:

1.  Klicken Sie auf **Start** und dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den **Text C\\: Programm\\Dateien Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting\\Services Report** Server ein, und drücken Sie dann die EINGABETASTE.

3.  Öffnen Sie im Ordner **Report Server** die Datei **RSReportServer. config** in Editor oder einem beliebigen anderen Text-Editor.

4.  Am Anfang der Datei sehen Sie eine Reihe von "Schlüssel hinzufügen"-Knoten. Suchen Sie den Eintrag, der mit ** \<Add Key = "SecureConnectionLevel"** beginnt, und legen Sie den Wert auf **0**fest:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Speichern Sie die Datei **RSReportServer. config** , und schließen Sie dann den Text-Editor.

Nachdem Sie die Berichts Server-Konfigurationsdatei aktualisiert haben, müssen Sie SQL Server Reporting Services das richtige Zertifikat zuweisen. Gehen Sie dazu wie folgt vor:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2008 R2**, klicken Sie auf **Konfigurations Tools**, und klicken Sie dann auf **Reporting Services-Konfigurations-Manager**.

2.  Stellen Sie im Dialogfeld **Reporting Services-Konfigurationsverbindung** sicher, dass der Name Ihres Servers im Feld **Servername** angezeigt wird. Wählen Sie die SQL Server-Instanz aus, die Ihre Operations Manager-Datenbank (beispielsweise **ARCHINST**) in der Dropdownliste **Berichts Server Instanz** hosten soll, und klicken Sie dann auf **verbinden**.

3.  Klicken Sie im Reporting Services-Konfigurations-Manager auf **Webdienst-URL**.

4.  Wählen Sie auf der Seite **Webdienst-URL** das für Ihre Reporting Services zu verwendende Zertifikat aus der Dropdownliste **SSL-Zertifikat** aus, und klicken Sie dann auf über **nehmen**. Nach ein paar Sekunden sehen Sie ein paar URLs, die unter den **URL des Berichts Server-** Webdiensts aufgelistet sind.

5.  Klicken Sie auf beide URLs, um zu überprüfen, ob Sie auf SQL Server Reporting Services zugreifen können.

6.  Schließen Sie den Reporting Services-Konfigurations-Manager.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Erstellen einer System Center Operations Manager-Datenbank für die Verwendung mit SQL Server 2008 R2

Wenn Sie System Center Operations Manager für die Verwendung einer SQL Server 2008 R2-Datenbank konfigurieren möchten, müssen Sie die Operations Manager-Datenbank auf dem Computer, auf dem SQL Server 2008 R2 ausgeführt wird, manuell erstellen. (Wieder sind diese Schritte nicht erforderlich, wenn Sie SQL Server 2005 oder SQL Server 2008 als Back-End-Datenbank verwenden.)

Gehen Sie wie folgt vor, um eine Operations Manager-Datenbank manuell zu erstellen:

1.  Doppelklicken Sie auf den Setupmedien von System Center Operations Manager 2007 R2\\im Support Tools amd64-Ordner auf **DBCreateWizard. exe**.

2.  Klicken Sie im Assistenten für die Datenbankkonfiguration auf der Seite **Willkommen beim Assistenten für die Datenbankkonfiguration** auf **weiter**.

3.  Übernehmen Sie auf der Seite **Datenbankinformationen** alle Einstellungen unverändert, und klicken Sie dann auf **weiter** .

4.  Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** einen Namen für Ihre Verwaltungsgruppe (beispielsweise die **lync Server-Überwachung**) im Feld **Verwaltungsgruppenname** ein, und klicken Sie dann auf **weiter**.

5.  Klicken Sie auf der Seite **Operations Manager-Fehlerberichte** auf **weiter**.

6.  Klicken Sie **** auf der Zusammenfassungsseite auf **Fertig stellen**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Erstellen eines System Center Operations Manager-Data Warehouse zur Verwendung mit SQL Server 2008 R2

Microsoft lync Server 2013 wird mit drei neuen System Center Operations Manager-Berichten ausgeliefert:

  - **Bericht zur Verfügbarkeit von Szenarien bis zum**   Ende dieser Bericht enthält Informationen zur Verfügbarkeit/Uptime für wichtige lync Server-Dienste wie Registrierung oder Anwesenheit.

  - **Kapazitäts Bericht**   mithilfe von Leistungsindikatorinformationen werden in diesem Bericht Trends für Systemkomponenten wie Speicherverfügbarkeit und Prozessorauslastung veranschaulicht.

  - **Komponentenbericht**   dieser Bericht listet die obersten Warnungs Generatoren auf, die nach lync Server-Komponente gruppiert sind.

Um diese neuen Berichte verwenden zu können, müssen Sie ein System Center Operations Manager-Data Warehouse installieren. (Ein Data Warehouse bietet die langfristige Speicherung von Vorgangsdaten.) Wenn Sie ein Data Warehouse mit SQL Server 2008 R2 verwenden möchten, müssen Sie auf dem Computer, auf dem Ihre SQL Server-Datenbank gehostet wird, die folgenden Schritte ausführen:

1.  Doppelklicken Sie auf den System Center Operations Manager-Setupmedien\\im\\Ordner Setup Support Tools amd64 auf **DBCreateWizard. exe**.

2.  Klicken Sie im Assistenten für die Datenbankkonfiguration auf der Seite **Willkommen beim Assistenten für die Datenbankkonfiguration** auf **weiter**.

3.  Wählen Sie auf der Seite **Datenbankinformationen** in der Dropdownliste **Datenbanktyp** die Option **Operations Manager Data Warehouse-Datenbank** aus, und klicken Sie dann auf **weiter**.

4.  Klicken Sie **** auf der Zusammenfassungsseite auf **Fertig stellen**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Installieren der System Center Operations Manager-Konsole

Die Operations Manager-Konsole ist das primäre Tool, das zum Verwalten von System Center Operations Manager verwendet wird. Bevor Sie die Operations Manager-Konsole installieren, stellen Sie sicher, dass Sie zusammen mit dem SQL Server-Berichterstattungsdienst eine unterstützte Version von SQL Server installiert haben. Außerdem wird empfohlen, den Reporting Services-Konfigurations-Manager von SQL Server auszuführen, um zu überprüfen, ob der Berichterstattungsdienst ordnungsgemäß installiert und konfiguriert wurde.

So installieren Sie die System Center Operations Manager-Konsole:

1.  Doppelklicken Sie auf den System Center Operations Manager-Setupmedien auf **SetupOM. exe**.

2.  Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Voraussetzungen prüfen**.

3.  Wählen Sie in der System Center Operations Manager-Voraussetzungs Anzeige die zu installierden System Center-Komponenten aus: (**Server**; **Console**; und **PowerShell**), und klicken Sie dann auf **überprüfen**. Stellen Sie sicher, dass keine Blockierungsprobleme gemeldet wurden, und klicken Sie dann auf **Schließen**. Wenn ein Blockierungsproblem gemeldet wurde, beheben Sie das Problem, und klicken Sie dann auf **überprüfen** , um die erforderlichen Tests erneut auszuführen.

4.  Klicken Sie in System Center Operations Manager-Setup auf **Operations Manager installieren**.

5.  Klicken Sie im System Center Operations Manager-Setup-Assistenten auf der Seite **Willkommen beim Setup-Assistenten von System Center Operations Manager** auf **weiter**.

6.  Wählen Sie auf der Seite **Endbenutzer-Lizenzvertrag** **die Option Ich akzeptiere die Bedingungen im Lizenzvertrag** aus, und klicken Sie dann auf **weiter**.

7.  Geben Sie auf der Seite **Produktregistrierung** ihren Namen in das Feld **Benutzername** und den Namen Ihrer Organisation in das Feld **Organisation** ein. Geben Sie Ihren System Center Operations Manager-Product Key in das Feld **Geben Sie Ihren 25-stelligen CD-Schlüssel** ein, und klicken Sie dann auf **weiter**.

8.  Wählen Sie auf der Seite **benutzerdefinierte Einrichtung** die zu installierbaren System Center-Optionen aus, und klicken Sie dann auf **weiter**. Wählen Sie **Verwaltungs Server**, **Benutzeroberflächen**und **Web Console** aus, die installiert werden sollen. Die **Datenbank** sollte nicht ausgewählt sein und sollte nicht installiert werden.

9.  Überprüfen Sie auf der Seite **SC-Datenbankserverinstanz** , ob der Name des Computers, auf dem die Operations Manager-Datenbanken installiert sind, im Feld **System Center-Datenbankserver** angezeigt wird. Klicken Sie auf **Weiter**.

10. Wählen Sie auf der Seite **Verwaltungs Server-Aktionskonto** die Option **Domäne oder lokales Computerkonto** aus, und geben Sie dann die entsprechenden Werte in die Felder **Benutzerkonto**, **Kennwort**und **Domäne oder lokaler Computer** ein. Klicken Sie auf **Weiter**.

11. Wählen Sie auf der Seite **SDK-und Konfigurationsdienstkonto** die Option **Domäne oder lokales Computerkonto** aus, und geben Sie dann die entsprechenden Werte in die Felder **Benutzerkonto**, **Kennwort**und **Domäne oder lokaler Computer** ein. Klicken Sie auf **Weiter**.

12. Klicken Sie auf der Seite **Operations Manager-Fehlerberichte** auf **weiter**.

13. Klicken Sie auf der Seite **Programm zur Verbesserung der Benutzerfreundlichkeit** auf **weiter**.

14. Klicken Sie auf der Seite **bereit zum Installieren des Programms** auf **Installieren**.

15. Deaktivieren Sie auf der Seite **System Center Operations Manager-Setup abschließen** das Kontrollkästchen **Verschlüsselungsschlüssel sichern** , und **Starten Sie die Kontrollkästchen** für die Konsole, und klicken Sie dann auf **Fertig stellen**.

16. Klicken Sie in System Center Operations Manager-Setup auf **Beenden**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Installieren von System Center Reporting Services

Nachdem Sie die System Center Operations Manager-Konsole installiert und konfiguriert haben, müssen Sie System Center Reporting Services installieren. Wenn Sie SQL Server 2008 R2 als Ihre Operations Manager-Back-End-Datenbank verwenden, müssen Sie zunächst eine temporäre Änderung an der Sicherheitsgruppe vornehmen, die mit SQL Server Reporting Services verknüpft ist. Wenn Sie SQL Server 2008 R2 verwenden, müssen Sie die folgenden Schritte ausführen:

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Erweitern Sie im Server-Manager **Konfiguration**, erweitern Sie **lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Suchen Sie die folgende Gruppe, wobei ATL-SC-001 den Namen Ihres Computers darstellt und ARCHINST die SQL Server-Instanz für die System Center-Datenbank darstellt: **SQLServerReportServerUser $ ATL-SC-001\_$ MSRS10 50. ARCHINST**.

4.  Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**. Benennen Sie die Gruppe um, indem Sie ** \_50** aus dem Gruppennamen löschen. Beispiel: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Schließen Sie den Server-Manager.

An diesem Punkt sind Sie bereit, System Center Reporting Services zu installieren. Gehen Sie dazu so vor:

1.  Doppelklicken Sie auf dem Setup Medium System Center Operations Manager 2007 R2 auf **SetupOM. exe**.

2.  Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Operations Manager-Berichterstellung installieren**.

3.  Klicken Sie im Setup-Assistenten von System Center Operations Manager 2007 R2 auf der Seite **Willkommen bei Operations Manager-Berichterstellung** auf **weiter**.

4.  Klicken Sie auf der Seite **Endbenutzer-Lizenzvertrag** auf **Ich akzeptiere die Bedingungen des Lizenzvertrags** und dann auf **weiter**.

5.  Stellen Sie auf der Seite **Produktregistrierung** sicher, dass Ihr Name und der Name Ihrer Organisation in den Feldern **Benutzername** und **Organisation** angezeigt werden, und klicken Sie dann auf **weiter**.

6.  Klicken Sie auf der Seite **benutzerdefinierte Einrichtung** auf **Berichts Server** , und wählen Sie **Diese Komponente aus, und alle abhängigen Komponenten werden auf dem lokalen Laufwerk installiert**. Klicken Sie auf **Data Warehouse** , und wählen Sie **Diese Komponente steht nicht zur Verfügung**, und klicken Sie dann auf **weiter**.

7.  Geben Sie auf der Seite **mit dem Stammverwaltungsserver verbinden** den Namen Ihres Operations Manager-Stammverwaltungsservers im Feld **Stamm Verwaltungs** Server ein, und klicken Sie dann auf **weiter**.

8.  Geben Sie auf der Seite **Verbindung mit dem Operations Manager-Data Warehouse herstellen** die SQL Server-Instanz ein, in der sich Ihr Data Warehouse im Feld **SQL Server-Instanz** befindet. (Wenn sich das Data Warehouse in der Standardinstanz befindet, geben Sie einfach den Servernamen ein, beispielsweise: ATL-SQL-001.) Überprüfen Sie, ob der Datenbankname **OperationsManagerDW** im Feld **Name** angezeigt wird, und dass Port **1433** im Feld **SQL Server-Port** angezeigt wird. Klicken Sie auf **Weiter**.

9.  Wählen Sie auf der Seite **SQL Server-Berichterstattungs Instanz** Ihren SQL Server-Berichtsserver aus der Dropdownliste **SQL Server Reporting Services-Server eingeben** aus, und klicken Sie dann auf **weiter**.

10. Geben Sie auf der Seite **Data Warehouse-Konto schreiben** den Namen und das Kennwort des Benutzers ein, dem zunächst Schreibberechtigungen für das Data Warehouse in den Feldern **Benutzerkonto** und **Kennwort** zugewiesen werden sollen. Wählen Sie die Domäne des Benutzers aus der Dropdownliste **Domäne** aus, und klicken Sie dann auf **weiter**.

11. Geben Sie auf der Seite **Datenleser Konto** den Namen und das Kennwort des Benutzerkontos ein, das verwendet werden soll, wenn SQL Reporting Services das Data Warehouse in den Feldern **Benutzerkonto** und **Kennwort** abfragt. Wählen Sie die Kontodomäne in der Dropdownliste **Domäne** aus, und klicken Sie dann auf **weiter**.

12. Klicken Sie auf der Seite **operative Daten Berichte** auf **weiter**.

13. Klicken Sie auf der Seite **Microsoft Update** auf **weiter**.

14. Klicken Sie auf der Seite **bereit zum Installieren des Programms** auf **Installieren**.

15. Klicken Sie auf der Seite **abschließen des Setup-Assistenten für die Operations Manager-Berichtskomponenten** auf **Fertig stellen**.

16. Klicken Sie in System Center Operations Manager 2007 R2-Setup auf **Beenden**.

Nachdem Sie die System Center-Berichterstellung installiert haben, verwenden Sie das folgende Verfahren, um den Namen der Sicherheitsgruppe zurückzusetzen, die der SQL Server-Berichterstellung zugeordnet ist. Diese Vorgehensweise ist wiederum nur erforderlich, wenn Sie SQL Server verwenden:

1.  Klicken Sie auf **Start**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.

2.  Erweitern Sie im Server-Manager **Konfiguration**, erweitern Sie **lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.

3.  Suchen Sie die folgende Gruppe, wobei ATL-SC-001 den Namen Ihres Computers darstellt und ARCHINST die SQL Server-Instanz für die Archivierungs-und Überwachungsdatenbanken darstellt: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Klicken Sie mit der rechten Maustaste auf die Gruppe, und klicken Sie dann auf **Umbenennen**. Benennen Sie die Gruppe um, indem Sie ** \_50** am Ende des Gruppennamens direkt vor dem Namen der SQL Server-Instanz hinzufügen. Beispiel: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Schließen Sie den Server-Manager.

Wenn die System Center-Betriebskonsole geöffnet ist, müssen Sie die Anwendung schließen und dann erneut starten. Wenn Sie dies nicht tun, wird die Registerkarte " **Berichterstattung** " nicht auf der Benutzeroberfläche der Betriebskonsole angezeigt. Beachten Sie, dass es nach dem ersten Neustart der Betriebskonsole einige Minuten dauern kann, bis alle Überwachungsberichte auf der Registerkarte **Berichterstattung** angezeigt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

